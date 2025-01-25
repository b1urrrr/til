## local.properties와 gradle.properties 파일을 구분하여 활용하자
### local.properties 파일
- 로컬 개발 환경에 종속적인 설정 저장
- 기본적으로 `.gitignore`에 추가되어 버전 관리에 포함되지 않음
- 안드로이드 플러그인에서 처리
- EX) API Key 값, 로컬 SDK 경로 등
### gradle.properties 파일
- Gradle 빌드 시스템의 전역 및 프로젝트별 속성 설정
- 일반적으로 Git에 포함
- Gradle을 통해 관리
- EX) 빌드 옵션, 프로젝트 전역 변수 등
### [홈 디렉토리의 gradle.properties 파일](https://pancake.coffee/jekyll/local-gradle-properties/)
- 커스텀 플러그인을 작성하는 등의 경우 local.properties를 통해 프로퍼티를 참조하기 번거로워 활용
  - local.properties 파일을 읽어들이는 로직 구현 필요 (원래 안드로이드 플러그인이 처리)
- 다른 모든 프로젝트 디렉토리의 gradle.properties가 참조
  - 프로퍼티명이 중복되지 않도록 프로젝트명을 포함하여 네이밍 권장
- 프로퍼티 설정에 대한 문서화 및 공유 필요
