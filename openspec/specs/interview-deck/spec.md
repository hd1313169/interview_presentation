# interview-deck Specification

## Purpose

Defines the two-case interview deck (product design, then AI prototype workflow) as a single self-contained HTML presentation, so the content, presenter tooling, and confidentiality rules stay consistent as it is revised.

## Requirements

### Requirement: Slide structure and order
The deck SHALL contain 19 main slides in the order given by the layout and copy doc (opening 01–03, case one 04–11, case two 12–18, closing 19), followed by an appendix marked as such: a project cover and A1–A4 for the marketing system, then a project cover and A5 for Echorise.

#### Scenario: Slide count and order
- **WHEN** the deck is loaded
- **THEN** there are 26 slides total, the first 19 are main slides in doc order, and the last 7 are flagged as appendix

#### Scenario: Appendix is visually separated
- **WHEN** the presenter pages from slide 19 to A1, or opens the overview
- **THEN** the appendix is announced as appendix and shown with a dashed marker in the overview

### Requirement: Copy fidelity
Every slide SHALL use the label, title, subtitle, table and card text, numbers, and speaker notes from the layout and copy doc. Revisions the user gave after reviewing the deck override the doc. Facts, numbers, and claims from neither source MUST NOT be added, except project-cover facts taken from the earlier deck or ryan-chiang.com.

#### Scenario: Numbers match the doc
- **WHEN** slides 11, 18, and A3 are reviewed
- **THEN** their figures (1 year, 100+, 1000+; 1/5/7 days earlier; 1 week, 2–3 weeks, 2 days) equal the doc

#### Scenario: Slide 15 inventory legend
- **WHEN** the annotation on slide 15 is displayed
- **THEN** the boxes mark the navigation bar, the link-text column, and one expandable row, and the legend names no colors

### Requirement: Shared layout and visual system
Each slide SHALL follow the shared skeleton (section label with square icon and rule, bold one-sentence title, optional grey subtitle, two-digit page number, progress bar, "RYAN CHIANG" at bottom right) and the existing visual tokens. Slides 07, 17, and 19 SHALL use a black background; others SHALL be white. At most one highlighted phrase SHALL appear per slide.

#### Scenario: Skeleton present
- **WHEN** any main slide is displayed
- **THEN** it shows label, title, page number, progress bar, and author mark in the specified positions

#### Scenario: Highlight limit
- **WHEN** any slide is inspected
- **THEN** it contains no more than one highlighted (marker) phrase

### Requirement: Progressive reveal
Lists, cards, and table rows SHALL appear one step per advance, in the order the doc specifies, with no more than 4 steps per slide.

#### Scenario: Step-by-step reveal
- **WHEN** the presenter advances on slide 15
- **THEN** the three stage cards appear one by one (the inventory annotation appears with card 1), then the wide "found at acceptance" card appears last and takes the annotation's place

#### Scenario: Step cap
- **WHEN** any slide's reveal steps are counted
- **THEN** the count is 4 or fewer

### Requirement: Presenter features retained
The deck SHALL keep keyboard paging, fullscreen, a presenter window with notes and a 12-minute timer, a page overview, and labelled asset slots that show a placeholder when an asset is absent.

#### Scenario: Presenter window
- **WHEN** the presenter opens the presenter window on slide 10
- **THEN** it shows that slide's notes and the running timer

#### Scenario: Missing asset
- **WHEN** an asset slot has no file
- **THEN** a labelled placeholder is shown and no fabricated screen appears

### Requirement: Fast navigation controls
The progress bar SHALL be draggable to jump between slides, and slides 19 and the final slide SHALL show an icon-only button returning to slide 1.

#### Scenario: Drag the progress bar
- **WHEN** the presenter drags along the bottom progress bar
- **THEN** the deck switches to the slide at that horizontal position, shown at its first reveal step

#### Scenario: Home button
- **WHEN** the presenter clicks the home icon on the final slide
- **THEN** the deck returns to slide 1

### Requirement: Fully offline presentation
The deck SHALL render completely from its single HTML file with no network access, including every glyph of its text in the embedded fonts.

#### Scenario: Opened without a network
- **WHEN** the file is opened with the network disabled
- **THEN** no external request is made, all images and the video load, and no slide text falls back to a system font

### Requirement: Prototype video slide
Slide 17 SHALL play `素材/5-b.mp4` full-bleed on black, muted, looping, and autoplaying when the slide is active.

#### Scenario: Video plays on entry
- **WHEN** slide 17 becomes active
- **THEN** the video starts and loops

### Requirement: No company or client names
The deck, including notes and metadata, SHALL NOT contain the name of any prospective employer or client, nor any sentence aimed at a specific employer's industry. The closing slide SHALL show no company sentence and the company-line switcher SHALL NOT exist.

#### Scenario: Name scan
- **WHEN** the built HTML is searched for the target employer's name, industry-specific phrasing tied to that employer, and other prior candidates' names
- **THEN** there are no matches

#### Scenario: Closing slide
- **WHEN** slide 19 is displayed
- **THEN** it shows the two-line headline, "謝謝，歡迎提問", and the site and email, with no company sentence

### Requirement: Neutral speaker notes
Speaker notes SHALL be kept in the HTML and MUST read as talking points; coaching-only remarks (JD references, "do not mention" reminders, what to say if challenged) SHALL be rewritten neutrally or kept out of the HTML.

#### Scenario: Coaching text removed
- **WHEN** notes for slides 10, 11, 12, 16, and A4 are reviewed
- **THEN** none mention JD, interview coaching, or instructions on what not to disclose
