# Spec Delta

## Purpose

Defines how the GitHub Pages root resolves to the current interview deck, so visiting the site always opens the presentation without a broken link.

## ADDED Requirements

### Requirement: Root opens the Athena deck
The root `index.html` SHALL redirect to the Athena-edition deck, preserving query string and hash.

#### Scenario: Visit the site root
- **WHEN** a visitor opens the Pages root URL
- **THEN** the browser lands on the Athena deck and the first slide is shown

#### Scenario: Query and hash preserved
- **WHEN** the root is opened with `?x=1#5`
- **THEN** the deck URL carries the same query and hash

### Requirement: No dangling redirect
The redirect target SHALL exist in the repository at the path the redirect names, and the fallback link in the page SHALL point to the same target.

#### Scenario: Target resolves
- **WHEN** the redirect target path is checked
- **THEN** the file exists and the fallback anchor uses the identical path

### Requirement: Prior deck untouched
Creating the new deck and redirect SHALL NOT modify any file under `cocomart/`.

#### Scenario: Old deck unchanged
- **WHEN** the change is complete
- **THEN** every file in `cocomart/` is byte-identical to before
