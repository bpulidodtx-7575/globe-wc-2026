# 🏆 globe-wc-2026

An interactive 3D globe of all **48 nations** competing at the **2026 FIFA World Cup**
(hosted by Canada, Mexico and the USA), colour-coded by confederation with full
group-stage details from the final draw.

🔗 **Live demo:** https://bpulidodtx-7575.github.io/globe-wc-2026/

> _Add a screenshot or GIF here (e.g. `preview.png`) — it is also referenced by the
> Open Graph / Twitter social-share tags in `index.html`._

## Features

- 🌍 **Photorealistic 3D globe** (NASA Blue Marble texture) with atmosphere,
  graticules, a starfield and smooth auto-rotation.
- 🎨 **Confederation colour-coding** — UEFA, CONMEBOL, CONCACAF, CAF, AFC and OFC
  each get their own colour, with host nations highlighted in gold.
- 🔎 **Search** any qualified nation to fly the globe straight to it.
- 🏳️ **Real country flags** in tooltips, labels and the detail card.
- 📋 **Detail card** on click — confederation, group letter and group opponents.
- ♿ **Accessible** — keyboard shortcuts, focus styles, ARIA live regions and labels.
- 📱 **Responsive** layout for desktop and mobile.
- 🛡️ **Resilient loading** — multi-CDN fallback for libraries and a timeout/abort
  guard on the map data so the page never hangs.

## Controls

| Action            | How                                   |
| ----------------- | ------------------------------------- |
| Rotate            | Drag                                  |
| Zoom              | Scroll / pinch                        |
| Toggle rotation   | Press **R** or **Space**              |
| Inspect a nation  | Hover (tooltip) or click (detail card)|
| Search            | Type a nation, press **Enter**        |
| Close detail card | **Esc** or the ✕ button               |

## Run locally

It is a single static file with no build step. Either open `index.html`
directly, or serve it (recommended, so the `fetch()` for map data works
without file-protocol restrictions):

```bash
python3 -m http.server 8000
# then open http://localhost:8000/
```

## Deploying (GitHub Pages)

The site lives at the repo root as `index.html`, so GitHub Pages needs no build:

1. Go to **Settings → Pages**.
2. Under **Build and deployment**, choose **Deploy from a branch**.
3. Select the `main` branch and the `/ (root)` folder, then **Save**.

A `.nojekyll` file is included so Pages serves the files as-is.

## Data source

Qualified teams, confederations and group assignments are taken from the
**2026 FIFA World Cup final draw** (5 December 2025) and verified against
Wikipedia / FIFA (last verified **2026-06-23**). Country polygons are matched
by ISO 3166-1 code (with a name fallback), so they stay accurate regardless of
dataset spelling. England and Scotland both qualified but share a single
United Kingdom map polygon, which is labelled to represent both.

## Tech / credits

- [Three.js](https://threejs.org/) · [globe.gl](https://github.com/vasturiano/globe.gl)
  · [topojson-client](https://github.com/topojson/topojson-client)
- Country geometry: [world-atlas](https://github.com/topojson/world-atlas) (Natural Earth)
- Globe textures: three-globe Blue Marble / topology imagery
