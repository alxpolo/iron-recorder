# Iron Recorder PWA v3

Fixes the transcription error:
`Cannot specify task or language for an English-only model`

Cause:
The app uses `whisper-tiny.en`, which is already English-only. Transformers.js rejects explicit `language` / `task` generation options for that model.

Fix:
The transcription call now uses only chunking options.

Replace these files in the GitHub repo:
- index.html
- manifest.webmanifest
- sw.js

Then open your Pages URL with `?v=3` once.
Example:
https://YOURNAME.github.io/iron-recorder/?v=3

You should see `v3` under the Iron Recorder title.
