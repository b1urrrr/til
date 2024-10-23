## Compose에서 블러 효과를 구현하는 다양한 방식을 구분하자
### 1. `Modifier.blur()` 속성 활용
- Android 12(API 31) 이후 버전에서만 적용
- 기기 호환성을 위해 버전 분기 필요
### 2. Render Script 기능 활용
- Android 12(API 31) 이전 버전에서만 적용
- 기기 호환성을 위해 버전 분기 필요
- 블러 처리 영역 Bitmap으로 변환 필요
### 3. `graphicsLayer`의 `renderEffect` 설정
- Android 12(API 31) 이후 버전에서만 적용
- 기기 호환성을 위해 버전 분기 필요
- Border가 뚜렷하도록 구현 가능
- radius, edgeTreatment, alpha, compositingStrategy를 통해 세부 조정
