# Design

## Context

- Existing deck: `cocomart/RyanChiang_presentation_cocomart.html`, one 12 MB file with 23 `<section class="slide">`, each with an `<aside class="notes">`. Images and the video are base64-embedded in `data-src` of `.slot` elements; the script falls back to a labelled placeholder when a slot has no source. Reveal steps use `.frag`; appendix slides use `data-appendix`; closing line comes from a `CO` array switched with `C`.
- Visual tokens and components are documented in `DESIGN.md`; product constraints (single HTML, 1920×1080 scaled canvas, no client names, no invented screens, facts only from Ryan) are in `PRODUCT.md`.
- Source of truth for layout and copy: a gitignored copy doc under `athena/` (named after the employer). It still contains a company-specific closing sentence and a company name in one note; the user decided those are dropped.
- Assets: `素材/` holds the case-one GIFs/PNGs/JPGs and `5-b.mp4`. ryan-chiang.com has more (`/images/case-02/2-a.jpg` user flow, `2-d-1/2.jpg` heatmap, `case-01/1-c.jpg` and `1-r-*.png` for Echorise, `case-04/4-b.jpg` permission diagram). Case-two CRM visuals (`/work/05`) have not been inspected.
- Git state: `cocomart/` and `athena/` are untracked; the root CocoMart HTML is a sanitized published copy marked skip-worktree. The local `cocomart/` HTML contains notes and other companies' closing lines.

## Goals / Non-Goals

**Goals:**
- A new single-file deck in `athena/` that reuses the existing CSS, JS, and components so the look and presenter tooling are identical.
- Every slide matches the copy doc, with company references removed.
- Root `index.html` opens the new deck.

**Non-Goals:**
- No visual redesign, no new framework, no build pipeline.
- No PDF (later), no per-company variants, no changes to `cocomart/`.
- No new facts, numbers, or screenshots beyond what the user or their site supplies.

## Decisions

1. **Copy, then edit, the existing HTML rather than regenerate from scratch.** The CSS/JS and component markup are proven; slide sections are replaced one by one. Alternative: a templating script. Rejected: one-off work, adds tooling the project does not have.
2. **File name `athena/RyanChiang_presentation.html`.** A neutral name keeps the employer out of the URL and the file. Alternative: keep the doc's company-based name. Rejected by the no-company-names rule.
3. **Keep assets base64-embedded, like the current deck.** `PRODUCT.md` says the file may be mailed without sibling folders. Cost: a large file, so downscale/optimize images before embedding and reference `5-b.mp4` as the only large item (1.8 MB). Alternative: relative links to `素材/`. Rejected for portability, but acceptable as a fallback if the file becomes unwieldy.
4. **Remove the `CO` switcher entirely**, instead of keeping an empty generic entry. The closing slide has no company sentence, so there is nothing to switch; the `C` key hint and the help text are removed too.
5. **Speaker notes stay in the HTML, rewritten neutrally.** The user chose to keep them for now. Coaching-only lines (JD references, "not to mention" reminders, interview Q&A) are rewritten as talking points or left in the markdown doc only. The Q&A section is not embedded.
6. **Slide 15 annotation reuses the slide-13 anonymized screenshot** with three colored outlines and a legend. After review, the legend names no colors and carries no "示意" label; the boxes themselves show it is an illustration.
7. **Missing visuals use slots with hints**, exactly as the current deck does: slide 13/17 CRM screens and any asset not found stay as placeholders.
8. **Redirect via the same pattern as today** (meta refresh + `location.replace` preserving query/hash), retargeted to the new path.

8b. **Built with a throwaway script kept outside the repo** (extract base64 assets, rewrite slide markup, reassemble). Map, report, and modal images were re-encoded to WebP (alpha preserved), which brought the file from about 13 MB to 8.8 MB. Case-two and appendix covers use the portfolio's cover images unmodified, so the case-two cover keeps the tool tags baked into that picture.
9. **Slide 15 swaps the annotation for the wide card.** At 1920x1080 the three cards, the annotated screenshot, and the wide card do not fit together, so the annotation appears with card 1 and the wide card takes its place on the last step (4 steps total).
10. **`.gitignore` guards**: `cocomart/*.html` and `athena/*.md` are ignored so the full local deck and the copy doc (which names the original employer and holds coaching notes) cannot be staged by `git add -A`.

## Risks / Trade-offs

- [Public repo exposes notes by view-source] → accepted by the user for now; notes are neutral and name no company. Revisit if sensitive content is added.
- [`git add -A` could publish the local `cocomart/` HTML with notes and other companies' lines] → before any commit, check `git status`, and consider adding `cocomart/*.html` to `.gitignore`; do not stage it.
- [Slide 07 needs high-res phone screenshots; only GIFs/PNGs available] → check resolution against site assets; otherwise use best available and keep the pending checklist item.
- [Slide 15 examples may not match Ryan's real inventory] → mark illustrative until confirmed.
- [Embedding many images bloats the file] → compress images; target well under the current 12 MB.
- [Timing] 19 slides sum to about 11 minutes with a 12-minute timer; slide 09 can be skipped for time.

## Migration Plan

1. Build the new deck in `athena/` and verify locally.
2. Retarget the root `index.html`.
3. Commit and push only the new deck, `index.html`, assets, and change artifacts. Rollback: revert the `index.html` commit to restore the old redirect.

## Open Questions

- Real content of the slide-15 orange and blue inventory examples (deferrable; shipped as illustrative meanwhile).
- Which case-two CRM visuals exist on ryan-chiang.com `/work/05` (deferrable; placeholders meanwhile).
