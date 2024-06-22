## `withTimeout()`으로 코루틴 동작에 타임아웃을 설정하자
### 구현 코드
```
suspend fun <T> withTimeout(
    timeMillis: Long, 
    block: suspend CoroutineScope.() -> T
): T
```
- 타임아웃 발생 시 `TimeoutCancellationException`을 던짐
### 사용 예시
```
withTimeout(500L) {
    repository.getDataFromServer()
}
```
- API 호출에 시간 제한을 설정하는 경우
- 백그라운드 동작에 시간 제한을 설정하는 경우
