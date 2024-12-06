## 단발성 이벤트 처리 시 Flow 대신 Channel을 사용하자
### Flow vs Channel
- Flow : 상태와 지속적 데이터 흐름에 적합
  - 여러 구독자 간 데이터 공유와 재처리 가능
- [Channel](https://kotlinlang.org/docs/channels.html) : 단발성 이벤트 전달에 최적화
  - Buffer가 가득 차면 작업dl 중단되고 구독자가 나타날 때까지 기다림
  - 이벤트의 한 번 처리와 소비를 보장
### Channel을 통해 단발성 이벤트 처리 시 효과
- 의도치 않은 이벤트의 중복 처리 및 누락 예방
