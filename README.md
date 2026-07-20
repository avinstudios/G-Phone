# G-phone — Jewelry OS 1

A phone UI shell styled after the "Jewelry OS 1" mockup: pearl wallpaper, gold-ringed hardware sensor, circular app icons, and a jewelry-forward app set (Catalog, Shop, Design, and room to add more). No build step — install it to a real phone's home screen and it behaves like a native app icon.

## What's in here
- `index.html` — the whole simulator (markup + styles + logic, no build step)
- `manifest.json` — PWA manifest (name, icons, colors) that makes "Add to Home Screen" install a real app icon instead of a bookmark
- `sw.js` — a minimal service worker so it can be installed and opened offline
- `icon-192.png` / `icon-512.png` — the gold gem app icon

## Matches the mockup
- Status bar: battery, wifi, fingerprint, and volume glyphs
- Nav row: a gold-ringed "sensor" button (tap to lock the screen), a house icon (returns home), and the faceted gem brand mark (tap for the "G-phone · Jewelry OS 1" about sheet)
- Home screen: circular icons in a mix of ivory and tinted backgrounds, echoing the sketch's mixed black/white icon style
- App set: Catalog, Phone, Mail, Messages in the dock; Shop, Browser, Files, Design, News, Contacts, Translate, Voice Memo on the grid — the repeated placeholder icons from the sketch were consolidated into a single "Shop" app, with empty grid space left open (use Settings → Add app to fill it in as you design more screens)
- Lock screen: serif clock, tap the sensor to lock/unlock

## Features
- Long-press an icon to enter edit mode (wiggle + remove)
- "Add app" flow — name it, give it an emoji/icon, drop it on the grid
- Settings drawer: gold accent color, wallpaper gradient, grid column count (3/4/5)
- Everything persists in the browser's local storage
- Installable as a PWA so it can live on a phone's actual home screen

## Put it on GitHub

```bash
cd phone-sim
git init
git add .
git commit -m "Initial commit: G-phone Jewelry OS 1"
git branch -M main
git remote add origin https://github.com/<your-username>/<your-repo>.git
git push -u origin main
```

## Turn on GitHub Pages
1. On GitHub, go to your repo → **Settings → Pages**
2. Under "Build and deployment", set **Source** to `Deploy from a branch`
3. Pick branch `main`, folder `/ (root)`, then **Save**
4. GitHub gives you a URL like `https://<your-username>.github.io/<your-repo>/` — that's your live simulator

## Add it to your phone's Home Screen
This is what makes it launch like a real app instead of opening in a browser tab.

**iPhone (Safari):**
1. Open the GitHub Pages URL in Safari
2. Tap the **Share** icon (square with an arrow)
3. Scroll down and tap **Add to Home Screen**
4. Tap **Add** — the icon now appears on your home screen and opens full-screen, no browser bar

**Android (Chrome):**
1. Open the URL in Chrome
2. Tap the **⋮** menu → **Add to Home screen** (or **Install app** if Chrome offers it directly)
3. Confirm — it installs like an app

Note: **HTTPS is required** for "Add to Home Screen" to register the manifest/service worker and behave like an app rather than a bookmark. GitHub Pages serves over HTTPS automatically.

## Customizing further
Everything lives in `index.html` — no framework, no build tools. The app list, colors, and icons are defined near the top of the `<script>` block (`DEFAULT_APPS`), and the visual tokens are CSS variables at the top of the `<style>` block if you want to push the jewelry aesthetic further before wiring screens to real functionality.
