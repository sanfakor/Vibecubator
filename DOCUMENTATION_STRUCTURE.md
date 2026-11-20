# VIBECUBATOR — Documentation Structure

**Version:** 1.1  
**Status:** APPROVED BASELINE  
**Last updated:** 2026-11-20

## 1. Purpose

This document defines where project information belongs, which document is authoritative for each subject, and how humans and AI agents must resolve inconsistencies. Documentation is part of the product and development process.

## 2. Governing principles

1. The Git repository is the version-controlled source of truth.
2. Each information domain has one canonical document or record.
3. Human-readable documentation and machine-readable state must agree.
4. Evidence, assumptions, proposals and decisions are explicitly distinguished.
5. Historical records are append-only in meaning; corrections remain traceable.
6. AI agents may analyze and propose. They may not silently approve strategic or architectural decisions.
7. Documents are created when they have real content; empty placeholder directories are avoided.

## 3. Authority and precedence

The following precedence applies by information domain, not as a blanket ranking of every file:

| Domain | Canonical authority |
|---|---|
| Strategic vision, goals and scope | `MASTERPLAN.md` (approved changes require owner approval) |
| Current project state | `docs/PROJECT_STATE.json` |
| Human-readable current status | `CURRENT_STATUS.md` (must agree with the JSON state) |
| Status vocabulary and evidence rules | `docs/STATUS_STANDARD.md` |
| AI operating rules | `AGENTS.md` |
| Documentation responsibilities | `DOCUMENTATION_STRUCTURE.md` |
| Persistent knowledge requirements | `PROJECT_MEMORY_SPECIFICATION.md` |
| Phase exit criteria | `docs/PHASE_0_CHECKLIST.md` and later phase-specific criteria |
| Technical decisions | Approved ADRs in `docs/architecture/decisions/`; proposals remain explicitly unapproved |
| Session-level history and handover | Individual records in `docs/sessions/` when introduced |

Actual source code, Git history and executed test output are evidence about implementation. They do not silently amend approved requirements or decisions.

If two authoritative sources conflict, record the conflict and stop affected work where the ambiguity could change scope, architecture or correctness. Do not resolve it by guessing.

## 4. Repository documentation map

```text
Vibecubator/
├── AGENTS.md
├── README.md
├── MASTERPLAN.md
├── CURRENT_STATUS.md
├── DOCUMENTATION_STRUCTURE.md
├── CURRENT_STATUS_AND_NEXT_STEPS.md   # legacy handover; points to canonical state
├── PROJECT_MEMORY_SPECIFICATION.md
└── docs/
    ├── PROJECT_STATE.json              # canonical machine-readable state
    ├── PROJECT_STATE.schema.json       # structural validation contract
    ├── STATUS_STANDARD.md
    ├── DOCUMENTATION_RULES.md
    ├── PHASE_0_CHECKLIST.md
    ├── CURRENT_STATUS.md               # compatibility pointer
    ├── architecture/
    │   └── PHASE_1_ARCHITECTURE_OPTIONS.md
    ├── audits/
    │   └── REPOSITORY_AUDIT_2026-11-20.md
    ├── planning/
    │   ├── DEVELOPMENT_ROADMAP.md
    │   └── PHASE_1_BACKLOG.md
    └── requirements/
        └── PHASE_1_MVP_REQUIREMENTS.md
```

Future documents may be added under `docs/project/`, `docs/architecture/`, `docs/development/` and `docs/sessions/` when the relevant work is approved and sufficiently defined. Phase 1 architecture options, MVP requirements and backlog are currently proposals under `docs/architecture/`, `docs/requirements/` and `docs/planning/`.

## 5. Status model

Use the controlled vocabulary in `docs/STATUS_STANDARD.md`. A planned feature is not implemented; an implemented feature is not automatically verified; a verified test must include its execution evidence.

## 6. Maintenance requirements

Update the canonical state and its human-readable counterpart together whenever any of the following changes:

- Current phase, phase status or next milestone
- Implementation status or verification evidence
- Active task or next concrete action
- Material risks, blockers or unresolved decisions
- Phase readiness or owner approval

Update the roadmap when phase scope or sequencing changes. Update the Masterplan only through an explicitly approved change. Record technical choices in ADRs rather than burying them in status reports.

## 7. Approval

This document records the approved documentation-structure baseline. It does not approve the proposed technical stack, declare Phase 0 complete, or authorize Phase 1 implementation.

**VIBECUBATOR — The project remembers. AI contributes. Humans decide.**
