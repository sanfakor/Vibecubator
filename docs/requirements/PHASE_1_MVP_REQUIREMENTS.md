# Phase 1 — Project Memory MVP Requirements

**Status:** PROPOSED — owner review required  
**Scope basis:** Approved Masterplan 1.0 and approved Project Memory decisions (FULL lifecycle scope; AUTONOMOUS bounded execution)  
**Implementation gate:** Phase 1 implementation remains prohibited until Phase 0 is complete and the owner approves the transition.

## 1. Product outcome

Deliver a useful, locally operated Project Memory foundation that allows a human to create and manage projects, preserve structured project knowledge, understand current status, organize work and decisions, and synchronize versioned project records with GitHub without requiring an AI provider.

FULL defines the intended lifecycle scope of VIBECUBATOR. Phase 1 is an incremental first delivery, not the implementation of the entire FULL scope.

## 2. MVP principles

- Local-first and usable without an AI provider.
- GitHub/Git is the versioned source of approved project records.
- Local persistence supports operational workflows and indexes.
- No silent overwrite or implicit conflict resolution.
- Approved decisions, proposals, working state and history remain distinguishable.
- All material changes are traceable.
- No autonomous agent execution is required for the Phase 1 MVP; the data model must not prevent later bounded autonomy.
- Technology choices remain subject to approved ADRs.

## 3. In scope

1. Create, open, edit, archive and list projects.
2. Store project identity, purpose, status and key metadata.
3. Organize project documents and retain repository-relative references.
4. Represent phases, milestones and tasks with stable IDs, status, dependencies and acceptance criteria.
5. Record decisions with status, rationale, date, source/evidence and supersession links.
6. Present a concise project dashboard based on canonical project state.
7. Maintain a local operational database and recoverable local data.
8. Connect a project to a Git repository and display branch/commit/sync state.
9. Support explicit initial GitHub synchronization for approved project files.
10. Detect divergent changes and present conflicts without silent overwrites.
11. Validate canonical structured project state against a versioned schema.
12. Export/import a portable project state package with provenance.

## 4. Out of scope for Phase 1

- AI provider integrations (browser, local model or API).
- Autonomous code editing or command execution.
- Multi-user real-time collaboration and permission administration.
- Cloud-hosted service or mandatory online account.
- Full session manager, handover automation and recovery workflow (Phase 2).
- Development engine, automated code changes and QA orchestration (Phase 4).
- Project template factory (Phase 5).
- Public release packaging and final open-source license selection.

## 5. Functional requirements

| ID | Requirement | Acceptance evidence |
|---|---|---|
| FR-001 | Create and manage multiple projects | Create, edit, archive and reopen at least two independent test projects |
| FR-002 | Maintain a canonical project identity and status | Each project has a stable ID and a validated current-state record |
| FR-003 | Organize documents with type, status and source references | User can locate a document and distinguish approved, proposed and historical material |
| FR-004 | Manage phases, milestones and tasks | Tasks support stable IDs, status, dependencies, acceptance criteria and completion evidence |
| FR-005 | Record decisions and their lifecycle | Decision records preserve alternatives, rationale, approval state and supersession history |
| FR-006 | Present current project status | Dashboard agrees with the canonical structured state and links to evidence |
| FR-007 | Persist local operational data | Data survives application restart and documented backup/restore test |
| FR-008 | Connect a project to a Git repository | Repository, branch and last-known commit are visible and validated |
| FR-009 | Perform explicit GitHub synchronization | User can inspect changes and deliberately start a sync; result is recorded |
| FR-010 | Detect synchronization conflicts | Divergent local/remote edits are surfaced and neither side is silently discarded |
| FR-011 | Validate structured project records | Invalid records are rejected with actionable validation errors |
| FR-012 | Export and import a portable project package | Export can be re-imported with stable IDs and provenance preserved |

## 6. Non-functional requirements

- **NFR-001 Reliability:** interrupted operations must not leave silently corrupted canonical records.
- **NFR-002 Traceability:** material edits, approvals, sync operations and conflict resolutions are attributable and timestamped.
- **NFR-003 Security:** credentials are never stored in project files or committed; access is limited to the required repository scope.
- **NFR-004 Privacy:** local operation is the default; no project content is sent to an AI provider in Phase 1.
- **NFR-005 Portability:** project records use documented, exportable formats and stable identifiers.
- **NFR-006 Recoverability:** backup and restore behavior is documented and tested.
- **NFR-007 Usability:** core project/task/document workflows can be completed without editing raw JSON.
- **NFR-008 Maintainability:** domain logic is separated from UI, persistence and GitHub integration at defined interfaces.
- **NFR-009 Verification:** each requirement has a testable acceptance check; unexecuted tests are never marked passed.
- **NFR-010 Offline behavior:** core local project and task workflows remain usable without network access; remote sync is clearly unavailable while offline.

## 7. Proposed acceptance gate for Phase 1

Phase 1 is ready for acceptance only when:
1. All in-scope FRs are implemented and their acceptance checks pass.
2. Data survives restart and a backup/restore cycle.
3. GitHub sync is explicit, traceable and conflict-safe in tested scenarios.
4. Invalid state records are rejected with useful diagnostics.
5. Documentation, setup instructions and a complete handover are updated.
6. Known limitations and security considerations are recorded.
7. The project owner reviews the evidence and explicitly accepts the phase.

## 8. Open questions for owner review

- Is the proposed Phase 1 MVP boundary correct, especially explicit GitHub sync and portable import/export?
- Should task and milestone management be fully included in the first usable release or staged after project/document/decision management?
- What is the expected GitHub authentication method and repository permission boundary?
- Is a single-user local installation the intended first deployment target?
- Which project artifacts should be canonical files in Git versus operational records in SQLite?

No requirement in this document is an approved implementation instruction until reviewed and approved by the project owner.
