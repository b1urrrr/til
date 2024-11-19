## [안드로이드 View의 생명주기를 이해하자](https://velog.io/@haero_kim/Android-View-%EC%9D%98-%ED%95%9C-%ED%8F%89%EC%83%9D-%EC%82%B4%ED%8E%B4%EB%B3%B4%EA%B8%B0)
### View가 그려지는 방식
- 액티비티 `onCreate()` 내부의 `setContentView()`를 통해 루트 노드 전달
- 액티비티로부터 전달된 루트 노드부터 리프 노드까지 Top-down 방식으로 레이아웃 그리기
- Measure, Layout 두 단계로 구성
### Measure 단계
- `measure()` 함수로 구성
- 모든 뷰가 각각 자신의 크기 측정값 저장
- 뷰의 `measure()` 반환 이후 자식뷰들의 값과 함께 `getMeasuredWidth()` 및 `getMeasuredHeight()` 값 설정
- 부모 뷰는 자식 뷰에게 두 번 이상의 `measure()` 호출 가능
### Layout 단계
- layout() 함수로 구성
- Measure 단계에서 측정한 크기를 사용하여 모든 자식 뷰 위치 배정
<br>

## View Lifecycle
![view_lifecycle](https://github.com/user-attachments/assets/079dc610-8b5d-4486-a99e-a5b82704f58a)
### 1. `constructor()`
> 생성자에 의해 생명 주기 시작
### 2. `onAttachedToWindow()`
> 부모 뷰가 `addView()`를 호출하여 뷰가 윈도우에 붙을 때 호출
- 뷰를 그리기 위한 Surface 부여
- 리소스 할당 및 리스너 설정 가능
### 3. `onMeasure()`
> `measure()` 콜백 함수로, 부모 뷰는 모든 자식 뷰의 `measure()`를 호출하고 자신의 크기 결정
### 4. `onLayout()`
> `layout()` 콜백 함수로, 뷰의 크기와 위치를 지정하여 화면에 배치한 후 호출
- 뷰가 그려지기 전 단계
### 5. `dispatchToDraw()`
> 뷰가 다시 그려져야 할 경우에 자식 뷰들도 다시 그려지도록 명령
### 6. `onDraw()`
> 실제로 뷰를 그리는 단계
### 6-1. `invalidate()`
> 뷰의 속성이 변경되어 View를 다시 그리기 위해 호출하는 함수
### 6-2. `requestLayout()`
> 뷰의 크기 변화가 발생할 경우 레이아웃 배치를 확인하기 위해 크기 측정부터 다시 실행하는 함수
