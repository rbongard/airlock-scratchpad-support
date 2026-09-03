# Airlock Scratchpad — support site

The support and privacy pages for [Airlock Scratchpad](https://apps.apple.com/),
a secure scratchpad for short-lived developer secrets on macOS.

This repository holds **only these pages**. The app's source is not public; its
design document is.

| File | Served at |
|---|---|
| `index.html` | Support URL — the one given to App Store Connect |
| `privacy.html` | Privacy policy URL |
| `style.css` | Shared styling |

## Publishing

GitHub Pages, from the `main` branch root:
**Settings → Pages → Source: Deploy from a branch → main → / (root)**

The first deploy takes a minute or two. After that:

- `https://rbongard.github.io/airlock-scratchpad-support/`
- `https://rbongard.github.io/airlock-scratchpad-support/privacy.html`

Both must return 200 before submitting to App Review — a support URL that
404s is a rejection.
