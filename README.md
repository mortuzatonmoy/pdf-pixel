# PDF Pixel

Private browser-based PDF to high-resolution PNG/JPG converter, made for Tonmoy.

## Features
- Drag-and-drop PDF upload (up to 100 MB), password-protected PDFs supported.
- 150, 300 and 600 DPI page rendering; PNG lossless or JPG with adjustable quality.
- All pages or ranges such as `1, 3-5`; individual downloads and ZIP export.
- Progress, cancellation, memory safeguards and a built-in sample.
- PDF content stays on your device. Dependencies are served locally, with no analytics or third-party CDN calls.

This renders complete PDF pages; it does not extract the original embedded image bytes. Higher DPI improves vector/text rasterization but cannot recover missing scan detail. Output is limited to 40 megapixels per page and 400 MB per batch. The DPI selector controls pixel dimensions; browser encoders may write default density metadata.

## Develop
Requires Node.js 22+ and npm. Run `npm install`, then `npm run build`. Serve `dist/` with any static HTTP server, e.g. `python -m http.server 4173 --directory dist`. Open http://localhost:4173. Do not open the HTML directly with `file://`.

## Deploy
Deploy `dist/` after building to any static host. The optional `.openai/hosting.json` binds the private Sites deployment. PDF.js and fflate are pinned in package.json; their licenses are copied into dist/vendor by the build script.

## Check
`node --test test.mjs`
