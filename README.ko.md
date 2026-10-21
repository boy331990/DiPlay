# DiPlay

[English](README.md) · [简体中文](README.zh-CN.md) · [繁體中文](README.zh-TW.md)

**호환되는 BYD Android 헤드 유닛용 CarPlay.** 유선 및 무선 연결을 지원하며 익숙한 DiAuto 인터페이스를 제공합니다. 독립 실행형 앱: `com.shihab.diplay`.

> **BYD 지원 범위:** 이 프로젝트는 BYD 차량에 중점을 둡니다. 다른 브랜드에서도 작동할 수 있지만, 다른 브랜드는 지원 대상이 아니며 지원을 추가하거나 브랜드별 비호환 문제를 수정할 계획이 없습니다.

[다운로드 및 웹사이트](https://shihabal3amri.github.io/DiPlay/) · [릴리스](https://github.com/shihabal3amri/DiPlay/releases/tag/v0.2.21) · [문제 신고](https://github.com/shihabal3amri/DiPlay/issues/new/choose)

![DiPlay 홈](site/assets/home.png)

## 0.2.21 — 공개 미리보기

**iPhone이 아니라 차량에** 설치하세요. 사용에 탈옥, 동글, Mac, 계정 또는 인증 서버가 필요하지 않습니다. 핵심 CarPlay 기능에는 ADB가 필요하지 않지만, 선택 기능인 대시보드, 배터리, 휠 속도 및 주차 중 동영상에는 ADB가 필요합니다. 헤드 유닛에서 APK 설치를 허용해야 합니다. APK는 Android 7.0+(API 24)를 지원합니다. 차량에서 Android 7.0–8.1이 지원되는지는 아직 확인되지 않았습니다. 무선 연결은 Wi-Fi Direct, 차량의 기존 핫스팟 또는 Existing Wi-Fi / Same LAN을 지원합니다. Android 7.0–9의 Wi-Fi Direct는 펌웨어에 따라 달라지는 레거시 경로를 사용하며, 그룹 인증 정보를 생성하고 요청한 주파수는 검증되지 않습니다. [Android 9 Wi-Fi Direct](docs/ANDROID9_WIFI_DIRECT.md)를 참조하세요. Android 10 이상에서는 협상된 그룹 주파수를 검증합니다.

- 로컬 인증을 사용하는 유선 USB 및 무선 CarPlay.
- 검증된 펌웨어에서 화살표, 거리 및 도로명이 표시되는 BYD HUD 내비게이션.
- 차량 핫스팟 지원, 개선된 오디오 버퍼링 및 저장된 수신 진단 정보.
- 자동 주소 검색, 고정 채널 Wi-Fi 대체 경로 및 성공한 구성 기억.
- 아이콘/텍스트 크기, 해상도 및 프레임 속도 조정. 디스플레이 변경을 적용하면 CarPlay가 다시 연결됩니다.
- 로컬 진단 정보 내보내기. 사용자가 공유를 선택한 경우에만 보고서가 전송됩니다.
- DiAuto와 별도로 설치됩니다. 프로젝션 앱은 한 번에 하나만 실행하세요.

이 제품은 **Apple 인증 제품이 아닙니다**. APK에는 DiPlay용으로 새로 발급된 MFi ID가 아니라 공개 Carlinkit 펌웨어에서 복구한 실험용 액세서리 ID가 포함되어 있습니다. 번들에 포함된 개인 키는 추출할 수 있습니다. 향후 iOS 업데이트 이후에도 승인될지, 헤드 유닛 전반에서 안정적으로 동작할지, 해당 ID가 일반 배포에 적합한지는 아직 확인되지 않았습니다. 이번 릴리스는 커뮤니티 테스트를 위한 것이며, 모든 환경과의 호환성을 보장하지 않습니다.

이전 릴리스는 개발용 DiLink5.1 차량에서 테스트했습니다. 앞유리의 실시간 안내와 도로명이 작동하고, 차량 핫스팟에서 이제 CarPlay가 시작되며, Wi-Fi Direct 성능이 크게 개선되었습니다. 0.2.15에서는 오디오 버퍼 언더런 복구가 개선되었습니다. 간헐적인 끊김 문제를 더 조사하려면 최신 진단 보고서가 필요합니다. 0.2.16의 소프트웨어 Opus 마이크 대체 기능은 iOS 27을 실행하는 iPhone 12와 Android 9 기반 BOS Mini A1 헤드 유닛에서 승인되었습니다. 플로팅 지도 테스트 빌드는 개발용 DiLink 5.1 차량에 설치되었으며, 받은 피드백을 반영해 0.2.9에서 핀치 동작을 수정했습니다. 이전의 휠 속도 및 동영상 기여 기능은 DiLink 5.0이 설치된 BYD Tang과 iOS 27을 실행하는 iPhone 15 Pro에서 테스트했습니다. 터널에서 휠 속도 추측 항법이 작동하는지는 아직 검증되지 않았습니다. 더 다양한 헤드 유닛 및 iOS와의 호환성은 보장되지 않습니다. HUD 펌웨어 적용 범위와 정리 기능의 한계는 [BYD 내비게이션](docs/BYD_NAVIGATION.md)에 설명되어 있습니다.

## 0.2.21의 새로운 기능

- 음악 재생이 iPhone과 다시 동기화됩니다. 0.2.20에서는 일시 정지, 건너뛰기 및 트랙 변경 반영이 몇 초 늦어지거나 재생 속도가 불안정해질 수 있었습니다.
- iPhone에서 CarPlay가 열리지 않을 때 유선 CarPlay가 자동으로 복구됩니다. **연결 해제** 후 무한정 대기하지 않으며, 이미 복구된 연결을 유지합니다.
- Android 자체 Opus 인코더가 없는 헤드 유닛에서도 마이크를 사용할 때 DiPlay가 종료되지 않습니다. 통화 또는 짧은 중단 후 음악도 다시 재생됩니다.
- 무선 CarPlay를 시작할 수 없는 이유가 표시됩니다. BYD 헤드 유닛에서는 CarPlay가 끝나면 대시보드 제어권을 차량에 돌려주며, DiYou 데스크톱 카드에서 실행해도 DiPlay가 종료되지 않습니다.
- DiPlay를 Android 7.0에 설치할 수 있으며, 이탈리아어를 지원합니다.
- 기본값은 꺼짐인 새 옵션: 임시 시스템 표시줄, 검은색 둥근 모서리, 재생/일시 정지 스티어링 휠 키, Siri 두 번 누르기, 차량 핫스팟 정보 가져오기, 홈 화면 버블, 차량 자체 음악 리듬.

기여 방법과 남은 실제 기기 테스트는 [0.2.21 릴리스 노트](docs/RELEASE-NOTES-0.2.21.md) 및 [검증 문서](docs/VALIDATION.md)를 참조하세요. 일반적인 끊김, 통화/Siri, 디코더 및 모델별 문제를 보고하려면 현재 기기에서 수집한 근거가 필요합니다. 과거 참고 자료로 [0.2.20 노트](docs/RELEASE-NOTES-0.2.20.md)도 계속 제공됩니다.

문제가 계속되면 **0.2.21**에서 재현한 다음 **Settings → Diagnostics → Save diagnostic report**를 사용하세요. Android 10 이상에서는 보통 **Downloads/DiPlay**에 저장됩니다. Android 7.0–9에서는 저장소 접근 권한을 요청한 뒤 같은 위치에 저장합니다. 해당 위치를 사용할 수 없으면 확인 화면에서 **View report** 또는 **Share**를 선택하세요. 대체 외부/비공개 저장소 위치가 표시됩니다. `.txt` 파일을 확인한 뒤 알맞은 [기존 이슈](https://github.com/shihabal3amri/DiPlay/issues)에 첨부하거나 [새 이슈](https://github.com/shihabal3amri/DiPlay/issues/new/choose)를 만드세요. 차량/헤드 유닛 모델, 정확한 펌웨어와 Android/DiLink 버전, 휴대전화/iOS 버전, 연결 백엔드, 관련 설정, 재현 절차 및 실패 시각을 포함하세요. 사용자가 선택한 경우에만 보고서가 공유됩니다. 핫스팟 비밀번호는 절대 게시하지 마세요.

## 문서

[Existing Wi-Fi / Same LAN](docs/EXISTING_WIFI.md)은 iPhone과 헤드 유닛을 외부 라우터에 연결하는 방법을 설명합니다. 설정, 빌드 요구 사항, BYD DiLink 4.0 / Android 10의 완전 초기 설치 검증 결과는 안내서를 참조하세요.

- [설치 및 연결](docs/INSTALL.md)
- [호환성 및 문제 해결](docs/COMPATIBILITY.md)
- [부드러운 무선 CarPlay](docs/SMOOTH_WIRELESS.md)
- [개인정보 및 진단 보고서](docs/PRIVACY.md)
- [소스에서 빌드](docs/BUILD.md) — 기본 DiPlay 앱은 `mobile`을 선택하세요. `maphost`는 지도 샘플입니다.
- [검증](docs/VALIDATION.md)
- [릴리스 노트](CHANGELOG.md)
- [크레딧 및 라이선스](docs/THIRD_PARTY_NOTICES.md)

앱과 웹사이트 소스에는 영어, 아랍어, 러시아어, 우크라이나어, 스페인어, 중국어 간체, 중국어 번체(대만) 및 일본어가 포함되어 있습니다. 중국어 번체는 대만식 표현을 사용합니다. 앱은 별도의 지역 번역이 있다고 주장하지 않으면서 홍콩/마카오 및 사용자가 명시적으로 선택한 Hant도 인식합니다. Settings에서 앱 언어를 선택하세요. Android 13 이상에서는 Android의 앱별 언어 설정과 동기화됩니다. 설치, 설정, 문제 해결, 개인정보 및 빌드 안내는 [중국어 번체 안내서](README.zh-TW.md)를 참조하세요.

## 소스 및 크레딧

[xcertplay](https://github.com/shilapi/xcertplay)을 기반으로 하며 GPL-3.0을 따릅니다. 홈/설정 UI와 웹사이트는 [DiAuto](https://github.com/shihabal3amri/DiAuto)(AGPL-3.0)를 바탕으로 수정했습니다. 해당 라이선스는 `docs/licenses`에 포함되어 있습니다. 수정본을 배포할 때 해당 고지 사항을 유지하세요. CarPlay와 그 아이콘은 Apple Inc.의 소유입니다. Apple 또는 BYD와의 제휴나 보증을 의미하지 않습니다.

이 저장소는 정리된 공개 소스 스냅샷에서 시작합니다. 로컬 조사 자료, 테스터 보고서 및 릴리스 서명 비밀 정보는 제외되어 있습니다. APK에 해당하는 전체 소스는 모든 릴리스와 함께 제공됩니다. 실험용 런타임 ID 자산은 빌드 안내 및 고지 문서에서 별도로 설명합니다.

## 로컬 릴리스 패키징

릴리스 APK에는 실험용 액세서리 ID가 의도적으로 포함되어 있습니다. Git 저장소와 소스 아카이브에는 액세서리 및 Android 서명 키가 포함되지 않으며, 테스트는 실행 시 합성 ID를 생성합니다. 기본적으로 소스/CI 빌드에는 런타임 ID 자산이 포함되지 않습니다. 로컬 릴리스 빌드는 외부 자산 디렉터리를 명시적으로 선택해야 합니다. APK를 게시하면 그 안의 ID를 추출할 수 있습니다. 로컬에서 빌드하더라도 해당 ID의 기밀성이 유지되는 것은 아닙니다.
