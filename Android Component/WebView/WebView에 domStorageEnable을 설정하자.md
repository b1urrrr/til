## WebView에 domStorageEnable을 설정하자
- WebView.settings.[domStorageEnable](https://developer.android.com/reference/android/webkit/WebSettings#setDomStorageEnabled(boolean)) `true` 설정 권장
- 웹의 JS 쪽에서 `localStorage.getItem()` 이나 `sessionStorage.getItem()`을 호출할 경우, 해당 속성이 true로 설정되어 있지 않으면 url이 로드되지 않음
    - EX) 소프트베리 공식 홈페이지, 네이버 한자 사전 등
- 불필요해 보이는 설정도 url 또는 웹의 내부 동작이 바뀌는 경우를 고려하여 기본적인 설정을 해놓는 것이 안정적
