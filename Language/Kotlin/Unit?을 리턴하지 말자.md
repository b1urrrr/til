## `Unit?`을 리턴하지 말자
- Unit?은 Boolean으로 대체하는 것이 적합
### `Unit?`을 처리하는 코드
```
isValid ?: return
```
- 모호한 표현으로 오해의 소지 있음
- 예측하기 어려운 오류 발생 가능

### `Boolean`을 처리하는 코드
```
if (!isValid) return
```
- 개선된 가독성과 안정성
