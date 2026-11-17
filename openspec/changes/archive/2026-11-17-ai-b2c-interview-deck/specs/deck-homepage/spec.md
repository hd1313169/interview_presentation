# Spec Delta

## MODIFIED Requirements

### Requirement: Root serves the current deck
The root `index.html` SHALL be the published AI + B2C edition deck itself, so the short site URL shows the presentation without a redirect. The previous bear-edition deck SHALL remain available at `bear/RyanChiang_presentation.html`.

#### Scenario: Visit the site root
- **WHEN** a visitor opens the Pages root URL
- **THEN** the deck loads at that URL and the first slide is shown

#### Scenario: Slide hash
- **WHEN** the root is opened with `#5`
- **THEN** slide 5 is shown and the URL stays at the root

#### Scenario: Previous edition still reachable
- **WHEN** a visitor opens `bear/RyanChiang_presentation.html`
- **THEN** the bear-edition deck loads
