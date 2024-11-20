## [Compose TextField의 비동기 입력을 구현하는 다양한 방법을 구분하자](https://github.com/orbit-mvi/orbit-mvi/issues/82)
- Compose TextField는 기본적으로 비동기 입력을 지원하지 않음
- 비동기 처리를 통해 입력값 처리 시 간헐적으로 커서 뒤에 새 입력값이 나타나는 현상 발생

### 방법1) remember를 통해 입력값 관리
```
val state = remember { mutableStateOf(initialValue) }

OutlinedTextField(
    value = state.value,
    onValueChange = {
        state.value = it
        onValueChange(it)
    }
)
```
- 코드 가독성 저하
- 데이터 처리 로직의 복잡성 증가

### 방법2) Orbit Container에서 Unconfined 디스패처 사용
```
container(
  ...
  settings = Container.Settings(intentDispatcher = Dispatchers.Unconfined)
)
```
- 텍스트 필드 입력값을 관리해야할 때마다 컨테이너 디스패처를 별도로 설정 필요 (보일러플레이트)
- 다른 디스패처를 사용하기 위해서 withContext 처리 필요
<br>

```
장단점을 고려하여 기능에 적합한 처리 방식을 선택할 것
더 좋은 방법이 있다면 알려주세요
```
