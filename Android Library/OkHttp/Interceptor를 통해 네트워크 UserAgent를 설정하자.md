## [Interceptor를 통해 네트워크 UserAgent를 설정하자](https://medium.com/mobile-app-development-publication/setting-useragent-for-android-network-9daf5264ef3f)
- 안드로이드는 OkHttp에서 UserAgent를 "okhttp/버전" 형식으로 설정
    - iOS는 Alamofire에서 세부적으로 UserAgent 정보를 설정
    - 안드로이드도 세부적인 정보를 UserAgent에 담기 위해서 Interceptor 활용

### 구현 예시
```
class UserAgentInterceptor @Inject(
    @ApplicationContext private val context: Context,
) : Interceptor {
    private val userAgent: String = 
        "${context.packageManager.getApplicationLabel(context.applicationInfo)}/" +
        "${VERSION_NAME} " +
        "(${context.packageName}; " +
        "build:${VERSION_CODE} " +
        "Android SDK ${Build.VERSION.SDK_INT}) " +
        "${Build.BRAND} ${Build.MODEL}"

    @Throws(IOException::class)
    override fun intercept(chain: Interceptor.Chain): Response {
        val requestWithUserAgent = chain.request().newBuilder()
            .header(USER_AGENT, userAgent)
            .build()

        return chain.proceed(requestWithUserAgent)
    }

    companion object {
        private const val USER_AGENT = "User-Agent"
        ...
    }
}
```
