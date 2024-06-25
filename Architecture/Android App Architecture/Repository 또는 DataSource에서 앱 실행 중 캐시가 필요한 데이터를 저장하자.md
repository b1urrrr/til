## [Repository 또는 DataSource에서 앱 실행 중 캐시가 필요한 데이터를 저장하자](https://developer.android.com/topic/architecture/data-layer#caches)
- 앱 실행 기간동안 저장해야하는 데이터는 Repository와 DataSource에 저장하여 사용하는 것이 적합
- Repository와 DataSource에 따라 데이터가 싱글톤으로 관리됨에 유의
- 싱글톤으로 주입되지 않는 클래스에서 캐싱이 이루어질 경우 최신화 관련 오류가 생기기 쉬워 지양
  - EX) UseCase 
### 구현 예시
```
class NewsRepository(
  private val newsRemoteDataSource: NewsRemoteDataSource
) {
    private val latestNewsMutex = Mutex()

    private var latestNews: List<ArticleHeadline> = emptyList()

    suspend fun getLatestNews(refresh: Boolean = false): List<ArticleHeadline> {
        if (refresh || latestNews.isEmpty()) {
            val networkResult = newsRemoteDataSource.fetchLatestNews()
            latestNewsMutex.withLock {
                this.latestNews = networkResult
            }
        }

        return latestNewsMutex.withLock { this.latestNews }
    }
}
```
