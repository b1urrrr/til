## `@Throws`를 사용하는 경우
- 함수가 특정 Exception을 `throw`하는 것을 명시하고 강제해야하는 경우
### 사용 예시
```
@Throws(IOException::class)
fun test() { ... }
```
### 컴파일 코드
```
public static final void test() throws IOException { ... }
```
