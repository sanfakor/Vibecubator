VIBECUBATOR – MASTERPLAN

Document: Project Foundation & Masterplan
Version: 1.0
Date: 2026-11-08
Status: Draft – awaiting approval
Project: VIBECUBATOR
Repository: https://github.com/sanfakor/Vibecubator

1. Vision

VIBECUBATOR is an independent, open-source framework for continuous, structured and AI-assisted project development.

It enables projects of different types to be planned, developed, documented and maintained over extended periods of time.

Its central purpose is to solve the continuity problem of AI-assisted development.

Projects must not lose their direction, knowledge or history when:

A development session ends.
Several days or weeks pass.
A different AI system takes over.
The user changes AI providers.
A project is temporarily paused.

Core principle: The project memory is the source of truth. AI systems are interchangeable contributors. The human remains in control.

2. Project independence

VIBECUBATOR is an independent product.

The framework should support software development, web applications, desktop applications, games, research, automation and other project types.

3. Core principles
AI provider independence.
Flexible operating costs.
Persistent project memory.
Structured and controlled planning.
Mandatory documentation.
Traceable development history.
Human approval of important decisions.
Reproducible development processes.
Mandatory AI Session Handover.
Modular and extensible architecture.
4. Main system modules
4.1 Project Manager

Creates, organizes, pauses, resumes and archives projects.

4.2 Project Memory

Maintains project goals, requirements, architecture, decisions, tasks, test results, problems and historical knowledge.

Project knowledge is divided into:

Static knowledge.
Dynamic project state.
Historical knowledge.
4.3 Master Planner

Maintains the planning hierarchy:

Project → Masterplan → Phase → Milestone → Work Package → Task.

Every task has a unique ID, scope, dependencies, expected result, acceptance criteria and status.

AI systems may suggest changes, but fundamental planning changes require human approval.

4.4 AI Manager

Supports three operating modes.

Browser AI: Manual exchange of structured work orders and results with browser-based AI services.

Local AI: Local model integration.

API AI: External AI providers through official APIs.

All modes use a common task and result format.

The browser mode must work without API credentials or paid API access.

4.5 Session Manager & AI Session Handover

A mandatory core component.

Each session records:

Session ID and project ID.
Assigned task.
AI provider and operating mode.
Starting project state.
Work performed.
Modified files.
Tests and results.
Decisions and discoveries.
Outstanding problems.
Next steps.
Handover document.
Mandatory session lifecycle
Load project state.
Check previous handover.
Compare documentation and Git state.
Create a structured work order.
Perform development work.
Verify changes and tests.
Update documentation.
Generate session handover.
Record the completed or interrupted session.

A session is not considered properly completed until its handover has been generated and stored.

A recovery check must identify incomplete work and inconsistencies before a new session starts.

4.6 Development Engine

Manages Git operations, files, development branches, changes, test execution and task-related modifications.

4.7 Quality Assurance

Checks acceptance criteria, tests, documentation, compatibility, regressions and security requirements.

Unexecuted tests must never be reported as passed.

4.8 Knowledge & Research

Maintains research results, technical references, sources and hypotheses.

Research findings must remain separate from approved architectural decisions.

4.9 Template & Project Factory

Provides reusable project templates and configurable workflows for different project types.

4.10 GitHub Integration

Uses GitHub for versioned source code, documentation, commits, branches, issues, milestones and pull requests.

GitHub is the central platform for approved project knowledge.

5. Project memory

The project memory is the authoritative knowledge base.

It must preserve:

Product vision.
Requirements.
Architecture.
Decisions and alternatives.
Current development status.
Completed and open tasks.
Known problems.
Test results.
Session history.

The context supplied to an AI should be generated specifically for the current task.

The entire project history should not have to be loaded for every interaction.

6. AI Session Handover

Every development session must leave a structured handover.

The handover must contain:

Project identity and goals.
Current development phase.
Current task.
Completed work.
Modified files.
Executed tests and results.
New findings.
Decisions.
Known problems.
Open work.
Next concrete action.
Relevant documentation links.
Git commit or reference state.
Important restrictions.

The handover must be understandable by a different AI provider and by a human returning after a long break.

7. Task and AI exchange standard

Every work order must define:

Project ID.
Session ID.
Task ID.
Relevant context.
Binding project rules.
Scope of work.
Expected result.
Acceptance criteria.

Every imported AI result must distinguish between:

