# ✂️ SnipSmart

> A Chrome extension that lets you capture any area of your screen, extract text via OCR, and translate it — all without leaving your browser.

Submitted to the **Google Chrome Built-in AI Challenge 2025**.

---

## Features

- **Screen Snipping** — Click and drag to select any region of the current tab
- **OCR Text Extraction** — Powered by [Tesseract.js](https://tesseract.space/), extracts text from the captured image entirely client-side (no server required)
- **Image Enhancement** — Automatically preprocesses captures (contrast boost, upscaling) to improve OCR accuracy
- **Confidence Score** — Each extraction is accompanied by a confidence percentage so you know how reliable the result is
- **Translation** — Translate extracted text into 18 languages using the free [MyMemory API](https://mymemory.translated.net/) — no API key needed
- **Snippet History** — Stores your last 10 snips locally with thumbnails, timestamps, and one-click copy/view
- **Clipboard Support** — Copy extracted or translated text to your clipboard instantly

---

## Demo

![SnipSmart popup showing OCR result and translation](frontend/public/SnipSmart-icon-128.png)

---

## Tech Stack

| Layer | Technology |
|---|---|
| Extension framework | Chrome Manifest V3 |
| UI | React 19 + Vite |
| OCR engine | Tesseract.js v6 |
| Translation | MyMemory Translation API |
| Storage | Chrome Storage API (local) |

---

## Installation

### From Source

1. **Clone the repo**
   ```bash
   git clone https://github.com/your-username/SnipSmart.git
   cd SnipSmart/frontend
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Build the extension**
   ```bash
   npm run build
   ```

4. **Load into Chrome**
   - Open Chrome and navigate to `chrome://extensions`
   - Enable **Developer mode** (toggle in the top right)
   - Click **Load unpacked**
   - Select the `frontend/dist` folder

The SnipSmart icon will appear in your Chrome toolbar.

---

## Usage

1. Click the **SnipSmart** icon in your toolbar to open the popup
2. Click **✂️ Start New Snip**
3. Click and drag over any area on the current page to capture it
4. SnipSmart will enhance the image and extract any text automatically
5. Optionally, select source and target languages and click **🔄 Translate**
6. Use **📋 Copy Text** or **📋 Copy Translation** to copy results to your clipboard

### Supported Translation Languages

Spanish · French · German · Italian · Portuguese · Russian · Chinese · Japanese · Korean · Arabic · Hindi · Dutch · Polish · Turkish · Swedish · Norwegian · Danish · Finnish

---

## Development

Run the extension in watch mode during development:

```bash
cd frontend
npm run dev
```

To lint the project:

```bash
npm run lint
```

The project uses **Vite** with `vite-plugin-static-copy` to bundle Tesseract's WASM assets alongside the extension output.

---

## Privacy

SnipSmart processes all OCR **locally in your browser** using WebAssembly — your screenshots never leave your device. Translation requests are sent to the MyMemory public API, which does not require an account or API key.

---

## License

[MIT](LICENSE)

---

## Acknowledgements

- [Tesseract.js](https://github.com/naptha/tesseract.js) — OCR in the browser
- [MyMemory Translation API](https://mymemory.translated.net/) — Free machine translation
- Google Chrome Built-in AI Challenge 2025
