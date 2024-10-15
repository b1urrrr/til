## Modifier.drawWithCache()를 통해 컴포저블 뷰를 Bitmap 이미지로 변환하자
### 컴포저블 뷰를 Bitmap 이미지로 변환하는 방법
1. Picture 객체 생성
```
val picture = remember { Picture() }
```
2. 컴포저블 뷰 영역 지정
```
Modifier.drawWithCache {
    val width = this.size.width.toInt()
    val height = this.size.height.toInt()
    onDrawWithContent {
        val pictureCanvas =
            androidx.compose.ui.graphics.Canvas(
                receiptPicture.beginRecording(
                    width,
                    height,
                )
            )
        draw(this, this.layoutDirection, pictureCanvas, this.size) {
            this@onDrawWithContent.drawContent()
        }
        receiptPicture.endRecording()

        drawIntoCanvas { canvas ->
            canvas.nativeCanvas.drawPicture(
                receiptPicture
            )
        }
    }
}
```
3. Bitmap 변환
```
picture.toBitmap()
```
