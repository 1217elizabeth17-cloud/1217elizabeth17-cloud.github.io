# Synesthetic — PWA deploy bundle

A self-contained, installable Progressive Web App. Works offline after first load; syncs across devices when online.

## Deploy to Netlify (drag & drop — easiest)
1. Go to https://app.netlify.com/drop
2. Drag this entire `deploy/` folder onto the page.
3. Done — you get a live URL. Open it on your phone/Mac and choose "Add to Home Screen" / "Install" to run it like a native app.

## Deploy to Netlify (from Git)
- Publish directory: this folder (`deploy`)
- Build command: none (static site)

## What's inside
- `index.html` — the full app, everything inlined (offline-ready shell)
- `manifest.webmanifest` — app name, colors, icons (install metadata)
- `sw.js` — service worker (offline caching; network-first for navigation, cache-first for assets)
- `icons/` — 192 / 512 / maskable / apple-touch icons
- `_headers` — Netlify cache + content-type rules

## Notes
- Must be served over HTTPS for install + service worker (Netlify does this automatically).
- To publish an update: rebuild `index.html` from `Synesthetic.dc.html`, bump `CACHE` in `sw.js` (e.g. `synesthetic-v2`), and redeploy.
