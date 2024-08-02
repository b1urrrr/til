## 웹뷰의 `shouldOverrideUrlLoading()`을 통해 웹 페이지 또는 intent를 처리하자
- 웹에서 새로운 웹 페이지의 url 또는 인텐트(EX. 특정 앱 실행)를 전달할 경우에 대해 적절히 처리 필요
- 불필요해보여도 웹 내부 동작이 바뀌는 경우를 고려하여 사전에 처리하는 것이 안정적
### 구현 예시
```
private class CustomWebViewClient() : WebViewClient() {
    override fun shouldOverrideUrlLoading(
        view: WebView?,
        request: WebResourceRequest?,
    ) {
        val url = request?.url.toString()

        when {
            url.startsWith("https://") || url.startsWith("http://") -> {
                // 웹 페이지 url 처리
            }

            url.startsWith("intent:") -> {
                // intent 처리
            }
        }
    }
}
```
