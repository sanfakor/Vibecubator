# ADR-0002: Backend and Frontend Technology Stack

- **Status:** ACCEPTED
- **Decision date:** 2026-11-20
- **Decision authority:** Project owner
- **Scope:** Phase 1 backend and browser frontend
- **Related:** ADR-0001, ADR-0003, ADR-0005

## Context
ADR-0001 selects a local web application. The owner explicitly selected the Masterplan's Python/FastAPI and React/TypeScript stack. The MVP targets a single-user local installation on Windows, macOS and Linux.

## Decision
- Backend: **Python + FastAPI**.
- Frontend: **React + TypeScript**.
- API: versioned HTTP/JSON over loopback only.
- Backend tests: pytest.
- Frontend unit/component and browser test tools: select after a small proof of concept.
- Dependency and build tools: choose supported lockfile-based tools during implementation planning.
- Keep domain logic independent of browser APIs and platform-specific services. Use adapters for OS credential storage and process integration.

## Alternatives
1. Python/FastAPI + React/TypeScript — selected; aligns with Masterplan and separates domain/API/UI.
2. Python with server-rendered or lighter UI — fewer moving parts, but less suited to planned interactive workflows.
3. TypeScript full-stack — one language, but less aligned with current project direction.
4. Desktop-first — not selected; desktop remains optional under ADR-0001.

## Consequences
Backend and frontend have separate build/test surfaces. API schemas are explicit compatibility boundaries. A vertical-slice proof of concept must validate startup, API connectivity, SQLite, cross-platform assumptions and test setup before broad implementation.

## Approval
The owner approved Python + FastAPI and React + TypeScript on 2026-11-20. This approves the stack, not dependency installation or Phase 1 implementation.
