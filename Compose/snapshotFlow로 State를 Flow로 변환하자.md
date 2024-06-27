## `snapshotFlow`로 State를 Flow로 변환하자
- snapshowFlow는 State<T> 객체를 Cold Flow로 변환
### [사용 예시](https://developer.android.com/develop/ui/compose/layouts/pager?hl=ko#get-notified)
```
LaunchedEffect(pagerState) {
    snapshotFlow { pagerState.currentPage }.collect { page ->
        // Do something with each page change
    }
}
```
- Flow가 제공하는 기능을 사용해야하는 경우
- 페이지 변경 시 애널리틱스 이벤트 전송 등 변수의 변경사항을 관찰하고 반응해야하는 경우
