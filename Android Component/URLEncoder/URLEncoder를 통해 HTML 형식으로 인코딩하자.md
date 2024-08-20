## URLEncoder를 통해 HTML 형식으로 인코딩하자
### URLEncoder란?
- `encode()` 함수를 통해 문자열을 HTML 형식으로 인코딩하여 반환하는 클래스
- String과 CharSet 타입을 파라미터로 전달하는 함수가 가장 안정적
### 구현 예시
```
URLEncoder.encode(info, StandardCharsets.UTF_8)
```
