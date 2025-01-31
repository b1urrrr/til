## [`DisposableEffect`](https://developer.android.com/develop/ui/compose/side-effects#disposableeffect)를 통해 생명주기에 따라 정리가 필요한 사이드 이펙트를 처리하자
- 메모리 누수 및 기타 성능 문제 예방의 효과
### `DisposableEffect` 동작 방식
```
DisposableEffect(key) {
    // 정리가 필요한 효과 초기화
    onDispose {
        // 효과에 대한 정리 (Composable 제거 시 호출)
    }
}
```
- Composable이 UI 계층에서 제거될 때 `onDispose` 블록 호출
- 초기에는 초기화 로직만 수행
- key값이 바뀔 때마다 `onDispose` 블록 호출 후 초기화 로직 재호출
- `onDispose` 블록은 항상 람다식의 최하단에 위치 (빌드 오류로 강제됨)
### 구현 예시
```
@Composable
fun HomeScreen(
    lifecycleOwner: LifecycleOwner = LocalLifecycleOwner.current,
    onStart: () -> Unit, // Send the 'started' analytics event
    onStop: () -> Unit // Send the 'stopped' analytics event
) {
    val currentOnStart by rememberUpdatedState(onStart)
    val currentOnStop by rememberUpdatedState(onStop)

    DisposableEffect(lifecycleOwner) {
        val observer = LifecycleEventObserver { _, event ->
            if (event == Lifecycle.Event.ON_START) {
                currentOnStart()
            } else if (event == Lifecycle.Event.ON_STOP) {
                currentOnStop()
            }
        }
        lifecycleOwner.lifecycle.addObserver(observer)

        onDispose {
            lifecycleOwner.lifecycle.removeObserver(observer)
        }
    }
    ...
}
```
