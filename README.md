# Knee Ability Zero PWA

A progressive web app for tracking the ATG Knee Ability Zero program. Installed on your iPhone via Safari's "Add to Home Screen" — works offline, no app store needed.

**Live URL:** https://finleydecker.github.io/knee-ability-zero-pwa/

## How it works

Three files — that's it:

- `index.html` — the entire app (HTML, CSS, JS all inline)
- `sw.js` — service worker that caches everything for offline use
- `manifest.json` — tells iOS to treat it as a standalone app

GitHub Pages serves these as a static site. The service worker caches them on first load, so the app works offline after that.

## Install on iPhone

1. Open the live URL in Safari
2. Tap the Share button (box with arrow)
3. Tap "Add to Home Screen"

## Making changes

1. Edit files in this repo
2. Bump `CACHE_NAME` in `sw.js` (e.g. `kaz-v6` → `kaz-v7`) so the service worker invalidates the old cache
3. Push to `main` — GitHub Pages auto-deploys via the workflow in `.github/workflows/pages.yml`
4. Open the app on your phone — it picks up the new version on next launch

## Data storage

All workout history is stored in the browser's `localStorage` on your phone. Nothing is sent to a server. If you clear Safari data, you lose your history.
