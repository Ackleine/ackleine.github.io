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

# 💫About Me :
I'm an IT Support Analyst and technician with hands-on experience in network diagnostics, field ISP work, and systems support. Raised in foster care and living with disabilities, I focus on building practical tools that help troubleshoot, document, and recover systems — while sharing what I've learned to help others. Open to collaboration, mentoring, and contract work; reach out via my profile or Discord.

# 💻Tech Stack
![C#](https://img.shields.io/badge/c%23-%23239120.svg?style=for-the-badge&logo=c-sharp&logoColor=white) ![C++](https://img.shields.io/badge/c++-%2300599C.svg?style=for-the-badge&logo=c%2B%2B&logoColor=white) ![HTML5](https://img.shields.io/badge/html5-%23E34F26.svg?style=for-the-badge&logo=html5&logoColor=white) ![Lua](https://img.shields.io/badge/lua-%232C2D72.svg?style=for-the-badge&logo=lua&logoColor=white) ![JavaScript](https://img.shields.io/badge/javascript-%23323330.svg?style=for-the-badge&logo=javascript&logoColor=%23F7DF1E) ![CSS3](https://img.shields.io/badge/css3-%231572B6.svg?style=for-the-badge&logo=css3&logoColor=white) ![Azure](https://img.shields.io/badge/azure-%230072C6.svg?style=for-the-badge&logo=azure-devops&logoColor=white) ![Cloudflare](https://img.shields.io/badge/Cloudflare-F38020?style=for-the-badge&logo=Cloudflare&logoColor=white) ![Netlify](https://img.shields.io/badge/netlify-%23000000.svg?style=for-the-badge&logo=netlify&logoColor=#00C7B7) ![FastAPI](https://img.shields.io/badge/FastAPI-005571?style=for-the-badge&logo=fastapi) ![Express.js](https://img.shields.io/badge/express.js-%23404d59.svg?style=for-the-badge&logo=express&logoColor=%2361DAFB) ![.Net](https://img.shields.io/badge/.NET-5C2D91?style=for-the-badge&logo=.net&logoColor=white) ![Apache](https://img.shields.io/badge/apache-%23D42029.svg?style=for-the-badge&logo=apache&logoColor=white) ![Nginx](https://img.shields.io/badge/nginx-%23009639.svg?style=for-the-badge&logo=nginx&logoColor=white) ![MariaDB](https://img.shields.io/badge/MariaDB-003545?style=for-the-badge&logo=mariadb&logoColor=white) ![SQLite](https://img.shields.io/badge/sqlite-%2307405e.svg?style=for-the-badge&logo=sqlite&logoColor=white) ![MySQL](https://img.shields.io/badge/mysql-%2300f.svg?style=for-the-badge&logo=mysql&logoColor=white) ![MicrosoftSQLServer](https://img.shields.io/badge/Microsoft%20SQL%20Sever-CC2927?style=for-the-badge&logo=microsoft%20sql%20server&logoColor=white) ![Adobe After Effects](https://img.shields.io/badge/Adobe%20After%20Effects-9999FF.svg?style=for-the-badge&logo=Adobe%20After%20Effects&logoColor=white) ![Gimp Gnu Image Manipulation Program](https://img.shields.io/badge/Gimp-657D8B?style=for-the-badge&logo=gimp&logoColor=FFFFFF) ![Blender](https://img.shields.io/badge/blender-%23F5792A.svg?style=for-the-badge&logo=blender&logoColor=white) ![PyTorch](https://img.shields.io/badge/PyTorch-%23EE4C2C.svg?style=for-the-badge&logo=PyTorch&logoColor=white) ![CMake](https://img.shields.io/badge/CMake-%23008FBA.svg?style=for-the-badge&logo=cmake&logoColor=white) ![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white) ![Raspberry Pi](https://img.shields.io/badge/-RaspberryPi-C51A4A?style=for-the-badge&logo=Raspberry-Pi)
# 📊GitHub Stats :
![](https://github-readme-stats.vercel.app/api?username=ackleine&theme=radical&hide_border=false&include_all_commits=false&count_private=false)<br/>
![](https://github-readme-streak-stats.herokuapp.com/?user=ackleine&theme=radical&hide_border=false)<br/>
![](https://github-readme-stats.vercel.app/api/top-langs/?username=ackleine&theme=radical&hide_border=false&include_all_commits=false&count_private=false&layout=compact)

---
[![](https://visitcount.itsvg.in/api?id=ackleine&icon=0&color=0)](https://visitcount.itsvg.in)


## Contact
For changes or questions, open an issue or edit `index.html` directly.

---
Generated README for the current single-file site. Adjust any text (API keys, URLs) before publishing.
