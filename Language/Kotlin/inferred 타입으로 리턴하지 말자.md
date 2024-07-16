## inferred 타입으로 리턴하지 말자
- inferred 타입은 불필요한 제한을 증가시키고 예측하지 못한 결과를 야기할 수 있음
- 외부 API 구현 시 명시적으로 확인 가능한 리턴 타입을 반환하는 것이 안정적
- 타입을 확실하게 지정해야 하는 경우, 명시적으로 타입 지정하는 것이 원칙

### 예시
```
val DEFAULT_CAR: Car = Fiat126P()

interface CarFactory {
    fun produce(): Car = DEFAULT_CAR
}
```
- `DEFAULT_CAR` 타입이 명시적이라는 판단으로 함수의 리턴 타입 제거
- `DEFAULT_CAR`는 타입 추론이 될 것이라는 판단으로 상수 타입 제거
```
val DEFAULT_CAR = Fiat126P()

interface CarFactory {
    fun produce() = DEFAULT_CAR
}
```
- Fiat126P 외의 자동차 생산 불가능
- 특히, 라이브러리 또는 모듈 내부 코드를 수정할 수 없는 경우 명시적인 타입으로 수정 불가능
