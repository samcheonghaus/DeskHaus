# DeskHaus

**Writing, tables, images, and PDFs — all in one place.**
An ultra-lightweight all-in-one office tool that combines a word processor,
a spreadsheet with formulas, layer-based image editing, and a PDF viewer/editor
in a single HTML file. Runs from one file — no server, no installation required.

## Features

**Text mode (documents)**
- Paragraph styles, bold/italic/underline, alignment, lists, font color
- Editable letterhead: logo, name/company, email, phone — saved in your browser
- Insert tables with add/remove rows and columns, and auto-sum (below / right)
- Select numbers by dragging to see count, sum, and average in the status bar
- Insert images, save/open as HTML, print and save as PDF

**Sheet mode (spreadsheet)**
- Excel-like grid with cell references and formulas (=A1+B1, =SUM(A1:A10), ~400 functions)
- Open Excel (.xlsx) / CSV files, keeping formulas; save back to Excel or CSV
- Sort by column, bold, font color, cell fill color
- Send the finished table into a document

**Image mode**
- Layer-based editing: move, resize, opacity, reorder, show/hide, rename
- 90° rotate, horizontal flip, crop, text layers, canvas size and background
- Export to PNG / JPG / WebP / ICO (16–256px) / GIF

**PDF mode**
- Open and read PDFs, page navigation and zoom
- Append PDFs together, and extract a single page as a new PDF
- Send a page to Image mode to annotate or sign it, or save a page as PNG

**Bilingual**
- Full English / Korean interface, switchable with one button (auto-detects browser language)

## How to use

Just open the single `index.html` file in a browser, or host it on any web server
to access it from anywhere.

## Built with

- Plain HTML / CSS / JavaScript — no framework, no build step
- Documents: `contenteditable` rich text
- Spreadsheet formulas: [HyperFormula](https://hyperformula.handsontable.com) (GPLv3)
- Excel import/export: [SheetJS](https://sheetjs.com) (Apache-2.0)
- Images: Canvas 2D layer rendering; GIF via [gif.js](https://github.com/jnordberg/gif.js) (MIT)
- PDF: [PDF.js](https://mozilla.github.io/pdf.js) and [pdf-lib](https://pdf-lib.js.org) (MIT)
- All data stays on your device — nothing is sent to a server

## License

MIT — free to use, modify, and distribute. See [LICENSE](LICENSE).

---

Made by Jinbaek Kim with Claude.

MIT — 자유롭게 사용, 수정, 배포할 수 있습니다. [LICENSE](LICENSE) 참조.

---

Made by [Jinbaek Kim](https://www.kimjinbaek.com) with Claude.
