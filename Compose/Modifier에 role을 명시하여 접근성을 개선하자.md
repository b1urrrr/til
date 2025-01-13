## Modifier에 role을 명시하여 접근성을 개선하자
### [Role](https://developer.android.com/reference/kotlin/androidx/compose/ui/semantics/Role)이란?
- UI 요소의 역할을 명시적으로 설정할 때 사용되는 Modifier 속성
- 접근성 서비스 사용자에게 해당 요소가 어떤 유형의 인터페이스 요소인지 알려주고, 커스터마이징을 가능하게 함
- 역할이 정확하지 않고 모호한 경우, Role을 명시하지 않고 프레임워크가 자동으로 설정하도록 권장
### 활용 예시
```
@Composable
fun ExampleButton() {
    Box(
        modifier = Modifier
            .size(100.dp)
            .role(Role.Button)
            .clickable { 
                ...
            },
    ) {
        ...
    }
}
```
