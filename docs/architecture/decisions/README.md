# Architecture Decision Records

A proposal is not an approved decision. Only records marked **ACCEPTED** represent owner-approved technical decisions.

## Decision index

| ADR | Subject | Status |
|---|---|---|
| [ADR-0001](ADR-0001-application-shape-and-runtime.md) | Local web first; desktop possible later | ACCEPTED |
| [ADR-0002](ADR-0002-backend-and-frontend-stack.md) | Python/FastAPI; React/TypeScript | ACCEPTED |
| [ADR-0003](ADR-0003-persistence-and-data-ownership.md) | Git canonical; SQLite operational | ACCEPTED |
| [ADR-0004](ADR-0004-git-sync-and-conflict-handling.md) | Controlled user-triggered sync; one configured branch | ACCEPTED |
| [ADR-0005](ADR-0005-local-security-and-credentials.md) | Cross-platform OS credential store; loopback-only | ACCEPTED |

## Change rules
- Preserve context, alternatives, consequences and approval gate in each ADR.
- Material changes to accepted ADRs require a superseding ADR and owner approval.
- Update canonical state and human status when decisions change.
- ADR approval does not close a phase or authorize implementation beyond the phase gate.
