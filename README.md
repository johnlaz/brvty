# BRVTY — Book Intelligence PWA

AI-powered book summaries with audio narration. Built for your commute.

## Deploy to GitHub Pages (5 minutes)

### Option A — Single File Deploy (Simplest)
1. Create a new GitHub repo (e.g. `brvty`)
2. Upload `brvty.html` → rename it to `index.html`
3. Go to **Settings → Pages → Branch: main → / (root)** → Save
4. Your app is live at `https://yourusername.github.io/brvty`

### Option B — Full Package Deploy
1. Create a new GitHub repo
2. Upload ALL files from this package as-is
3. Go to **Settings → Pages → Branch: main → / (root)** → Save
4. Live at `https://yourusername.github.io/repo-name`

---

## Install as PWA (Add to Home Screen)

### iPhone / iPad (Safari)
1. Open your GitHub Pages URL in **Safari**
2. Tap the **Share** button → **Add to Home Screen**
3. Name it `BRVTY` → Add
4. Launch from home screen — runs fullscreen, no browser chrome

### Android (Chrome)
1. Open URL in **Chrome**
2. Tap ⋮ menu → **Add to Home Screen** or look for the install prompt
3. Tap Install

### Desktop (Chrome / Edge)
1. Open URL
2. Click the **install icon** in the address bar (⊕ or computer icon)

---

## Get Your Gemini API Key (Free)
1. Go to **https://aistudio.google.com**
2. Sign in with Google → Click **Get API Key**
3. Create key → Copy it
4. Open BRVTY → tap ⚙ Settings → paste key → Save
5. Free tier: 10 requests/min, 250/day — plenty for personal use

---

## Files in This Package

| File | Purpose |
|------|---------|
| `index.html` | The complete app (single file, self-contained) |
| `icon-192.png` | PWA icon (home screen, Android) |
| `icon-512.png` | PWA icon (splash, high-res) |
| `icon-180.png` | Apple Touch Icon (iOS home screen) |
| `icon-152.png` | iPad icon |
| `icon-120.png` | iPhone icon |
| `README.md` | This file |

> **Note:** The icons are also embedded inline in `index.html` as base64, so the app works perfectly even if deployed as a single file without the icon PNGs.

---

## Features
- **Generate** — Enter any book title (+optional notes) → Gemini 2.5 Flash returns structured JSON: thesis, key pillars, deep dives, action items, quotes
- **Audio** — Gemini TTS narrates a custom audio script in 4 voices. Plays as proper WAV audio.
- **Car Mode** — Fullscreen large-button player. Registers with Media Session API so steering wheel controls work.
- **Library** — All summaries + audio saved locally in IndexedDB. Searchable. Persistent.
- **Vault** — Export/import your entire library (text + audio) as a `.brvty` file for backup or cross-device transfer.
- **Offline** — Service Worker caches the app shell. Works without internet after first load.

---

## Tech
- Vanilla JS — no framework, no build step
- Gemini 2.5 Flash (`generateContent` with `responseMimeType: application/json`)
- Gemini 2.5 Flash Preview TTS (PCM→WAV conversion built-in)
- IndexedDB for local persistence
- Media Session API for car/headphone controls
- Service Worker for offline support

