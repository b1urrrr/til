## require 함수를 통해 함수 argument에 제한을 걸자
### require 함수란?
> 제한을 확인하고 만족하지 못할 경우 예외를 던지는 조건 함수
- 매개변수의 값이 true인지 확인하고, false면 lazyMessage를 호출하고 `throw IllegalArgumentException`
- 입력 유효성 검사 코드라 함수의 가장 앞부분에 배치되어 쉽게 확인 가능
- 코드를 읽지 않는 사람을 위해 제한에 대한 별도 표시 필요
### 함수 원형
```
public inline fun require(value: Boolean): Unit {
    contract {
        returns() implies value
    }
    require(value) { "Failed requirement." }
}
```
```
public inline fun require(value: Boolean, lazyMessage: () -> Any): Unit {
    contract {
        returns() implies value
    }
    if (!value) {
        val message = lazyMessage()
        throw IllegalArgumentException(message.toString())
    }
}
```
