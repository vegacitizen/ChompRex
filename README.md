# ChompRex 🦖

공룡이 다른 공룡을 잡아먹고 자라는 안드로이드용 캐주얼 게임입니다.

## 게임 규칙

- 화면을 드래그하면 가상 조이스틱이 나타나고, 그 방향으로 공룡이 움직입니다.
- 나보다 **작거나 비슷한 크기**(내 크기의 108% 이하)의 공룡을 잡아먹을 수 있습니다. 발밑에 초록 테두리로 표시됩니다.
- 잡아먹으면 **먹은 공룡의 몸무게만큼** 내 몸무게가 늘어나고 몸이 커집니다.
- 나보다 **큰 공룡**(빨간 테두리와 `!` 표시)에게 닿으면 잡아먹혀 게임이 끝납니다.
- 맵에 드물게 나타나는 **신비의 광석 ◆** 을 먹으면 8초 동안 나보다 큰 공룡도 잡아먹을 수 있습니다.
  광석이 화면 밖에 있으면 화면 가장자리의 하늘색 화살표가 방향을 알려줍니다.
- 3 kg 콤프소그나투스로 시작해 몸무게 20 t의 대왕 티라노사우루스가 되면 승리합니다.

## 구조

| 경로 | 설명 |
| --- | --- |
| `app/src/main/assets/index.html` | 게임 본체 (HTML5 Canvas, 외부 의존성 없음) |
| `app/src/main/java/.../MainActivity.java` | 게임을 전체 화면 WebView로 띄우는 액티비티 |
| `.github/workflows/android.yml` | 푸시할 때마다 디버그 APK를 빌드하는 GitHub Actions |

## 빌드

Android Studio로 이 폴더를 열어 실행하거나, 명령줄에서:

```
./gradlew assembleDebug
```

APK는 `app/build/outputs/apk/debug/app-debug.apk` 에 생성됩니다.
GitHub Actions 실행 결과의 `ChompRex-debug-apk` 아티팩트에서도 내려받을 수 있습니다.

게임 로직만 빠르게 확인하려면 `app/src/main/assets/index.html` 을 브라우저로 열면 됩니다 (방향키/WASD 또는 마우스 드래그).
