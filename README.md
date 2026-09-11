# Airlock Scratchpad — support site

The public pages for [Airlock Scratchpad](https://apps.apple.com/us/app/airlock-scratchpad/id6808056086?mt=12),
a secure scratchpad for short-lived developer secrets on macOS.

**The app's source is not public; its design document is** — and it is served
from here, so that claim is one anyone can check rather than one they have to
take on trust.

| File | Served at | What it is |
|---|---|---|
| `index.html` | Support URL — the one given to App Store Connect | Getting started, and the questions users actually ask |
| `design.html` | `design.html` | Threat model, cryptography, expiry, the limits, and the commands to verify the main claims without the source |
| `why.html` | `why.html` | Why the app exists, and what was deliberately not built |
| `privacy.html` | Privacy policy URL | |
| `style.css` | — | Shared styling |

Every page links to every other, so none of them is a dead end.

## Keeping it honest

`design.html` is generated from `Docs/design-overview.md` in the app
repository, which is the source of truth. **When the security model or the
app's behaviour changes, that document changes and this page is regenerated.**

A published design document that has drifted is worse than none: it is a
specific, checkable claim that has quietly stopped being true. An earlier
hand-edited copy of the design fell four revisions behind without anyone
noticing, which is why it is generated now.

## Publishing

GitHub Pages, from the `main` branch root:
**Settings → Pages → Source: Deploy from a branch → main → / (root)**

A deploy takes a minute or two after a push. Check it landed:

```
gh api repos/rbongard/airlock-scratchpad-support/pages/builds/latest \
  --jq '{status: .status, commit: .commit}'
```

- `https://rbongard.github.io/airlock-scratchpad-support/`
- `https://rbongard.github.io/airlock-scratchpad-support/design.html`
- `https://rbongard.github.io/airlock-scratchpad-support/why.html`
- `https://rbongard.github.io/airlock-scratchpad-support/privacy.html`

All must return 200. A support URL that 404s is a rejection.

## Support

Questions and bug reports arrive as
[issues](https://github.com/rbongard/airlock-scratchpad-support/issues) on this
repository — which means notifications need to be on for it.
