# ADR-0005: Local Security and Credential Handling

- **Status:** ACCEPTED
- **Decision date:** 2026-11-20
- **Decision authority:** Project owner
- **Scope:** Local service, filesystem access, GitHub credentials and desktop boundary
- **Related:** ADR-0001, ADR-0002, ADR-0004

## Decision

### Platform support
Support Windows, macOS and Linux. Keep platform integrations behind adapters. Use native credential facilities: Windows Credential Manager, macOS Keychain and a Linux Secret Service-compatible provider (e.g. Secret Service via libsecret). If secure storage is unavailable or locked, credential-dependent operations fail closed. **Never fall back to plaintext files, SQLite plaintext fields, project files, exports or logs.**

### Local service and browser boundary
- Bind to loopback only; no LAN/public exposure in the MVP.
- Generate a cryptographically random, installation-specific authentication secret and store it in the OS credential store. Never embed it in frontend bundles or URLs.
- Validate request origin/host and protect state-changing requests against CSRF. CORS is not authentication.
- Redact secrets from logs, diagnostics, crash reports and exports.

### GitHub credentials and permissions
- Store credentials only via the OS credential-store adapter.
- Least-privilege repository-scoped permissions; read-only by default.
- Enable write access only for the explicitly confirmed controlled-push workflow.
- Concrete authentication flow and permission manifest must be documented and security-reviewed before remote writes are enabled.

### Filesystem and process boundaries
- Restrict file operations to user-selected project roots; prevent path traversal.
- No arbitrary shell or user-supplied command execution in Phase 1.
- If Git subprocesses are needed, use a fixed executable, argument arrays, controlled working directory, timeouts and sanitized output.
- A future desktop wrapper must reuse these least-privilege interfaces.

## Alternatives
Native OS credential stores behind an adapter — selected. Encrypted application-managed file — not default due to key-management complexity. Plaintext storage — rejected. LAN server — out of scope.

## Consequences and verification
Test loopback binding, origin/CSRF, root boundaries, secret redaction, safe Git invocation and credential-provider absent/locked behavior on each OS. Linux without a secure provider must fail closed.

## Approval
The owner approved cross-platform support, OS-native credential storage and loopback-only access with an installation-specific secret on 2026-11-20. This does not authorize LAN exposure, arbitrary shell execution or Phase 1 implementation.
