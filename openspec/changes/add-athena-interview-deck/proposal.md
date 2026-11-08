# Proposal

## Why

Ryan needs a second interview deck for a different employer, built from the existing CocoMart deck but with a different story: two cases (a shipped product, then an AI prototype workflow) instead of three. The page-by-page layout and copy are already written in a copy doc under `athena/` (gitignored: it names the employer and holds coaching notes). The new deck must also become the GitHub Pages homepage, and the root `index.html` is currently broken because the CocoMart files were moved into `cocomart/`.

## What Changes

- Add a new single-file HTML deck under `athena/`: 19 main slides (about 11 min plus 1 min buffer) and 5 appendix slides (A1–A5), following the layout and copy doc.
- Reuse the existing deck's visual system, components, and presenter features (keyboard paging, fullscreen, presenter window with notes and timer, overview, asset slots, appendix marking). The look does not change.
- Rewrite content and page order: new slides 06 (User flows), 10 (trade-offs and boundaries), 15 (how it is verified, with component-inventory annotation), 16 (design decisions it influenced); cases 1 and 2 re-cut; former case 3 becomes appendix A1–A4; add A5 (Echorise).
- Remove all company names and company-specific lines. The closing slide drops the company sentence, and the `C`-key company switcher is removed. One version only, with no per-company variants.
- Keep speaker notes in the HTML (`<aside class="notes">`), with coaching-only remarks rewritten as neutral talking points.
- Point the root `index.html` at the new deck so it is the Pages homepage. `cocomart/` is not modified.
- Source assets from `素材/` (including `5-b.mp4` for slide 17) and fill gaps from ryan-chiang.com. Where an asset is missing, use a labelled placeholder slot, never an invented screen.

Out of scope: PDF export (done after the deck is final), editing anything under `cocomart/`, a second deck variant, and inventing any facts not in the copy doc.

## Capabilities

### New Capabilities
- `interview-deck`: the content, structure, presenter behavior, and confidentiality rules of the Athena-edition deck (slide list, copy fidelity, animation limits, assets, appendix, no company names).
- `deck-homepage`: how the Pages root resolves to the new deck.

### Modified Capabilities

(none; no specs exist yet in `openspec/specs/`)

## Impact

- New: `athena/<deck>.html`, plus asset files copied or referenced from `素材/`.
- Changed: root `index.html` (redirect target).
- Untouched: `cocomart/*`, `素材/*`, `DESIGN.md`, `PRODUCT.md`.
- Publishing: the repo is public and the deck keeps its notes, so notes are visible via view-source. This was accepted by the user for now.
