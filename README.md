# Northstar Workspace

A responsive, vanilla HTML/CSS/JavaScript productivity mini-suite.

## Run locally
1. Unzip the project.
2. Open `index.html` directly, or run a local server from this directory:
   - Python: `python -m http.server 8000`
   - Visit `http://localhost:8000`
3. Login accepts any username/password, including empty fields. It is a demo gate, not authentication.

## Pages
- `index.html`: login
- `home.html`: dashboard
- `tasks.html`: task organizer, persisted in `localStorage`
- `powerpoint.html`: PPTX package validation and conversion status
- `cables.html`: cable puzzle

## PowerPoint conversion limitation
The interface intentionally does **not** claim to convert a PPTX into PNGs. A `.pptx` is an OOXML package, and PptxGenJS is a presentation authoring library, not a general renderer for arbitrary uploaded decks. The current page uses JSZip to inspect a selected PPTX and report its slide count, but it does not fabricate preview images. To enable true conversion, integrate and test a dedicated browser-compatible OOXML slide renderer or use a server-side LibreOffice/PowerPoint rendering service. The included JSZip/PptxGenJS scripts are loaded from jsDelivr, so internet access is required for package inspection; all task and puzzle logic is local.

## Storage and privacy
Tasks are saved in the browser's `localStorage`; demo username is held in `sessionStorage` unless “Remember me” is checked. Nothing is sent to a backend.
