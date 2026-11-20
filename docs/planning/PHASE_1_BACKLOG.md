# Phase 1 — Proposed Implementation Backlog

**Status:** PROPOSED — not authorized for implementation  
**Depends on:** Phase 0 completion, approved architecture ADRs and owner approval of MVP requirements  
**Rule:** Work packages below are planning units. Do not start coding while Phase 0 is OPEN.

## Backlog conventions

Each item has a stable ID, dependency, expected result and acceptance evidence. Priority is provisional and must be confirmed with the owner after architecture decisions.

## Work packages

| ID | Priority | Work package | Dependencies | Acceptance evidence |
|---|---|---|---|---|
| P1-001 | P0 | Repository and developer environment baseline | Phase 0 gate; ADR-0001/0002 | Reproducible setup, documented commands, clean environment verification |
| P1-002 | P0 | Domain model and canonical project-state contract | P1-001; ADR-0003 | Versioned entities, IDs, status lifecycle and schema validation tests |
| P1-003 | P0 | Local persistence and migrations | P1-002; ADR-0003 | Create/read/update/archive flows; restart and migration tests |
| P1-004 | P0 | Project and workspace management | P1-003 | Create, list, open, edit and archive projects with stable identity |
| P1-005 | P1 | Document registry and provenance | P1-002, P1-003 | Document metadata, status, source references and filtering |
| P1-006 | P1 | Phase, milestone and task management | P1-002, P1-003 | Dependencies, acceptance criteria, status transitions and evidence |
| P1-007 | P1 | Decision records and lifecycle | P1-002, P1-003 | Proposals, approvals, rejection, supersession and rationale traceable |
| P1-008 | P1 | Project status dashboard | P1-004 through P1-007 | Dashboard matches canonical state and links to underlying records |
| P1-009 | P1 | Git repository connection and status inspection | P1-001; ADR-0001/0002/0004 | Repository, branch and commit state displayed without mutation |
| P1-010 | P1 | Explicit GitHub sync workflow | P1-005, P1-009; ADR-0004/0005 | Preview, user-triggered sync, recorded outcome and no silent overwrite |
| P1-011 | P1 | Conflict detection and resolution UI | P1-010; ADR-0004 | Divergent changes detected, both versions preserved, resolution audited |
| P1-012 | P2 | Portable project export/import | P1-002 through P1-007 | Round-trip test preserves IDs, statuses, references and provenance |
| P1-013 | P2 | Backup and restore | P1-003 | Documented backup and successful restore test |
| P1-014 | P2 | Security, privacy and failure-mode verification | P1-001 through P1-013; ADR-0005 | Credential handling, access boundaries and interruption scenarios tested |
| P1-015 | P2 | User/developer documentation and release candidate handover | P1-001 through P1-014 | Setup, workflows, limitations, test evidence and complete handover published |

## Suggested delivery sequence

1. Establish environment and architecture boundaries (P1-001).
2. Define domain model and canonical contracts before UI work (P1-002).
3. Implement local persistence, then project and knowledge workflows (P1-003 to P1-007).
4. Add status projection and dashboard (P1-008).
5. Add read-only Git inspection, then explicit synchronization and conflict resolution (P1-009 to P1-011).
6. Finish export/recovery, security verification and documentation (P1-012 to P1-015).

## Definition of Ready

A work package may enter implementation only when:
- Phase 0 is COMPLETE and the owner has approved the transition.
- The relevant architecture ADRs are approved.
- The work package has a bounded scope and testable acceptance criteria.
- Dependencies are complete or explicitly waived.
- Permissions, data access and stop conditions are clear.

## Definition of Done

A work package is DONE only when:
- Acceptance criteria are met with recorded evidence.
- Relevant tests/checks have actually run.
- Documentation and canonical project state are updated.
- Changes are reviewable and traceable.
- Known limitations and follow-up work are recorded.

No estimate or implementation priority is final until architecture and MVP scope are approved.
