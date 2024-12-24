## Compose 컴포넌트를 구현할 때 Material에 대한 의존성을 최소화하자
- Material 컴포넌트는 요구사항에 따라 커스텀이 어려운 상황이 발생하기 쉬움
  - EX) 컴포넌트 높이 변경
- foundation만을 사용하여 직접 컴포넌트를 커스텀하는 것이 확장성이 높음
  - 하지만 이는 리소스가 많이 듦
  - [Material에서 제공하는 영역을 파악하고 적절하게 매핑하는 것을 권장](https://thdev.tech/android/2023/01/25/Android-Compose-Scaffold/)
- 같은 맥락으로 실험적 단계의 accompanist 컴포넌트를 사용하기보다 직접 커스텀하여 사용하는 것을 권장
- 부수적으로 기기 호환성, 의존성 관리 용이성 측면에서의 효과도 존재
