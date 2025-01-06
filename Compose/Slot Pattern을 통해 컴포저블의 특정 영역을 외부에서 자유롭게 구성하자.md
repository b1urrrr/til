## [Slot Pattern을 통해 컴포저블의 특정 영역을 외부에서 자유롭게 구성하자](https://speakerdeck.com/wisemuji/songdo-compose-ui-johab-simhwa?slide=17)
### [Slot Pattern](https://developer.android.com/develop/ui/compose/layouts/basics#slot-based-layouts)이란?
> 컴포저블 람다를 함수 파라미터로 활용하여 특정 영역을 외부에서 구성할 수 있도록 하는 디자인 패턴
- 부모 컴포넌트는 자식 컴포넌트의 구체적인 구현에 대한 의존성 없이 UI 구조 정의 가능
  - 컴포넌트 간 결합 제거의 효과
- 대부분의 Compose Material Design Component에서 활용
### 구현 예시
```
@Composable
fun Scaffold(
    ...
    topBar: @Composable () -> Unit = {},
    bottomBar: @Composable () -> Unit = {},
    snackbarHost: @Composable () -> Unit = {},
    floatingActionButton: @Composable () -> Unit = {},
    content: @Composable (PaddingValues) -> Unit,
    ...
) { ... }
```
