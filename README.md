# DeskHaus

한국어 | [English](#deskhaus-english)

**글과 그림, 한 자리에서.**

문서 작성(워드) · 표 계산(엑셀 기초) · 레이어 이미지 편집(포토샵/일러스트 기초) ·
PDF 보기/편집 · 프레젠테이션(파워포인트 기초)을
하나로 합친 초경량 사무 도구입니다. 파일 하나(HTML)로 동작하며, 서버도 설치도 필요 없습니다.

## 주요 기능

**글 모드 (문서)**
- 문단 스타일, 굵게/기울임/밑줄, 정렬, 목록, 글자 색
- 레터헤드(로고 · 이름 · 연락처) — 편지지처럼 쓰고 접기/펼치기 가능
- 표 삽입 + 커서 위치 기준 행/열 추가·삭제 (＋행 －행 ＋열 －열)
- Σ 아래 합계 / Σ 우측 합계 — 표의 숫자를 자동 합산한 행·열 추가, 재클릭 시 재계산
- 숫자를 드래그 선택하면 상태 바에 개수·합계·평균 자동 표시
- 이미지 삽입 및 크기·정렬 조절, 워드(.docx)·HTML·텍스트 저장/열기, 인쇄 및 PDF 저장

**그림 모드 (이미지)**
- 레이어 기반 편집: 이동, 크기 조절, 투명도, 순서 변경, 표시/숨김, 이름 변경
- 90° 회전, 좌우 반전, 자르기, 텍스트 레이어, 캔버스 크기·배경 설정
- PNG / JPG / WebP / ICO(16~256px) / GIF 내보내기

**표 모드 (스프레드시트)**
- 셀 편집, 수식 계산 — `=A1+B1`, `=SUM(A1:A10)` 등 (HyperFormula 엔진)
- 굵게, 글자 색, 셀 배경색, 오름차순/내림차순 정렬, 행·열 추가
- 엑셀(.xlsx)·CSV 열기 및 저장, 현재 표를 문서(글 모드)로 보내기

**PDF 모드**
- PDF 열기, 페이지 이동, 확대/축소
- PDF 이어붙이기(병합), 페이지 삭제, 현재 페이지만 PDF로 저장
- 현재 페이지를 PNG로 저장하거나 그림 모드로 가져와 레이어 편집

**PPT 모드 (프레젠테이션)**
- 파워포인트 파일(.pptx) 열기 — 텍스트·이미지·도형·배경을 불러와 편집
  (복잡한 서식·효과는 단순화되어 표시될 수 있습니다)
- 슬라이드 편집: 텍스트 상자·이미지·도형(사각형/원) 추가,
  드래그 이동, 모서리 핸들로 크기 조절, 더블클릭으로 글 수정, Delete 키로 삭제
- 슬라이드 관리: 축소판 목록, 레이아웃(제목/제목＋내용/빈 슬라이드) 선택 추가,
  복제, 삭제, ▲▼ 순서 변경
- 서식: 글자 크기·굵게·색·정렬, 도형 채움색, 슬라이드 배경색
- 전체 화면 **슬라이드쇼** (클릭·방향키로 이동, Esc로 종료), 발표자 노트
- 실행 취소/다시 실행(Ctrl+Z/Y), PPTX로 저장, 현재 슬라이드 PNG 저장

**연결 기능**
- 문서 안의 이미지를 더블클릭 → 그림 모드에서 레이어 편집 → "문서에 적용"으로 교체
- 표 모드의 계산 결과를 문서로 보내기, PDF 페이지를 그림 모드로 가져오기

**기타**
- 한국어 / English 인터페이스 전환 (`?lang=ko` / `?lang=en` 으로 고정 가능)

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
- 표 계산: [HyperFormula](https://hyperformula.handsontable.com) (GPLv3/상용, CDN 로드)
- 엑셀 입출력: [SheetJS](https://sheetjs.com) (Apache-2.0, CDN 로드)
- 워드 입출력: [mammoth.js](https://github.com/mwilliamson/mammoth.js) · [docx](https://github.com/dolanmiu/docx) (MIT, CDN 로드)
- PDF 렌더링/편집: [PDF.js](https://mozilla.github.io/pdf.js/) (Apache-2.0) · [pdf-lib](https://pdf-lib.js.org) (MIT, CDN 로드)
- PPTX 읽기/쓰기: [JSZip](https://stuk.github.io/jszip/) (MIT) · [PptxGenJS](https://gitbrent.github.io/PptxGenJS/) (MIT, CDN 로드)
- GIF 내보내기: [gif.js](https://github.com/jnordberg/gif.js) (MIT, CDN 로드)
- 데스크톱 포장: [Neutralinojs](https://neutralino.js.org) (MIT)
- 모든 데이터는 사용자 PC에만 저장됩니다 — 서버 전송 없음
  (외부 라이브러리 CDN 로드에만 인터넷 연결이 필요합니다)

## 라이선스
MIT — 자유롭게 사용, 수정, 배포할 수 있습니다. [LICENSE](LICENSE) 참조.

---
Made by [Jinbaek Kim](https://www.kimjinbaek.com) with Claude.

---

# DeskHaus (English)

[한국어](#deskhaus) | English

**Writing and images, in one place.**

An ultra-lightweight all-in-one office tool that combines a word processor,
a basic spreadsheet, layer-based image editing, PDF viewing/editing,
and presentation slides — all in a single HTML file.
No server, no installation.

## Features

**Text mode (documents)**
- Paragraph styles, bold/italic/underline, alignment, lists, font color
- Letterhead (logo · name · contact) — use it like stationery, collapsible
- Insert tables + add/remove rows and columns at the cursor
- Σ sum row / Σ sum column — auto-sums the numbers in a table; click again to recalculate
- Select numbers by dragging to see count · sum · average in the status bar
- Insert and resize/align images; open and save Word (.docx), HTML, and text; print / save as PDF

**Image mode**
- Layer-based editing: move, resize, opacity, reorder, show/hide, rename
- 90° rotation, horizontal flip, crop, text layers, canvas size and background
- Export as PNG / JPG / WebP / ICO (16–256px) / GIF

**Sheet mode (spreadsheet)**
- Cell editing with formulas — `=A1+B1`, `=SUM(A1:A10)`, etc. (HyperFormula engine)
- Bold, font color, cell background, ascending/descending sort, add rows and columns
- Open and save Excel (.xlsx) and CSV; send the current sheet into the document

**PDF mode**
- Open PDFs, navigate pages, zoom
- Append (merge) PDFs, delete pages, save a single page as a new PDF
- Save the current page as PNG, or send it to Image mode for layer editing

**Slides mode (presentations)**
- Open PowerPoint files (.pptx) — imports text, images, shapes, and backgrounds for editing
  (complex formatting and effects may appear simplified)
- Slide editing: add text boxes, images, and shapes (rectangle/circle);
  drag to move, resize with the corner handle, double-click to edit text, press Delete to remove
- Slide management: thumbnail list; add slides with a layout (title / title + body / blank);
  duplicate, delete, reorder with ▲▼
- Formatting: font size, bold, color, alignment, shape fill, slide background
- Full-screen **slideshow** (click or arrow keys to advance, Esc to exit), speaker notes
- Undo/redo (Ctrl+Z/Y), save as PPTX, save the current slide as PNG

**Connected workflows**
- Double-click an image in a document → edit it in Image mode → "Apply to document" to replace it
- Send sheet results into the document; bring a PDF page into Image mode

**Other**
- Korean / English interface toggle (pin with `?lang=ko` / `?lang=en`)

## How to use

### 1. Web version (simplest)
Just open the single `index.html` file in a browser.
Host it on any web server to use it from anywhere.

### 2. Windows desktop version
Built with [Neutralinojs](https://neutralino.js.org).
```bash
npm install -g @neutralinojs/neu
cd desktop
neu update      # download runtime binaries
neu build --release
```
Put `DeskHaus-win_x64.exe` and `resources.neu` from `desktop/dist/DeskHaus/`
in the same folder and run the exe.
(macOS and Linux binaries are produced by the same build.)

## Tech stack
- Pure HTML / CSS / JavaScript — no framework, no build step
- Documents: `contenteditable`-based rich text
- Images: Canvas 2D layer rendering
- Spreadsheet engine: [HyperFormula](https://hyperformula.handsontable.com) (GPLv3/commercial, loaded via CDN)
- Excel I/O: [SheetJS](https://sheetjs.com) (Apache-2.0, CDN)
- Word I/O: [mammoth.js](https://github.com/mwilliamson/mammoth.js) · [docx](https://github.com/dolanmiu/docx) (MIT, CDN)
- PDF rendering/editing: [PDF.js](https://mozilla.github.io/pdf.js/) (Apache-2.0) · [pdf-lib](https://pdf-lib.js.org) (MIT, CDN)
- PPTX read/write: [JSZip](https://stuk.github.io/jszip/) (MIT) · [PptxGenJS](https://gitbrent.github.io/PptxGenJS/) (MIT, CDN)
- GIF export: [gif.js](https://github.com/jnordberg/gif.js) (MIT, CDN)
- Desktop packaging: [Neutralinojs](https://neutralino.js.org) (MIT)
- All data stays on the user's PC — nothing is sent to a server
  (internet is only needed to load the CDN libraries)

## License
MIT — free to use, modify, and distribute. See [LICENSE](LICENSE).

---
Made by [Jinbaek Kim](https://www.kimjinbaek.com) with Claude.
