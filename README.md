# VIBECUBATOR

**AI-assisted Project Development & Production Framework**

VIBECUBATOR is an open-source framework for planning, developing, documenting and maintaining projects with interchangeable AI systems. Its purpose is to make long-running AI-assisted work understandable, traceable and resumable for both humans and machines.

## Core principle

**The project repository is the source of truth. AI systems are interchangeable contributors. Humans retain decision authority.**

VIBECUBATOR addresses context loss, contradictory AI output, repeated work, undocumented decisions and unclear development status through structured project memory, controlled planning, evidence-based status tracking and mandatory session handovers.

## Start here

Read these documents in order:

1. [Current Status](CURRENT_STATUS.md) — concise, human-readable current state.
2. [Machine-readable Project State](docs/PROJECT_STATE.json) — canonical structured status.
3. [Status Standard](docs/STATUS_STANDARD.md) — status vocabulary, evidence and update rules.
4. [AI Agent Instructions](AGENTS.md) — mandatory operating rules for AI contributors.
5. [Masterplan](MASTERPLAN.md) — approved strategic direction.
6. [Documentation Structure](DOCUMENTATION_STRUCTURE.md) — document responsibilities and authority.
7. [Phase 0 Checklist](docs/PHASE_0_CHECKLIST.md) — foundation exit criteria.
8. [Development Roadmap](docs/planning/DEVELOPMENT_ROADMAP.md) — phases and intended outcomes.

## Project status

**Phase 0 — Project Foundation · OPEN**

The repository currently contains planning and specification documents. No executable application or automated test suite is present in the inspected repository tree. Phase 0 is not complete; implementation must not begin until the checklist is satisfied and the project owner explicitly approves the transition.

The machine-readable state in `docs/PROJECT_STATE.json` is the canonical status record. `CURRENT_STATUS.md` is its human-readable counterpart. Both must be updated together in the same change.

## Main system capabilities (planned)

- Project Manager and persistent Project Memory
- Master Planner, phases, milestones and tasks
- AI Manager with browser, local and API operating modes
- Session Manager and mandatory AI Session Handover
- Development Engine and Quality Assurance
- Knowledge & Research
- Template & Project Factory
- GitHub integration

These are product concepts, not claims of implemented functionality.

## Development principles

- Preserve the approved strategic direction in `MASTERPLAN.md`.
- Separate verified facts, approved decisions, proposals and unknowns.
- Never claim a feature exists without source evidence.
- Never report a test as passed unless it was executed.
- Record decisions and material changes traceably.
- Keep AI-provider integrations out of the Phase 1 MVP unless an approved dependency requires them.
- Require human approval for changes to project fundamentals and phase transitions.

## Repository

[github.com/sanfakor/Vibecubator](https://github.com/sanfakor/Vibecubator)

## License

The project license has not yet been finalized.
