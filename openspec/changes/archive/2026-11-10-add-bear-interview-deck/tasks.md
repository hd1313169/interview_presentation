# Tasks

## 1. Scaffold

- [x] 1.1 Copy `athena/RyanChiang_presentation.html` to `bear/RyanChiang_presentation.notes.html`; add the employer-named source folder, `bear/*.md`, `bear/*.notes.html` to `.gitignore`; verify `git status` shows no change in `athena/` or `cocomart/` and the ignored paths are hidden
- [x] 1.2 Set title/meta to neutral text and remove slides not in the new structure; verify the remaining slide list

## 2. Opening and case one (p01–p09)

- [x] 2.1 Rewrite p01–p03 (cover, four-step timeline with the +600% tag on the marketing step, three-row contents); verify text matches the doc, 銷售頁 spelling, ≤4 steps
- [x] 2.2 Adapt p04–p09 from Athena p04–p07, p10, p11 with the new copy (p09 adds the UAT line); verify 1 year / 100+ / 1000+ / 50+

## 3. Case two Echorise (p10–p15)

- [x] 3.1 Build p10 from the Echorise cover with the doc's roles, team, and timeline; verify copy
- [x] 3.2 Build p11 competitor table (3×3, highlighted conclusion, marked skippable), p12 onboarding before/after flow with the breakpoint, p13 three paywall sketches plus a mobile paywall placeholder; verify reveal order
- [x] 3.3 Adapt p14 from Athena A5 with new copy; build p15 big number + quote; verify the 30-account figure

## 4. Marketing (p16–p22)

- [x] 4.1 Build p16 black section cover with a thumbnail strip; p17 GoBridge long-page placeholder with six numbered annotations and a mobile placeholder (陌生人 spelling in notes); p18 three zoomed placeholders with captions as written; verify placeholders are labelled
- [x] 4.2 Build p19 HERA (placeholders, skippable), p20 three book-fair banners + hierarchy column, p21 social posts, ad banners, and the 瑜珈 app banner from `素材/`; verify images load and spelling
- [x] 4.3 Build p22 three big numbers (2.4萬 +600%, 1倍, +20%) and footer; verify against the doc

## 5. Closing and appendix

- [x] 5.1 Rewrite p23 closing (NEXT, headline, thanks, site and email, home button); verify black background
- [x] 5.2 Build A1 (merged AI workflow + checkpoints + 1/5/7 days), A2 Partime placeholder, A3 Wild Rescue placeholders, flagged `data-appendix`; verify 26 slides with the last 3 as appendix
- [x] 5.3 Write speaker notes in the notes copy from the doc's 講稿要點; verify every slide has notes

## 6. Publish and checks

- [x] 6.1 Re-subset the embedded font for all text; verify offline load with no system-font fallback
- [x] 6.2 Generate `bear/RyanChiang_presentation.html` by stripping notes; verify grep finds no note text, no the employer's name, no 销售 / 陸生人 / 瑑珈
- [x] 6.3 Retarget `index.html` (refresh, script, fallback link) to `bear/RyanChiang_presentation.html`; verify the target exists and query/hash are preserved
- [x] 6.4 Browser pass: paging, overview, progress-bar drag, home buttons, no console errors; verify `athena/` and `cocomart/` are unchanged (`git diff --stat` empty for them)
- [x] 6.5 Report pending assets, the `素材/` image mapping, and the doc's three confirmation items

## 7. Post-review revisions

- [x] 7.1 Fill p11, p12, p13 with content from ryan-chiang.com /work/01 and lay out images by their aspect ratio; verify by screenshots
- [x] 7.2 Match the Athena style: four-fact project covers, stat-row result pages, lead subtitles, "NN · 段落" eyebrows; verify by screenshots
- [x] 7.3 Remove the Partime and Wild Rescue appendix pages; add the CRM cover before A1 and restore the marketing-system cover and pages as A2–A5; verify 30 slides, 7 appendix
- [x] 7.4 Enlarge marketing images (GoBridge from gobridge.design split over 5 slides, social and ads over 2), replace HERA with LPG (lpgtw.com), banners-only p20, drop the reflection on the Echorise result; verify 34 slides by screenshots
- [x] 7.5 Apply review round: Athena p02/p05/p06 verbatim, agenda title, table/onboarding/paywall/token rework, new result numbers, VISUAL DESIGN cover, GoBridge 4 steps over 2 slides with site links, LPG product page, renamed asset slides; verify 31 slides by screenshots
- [x] 7.6 Replace the merged AI appendix page with the Athena CRM case slides and number appendix slides sequentially; verify 36 slides, pages 25–36
- [x] 7.7 Site links as 「查看網站」, 視覺規劃 wording, ads before social, larger app banner, remove marketing numbers slide; verify 35 slides by screenshots
