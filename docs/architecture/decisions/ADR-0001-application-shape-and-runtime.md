# ADR-0001: Application Shape and Runtime

- **Status:** ACCEPTED
- **Decision date:** 2026-11-20
- **Decision authority:** Project owner
- **Scope:** Phase 1 deployment shape and future desktop compatibility
- **Related:** `MASTERPLAN.md`, `docs/architecture/PHASE_1_ARCHITECTURE_OPTIONS.md`

## Context

VIBECUBATOR needs a local-first application that remains usable without an AI provider or continuous network access. The approved Masterplan describes the first application as a locally operated web application. The product may later benefit from desktop integration, but introducing platform-specific packaging before the core workflows exist would add cost and constrain early validation.

## Decision drivers

- Local-first operation and user control of project data.
- Keep UI, domain logic, persistence and integrations independently testable.
- Support Windows, Linux and macOS without making a desktop shell a Phase 1 prerequisite.
- Preserve a viable path to a desktop distribution later.
- Avoid coupling core business logic to browser or desktop APIs.

## Decision

Build VIBECUBATOR initially as a **local web application**:

1. A local application service owns domain logic, persistence and integration boundaries.
2. A browser-based frontend communicates with that service through a documented local interface.
3. Core domain and application logic must not depend on browser-specific APIs.
4. The local service must bind only to an appropriately restricted local interface by default; security details are specified in ADR-0005.
5. A desktop shell/wrapper may be evaluated later as an optional distribution and integration layer. It must reuse the same application/domain interfaces rather than fork core behavior.
6. A desktop application is not part of the Phase 1 MVP acceptance scope unless the owner explicitly changes that scope.

This decision approves the product/application shape only. It does **not** select a backend language, web framework, frontend framework, packaging tool or specific API protocol. Those remain subject to ADR-0002 and subsequent owner approval.

## Alternatives considered

### A. Local modular web application — selected

Pros: aligns with the Masterplan; portable; clear API boundary; frontend and backend can evolve independently; desktop wrapper remains possible.

Cons: local service lifecycle, browser-to-service communication and local network security require deliberate design.

### B. Desktop shell from the beginning — not selected

Pros: integrated launch, native menus and direct desktop affordances.

Cons: packaging and platform-specific behavior add early complexity; no demonstrated Phase 1 need justifies making this the primary architecture.

### C. Headless local service first — not selected as product shape

Pros: strong API and testability foundation.

Cons: postpones validation of the user workflows. A headless-first development sequence can still be used internally if it supports rapid end-to-end validation.

## Consequences

- Phase 1 architecture must define a local service lifecycle, health/readiness behavior and browser connection model.
- Frontend and backend communicate across an explicit interface, with contract tests where practical.
- Domain logic must remain reusable by future desktop packaging and non-browser clients.
- No remote/cloud deployment is implied or authorized by this decision.
- Desktop-specific features are deferred until validated user needs justify them.

## Acceptance and review

This ADR records the owner's explicit selection of a hybrid direction: local web application first, desktop possible later. The decision is accepted for the application shape. Revisit only if evidence shows that local browser delivery cannot satisfy essential workflows or the owner changes the direction.
