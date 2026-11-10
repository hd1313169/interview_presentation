# Design

## Context

The Athena deck (`athena/RyanChiang_presentation.html`, ~9 MB) is a single self-contained HTML file: base64 images, an embedded font subset, slides as `<section class="slide">` with `data-title` / `data-appendix`, and 26 speaker-note blocks. The copy doc for the new deck lives in the employer-named source folder, a path that would expose the employer if published.

## Goals / Non-Goals

**Goals:** complete the 23 + 3 structure now with placeholders; published copy free of notes and employer name.

**Non-Goals:** final assets, PDF export, resolving the doc's three "請確認" items, editing the Athena or CocoMart decks.

## Decisions

- **Start from a copy of the Athena deck** rather than a blank file, so tooling and tokens stay identical. Reused: Athena p01–p07, p10, p11, the Echorise cover, A5, p14–p15 (merged into A1), and the closing slide. Dropped: map layers, condition tuning, the CRM case-two slides, Athena A1–A4.
- **Two outputs from one source:** build the full deck with notes as `bear/RyanChiang_presentation.notes.html` (git-ignored), then produce the published `bear/RyanChiang_presentation.html` by stripping note blocks with a script. Hand-maintaining two files would drift.
- **Placeholders** reuse the existing asset-slot fallback with a "待放：…" label at the layout size, so swapping in an image later is a one-slot edit.
- **Assets:** case-one screens and phone images already embedded in Athena; `素材/` marketing images (book-fair banners, social posts, ad and yoga-app banners) mapped to p20–p21 where they match; every item on the doc's pending list is a placeholder. Echorise thumbnails reuse those in Athena A5.
- **Font coverage:** new copy adds glyphs, so re-subset the embedded font from the full slide text.
- **p19:** HERA per the doc default; a single slot to swap if 索拉電波 is chosen.

## Risks / Trade-offs

- [Embedded font misses new glyphs] → scan all slide text against the subset and regenerate.
- [Notes or the employer name leak via the published file] → grep the published file for the employer's name / note text before committing.
- [Unclear which `素材/` image is which] → place a best guess and list the mapping in the final report for confirmation.
- [Tight timeline] → structure first; assets swapped in later without layout changes.
