# Phase 1 — Architecture Options and Open Decisions

**Status:** PROPOSED — decision preparation only  
**Phase:** 0 (foundation)  
**Decision authority:** Project owner  
**Constraint:** No option in this document is an approved technology or architecture decision.

## 1. Purpose

Prepare the architecture decisions needed to implement Phase 1 (Project Memory) without silently converting the Masterplan's initial technology proposal into a binding stack.

The approved Masterplan requires a locally operated first application, provider-independent Project Memory, GitHub/Git as the versioned project record, SQLite as the local operational database/index, offline operation, conflict detection and no silent overwrites. Its listed language and framework choices remain proposals pending ADRs.

## 2. Architecture drivers

1. Local-first operation; the user can work without an AI provider or continuous network connection.
2. Durable, traceable project knowledge across sessions and AI providers.
3. GitHub/Git remains the versioned source for approved project documents and source code.
4. Local operational data supports fast queries without becoming an untraceable competing authority.
5. Synchronization detects conflicts and never silently overwrites divergent changes.
6. Clear separation between domain logic, persistence, UI and external integrations.
7. Small Phase 1 delivery surface; defer AI provider adapters and autonomous code execution to later phases.
8. Testability, maintainability, portability and secure handling of credentials.

## 3. Candidate deployment shapes

| Option | Description | Advantages | Costs / risks |
|---|---|---|---|
| A — Local modular web application | Local backend service, browser UI, local database; modules separated by domain boundaries | Matches Masterplan's locally operated web application; clear API and test seams; UI/backend can evolve independently | Two runtime surfaces; local service lifecycle, ports and browser integration need care |
| B — Single-process desktop application | Desktop shell with embedded UI and local domain/persistence layer | Integrated launch experience; potentially simpler distribution and local file access | Desktop packaging and platform-specific complexity; may constrain later browser-based access |
| C — Headless local service first | Domain/API and persistence first; UI initially minimal or deferred | Strong testability and clean API foundation; reduces early UI effort | Delays user workflow validation; risks building abstractions before usability is tested |

**Initial assessment:** Option A is the closest fit to the Masterplan's stated local web application direction, but it is not selected or approved. Option B should be reconsidered only if desktop integration becomes a demonstrated requirement. Option C may be useful as an implementation sequence inside A, not necessarily as the final product shape.

## 4. Technology candidates (not decisions)

The Masterplan's initial proposal lists Python, FastAPI, React, TypeScript, SQLite, Markdown, Git, GitHub and pytest, with Ollama/provider adapters later. Evaluate each choice against the architecture drivers rather than treating the list as approved.

| Concern | Candidate direction | Decision still required |
|---|---|---|
| Backend | Python + FastAPI (Masterplan proposal) | Confirm language/framework and runtime support |
| Frontend | React + TypeScript (Masterplan proposal) | Confirm SPA vs simpler server-rendered UI and packaging |
| Local persistence | SQLite (Masterplan direction) | Define schema ownership, migrations, backup and recovery |
| Project files | Markdown + structured JSON where appropriate | Define canonical formats and validation rules |
| Version control | Git + GitHub integration | Define supported operations and authentication model |
| Tests | pytest (Masterplan proposal) plus frontend tests if needed | Choose test layers and coverage gates |
| AI integrations | Excluded from Phase 1 MVP | Preserve extension points without implementing adapters |

## 5. Data and synchronization boundaries

Proposed responsibility split for review:

- **Git repository:** versioned, reviewable project specifications, approved decisions, source code and other durable project artifacts.
- **Local SQLite database:** operational indexes, local UI state, task/query projections and synchronization metadata.
- **Derived indexes/cache:** rebuildable from authoritative repository records and local operational records; never an independent authority.
- **AI context package:** generated, task-scoped read model with provenance and status; never a write authority by itself.

Synchronization must be explicit and observable. At minimum it needs remote/local revision identifiers, last successful sync, pending changes, conflict records and a user-visible resolution path. Do not define a last-write-wins policy without owner approval.

## 6. ADRs required before Phase 1 implementation

| ADR | Decision | Required alternatives / evaluation |
|---|---|---|
| ADR-0001 | Application shape and runtime | Local web app vs desktop shell vs headless-first; lifecycle, portability, usability |
| ADR-0002 | Backend and frontend stack | Masterplan candidates vs alternatives; ecosystem, testability, maintenance |
| ADR-0003 | Persistence and data ownership | SQLite schema, repository files, migrations, backups, derived indexes |
| ADR-0004 | GitHub synchronization and conflict handling | Manual/explicit sync vs background sync; conflict representation and recovery |
| ADR-0005 | Local security and credential handling | GitHub auth, secret storage, file-system boundaries, local network exposure |

Each ADR must contain context, decision drivers, alternatives, consequences, status and owner approval. Until then, decisions remain OPEN.

## 7. Recommended next action

The owner reviews the candidate architecture and confirms the deployment shape, technology preferences and synchronization behavior. After that, prepare ADRs with concrete trade-offs and request explicit approval. No code or dependency selection should be based solely on this proposal.
