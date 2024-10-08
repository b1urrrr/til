## 비전역적인 ModalBottomSheet 사용을 지양하자
- Fragment에서 ModalBottomSheet의 리소스를 관리하는 등 전역적이지 않은 ModalBottomSheet 사용은 지양할 것
### Fragment에서 ModalBottomSheet 사용하면 안 되는 이유
- **생명주기 관리의 복잡성 증가**
  - 프래그먼트 상태 변경 시 ModalBottomSheet 생명주기 관리가 어려움
  - 화면 전환 시 ModalBottomSheet가 닫히거나 재생성될 수 있음
- **백스택 처리의 어려움**
  - 프래그먼트의 백스택 관리 시스템과 모달 시트와의 상호작용이 충돌할 수 있음
- **UI 복잡도 증가**
  - ModalBottomSheet가 특정 프래그먼트에 의존적으로 동작하여 재사용성과 유지보수성 문제 야기
### 대안
- Activity 또는 ViewModel에서 ModalBottomSheet의 리소스 관리
- Navigation Component 활용
