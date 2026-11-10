# deck-homepage Specification

## Purpose

Defines how the GitHub Pages root resolves to the current interview deck, so visiting the site always opens the presentation without a broken link.

## Requirements

### Requirement: Root serves the current deck
The root `index.html` SHALL be the published bear-edition deck itself, so the short site URL shows the presentation without a redirect.

#### Scenario: Visit the site root
- **WHEN** a visitor opens the Pages root URL
- **THEN** the deck loads at that URL and the first slide is shown

#### Scenario: Slide hash
- **WHEN** the root is opened with `#5`
- **THEN** slide 5 is shown and the URL stays at the root

### Requirement: Old deck path forwards to the root
`presentation/RyanChiang_presentation.html` SHALL redirect to the site root, preserving query string and hash, and its fallback link SHALL point to the same target.

#### Scenario: Old link still works
- **WHEN** a visitor opens `presentation/RyanChiang_presentation.html#5`
- **THEN** the browser lands on the root at slide 5

### Requirement: Prior deck untouched
Creating the new deck and redirect SHALL NOT modify any file under `cocomart/` or `athena/`.

#### Scenario: Old deck unchanged
- **WHEN** the change is complete
- **THEN** every file in `cocomart/` and `athena/` is byte-identical to before
