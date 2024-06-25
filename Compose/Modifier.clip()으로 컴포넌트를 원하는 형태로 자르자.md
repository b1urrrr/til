## [`Modifier.clip()`](https://developer.android.com/reference/kotlin/androidx/compose/ui/Modifier#(androidx.compose.ui.Modifier).clip(androidx.compose.ui.graphics.Shape))으로 컴포넌트를 원하는 형태로 자르자
- `Modifier.clip()`으로 인자에 지정한 Shape에 따라 컴포넌트를 자를 수 있음
### [사용 예시](https://coil-kt.github.io/coil/compose/#asyncimage)
```
AsyncImage(
    model = ImageRequest.Builder(LocalContext.current)
        .data("https://example.com/image.jpg")
        .build(),
    contentDescription = stringResource(R.string.description),
    contentScale = ContentScale.Crop,
    modifier = Modifier.clip(CircleShape)
)
```
- Coil 사용 시 로드 이미지를 컴포넌트 크기에 알맞는 Shape으로 잘라 사용하는 경우
