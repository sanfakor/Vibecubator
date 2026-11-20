# Phase 0 — Foundation Exit Checklist

**Phase status:** OPEN  
**Rule:** No Phase 1 application implementation until every mandatory item is evidenced and the project owner explicitly approves the transition.

| ID | Exit criterion | Evidence required | Status |
|---|---|---|---|
| P0-01 | Complete repository inventory | Full file tree, branch/commit state, history review, code/config/test scan | OPEN |
| P0-02 | Documentation authority approved | Canonical document map and conflict rules | DONE — documentation structure recorded as approved |
| P0-03 | AI operating governance exists | Reviewed `AGENTS.md` | IN_REVIEW |
| P0-04 | Current status is machine- and human-readable | Valid JSON state plus matching human status | IN_REVIEW — schema validation pending |
| P0-05 | Masterplan remains authoritative | Owner-approved Masterplan 1.0; changes controlled | DONE — existing document marked approved |
| P0-06 | Project Memory requirements reviewed | Specification approval or documented revision | OPEN |
| P0-07 | Technical architecture sufficiently defined | Architecture proposal and approved ADRs for Phase 1 | OPEN |
| P0-08 | Phase 1 MVP scope defined | Requirements, exclusions, measurable acceptance criteria | OPEN |
| P0-09 | Phase 1 backlog actionable | Ordered tasks with IDs, dependencies, files/components, acceptance and verification | OPEN |
| P0-10 | Risks and unresolved decisions recorded | Current state and decision log | IN_REVIEW |
| P0-11 | Owner approves phase transition | Explicit recorded approval after review of all evidence | OPEN |

## Completion rule

Phase 0 is COMPLETE only when P0-01 through P0-10 are DONE with linked evidence, P0-11 is explicitly approved, and the canonical project state is updated accordingly. An AI agent cannot grant owner approval or mark the phase complete on the owner's behalf.

## Current assessment

The initial remote inventory found a documentation-only repository tree and no executable application files. This is a bounded observation, not proof that every possible branch or historical commit lacks implementation. The complete audit remains P0-01.

## Next action

Complete P0-01 on this branch, then reconcile all existing documents against the canonical status and prepare the Phase 1 architecture/MVP package without implementing the application.
