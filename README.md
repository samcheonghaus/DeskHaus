# DeskHaus

**One file. One tool. Your everyday office work.**

[한국어 README (Korean)](./README.ko.md)

DeskHaus is a lightweight office suite that runs entirely in your browser from a **single HTML file** — no installation, no server, no account. Write documents, edit images, calculate in spreadsheets, handle PDFs, build slides, and view 3D CAD models, all in one place. Your files never leave your computer.

## Getting Started

1. Download `index.html`
2. Open it in a modern browser (Chrome, Edge, Firefox, Safari)
3. That's it.

> An internet connection is required on first use — the libraries (spreadsheet engine, PDF tools, 3D reader, etc.) are loaded from public CDNs and cached by your browser afterwards.

## Features

### 📝 Text — documents & letterhead
- Rich-text editing on an A4 page with a personal letterhead (logo, name, contact)
- Insert tables and images; double-click an image to edit it in Image mode and apply it back
- Open `.docx`, `.html`, `.txt`, `.hwpx` — save as HTML, Word (.docx), or text

### 🖼 Image — layer-based editor
- Layers with move, resize, reorder, show/hide, and rename
- Draw shapes and text, set canvas and background color
- Bring in a PDF page or a document image, edit, and send it back

### 📊 Sheet — a spreadsheet with real Excel basics
- **Formulas** powered by HyperFormula: `=A1+B1`, `=SUM(A1:A10)`, `=AVERAGE(...)` and hundreds more
- **Range selection**: drag, Shift+click, Shift+arrows, header click for whole rows/columns, Ctrl+A
- **Live selection stats** — sum, average, and count shown as you select, just like Excel's status bar
- **Σ AutoSum** — one click inserts the right `=SUM()` for your selection
- **Copy / Cut / Paste** (Ctrl+C/X/V) with relative-reference shifting — and it's clipboard-compatible with real Excel in both directions
- **Auto-fill handle** — drag the corner of a selection; `1, 2` becomes `3, 4, 5`, formulas shift their references
- **Undo / Redo** (Ctrl+Z / Ctrl+Y)
- **Find & Replace** (Ctrl+F / Ctrl+H) in a small non-blocking panel
- **Merge cells** — one toggle button; merges survive Excel export/import
- **Pivot tables** — pick row / column / value fields and an aggregate (sum, count, avg, min, max), get a pivot with grand totals
- Insert/delete rows & columns with automatic formula-reference adjustment, column resizing, sorting with header detection
- Formatting applied instantly to the whole selection: bold, italic, underline, alignment, text & fill color (applies the moment you pick a color), thousands separator, percent, decimal places
- Open and save `.xlsx` / `.csv` (formulas preserved), or send the table straight into your document

### 📄 PDF
- View, zoom, and navigate PDFs
- Append PDFs together, delete pages, save a single page or the whole file
- Send a page to Image mode for markup, or export it as PNG

### 📽 Slides
- 16:9 slides with text, shapes, and images; drag to move, resize, and edit in place
- Presenter notes, slideshow mode, open/save `.pptx`

### 🧊 3D — STEP viewer & drawing export
- Open `.step` / `.stp` CAD files (parsed by OpenCascade compiled to WebAssembly)
- Orbit with the mouse, scroll to zoom, right-drag to pan; one-click Front / Top / Right / Isometric views; faces or wireframe
- **Save a PDF drawing** — a single A4 sheet with Front, Top, Right-side, and Isometric views and a title block
- **Save DXF for CAD** — triangle-mesh DXF (AC1009) that opens in AutoCAD and other CAD software, where you can save it as **DWG** with one click
- DWG is a proprietary format and is intentionally not written directly; the DXF route is the reliable path

*The STEP reader (~10 MB WebAssembly) downloads once on first use and is cached afterwards.*

## Keyboard Shortcuts (Sheet)

| Shortcut | Action |
|---|---|
| Arrow keys / Enter / Tab | Move active cell |
| Shift + arrows / click | Extend selection |
| Ctrl + arrows | Jump to edge of data |
| Ctrl + A | Select all |
| F2 or double-click | Edit cell |
| Ctrl + C / X / V | Copy / Cut / Paste |
| Ctrl + Z / Y | Undo / Redo |
| Ctrl + D / R | Fill down / right |
| Ctrl + B / I / U | Bold / Italic / Underline |
| Ctrl + F / H | Find / Replace |
| Delete | Clear selection |

While typing a formula (`=`), click or drag on cells to insert references like `A1` or `A1:B5`.

## Language

The interface is fully bilingual — switch between **한국어** and **English** with the language button in the header.

## Tech

Single-file HTML + vanilla JavaScript. Libraries loaded from CDN:

| Library | Used for |
|---|---|
| [HyperFormula](https://hyperformula.handsontable.com/) | Spreadsheet formula engine |
| [SheetJS (xlsx)](https://sheetjs.com/) | Excel/CSV read & write |
| [pdf.js](https://mozilla.github.io/pdf.js/) / [pdf-lib](https://pdf-lib.js.org/) | PDF rendering & editing |
| [mammoth](https://github.com/mwilliamson/mammoth.js) / [docx](https://docx.js.org/) | Word import & export |
| [PptxGenJS](https://gitbrent.github.io/PptxGenJS/) / JSZip | PowerPoint export & import |
| [Three.js](https://threejs.org/) | 3D rendering |
| [occt-import-js](https://github.com/kovacsv/occt-import-js) | STEP file parsing (OpenCascade WASM) |

## Privacy

Everything runs locally in your browser. No files are uploaded anywhere; the only network traffic is downloading the libraries themselves from CDNs.

## License Notes

This project bundles usage of third-party libraries under their own licenses, including HyperFormula (**GPL v3** — the free license key is used, which requires GPL-compatible distribution of this project), OpenCascade via occt-import-js (**LGPL 2.1**), and MIT/Apache-licensed libraries (Three.js, pdf-lib, SheetJS, and others). If you fork or redistribute, please review these licenses.
