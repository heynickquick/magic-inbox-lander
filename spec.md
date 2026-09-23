# Magic Inbox — Lead Magnet Opt-In Mockup

## Project Context

**Brand:** Co-Writing With AI (Nick Quick's newsletter / course business).
**Product:** "Magic Inbox" — a free system that turns a user's inbox into an AI email assistant. Email goes in, replies / follow-ups / receipts / bookings come out.
**Audience:** Knowledge workers, solopreneurs, creators, marketers — people drowning in email who'd pay for hours back.
**Goal of this page:** Convert email opt-ins to the free Magic Inbox setup. Form posts to `https://go.cowritingwithai.com/magic-inbox-thank-you` via FlexiFunnels (`form id flexiForm_64475`).
**Mood:** Cinematic, premium, "tech-magical." Reads like a launch trailer, not a SaaS landing page. The user wants the *exact* aesthetic from the reference image: dark charcoal stage, mint-green neon, glowing product hero, friendly robot mascot, sparkle accents, iPhone showing the email list.

## Hero Section Philosophy

**Image-Led + Type-Composite.** The hero is dominated by a high-fidelity 3D render on the right (book + robot + phone), with chunky display type and copy on the left. No autoplay video — the still image carries it. The "Free guide" pill in the reference becomes the badge.

- Left column (~58%): eyebrow, oversized display H1, sub, proof chips, then the email opt-in form (kept structurally identical to the live FlexiFunnels form).
- Right column (~42%): hero product image, full-bleed dark with floor reflection, glow halo behind the composition.

## Color Palette (NON-NEGOTIABLE — NO BLUE / NO PURPLE)

| Token | Value | Use |
|---|---|---|
| `--bg` | `#07070B` | Page base |
| `--bg-1` | `#0E0E14` | Section variation |
| `--bg-2` | `#15151E` | Card / panel |
| `--surface` | `#1C1C28` | Elevated cards, form inputs |
| `--border` | `#2A2A38` | Subtle dividers |
| `--mint` | `#3DFFB0` | Primary accent — glowing neon |
| `--mint-bright` | `#7CFFC8` | Highlights, sparkle cores |
| `--mint-deep` | `#1FA876` | Pressed states, gradient stops |
| `--ink` | `#F5F4EF` | Primary text (warm cream, not blue-white) |
| `--ink-soft` | `#B8B8C4` | Secondary text |
| `--ink-mute` | `#7A7A88` | Tertiary / micro |

All greens are nature-spectrum (mint/teal) — no blue shift, no purple. Verified against the skill's color constraint.

## Typography

- **Display ("Magic Inbox" wordmark & headlines):** `Boldonse` — heavy rounded display, the chunky "M" feel from the reference. (Google Fonts, free.)
- **Body:** `Inter` 400/500/700 — clean, premium, reads warm at small sizes.
- **Mono accent:** `JetBrains Mono` 400/700 — for the proof chips, form labels, micro copy.
- **Serif option:** `Fraunces` italic for occasional accent quotes.

Scale (desktop):
- H1: clamp(56px, 7vw, 112px), line-height 0.95, letter-spacing -0.02em
- H2: clamp(34px, 4.5vw, 64px), line-height 1.05
- H3 / section eyebrows: 13px tracked uppercase
- Body: 18px / 1.65
- Micro: 13px / 1.5

## Layout

- Max-width: 1280px
- Side gutters: 32px (mobile 20px)
- Section vertical rhythm: 120px top/bottom (88px mobile)
- 12-col grid (visual), with hero as 7/5 split

## Motion (subtle — premium not gimmicky)

- Hero load: H1 stagger-fade up (60ms steps), proof chips reveal left-to-right, image fade-in with slow scale (1.04 → 1.0) over 1.2s
- Scroll: section headings sweep-fade in, illustration groups fade-up 12px
- Hover on primary CTA: button glow intensifies, mint arrow nudges right 4px
- Sparkles in hero: gentle drift / twinkle (CSS keyframes, 6–9s loops, staggered)
- Floor reflection: subtle parallax on scroll (translate3d)

No bouncy springs, no auto-playing audio, no flashing.

## Tech Strategy

- **Stack:** Static HTML5 + embedded CSS + minimal vanilla JS. No build step, no frameworks.
- **Fonts:** Google Fonts preconnect + display=swap.
- **Form:** Preserved **exactly** as the FlexiFunnels runtime expects. Form ID `flexiForm_64475`, all original classes (`flexi-form`, `ff-orderform-theme`, `ft-input-block`, `ft-form-btn`, `ffbtntxt`, hidden Encharge helper `flexiForm_64475_encharge`), `data-nextgo="https://go.cowritingwithai.com/magic-inbox-thank-you"`, `data-target="_self"`. Submit button keeps its original classes so the runtime JS still finds it. **We do not re-implement submission** — the original runtime handles it.
- **Copy:** Preserved **verbatim** from the live page. H1, sub, eyebrow, proof chips, all body paragraphs, all task list items, all CTAs, microcopy, byline — none altered, none added.
- **Assets:** AI-generated hero composite (book + robot + phone + glow), and a few section accent illustrations. All in `./imgs/`. WebP where possible, JPG fallback. `loading="lazy"` on below-fold. `onerror` handlers on every img.
- **Responsive:** Mobile-first, breakpoints at 640 / 768 / 1024 / 1280.

## Sections (preserved order, all 9)

1. **Hero** — eyebrow + H1 + sub + proof chips + opt-in form + hero product image
2. **"I Gave My Assistant An Email Address"** — body + stacked-envelope dark illustration + pull quote
3. **Tasks panel** — 5 swept task items in dark glassmorphic panel
4. **"Most Expensive Assistant"** — body + dark receipt illustration + scroll-to-form CTA
5. **"Five Moves Nobody On The Other End Can See"** — body + dark email BCC illustration
6. **Notes / Substack** — body + dark substack→list illustration
7. **"Wake Up To Work"** — dark close-section with final CTA (already dark in original — refresh with neon accents)
8. **Byline** — Nick Quick avatar + bio
9. **"Now Go Hire Yours"** — final nudge CTA

Footer: privacy link only (preserved).

## Form Specifics — Must Stay Identical

```html
<form id="flexiForm_64475" data-formid="flexiForm_64475" data-droptype="form" class="flexi-form flexi-vform-box ff-orderform-theme">
  <div class="flexi-form-inner">
    <div class="ft-input-groups">
      <div class="ft-input-group ft-vinput-box">
        <label class="ft-input-label d-none"></label>
        <div type="email" class="ft-input-block">
          <input type="email" name="email" placeholder="Email ID" required="true" class="ft-input-height ft-form-ctl ft-input-vstyle">
        </div>
      </div>
    </div>
    <div class="ft_as_com_div ft-com-btnstyle">
      <a data-formid="flexiForm_64475" data-smsg="Your details were submitted successfully" data-formmode="ft-flexi" data-ftbuttontype="1" href="#submit" class="ft-form-btn ft-btn-vstyle" data-nextgo="https://go.cowritingwithai.com/magic-inbox-thank-you" data-target="_self">
        <span class="ffbtnmaintxt"><span class="ffbtntxt">Submit</span></span>
        <span class="ffbtnsubtxt"> </span>
      </a>
    </div>
  </div>
</form>
<!-- Hidden Encharge helper also kept identical -->
<form id="flexiForm_64475_encharge" ...> ... </form>
```

The visible submit button label text is overwritten to "Get Free Access" via JS (already done on the live page — we replicate that). The hidden email-sync handler is also kept.

## Asset Manifest

| File | Use |
|---|---|
| `./imgs/hero-product.webp` | Hero — book + robot + phone mockup, dark mint-glow 3D render |
| `./imgs/section-stack.webp` | Section 2 — dark stacked-envelopes / to-do pile illustration |
| `./imgs/section-receipt.webp` | Section 4 — dark mint receipt illustration |
| `./imgs/section-email-bcc.webp` | Section 5 — dark email BCC mockup |
| `./imgs/section-substack.webp` | Section 6 — dark substack→list flow illustration |
| `./imgs/avatar.webp` | Byline avatar (or use existing original URL) |

Hero image is the priority — section illustrations can be CSS/SVG composites if generation is constrained.

## Output Checklist

- [ ] spec.md (this file) — done
- [ ] Assets generated and saved under `./imgs/`
- [ ] `index.html` — clean, semantic, responsive, all 9 sections preserved
- [ ] Form `flexiForm_64475` left structurally identical
- [ ] All copy verbatim from live page
- [ ] No console errors, no 404s on media
- [ ] Deployed and live URL delivered