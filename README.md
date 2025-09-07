# Flapper — Web Export (v1.0)

**Live demo / deployment**
Play online: https://flapper-godot-web.vercel.app/

**Repository**
This repository contains the Godot HTML5 / WebAssembly export (static web build) for *Flapper*. The repo includes the web artifacts produced by the Godot export (e.g. `index.html`, `index.wasm`, `index.pck`, `index.js`, audio worklets and icons).

---

## Short description
This is the web-export of *Flapper* — a compact Flappy‑Bird style game exported from Godot to run in the browser. Files required to run the build are included in the repo and the site is deployed to Vercel.

---

## What’s included
- `index.html` — entry page for the web export.  
- `index.wasm` — WebAssembly runtime / engine binary.  
- `index.pck` — packed project data (game assets and scenes).  
- `index.js`, audio worklet files, icons and other static assets.

---

## Features (same gameplay as desktop)
- Classic Flappy‑Bird controls and scoring (tap/click to flap, avoid pipes).  
- Procedural pipes and scrolling ground.  
- Score counter + persistent high score (where browser storage is available).  
- Sound effects (if browser autoplay rules allow audio).

---

## Play (quick)
Open the live site: https://flapper-godot-web.vercel.app/ and the game should load in a modern desktop browser.

---

## Run locally (development / testing)
To run the web build locally you must serve the files over HTTP (browsers usually block WASM or fetches from `file://`):

1. Clone the repo:
```bash
git clone https://github.com/Tanish-Desai/Flapper-godot-web.git
cd Flapper-godot-web
```

2. Start a simple static server from the folder that contains `index.html`:

- Python 3:
```bash
python -m http.server 8000
# then visit http://localhost:8000
```

- Or using Node (if installed):
```bash
npx http-server -p 8000
# then visit http://localhost:8000
```

3. Open the page in a modern browser (Chrome, Edge, Firefox). If you see a message like “Your browser does not support the canvas tag” or a blank page, ensure JavaScript is enabled and your browser supports WebAssembly.

---

## Notes about browser compatibility & behavior
- Use a modern desktop browser (Chromium-based browsers and recent Firefox work best). Mobile support varies and may require additional input/touch polish.  
- Some browsers restrict autoplay of audio — user interaction (a click) may be required before SFX or music will play.  
- Serving via HTTPS (like Vercel) is recommended for best behavior and to avoid mixed-content or blocked resource issues.

---

## Troubleshooting
- Blank screen / immediate failure: make sure you served the files over HTTP(S) (not `file://`) and opened the correct `index.html`.  
- “Canvas / JS not supported” messages: confirm JS is enabled and try a different modern browser.  
- Audio not playing: browser autoplay policy may block sound until user interacts with the page.  
- If the game fails to load engine files (`.wasm`, `.pck` etc.), check your server is sending correct `Content-Type` headers (static servers and Vercel handle this automatically).

---

## Re-deploying / Hosting
- The repo is already deployed to Vercel — to redeploy or host elsewhere, push the static files (the folder with `index.html`, `index.wasm`, `index.pck`, etc.) to any static host (Vercel, Netlify, GitHub Pages, S3 + CloudFront). Vercel auto-deploys from a Git repo when configured.

---

## How this build was produced (developer notes)
- This repository contains a Godot HTML5 / WebAssembly export of Flapper (the export creates the `.html`, `.js`, `.wasm` and `.pck` artifacts). If you want to re-export from the source project, open the original Godot project and use the HTML5 export preset (ensure export templates for your Godot version are installed). The output files are then the static assets used here.

---

## Attribution & contact
Project by **Tanish-Desai**. Live demo: https://flapper-godot-web.vercel.app/. Repository contents (web build files) are in the repo.

---
