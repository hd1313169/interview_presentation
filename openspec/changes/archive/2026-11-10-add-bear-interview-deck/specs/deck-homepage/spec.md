# Spec Delta

## MODIFIED Requirements

### Requirement: Root opens the Athena deck
The root `index.html` SHALL redirect to the bear-edition deck at `bear/RyanChiang_presentation.html`, preserving query string and hash.

#### Scenario: Visit the site root
- **WHEN** a visitor opens the Pages root URL
- **THEN** the browser lands on the bear deck and the first slide is shown

#### Scenario: Query and hash preserved
- **WHEN** the root is opened with `?x=1#5`
- **THEN** the deck URL carries the same query and hash

### Requirement: Prior deck untouched
Creating the new deck and redirect SHALL NOT modify any file under `cocomart/` or `athena/`.

#### Scenario: Old deck unchanged
- **WHEN** the change is complete
- **THEN** every file in `cocomart/` and `athena/` is byte-identical to before
