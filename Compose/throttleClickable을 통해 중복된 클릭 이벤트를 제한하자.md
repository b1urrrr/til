## throttleClickable을 통해 중복된 클릭 이벤트를 제한하자
- 기본으로 제공되는 `Modifier.clickable`은 짧은 시간 내 발생하는 중복 이벤트를 제한하지 않음
- API 호출 등의 중복 이벤트로 인해 이슈 발생 가능
- throttle 처리를 통해 특정 시간 내 발생한 중복 이벤트는 무시하도록 구현하여 안정성 개선 권장
### throttleClickable 구현 예시
```
@Composable
fun Modifier.throttleClickable(
    enabled: Boolean = true,
    onClickLabel: String? = null,
    role: Role? = null,
    throttleLevel: Long = DELAY_CLICK_LISTENER,
    onClick: () -> Unit,
): Modifier {
    val lastClickTime = remember { mutableLongStateOf(0L) }

    return this.clickable(
        enabled = enabled,
        onClickLabel = onClickLabel,
        role = role,
    ) {
        val currentTime: Long = System.currentTimeMillis()

        if (currentTime - lastClickTime.longValue >= throttleLevel) {
            onClick()
            lastClickTime.longValue = currentTime
        }
    }
}

@Composable
fun Modifier.throttleClickable(
    interactionSource: MutableInteractionSource?,
    indication: Indication?,
    enabled: Boolean = true,
    onClickLabel: String? = null,
    role: Role? = null,
    throttleLevel: Long = DELAY_CLICK_LISTENER,
    onClick: () -> Unit,
): Modifier {
    val lastClickTime = remember { mutableLongStateOf(0L) }

    return this.clickable(
        interactionSource = interactionSource,
        indication = indication,
        enabled = enabled,
        onClickLabel = onClickLabel,
        role = role,
    ) {
        val currentTime: Long = System.currentTimeMillis()

        if (currentTime - lastClickTime.longValue >= throttleLevel) {
            onClick()
            lastClickTime.longValue = currentTime
        }
    }
}
```
