# 멜론 턴테이블 (안드로이드 앱)

## APK 만들기 (방법 A: Android Studio)
1. Android Studio에서 이 폴더 열기 → Gradle Sync
2. 메뉴 Build > Build Bundle(s) / APK(s) > Build APK(s)
3. 완료 알림의 locate를 누르면 `app/build/outputs/apk/debug/app-debug.apk`

## APK 만들기 (방법 B: GitHub Actions, 설치 불필요)
1. 이 폴더를 GitHub 저장소에 올리기 (루트에 build.gradle.kts, .github 폴더가 오도록)
2. Actions 탭 > Build APK > Run workflow
3. 끝나면 Artifacts에서 melon-turntable-debug-apk 다운로드

## 폰에 설치
APK를 폰으로 옮겨 실행 → '출처를 알 수 없는 앱 설치' 허용 → 설치.
처음 실행 시 알림 접근 권한에서 '멜론 턴테이블'을 켜면 멜론과 연동됩니다.


## Android Auto 사용
- 이 프로젝트에는 Android Auto 미디어 브라우징 서비스(`MelonMirrorService`)가 포함되어 있습니다.
- 휴대폰에서 멜론 앱을 실행하고 음악을 재생한 뒤, 알림 접근 설정에서 `멜론 턴테이블`을 허용하세요.
- Android Auto의 미디어 앱 목록에서 `멜론 턴테이블`을 선택하면 곡 정보와 재생 컨트롤을 미러링합니다.
- Android Auto 화면에는 Google의 미디어 템플릿이 표시되므로 앱의 턴테이블 애니메이션/앨범 화면 자체는 표시되지 않습니다.
- 앱이 목록에 나타나지 않으면 Android Auto 설정에서 개발자 모드를 켜고 `알 수 없는 소스` 허용 여부를 확인하세요. 차량/휴대폰/Android Auto 버전에 따라 표시 정책이 다를 수 있습니다.

## 주의
이 앱은 멜론의 음원을 직접 재생하거나 멜론 계정에 로그인하지 않습니다. 휴대폰에서 재생 중인 멜론의 미디어 세션 정보를 읽어 Android Auto에 표시하고, 재생/일시정지/이전/다음 명령을 멜론에 전달합니다. 최초 실행 후 알림 접근 권한이 필요합니다.
