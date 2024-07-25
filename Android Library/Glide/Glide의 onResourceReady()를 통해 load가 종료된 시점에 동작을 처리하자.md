## Glide의 `onResourceReady()`를 통해 load가 종료된 시점에 동작을 처리하자
- `Glide.into()` 함수 내부에 `onResourceReady()`를 구현한 CustomTarget 객체를 넘겨 load가 종료 또는 실패한 시점에 동작 처리 가능
### 구현 예시
```
Glide.with(requireView())
    .load(imgUrl)
    .into(object : CustomTarget<Drawable>() {
        override fun onResourceReady(
            resource: Drawable,
            transition: Transition<in Drawable>?
        ) {
            // Do something with the Drawable here.
        }

        override fun onLoadCleared(placeholder: Drawable?) {
            // Remove the Drawable provided in onResourceReady from any Views and ensure no references to it remain.
        }
    })
```
