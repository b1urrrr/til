## `Modifier.offset()`은 다른 컴포넌트와 독립적인 경우에만 사용하자.md
- `offset`은 Composition 단계 이후, Layout 단계에서 반영되기 때문에 다른 컴포넌트의 배치에 영향을 주지 않음
- 따라서 offset으로 인해 생긴 빈 공간에 시스템 배경 색이 노출될 수 있어 유의
