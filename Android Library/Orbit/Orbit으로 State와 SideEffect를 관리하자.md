## Orbit으로 State와 SideEffect를 관리하자
### Orbit이란?
> Compose에서 Coroutine Block을 통해 State와 SideEffect를 관리하는 라이브러리
### Orbit 주요 개념
- **container** : State와 Side Effect를 관리하는 공간으로, 주로 ViewModel과 함께 사용
- **reduce** : State 값을 변경하는 스코프 함수
- **postSideEffect** : Side Effect를 발생하는 함수
- **intent** : `reduce`와 `postSideEffect`를 호출하는 Coroutine Block
### Orbit의 장점
- 효율적인 MVI 패턴 구현
- 사이드 이펙트 관리하는 로직 집약
- 상태 변경 및 사이드 이펙트 관리 로직 가독성 향상
- 상태 변경에 대한 용이한 비동기 처리
