## [`pauseTimers()`와 `resumeTimers()`를 통해 WebView의 리소스를 관리하자](https://docs.notifly.tech/ko/developer-guide/client-sdk/advanced/android-sdk-advanced#5-webview)
- 안드로이드는 앱이 백그라운드에 있을 때에도 WebView의 Javascript 코드가 실행됨
- 백그라운드 상태의 리소스 소모를 예방하기 위해 `pauseTimers()`와 `resumeTimers()` 사용
### 구현 예시
```
override fun onPause() {
    super.onPause()
    mNotiflyWebView?.pauseTimers()
}

override fun onResume() {
    super.onResume()
    mNotiflyWebView?.resumeTimers()
}
```
- 두 메소드 모두 하나의 WebView가 아닌 전역적으로 적용
