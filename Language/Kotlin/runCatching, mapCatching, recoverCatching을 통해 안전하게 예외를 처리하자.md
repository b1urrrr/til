## runCatching, mapCatching, recoverCatching을 통해 안전하게 예외를 처리하자
- Result 클래스를 활용한 함수를 통해 간결하게 성공 또는 실패에 대한 처리 가능
### runCatching
> 코드 블록을 실행하고 발생한 예외를 Result 객체로 캡슐화
- 성공 : `Result.success(value)` 반환
- 실패 : `Result.failure(exception)` 반환
```
runCatching {
    ...
}.onSuccess { value ->
    ...
}.onFailure { exception ->
    ...
}
```
### mapCatching
> Result 객체의 값을 변환하여 반환하며, 예외 발생 시 실패 상태로 처리
```
runCatching {
    ...
}.mapCatching { value ->
    value.toInt()
}.onSuccess { value ->
    ...
}.onFailure { exception ->
    ...
}
```
### recoverCatching
> Result가 실패 상태일 때 예외 처리 후 새 값을 변환하며, 예외 처리 중 다시 예외 발생 시 실패 상태 유지
```
runCatching {
    ...
}.recoverCatching { exception ->
    ...
    value
}.onSuccess { value ->
    ...
}.onFailure { exception ->
    ...
}
```
### 활용 예시
```
fun parseNumber(input: String): Int {
    return runCatching { input.toInt() }
        .mapCatching { it * 2 }
        .recoverCatching { 0 }
        .getOrThrow() // 성공 시 값 반환, 실패 시 예외 던짐
}
```
- input이 "123"인 경우 : 246 반환
- input이 "abc"인 경우 : 0 반환
