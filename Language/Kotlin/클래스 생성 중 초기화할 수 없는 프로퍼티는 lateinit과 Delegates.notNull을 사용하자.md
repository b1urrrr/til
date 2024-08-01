## 클래스 생성 중 초기화할 수 없는 프로퍼티는 `lateinit`과 `Delegates.notNull`을 사용하자
- 클래스 생성 중 초기화할 수 없는 경우 일반적으로 `lateinit` 활용
- JVM에서 기본 타입과 연결된 타입으로 프로퍼티를 초기화하는 경우 프로퍼티 위임(`Delegates.notNull`) 활용
  - **기본 타입 EX)** Int, Long, Double, Boolean 타입
  - **구현 EX)** `private var test: Int by Delegates.notNull()`
  - `lateinit`보다 느리게 동작
- 사용하기 전 반드시 초기화가 되어 있을 경우에만 사용
