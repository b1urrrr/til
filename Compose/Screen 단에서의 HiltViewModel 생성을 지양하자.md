## [Screen 단에서의 HiltViewModel 생성을 지양하자](https://velog.io/@mraz3068/Jetpack-Compose-Top-20-mistakes-6-10)
### ViewModel이 Screen 생성자에 주입되는 경우의 문제점
- Screen 프리뷰 확인 불가능
- 고립된 UI Test 불가능
- Screen 사용 시 ViewModel을 초기화하기 위한 Hilt 문맥 파악 필요
