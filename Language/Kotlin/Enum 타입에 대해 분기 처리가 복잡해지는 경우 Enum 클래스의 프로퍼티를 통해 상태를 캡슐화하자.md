## Enum 타입에 대해 분기 처리가 복잡해지는 경우 Enum 클래스에 프로퍼티를 추가하여 상태를 캡슐화하자
- Enum의 함수 또는 프로퍼티를 활용하여 상수 특성 캡슐화 가능
- 가독성 및 유지보수성 증가 효과
- 경우에 따라 지나치게 복잡한 enum class는 sealed class로 리팩토링 권장
### 프로퍼티 추가 없이 Enum 타입을 분기 처리하는 예시
```
Text(
    text = "text",
    color = if (EnumState.Selected) Green else Gray,
)
```
### Enum 클래스에 프로퍼티를 추가하여 상태를 캡슐화하는 예시
```
Text(
    text = "text",
    color = EnumState.Selected.color,
)
```
