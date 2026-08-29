# jonnasingh.github.io

Personal academic site. Plain HTML + CSS — no build step, no dependencies.

## Files

| file | what it is |
|---|---|
| `index.html` | all the content |
| `style.css` | all the styling (light + dark) |
| `cv.pdf` | linked from the header and footer — awards, talks, service live here |
| `profile.jpg` | headshot |
| `papers/*.jpg` | one figure per paper in Selected |
| `.nojekyll` | tells GitHub Pages to serve the files as-is |
| `cv.html` | the CV source — edit this, then re-print to `cv.pdf` |
| `variants/` | abandoned style explorations — gitignored, delete whenever |

## Type

Inter for everything, IBM Plex Mono for labels, dates, and venues. Both load
from Google Fonts via the `<link>` in `index.html`; there's a system fallback
stack if that request fails.

## Structure

- **Updates** — five most recent, reverse-chronological, with a `<details>`
  toggle holding the rest. No JavaScript.
- **Research** — three tiers: `Selected` (with figures), `Outreach`,
  `Collaborations`.
- Everything else — full talk list, awards, teaching, service — is in `cv.pdf`
  on purpose. Keep it that way and the page stays short.

## Paper figures

Drop a replacement into `papers/` keeping the filename and it appears
automatically. The frame is **4:3 (132 × 100)**; images are letterboxed and
centered, so nothing is ever cropped, but a 4:3 crop fills the box best.

- `easipass.jpg` · `camp.jpg` · `lc.jpg` · `birdsong.jpg`

## Preview locally

Double-click `index.html`. Or:

```bash
python -m http.server 8000     # then open http://localhost:8000
```

## Publish

1. On GitHub, create a public repo named exactly `jonnasingh.github.io`.
   Don't add a README or .gitignore.
2. In this folder:

```bash
git init
git add .
git commit -m "initial site"
git branch -M main
git remote add origin https://github.com/jonnasingh/jonnasingh.github.io.git
git push -u origin main
```

3. Settings → Pages → Deploy from a branch → `main` / `(root)`.
4. Live at https://jonnasingh.github.io

Updates after that: `git add . && git commit -m "update" && git push`

## The CV

`cv.html` is the source; `cv.pdf` is what the site links to. Inter is embedded
in the HTML as base64, so it renders identically anywhere with no network.

To regenerate after editing `cv.html`: open it in Chrome, Ctrl+P, Save as PDF,
Letter, margins **None** (the `@page` rule sets them), Background graphics on.
Save over `cv.pdf`.

## Loose ends

- The CNN link sits in the footer, unlabeled beyond "CNN".
- No ViDA link yet.
- Two dates I couldn't verify and took from the old CV: the Neuromodulation GRC
  talk (2019 there, 2018 in your 2026 biosketch) and the Duke Brown Bag / DIBS
  Symposium years.
