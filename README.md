# YourBook

A browser-based PDF audiobook reader with highlights, notes, and natural-sounding narration.

Drop a PDF in. Press play. Listen while the words highlight in sync with the audio. Drag-select any passage to highlight it in one of six colors, add a note and tags, and find them all on the Notes page later. Everything stays in your browser — no servers, no accounts, no cloud.

## Features

- **Two voice modes** — free browser TTS (the "Robotic" voice) or natural-sounding narration via your own ElevenLabs API key
- **Word-by-word sync highlighting** as the audio plays
- **Smart chapter detection** — uses the PDF's table of contents when it's clean, falls back to a font-size + heading heuristic when it isn't
- **Drag-select highlighting** — select any passage in the reader, click the floating Highlight button, pick a color
- **Notes & tags** — attach commentary to any highlight, organize by tag
- **Library** — every PDF you upload is saved to your browser; create custom lists to organize them
- **Export** — download all your notes as a Word document or Markdown file
- **Privacy by default** — everything (PDFs, highlights, notes, your API key) lives in your browser's IndexedDB and localStorage. Nothing is sent to any server except ElevenLabs, and only the text being narrated.

## Quick start

1. Open the live site (see Deploy section below)
2. Drag any PDF onto the reader page
3. Press **Play** — the free Robotic voice works immediately
4. For better narration, set up an ElevenLabs API key (see Help page in-app for permissions guide)

## Tech

Single-file HTML app. No build step, no framework, no backend.

- **PDF parsing**: [PDF.js](https://mozilla.github.io/pdf.js/) (CDN)
- **Free voice**: Web Speech API (built into the browser)
- **Natural voice**: [ElevenLabs](https://elevenlabs.io) streaming TTS API (your key, your account)
- **Storage**: IndexedDB for PDFs and notes, localStorage for the API key and preferences
- **Word document export**: hand-written ZIP + OOXML, no library
- **Fonts**: Manrope (body), Fraunces (display), JetBrains Mono (numbers/UI)

## Deploy

The site is a single static HTML file. Anything that serves static files works:

- **Netlify Drop**: drag `pdf_audiobook.html` onto [app.netlify.com/drop](https://app.netlify.com/drop) — done in 30 seconds
- **GitHub Pages**: enable Pages in repo settings, point at the root branch
- **Vercel / Cloudflare Pages**: connect the repo, no build command needed
- **Local**: open the file in a browser. (Note: some features need an HTTPS context, so a deployed version is more reliable than `file://`)

## License

MIT — see LICENSE file. Use it, modify it, ship it.

## Acknowledgments

Built on top of PDF.js and ElevenLabs. Inspired by the desire to actually finish dense academic PDFs without staring at a screen.
