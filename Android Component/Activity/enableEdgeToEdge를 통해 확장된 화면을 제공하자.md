## enableEdgeToEdge를 통해 확장된 화면을 제공하자
### [enableEdgeToEdge](https://developer.android.com/reference/kotlin/androidx/activity/ComponentActivity#(androidx.activity.ComponentActivity).enableEdgeToEdge(androidx.activity.SystemBarStyle,androidx.activity.SystemBarStyle))란?
> 상단 상태바와 하단 내비게이션 바를 투명하게 설정하여 화면이 디바이스 전체를 활용할 수 있도록 하는 ComponentActivity 확장 함수
- 액티비티의 `onCreate()`에서 호출
- 간편하게 넓은 화면 디스플레이 설정 및 시스템 표시줄 색상 변경 가능
- sdk 버전이 29보다 낮은 경우, 네비게이션 바가 반투명하게 노출될 수 있음에 주의
- 경우에 따라 시스템 창 영역을 고려하여 WindowInsets를 통해 레이아웃 배치 필요
