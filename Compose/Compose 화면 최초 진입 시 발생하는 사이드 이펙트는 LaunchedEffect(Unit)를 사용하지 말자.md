## Compose 화면 최초 진입 시 발생하는 사이드 이펙트는 LaunchedEffect(Unit)를 사용하지 말자
- `LaunchedEffect(Unit)`을 통해 사이드 이펙트를 처리하는 경우, pop back stack이 발생할 때마다 재호출
- 최초 진입 시 일회성으로 처리해야하는 사이드 이펙트는 다른 방법으로 처리 필요
- EX) 화면 진입 애널리틱스 로그, 최초 서버통신
### 대안1. ViewModel `init` 블록에서 사이드 이펙트 발생
```
init {
    postSideEffect(InitialScreenLaunch)
}
```
### 대안2. 최초 진입 여부 State 활용
```
LaunchedEffect(isInitialLaunch) {
    if (isInitialLaunch) { ... }
}
```
