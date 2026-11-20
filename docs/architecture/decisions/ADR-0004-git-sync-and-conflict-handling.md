# ADR-0004: Git Synchronization and Conflict Handling

- **Status:** PROPOSED — owner approval required
- **Decision authority:** Project owner
- **Scope:** Phase 1 repository connection, GitHub synchronization and conflict handling
- **Related:** ADR-0001, ADR-0003, ADR-0005, `MASTERPLAN.md`

## Context

Git and GitHub are central to VIBECUBATOR's versioned project knowledge. Phase 1 must connect local projects to repositories and support initial synchronization. Offline use, explicit user control and the Masterplan's prohibition on silent overwrites require a conservative sync model.

## Decision drivers

- No loss of divergent local or remote changes.
- Explicit user control over network writes.
- Clear provenance and auditability.
- Useful offline behavior.
- Recoverability after interruption.
- Least-privilege GitHub access.

## Proposed policy

1. **Local-first operation:** core project and task workflows remain usable offline.
2. **Read/inspect before write:** show repository identity, branch, current local commit, known remote revision and pending changes before a sync operation.
3. **Explicit synchronization:** Phase 1 sync is user-triggered. No background push, automatic merge or automatic overwrite.
4. **Conflict detection:** compare common ancestry and changed paths/content. Treat divergent edits to the same canonical artifact as conflicts requiring resolution.
5. **Preserve both sides:** retain local and remote versions or their Git references until a resolution is explicitly recorded.
6. **No implicit last-write-wins:** timestamp or arrival order is not a valid conflict-resolution policy.
7. **Traceability:** record sync attempt, source and target revisions, changed paths, outcome, conflicts and resolution reference.
8. **Safe interruption:** failed or interrupted sync must leave the repository in a recoverable state and must not report success.
9. **Scope control:** initial implementation should support a clearly bounded repository workflow; destructive Git operations and automatic branch/PR creation are not assumed.

## Alternatives considered

- **Automatic background synchronization:** convenient, but increases surprise and data-loss risk; not recommended for Phase 1.
- **Explicit pull/push with conflict preview (proposed):** more deliberate and auditable, with some user interaction cost.
- **Manual Git only:** safest initial scope, but does not satisfy the proposed Phase 1 initial synchronization workflow.

## Open questions for owner

- Is user-triggered sync the required Phase 1 policy?
- Should Phase 1 support only a single configured branch, or allow branch selection?
- Which operations are in scope: fetch, pull, commit, push, or a constrained subset?
- Should VIBECUBATOR create commits, or prepare changes for review in the user's existing Git workflow?
- What conflict-resolution UI and evidence are required for acceptance?

## Approval gate

This ADR remains PROPOSED. The owner must approve sync triggers, branch/operation scope and conflict policy before implementation. No background sync or destructive Git operation is authorized by this proposal.
