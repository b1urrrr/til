## `close` 대신 `use`를 사용하여 리소스를 해제하자
### 명시적으로 해제해야하는 리소스
- `AutoCloseable`을 상속받는 `Closeable` 인터페이스의 구현체 해당
- 가비지 컬렉터는 속도가 느리기 때문에 리소스 유지 비용을 최소화하기 위해 명시적으로 해제 필요
- EX) `InputStream`, `OutputStream`, `Connection`, `FileReader`, `BufferedReader`, `CSSParser`, `Socket`, `Scanner`
### `close`를 사용하는 경우
```
try {
    // reader 리소스 사용
} finally {
    reader.close()
}
```
- 복잡성 높음
- 리소스를 닫을 때 발생하는 예외 처리 불가능
- 하나의 오류만 전파 가능
### `use`를 사용하는 경우
```
reader.use { reader ->
    // reaer 리소스 사용
}
```
- 가독성 개선
- 모든 오류 전파 가능
### `useLines`를 사용하는 경우
```
File(path).useLines { lines ->
    // 파일 한 줄에 대한 처리
}
```
- 파일을 한 줄씩 읽어 들이는 경우 사용
