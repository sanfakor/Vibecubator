# Phase 1 — Project Memory MVP Requirements

**Status:** APPROVED — owner decisions recorded 2026-11-20  
**Scope basis:** Approved Masterplan, Project Memory specification and ADR-0001 through ADR-0005  
**Implementation gate:** No Phase 1 implementation until Phase 0 is complete and the owner approves the transition.

## 1. Product outcome
Deliver a useful, locally operated Project Memory foundation that lets a human manage projects, preserve structured knowledge, understand status, organize work and decisions, and synchronize versioned project records with GitHub without requiring an AI provider.

FULL defines the intended product lifecycle scope. Phase 1 is an incremental first delivery, not the entire product.

## 2. MVP principles
- Local-first; core workflows work without an AI provider or network.
- Git is authoritative for approved, durable project records; SQLite supports operational workflows and rebuildable indexes.
- No silent overwrite or implicit conflict resolution.
- Material changes and approvals are traceable.
- No AI provider integration, autonomous code editing or command execution in this MVP.
- Single-user local installation; Windows, macOS and Linux targets.
- Platform-specific services use adapters; credential-dependent operations fail closed if secure OS storage is unavailable.
- Architecture follows accepted ADR-0001 through ADR-0005.

## 3. In scope
1. Create, open, edit, archive and list multiple projects.
2. Store project identity, purpose, status and key metadata.
3. Organize documents and retain repository-relative references.
4. Manage phases, milestones and tasks with stable IDs, status, dependencies, acceptance criteria and completion evidence.
5. Record decisions with status, rationale, date, provenance and supersession links.
6. Present a dashboard based on canonical project state.
7. Maintain local operational persistence and recoverable local data.
8. Connect a project to a Git repository and display branch, commit and sync state.
9. Support controlled, user-triggered GitHub synchronization on one configured branch. Show diffs and require explicit confirmation before commit, push or applying remote fast-forward changes.
10. Detect divergence and preserve both sides until explicit conflict resolution.
11. Validate canonical structured project state against versioned schemas.
12. Provide portable project export/import with stable IDs and provenance.

## 4. Out of scope
- AI provider integrations (browser, local model or API).
- Autonomous code editing or arbitrary command execution.
- Multi-user real-time collaboration or permission administration.
- LAN-accessible or cloud-hosted service.
- Desktop packaging (optional future delivery layer).
- Full session manager and handover automation (Phase 2).
- Development engine and QA orchestration (Phase 4).
- Project template factory (Phase 5).
- Public release packaging and final license selection.

## 5. Functional requirements

| ID | Requirement | Acceptance evidence |
|---|---|---|
| FR-001 | Manage multiple projects | Create, edit, archive and reopen at least two independent projects |
| FR-002 | Maintain canonical identity and status | Stable project ID and schema-validated current state |
| FR-003 | Organize documents and provenance | Find documents and distinguish approved, proposed and historical records |
| FR-004 | Manage phases, milestones and tasks | Stable IDs, dependencies, acceptance criteria, status and completion evidence |
| FR-005 | Record decision lifecycle | Alternatives, rationale, approval, provenance and supersession traceable |
| FR-006 | Present current status | Dashboard agrees with canonical state and links to evidence |
| FR-007 | Persist operational data | Data survives restart and backup/restore test |
| FR-008 | Connect Git repository | Repository, configured branch and last-known commit visible |
| FR-009 | Controlled GitHub synchronization | User-triggered fetch, file-level preview, confirmed commit, separately confirmed push and recorded outcome |
| FR-010 | Detect conflicts | Divergent edits surfaced; neither side silently discarded |
| FR-011 | Validate structured records | Invalid records rejected with actionable diagnostics |
| FR-012 | Portable import/export | Round trip preserves IDs, statuses, relationships and provenance |

## 6. Non-functional requirements
- **NFR-001 Reliability:** interrupted operations do not silently corrupt canonical records.
- **NFR-002 Traceability:** material edits, approvals, sync operations and resolutions are attributable and timestamped.
- **NFR-003 Security:** credentials never enter repository artifacts, plaintext SQLite fields, logs or exports.
- **NFR-004 Privacy:** local operation is default; no project content is sent to an AI provider in Phase 1.
- **NFR-005 Portability:** documented formats and stable IDs.
- **NFR-006 Recoverability:** backup and restore documented and tested.
- **NFR-007 Usability:** core workflows do not require raw JSON editing.
- **NFR-008 Maintainability:** domain logic separated from UI, persistence and integrations.
- **NFR-009 Verification:** every requirement has a testable check; unexecuted tests are never passed.
- **NFR-010 Offline behavior:** local project/task workflows remain available offline.
- **NFR-011 Platform support:** Windows, macOS and Linux; platform integrations behind adapters.
- **NFR-012 Credential safety:** native OS credential store only; fail closed without plaintext fallback.
- **NFR-013 Local service boundary:** loopback-only binding, installation-specific secret and origin/CSRF protections.

## 7. Owner decisions recorded
The owner approved tasks and milestones in the first MVP, a single-user local installation, cross-platform targets and portable import/export on 2026-11-20. Controlled Git actions and the single-branch policy are recorded in ADR-0004.

The concrete GitHub authentication flow, permission manifest, canonical file layouts, frontend tooling and platform packaging are implementation details. They must be resolved and reviewed before their work packages are implemented.

## 8. Acceptance and implementation gate
Phase 1 is ready for acceptance only when all in-scope requirements pass, data survives restart and backup/restore, Git sync is conflict-safe, invalid records are rejected, documentation and handover are complete, and the owner accepts the evidence. This document is a planning authority, not implementation authorization.
