# Support Jarod Mowry — Website

This repository is a single-page static website (client-side HTML/CSS/JS) that presents a personal support/donation page and several small utilities.

- Main file: [index.html](index.html)

## Key Features
- Neon/glitch visual theme with Three.js background:
  - Large emissive globe, animated starfield, and low-poly wireframe shapes.
  - Location page (`my location`) contains an interactive wireframe bouncing ball art (`initIllinoisArt()`).
- Discord integration UI:
  - Fixed Discord action button and a popup containing a mini 3D ball rendered into a `<canvas id="popup-ball">`.
  - Popup includes Copy username and Open Discord App/Web actions.
- Animated favicon:
  - A small 64×64 canvas renders a spinning globe and updates the browser favicon dynamically.
- Donation flow via PayPal SDK integration (client-side `paypal.Buttons()` usage).
- Developer utilities: IP/MAC/domain lookup, EXIF viewer, Imgur upload.

## Notable Changes (recent)
- Replaced the bouncing sphere with a wireframe line-rendered ball and matching shadow.
- Rewrote the global Three.js scene for a neon globe, stars, and wireframe shapes.
- Replaced the external Discord logo in the popup with an inline canvas and added `startPopupBall()` / `stopPopupBall()` to initialize/dispose the mini-ball only when the popup is open.
- Removed all music/YouTube-related UI and scripts.
- Added an animated favicon that falls back to a gradient if cross-origin image data cannot be exported.
- Added loader gating so popups and buttons remain disabled until the initial typing/loader finishes (`setDiscordUIEnabled()` helper).

## How to Run
1. Clone or copy the repository to your local machine.
2. Open `index.html` in a modern browser (Chrome, Edge, Firefox).

Notes:
- For some features (Google Maps Places & Directions) to work fully, the included Google Maps API key must be valid and the page should be served over HTTPS (or `localhost`) to enable geolocation.
- If you open the file over `file://` some features (Google Maps, geolocation, cross-origin textures) may be limited.

Recommended quick test (serve locally):

```bash
# using a simple Python http server from the project root
python -m http.server 8000
# then open http://localhost:8000/index.html
```

## Files of Interest
- `index.html` — entire application (UI, styles, Three.js scenes, popup logic).

## Development Notes
- Three.js is loaded from CDN (r128). If you wish to upgrade, check API changes before bumping the version.
- Popup mini-ball and background globe are intentionally lightweight; the popup renderer starts/stops with the popup to conserve CPU.
- Favicon generation uses `canvas.toDataURL()`; some hosts disallow exporting cross-origin images — the script falls back to a gradient animation in that case.

## Customization
- Visuals: tweak colors/rotation speeds inside `init3D()` and `startPopupBall()`.
- Favicon: change the source texture URL in the favicon script near the bottom of `index.html`.
- Remove/restore features: music/YouTube code was removed intentionally; re-adding requires reintroducing script tags and UI blocks.

## Troubleshooting
- If the popup logo is blank, ensure WebGL is enabled and the browser supports WebGL contexts on `<canvas>`.
- If PayPal buttons do not render, verify the PayPal SDK script is loaded and the client ID is valid.
- If Google Maps fails, check the console for billing or API key errors and ensure the API key allows the Places & Directions libraries.

## Contact
For changes or questions, open an issue or edit `index.html` directly.

---
Generated README for the current single-file site. Adjust any text (API keys, URLs) before publishing.
