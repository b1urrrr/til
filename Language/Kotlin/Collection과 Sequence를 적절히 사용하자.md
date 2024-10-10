## [Collection과 Sequence를 적절히 사용하자](https://bcp0109.tistory.com/359)
### Lazy Evaluation이란?
> 특정 로직 또는 연산을 즉시 수행하지 않고 실제 사용되기 전까지 미루는 것
- 중간 단계의 결과 생략

### Eager Evaluation
> 특정 로직 또는 연산을 연산을 즉시 수행하는 것

### Collection과 Sequence의 연산 방식
- Collection : Eager Evaluation
- Sequence : Lazy Evaluation

### Sequence를 사용해야하는 경우
- 불필요한 연산을 생략하여 성능을 향상시켜야 하는 경우

### Collection을 사용해야하는 경우
- 적은 데이터 또는 연산이 단순한 컬렉션을 처리해야하는 경우
    - Sequence는 오버헤드 발생 가능
