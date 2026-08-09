# Investors Blueprint — Adriel Hsu

A full-viewport, arrow-navigated pitch deck for Adriel Hsu's real estate
development mentorship program ("Investors Blueprint").

## What this is

A single self-contained static HTML page — no build step, no dependencies
to install. Each of the deck's 15 sections fills the entire viewport; a
down/up arrow (bottom-right), a dot rail (right edge), the keyboard, mouse
wheel, or touch swipe move between them. A "Contents" button (bottom-left)
opens a drawer listing every section title for quick navigation.

## Running it locally

No build step — open `index.html` directly, or serve the folder so
relative asset paths and the appraisal PDF resolve correctly:

```bash
python3 -m http.server 8000
# then open http://localhost:8000/index.html
```

## Structure

```
index.html                          the entire site (markup, styles, script)
saphira-apartments.png              case-study section photo
saphira-apartments-appraisal.pdf    real appraisal document, viewable in-page
thumbnails/                         "Proof on Camera" and "Land Flips" images
```

## The in-page PDF viewer

Clicking "View appraisal document" opens the PDF inline using
[pdf.js](https://mozilla.github.io/pdf.js/) (Mozilla, Apache License 2.0),
bundled directly into `index.html` and rendered to a `<canvas>`. This is
deliberate: relying on a browser's native PDF viewer (`<embed>`, `<iframe>`,
or `window.open`) turned out to be unreliable across browsers and
Content-Security-Policy configurations, so the document is rendered
independently instead — nothing browser- or plugin-dependent to fail.

## Content notes

Some figures on the Land Flips slide (slide 12) are marked with `~` to
indicate they were reconciled/derived from other given figures rather than
sourced from a closing statement — worth double-checking against the real
paperwork before this goes out publicly.
