# ADR-0004: Git Synchronization and Conflict Handling

- **Status:** ACCEPTED
- **Decision date:** 2026-11-20
- **Decision authority:** Project owner
- **Scope:** Phase 1 repository connection and synchronization
- **Related:** ADR-0001, ADR-0003, ADR-0005

## Decision
1. Core project, task, document and decision workflows remain usable offline.
2. MVP supports **one configured branch** per project. Branch switching, automatic branch creation and multi-branch workflows are out of scope.
3. Synchronization is user-triggered only; no background fetch/push or scheduled network writes.
4. Before mutation, show repository identity, branch, local/remote revisions, pending changes and file-level diff.
5. VIBECUBATOR may prepare a commit from selected changes; show paths and diff and require explicit confirmation before creating it.
6. Push requires a separate explicit confirmation. A local commit is not a successful remote push.
7. Remote changes may be applied only after preview and explicit confirmation. Even clean fast-forward updates are never silent.
8. Detect divergence by common ancestry and changed paths/content. Preserve both sides and Git references until explicit resolution.
9. No last-write-wins policy based on timestamps or arrival order.
10. No automatic merge/rebase, force-push, reset, clean, deletion, branch or PR creation in the MVP.
11. Record revisions, selected paths, operation outcomes, conflicts and resolution references.
12. Interrupted/failed operations must leave a recoverable state and never report success.

## Alternatives
- Background sync — rejected due to surprise and data-loss risk.
- Controlled explicit sync — selected: inspect, preview, select, confirm commit, separately confirm push.
- External manual Git only — safe but omits integrated workflow.

## Consequences
UI distinguishes fetch, preview, commit, push and remote fast-forward. Write permission is only needed for explicitly enabled push. Conflict resolution preserves both originals.

## Approval
The owner selected controlled Git actions and one configured branch on 2026-11-20. No background sync, automatic merges or destructive operations are authorized.
