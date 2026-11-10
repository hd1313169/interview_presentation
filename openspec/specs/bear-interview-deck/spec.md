# bear-interview-deck Specification

## Purpose
Defines the bear-edition interview deck (two product cases plus a marketing section) as a self-contained HTML presentation published on GitHub Pages without speaker notes or the employer's name.

## Requirements

### Requirement: Slide structure and order
The deck SHALL contain 23 main slides in the order of the copy doc (opening p01–03, case one p04–09, Echorise p10–15, marketing p16–22 with GoBridge over 2 slides and social posts and ads over 2 slides, closing), followed by an appendix flagged as such: the Athena deck's CRM AI prototype case (cover plus its six slides) and marketing management system (cover plus four slides), carried over unchanged; every slide, appendix included, shows its sequential page number.

#### Scenario: Slide count and order
- **WHEN** the deck is loaded
- **THEN** there are 35 slides, the first 23 are main slides in doc order, and the last 12 are flagged as appendix and numbered 24–35

#### Scenario: Skippable slides marked
- **WHEN** the overview is opened
- **THEN** the competitor and brand-page slides are labelled as skippable

### Requirement: Copy fidelity with typo fixes
Each slide SHALL use the eyebrow, title, subtitle, card, table, label, and number text from the copy doc, except that 销售頁, 陸生人, and 瑑珈 SHALL appear as 銷售頁, 陌生人, and 瑜珈. Facts or numbers not in the doc MUST NOT be added. Text the doc marks "設計判斷，請確認" SHALL be shown as written and remain revisable.

#### Scenario: Numbers match the doc
- **WHEN** p02, p09, p15, and p22 are reviewed
- **THEN** their figures (+600%; 1 year, 100+, 1000+, 50+; 30 accounts; 2.4萬, 1倍, +20%) equal the doc

#### Scenario: Typos corrected
- **WHEN** the deck text is searched for 销售, 陸生人, 瑑珈
- **THEN** there are no matches

### Requirement: Shared visual system and presenter tooling
The deck SHALL reuse the Athena deck's slide skeleton, visual tokens, progressive reveal (at most 4 steps per slide), keyboard paging, fullscreen, overview, 12-minute timer, draggable progress bar, and home button on the closing and final slides. p07, p16, and p23 SHALL use a black background.

#### Scenario: Presenter features work
- **WHEN** the presenter pages, opens the overview, and drags the progress bar
- **THEN** each works as in the Athena deck with no console errors

### Requirement: Labelled placeholders for missing assets
Every slot whose asset is not available SHALL show a placeholder naming the expected asset (for example "待放：GoBridge 整頁長截圖"). No fabricated screen SHALL appear.

#### Scenario: Missing asset
- **WHEN** a slide with a missing asset is displayed
- **THEN** a labelled placeholder occupies the slot at the layout's intended size

### Requirement: No speaker notes in the published deck
The published `bear/RyanChiang_presentation.html` SHALL contain no speaker-note text. A local copy with notes MAY exist but MUST be ignored by git.

#### Scenario: Notes absent
- **WHEN** the published file is searched for note content
- **THEN** no talking-point text is found

#### Scenario: Local copy not staged
- **WHEN** `git status` is run after the build
- **THEN** the local notes copy and the employer-named source folder do not appear as untracked or staged

### Requirement: No employer name
The published deck, its metadata, and its path SHALL NOT contain the employer's name, or sentences aimed at the employer.

#### Scenario: Name scan
- **WHEN** the published HTML is searched for the employer's name
- **THEN** there are no matches outside embedded binary data

### Requirement: Fully offline presentation
The deck SHALL render from its single HTML file with no network access, with all glyphs covered by embedded fonts.

#### Scenario: Opened without a network
- **WHEN** the file is opened offline
- **THEN** no external request is made and no text falls back to a system font
