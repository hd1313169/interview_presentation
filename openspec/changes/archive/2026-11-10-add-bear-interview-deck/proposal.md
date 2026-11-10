# Proposal

## Why

A second employer (codename "bear") interviews on 2026-11-11 and wants to see product cases plus marketing work. The Athena deck is tuned for a different company, so a separate deck is needed, and the GitHub Pages root must open it instead.

## What Changes

- New deck `bear/RyanChiang_presentation.html`: 23 main slides (opening p01–03, case one p04–09, Echorise p10–15, marketing p16–22, closing p23) plus appendix A1–A3, built from the employer's layout and copy doc (kept local) and reusing the Athena deck's visual system and presenter tooling.
- Missing assets are shown as labelled placeholders so the structure is complete now; pages may be added or removed after review.
- Published deck carries no speaker notes. A full local copy with notes is kept out of git.
- Typos in the copy doc are fixed in the slides: 销售頁 → 銷售頁, 陸生人 → 陌生人, 瑑珈 → 瑜珈.
- Root `index.html` redirects to the bear deck instead of the Athena deck.
- `.gitignore` excludes the employer-named source folder, `bear/*.md`, and the local notes copy so the employer name never reaches GitHub.
- `athena/` and `cocomart/` are not modified.

## Capabilities

### New Capabilities
- `bear-interview-deck`: the bear-edition deck's slide structure, copy fidelity, placeholders, no-notes publishing, and no-employer-name rule.

### Modified Capabilities
- `deck-homepage`: root now redirects to the bear deck; both prior decks must stay untouched.

## Impact

- New: `bear/RyanChiang_presentation.html` (published), local notes copy (ignored).
- Modified: `index.html`, `.gitignore`.
- Unchanged: `athena/`, `cocomart/`, `openspec/specs/interview-deck` (still describes the Athena deck).
