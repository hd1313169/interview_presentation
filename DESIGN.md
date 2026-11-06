---
name: Ryan Chiang Interview Deck
description: Portfolio interview deck in the quiet, paper-editorial visual world of ryan-chiang.com
colors:
  ink: "#141414"
  ink-secondary: "#5c5c5c"
  ink-tertiary: "#6b6b6b"
  line: "#dcdad5"
  block-bg: "#f0efec"
  thumb-bg: "#efefef"
  bg: "#ffffff"
  marker: "#feffbf"
  on-ink: "#ffffff"
  on-ink-secondary: "#d6d6d6"
  on-ink-tertiary: "#b4b4b4"
  before-bg: "#fff7ed"
  before-icon: "#f97316"
  after-bg: "#f0fdf4"
  after-icon: "#22c55e"
typography:
  display:
    fontFamily: "Archivo, \"Deck TC\", \"Noto Sans TC\", \"PingFang TC\", \"Microsoft JhengHei\", system-ui, sans-serif"
    fontSize: "92px"
    fontWeight: 700
    lineHeight: 1.28
    letterSpacing: "-0.01em"
  headline:
    fontFamily: "Archivo, \"Deck TC\", \"Noto Sans TC\", sans-serif"
    fontSize: "58px"
    fontWeight: 700
    lineHeight: 1.28
    letterSpacing: "-0.01em"
  body:
    fontFamily: "Archivo, \"Deck TC\", \"Noto Sans TC\", sans-serif"
    fontSize: "27px"
    fontWeight: 400
    lineHeight: 1.65
  label:
    fontFamily: "Archivo, \"Deck TC\", \"Noto Sans TC\", sans-serif"
    fontSize: "20px"
    fontWeight: 500
    lineHeight: 1.3
rounded:
  sm: "6px"
  md: "14px"
  pill: "999px"
spacing:
  sm: "14px"
  md: "24px"
  lg: "44px"
  xl: "84px"
components:
  card:
    backgroundColor: "{colors.block-bg}"
    rounded: "{rounded.md}"
    padding: "36px"
  card-emphasis:
    backgroundColor: "{colors.bg}"
    rounded: "{rounded.md}"
  card-dark:
    backgroundColor: "{colors.ink}"
    textColor: "{colors.on-ink}"
    rounded: "{rounded.md}"
  chip:
    backgroundColor: "{colors.block-bg}"
    textColor: "{colors.ink}"
    rounded: "{rounded.pill}"
    padding: "10px 22px"
---

# Design System: Ryan Chiang Interview Deck

## Overview

**Creative North Star: "The Website at Slide Scale"**

The deck is Ryan Chiang's portfolio website (ryan-chiang.com) re-expressed as a 1920×1080 presentation: a white page, near-black ink, a single warm neutral block color, and one yellow marker reserved for the one idea each slide owns. It replaced an earlier navy-and-corporate-blue identity, which is now anti-reference, not a style to blend with. Density stays Read-mode calm — generous margins, one hierarchy step per element, no competing accents — so the deck reads correctly both presented live and skimmed cold by a recipient who received the file ahead of the meeting.

The system refuses hardware-mockup imagery (iMac/laptop renders with gradients and shadows) for work samples; screenshots crop to flat screen content only, matching the site's own flat image-card treatment. It also refuses a kicker-style label stacked directly above a headline; every slide instead carries a muted corner locator, decoupled from the heading's own flow.

**Key Characteristics:**
- Near-black ink on white, one warm block-gray surface color, one yellow marker — no blue, no navy, no gradient.
- Archivo (Latin) + Noto Sans TC (CJK), bold grotesk headlines, restrained body weight.
- 14px radius, 1px hairline borders, zero drop shadows.
- One signature interaction: the marker sweeping under a key phrase.

## Colors

A black-on-white page with exactly one warm neutral surface tone and one accent, used sparingly.

### Primary
- **Ink Black** (`#141414`): headline, body, and dark-slide background color. Carries essentially all text weight in the deck.

### Secondary
- **Marker Yellow** (`#feffbf`): the sole accent. Used only as a background-size-animated highlight behind a key phrase (`<mark>`) — never as a fill, border, or icon color. At most one or two marks per slide.

### Neutral
- **Ink Secondary** (`#5c5c5c`) / **Ink Tertiary** (`#6b6b6b`): body copy and muted captions on light slides.
- **Line** (`#dcdad5`): hairlines under headings, card dividers, image borders.
- **Block Background** (`#f0efec`): the warm off-white used for cards, stat panels, and image placeholder slots — the site's own `--color-block-bg`.
- **On-Ink** (`#ffffff` / `#d6d6d6` / `#b4b4b4`): text roles on the dark (ink-background) slides — cover, case openers, closing, dark showcase slide.

