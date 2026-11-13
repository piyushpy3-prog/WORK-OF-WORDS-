# WORK OF WORDS — Signature Studio

A browser-based PDF/image signature placement tool by **Piyush.PY**.

## Run locally

1. Extract the project folder.
2. Open `index.html` in a modern browser (Chrome, Edge, Firefox or Safari).
3. Internet access is needed to load PDF.js and pdf-lib from their CDNs on first use.
4. Choose one PDF/image document and one signature image. The signature accepts common browser-readable image formats such as PNG, JPG/JPEG, WebP, GIF, BMP, SVG and AVIF. It is normalized to PNG in memory for consistent PDF export.
5. Select pages, drag the signature, resize it from the corner, or enter exact X/Y/width percentages.
6. Download the signed PDF or the current page as a PNG.

For best compatibility, run it through a local static server instead of opening the file directly:

```bash
python -m http.server 8000
```

Then visit `http://localhost:8000` from this folder.

## Features

- PDF documents with multiple pages, plus PNG/JPG/WebP image documents.
- A signature image layer. Common browser-readable image formats are accepted and normalized to PNG for PDF export; source transparency is retained when supported by the format.
- Independent placement, position and size on every page.
- Drag-to-move, corner-handle resize, numeric X/Y/width controls, and quick position presets.
- Copy the current placement to all pages or remove it from the current page.
- High-resolution PDF export and current-page PNG export.
- Files are processed locally in the browser. The site does not upload document or signature files to a server.

## Export note

For standard PDFs without rotated pages, the signature is normalized to a PNG overlay (retaining transparency when the source supports it) and the original PDF text, vectors and page quality are retained. If the source PDF contains rotated pages, the app uses a high-resolution visual export so the signature position matches the preview; that rotated-document export is flattened, so text is not selectable/searchable. Image documents export as a one-page PDF. Your original file is never modified.

## Libraries

- PDF.js 3.11.174 (document rendering)
- pdf-lib 1.17.1 (PDF generation)
