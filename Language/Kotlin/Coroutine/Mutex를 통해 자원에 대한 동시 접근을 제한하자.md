## [Mutex](https://kotlinlang.org/api/kotlinx.coroutines/kotlinx-coroutines-core/kotlinx.coroutines.sync/-mutex/)를 통해 자원에 대한 동시 접근을 제한하자
- Mutex의 상태 : locked, unlocked
- 재진입 불가능한 성질(Non-Reentrant)을 가짐
- locked 상태에서 `lock` 호출 시 suspend 처리
- 코루틴 중단 시 mutex 해제가 불가능
  - 락을 두 번 걸지 않고 중단 함수를 호출하지 않도록 주의
### Mutex 제공 함수
- `lock` : lock this mutex
- `unlock` : unlock this mutex
- `withLock` : `lock`와 `unlock`을 자동적으로 수행하는 스코프 함수
  - 예외 발생 시 자동적으로 `unlock` 처리하여 안정적으로 동시 접근 문제 해결 가능
