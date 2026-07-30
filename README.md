# DeskHaus

**Writing and images, all in one place.**
An ultra-lightweight all-in-one office tool that combines a word processor,
basic table calculation, and layer-based image editing in a single HTML file.
Runs from one file — no server, no installation required.

## Features

**Document mode**
- Paragraph styles, bold/italic/underline, alignment, lists, font color
- Insert tables + add/remove rows and columns at the cursor (+Row −Row +Col −Col)
- Sum Below / Sum Right — auto-sum rows and columns; click again to recalculate
- Select numbers by dragging to see count, sum, and average in the status bar
- Insert images, save/open as HTML, print and save as PDF
- Import Excel (.xlsx) / CSV files as tables, and export any table back to Excel

**Image mode**
- Layer-based editing: move, resize, opacity, reorder, show/hide, rename
- 90° rotate, horizontal flip, crop, text layers, canvas size and background
- Export to PNG / JPG / WebP / ICO (16–256px) / GIF

**Bridge feature**
- Double-click an image inside a document → edit it with layers in Image mode → "Apply to document" to replace it

## How to use

### 1. Web version (simplest)
Just open the single `index.html` file in a browser.
Host it on any web server to access it from anywhere.

### 2. Windows desktop version
Built on [Neutralinojs](https://neutralino.js.org).

```bash
npm install -g @neutralinojs/neu
cd desktop
neu update      # download runtime binaries
neu build --release
```

Place `DeskHaus-win_x64.exe` and `resources.neu` (found in `desktop/dist/DeskHaus/`)
in the same folder and run the .exe.
(macOS and Linux binaries are produced in the same build.)

## Built with

- Plain HTML / CSS / JavaScript — no framework, no build step
- Documents: `contenteditable` rich text
- Images: Canvas 2D layer rendering
- Excel import/export: [SheetJS](https://sheetjs.com) (Apache-2.0, via CDN)
- GIF export: [gif.js](https://github.com/jnordberg/gif.js) (MIT, via CDN)
- Desktop packaging: [Neutralinojs](https://neutralino.js.org) (MIT)
- All data stays on your device — nothing is sent to a server

## License

MIT — free to use, modify, and distribute. See [LICENSE](LICENSE).

---

Made by Jinbaek Kim with Claude.
