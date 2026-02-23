# 🍳 BigHead Character Cooker

A browser-based character creation and animation tool built for the **Big Head Billionaires** universe. Users can mix and match layered character parts, record voiceovers with automatic lip sync, and export animated video clips — all in a single `index.html` file with no dependencies or server required.

---

## 🚀 Live Demo

> Host `index.html` on any static server or open it directly in your browser.  
> No build step. No npm. No backend.

---

## 📁 Repo Structure

```
BigHeadCharacterCooker/
├── index.html          # The entire app — all JS, CSS, and logic lives here
├── ASSETS/             # Misc UI assets and icons
├── BACKGROUNDS/        # Scene background images
├── BODY/               # Body layer sprite sheets / PNGs
├── EYES/               # Eye expressions (open, blink, etc.)
├── GIRL/               # Female character variant parts
├── HEAD/               # Head shape options
├── MOUTH/              # Mouth shapes for lip sync (A, E, I, O, U, rest, etc.)
├── OUTFIT/             # Clothing and accessory options
└── TEXTURE/            # Skin tones and surface textures
```

Each folder contains **numbered PNG files** that map to character customization options in the UI. The app loads them dynamically — so adding new options is as simple as dropping in a new file.

---

## ✨ Features

- **Layered Character Builder** — Mix heads, bodies, eyes, mouths, outfits, textures, and backgrounds
- **Automatic Lip Sync** — Records microphone audio and maps detected phonemes to mouth shape frames in real time
- **Blink Animation** — Auto-generated blink keyframes on a natural, randomized timer
- **Timeline Controls** — Scrub, preview, and adjust your animation before exporting
- **Video Export** — Renders the final animation with synced audio to a downloadable video file
- **Animated Export Progress** — Visual progress bar during render so you know the app is working
- **Auto Settings Configuration** — Export settings are automatically detected and applied based on your recording

---

## 🔧 How to Fork & Customize for Your Own Project

This tool was designed with remixability in mind. Here's how to adapt it:

### 1. Swap Out the Art

All character parts are plain PNGs organized by body region. To use your own art:

- Drop your PNGs into the appropriate folder (e.g., `HEAD/`, `MOUTH/`, `OUTFIT/`)
- Follow the existing naming convention (numbered files: `1.png`, `2.png`, etc.)
- The app will automatically pick them up — no code changes needed for adding options

> **Mouth shapes for lip sync** are mapped in a specific order. Check the mouth images in `MOUTH/` and match your artwork to the same phoneme sequence (rest, open, wide, round, etc.) to keep lip sync working correctly.

### 2. Change the Branding

All UI text, colors, and the app title live inside `index.html`. Search for:
- `"BigHead"` or `"Big Head Billionaires"` to update the branding copy
- CSS variables or inline styles near the top of the `<style>` block to retheme colors

### 3. Adjust Lip Sync Behavior

The lip sync system analyzes microphone audio amplitude and frequency to select mouth frames. To tune it:
- Look for the audio analysis / mouth-mapping section in the JS inside `index.html`
- Adjust the amplitude thresholds to match your character's mouth shapes

### 4. Add or Remove Character Layers

The layer system is modular. To add a new category (e.g., `HATS/`):
- Create the folder and add your PNGs
- Add a new layer entry in the character builder section of `index.html` following the same pattern as existing layers

### 5. Deploy

Because this is a single `index.html` with relative asset paths, you can host it on:
- **GitHub Pages** (free, just enable it in repo settings)
- **Netlify / Vercel** (drag and drop the folder)
- **Any static file host**

> ⚠️ **Microphone access requires HTTPS.** If you're testing locally, use a local server (`npx serve .` or VS Code Live Server) rather than opening the file directly, or mic recording won't work.

---

## 🎙️ Microphone / Audio Notes

- The app requests microphone permission on load for the lip sync feature
- Audio is recorded locally in the browser — nothing is sent to a server
- For best lip sync results, record in a quiet environment close to the mic
- Audio/video sync is handled during the export render, not during live preview

---

## 🛠️ Tech Stack

- **Vanilla JavaScript** — No frameworks
- **HTML5 Canvas** — Character rendering and animation
- **Web Audio API** — Microphone capture and amplitude analysis for lip sync
- **MediaRecorder API** — Video export
- Single `index.html` file — everything bundled, no build tools needed

---

## 📝 License & Credits

Built by [B.HaleyArt](https://github.com/BHALEYART) for the **Big Head Billionaires** show.

If you fork this for your own project, a credit or shoutout is appreciated but not required. Have fun cooking up some characters! 🍳
