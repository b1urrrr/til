### Repository를 인터페이스와 구현체로 분리시키는 이유
- 구현체만 교체시키며 간단하게 테스트 가능
- Domain 레이어와 Data 레이어 간의 의존성 제거 (클린 아키텍처 원칙 준수)
  - UseCase는 Domain 레이어에 존재하기 때문에 참조하는 Repository의 Interface는 Domain 레이어에 구현
  - 실제 데이터는 Data 레이어에 존재하기 때문에 Repository의 구현체는 Data 레이어에 구현
