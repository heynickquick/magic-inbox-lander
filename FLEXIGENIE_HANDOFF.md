# FlexiGenie Handoff — Magic Inbox Lander

Everything you need to paste into **FlexiGenie** (FlexiFunnels' AI page builder) so it can rebuild this design on the FlexiFunnels platform **without breaking the form runtime**.

> **Live reference:** https://sa7m8wqkf3ehs.space.minimax.io
> **Source HTML:** `index.html` in this repo (single file, all CSS/JS embedded).
> **Form runtime contract (FlexiFunnels-native, must be preserved verbatim):** see §4.

## ⚠️ Which file to use

**Use `FLEXIGENIE_PROMPT.md`** — that's the single self-contained message designed to be pasted as ONE message into FlexiGenie. This file (`FLEXIGENIE_HANDOFF.md`) is the multi-section reference doc; the prompt-only version has everything inlined so it can't get truncated when pasted.

## Files in this handoff

| File | Purpose |
|---|---|
| `FLEXIGENIE_PROMPT.md` | **The single-message prompt.** Paste the content between the outer fences as your first (and only) message to FlexiGenie. |
| `FLEXIGENIE_HANDOFF.md` | This doc — the longer-form reference broken into sections. Use if FlexiGenie wants to dig deeper into any specific area, or if you'd rather send the brief in multiple messages. |

---

## 1. The Prompt to Paste into FlexiGenie

**Before pasting:** upload `imgs/hero-product.png` and `imgs/avatar.webp` to
your FlexiFunnels media library. The prompt below assumes those are
already in the library — replace `[HERO_IMAGE_URL]` and `[AVATAR_IMAGE_URL]`
with the URLs FlexiFunnels gives you after upload.

Copy everything between the fences below and paste it as the first message to FlexiGenie. Adjust the `[bracketed]` placeholders for your setup.

````
You are rebuilding a single-page lead-magnet opt-in on the FlexiFunnels platform.

The visual design, copy, and layout are locked. Your job is to recreate it
section by section on FlexiFunnels so it matches the live reference while
keeping the existing form runtime working exactly as it does today.

CRITICAL — DO NOT BREAK THE FORM RUNTIME
=========================================
The page already has a working FlexiFunnels opt-in form that must be reused,
not replaced. Specifically:

  • The visible form has id="flexiForm_64475" and posts on submit to
    https://go.cowritingwithai.com/magic-inbox-thank-you
    with data-target="_self" and data-smsg="Your details were submitted
    successfully".
  • A HIDDEN helper form with id="flexiForm_64475_encharge" sits in the
    same container. It exists to mirror the visible email value into the
    Encharge integration. Both forms must remain on the page, both with
    name="email" inputs, both posting to the same thank-you URL with
    data-target="_self". The helper is hidden via class
    "ff-hidden-encharge" and aria-hidden="true".
  • Submit button class "ft-form-btn" with data-formid="flexiForm_64475",
    data-formmode="ft-flexi", data-ftbuttontype="1".
  • Do not change form IDs, data-* attributes, class names (flexi-form,
    flexi-vform-box, ff-orderform-theme, ft-input-block, ft-form-ctl,
    ft-input-vstyle, ft-input-height, ft-com-btnstyle, ft-btn-vstyle,
    ffbtnmaintxt, ffbtntxt, ffbtnsubtxt), or the thank-you URL. Any
    change here breaks the integration.
  • Use FlexiFunnels' native form element to render the visible form so
    all the required classes/IDs/data-attrs are emitted automatically.
    Do not hand-roll the <form> tag in raw HTML.

What you need to do
===================
1. Add the four Google Fonts to <head>:
   Inter (400/500/600/700/800/900),
   Sora (600/700/800),
   JetBrains Mono (400/700),
   Fraunces italic (500/700).
2. Inject the design system (§2 below) as page-level CSS.
3. Build the page in this exact section order (§3 below), with the copy
   verbatim from §3 (do NOT reword a single line — the copy is a tested
   sales page, the wording is the design).
4. Place the EXISTING FlexiFunnels opt-in form inside the hero section,
   right below the proof chips and the "Get Free Access Now" heading.
   Override its placeholder text to "Your email address" and its submit
   label to "Get Free Access" via small inline JS or a FlexiFunnels
   form-level setting (do not change the form HTML).
5. Wire all "Give Me My Magic Inbox" buttons (in sections 4, 7, and 9)
   to smooth-scroll the page back to the hero form and focus the email
   field.
6. Match the visual design at 1440×900 desktop, 768×900 tablet, and
   390×844 mobile. The entire hero (eyebrow + headline + lead + 4 chips
   + CTA + email + button + microcopy) must fit above the fold on both
   desktop and mobile.

What you should NOT do
======================
  • Don't change the copy. Not a word.
  • Don't change form IDs, classes, data-* attrs, or the thank-you URL.
  • Don't drop the hidden Encharge helper form.
  • Don't remove the per-button data-nextgo / data-target / data-smsg.
  • Don't use any blue/purple in the palette. Charcoal + mint only.
  • Don't introduce an external image for the hero — the supplied
    hero-product.png (1122×1402 transparent BG) is the centerpiece.

  • Hero product image: [HERO_IMAGE_URL]  ← upload `imgs/hero-product.png`
  • Avatar (section 8): [AVATAR_IMAGE_URL]  ← upload `imgs/avatar.webp`

(Reference paths in the source repo, in case you need to verify the
files match the design: `imgs/hero-product.png` and `imgs/avatar.webp`
in https://github.com/heynickquick/magic-inbox-lander)

Asset URLs
==========
Two binary image files MUST be uploaded to FlexiFunnels' media library
BEFORE you start the FlexiGenie session, because the prompt references them
and FlexiGenie needs an actual image to use, not a path:

  1. Hero product image — `imgs/hero-product.png` from this repo
     (1122×1402, transparent BG, ~1.7 MB). Upload it; reference it in
     the hero right column with the caption "Magic Inbox — The Complete
     Guide, your AI email assistant". Max display width 440px desktop,
     hidden below 960px viewport.

  2. Avatar (byline section, section 8) — `imgs/avatar.webp` from
     this repo. Upload it; reference it in section 8 inside a 130px
     circular frame with mint gradient border.

The logo (`imgs/logo.png`) is preserved in this repo for your other uses
but is NOT used on this page — do not add it to the FlexiFunnels build.

Visual reference while FlexiGenie works
=======================================
Point FlexiGenie at the live URL so it can scrape the actual visual:

  https://sa7m8wqkf3ehs.space.minimax.io

Tell it: "Open this URL, study the rendered design, then rebuild it
section-by-section using the spec in §2, §3, §4 of the conversation
context above." FlexiGenie has browser tools — let it look.

Output
======
Produce the page on FlexiFunnels, then verify:
  • Visible form submits to https://go.cowritingwithai.com/magic-inbox-thank-you
  • Helper form is present in DOM and hidden
  • Submit button has data-formid="flexiForm_64475"
  • All "Give Me My Magic Inbox" buttons scroll back to the form
  • Hero is above-the-fold at 1440×900 and 390×844
  • All ten sections render in order with copy verbatim from §3
````

---

## 2. Design System

Inject this CSS into FlexiFunnels' page-level custom CSS. The tokens are the single source of truth.

### 2.1 Color tokens

```css
:root{
  --bg:        #07070B;   /* page background — true near-black charcoal */
  --bg-1:      #0B0B12;
  --bg-2:      #11111A;
  --bg-warm:   #0D0D14;
  --surface:   #1A1A26;   /* card / input surface */
  --surface-2: #232333;
  --border:    #2A2A38;
  --border-soft: #1F1F2C;
  --mint:      #3DFFB0;   /* primary mint neon */
  --mint-bright: #7CFFC8;
  --mint-deep: #1FA876;
  --mint-glow: rgba(61,255,176,0.45);
  --mint-soft: rgba(61,255,176,0.08);
  --ink:       #FAFAF7;   /* primary text */
  --ink-soft:  #D5D5DA;   /* body text — high contrast */
  --ink-mute:  #9A9AA8;   /* secondary text */
  --ink-faint: #5A5A66;   /* microcopy / footer */
}
```

**Palette rule:** charcoal + mint only. No blue, no purple. No warm browns or grays beyond the ink scale.

### 2.2 Typography

| Role | Font | Weight | Size | Notes |
|---|---|---|---|---|
| H1 (hero) | Sora | 800 | clamp(36px, 4.4vw, 60px) | line-height 1.02, letter-spacing -0.03em |
| H2 (section) | Sora | 800 | clamp(30px, 4.2vw, 56px) | letter-spacing -0.025em |
| Eyebrow / chip / micro | JetBrains Mono | 700 | 11–13px | letter-spacing 0.16–0.18em, uppercase |
| Body | Inter | 400 | 18px mobile / 19px desktop | line-height 1.75 |
| Lead | Inter | 400 | 1.0625em (=~20px) | line-height 1.65 |
| Accent italic | Fraunces | 500 italic | inherits | used for "Stole My Job" word in section 2 |

Load via:
```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link rel="stylesheet"
  href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800;900&family=Sora:wght@600;700;800&family=JetBrains+Mono:wght@400;700&family=Fraunces:ital,wght@1,500;1,700&display=swap">
```

### 2.3 Spacing

| Element | Desktop | Mobile |
|---|---|---|
| Section vertical padding | 140px | 88px |
| Container max-width | 1280px (with 40px gutters) | full-bleed with 24px gutters |
| Form input height | 48–54px | 48px |
| Primary CTA padding | 14px 22px | 14px 22px |

### 2.4 Primary CTA spec

```css
.cta-mint{
  display:inline-flex; align-items:center; justify-content:center; gap:10px;
  padding:14px 22px;
  font:700 15px 'Inter',sans-serif;
  color:#001510;
  background:var(--mint);
  border:none; border-radius:14px; cursor:pointer;
  box-shadow:
    0 0 0 1px rgba(61,255,176,0.4),
    0 10px 30px -8px var(--mint-glow),
    0 0 40px -10px var(--mint-glow),
    inset 0 1px 0 rgba(255,255,255,0.4);
  position:relative; overflow:hidden;
}
```

Add a 2.4s `cta-glow` keyframe pulse on the box-shadow and a 2.4s shine-sweep `::after` (skewX(-18deg), translateX 380%). The reverse-pointing arrow icon (`<svg class="rev">`) sits inside the button to its right.

---

## 3. Sections — In Order, With Verbatim Copy

The page is **nine sections + footer**, in this exact order. Each block below tells FlexiGenie what to render.

### 3.1 HERO — `<header class="hero">` (full-bleed, min-height: 100vh)

Two-column grid on desktop (1.15fr copy / 0.85fr image), stacked single-column on mobile.

**Left column (.hero-copy):**

- Eyebrow (`<p class="eyebrow">`):
  `Free. And It Works The Hours You Don't.`
- H1 (`<h1 class="h-display">`):
  `Open Your Laptop To Work That's ` + (gradient-text) `Already Been Done For You`
- Lead (`<p class="lead">`):
  `The Magic Inbox is an assistant with an email address of its own. You forward it the jobs buried in your inbox and it works through them while you're doing something else. Here's the whole setup, free, in about twenty minutes.`
- Proof chips (`<ul class="hero-proof">`), 2×2 grid, each has an SVG checkmark before the text:
  - `Replies Drafted.`
  - `Receipts Filed.`
  - `Follow-Ups Chased.`
  - `Before You Sat Down.`
- Opt-in CTA header (`<p class="optin-cta">`):
  - strong: `Get Free Access Now`
  - span: `The full Magic Inbox setup, sent to your inbox.`
- **FlexiFunnels opt-in form goes here.** (See §4. Form runtime contract.)
- Microcopy (`<p class="micro">`):
  `Your email stays private and you can leave whenever you want.`

**Right column (.hero-product):**

- Hero product image: `imgs/hero-product.png` (1122×1402, transparent BG), max-width 440px desktop / hidden on mobile.
- Mint radial glow behind it (`.hero-product-glow`).

### 3.2 SECTION 2 — "Stole My Job" (`.split.split-reverse`)

Two-column grid. **Copy on RIGHT, envelope illustration on LEFT.** Pull-quote spans full-width BELOW (not above — order:3 on `.pull`).

**Copy column:**
- H2:
  `I Gave My Assistant An ` + (gradient-text) `Email Address` + ` And It ` + (Fraunces italic accent) `Stole My Job`
- p: `I hated that job. The pay was shit, on account of it being me doing it for free at eleven at night. And I wasn't any good at it.`
- p: `Here's what the job actually was.`
- p: strong `Every inbox is a to-do list you didn't write.` ` Most of what's sitting in yours is a task wearing a sender's name. Book the thing. Pay the invoice. Answer the question. Find the file. Chase the person who went quiet on you.`
- p: `So you sort the list instead of working it. Emails that need nothing from you get archived. Emails that need something get snoozed, because not right now. A few get done, whichever ones you could stand that day.`
- p: `Tomorrow the snoozed emails are back, in exactly the state you left them. And they brought friends.`
- p: strong `So I stopped doing it.` ` My AI assistant has its own email address now. I forward it the emails I'd have snoozed, and they start getting done automatically.`

**Illustration column (`.illust-stack.illust-stack-sticky`):** stack of 5 envelope cards on a mint-glow radial, with 3 pulsing concentric rings. The wrapper uses `position:sticky; top:18vh; align-self:start` at ≥640px viewport so the illustration pins during scroll.

**Pull-quote BELOW (`.pull`):**
- Italic Fraunces, with mint diamond bullets before/after:
  `Sorting A To-Do List Finishes None Of It. It Only Decides The Order You Get To Feel Bad In.`

### 3.3 SECTION 3 — "Tasks You Keep Putting Off"

Centered H2:
`The Tasks You Keep Putting Off. ` + (gradient-text) `None Of Them Are Yours Anymore.`

Tasks panel (`.panel`), glass-morphism backdrop-filter blur(20px), 5 list items each with a mint checkmark marker:

1. `The quote you sent three weeks ago gets chased, so it stops being money you never collected`
2. `The buyer who can't find their login gets working access and a written reply, before they email you a second time`
3. `Every "I'll have that to you by Friday" you send comes back as a reminder on Thursday`
4. `Your client's new requirement goes into that client's brief, instead of staying buried four replies deep`
5. `The receipt gets filed with its vendor, amount and date, so tax season stops being an archaeology dig`

After the panel:
- p strong `And that's just five tasks off your list. The Magic Inbox takes dozens more, and the best ones are the ones you invent yourself.`
- p strong `Adding one of your own takes a sentence.` ` Tell it how to handle that kind of email once, and it handles it from then on.`

### 3.4 SECTION 4 — "Most Expensive Assistant"

Two-column (`.split.split-receipt`), copy on LEFT.

**Copy column:**
- H2:
  `You Are The ` + (gradient-text) `Most Expensive Assistant` + ` You Will Ever Employ`
- p: `Work out roughly what an hour of your time is worth. Then think about what you spent last night doing. Copying an address out of a confirmation email. Hunting for a receipt. Writing a reply you'd already written twice this month.`
- p: `The worse version is the one where you don't do it at all, and it sits there until doing it stops being an option. The quote goes cold. The trial charges you. The buyer gives up and asks for a refund instead.`
- p: `That's the bill. It arrives as tiredness rather than an invoice, which is why nobody ever adds it up.`
- CTA button: `Give Me My Magic Inbox ←` (reverse arrow) — scrolls to hero form
- Microcopy: `Free. About twenty minutes. Your email stays private and you can leave whenever you want.`

**Receipt column (`.illust-receipt`):**
Receipt card with zigzag edges, label `Your Time — Last Night`, items:
- `Copying an address` — `14 min`
- `Hunting a receipt` — `22 min`
- `Rewriting a reply` — `18 min`
- `Chasing a follow-up` — `11 min`
- `Snoozing, again` — `9 min`
- Total row: `TOTAL` — `one evening`

### 3.5 SECTION 5 — "Five Moves Nobody On The Other End Can See"

Centered H2:
`Plus: ` + (gradient-text) `Five Moves Nobody On The Other End Can See`

Inline flex layout: email mockup LEFT (260px max-width), 3 paragraphs RIGHT:

Email mock contents (`.email-mock`):
- Subject: `Re: Project brief`
- Recipient: `to client@co.com`
- Body: `Here's the updated brief — let me know if anything needs adjusting before Thursday.`
- Mint dashed callout: `BCC → assistant@magic`

Inline copy (`.inline-copy`):
- p: `BCC your assistant instead of forwarding. Blind copy, so the person you wrote to never sees it was there, and it goes to work anyway.`
- p: `That Thursday reminder is the one to start with. The person waiting never learns you needed reminding. They just think you're somebody who always delivers.`
- p: `The other four come with the setup, on top of what you came here for.`

### 3.6 SECTION 6 — "If you're on Substack…"

Two-column (`.notes-grid`), copy on LEFT, task-panel on RIGHT.

**Copy column:**
- p strong `If you're on Substack,` ` your subscriber list lives inside Substack, and the only way to get it out is exporting the whole thing by hand. Your assistant reads the notification Substack sends you and adds each new subscriber, as they arrive, to a separate marketing list you own in Kit or Mailchimp. That's where your promotions go, instead of into your publication.`
- p strong `Some of it happens out in the real world.` ` I forwarded my assistant an email about a limited screening of a movie I wanted to see, and it came back with two tickets. Best seats in the house. All it cost me was forwarding the email.`

**Task panel (`.task-panel`):**
Header: pulsing mint dot + `MAGIC INBOX · LIVE`
Three rows (`.tp-row`), each: avatar tile (S/C/A in different colors), sender name + sub, arrow, mint result badge with checkmark:

| Avatar | Sender | Sub | Result |
|---|---|---|---|
| S | Substack | `New subscriber · sarah@gmail` | `Your list` |
| C | Cinema Centro | `Limited screening · Sat 9pm` | `2 tickets` |
| A | Adobe | `Receipt · $29.99 · Aug 12` | `Filed` |

### 3.7 SECTION 7 — "Wake Up To Work You Didn't Have To Do"

Centered, full-bleed mint radial glow background, scattered star sparkles.

- H2:
  `Wake Up To ` + (gradient-text) `Work You Didn't Have To Do`
- p.sub: `Twenty minutes tonight is the whole cost. Put your email in the box and the entire setup comes to you, free. The paste blocks, the filters, the playbook, and the moves nobody on the other end can see.`
- CTA button: `Give Me My Magic Inbox ←` — scrolls to hero form
- Microcopy with star sparkles: ✦ `Your email stays private and you can leave whenever you want.` ✦

### 3.8 SECTION 8 — Byline

Two-column flex (avatar + body), single-column on mobile.

**Avatar column (`.avatar-panel`):** 130px circular, mint gradient border, contains `imgs/avatar.webp`.

**Body column (`.byline-body`):**
- p: `I'm Nick Quick. I write and publish my own work, and I run marketing campaigns for people who'd rather not run theirs.`
- p: `I do it from Asunción, Paraguay, where the correct way to spend an afternoon is a shaded bench and a guampa of cold tereré.`
- p: `Two decades in, I can tell you the work was never the problem. It was everything stacked around the work.`
- p (last, mint italic Fraunces): `So I hired something to take that part.`

### 3.9 SECTION 9 — "Now Go Hire Yours"

Centered.

- H2:
  `Now Go ` + (gradient-text) `Hire Yours`
- p.sub: `Twenty minutes tonight, and an email address is the whole price.`
- CTA button: `Give Me My Magic Inbox ←` — scrolls to hero form
- Microcopy with star sparkles: ✦ `Your email stays private and you can leave whenever you want.` ✦

### 3.10 FOOTER

- Italic Fraunces, mint, 22px: `Made with 🧉 in Paraguay` (yerba emoji spins slowly via `yerba-spin` keyframe)
- Brand block:
  - `● CO-WRITE WITH AI` (JetBrains Mono uppercase, mint dot)
  - Tagline (ink-mute, 14px): `Field notes on handing the boring parts of your inbox to something that doesn't mind.`
- Nav (JetBrains Mono, 14px): `Privacy` `Terms` `Contact` (only three — no cowritingwithai.com link in the nav)
- Copyright (JetBrains Mono, 12px, ink-faint, centered, single line):
  `© [auto-year] Co-Write With AI · All rights reserved · Asunción, Paraguay`

The `[auto-year]` is filled by a tiny inline script reading `new Date().getFullYear()`.

---

## 4. Form Runtime Contract — DO NOT BREAK

This is the most important section. FlexiFunnels' opt-in form runtime depends on exact IDs, classes, and `data-*` attributes. Anything renamed or removed breaks the integration.

### 4.1 The visible form (REQUIRED)

Use FlexiFunnels' native opt-in form element to render this. Configure it so the generated DOM matches the structure below.

```html
<form id="flexiForm_64475"
      data-formid="flexiForm_64475"
      data-droptype="form"
      class="flexi-form flexi-vform-box ff-orderform-theme">

  <input type="email" name="email"
         placeholder="Email ID"
         required="true"
         class="ft-input-height ft-form-ctl ft-input-vstyle">

  <a data-formid="flexiForm_64475"
     data-smsg="Your details were submitted successfully"
     data-formmode="ft-flexi"
     data-ftbuttontype="1"
     href="#submit"
     class="ft-form-btn ft-btn-vstyle"
     data-nextgo="https://go.cowritingwithai.com/magic-inbox-thank-you"
     data-target="_self">
    <span class="ffbtnmaintxt"><span class="ffbtntxt">Submit</span></span>
    <span class="ffbtnsubtxt"> </span>
  </a>
</form>
```

### 4.2 The hidden Encharge helper form (REQUIRED — must remain in DOM)

This mirrors the visible email value into the Encharge integration. Both forms must remain on the page. The helper is visually hidden but semantically present.

```html
<form id="flexiForm_64475_encharge"
      data-formid="flexiForm_64475"
      data-droptype="form"
      class="flexi-form flexi-vform-box ff-orderform-theme ff-hidden-encharge"
      aria-hidden="true"
      tabindex="-1">

  <input type="email" name="email" tabindex="-1" aria-hidden="true">

  <a data-formid="flexiForm_64475"
     data-formmode="ft-flexi"
     data-ftbuttontype="1"
     href="#submit"
     class="ft-form-btn ft-btn-vstyle"
     tabindex="-1" aria-hidden="true"
     data-nextgo="https://go.cowritingwithai.com/magic-inbox-thank-you"
     data-target="_self">
    <span class="ffbtnmaintxt"><span class="ffbtntxt">Submit</span></span>
    <span class="ffbtnsubtxt"> </span>
  </a>
</form>
```

Hidden CSS (add to page CSS):
```css
.ff-hidden-encharge{
  position:absolute;width:1px;height:1px;padding:0;margin:-1px;
  overflow:hidden;clip:rect(0,0,0,0);white-space:nowrap;border:0;
}
```

### 4.3 Required attributes summary

| Attribute | Value | Purpose |
|---|---|---|
| `id` on visible form | `flexiForm_64475` | FlexiFunnels runtime hook |
| `id` on helper form | `flexiForm_64475_encharge` | Encharge integration hook |
| `data-formid` (both) | `flexiForm_64475` | form identity |
| `data-nextgo` (both) | `https://go.cowritingwithai.com/magic-inbox-thank-you` | submit redirect |
| `data-target` (both) | `_self` | opens in same window |
| `data-smsg` (visible only) | `Your details were submitted successfully` | success toast |
| `data-formmode` (both) | `ft-flexi` | tells runtime this is a FlexiFunnels form |
| `data-ftbuttontype` (both) | `1` | button type flag |
| `name` on email inputs | `email` | field contract |
| Submit button class | `ft-form-btn ft-btn-vstyle` | runtime expects these |
| Submit text wrapper | `<span class="ffbtnmaintxt"><span class="ffbtntxt">…</span></span>` | runtime label hook |

### 4.4 Custom JS behaviors (small, add at page bottom)

```js
// 1) Override the visible form's placeholder + button label.
//    Do NOT change form HTML — just text content.
document.addEventListener('DOMContentLoaded', function(){
  var vf = document.getElementById('flexiForm_64475');
  if (!vf) return;
  var email = vf.querySelector('input[type="email"]');
  if (email) email.placeholder = 'Your email address';
  var lbl = vf.querySelector('.ffbtntxt');
  if (lbl) lbl.textContent = 'Get Free Access';

  // 2) Sync visible email value into the hidden Encharge helper on submit.
  var hf = document.getElementById('flexiForm_64475_encharge');
  var btn = vf.querySelector('.ft-form-btn');
  if (btn && hf) {
    btn.addEventListener('click', function(){
      var v = vf.querySelector('input[type="email"]');
      var h = hf.querySelector('input[type="email"]');
      if (v && h) h.value = v.value;
    }, true);
  }

  // 3) Enter-key submits the visible form.
  if (email && btn) {
    email.addEventListener('keydown', function(ev){
      if (ev.key === 'Enter') { ev.preventDefault(); btn.click(); }
    });
    vf.addEventListener('submit', function(ev){ ev.preventDefault(); btn.click(); });
  }
});

// 4) "Give Me My Magic Inbox" buttons scroll back to the form.
document.addEventListener('click', function(ev){
  var t = ev.target.closest('[data-scroll-to-form]');
  if (!t) return;
  ev.preventDefault();
  var form = document.getElementById('optin-form') || document.getElementById('flexiForm_64475');
  if (!form) return;
  form.scrollIntoView({behavior:'smooth', block:'center'});
  setTimeout(function(){
    var firstField = form.querySelector('input, select, textarea, button');
    if (firstField) firstField.focus({preventScroll:true});
  }, 500);
});
```

---

## 5. Layout & Behavior Spec

| Behavior | Detail |
|---|---|
| Hero 2-column grid | 1.15fr copy / 0.85fr image at ≥960px; single column below |
| Section 2 columns | REVERSED: copy on RIGHT, illustration on LEFT |
| Section 2 sticky | Envelope illustration pins via `position:sticky; top:18vh` at ≥640px |
| Section 5 inline | Email mockup left, 3 paragraphs right, inline flex |
| Section 6 panel | Replaces ugly Substack→YourList graphic with task panel |
| Proof chips 2×2 | Mint-bordered cards with SVG checkmark + staggered shimmer sweep |
| Microcopy + stars | In sections 7 and 9, center the microcopy and flank with ✦ |
| Copyright line | Single line, centered, `white-space:nowrap` |
| Year auto-fill | `© <span id="year">2026</span>` filled by JS |

### Mobile breakpoints

| Width | Layout |
|---|---|
| ≥960px | Two-column hero (form + image) |
| 640–959px | Two-column Section 2 (envelope + copy), single-column hero, hidden hero image |
| <640px | Single-column everywhere; hero image hidden; chips 2×2 maintained |

Above-the-fold invariant: **at both 1440×900 and 390×844, the submit button must end with ≥170px of viewport space below it**.

---

## 6. Animation Notes (Optional, but match the live feel)

These are subtle, all respect `prefers-reduced-motion`.

- **`cta-glow`** — primary CTA mint box-shadow pulse, 2.4s loop
- **Shine sweep** — diagonal white sweep across CTA `::after`, 2.4s
- **`text-shimmer`** — gradient-text background-position slides 0%→100% over 6s
- **`float-img`** — hero product image bobs ±6px vertically, 6s
- **`proof-shimmer`** — diagonal white sweep across each proof chip `::after`, staggered 0.6s per chip
- **`star-pulse`** — `✦` microcopy stars scale 0.9→1.18 over 2.4s, second star delayed 1.2s
- **`yerba-spin`** — 🧉 emoji in footer rotates ±8° over 5s
- **`pulse`** — task-panel "Live" dot + envelope pulse rings

Drop them all if FlexiGenie doesn't allow custom CSS animations.

---

## 7. Acceptance Checklist

When FlexiGenie finishes, verify:

- [ ] All ten sections + footer render in the order in §3
- [ ] Every line of copy is verbatim (compare character-by-character against §3)
- [ ] Visible form has `id="flexiForm_64475"`
- [ ] Hidden form has `id="flexiForm_64475_encharge"` and is `aria-hidden="true"`
- [ ] Submit button has `data-nextgo="https://go.cowritingwithai.com/magic-inbox-thank-you"` AND `data-target="_self"`
- [ ] Submit button visible text reads "Get Free Access" (label is "Submit" in source, overridden to "Get Free Access" via JS)
- [ ] Email input placeholder reads "Your email address"
- [ ] "Give Me My Magic Inbox" buttons (sections 4, 7, 9) scroll back to the hero form
- [ ] Hero submit button has ≥170px below it at 1440×900 and 390×844
- [ ] No blue or purple appears anywhere in the palette
- [ ] Section 2 envelope illustration pins during scroll at desktop and tablet widths
- [ ] Footer nav has exactly three links: Privacy, Terms, Contact
- [ ] Copyright line is single-line and centered
