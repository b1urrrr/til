## SDK의 설정과 AndroidManifest.xml의 속성이 충돌하는 경우에 `tools:replace` 속성을 활용하자
### [`tools:replace`란?](https://eonj.github.io/trouble.log/2024-04-16.android-manifest-tools-replace-conflict/)
> manifest XML을 병합하는 시점에 충돌하는 노드가 정의된 경우, 해당 노드의 속성값 중에서 대체되어야 할 이름을 명시하는 속성
- 자식 노드는 노드의 목록으로 병합됨
### 충돌 발생 예시
- [Airbridge SDK의 백업 규칙과 `AndroidManifest.xml`의 `android:allowBackup="false"`값이 충돌하는 경우](https://help.airbridge.io/ko/developers/troubleshooting-android-sdk-v4#allowbackup-false%EA%B3%BC%EC%9D%98-%EC%B6%A9%EB%8F%8C-%EB%B0%A9%EC%A7%80)