Implemented changes.
Proposed changes.
Unimplemented proposals.
Executed tests.
Unexecuted tests.
Confirmed findings.
Unverified hypotheses.
8. Development and architecture rules
No silent architecture changes.
No unauthorized changes to the masterplan.
Every task must have a defined scope.
Every task must have acceptance criteria.
Documentation is part of completion.
Tests must actually be executed.
AI suggestions are not automatically approved decisions.
No mandatory dependency on a single AI provider.
Project knowledge must not exist exclusively in chat histories.
Changes must be traceable.
Important decisions require Architecture Decision Records (ADRs).
Security-sensitive operations require appropriate safeguards.
Completed development states must be recoverable.
9. Technical direction

Initial technology proposal:

Area	Technology
Backend	Python
Backend framework	FastAPI
Frontend	React
Frontend language	TypeScript
Database	SQLite
Documentation	Markdown
Version control	Git
Online platform	GitHub
Local AI	Ollama
API integration	Provider adapters
Testing	pytest
Documentation website	Optional GitHub Pages

Final technology decisions must be documented in ADRs.

The first application is planned as a locally operated web application.

10. Data management

GitHub and Git contain the versioned and approved project documentation and source code.

SQLite serves as a local operational database and index.

Rules:

No silent overwriting during synchronization.
Conflicts must be detected.
Offline operation must remain possible.
Credentials must never be committed to public repositories.
Local and remote project states must be reconcilable.
11. Security and privacy

VIBECUBATOR is initially designed for local operation.

The user controls which information is shared with external AI providers.

API credentials must be stored securely.

AI-generated code must not be executed without appropriate safeguards.

Critical changes require appropriate confirmation and traceability.

12. Development roadmap
Phase 0 – Project foundation
Approve the masterplan.
Establish the GitHub repository.
Define documentation structure.
Establish development rules.
Introduce ADRs.
Establish project status tracking.

Result: A documented project foundation.

Phase 1 – Project Memory
Project management.
Document management.
Project status.
Tasks and milestones.
Decision history.
Local persistence.
Initial GitHub synchronization.

Result: A functioning project memory without AI dependency.

Phase 2 – Session Manager & Handover
Session management.
Structured work orders.
Session records.
Handover generation.
Handover import.
Recovery checks.
Git and documentation comparison.

Result: Reliable continuation across different sessions and AI systems.

Phase 3 – AI Manager
Common task format.
Browser AI workflow.
Result import.
Local AI integration.
API integration.
Context generation.
Provider switching.

Result: Multiple AI systems working with the same project knowledge.

Phase 4 – Development Engine & Quality Assurance
Git integration.
File change tracking.
Task-related changes.
Test execution.
Quality checks.
Approval workflows.

Result: Controlled AI-assisted development.

Phase 5 – Project Factory
Project templates.
Project generation.
Configurable workflows.
Extensible modules.
Project-specific rules.

Result: A reusable development framework for different project types.

Phase 6 – Pilot projects and product maturity.
Test different project types.
Improve usability.
Complete documentation.
Evaluate stability and extensibility.
Prepare public release.

Result: A mature open-source framework.

13. Acceptance and quality criteria

A development phase is complete only when:

Defined functionality exists.
Acceptance criteria are fulfilled.
Required tests have passed.
Documentation is updated.
Known limitations are recorded.
A complete handover exists.
The development state is versioned.
14. Open-source strategy

VIBECUBATOR is intended to become an independent open-source product.

The proposed initial license is MIT, subject to final approval before public release.

The project should provide installation instructions, user documentation, developer documentation, contribution guidelines and a transparent development history.

15. Success criteria

VIBECUBATOR achieves its primary objective when:

Projects of different types can be managed.
Project memory remains consistent over time.
New AI systems can understand the existing project state.
Different providers can work on the same tasks.
Browser AI can be used without API costs.
Local and API-based AI are optional alternatives.
Session handover reliably enables continuation.
Completed work is not unnecessarily repeated.
Architectural decisions are preserved.
Development progress is verifiable and reproducible.

The ultimate goal: A project must remain continuously developable even when weeks or months pass between sessions and different AI systems contribute to its development.

16. Document governance

This masterplan defines the strategic foundation of VIBECUBATOR.

It may evolve, but changes must be justified, documented and versioned.

Fundamental changes require explicit human approval.

The following specifications will be derived from this masterplan:

Documentation Structure.
Project Memory Specification.
AI Session Handover Specification.
Technical Architecture.
Development Guidelines.
Architecture Decision Records.

VIBECUBATOR – The project remembers. AI contributes. Humans decide.
