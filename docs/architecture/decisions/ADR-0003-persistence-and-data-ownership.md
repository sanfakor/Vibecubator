# ADR-0003: Persistence and Data Ownership

- **Status:** ACCEPTED
- **Decision date:** 2026-11-20
- **Decision authority:** Project owner
- **Scope:** Phase 1 canonical records, operational storage and derived data
- **Related:** ADR-0001, ADR-0002, ADR-0004

## Decision
Adopt strict split ownership:

1. **Git repository — canonical project data:** approved specifications, requirements, ADRs, structured project state, project documents, phases, milestones, tasks, decisions, provenance references and source code.
2. **SQLite — local operational data:** UI preferences, caches, search indexes, query projections, sync bookkeeping, local connection metadata and transient workflow state that is not canonical project knowledge.
3. **Derived indexes — rebuildable:** reproducible from declared sources; never the only copy of material knowledge.
4. **AI context packages — derived read models:** task-scoped and provenance-aware; never write authorities.
5. **No dual ownership:** every field/entity has one declared owner. SQLite may index canonical records but cannot silently override them.

Use Markdown and structured JSON where appropriate, versioned schema validation, stable IDs, SQLite migrations, transaction boundaries, integrity checks and documented backup/restore. Import/export preserves IDs, statuses, relationships and provenance. Tasks and milestones are canonical project records, not SQLite-only rows.

## Alternatives
- All SQLite: simpler transactions, weaker Git-native review and portability.
- All repository files: transparent, but inefficient for operational state and indexing.
- Split ownership — selected: reviewable canonical artifacts plus efficient local operations.

## Consequences
Migrations and restore must be tested; indexes rebuildable; repository changes reviewable; UI exposes source/freshness. SQLite projections never become competing authority.

## Approval
The owner approved Git for canonical project data and SQLite for operational persistence on 2026-11-20. Detailed schemas and file layouts are implementation contracts to define before their work packages.
