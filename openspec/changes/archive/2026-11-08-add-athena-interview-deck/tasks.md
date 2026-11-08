# Tasks

## 1. Scaffold and neutralize

- [x] 1.1 Copy `cocomart/RyanChiang_presentation_cocomart.html` to `athena/RyanChiang_presentation.html`; verify `cocomart/` is unchanged (`git status` shows no edits there) and the copy opens with no console errors
- [x] 1.2 Remove the `CO` company-line array, the `C`-key switcher, and its help text, and set title/meta to neutral text; verify a search for the target employer's name, its industry phrasing, and other prior candidates' names returns no matches in the script and markup
- [x] 1.3 Set the timer target and any "N minutes" text to 12 minutes; verify the presenter window shows a 12:00 target

## 2. Opening and case one (slides 01–11)

- [x] 2.1 Rewrite slides 01–03 (cover, about me timeline with 4 steps, two-row table of contents) from the copy doc; verify page count, one highlight per slide, and step count ≤ 4
- [x] 2.2 Rewrite slides 04–05 (case cover, context table with two rows and footnote); verify text matches the doc line by line
- [x] 2.3 Add slide 06 (two problem→solution cards, bottom insight, optional blurred user-flow thumbnail from `/images/case-02/2-a.jpg`); verify two reveal steps and slot fallback
- [x] 2.4 Build slides 07–09 (black two-phone Wizard slide, two-step map slide with caption swap, conditions modal slide) using `素材/` images, checking resolution of phone images; verify reveal order and captions; record the pending high-res item if only low-res exists
- [x] 2.5 Add slide 10 (trade-off and boundary cards, left then right) and slide 11 (three big numbers 1 year / 100+ / 1000+ and UAT line); verify numbers equal the doc
- [x] 2.6 Write neutral speaker notes for slides 01–11, dropping the employer reference on slide 11 and the JD reference on slide 10; verify notes contain no company or JD wording

## 3. Case two and closing (slides 12–19)

- [x] 3.1 Rewrite slides 12–13 (case cover with Figma/Claude Code/Gemini Notebook tags, challenge slide with two cards and four interaction tags); verify cards reveal in order and the screenshot slot shows a placeholder when no asset exists
- [x] 3.2 Rewrite slide 14 (keep workflow diagram, add 3-row AI-vs-me table with row-by-row reveal); verify three rows reveal one at a time
- [x] 3.3 Build slide 15: three numbered stage cards joined by arrows, wide "found at acceptance" card last, and the component-inventory annotation (reused slide-13 screenshot, green/orange/blue outlines, legend rows, grey caption); mark orange and blue examples as illustrative; verify reveal is cards, then wide card, within 4 steps
- [x] 3.4 Build slide 16 (three stacked cards, "開發前" highlighted) and slide 18 (explanatory line with three tags, three big numbers 1/5/7 days, Gantt); verify card order and numbers
- [x] 3.5 Build slide 17: black background, `素材/5-b.mp4` embedded or linked, muted, looping, autoplay on activation; verify it plays when the slide becomes active and pauses off-slide
- [x] 3.6 Build slide 19 without any company sentence (two-line headline with yellow second line, thanks, site and email); verify no company sentence exists and slide is black
- [x] 3.7 Write neutral notes for slides 12–19, removing "do not mention" coaching text; verify no coaching phrasing remains

## 4. Appendix (A1–A5)

- [x] 4.1 Convert former case-three slides into A1–A4 (three rule cards, permission diagram with strikethrough, four-layer verification with highlighted skill name and bottom numbers, AI-not-to-use comparison), flagged `data-appendix`; verify the overview shows them dashed and the toast announces the appendix
- [x] 4.2 Add A5 Echorise (back-office vs front-end columns, thumbnails from ryan-chiang.com `/images/case-01/` or placeholders if unavailable, bottom card); verify copy equals the doc
- [x] 4.3 Write neutral notes for A1–A5; verify A4 has no JD reference

## 5. Homepage and integration checks

- [x] 5.1 Retarget root `index.html` (meta refresh, script, fallback link) to `athena/RyanChiang_presentation.html` preserving query and hash; verify the target file exists and opening the root lands on slide 1
- [x] 5.2 Run a full pass in a browser: 24 slides, keyboard paging, fullscreen, presenter window, overview, no console errors, no company-name matches, `cocomart/` unchanged; fix findings
- [x] 5.3 Check `git status` before committing so the local `cocomart/` HTML (notes and other companies' lines) is not staged; add an ignore rule if needed; verify only the new deck, assets, `index.html`, and change files are staged
- [x] 5.4 List the remaining pending items for Ryan (slide 15 real examples, high-res phone screenshots, case-two visuals from `/work/05`, the PDF later) in the final report

## 6. Post-review revisions

- [x] 6.1 Apply the user's slide edits (03, 06, 07, 11, 12, 13, 15); verify with screenshots of each slide
- [x] 6.2 Add project covers before A1 and A5 using the portfolio cover images and enlarge A1 card text; verify 26 slides and 7 appendix entries
- [x] 6.3 Stop the last slide replaying its reveal when advancing past the end; verify repeated presses leave the slide state unchanged
- [x] 6.4 Enlarge the slide 15 screenshot, add a home icon button to slides 19 and 26, and add drag-to-jump on the progress bar; verify by screenshots and simulated drag
- [x] 6.5 Remove the remote font stylesheet and embed the missing glyphs; verify with the network disabled that there are no external requests and no system-font fallback

## Workflow follow-up

- Export the PDF after the deck is final (separate request).
- Archive the change after review.
