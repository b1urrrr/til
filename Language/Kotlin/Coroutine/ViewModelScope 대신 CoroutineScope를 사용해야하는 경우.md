## ViewModelScope 대신 CoroutineScope를 사용해야하는 경우
- ViewModelScope는 ViewModel이 파괴될 경우 내부 동작이 취소됨
  - 내부적으로 `onClear()`에서 할당된 job을 `cancel()`함
- ViewModel이 파괴된 후에도 태스크가 진행되어야 한다면 CoroutineScope를 사용하는 것이 적합
