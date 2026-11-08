VIBECUBATOR
Documentation Structure

Document: DOCUMENTATION_STRUCTURE.md
Version: 1.0
Status: Draft – Pending Approval
Project: VIBECUBATOR

1. Purpose

This document defines the official documentation structure of VIBECUBATOR.

Its purpose is to establish a consistent, maintainable and scalable system for storing and managing all project-related information.

The documentation system must ensure that:

Project knowledge is preserved over time.
Different AI systems can continue working on the same project.
Decisions and their reasoning remain traceable.
Development progress can be reconstructed.
Outdated or contradictory information can be identified.
Documentation remains manageable as the project grows.

Documentation is an integral part of the development process, not an optional activity.

2. Fundamental Principles

The documentation system follows these principles:

2.1 One Authoritative Project Memory

The GitHub repository contains the authoritative, version-controlled project documentation.

Local databases, AI conversations and temporary working files must not silently replace or contradict the approved documentation.

2.2 Clear Separation of Information

Different types of information must have clearly defined locations.

Project goals, architecture decisions, current status, development history and session handovers must not become mixed into one large document.

2.3 Traceability

Important changes must be traceable.

Where applicable, documentation changes should reference:

Related tasks.
Relevant decisions.
Git commits.
Test results.
Previous documentation versions.
2.4 AI Independence

Documentation must be understandable by different AI providers and models.

No document may depend on the memory, internal context or proprietary conversation history of a particular AI system.

2.5 Controlled Changes

AI systems may propose documentation changes.

Changes to approved project goals, architecture principles and binding decisions require explicit approval by the project owner.

2.6 Scalability

The documentation structure must support small personal projects as well as large, long-running development projects.

Additional documentation areas may be introduced when justified.

3. Documentation Categories

VIBECUBATOR documentation is divided into the following categories.

3.1 Project Foundation

Defines the identity, purpose and fundamental direction of the project.

Documents:

README.md
MASTERPLAN.md

These documents establish what VIBECUBATOR is and what it is intended to become.

3.2 Project Memory

Contains the persistent knowledge required to understand and continue the project.

It includes:

Project objectives.
Requirements.
Architecture.
Technical concepts.
Important constraints.
Established knowledge.

Project Memory must provide sufficient context for a new AI system to understand the project without access to previous conversations.

3.3 Project Planning

Defines the intended development direction and organizes work into manageable units.

It includes:

Development phases.
Milestones.
Work packages.
Tasks.
Dependencies.
Acceptance criteria.

The planning structure must distinguish long-term objectives from immediately actionable tasks.

3.4 Architecture and Decisions

Documents the technical structure and the reasoning behind important decisions.

It includes:

Architecture documentation.
Architecture Decision Records (ADRs).
Technical constraints.
Interface definitions.
Approved alternatives and rejected approaches.

Previously approved decisions must not be silently replaced.

3.5 Development History

Records what actually happened during development.

It includes:

Completed work.
Important modifications.
Test results.
Known problems.
Relevant Git references.

Development history must distinguish verified facts from assumptions and AI-generated interpretations.

3.6 Session Management

Manages individual development sessions and their transitions.

It includes:

Session records.
Work assignments.
Session results.
Open questions.
Session handovers.
Recovery information.

A session is not considered properly completed until its results and remaining work have been documented.

4. Proposed Repository Structure

The following structure defines the intended documentation layout.

text
Vibecubator/
│
├── README.md
├── MASTERPLAN.md
├── CURRENT_STATUS.md
│
├── docs/
│   │
│   ├── DOCUMENTATION_STRUCTURE.md
│   ├── PROJECT_MEMORY_SPECIFICATION.md
│   ├── DOCUMENTATION_RULES.md
│   │
│   ├── project/
│   │   ├── VISION.md
│   │   ├── REQUIREMENTS.md
│   │   └── SCOPE.md
│   │
│   ├── architecture/
│   │   ├── ARCHITECTURE.md
│   │   └── decisions/
│   │
│   ├── planning/
│   │   ├── DEVELOPMENT_ROADMAP.md
│   │   ├── MILESTONES.md
│   │   └── tasks/
│   │
│   ├── development/
│   │   ├── DEVELOPMENT_LOG.md
│   │   ├── TEST_STATUS.md
│   │   └── KNOWN_ISSUES.md
│   │
│   └── sessions/
│       ├── SESSION_INDEX.md
│       ├── handovers/
│       └── records/
│
└── src/


This structure represents the intended documentation organization.

Directories and documents should only be created when their contents are actually needed.

The structure must not force unnecessary documentation or create empty administrative overhead.

5. Document Responsibilities

