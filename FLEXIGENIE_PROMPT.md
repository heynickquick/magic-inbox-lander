# FlexiGenie Prompt — Paste This as ONE Message

This is a **single self-contained message** designed to be pasted as your first (and only) message to FlexiGenie. Every section — design tokens, copy, form contract, layout spec — is inlined below so nothing gets truncated.

**Before pasting:**
1. Paste the entire content below (everything between the ``` fences, including the prose) into FlexiGenie.
2. The image URLs below are already publicly hosted on the live deploy of this page — FlexiGenie can fetch them directly with no manual upload, no auth.
3. Open this URL in a separate tab so FlexiGenie can study the visual: `https://sa7m8wqkf3ehs.space.minimax.io`

---

````
You are rebuilding a single-page lead-magnet opt-in on the FlexiFunnels platform.

The visual design, copy, and layout are locked. Your job is to recreate it
section by section on FlexiFunnels so it matches the live reference at
https://sa7m8wqkf3ehs.space.minimax.io while keeping the existing form
runtime working exactly as it does today.

================================================================
CRITICAL — DO NOT BREAK THE FORM RUNTIME
================================================================
The page already has a working FlexiFunnels opt-in form that must be
reused, not replaced. Specifically:

  • The visible form has id="flexiForm_64475" and posts on submit to
    https://go.cowritingwithai.com/magic-inbox-thank-you
    with data-target="_self" and data-smsg="Your details were submitted
    successfully".
  • A HIDDEN helper form with id="flexiForm_64475_encharge" sits in
    the same container. It mirrors the visible email value into the
    Encharge integration. Both forms must remain on the page, both with
    name="email" inputs, both posting to the same thank-you URL with
    data-target="_self". The helper is hidden via class
    "ff-hidden-encharge" and aria-hidden="true".
  • Submit button class "ft-form-btn" with data-formid="flexiForm_64475",
    data-formmode="ft-flexi", data-ftbuttontype="1".
  • Do NOT change form IDs, data-* attributes, class names (flexi-form,
    flexi-vform-box, ff-orderform-theme, ft-input-block, ft-form-ctl,
    ft-input-vstyle, ft-input-height, ft-com-btnstyle, ft-btn-vstyle,
    ffbtnmaintxt, ffbtntxt, ffbtnsubtxt), or the thank-you URL.
  • Use FlexiFunnels' native opt-in form element to render the visible
    form so all the required classes/IDs/data-attrs are emitted
    automatically. Do NOT hand-roll the <form> tag in raw HTML.

================================================================
WHAT TO DO
================================================================
1. Add the four Google Fonts to <head>:
   Inter (400/500/600/700/800/900),
   Sora (600/700/800),
   JetBrains Mono (400/700),
   Fraunces italic (500/700).

2. Inject the design system below as page-level CSS.

3. Build the page in the section order below, with the copy verbatim —
   not a word different.

4. Place the existing FlexiFunnels opt-in form inside the hero section,
   right below the proof chips and the "Get Free Access Now" heading.
   Override its placeholder text to "Your email address" and its submit
   label to "Get Free Access" via small inline JS — do NOT change the
   form HTML.

5. Wire all "Give Me My Magic Inbox" buttons (sections 4, 7, 9) to
   smooth-scroll the page back to the hero form and focus the email
   field.

6. Match the visual design at 1440×900 desktop, 768×900 tablet, and
   390×844 mobile. The ENTIRE hero (eyebrow + headline + lead + 4
   chips + CTA + email + button + microcopy) must fit above the fold
   on both desktop and mobile.

================================================================
WHAT NOT TO DO
================================================================
  • Don't change the copy. Not a word.
  • Don't change form IDs, classes, data-* attrs, or the thank-you URL.
  • Don't drop the hidden Encharge helper form.
  • Don't use blue/purple in the palette. Charcoal + mint only.

================================================================
ASSET URLS (publicly hosted — FlexiGenie can fetch directly)
================================================================
  • Hero product image:
    https://sa7m8wqkf3ehs.space.minimax.io/imgs/hero-product.png
  • Avatar (section 8):
    https://sa7m8wqkf3ehs.space.minimax.io/imgs/avatar.webp

These URLs serve the exact same files that are checked into the source
repo. The repo itself is private, so raw.githubusercontent.com URLs
won't work without auth — but these public deploy URLs are open.

If FlexiFunnels requires images to be hosted on its own CDN, fetch
both URLs above and re-upload them to the FlexiFunnels media library,
then use the resulting FlexiFunnels-hosted URLs in the page.

The logo (imgs/logo.png in the repo) is preserved for other uses but
is NOT used on this page — do not add it.

================================================================
SOURCE FILES (FlexiGenie may consult for reference)
================================================================
  • Live visual reference (most important):
    https://sa7m8wqkf3ehs.space.minimax.io
  • index.html (full source):
    https://sa7m8wqkf3ehs.space.minimax.io/
      (FlexiGenie can scrape this — the rendered HTML is what matters)

You don't need to scrape the source repo directly — the inline spec
below is self-contained. The live URL is your visual source of truth.

================================================================
1. DESIGN SYSTEM
================================================================

Colors — use these CSS custom properties as the single source of truth:

  --bg:        #07070B  page background, true near-black charcoal
  --bg-1:      #0B0B12
  --bg-2:      #11111A
  --bg-warm:   #0D0D14
  --surface:   #1A1A26  card / input surface
  --surface-2: #232333
  --border:    #2A2A38
  --border-soft: #1F1F2C
  --mint:      #3DFFB0  primary mint neon
  --mint-bright: #7CFFC8
  --mint-deep: #1FA876
  --mint-glow: rgba(61,255,176,0.45)
  --mint-soft: rgba(61,255,176,0.08)
  --ink:       #FAFAF7  primary text
  --ink-soft:  #D5D5DA  body text, high contrast
  --ink-mute:  #9A9AA8  secondary text
  --ink-faint: #5A5A66  microcopy / footer

Palette rule: charcoal + mint only. No blue, no purple. No warm browns
or grays beyond the ink scale.

Typography:
  H1 (hero)       Sora 800   clamp(36px, 4.4vw, 60px)   lh 1.02 ls -0.03em
  H2 (section)    Sora 800   clamp(30px, 4.2vw, 56px)   lh 1.04 ls -0.025em
  Eyebrow/chip    JetBrains Mono 700  11–13px            ls 0.16–0.18em uppercase
  Body            Inter 400  18px mobile / 19px desktop  lh 1.75
  Lead            Inter 400  1.0625em (~20px)            lh 1.65
  Accent italic   Fraunces 500 italic                   for "Stole My Job" word

Font URL:
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link rel="stylesheet"
  href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800;900&family=Sora:wght@600;700;800&family=JetBrains+Mono:wght@400;700&family=Fraunces:ital,wght@1,500;1,700&display=swap">

Spacing:
  Section vertical padding  140px desktop, 88px mobile
  Container max-width       1280px (40px gutters desktop, 24px mobile)
  Form input height         48–54px
  Primary CTA padding       14px 22px

Primary CTA spec:
  display:inline-flex; align-items:center; justify-content:center; gap:10px;
  padding:14px 22px;
  font:700 15px 'Inter',sans-serif;
  color:#001510;
  background:var(--mint);
  border:none; border-radius:14px;
  box-shadow:
    0 0 0 1px rgba(61,255,176,0.4),
    0 10px 30px -8px var(--mint-glow),
    0 0 40px -10px var(--mint-glow),
    inset 0 1px 0 rgba(255,255,255,0.4);
  A 2.4s cta-glow keyframe pulses the box-shadow.
  A 2.4s shine-sweep ::after (skewX -18deg, translateX 380%) sweeps across.
  Reverse-pointing arrow icon <svg class="rev"> sits inside, on the right.

================================================================
2. SECTIONS — IN ORDER, VERBATIM COPY
================================================================

The page is NINE sections + footer. Build them in this exact order.

----- HERO ----- <header> full-bleed, min-height: 100vh
  Two-column grid on desktop (1.15fr copy / 0.85fr image), single
  column on mobile.

  LEFT column:
    eyebrow:        "Free. And It Works The Hours You Don't."
    h1:             "Open Your Laptop To Work That's [GRADIENT]Already Been Done For You[/GRADIENT]"
    lead:           "The Magic Inbox is an assistant with an email address of its own. You forward it the jobs buried in your inbox and it works through them while you're doing something else. Here's the whole setup, free, in about twenty minutes."
    proof chips     (2×2 grid, each with mint checkmark + label, staggered shimmer sweep):
        "Replies Drafted."
        "Receipts Filed."
        "Follow-Ups Chased."
        "Before You Sat Down."
    optin heading:  strong "Get Free Access Now"
                    span   "The full Magic Inbox setup, sent to your inbox."
    [FLEXIFUNNELS OPT-IN FORM GOES HERE — see §3 form contract]
    microcopy:      "Your email stays private and you can leave whenever you want."

  RIGHT column:
    https://sa7m8wqkf3ehs.space.minimax.io/imgs/hero-product.png
    alt "Magic Inbox — The Complete Guide, your AI email assistant",
    max-width 440px, hidden below 960px viewport. Mint radial glow behind it.

----- SECTION 2 ----- "Stole My Job" — two-column, REVERSED
  Copy on RIGHT, envelope illustration on LEFT.
  Pull-quote spans full-width BELOW the columns (not above).

  COPY column (right):
    h2:  "I Gave My Assistant An [GRADIENT]Email Address[/GRADIENT] And It [SERA_ACCENT]Stole My Job[/SERA_ACCENT]"
    p:   "I hated that job. The pay was shit, on account of it being me doing it for free at eleven at night. And I wasn't any good at it."
    p:   "Here's what the job actually was."
    p:   strong "Every inbox is a to-do list you didn't write." " Most of what's sitting in yours is a task wearing a sender's name. Book the thing. Pay the invoice. Answer the question. Find the file. Chase the person who went quiet on you."
    p:   "So you sort the list instead of working it. Emails that need nothing from you get archived. Emails that need something get snoozed, because not right now. A few get done, whichever ones you could stand that day."
    p:   "Tomorrow the snoozed emails are back, in exactly the state you left them. And they brought friends."
    p:   strong "So I stopped doing it." " My AI assistant has its own email address now. I forward it the emails I'd have snoozed, and they start getting done automatically."

  ILLUSTRATION column (left, STICKY):
    Stack of 5 envelope cards with mint-glow radial background,
    3 pulsing concentric rings around it. The illustration wrapper
    uses position:sticky; top:18vh; align-self:start at viewports
    ≥640px so it pins during scroll.

  PULL-QUOTE (below, full-width):
    italic Fraunces with mint diamond bullets: "Sorting A To-Do List Finishes None Of It. It Only Decides The Order You Get To Feel Bad In."

----- SECTION 3 ----- "Tasks You Keep Putting Off"
  Centered h2: "The Tasks You Keep Putting Off. [GRADIENT]None Of Them Are Yours Anymore.[/GRADIENT]"

  Tasks panel (glass-morphism backdrop-filter blur, 5 list items with mint checkmark marker):
    "The quote you sent three weeks ago gets chased, so it stops being money you never collected"
    "The buyer who can't find their login gets working access and a written reply, before they email you a second time"
    "Every "I'll have that to you by Friday" you send comes back as a reminder on Thursday"
    "Your client's new requirement goes into that client's brief, instead of staying buried four replies deep"
    "The receipt gets filed with its vendor, amount and date, so tax season stops being an archaeology dig"

  After panel:
    p strong "And that's just five tasks off your list. The Magic Inbox takes dozens more, and the best ones are the ones you invent yourself."
    p strong "Adding one of your own takes a sentence." " Tell it how to handle that kind of email once, and it handles it from then on."

----- SECTION 4 ----- "Most Expensive Assistant" — two-column, copy LEFT
  COPY column (left):
    h2:  "You Are The [GRADIENT]Most Expensive Assistant[/GRADIENT] You Will Ever Employ"
    p:   "Work out roughly what an hour of your time is worth. Then think about what you spent last night doing. Copying an address out of a confirmation email. Hunting for a receipt. Writing a reply you'd already written twice this month."
    p:   "The worse version is the one where you don't do it at all, and it sits there until doing it stops being an option. The quote goes cold. The trial charges you. The buyer gives up and asks for a refund instead."
    p:   "That's the bill. It arrives as tiredness rather than an invoice, which is why nobody ever adds it up."
    CTA button: "Give Me My Magic Inbox ←" — scrolls to hero form
    microcopy: "Free. About twenty minutes. Your email stays private and you can leave whenever you want."

  RECEIPT column (right):
    Receipt card with zigzag top/bottom edges.
    label: "Your Time — Last Night"
    items (label — value):
        "Copying an address" — "14 min"
        "Hunting a receipt" — "22 min"
        "Rewriting a reply" — "18 min"
        "Chasing a follow-up" — "11 min"
        "Snoozing, again" — "9 min"
    Total row: "TOTAL" — "one evening"

----- SECTION 5 ----- "Five Moves Nobody On The Other End Can See"
  Centered h2: "Plus: [GRADIENT]Five Moves Nobody On The Other End Can See[/GRADIENT]"

  Inline flex: email mockup LEFT (260px max-width), 3 paragraphs RIGHT.

  EMAIL MOCK contents:
    macOS-style traffic light dots (red/yellow/green)
    From: strong "Re: Project brief"   sub "to client@co.com"
    Body: "Here's the updated brief — let me know if anything needs adjusting before Thursday."
    Mint dashed callout pill: "BCC → assistant@magic"

  INLINE COPY (right):
    p: "BCC your assistant instead of forwarding. Blind copy, so the person you wrote to never sees it was there, and it goes to work anyway."
    p: "That Thursday reminder is the one to start with. The person waiting never learns you needed reminding. They just think you're somebody who always delivers."
    p: "The other four come with the setup, on top of what you came here for."

----- SECTION 6 ----- "If you're on Substack…" — two-column, copy LEFT, panel RIGHT

  COPY column (left):
    p strong "If you're on Substack," " your subscriber list lives inside Substack, and the only way to get it out is exporting the whole thing by hand. Your assistant reads the notification Substack sends you and adds each new subscriber, as they arrive, to a separate marketing list you own in Kit or Mailchimp. That's where your promotions go, instead of into your publication."
    p strong "Some of it happens out in the real world." " I forwarded my assistant an email about a limited screening of a movie I wanted to see, and it came back with two tickets. Best seats in the house. All it cost me was forwarding the email."

  TASK PANEL (right):
    Header: pulsing mint dot + "MAGIC INBOX · LIVE"
    Three rows, each: avatar tile (S/C/A in distinct colors) + sender name + sub + arrow + mint result badge with checkmark.

    Row 1: avatar "S",   who "Substack",       sub "New subscriber · sarah@gmail",      result "Your list"
    Row 2: avatar "C",   who "Cinema Centro",  sub "Limited screening · Sat 9pm",       result "2 tickets"
    Row 3: avatar "A",   who "Adobe",          sub "Receipt · $29.99 · Aug 12",         result "Filed"

----- SECTION 7 ----- "Wake Up To Work You Didn't Have To Do" — centered, full-bleed
  Mint radial glow background + scattered star sparkles.

  h2:  "Wake Up To [GRADIENT]Work You Didn't Have To Do[/GRADIENT]"
  p.sub: "Twenty minutes tonight is the whole cost. Put your email in the box and the entire setup comes to you, free. The paste blocks, the filters, the playbook, and the moves nobody on the other end can see."
  CTA button: "Give Me My Magic Inbox ←" — scrolls to hero form
  microcopy centered with star sparkles:
    ✦ "Your email stays private and you can leave whenever you want." ✦

----- SECTION 8 ----- Byline — two-column flex, single-column on mobile
  Avatar (LEFT): 130px circular frame, mint gradient border, contains:
    https://sa7m8wqkf3ehs.space.minimax.io/imgs/avatar.webp
  Body (RIGHT):
    p: "I'm Nick Quick. I write and publish my own work, and I run marketing campaigns for people who'd rather not run theirs."
    p: "I do it from Asunción, Paraguay, where the correct way to spend an afternoon is a shaded bench and a guampa of cold tereré."
    p: "Two decades in, I can tell you the work was never the problem. It was everything stacked around the work."
    p (mint italic Fraunces): "So I hired something to take that part."

----- SECTION 9 ----- "Now Go Hire Yours" — centered
  h2:  "Now Go [GRADIENT]Hire Yours[/GRADIENT]"
  p.sub: "Twenty minutes tonight, and an email address is the whole price."
  CTA button: "Give Me My Magic Inbox ←" — scrolls to hero form
  microcopy centered with star sparkles:
    ✦ "Your email stays private and you can leave whenever you want." ✦

----- FOOTER -----
  Italic Fraunces mint 22px: "Made with 🧉 in Paraguay" (emoji spins slowly)
  Brand block:
    ● CO-WRITE WITH AI (JetBrains Mono uppercase, mint dot)
    Tagline (ink-mute 14px): "Field notes on handing the boring parts of your inbox to something that doesn't mind."
  Nav (JetBrains Mono 14px): "Privacy" "Terms" "Contact"  ← exactly three links
  Copyright (JetBrains Mono 12px ink-faint, centered, single line, white-space:nowrap):
    "© [auto-year] Co-Write With AI · All rights reserved · Asunción, Paraguay"
  The year is filled by tiny inline JS: new Date().getFullYear()

================================================================
3. FORM RUNTIME CONTRACT — DO NOT BREAK
================================================================

Use FlexiFunnels' native opt-in form element. Configure it so the
generated DOM matches this structure:

VISIBLE FORM:
<form id="flexiForm_64475"
      data-formid="flexiForm_64475"
      data-droptype="form"
      class="flexi-form flexi-vform-box ff-orderform-theme">
  <input type="email" name="email" placeholder="Email ID"
         required="true" class="ft-input-height ft-form-ctl ft-input-vstyle">
  <a data-formid="flexiForm_64475"
     data-smsg="Your details were submitted successfully"
     data-formmode="ft-flexi" data-ftbuttontype="1" href="#submit"
     class="ft-form-btn ft-btn-vstyle"
     data-nextgo="https://go.cowritingwithai.com/magic-inbox-thank-you"
     data-target="_self">
    <span class="ffbtnmaintxt"><span class="ffbtntxt">Submit</span></span>
    <span class="ffbtnsubtxt"> </span>
  </a>
</form>

HIDDEN ENCHARGE HELPER FORM (must stay in DOM):
<form id="flexiForm_64475_encharge"
      data-formid="flexiForm_64475" data-droptype="form"
      class="flexi-form flexi-vform-box ff-orderform-theme ff-hidden-encharge"
      aria-hidden="true" tabindex="-1">
  <input type="email" name="email" tabindex="-1" aria-hidden="true">
  <a data-formid="flexiForm_64475" data-formmode="ft-flexi"
     data-ftbuttontype="1" href="#submit" class="ft-form-btn ft-btn-vstyle"
     tabindex="-1" aria-hidden="true"
     data-nextgo="https://go.cowritingwithai.com/magic-inbox-thank-you"
     data-target="_self">
    <span class="ffbtnmaintxt"><span class="ffbtntxt">Submit</span></span>
    <span class="ffbtnsubtxt"> </span>
  </a>
</form>

Hidden CSS:
.ff-hidden-encharge{
  position:absolute;width:1px;height:1px;padding:0;margin:-1px;
  overflow:hidden;clip:rect(0,0,0,0);white-space:nowrap;border:0;
}

REQUIRED ATTRIBUTES (summary):
  id visible:                  flexiForm_64475
  id helper:                   flexiForm_64475_encharge
  data-formid (both):          flexiForm_64475
  data-nextgo (both):          https://go.cowritingwithai.com/magic-inbox-thank-you
  data-target (both):          _self
  data-smsg (visible only):    Your details were submitted successfully
  data-formmode (both):        ft-flexi
  data-ftbuttontype (both):    1
  name on email inputs:        email
  submit classes:              ft-form-btn ft-btn-vstyle
  label wrapper:               <span class="ffbtnmaintxt"><span class="ffbtntxt">…</span></span>

================================================================
4. CUSTOM JS BEHAVIORS — small, page-level
================================================================

Add this at page bottom (after FlexiFunnels' own scripts):

// 1) Override visible form placeholder + button label. DO NOT change form HTML.
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
    vf.addEventListener('submit', function(ev){
      ev.preventDefault(); btn.click();
    });
  }
});

