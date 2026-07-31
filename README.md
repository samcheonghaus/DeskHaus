# DeskHaus

**글과 그림, 한 자리에서.**
문서 작성(워드) · 표 계산(엑셀 기초) · 레이어 이미지 편집(포토샵/일러스트 기초)을
하나로 합친 초경량 사무 도구입니다. 파일 하나(HTML)로 동작하며, 서버도 설치도 필요 없습니다.

An ultra-lightweight all-in-one office tool that combines a word processor,
basic table calculation, and layer-based image editing in a single HTML file.

## 주요 기능

**글 모드 (문서)**
- 문단 스타일, 굵게/기울임/밑줄, 정렬, 목록, 글자 색
- 표 삽입 + 커서 위치 기준 행/열 추가·삭제 (＋행 －행 ＋열 －열)
- Σ 아래 합계 / Σ 우측 합계 — 표의 숫자를 자동 합산한 행·열 추가, 재클릭 시 재계산
- 숫자를 드래그 선택하면 상태 바에 개수·합계·평균 자동 표시
- 이미지 삽입, HTML 저장/열기, 인쇄 및 PDF 저장

**그림 모드 (이미지)**
- 레이어 기반 편집: 이동, 크기 조절, 투명도, 순서 변경, 표시/숨김, 이름 변경
- 90° 회전, 좌우 반전, 자르기, 텍스트 레이어, 캔버스 크기·배경 설정
- PNG / JPG / WebP / ICO(16~256px) / GIF 내보내기

**연결 기능**
- 문서 안의 이미지를 더블클릭 → 그림 모드에서 레이어 편집 → "문서에 적용"으로 교체

## 사용 방법

### 1. 웹 버전 (가장 간단)
`index.html` 파일 하나를 브라우저로 열면 끝입니다.
웹 서버에 올리면 어디서든 접속해서 쓸 수 있습니다.

### 2. 윈도우 데스크톱 버전
[Neutralinojs](https://neutralino.js.org) 기반으로 빌드합니다.

```bash
npm install -g @neutralinojs/neu
cd desktop
neu update      # 실행 바이너리 다운로드
neu build --release
```

`desktop/dist/DeskHaus/` 안의 `DeskHaus-win_x64.exe`와 `resources.neu`
두 파일을 같은 폴더에 두고 exe를 실행하면 됩니다.
(macOS·Linux 바이너리도 같은 빌드에서 함께 생성됩니다)

## 기술 구성

- 순수 HTML / CSS / JavaScript — 프레임워크 없음, 빌드 없음
- 문서: `contenteditable` 기반 리치텍스트
- 이미지: Canvas 2D 레이어 렌더링
- GIF 내보내기: [gif.js](https://github.com/jnordberg/gif.js) (MIT, CDN 로드)
- 데스크톱 포장: [Neutralinojs](https://neutralino.js.org) (MIT)
- 모든 데이터는 사용자 PC에만 저장됩니다 — 서버 전송 없음

## 라이선스

MIT — 자유롭게 사용, 수정, 배포할 수 있습니다. [LICENSE](LICENSE) 참조.

---

Made by [Jinbaek Kim](https://www.kimjinbaek.com) with Claude.
