# InkPDF — Browser-Based PDF Editor

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![HTML](https://img.shields.io/badge/built%20with-HTML%2FCSS%2FJS-orange)
![No Backend](https://img.shields.io/badge/backend-none-green)

**InkPDF** is a lightweight, privacy-first PDF editor that runs entirely in your browser. No uploads to any server. No accounts. No tracking. Just open, edit, save.

![InkPDF Screenshot](screenshot.png)

## Features

- **Upload PDFs** via drag-and-drop or file picker
- **Freehand Drawing** with customizable color and stroke size
- **Shape Tools** including lines, rectangles, circles, and arrows
- **Text Annotations** that are draggable, resizable, and deletable
- **Highlighter** with adjustable opacity for marking up content
- **Eraser** to remove specific annotations
- **Multi-page Support** with per-page annotation persistence
- **Zoom Controls** for precise editing
- **Undo** support per page (Ctrl+Z)
- **Save to PDF** flattens all annotations directly into the PDF file
- **100% Client-Side** with zero data leaving your browser

## Tech Stack

- **PDF.js** (Mozilla) for rendering PDFs in the browser
- **pdf-lib** for writing annotations back into PDF files
- **Vanilla HTML/CSS/JS** with no build step required
- **DM Sans + Instrument Serif** typography from Google Fonts

## Getting Started

### Option 1. Just open the file

Download `index.html` and open it in any modern browser. That's it.

### Option 2. Serve locally

```bash
git clone https://github.com/udhay-ravi/inkpdf.git
cd inkpdf
# Use any static server
npx serve .
# or
python3 -m http.server 8000
```

Then visit `http://localhost:8000`

### Option 3. Deploy anywhere

Since InkPDF is a single HTML file with no dependencies to install, you can deploy it to any static hosting platform.

**GitHub Pages**

1. Push to a repo
2. Go to Settings > Pages
3. Set source to your main branch
4. Your editor is live at `https://udhay-ravi.github.io/inkpdf/`

**Netlify / Vercel / Cloudflare Pages**

Just drag the folder into their deploy UI or connect your repo. Zero config needed.

## Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| Ctrl + Z | Undo last annotation |
| Ctrl + S | Save and download edited PDF |

## How It Works

1. **Upload** a PDF. The file is read into memory using the FileReader API.
2. **Render** each page onto an HTML canvas using PDF.js.
3. **Edit** by drawing on a transparent overlay canvas layered on top.
4. **Text** annotations are HTML contentEditable divs positioned absolutely.
5. **Save** uses pdf-lib to read the original PDF bytes, then draws all annotations (strokes, shapes, text) onto the corresponding PDF pages at the correct coordinates.
6. **Download** triggers a blob download of the modified PDF. The original file is never altered.

## Privacy

InkPDF processes everything locally. Your PDF never leaves your device. There are no analytics, cookies, tracking pixels, or server calls of any kind. The external resources loaded are Google Fonts (typography) and CDN-hosted JavaScript libraries (PDF.js and pdf-lib).

## Contributing

Contributions are welcome. Here are some ideas for improvements.

- Image stamp / signature insertion
- PDF form field editing
- Page rotation and reordering
- Dark/light theme toggle
- Mobile touch optimization
- PWA support for offline use
- Sticky notes with collapse/expand

To contribute, fork the repo, create a feature branch, and submit a pull request.

## License

MIT License. See [LICENSE](LICENSE) for details.

---

Built with care. Edit with confidence.
