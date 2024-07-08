## Compose의 상태는 메인 스레드에서만 접근하자
- Jetpack Compose의 상태 시스템은 기본적으로 메인(UI) 스레드에서 작동하도록 설계
- `SnapshotState`는 상태의 일관성을 유지하기 위해 특정 스레드에서의 접근을 강제
- 메인 스레드가 아닌 다른 스레드에서 SnapshotState에 접근하는 경우 `IllegalArgumentException(Detected multithreaded access to SnapshotStateObserver)` 발생
