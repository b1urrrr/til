## 점진적으로 Compose로 마이그레이션하는 전략을 사용하자
### 점진적 Compose Migration 단계
1. 신규 기능 Compose 개발
    - Base가 되는 ComposeActivity/ComposeFragment 활용
2. 기존 화면에 Compose 신규 컴포넌트 추가
    - ComposeView 활용
3. 기존 컴포넌트 Compose로 교체
    - AbstractComposeView 활용
4. ViewHolder Item Compose로 교체
    - 리스트 뷰에 대한 마이그레이션 부담 최소화 (특히, 여러 ViewHolder를 사용하는 경우)
5. 기존 화면 모두 Compose로 교체
6. Compose 미지원 뷰 호스팅
    - AndroidView Compose Interop API 활용
