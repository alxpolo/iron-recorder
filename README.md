# Iron Recorder PWA — free iPhone version

This is the $0 / no-Mac version.

## What works
- Import several audio files at once from the iPhone Files picker, including an attached USB/OTG recorder if iOS exposes it there.
- Store imported recordings in the app using IndexedDB.
- Transcribe on-device/in-browser with Whisper Tiny through Transformers.js.
- Generate a usable title, category, short extractive summary, and tags.
- Export the original audio under the generated filename.
- Install to the iPhone Home Screen once hosted over HTTPS.

## iPhone limitation
Safari/PWAs cannot silently wake up and auto-import files merely because a generic USB mass-storage recorder was plugged in. On iPhone, the free web version must show the Files picker and you select the new files. Once selected, processing can be automatic.

## Fast free deployment

### GitHub Pages
1. Create a free GitHub account/repository.
2. Upload `index.html`, `manifest.webmanifest`, and `sw.js` to the repository root.
3. In the repository: Settings -> Pages -> Deploy from branch -> main / root.
4. Open the resulting HTTPS Pages address in Safari on your iPhone.
5. Share button -> Add to Home Screen.

### Any other free static host
These three files are a static website, so any HTTPS static host works.

## First transcription
The first run downloads a Whisper model from Hugging Face. It can take a while and use substantial data. Wi‑Fi is recommended. Later runs may reuse the browser cache.

## Privacy
No OpenAI key is required. The included transcription runs in the browser. Audio is stored locally in that browser's IndexedDB. The model itself is loaded from public CDN/model hosting.
