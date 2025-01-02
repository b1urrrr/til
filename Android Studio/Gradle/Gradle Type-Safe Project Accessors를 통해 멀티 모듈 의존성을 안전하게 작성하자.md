## [Gradle Type-Safe Project Accessors를 통해 멀티 모듈 의존성을 안전하게 작성하자](https://medium.com/@ndusundayDev/simplify-dependency-declarations-with-gradles-type-safe-project-accessors-2227859330fe)
- settings gradle 파일에 `enableFeaturePreview("TYPESAFE_PROJECT_ACCESSORS")` 코드 추가하여 설정
- gradle 7.0 이상에서 사용 가능
- 모듈명을 하드 코딩이 아닌 자동 완성 기능을 통해 작성 가능
- 유지보수성 증가 효과
### 기존 방식 예시
```
implementation project(":data")
```
### Type-safe project accessors 사용 예시
```
implementation(projects.data)
```
