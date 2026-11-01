# DeskHaus 1.1.0 — 표(스프레드시트) 대폭 강화

## 새 기능 (표 모드)
- **자동 채우기 핸들 더블클릭** — `1, 2`를 선택하고 ■ 핸들을 더블클릭하면 옆 열 데이터 끝까지 번호가 채워집니다. 옆 열이 비어 있으면 끝 값을 묻는 창이 열립니다.
- **똑똑한 채우기** — 위·아래·좌·우 어느 방향으로든, 날짜·요일·월·분기·`항목1 → 항목2`까지 이어서 채움. Ctrl+끌기로 숫자 증가.
- **연속 데이터 채우기** — 시작·단계·종료 값으로 선형·급수·날짜 계열 생성.
- **여러 시트** — 시트 탭 추가·이름 바꾸기·복제·삭제·이동, 시트 간 수식(`=Sheet2!A1`), Ctrl+PageUp/Down, Shift+F11.
- **피벗 테이블 개선** — 표 범위 자동 인식, 결과를 새 시트에 생성.
- **자동 필터** (Ctrl+Shift+L) — 값 선택·검색·정렬.
- **서식** — 테두리, 줄 바꿈, 글자 크기, 표시 형식(숫자·₩·$·%·날짜), 열 너비 자동 맞춤.
- **Ctrl+Enter** 범위 한 번에 입력, **fx 함수** 목록, **Alt+=** 자동 합계, 날짜 계산(`=A1+7`).
- **엑셀 파일** — 모든 시트·수식·표시 형식·열 너비·병합을 함께 열고 저장.

## 알려진 제한
- 저장한 `.xlsx`에는 글자색·배경색·테두리가 담기지 않습니다 (화면에서는 표시됨).

## English
- Fill-handle double-click auto-fill, smart series (dates, weekdays, months, `Item1 → Item2`), Fill Series dialog
- Multiple sheets with cross-sheet formulas; pivot tables on a new sheet; AutoFilter
- Borders, wrap text, font size, number formats, AutoFit; Ctrl+Enter; multi-sheet `.xlsx` open/save

---

# DeskHaus 1.0.0 — Windows

하나로 쓰는 사무 도구 (글 · 그림 · 표 · PDF · PPT · 3D). 인터넷 없이도 모든 기능이 동작합니다.

## 다운로드
| 파일 | 설명 |
|---|---|
| **DeskHaus-Setup.exe** (추천) | 설치형. 바탕화면·시작 메뉴 바로가기 생성, Windows [설정 → 앱]에서 삭제 |
| **DeskHaus-Portable.zip** | 포터블. 압축을 풀고 `DeskHaus.exe` 실행, 삭제는 폴더만 지우면 됨 |

- 지원: Windows 10 / 11 (64비트)
- 처음 실행 시 "Windows의 PC 보호" 창이 뜨면 **[추가 정보 → 실행]**

## English
All-in-one office tool (docs, images, sheets, PDF, slides, 3D). Works fully offline.
- **DeskHaus-Setup.exe** (recommended): installer with shortcuts; uninstall from Settings → Apps.
- **DeskHaus-Portable.zip**: no install; unzip and run `DeskHaus.exe`.

License: GPLv3 · © 2026 Kim Jin Baek (samcheonghaus)
