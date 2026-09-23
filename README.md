# Magic Inbox Lander

Lead-magnet opt-in page for **Magic Inbox: Your AI Email Assistant**, hosted at `go.cowritingwithai.com/magic-inbox`.

Dark charcoal `#07070B` + mint neon `#3DFFB0` aesthetic. Single-page static HTML, no build step.

## Stack

- Vanilla HTML/CSS/JS — no bundler, no framework
- Fonts: Sora (display), Inter (body), JetBrains Mono (chips/microcopy), Fraunces (italic accent)
- Form: FlexiFunnels runtime (`flexiForm_64475`) preserved verbatim — submits to `https://go.cowritingwithai.com/magic-inbox-thank-you`
- Hidden Encharge helper form (`flexiForm_64475_encharge`) is kept and synced on submit

## File map

```
index.html                       # the page (single file, all CSS/JS embedded)
spec.md                          # design tokens + section manifest
imgs/
  hero-product.png               # hero 3D book + robot + phone (transparent BG)
  logo.png                       # Co-Writing With AI brand mark
  avatar.webp                    # author avatar (byline section)
```

## Local preview

Just open `index.html` in a browser. Or serve it locally:

```bash
python -m http.server 8080
# then visit http://localhost:8080
```

## Design notes

- **Hero** is 2-column (copy + form left, image right) sized to keep the entire pitch above the fold at 1440×900 and 390×844.
- **Proof chips** are a 2×2 grid with embedded SVG checkmark and a staggered shimmer sweep.
- **Section 2** envelope illustration uses `position:sticky; top:18vh` to scroll-with-reader; the section uses `background-attachment:scroll` (not `fixed`) so the sticky containing block isn't broken.
- **Section 6** uses a clean "Magic Inbox · Live" task panel in place of a heavy Substack→YourList flow graphic.
- **Footer** tagline: *"Field notes on handing the boring parts of your inbox to something that doesn't mind."*

## Deployment

Published as a static site. Single-file build, no asset pipeline beyond copying `index.html` + `imgs/` into the deploy root.
