# WINAMP (web)

> it really whips the llama's ass 🦙

A browser recreation of the classic Winamp 2.x "base" skin — the squat charcoal window, green LCD display, dancing spectrum analyzer, scrolling title, and playlist. Built as one self-contained HTML file. Drop a track for the real reacting visualizer, or paste YouTube links to build a playlist.

![WINAMP](https://img.shields.io/badge/skin-base-1be23c?style=flat-square) ![no build](https://img.shields.io/badge/build-none-555?style=flat-square) ![MIT](https://img.shields.io/badge/license-MIT-blue?style=flat-square)

## Features

- **Faithful classic look** — 275x116 proportion, clutterbar, mono/stereo + kbps/kHz indicators, EQ/PL toggles, scanline atmosphere.
- **Local files -> real audio-reactive visualizer** — true FFT spectrum (peak-hold caps) + oscilloscope via the Web Audio API. Drag & drop anywhere. This is the mode for screen-recording content.
- **YouTube playlist** — paste multiple links (one per line) to queue them; auto-advances. Add a free API key to search by name.
- **Apple Music** (optional) — for subscribers, with an Apple Developer token.
- **Fullscreen MilkDrop visualizer** — the morphing 2004-style plugin (butterchurn). The money shot.
- **Playlist, seek, volume, balance, shuffle, repeat** — all working, in every mode.
- Zero dependencies to run locally. Zero build step. One file.

## Quick start

Open `index.html` in any modern browser. Drag music files onto the window — it plays and the visualizer reacts.

Live: https://unclemal-official.github.io/winamp-web/

> **Why host it?** Browsers block streaming services from arbitrary local files. YouTube and Apple Music only activate when the page is served from a real origin (GitHub Pages, your own domain). Local-file playback + the reacting visualizer work everywhere.

## Optional config

Open `index.html`, find the `CONFIG` block near the top of the `<script>`:

```js
var CONFIG = { YOUTUBE_API_KEY:"", APPLE_DEV_TOKEN:"", APP_NAME:"WINAMP" };
```

- **YouTube search by name** — put a YouTube Data API v3 key in `YOUTUBE_API_KEY`. Pasting a link needs no key.
- **Apple Music** — put a MusicKit developer token in `APPLE_DEV_TOKEN` (requires an Apple Developer membership).

## Note on the visualizer + streaming

Streaming audio (YouTube, Apple Music) is DRM-protected, so the Web Audio analyser can't read it — during streaming the bars run a beat-synced animation. **Local files get the real frequency reaction.** For recorded content, use local files.

## License

MIT — see [LICENSE](LICENSE). A tribute to the original Winamp / Nullsoft look. Not affiliated with or endorsed by the Winamp brand.
