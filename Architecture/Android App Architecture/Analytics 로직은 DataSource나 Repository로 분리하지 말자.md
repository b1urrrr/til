## Analytics 로직은 DataSource나 Repository로 분리하지 말자
### DataSource로 분리하지 않는 이유
- Analytics Provider 라이브러리 내부에 DB에 접근하는 로직이 구현되어 있어 불필요
### Repository로 분리하지 않는 이유
- Domain 레이어에 외부 라이브러리의 의존성이 생길 수 있음
- Domain 레이어와 독립적인 클래스로 구현 필요
