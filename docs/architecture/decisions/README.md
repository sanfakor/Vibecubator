# Architecture Decision Records

This directory contains decision records for VIBECUBATOR. A proposal is not an approved decision. Only records explicitly marked **ACCEPTED** represent an owner-approved technical decision.

## Decision index

| ADR | Subject | Status |
|---|---|---|
| [ADR-0001](ADR-0001-application-shape-and-runtime.md) | Application shape and runtime — local web first, desktop possible later | ACCEPTED |
| [ADR-0002](ADR-0002-backend-and-frontend-stack.md) | Backend and frontend technology stack | PROPOSED |
| [ADR-0003](ADR-0003-persistence-and-data-ownership.md) | Persistence and data ownership | PROPOSED |
| [ADR-0004](ADR-0004-git-sync-and-conflict-handling.md) | Git synchronization and conflict handling | PROPOSED |
| [ADR-0005](ADR-0005-local-security-and-credentials.md) | Local security and credential handling | PROPOSED |

## Change rules

- Preserve the context, alternatives, consequences and approval gate in each ADR.
- Do not silently change an accepted ADR. A material change requires a superseding ADR and owner approval.
- Update the canonical project state and human-readable status when a decision is accepted, rejected or superseded.
- ADR approval does not by itself close a project phase or authorize implementation beyond the approved phase gate.
