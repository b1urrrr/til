## Extra를 전달 받을 때 SavedStateHandle을 활용하자
### SavedStateHandle이란?
> 화면에 필요한 데이터를 안전하게 저장할 수 있는 Handle
- 시스템이 프로세스를 종료하더라도 동일한 정보 유지
- ViewModel에만 저장하는 경우, 메모리 내에 존재하기 때문에 프로세스 종료까지 안전하지 않음
- ViewModel의 생성자 매개변수를 통해 주입
