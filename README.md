# 呪術廻戦 — SATORU GOJO

An interactive hand-tracking particle experience built with Three.js and MediaPipe. Control cursed techniques in real time using your webcam and hand gestures — just like Gojo.

---

## Demo

Open `index.html` in a browser, allow webcam access, and unleash your cursed energy.

---

## Gestures

| Gesture | Technique | Visual Effect |
|---|---|---|
| 🤏 Pinch | **Hollow Purple** | Explosive purple particles erupt in all directions with intense bloom |
| 🖐️ Open palm | **Malevolent Shrine** | Domain expansion with structured pillars, formations, and crimson glow |
| ✌️ Two fingers | **Infinite Void** | Infinite void particles in spherical formation with cyan accents |
| ☝️ Index finger | **Red** | Spiraling red energy arms with fiery crimson particles |
| Neutral | **Neutral** | Minimal cursed energy particles in default state |

---

## How It Works

### Stack
- **[Three.js](https://threejs.org/) r160** — 3D particle rendering via `THREE.Points` with additive blending
- **[MediaPipe Hands](https://developers.google.com/mediapipe/solutions/vision/hand_landmarker)** — real-time hand landmark detection (21 keypoints per hand)
- **`UnrealBloomPass`** — HDR bloom glow, strength varies per technique (1.0-4.0)
- No build step — single HTML file, all dependencies via CDN

### Particle System
20,000 particles share three typed arrays (`position`, `color`, `size`). Each technique defines a target configuration; every animation frame lerps the current arrays toward the targets:

```js
pos[i] += (targetPos[i] - pos[i]) * 0.1;
```

All techniques use the same lerp speed for smooth transitions. Particles are positioned using spherical coordinates for organic formations, with color and size attributes for visual variety.

### Gesture Detection
Finger state is determined by comparing tip landmark Y to PIP joint Y — lower Y on screen means the finger is extended:

```js
const isUp = (t, p) => lm[t].y < lm[p].y;
const pinch = Math.hypot(lm[8].x - lm[4].x, lm[8].y - lm[4].y);
```

Priority order: pinch → all 4 up → 3 up → 2 up → 1 up.

---

## Running Locally

No install required. Just open the file:

```bash
# Option 1 — direct file open
open index.html    # macOS
start index.html   # Windows

# Option 2 — local server (recommended for some browsers)
npx serve .
# or
python -m http.server 8080
```

> **Note:** Chrome and Edge work best. A webcam is required.

---

## Project Structure

```
SATORU GOJO/
└── index.html    # Everything — scene, particle systems, hand tracking, UI
└── README.md
```

---

## Inspired By

- Jujutsu Kaisen (Gege Akutami)