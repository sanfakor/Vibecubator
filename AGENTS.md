# AI Agent Operating Rules — VIBECUBATOR

**Status:** APPROVED OPERATING BASELINE  
**Effective:** 2026-11-20

These instructions apply to every AI coding or research agent working in this repository.

## 1. Required reading

Before proposing or changing project files, read:

1. `README.md`
2. `CURRENT_STATUS.md`
3. `docs/PROJECT_STATE.json`
4. `docs/STATUS_STANDARD.md`
5. `MASTERPLAN.md`
6. `DOCUMENTATION_STRUCTURE.md`
7. The specification, ADRs and task documents relevant to the assignment

If any required file is missing or contradictory, report that before proceeding.

## 2. Source of truth

- The repository is the persistent project source of truth.
- `docs/PROJECT_STATE.json` is the canonical current-state record.
- Root `CURRENT_STATUS.md` is its human-readable projection.
- `MASTERPLAN.md` governs approved strategic direction.
- Approved ADRs govern technical decisions within their scope.
- Source code and executed test output are evidence, not permission to change requirements.
- Chat history is not authoritative project memory.

## 3. Status and evidence

Use only the statuses defined in `docs/STATUS_STANDARD.md`. Every material claim about implementation or verification must include a repository path, commit, test output or a clear statement that evidence is unavailable.

Never:
- describe a proposal as approved;
- describe documented intent as implemented functionality;
- describe implementation as verified without appropriate executed checks;
- report tests as passed if they were not run;
- infer absence from a partial inventory.

## 4. Change control

- Keep changes within the assigned scope.
- Prefer a dedicated branch and a reviewable pull request.
- Do not force-push, rewrite history, delete branches or remove project data without explicit owner authorization.
- Do not modify approved strategic goals or scope without explicit owner approval.
- Record significant technical choices as ADRs.
- Record unresolved conflicts rather than silently choosing a side.
- Do not add dependencies or speculative architecture without a documented need.
- Never commit credentials, tokens, private keys or local secret files.

## 5. Implementation gate

Phase 1 implementation is prohibited while Phase 0 is OPEN. Phase 0 may be marked COMPLETE only when every mandatory criterion in `docs/PHASE_0_CHECKLIST.md` has evidence and the project owner has explicitly approved the transition.

Documentation work that clarifies the foundation is allowed while Phase 0 remains open.

## 6. Required task workflow

For every assigned task:

1. Read relevant project context and inspect the actual repository state.
2. Confirm task scope, dependencies and acceptance criteria.
3. Identify affected files and risks.
4. Implement only the agreed scope.
5. Run relevant checks; record exact commands and outcomes.
6. Update affected documentation and project state.
7. Review the diff for unintended changes and secrets.
8. Provide a handover with completed work, changed files, evidence, uncompleted work, risks and one next action.

## 7. Session handover minimum

A handover must identify project, branch and commit; task and scope; work completed; files changed; commands/tests actually run and results; decisions made or proposed; blockers and unresolved questions; and the next concrete action.

## 8. Communication

Be explicit about uncertainty. Distinguish facts, assumptions, recommendations and owner decisions. Ask the owner when a decision changes strategic scope, approved architecture, security posture or a phase gate.

**The project remembers. AI contributes. Humans decide.**
