## sealed class와 enum class를 적절히 사용하자
- 이전에는 enum class를 사용할 경우, 불필요한 else문 처리가 필요하여 sealed class 사용이 권장됨
- 최신 코틀린 버전에서는 enum class도 else문 처리를 할 필요가 없으며, 안드로이드 스튜디오에서도 경고를 노출하지 않음
```
클래스에 추가 정보를 저장하지 않거나 여러 인스턴스를 생성하지 않아도 되는 경우에는 enum class를 사용하는 것이 적합
```
