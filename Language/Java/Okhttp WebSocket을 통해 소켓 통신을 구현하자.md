## OkHttp [WebSocket](https://square.github.io/okhttp/3.x/okhttp/okhttp3/WebSocket.html)을 통해 소켓 통신을 구현하자
### 1. Android Studio 설정
- AndroidManifest 인터넷 권한 허용
```
<uses-permission android:name="android.permission.INTERNET" />
```
- OkHttp 의존성 추가
```
dependencies {
    implementation 'com.squareup.okhttp3:okhttp:{latest_version}'
    ...
}
```
### Listener 구현체 생성
```
class TestSocketListener : WebSocketListener() {
    override fun onClosed(webSocket: WebSocket, code: Int, reason: String) {
        super.onClosed(webSocket, code, reason)
    }

    override fun onClosing(webSocket: WebSocket, code: Int, reason: String) {
        super.onClosing(webSocket, code, reason)
    }

    override fun onFailure(webSocket: WebSocket, t: Throwable, response: Response?) {
        super.onFailure(webSocket, t, response)
    }

    override fun onMessage(webSocket: WebSocket, text: String) {
        super.onMessage(webSocket, text)
    }

    override fun onMessage(webSocket: WebSocket, bytes: ByteString) {
        super.onMessage(webSocket, bytes)
    }

    override fun onOpen(webSocket: WebSocket, response: Response) {
        super.onOpen(webSocket, response)
    }
}
```
- `onClosed` : 소켓 연결 종료 시 호출되는 콜백 함수
- `onClosing` : 원격 서버로부터 소켓 연결 종료 메시지 수신 시 호출되는 콜백 함수
- `onFailure` : 메시지를 읽는 과정 또는 네트워크 상 오류로 인해 소켓이 닫히는 경우 호출되는 콜백 함수
- `onMessage` : 원격 서버로부터 메시지를 수신한 경우 호출되는 콜백 함수
- `onOpen` : 원격 서버와 소켓 연결이 완료된 경우 호출되는 콜백 함수
### WebSocket 객체 생성
```
private lateinit var webSocket: WebSocket

fun openSocket() {
    val request = Request
        .Builder()
	...
        .url(SOCKET_BASE_URL)
        .build()

    val listener: WebSocketListener = TestSocketListener()

    webSocket = okHttpClientBuilder.newWebSocket(
        request = request,
        listener = listener,
    )
}

fun sendMessage(message: String) {
    webSocket.send(message)
}

fun closeSocket() {
    webSocket.close(1000, null)
}
```
- `newWebSocket()` : 웹 소켓 객체 생성
- `send()` : 메시지 전송 요청
- `close()` : 소켓 닫기 요청

```
위와 같은 동작을 기반으로 프로덕트와 아키텍처에 적합하게 사용할 것
```
