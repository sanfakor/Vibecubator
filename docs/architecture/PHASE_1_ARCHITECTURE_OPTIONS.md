# Phase 1 — Architecture Options and Decision Disposition

**Status:** DECISIONS RECORDED — binding decisions are in ADR-0001 through ADR-0005  
**Phase:** 0 (foundation)  
**Decision authority:** Project owner

## Purpose
This document preserves the rationale for the Phase 1 architecture. It is an overview, not a substitute for the accepted ADRs.

## Accepted architecture baseline (2026-11-20)
- Application shape: local web application first; optional desktop wrapper later (ADR-0001).
- Backend/frontend: Python + FastAPI; React + TypeScript; versioned HTTP/JSON API over loopback (ADR-0002).
- Data ownership: Git repository for canonical project artifacts; SQLite for local operational data, indexes and sync bookkeeping (ADR-0003).
- Synchronization: user-triggered controlled operations, one configured branch, preview and explicit confirmation before commit, push or applying remote fast-forward changes (ADR-0004).
- Security/platforms: Windows, macOS and Linux; native OS credential store; loopback-only service and installation-specific secret; fail closed if secure credential storage is unavailable (ADR-0005).

## Architectural boundaries
Git owns durable, reviewable project knowledge: specifications, structured state, phases, milestones, tasks, decisions and source code. SQLite owns operational projections and local-only state. Derived indexes must be rebuildable. Context packages are read models, not write authorities.

The MVP is single-user and locally operated. It does not include LAN exposure, cloud hosting, multi-user collaboration, desktop packaging, AI provider integration or autonomous code execution.

## Implementation-level details still to resolve
- Concrete GitHub authentication flow and least-privilege permission manifest.
- Canonical file layouts and detailed schemas for project/work/task/decision records.
- Frontend build/test tooling and platform packaging after a vertical-slice proof of concept.
- Linux Secret Service availability and locked/unavailable provider behavior.
- Cross-platform service lifecycle, origin/CSRF controls and safe Git process invocation.

These details must be resolved before the corresponding work packages. They do not reopen the accepted architecture baseline.

## Implementation gate
All five ADRs are ACCEPTED for planning. Phase 1 implementation remains prohibited until Phase 0 is complete and the owner explicitly approves P0-11.
