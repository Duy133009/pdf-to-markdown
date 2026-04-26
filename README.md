<div align="center">
  <br/>
  <img src="https://img.shields.io/badge/status-active-success.svg" alt="Active">
  <img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="License">
  <img src="https://img.shields.io/badge/build-passing-brightgreen" alt="Build">
  <br/><br/>
</div>

<p align="center">
  <b>⚡ MD Convert</b> — A blazing-fast, privacy-first file-to-Markdown converter that runs entirely in your browser.
  <br/>
  No uploads. No servers. No tracking.
</p>

---

## Features

- **100% Client-side** — All conversion happens locally in your browser. Your files never leave your device.
- **Multiple formats** — Convert PDF, DOCX, XLSX, CSV, HTML, JSON, XML, images (PNG/JPG/GIF), and plain text to Markdown.
- **OCR support** — Built-in OCR (Tesseract.js) for extracting text from scanned PDFs and images. Toggle on/off per file.
- **Live preview** — Side-by-side preview panel for PDFs (rendered page-by-page), images, and text files.
- **Toggleable preview pane** — Show or hide the preview panel with one click. Preference saved across sessions.
- **Beautiful theming** — 5 built-in themes (Dark, Light, Ocean, Midnight, Forest) plus fully customizable colors.
- **Instant download** — Export your Markdown as a `.md` file with one click.
- **One-click copy** — Copy the converted Markdown to your clipboard instantly.
- **Drag & drop** — Drag files directly onto the drop zone or click to browse.
- **File statistics** — See character count, line count, and word count after conversion.
- **Persistent settings** — Your theme preference is saved in `localStorage` across sessions.
- **Responsive design** — Works perfectly on desktop, tablet, and mobile.

## Supported Formats

| Format      | Extension                         | Converter                          |
|-------------|-----------------------------------|------------------------------------|
| PDF         | `.pdf`                            | pdf.js text extraction             |
| Word        | `.docx`, `.doc`                   | Mammoth.js + Turndown              |
| Excel       | `.xlsx`, `.xls`                   | SheetJS                            |
| CSV         | `.csv`                            | Custom CSV parser                  |
| HTML        | `.html`, `.htm`                   | Turndown                           |
| JSON        | `.json`                           | Pretty-printed code block          |
| XML         | `.xml`                            | Syntax-highlighted code block      |
| Plain text  | `.txt`                            | Raw text                           |
| Images      | `.png`, `.jpg`, `.jpeg`, `.gif`, `.webp`, `.bmp` | OCR (Tesseract.js) or raw text |

## Getting Started

### Option A: Open directly in browser (no server needed)

Simply open `index.html` in any modern browser:

```bash
# On Windows
start index.html

# On macOS
open index.html

# On Linux
xdg-open index.html
```

### Option B: Run with FastAPI server (for production or Docker)

```bash
# Install dependencies
pip install -r requirements.txt

# Start the server
uvicorn app:app --host 0.0.0.0 --port 8000 --reload
```

Then open **http://localhost:8000** in your browser.

### Option C: Docker

```bash
docker build -t md-convert .
docker run -p 8000:8000 md-convert
```

## Project Structure

```
pdf-to-md/
├── index.html          # Single-page application (HTML + CSS + JS)
├── app.py              # FastAPI server (optional, for API access)
├── requirements.txt    # Python dependencies
├── Dockerfile          # Container build instructions
└── README.md           # This file
```

## Themes

MD Convert comes with 5 carefully crafted themes:

| Theme      | Vibe                | Accent Color |
|------------|---------------------|--------------|
| **Dark**   | Deep space (default)| Indigo       |
| **Light**  | Clean & bright      | Indigo       |
| **Ocean**  | Deep blue waters    | Sky blue     |
| **Midnight** | Royal purple      | Periwinkle   |
| **Forest** | Calming greens      | Emerald      |

You can also customize every color to your liking via the **Settings** panel (gear icon in the top-right corner).

> **Note:** The server component (`app.py`) is optional. The frontend works fully offline as a static file.

## Tech Stack

| Layer      | Technology                                              |
|------------|---------------------------------------------------------|
| Frontend   | Vanilla HTML + CSS + JavaScript                         |
| Fonts      | Inter, JetBrains Mono (Google)                          |
| OCR        | [Tesseract.js](https://tesseract.projectnaptha.com/) v4 |
| PDF        | [pdf.js](https://mozilla.github.io/pdf.js/) v3.11.174   |
| DOCX       | [Mammoth.js](https://github.com/mwilliamson/mammoth.js) v1.6.0 |
| Markdown   | [Turndown](https://github.com/mixmark-io/turndown) v7.1.2 |
| XLSX       | [SheetJS](https://sheetjs.com/) v0.18.5                 |
| Backend    | [FastAPI](https://fastapi.tiangolo.com/) + [Uvicorn](https://www.uvicorn.org/) |

## License

This project is open source and available under the [MIT License](LICENSE).
