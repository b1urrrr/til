## 사이드 이펙트가 발생하는 로직은 LaunchedEffect 스코프 내부에서 호출하자
- 컴포저블에서 사이드 이펙트가 발생하는 것은 최대한 지양
- 사이드 이펙트를 활용해야하는 경우도 존재
  - EX) 스낵바, 상태에 따라 화면 분기 등
- LaunchedEffect 내부에서 로직을 호출하면 Recomposition으로 인한 중복 호출을 예방할 수 있음
