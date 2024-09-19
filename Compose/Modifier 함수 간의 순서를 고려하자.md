## Modifier 함수 간의 순서를 고려하자
- Modifier 함수의 순서에 따라 UI가 달라지므로 순서에 주의 필요
  - EX) `clickable()`, `background()`
- `clickable()`의 ripple 효과를 제거하기 전에 테스트를 수행하여 터치 타겟을 확인하는 것이 좋음
