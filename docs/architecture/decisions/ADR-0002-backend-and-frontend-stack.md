# ADR-0002: Backend and Frontend Technology Stack

- **Status:** PROPOSED — owner approval required
- **Decision authority:** Project owner
- **Scope:** Phase 1 backend and browser frontend technology
- **Related:** ADR-0001, `MASTERPLAN.md`

## Context

ADR-0001 selects a local web application as the initial product shape. The Masterplan lists Python, FastAPI, React and TypeScript as initial technology proposals, but explicitly requires final technology decisions to be recorded in ADRs. This document evaluates a candidate direction without silently converting the Masterplan proposal into an approved stack.

## Decision drivers

- Mature ecosystem and maintainable dependencies.
- Clear separation between domain logic, API and UI.
- Good automated testing and developer tooling.
- Straightforward local development and packaging.
- Accessibility and responsive browser UI.
- Compatibility with Git/GitHub and SQLite.
- Low operational complexity for a single-user local installation.

## Candidate recommendation (not approved)

Evaluate the following as the preferred candidate stack:

- **Backend:** Python with FastAPI.
- **Frontend:** React with TypeScript.
- **API contract:** versioned HTTP/JSON interface on loopback; exact API conventions remain to be specified.
- **Backend tests:** pytest.
- **Frontend tests:** select a maintained TypeScript-compatible unit/component and browser test tool after a small proof of concept.
- **Dependency management/build tooling:** choose supported, lockfile-based tools during implementation planning; do not add them before this ADR is approved.

The recommendation follows the Masterplan and provides a familiar, testable separation. It is a candidate, not an instruction to install dependencies or start implementation.

## Alternatives to evaluate

1. **Python + FastAPI / React + TypeScript** — strongest alignment with current Masterplan proposal.
2. **Python backend with server-rendered UI or a lighter frontend** — potentially fewer moving parts; evaluate whether richer interactions justify a separate SPA.
3. **TypeScript full-stack runtime** — one primary language across UI and service; evaluate local process, file/Git integration and ecosystem trade-offs.
4. Other stacks only where a concrete requirement or proof-of-concept demonstrates a material advantage.

## Consequences if the candidate is approved

- Frontend and backend will be separate build/test surfaces.
- API schemas and validation become explicit compatibility boundaries.
- Python domain logic can be tested without launching the browser.
- Frontend dependencies and browser tests require their own maintenance.
- A small vertical-slice proof of concept should validate local startup, API connectivity, SQLite access and test setup before broad implementation.

## Open questions for owner

- Approve Python + FastAPI for the local service?
- Approve React + TypeScript for the browser UI, or prefer a simpler UI approach?
- Which frontend test/build tools should be selected after a minimal comparison?
- Are there deployment or maintenance constraints that should change the candidate stack?

## Approval gate

No framework or dependency choice in this ADR is approved. Update status to ACCEPTED only after the owner explicitly approves the stack and the chosen alternatives are recorded.
