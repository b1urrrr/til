## Spread 연산자(`*`)를 이용해 배열이나 컬렉션 요소를 개별 인자로 변환하자
### [Spread 연산자(`*`)](https://kotlinlang.org/docs/functions.html#named-arguments)란?
> 배열이나 컬렉션 앞에 별 기호(`*`)를 붙여 요소들을 개별 인자로 나열하는 Kotlin 연산자
- 함수 호출, 배열 조작 등의 동작을 가독성 높은 코드로 작성 가능
### 사용 예시
- 여러 인자를 전달하는 함수를 호출하는 경우
```
val numbers = arrayOf(1, 2, 3, 4, 5)
println(*numbers)

// 출력 : 1 2 3 4 5
```
- 배열을 결합하는 경우
```
val arrayA = arrayOf(1, 2, 3)
val arrayB = arrayOf(*arrayA, 4, 5)
```
- `varargs` 타입의 인자를 전달하는 경우
```
getString("message", *formatArgs.toTypedArray())
```
### 주의 사항
- 배열 복사를 기반으로 동작하기 때문에 메모리 사용량 증가에 유의
- 큰 배열이나 컬렉션을 스프레드 하는 경우 성능에 주의
- 이 외에도 성능에 민감한 기능을 구현하는 경우 다른 방법 고려 권장
