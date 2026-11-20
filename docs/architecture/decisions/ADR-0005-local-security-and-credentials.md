# ADR-0005: Local Security and Credential Handling

- **Status:** PROPOSED — owner approval required
- **Decision authority:** Project owner
- **Scope:** Local service exposure, filesystem access, GitHub credentials and future desktop boundary
- **Related:** ADR-0001, ADR-0002, ADR-0004, `MASTERPLAN.md`

## Context

VIBECUBATOR is initially local-first but will access project files, run a local service and may connect to GitHub. A local application is not automatically secure: a loopback service can still be exposed through unsafe binding, browser-origin issues, weak local authentication or excessive filesystem/command permissions. Credentials must never enter project files or Git history.

## Decision drivers

- Least privilege and explicit user control.
- Protect GitHub tokens and other credentials.
- Restrict local service access.
- Prevent arbitrary filesystem access and command execution.
- Make security behavior understandable and testable.
- Preserve a future desktop wrapper without granting it broad privileges by default.

## Proposed baseline controls

1. **Network binding:** bind the service to loopback only by default. Do not expose it on LAN/public interfaces unless the owner explicitly approves a separately reviewed deployment mode.
2. **Browser/service boundary:** define strict allowed origins, validate requests and use an appropriate CSRF strategy for state-changing endpoints. Do not rely on CORS as authentication.
3. **Local access:** evaluate a per-installation secret or equivalent local request authentication; avoid embedding reusable secrets in frontend bundles or URLs.
4. **Credentials:** use the operating system credential store where practical, or a documented secure alternative. Never store tokens in repository files, SQLite plaintext fields, logs, crash reports or exported project packages.
5. **GitHub permissions:** request the narrowest repository permissions required. Make read-only access the default until write operations are explicitly enabled by the user.
6. **Filesystem access:** scope operations to user-selected project roots. Resolve paths safely and prevent traversal outside approved roots.
7. **Command execution:** no arbitrary shell execution in the Phase 1 MVP. If Git subprocesses are required, use fixed executable invocation, argument arrays, controlled working directories, timeouts and sanitized output.
8. **Logging:** redact secrets and avoid logging project content unless necessary and disclosed.
9. **Updates and dependencies:** use pinned/locked dependencies and document security update practices.
10. **Desktop extension:** a future wrapper must use the same least-privilege interfaces and must not silently widen filesystem, process or network access.

## Alternatives considered

- **Loopback-only with minimal access (proposed):** reduces network exposure while preserving local workflows; still requires browser/service request protections.
- **LAN-accessible local server:** enables other devices but expands the threat model; not in initial scope.
- **Desktop-only privileged process:** offers OS integration but can increase impact of vulnerabilities; not selected by ADR-0001.

## Open questions for owner

- Which OS credential stores must be supported initially?
- Is a per-installation local authentication secret acceptable for browser-to-service requests?
- What exact GitHub permission model and authentication flow should Phase 1 support?
- Which project root and filesystem operations are permitted?
- Should any narrowly scoped command execution be allowed in Phase 1, or should all process execution remain excluded?

## Approval gate

This ADR is PROPOSED. Security boundaries, credential storage, GitHub permissions and any process-execution capability require explicit owner approval and security verification before implementation.
