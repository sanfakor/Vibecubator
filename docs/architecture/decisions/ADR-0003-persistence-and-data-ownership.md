# ADR-0003: Persistence and Data Ownership

- **Status:** PROPOSED — owner approval required
- **Decision authority:** Project owner
- **Scope:** Phase 1 canonical project records, operational storage and derived data
- **Related:** ADR-0001, ADR-0002, ADR-0004, `MASTERPLAN.md`

## Context

VIBECUBATOR must preserve project knowledge across sessions and AI providers. The Masterplan assigns Git/GitHub the role of versioned home for approved project documentation and source code, and SQLite the role of local operational database and index. Phase 1 needs a precise ownership boundary so two stores do not silently become competing sources of truth.

## Decision drivers

- Human-readable, versionable and portable project knowledge.
- Reliable local workflows while offline.
- Traceable history and reviewable changes.
- Recoverable operational state.
- No silent divergence between repository artifacts and local indexes.
- Schema evolution and migrations that can be tested.

## Proposed ownership model

1. **Git repository — canonical versioned artifacts:** approved project specifications, ADRs, structured project-state files, documentation and source code. Changes to these artifacts are versioned and reviewable.
2. **SQLite — operational store:** local UI preferences, caches/indexes, query projections, sync bookkeeping and transient workflow state that does not need to be a canonical shared project artifact.
3. **Derived indexes — rebuildable:** indexes and search projections must be reproducible from their declared source records. They must not become the only copy of material project knowledge.
4. **AI context packages — derived read models:** task-scoped context is generated from canonical records and operational state with provenance. An AI context package is not a write authority.
5. **No ambiguous dual ownership:** each field/entity must have a declared owner. If a record must be shared/versioned, it belongs in a documented repository artifact; SQLite may index it but must not silently override it.

## Candidate technical direction

Use SQLite for local operational persistence, with explicit schema migrations, transaction boundaries, backup/restore behavior and integrity checks. Use documented Markdown and JSON formats for repository artifacts, with JSON Schema or equivalent validation for machine-readable contracts.

This direction is consistent with the Masterplan but remains proposed until owner approval.

## Alternatives considered

- **All project data only in SQLite:** simple local transactions, but weak Git-native review, portability and collaboration for canonical project knowledge.
- **All project data only in repository files:** transparent and versionable, but inefficient for operational queries, local UI state and sync bookkeeping.
- **Split ownership (proposed):** balances reviewable canonical artifacts with efficient local operations, but requires strict boundaries and rebuild/reconciliation rules.

## Required safeguards

- Database migrations are versioned and tested.
- Backups and restore are documented and verified.
- Derived indexes can be rebuilt.
- Repository artifact updates are atomic at the file/commit boundary where possible.
- Local operational state never silently overwrites canonical repository records.
- Import/export preserves stable IDs, statuses and provenance.
- The UI exposes the source and freshness of synchronized data.

## Open questions for owner

- Confirm SQLite for operational storage.
- Confirm the repository-file vs SQLite ownership boundary.
- Which entities are canonical versioned files in Phase 1?
- Which local-only records may remain exclusively in SQLite?
- What backup/retention behavior is required for the initial single-user installation?

## Approval gate

This ADR is PROPOSED. The data ownership model and SQLite choice require explicit owner approval before implementation.
