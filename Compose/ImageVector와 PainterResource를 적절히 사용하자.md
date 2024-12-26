## [ImageVector와 PainterResource를 적절히 사용하자](https://proandroiddev.com/imagevector-vs-painterresources-under-the-hood-6c002abbaaf1)
### ImageVector
- Image 파라미터가 변화해도 ImageVector에 대한 리컴포지션 미발생
  - ImageVector 클래스는 `@Immutable`
  - imageVector 파라미터를 사용하는 Image는 `@NonRestartableComposable`
- 벡터 이미지만 처리 가능
### PainterResource
- Image 파라미터 변화 시, painter에 대한 리컴포지션 발생
- 다양한 형식의 이미지(vector, bitmap, png, jpg) 사용 가능
- `@NonRestartableComposable`을 활용한 커스텀 컴포넌트로 성능 문제 해결 가능
### 커스텀 ImagePainter 예시
```
@NonRestartableComposable
@Composable
fun ImagePainter(
    painter: Painter,
    contentDescription: String?,
    modifier: Modifier = Modifier,
    alignment: Alignment = Alignment.Center,
    contentScale: ContentScale = ContentScale.Fit,
    alpha: Float = DefaultAlpha,
    colorFilter: ColorFilter? = null
) {
    val semantics = if (contentDescription != null) {
        Modifier.semantics {
            this.contentDescription = contentDescription
            this.role = Role.Image
        }
    } else {
        Modifier
    }

    // Explicitly use a simple Layout implementation here as Spacer squashes any non fixed
    // constraint with zero
    Layout(
        {},
        modifier.then(semantics).clipToBounds().paint(
            painter,
            alignment = alignment,
            contentScale = contentScale,
            alpha = alpha,
            colorFilter = colorFilter
        )
    ) { _, constraints ->
        layout(constraints.minWidth, constraints.minHeight) {}
    }
}
```
