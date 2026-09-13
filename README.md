# Stitchy Mobile 🧵

A privacy-first, offline cross-stitch companion for iPad, iPhone, and modern
browsers. Import a portable Stitchy backup, mark stitches with touch or Apple
Pencil, isolate colors, attach notes, park threads, and keep your place without
uploading the pattern anywhere.

## Live demo

[Open the live Stitchy Mobile app](https://makoffka.github.io/stitchy-mobile/) and choose **Try bunny demo**. The included demo is
an original pattern derived from the Stitchy bunny logo.

## Highlights

- Installable Progressive Web App
- Works offline after its first load
- Touch and Apple Pencil marking
- Pinch zoom, one-finger pan, and Fit
- Color isolation and thread palette
- Notes, parked threads, Undo, and progress totals
- Distraction-free stitching session with timer and screen-wake protection
- Multiple projects stored locally in IndexedDB
- Portable `.stitchy.zip` import and export
- No accounts, analytics, telemetry, or pattern-upload service

## Privacy architecture

GitHub Pages serves only the application shell. Imported files are read with
the browser File API and stored in IndexedDB on the user's device. Pattern
contents are not sent to GitHub or to any application server.

## Install on iPhone or iPad

1. Open the live site in Safari.
2. Tap **Share**.
3. Choose **Add to Home Screen**.
4. Launch Stitchy from the new Home Screen icon.

## Run locally

```bash
python3 -m http.server 8765
```

Open `http://127.0.0.1:8765`. Localhost is treated as a secure context for
service-worker development. Public PWA installation requires HTTPS.

## Repository safety

This public repository intentionally excludes purchased patterns and the
private desktop conversion engine. CI fails if XSD, SAGA, CSS-pattern, PDF, or
unexpected Stitchy backup files enter the repository. The sole allowed backup
is `demo/stitchy-bunny.stitchy.zip`, which contains original demo data and no
XSD payload.

## Technology

Vanilla HTML, CSS, and JavaScript; Canvas rendering; IndexedDB persistence;
Service Worker offline caching. There is no framework and no build step.

## License

Application source is available under the MIT License. Pattern files imported
by users remain their own and are not covered by this repository's license.
