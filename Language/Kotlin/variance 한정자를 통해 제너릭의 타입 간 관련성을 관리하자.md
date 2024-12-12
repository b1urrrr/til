## variance 한정자를 통해 제너릭의 타입 간 관련성을 관리하자 
### 한정자가 없는 타입 파라미터 `T`
- **Invariant(불공변성)** : 타입 간 관련성이 없음
```
class Cup<T>
val anys: Cup<Any> = Cup<Int>() // 오류
val nothings: Cup<Nothing> = Cup<Int>() // 오류
```
### `out` 한정자가 있는 타입 파라미터 `T`
- **Convariant(공변성)** : `T` 타입이 서브타입인 경우 서브타입에 해당
```
class Cup<out T>
val anys: Cup<Any> = Cup<Int>() // OK
val nothings: Cup<Nothing> = Cup<Int>() // 오류
```
### `in` 한정자가 있는 타입 파라미터 `T`
- **Contravariant(반공변성)** : `T` 타입이 서브타입인 경우 슈퍼타입에 해당
```
class Cup<in T>
val anys: Cup<Any> = Cup<Int>() // 오류
val nothings: Cup<Nothing> = Cup<Int>() // OK
```