### Before/After (scoped exception)
- **Before Orange** (bg `#fff7ed`, icon `#f97316`): the "surface-level" half of a before/after pair — what the documentation or first read showed.
- **After Green** (bg `#f0fdf4`, icon `#22c55e`): the "ground-truth" half — what the interview or operation actually confirmed.

### Named Rules
**The One Marker Rule.** Yellow never appears as a UI fill, chip, button, or icon — only as the `<mark>` sweep behind the single phrase a slide wants remembered. A second accent color is never introduced, **except** the orange/green before→after pair, scoped to the case-study comparison component only (the portfolio's own device for this exact pattern) and never used elsewhere in the deck.

## Typography

**Display/Body Font:** Archivo (Latin), paired with Noto Sans TC (CJK), falling back to PingFang TC / Microsoft JhengHei / system-ui.

**Character:** A bold, slightly condensed grotesk for headlines against a lighter-weight, long-line-height body — the same pairing the source website uses for its own hero and body copy.

### Hierarchy
- **Display** (700, 92px, 1.28): cover slide name/claim only.
- **Headline** (700, 58px, 1.28): every slide's `h2` title.
- **Title** (700, 34–44px): sub-headings inside cards and agenda rows (`h3`).
- **Body** (400, 27px, 1.65): paragraph copy, card descriptions.
- **Label** (500, 20px, 1.3): the corner locator and small captions; never styled as a kicker directly above a headline.

## Layout

Fixed 1920×1080 slide canvas scaled uniformly to the viewport (no reflow; it is a deck, not a responsive page). Content padding is 84px top, 128px sides, 128px bottom. Every content slide opens with a corner locator (square-mark icon + label) pinned top-left, independent of a hairline-topped heading block below it — the two are structurally decoupled so the label never collides with the entrance animation on the headline. Case-opener slides split 1:0.9 into a text column and a flat image panel on a block-gray ground.

## Elevation & Depth

Flat throughout — no box-shadows anywhere in the deck. Depth and grouping come from the block-gray fill (`#f0efec`) against the white page, plus 1px hairline borders. This directly inherits the source website's `.block` treatment.

### Named Rules
**The Flat-By-Default Rule.** No shadow, no gradient, no 3D device mockup. A screenshot ships as a flat, radius-cropped image with a 1px border — never inside a rendered laptop or monitor frame.

## Shapes

14px corner radius on cards, image slots, and chips (matching the site's `.thumb`/`.block` radius). Hairline 1px borders/dividers in `--line`. Pills (`border-radius: 999px`) are reserved for small status chips (tool names, org chart nodes) — never for primary actions, since the deck has none.

## Components

### Cards
- **Corner Style:** 14px radius.
- **Background:** block-gray (`#f0efec`) by default; white with a 1px ink outline for an emphasized card; solid ink with white text for the "highlighted step" card.
- **Shadow Strategy:** none (see Elevation & Depth).
- **Internal Padding:** 36–44px.

### Chips
- **Style:** block-gray fill, ink text, pill radius; a muted/struck-through variant for a superseded option; solid-ink fill for the "selected" state in diagrams (e.g., the org-hierarchy slide).

### Image / Screenshot Slots
- **Style:** 14px radius, 1px line border, block-gray fill. Populated images are flat crops only — never a device mockup. Unfilled slots render a dashed placeholder with a filename hint, never invented content.

### Corner Locator (signature component)
Square-mark icon (two nested squares, ink or white depending on slide) + a muted 20px label, pinned to the slide's top-left corner, independent of the heading below. This replaced a conventional "eyebrow" kicker, which the deck's quality floor prohibits as a device.

## Do's and Don'ts

### Do:
- **Do** keep yellow to the single `<mark>` sweep; everything else stays ink/white/block-gray.
- **Do** crop any product screenshot to flat screen content with a 1px border and 14px radius.
- **Do** keep the corner locator visually separate from the heading it precedes.
- **Do** leave an asset slot as a dashed placeholder, labeled with its expected filename, when the real screenshot/video isn't supplied yet.

### Don't:
- **Don't** reintroduce navy, blue, or any second accent hue — that is the discarded identity this deck replaced.
- **Don't** render a work sample inside a 3D device mockup (laptop/monitor bezel, gradient, drop shadow).
- **Don't** stack a label directly above a headline as a kicker; use the detached corner-locator pattern instead.
- **Don't** add a box-shadow anywhere in the deck.
