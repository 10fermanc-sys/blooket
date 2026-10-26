# Blooket overlay demo for GitHub Pages

This repository contains a simple static GitHub Pages site that embeds Blooket in an iframe and adds a floating HUD overlay.

## Important browser security note

A normal web page cannot run JavaScript inside a cross-origin iframe such as `https://www.blooket.com` because browsers enforce the same-origin policy. That means:

- You cannot directly read or modify Blooket's DOM from your GitHub Pages site.
- You cannot inject custom code into the iframe's page unless the iframe is same-origin, you control the target page, or you use a browser extension / user script solution.
- The overlay here is a floating UI layered on top of the iframe, which is the safe and supported approach for GitHub Pages.

## Files

- `index.html` — the main page with the embedded iframe and overlay
- `styles.css` — page and HUD styling
- `script.js` — overlay controls and interaction logic

## Deploy on GitHub Pages

1. Push this repo to GitHub.
2. Open the repo in GitHub.
3. Go to Settings → Pages.
4. Set the source to the default branch and root folder.
5. Save and wait for the site to publish.

Your pages URL will be similar to:

`https://<your-user-name>.github.io/blooket/`

## Optional advanced option

If you truly need code to run inside the iframe itself, the only practical ways are:

- host a same-origin copy of the app you control,
- run a local proxy / reverse proxy you own,
- use a browser extension or userscript that runs with elevated privileges.

A GitHub Pages site alone cannot modify the DOM of a different origin in the browser.