// 4) "Give Me My Magic Inbox" buttons scroll back to the form.
document.addEventListener('click', function(ev){
  var t = ev.target.closest('[data-scroll-to-form]');
  if (!t) return;
  ev.preventDefault();
  var form = document.getElementById('optin-form')
          || document.getElementById('flexiForm_64475');
  if (!form) return;
  form.scrollIntoView({behavior:'smooth', block:'center'});
  setTimeout(function(){
    var firstField = form.querySelector('input, select, textarea, button');
    if (firstField) firstField.focus({preventScroll:true});
  }, 500);
});

================================================================
5. LAYOUT & BEHAVIOR
================================================================

  Hero:                       2-col (1.15fr copy / 0.85fr image) ≥960px
                              Single column below
  Section 2:                  REVERSED 2-col, copy RIGHT, illustration LEFT
                              Envelope illustration STICKY at top:18vh ≥640px
  Section 5:                  Email mockup left, 3 paragraphs right (inline flex)
  Section 6:                  Task panel replaces any Substack→YourList graphic

  Mobile breakpoints:
    ≥960px:  2-col hero
    640–959: 2-col section 2, single-col hero, hero image hidden
    <640px:  Single-col everywhere, hero image hidden

  Above-the-fold invariant: at both 1440×900 and 390×844, the submit
  button must end with ≥170px of viewport space below it.

