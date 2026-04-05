# Portfolio Roadmap

This roadmap prioritizes improvements that increase employer-facing impact.

## Phase 1: Reliability and developer experience
- Add validation for duplicate schedule entries and duplicate student records.
- Add safer error messages in UI (replace silent stack traces in user paths).
- Add reproducible local setup with scripts (completed in this repo refresh).

## Phase 2: Testability and code quality
- Introduce unit tests for query classes with a disposable Derby test database.
- Split `MainFrame` into smaller UI/controller classes.
- Centralize constants for status flags and SQL strings.

## Phase 3: Product polish
- Modernize Swing styling and UX copy.
- Add screenshot/GIF walkthrough to README.
- Add export capability (CSV/PDF) for schedule and roster views.

## Phase 4: Advanced portfolio upgrades
- Migrate to layered architecture (service + repository + UI).
- Add REST API mode alongside desktop UI.
- Introduce authentication roles (admin vs student login).

## Recommended showcase narrative
“I inherited a course scheduling desktop app and turned it into a production-style portfolio project by improving setup automation, architecture docs, runtime configurability, and maintainability.”
