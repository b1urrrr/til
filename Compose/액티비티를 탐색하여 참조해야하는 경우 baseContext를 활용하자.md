## 액티비티를 탐색하여 참조해야하는 경우 baseContext를 활용하자
- LocalContext.current를 활용하는 경우 강제 타입 캐스팅으로 인한 문제 발생 가능
- baseContext를 활용하여 액티비티를 탐색하는 경우 더 안정적
### [구현 예시](https://github.com/google/accompanist/blob/6611ebda55eb2948eca9e1c89c2519e80300855a/permissions/src/main/java/com/google/accompanist/permissions/PermissionsUtil.kt#L99)
```
internal fun Context.findActivity(): Activity {
    var context = this
    while (context is ContextWrapper) {
        if (context is Activity) return context
        context = context.baseContext
    }
    throw IllegalStateException("Permissions should be called in the context of an Activity")
}
```
- while 문에 조건을 추가하여 무한루프 동작 예방
