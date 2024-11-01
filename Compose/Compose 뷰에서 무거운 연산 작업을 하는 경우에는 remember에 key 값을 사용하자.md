## [Compose 뷰에서 무거운 연산 작업을 하는 경우에는 remember에 key 값을 사용하자](https://velog.io/@mraz3068/Jetpack-Compose-Top-20-mistakes-6-10)
- 무거운 연산 작업에 Remember를 사용하는 경우, UI 성능 저하 발생 가능
- remember에 key 값을 사용하여 key 값이 변경되는 경우에만 연산 수행
- 주로 UI와 관련된 무거운 연산 작업에 적용