Every document must have a clearly defined responsibility.

Document	Responsibility
README.md	Project introduction and entry point
MASTERPLAN.md	Approved strategic foundation
CURRENT_STATUS.md	Current verified project status
VISION.md	Long-term project vision
REQUIREMENTS.md	Functional and non-functional requirements
SCOPE.md	Project boundaries
ARCHITECTURE.md	Overall technical architecture
DEVELOPMENT_ROADMAP.md	Development phases
MILESTONES.md	Major development objectives
DEVELOPMENT_LOG.md	Relevant development history
TEST_STATUS.md	Verified test status
KNOWN_ISSUES.md	Known problems and limitations
SESSION_INDEX.md	Overview of development sessions
PROJECT_MEMORY_SPECIFICATION.md	Rules governing persistent project knowledge
DOCUMENTATION_RULES.md	Mandatory documentation procedures

Individual tasks, ADRs, session records and handovers will use separate documents where appropriate.

6. Information Authority and Conflict Resolution

Different documents serve different purposes.

The following rules define how conflicting information must be handled.

6.1 Approved Decisions

Approved project decisions are authoritative within their defined scope.

An Architecture Decision Record documents the reasoning and consequences of a technical decision.

A newer approved decision may supersede an older one.

The original decision must remain available for historical reference.

6.2 Strategic Direction

MASTERPLAN.md defines the approved strategic direction.

Changes to the project's fundamental objectives or scope require explicit approval.

6.3 Current Development Status

CURRENT_STATUS.md represents the latest documented project state.

It must reflect verified information rather than planned or assumed functionality.

Actual source code, Git history and test results provide evidence for its contents.

6.4 Development History

Historical records must not be rewritten merely to make the current project state appear consistent.

Corrections must remain traceable.

6.5 Unresolved Conflicts

If two authoritative documents contradict each other, the conflict must be recorded.

AI systems must not independently invent a resolution.

The affected work must be clarified before proceeding if the conflict could change the implementation or project direction.

7. Information Status Classification

All important project information must be distinguishable by its status.

The following classifications are mandatory:

PROPOSED: Suggested but not approved.
APPROVED: Explicitly accepted by the project owner.
IMPLEMENTED: Actually implemented in the project.
VERIFIED: Confirmed through appropriate testing or other documented evidence.
DEPRECATED: No longer recommended or applicable.
SUPERSEDED: Replaced by a newer approved decision.

These classifications must not be used interchangeably.

For example, an implemented feature is not automatically verified.

An AI-generated proposal is not automatically an approved architectural decision.

8. Document Maintenance

Documentation must be maintained throughout development.

The following events require documentation review:

Approval of a new architectural decision.
Completion of a significant development task.
Changes to project requirements.
Changes to the development roadmap.
Discovery of important technical limitations.
Completion or interruption of a development session.
Changes to verified test results.

Documentation updates should be committed together with the relevant development changes whenever practical.

9. AI Documentation Responsibilities

Every AI system working on VIBECUBATOR must follow these rules:

Read the relevant project documentation before beginning work.
Identify the current approved project state.
Respect existing architectural decisions.
Distinguish proposals from approved decisions.
Never claim that unimplemented functionality exists.
Never claim that tests have passed unless they were actually executed.
Document relevant changes and findings.
Identify missing or contradictory documentation.
Prepare a proper session handover before ending development work.
Request approval before changing binding project decisions.

AI systems must not assume that information from previous conversations is still valid.

The repository documentation is the authoritative reference.

10. Relationship to AI Session Handover

The Session Handover system is a mandatory part of the VIBECUBATOR documentation architecture.

It ensures continuity between:

Different AI providers.
Different AI models.
Separate development sessions.
Interrupted development periods.
Different working environments.

A handover must reference the actual project state, relevant decisions, completed work, remaining tasks and the next recommended action.

The detailed handover process will be defined separately in the AI Session Handover specification.

11. Future Extensions

The documentation structure is designed to be extensible.

Additional categories may be introduced when new functionality requires them.

Examples include:

Research and external references.
Security documentation.
Release management.
Plugin documentation.
Project templates.
Automated quality reports.

Extensions must follow the same principles of clear responsibilities, traceability and controlled changes.

12. Document Status

Current version: 1.0
Status: Draft – Pending Approval

This document becomes binding only after explicit approval by the project owner.

Future modifications must be version-controlled and documented.

DOCUMENTATION_STRUCTURE.md
Approved
Version 1.0

Mandatory Documentation Structure

The structure and the rules defined therein are now considered the approved basis for further development.

VIBECUBATOR

Continuous, documented and controlled AI-assisted project development.
