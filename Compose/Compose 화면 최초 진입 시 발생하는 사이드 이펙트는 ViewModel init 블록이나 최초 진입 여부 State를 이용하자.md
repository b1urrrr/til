## Compose 화면 최초 진입 시 발생하는 사이드 이펙트는 ViewModel init 블록이나 최초 진입 여부 State를 이용하자
- `LaunchedEffect(Unit)`을 통해 사이드 이펙트를 처리하는 경우, pop back stack이 발생할 때마다 재호출
- 최초 진입 시 일회성으로 처리해야하는 사이드 이펙트는 다른 방법으로 처리 필요
- EX) 화면 진입 애널리틱스 로그, 최초 서버통신
### ViewModel `init` 블록에서 사이드 이펙트 발생
```
init {
    postSideEffect(InitialScreenLaunch)
}
```
### 최초 진입 여부 State 활용
```
LaunchedEffect(needRefresh) {
    if (needRefresh) { ... }
}
```
