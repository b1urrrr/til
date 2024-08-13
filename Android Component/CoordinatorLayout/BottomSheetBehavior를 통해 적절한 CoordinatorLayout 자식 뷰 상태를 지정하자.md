## BottomSheetBehavior를 통해 적절한 CoordinatorLayout 자식 뷰 상태를 지정하자
### BottomSheetBehavior란?
> CoordinatorLayout 자식 뷰가 하단에서 펼쳐지는 방식을 지정하는 플러그인
- `app:layout_behavior`를 통해 지정 가능
### BottomSheetBehavior 상태 유형
- `STATE_EXPANDED` : 완전히 펼쳐진 상태
- `STATE_COLLAPSED` : 하단에 접혀 있는 상태
- `STATE_HIDDEN` : 하단에 숨겨져 보이지 않는 상태
- `STATE_HALF_EXPANDED` : 절반으로 펼쳐진 상태
- `STATE_DRAGGING` : 드래깅되고 있는 상태
- `STATE_SETTLING` : 드래그 및 스와이프 직후 고정된 상태
