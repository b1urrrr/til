## [액티비티 launchMode로 singleTask나 singleInstance를 지정하는 것을 지양하자](https://developer.android.com/guide/topics/manifest/activity-element?hl=ko#lmode)
- 일반적으로 launchMode로 `standard`나 `singleTop`을 설정하는 것이 적합
- 특정 상황에서 `singleTask`나 `singleInstance` 도 사용성에 맞게 사용하면 충분히 사용 가능
### `singleTask`란?
- 동일한 Task 상에서 하나의 액티비티만 존재
- onNewIntent() 함수 호출
- 상단에 존재하지 않아도 재사용하며 사이에 존재하는 액티비티 모두 clear
- 주의점 : 백그라운드 상태의 앱을 아이콘 클릭으로 재실행하는 경우, 런처 액티비티부터 재시작 (UX 저하)
### `singleInstance`란?
- 단일 Task에 최상단으로 존재
- 기존에 띄워진 액티비티를 명시적으로 해제해야 하는 이슈 존재 (유지보수성 저하)
- 백 버튼 클릭 시 앱 종료되므로 스택 관리가 어려움
