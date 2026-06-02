<div align="center">
  <img src="logo.svg" width="120" alt="Glory Read Logo">
  <h1 align="center" style="margin-top:16px">Glory Read</h1>
  <p align="center" style="color:#888;font-size:16px;margin-bottom:24px">
    3D sight word explorer for early readers
  </p>

  <p>
    <img src="https://img.shields.io/badge/words-1,849-ffd866?style=flat-square&labelColor=0a0a2a" alt="1,849 words">
    <img src="https://img.shields.io/badge/sound%20groups-55-ff4b6e?style=flat-square&labelColor=0a0a2a" alt="55 sound groups">
    <img src="https://img.shields.io/badge/3D-Three.js-ffd866?style=flat-square&labelColor=0a0a2a" alt="Three.js 3D">
    <img src="https://img.shields.io/badge/ages-4–7-ffd866?style=flat-square&labelColor=0a0a2a" alt="Ages 4-7">
    <img src="https://img.shields.io/badge/license-MIT-ff4b6e?style=flat-square&labelColor=0a0a2a" alt="MIT License">
  </p>
</div>

<br>

A beautifully crafted 3D reading app that helps early readers build phonics skills through immersive, Star Wars–inspired word exploration. Each word appears as glowing 3D text against a starfield, with the target sound pattern highlighted in red so children can visually map letters to sounds.

<br>

## ✦ Preview

Open [`preview.html`](preview.html) in any modern browser — zero setup, no build tools needed.

| What you'll see | How it works |
|---|---|
| <img src="logo.svg" width="32" alt=""> Words float into view as 3D text with subtle depth and glow | Each word holds at center for **5 seconds** — plenty of time to sound it out |
| <img src="logo.svg" width="32" alt=""> The target sound appears in **red** (e.g., "b**at**") | A label at the top shows which sound is being practiced (`✦ at ✦`) |
| <img src="logo.svg" width="32" alt=""> Same-sound words appear in groups of 4 | Builds pattern recognition: "bat, cat, fat, hat" → "they all end with _at_!" |
| <img src="logo.svg" width="32" alt=""> Tap or click to advance at your own pace | Full control — linger longer on tricky words or skip ahead |

<br>

## ✦ Features

- **1,849 sight words** across **55 phonics sound groups** — short vowels, digraphs, blends, and silent-e patterns
- **3D typography** — clean, bevel-free 3D text with subtle drop shadows and warm gold emissive glow
- **Sound highlighting** — every word's target phonics pattern is rendered in coral red for visual mapping
- **Progressive groups** — 4 words per sound family before moving to the next (e.g., 4 × `-at` → 4 × `-an` → 4 × `-ip` → ...)
- **Cinematic 3D environment** — deep gradient starfield with twinkling stars, ambient particles, and subtle camera sway
- **Bloom post-processing** — soft glow that enhances without blurring letterforms
- **Fullscreen mode** — press `F` or double-click
- **No dependencies** — loads Three.js from CDN, everything runs in the browser

<br>

## ✦ Word List

All words live in [`words.json`](words.json) and are organized by sound pattern:

```json
{ "sound": "at",  "words": ["bat","cat","fat","hat","mat","pat","rat","sat","that","flat","brat","chat","spat","slat"] },
{ "sound": "an",  "words": ["can","fan","man","pan","ran","tan","van","than","plan","bran","clan","scan","span"] },
{ "sound": "sh",  "words": ["ship","shop","shut","fish","dish","wish","cash","rush","shell","shoe","shot","shed"...] },
{ "sound": "a",   "words": ["bake","cake","date","gate","hate","lake","make","name","rake","sale","take"...] },
```

**Sound categories covered:**

| Category | Groups | Examples |
|---|---|---|
| Short vowels | 26 | `-at`, `-an`, `-ip`, `-ot`, `-ug`, `-ell`, `-ing`… |
| Digraphs | 5 | `sh`, `ch`, `th`, `wh`, `ck` |
| Blends | 18 | `bl`, `br`, `cl`, `cr`, `dr`, `fl`, `fr`, `gr`, `pl`, `pr`, `sc`, `sk`, `sl`, `sm`, `sn`, `sp`, `st`, `sw`, `tr`, `tw` |
| Long vowels (silent-e) | 4 | `a` (bake), `i` (kite), `o` (bone), `u` (cube) |

<br>

## ✦ Usage

1. Clone or download this repo
2. Open `preview.html` in a browser
3. Watch the first word appear — read it aloud together
4. Tap the screen or click to move to the next word
5. Press `F` for fullscreen mode

That's it. No server, no install, no build step.

<br>

## ✦ Customizing

### Add your own words
Edit [`words.json`](words.json) — each group has a `sound` key and a `words` array. The code automatically finds the sound substring in each word and highlights it red.

### Change pacing
Open `preview.html` and look for these constants near the top of the module script:

```js
const FI = 1.2     // fade-in duration (seconds)
const HOLD = 5     // reading hold time
const FO = 1.5     // fade-out duration
const GAP = 0.5    // pause between words
```

### Adjust colors
The gold and red material colors are defined inside `createWord()`:
- `gold`: `0xffd866` (text color), `0xffaa22` (emissive glow)
- `red`: `0xff4b6e` (text color), `0xff2244` (emissive glow)

<br>

## ✦ Tech

| | |
|---|---|
| **3D Engine** | [Three.js](https://threejs.org/) (r160) via CDN |
| **Post-processing** | UnrealBloomPass for soft glow |
| **Typography** | TextGeometry with helvetiker bold |
| **Data** | Static JSON — no backend needed |
| **Format** | Single HTML file + word list |

<br>

## ✦ License

MIT — use it, fork it, make it your own.

---

<div align="center">
  <p style="color:#666;font-size:13px">Made with <span style="color:#ff4b6e">✦</span> for early readers</p>
</div>
