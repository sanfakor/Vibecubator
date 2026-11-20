# Phase 1 — Approved Planning Backlog

**Status:** APPROVED PLANNING BASELINE — implementation not authorized  
**Depends on:** Phase 0 completion, accepted ADRs and owner approval of the transition

## Backlog conventions
Each item has a stable ID, dependency, expected result and acceptance evidence. Priority expresses delivery order. Effort estimates are intentionally deferred until the developer environment and vertical-slice assumptions can be measured.

## Work packages

| ID | Priority | Work package | Dependencies | Acceptance evidence |
|---|---|---|---|---|
| P1-001 | P0 | Repository and developer environment baseline | Phase 0 gate; ADR-0001/0002 | Reproducible setup, documented commands, clean environment verification |
| P1-002 | P0 | Domain model and canonical project-state contract | P1-001; ADR-0003 | Versioned entities, stable IDs, status lifecycle and schema tests |
| P1-003 | P0 | Local persistence and migrations | P1-002; ADR-0003 | CRUD flows, restart, migration and integrity tests |
| P1-004 | P0 | Project and workspace management | P1-003 | Create, list, open, edit and archive projects |
| P1-005 | P1 | Document registry and provenance | P1-002, P1-003 | Metadata, status, source references and filtering |
| P1-006 | P1 | Phase, milestone and task management | P1-002, P1-003 | Stable IDs, dependencies, acceptance criteria, status transitions and evidence |
| P1-007 | P1 | Decision records and lifecycle | P1-002, P1-003 | Proposal, approval, rejection, supersession and rationale traceable |
| P1-008 | P1 | Project status dashboard | P1-004 through P1-007 | Dashboard matches canonical state and links to records |
| P1-009 | P1 | Git repository connection and status inspection | P1-001; ADR-0001/0002/0004 | Repository, configured branch and commit displayed without mutation |
| P1-010 | P1 | Controlled GitHub sync workflow | P1-005, P1-009; ADR-0004/0005 | Preview, user-triggered operations, separate commit/push confirmation and audit record |
| P1-011 | P1 | Conflict detection and resolution UI | P1-010; ADR-0004 | Divergence detected, both versions preserved and resolution audited |
| P1-012 | P1 | Portable project export/import | P1-002 through P1-007 | Round-trip preserves IDs, statuses, references and provenance |
| P1-013 | P2 | Backup and restore | P1-003 | Documented backup and successful restore test |
| P1-014 | P1 | Security, privacy and failure-mode verification | P1-001 through P1-013; ADR-0005 | Credential handling, access boundaries, cross-platform and interruption tests |
| P1-015 | P2 | User/developer documentation and release-candidate handover | P1-001 through P1-014 | Setup, workflows, limitations, test evidence and handover published |

## Suggested delivery sequence
1. Establish environment and architecture boundaries (P1-001).
2. Define canonical domain model and contracts (P1-002).
3. Implement persistence, then project and knowledge workflows (P1-003 to P1-007).
4. Add dashboard (P1-008).
5. Add read-only Git inspection, controlled sync and conflict handling (P1-009 to P1-011).
6. Deliver import/export, backup/recovery and security verification (P1-012 to P1-014).
7. Complete documentation and release-candidate handover (P1-015).

## Definition of Ready
A work package may enter implementation only when:
- Phase 0 is COMPLETE and the owner approved the transition.
- Relevant ADRs are accepted.
- Scope and acceptance evidence are clear.
- Dependencies are complete or explicitly waived.
- Permissions, data access and stop conditions are clear.

## Definition of Done
- Acceptance criteria met with recorded evidence.
- Relevant tests/checks actually executed.
- Documentation and canonical state updated.
- Changes reviewable and traceable.
- Known limitations and follow-up work recorded.

No effort estimate is implied. Measure it after P1-001 and the initial vertical slice. This backlog does not authorize implementation while Phase 0 is OPEN.
