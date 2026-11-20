# VIBECUBATOR — Project Status Standard

**Version:** 1.0  
**Status:** APPROVED  
**Effective date:** 2026-11-20

## 1. Purpose

This standard makes the actual project state legible to humans, AI systems and automation. It defines one vocabulary, one canonical state file, evidence requirements and update procedures.

## 2. Canonical status source

- Canonical machine-readable state: `docs/PROJECT_STATE.json`
- Human-readable status: root `CURRENT_STATUS.md`
- Both are updated in the same change/commit.
- Other documents link to these sources and must not maintain competing live status summaries.
- The JSON structure is constrained by `docs/PROJECT_STATE.schema.json`.

## 3. Status vocabulary

### Project and phase status

| Status | Meaning |
|---|---|
| `NOT_STARTED` | Work has not begun. |
| `OPEN` | Work is active or available; completion criteria remain unmet. |
| `BLOCKED` | Work cannot proceed until a named blocker is resolved. |
| `IN_REVIEW` | Work is submitted for review or approval. |
| `COMPLETE` | All defined acceptance criteria are evidenced and required approval is recorded. |
| `ON_HOLD` | Work is intentionally paused. |
| `CANCELLED` | Work was explicitly stopped; rationale is recorded. |

### Work item status

Use `NOT_STARTED`, `READY`, `IN_PROGRESS`, `BLOCKED`, `IN_REVIEW`, `DONE`, `CANCELLED`.

### Evidence / maturity classification

| Classification | Meaning |
|---|---|
| `PROPOSED` | Suggested; not approved. |
| `APPROVED` | Explicitly accepted by the project owner or authorized governance. |
| `DOCUMENTED` | Described in repository documentation; does not imply implementation. |
| `IMPLEMENTED` | Present in source/configuration; does not imply successful verification. |
| `PARTIALLY_IMPLEMENTED` | Some implementation exists; criteria are not fully met. |
| `VERIFIED` | Checked against defined criteria with recorded evidence. |
| `MISSING` | Required item was checked and is absent. |
| `UNKNOWN` | Not inspected or insufficient evidence exists. |
| `DEPRECATED` | No longer recommended; retained for context. |
| `SUPERSEDED` | Replaced by a newer authoritative item. |
| `ARCHIVED` | Retained for historical reference but excluded from the active knowledge base. |
| `REJECTED` | Explicitly evaluated and rejected; rationale remains traceable. |

These classifications describe different dimensions and must not be treated as interchangeable. For example, a specification can be APPROVED and DOCUMENTED while the feature remains NOT_STARTED.

## 4. Evidence rules

Each material status claim should carry:
- a stable ID;
- a concise statement;
- a status;
- evidence references (repository-relative paths, commit SHA, issue/PR, test command/result);
- an observation date;
- optional owner or dependency.

Use explicit evidence limitations. A missing file in a complete repository tree can support MISSING; an incomplete inventory supports UNKNOWN. Planned work is not evidence of implementation. A test is VERIFIED only if it was executed and its result is retained or summarized.

## 5. Required project state fields

The canonical state records schema version, project identity, repository and branch, last verified commit, update timestamp, current phase, phase status, overall status, next action, implementation summary, documentation inventory, blockers, open decisions, risks, verification record and owner approvals.

Keep state concise. Link to detailed specifications and logs instead of duplicating them.

## 6. Update procedure

Update state whenever phase, milestone, implementation, verification, blocker, next action or approval changes. In one change:

1. Inspect the relevant files, Git state and tests.
2. Update `docs/PROJECT_STATE.json`.
3. Update root `CURRENT_STATUS.md` to agree with it.
4. Update roadmap/checklist or detailed records if affected.
5. Validate JSON against the schema.
6. Review both files for consistency.
7. Commit with a message explaining the state change.

Do not update the timestamp merely to make stale information appear fresh; it is the time of the latest actual verification/update.

## 7. Phase completion

A phase is COMPLETE only when all exit criteria are met, evidence is recorded, relevant tests/checks are executed where applicable, unresolved exceptions are accepted explicitly, and required human approval is recorded. A phase cannot self-approve based on an AI agent's assessment.

## 8. Conflict handling

If sources conflict, preserve the conflicting references, mark the affected fact UNKNOWN or BLOCKED as appropriate, explain the impact, and ask for owner clarification when required. Do not silently infer precedence beyond the documented authority rules.
