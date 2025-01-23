## [PreviewParameterProvider](https://developer.android.com/reference/kotlin/androidx/compose/ui/tooling/preview/PreviewParameterProvider)를 통해 프리뷰의 상태별 파라미터를 주입하자
- 일반적으로 Preview는 필요한 State를 외부에서 주입하여 사용
- 대량의 파라미터가 필요하거나 하나의 파일에 여러 Preview가 필요한 경우 코드량이 비효율적으로 증가
### PreviewParameterProvider 구현 코드
```
interface PreviewParameterProvider<T> {
    val values: Sequence<T>
    val count get() = values.count()
}
```
- Preview에 주입할 샘플 데이터 타입을 시퀀스로 관리
- 한 번의 주입으로 여러 개의 프리뷰 구현 가능
### 구현 예시
```
class UserPreviewParameterProvider : PreviewParameterProvider<User> {
    override val values = sequenceOf(
        User("UserA"),
        User("UserB"),
        User("UserC"),
    )
}

@Preview
@Composable
fun UserProfilePreview(
    @PreviewParameter(UserPreviewParameterProvider::class) user: User,
) {
    UserProfile(user)
}
```