================================================================
6. ANIMATIONS (optional, all respect prefers-reduced-motion)
================================================================

  cta-glow         mint box-shadow pulse, 2.4s loop
  shine sweep      diagonal white across CTA ::after, 2.4s
  text-shimmer     gradient-text bg-position 0%→100%, 6s
  float-img        hero product ±6px vertical, 6s
  proof-shimmer    diagonal across each chip ::after, staggered 0.6s
  star-pulse       ✦ scales 0.9→1.18, 2.4s, second star delayed 1.2s
  yerba-spin       🧉 ±8° rotation, 5s
  pulse rings      envelope + task-panel "Live" dot

Drop any of these if FlexiGenie doesn't allow custom animations.

================================================================
7. ACCEPTANCE CHECKLIST
================================================================

When done, verify each item:

[ ] All 9 sections + footer render in the order above
[ ] Every line of copy is verbatim (compare character-by-character)
[ ] Visible form has id="flexiForm_64475"
[ ] Hidden form has id="flexiForm_64475_encharge" and aria-hidden="true"
[ ] Submit button has data-nextgo="https://go.cowritingwithai.com/magic-inbox-thank-you" AND data-target="_self"
[ ] Submit button visible text reads "Get Free Access"
[ ] Email input placeholder reads "Your email address"
[ ] "Give Me My Magic Inbox" buttons (sections 4, 7, 9) scroll back to hero form
[ ] Hero submit button has ≥170px below it at 1440×900 and 390×844
[ ] No blue or purple in the palette
[ ] Section 2 envelope illustration pins during scroll at desktop and tablet
[ ] Footer nav has exactly three links: Privacy, Terms, Contact
[ ] Copyright line is single-line and centered
[ ] Visible form posts to https://go.cowritingwithai.com/magic-inbox-thank-you on submit

When you finish, paste your output and I'll verify against the live URL.
````

---

## Why this file exists

The original `FLEXIGENIE_HANDOFF.md` was split into §1–§7 as separate sections of a long document. When you paste only §1 into FlexiGenie's chat, the other sections don't get included in the same message context — that's exactly what FlexiGenie flagged.

**This file is the entire brief as one single message.** Paste everything between the outer ``` fences above (or just everything from "You are rebuilding..." through "When you finish, paste your output...") as your first message to FlexiGenie and the truncation problem goes away.

## Why GitHub raw URLs work

FlexiGenie has browser tools and can fetch any public URL. `raw.githubusercontent.com` serves the actual file bytes — same as downloading from the repo. FlexiGenie will either reference these URLs directly in the page (works fine for visual matching during build) or download them and re-upload to FlexiFunnels' own CDN before publishing. Either way, you don't need to manually download, upload, or paste the images.
