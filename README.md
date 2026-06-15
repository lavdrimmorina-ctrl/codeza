# Codéza

> A minimalist digital manuscript for musicians — store, organize, and read your song lyrics on stage.

![PWA](https://img.shields.io/badge/PWA-ready-blueviolet) ![Offline](https://img.shields.io/badge/offline-first-green) ![License](https://img.shields.io/badge/license-MIT-blue)

## Overview

Codéza is a single-file Progressive Web App built for performers. It runs entirely in the browser, stores all data locally via IndexedDB, and works fully offline after the first visit.

## Features (Phases 1–3)

- **Library** — Create, read, update, delete songs with title, artist, key, BPM and tags
- **Editor** — Manuscript-style editor with section formatting (`# Verse`, `# Chorus`…) and inline chord notation (`[Am]`, `[F#m7]`)
- **Viewer** — Rendered lyric view with section dividers, chord highlighting and metadata chips
- **Performance Mode** — Distraction-free OLED-dark full-screen view with adjustable font size (14–42px), tap-to-toggle HUD, screen wake lock, read progress bar, and keyboard scroll control
- **Themes** — Light, dark, and system-matching; OLED-optimised for stage use
- **Offline** — Service Worker + IndexedDB; no server, no account, no sync needed
- **Installable** — Full PWA with manifest, icons, and install prompt

## Roadmap

| Phase | Status | Feature |
|-------|--------|---------|
| 1 | ✅ | App shell, PWA, IndexedDB, theme engine |
| 2 | ✅ | Song CRUD, editor, lyric renderer |
| 3 | ✅ | Performance Mode, font controls, wake lock |
| 4 | 🔜 | Auto-scroll with speed controls |
| 5 | 🔜 | Setlists — group songs, swipe navigation |
| 6 | 🔜 | Polish, offline audit, install hardening |

## Stack

| Layer | Choice | Why |
|-------|--------|-----|
| Framework | Vanilla HTML/CSS/JS | Zero build step, maximum portability |
| Fonts | Inter + Lora (Google Fonts) | UI precision + manuscript character |
| Icons | Lucide (CDN) | Consistent, lightweight stroke icons |
| Storage | IndexedDB (raw) | No size limits, no external deps |
| PWA | Service Worker + manifest | Real offline, installable |
| Deployment | GitHub Pages | Free, fast, zero-config |

## Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| `⌘N` / `Ctrl+N` | New song |
| `⌘K` / `Ctrl+K` | Focus search |
| `⌘S` / `Ctrl+S` | Save (in editor) |
| `⌘↵` / `Ctrl+Enter` | Preview (in editor) |
| `F5` | Enter Performance Mode |
| `Esc` | Exit Performance Mode / close modal |
| `+` / `-` | Font size (in Performance Mode) |
| `Space` | Page down (in Performance Mode) |
| `↑` / `↓` | Scroll (in Performance Mode) |

## Lyric Syntax

```
# Verse 1          → section heading
# Chorus           → another section
[Am]word [F]word   → inline chord token
**bold text**      → bold
*italic text*      → italic
                   → blank line = spacer
```

## Deployment (GitHub Pages)

1. Fork or clone this repo
2. Go to **Settings → Pages**
3. Set source to **Deploy from a branch** → `main` → `/ (root)`
4. Visit `https://your-username.github.io/codeza/`

No build step. No config. The entire app is `index.html` + `sw.js` + `manifest.json` + `icons/`.

## Project Structure

```
codeza/
├── index.html          # Complete app (HTML + CSS + JS)
├── sw.js               # Service Worker (Cache-First strategy)
├── manifest.json       # PWA manifest
├── icons/
│   ├── icon-192.png    # PWA icon (Android, Chrome)
│   ├── icon-512.png    # PWA icon (splash screen)
│   └── icon-apple-touch.png  # iOS home screen icon
├── .gitignore
└── README.md
```

## License

MIT — use it, fork it, play it on stage.
