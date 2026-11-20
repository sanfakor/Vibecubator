# VIBECUBATOR — Project Memory Specification

> **Reconstruction notice — RECONSTRUCTED; scope and autonomy decisions APPROVED**
>
> Sections 1 and 2.1–2.5 were missing from the repository's original file and could not be recovered from Git history. The text below is a newly reconstructed draft based on the approved `MASTERPLAN.md` and the surviving sections 2.6–14. It is **not original source text**. The project owner has approved the FULL lifecycle scope and AUTONOMOUS bounded-execution model on 2026-11-20. Approval of those decisions does not imply approval of every reconstructed passage or of the complete specification.
>
> **Document status:** Draft — reconstructed opening remains subject to review; scope and autonomy decisions approved
> **Version:** 1.1 (owner approval of FULL scope and AUTONOMOUS bounded execution recorded on 2026-11-20)
> **Project:** VIBECUBATOR
> **Source basis:** `MASTERPLAN.md` (approved, version 1.0) and surviving content of this document from section 2.6 onward
>
> **Interpretation rule:** The FULL scope and AUTONOMOUS bounded-execution model are approved project decisions as of 2026-11-20. Reconstructed explanatory wording remains subject to review where explicitly indicated. This approval does not approve a technical stack or implementation architecture.
>
> **Owner decisions (2026-11-20):** Project Memory scope = `FULL` — **APPROVED**. AI autonomy = `AUTONOMOUS` — **APPROVED**, subject to the bounded-execution rules in this specification.

## 1. Purpose and Scope

### 1.1 Purpose

The Project Memory is the persistent, structured knowledge foundation of VIBECUBATOR. Its purpose is to preserve a project's direction, context, decisions and development history so that work can continue reliably across separated development sessions, long pauses and interchangeable AI systems.

It provides a consistent source of project context for humans and AI contributors. It should make the current state understandable, support evidence-based continuation and reduce repeated work caused by lost or fragmented context.

The Project Memory supports the VIBECUBATOR principle:

**The project remembers. AI contributes. Humans decide.**

### 1.2 Scope

The approved scope is `FULL`: the Project Memory is intended to maintain and make retrievable the complete body of knowledge required across the project lifecycle — from inception and planning through requirements, design, implementation, testing, release, operation, maintenance and evolution. It includes, at minimum:

- Project identity, vision, objectives and scope.
- Requirements, constraints and acceptance criteria.
- Approved decisions and their rationale.
- Architecture and technical knowledge, including known limitations.
- Tasks, milestones, dependencies and current working state.
- Session outcomes, handovers, discoveries and unresolved issues.
- Test evidence and references to implemented changes.
- Relevant external knowledge together with its source.

The Project Memory must support both relatively stable project knowledge and information that changes during active development. The surviving sections of this specification define the knowledge categories, lifecycle, retrieval, logical model, security considerations and minimum functional expectations in more detail. FULL scope means these areas are not limited to a lightweight notes store or chat-history archive: the system must connect project fundamentals, requirements, decisions, work items, implementation evidence, tests, operational knowledge, session handovers, external sources and historical context through traceable relationships. The detailed implementation may be incremental, but the intended product scope is the complete lifecycle.

### 1.3 Boundaries

This specification defines logical responsibilities and requirements for Project Memory. It does not by itself define or approve the complete VIBECUBATOR application architecture, user interface, database technology, indexing engine, embedding model or AI-provider integration.

The approved Masterplan remains the strategic authority. Detailed technical choices must be evaluated separately and recorded through the project's decision process, including Architecture Decision Records where appropriate.

The Project Memory is not intended to make AI-generated content authoritative merely because it has been stored. Provenance, status, review and human approval remain essential.

### 1.4 Intended Users and Contributors

The Project Memory is intended for:

- The human project owner, who retains authority over project direction and important approvals.
- Human developers and maintainers who need a reliable view of project knowledge and state.
- AI systems and specialized agents that retrieve context, analyze work, propose changes or execute explicitly assigned tasks.
- Supporting software components that validate, index, synchronize or present project information.

Different contributors may interact with the same knowledge base, but their permissions and the authority of their contributions must remain distinguishable.

## 2. Fundamental Principles

The following principles establish the conceptual foundation for the Project Memory. The detailed requirements in later sections refine these principles.

### 2.1 Persistent Project Continuity

Project knowledge must remain available beyond the lifetime of an individual conversation, AI session or development environment.

The Project Memory must preserve enough context to allow work to resume after interruptions and to allow a different human or AI contributor to understand the project's purpose, current state, relevant history and next steps.

A session ending, a change of AI provider or a long period of inactivity must not cause the project to lose its established direction or essential knowledge.

The memory should distinguish durable knowledge from time-sensitive working state and historical records. Current state must be identifiable without discarding the history needed to understand how that state was reached.

### 2.2 One Authoritative Project Record and Clear Human Authority

The Project Memory must provide a coherent and traceable representation of project knowledge. It must not create competing, silently divergent sources of truth.

In accordance with the approved Masterplan, version-controlled project documentation and source code in GitHub/Git form the authoritative project record for approved project information. Operational stores, indexes, caches and AI context packages may support access and processing, but must not silently supersede that record.

The human project owner retains final authority over project direction, fundamental requirements and important architectural or planning decisions. AI systems may analyze, recommend and prepare changes; they must not independently approve their own proposals or redefine approved project fundamentals.

Where authority or approval status is unclear, the information must be treated as unresolved and surfaced for review rather than guessed.

### 2.3 AI- and Provider-Independent Collaboration

The Project Memory must be usable by different AI systems, models, providers and specialized agents without making project continuity dependent on one particular service.

Contributors should receive task-relevant context in a consistent, structured form and should return findings and proposed changes in a form that can be evaluated and traced.

An AI system's identity, provider or apparent confidence does not make its output authoritative. Contributions must remain attributable where possible and must be evaluated against evidence, requirements and approved decisions before they are accepted as persistent approved knowledge.

The Project Memory should support collaboration between multiple contributors while preserving the distinction between independent contributions, consolidated proposals and approved project knowledge.

### 2.4 Provenance, Traceability and Verifiable State

Important project information must retain its origin and, where available, references to the source from which it was derived. This may include repository paths, commits, requirement or task identifiers, session references, external URLs and timestamps.

Changes to important knowledge must be traceable. A reviewer should be able to understand what changed, why it changed, who or what proposed the change, what evidence supports it and whether it was approved.

Statements about implementation and verification must reflect observable evidence. A proposal must not be represented as implemented; an implementation must not be represented as tested or verified unless the relevant checks were actually performed and their results recorded.

Where evidence is missing, incomplete or uncertain, that limitation must be explicit.

### 2.5 Controlled Knowledge Lifecycle and Human Review

Project knowledge must be managed through an explicit lifecycle rather than treated as an undifferentiated collection of notes.

New information may be proposed, reviewed, approved, superseded, deprecated, rejected or archived as appropriate to its category. Temporary working information and AI-generated suggestions must not silently become approved persistent knowledge.

Changes that affect approved requirements, project fundamentals, architecture or strategic direction require the appropriate human review and approval. Routine factual corrections and maintenance may follow documented governance rules, but must remain traceable.

Conflicts, uncertainty and missing evidence must be exposed rather than silently resolved by an AI system. Previous approved states and their history must remain recoverable in accordance with the controlled-evolution rules defined below.

The approved operating model is `AUTONOMOUS`: AI agents should be able to carry out assigned work end-to-end within an explicitly approved task scope, including analysis, planning, implementation, routine corrections, testing and evidence collection. Autonomy is bounded by approved requirements, permissions, budgets, security constraints, acceptance criteria and stop conditions. It does not grant agents authority to approve their own changes to project fundamentals, requirements, architecture, security policy, scope or other reserved decisions.


### 2.9 Bounded Autonomous AI Execution — APPROVED

The autonomy level `AUTONOMOUS` was approved by the project owner on 2026-11-20. This approval defines the target operating model; it is not an authorization for an agent to act outside the permissions and task scope actually granted in a given environment.

Within an approved task, an AI agent should be able to independently:

- Inspect relevant project context and evidence, identify dependencies and formulate an execution plan.
- Make routine, task-scoped and reversible changes to code, tests and documentation.
- Run available checks, diagnose failures, iterate and collect verifiable evidence.
- Update task progress, working state and handover information.
- Prepare a concise completion report describing changes, test results, limitations and remaining risks.

Autonomous execution must remain within explicit task boundaries: approved objective, affected areas, permitted actions, acceptance criteria, resource/time limits, data-access permissions and stop conditions. Agents must stop and request human direction when scope is ambiguous or exceeded, evidence conflicts with approved requirements, security/privacy risk is elevated, destructive or externally consequential action is required, or a reserved decision is encountered.

The following remain human-reserved unless the owner explicitly establishes a narrower, documented delegation policy: changing project vision or scope; approving or changing fundamental requirements; approving architecture or technology decisions; changing security, privacy or access policy; accepting material cost, legal, safety or irreversible risks; and granting an agent new permissions. An agent must never approve its own proposal or mark a human approval as granted.

Routine execution within a previously approved task may proceed without per-edit approval. Changes and outcomes must nevertheless be traceable, reviewable and reversible where practical. Where repository policy or the execution environment requires pull requests, protected branches or other controls, those controls remain binding. A successful test run is evidence of the checks performed, not automatic approval of the change.

`AUTONOMOUS` therefore means maximum delegated execution inside approved boundaries — not unrestricted self-direction, self-authorization or exemption from governance.

2.6 Controlled Evolution

The Project Memory must evolve in a controlled and traceable manner.

Information must never be modified, replaced or deleted without considering its origin, relevance and potential impact.

Changes to persistent project knowledge must follow defined rules.

The system must distinguish between:

Adding new information.
Updating existing information.
Correcting incorrect information.
Marking information as outdated.
Resolving conflicting information.
Archiving information that is no longer relevant.

Important changes must remain traceable through version history.

2.7 Separation of Knowledge and Working State

The Project Memory must distinguish between persistent project knowledge and temporary working information.

Not every piece of information generated during a development session deserves permanent storage.

The system must prevent temporary assumptions, incomplete ideas or intermediate results from becoming permanent project knowledge without evaluation.

2.8 Structured but Technology Independent

The Project Memory must use structured information that can be processed by different AI systems and software components.

However, the specification must not mandate a particular database, indexing engine, embedding model or search technology.

The logical structure and requirements must remain independent of the eventual technical implementation.

3. Knowledge Classification

All persistent information must be assigned to an appropriate knowledge category.

The following categories establish the initial logical classification.

3.1 Project Fundamentals

Long-term information describing the identity and purpose of the project.

Examples:

Project vision and objectives.
Core principles.
Fundamental requirements.
Project scope.
Architectural principles.

These records should change relatively rarely.

3.2 Decisions

Approved decisions that influence the direction or implementation of the project.

Examples:

Architecture decisions.
Technology selections.
Approved concepts.
Rejected approaches with relevant reasoning.
Changes to previously approved decisions.

Decisions must be traceable and must not be silently overwritten.

3.3 Requirements

Functional and non-functional requirements.

Examples:

Required system capabilities.
Performance expectations.
Security requirements.
Compatibility requirements.
User experience requirements.

Requirements must have an identifiable status.

3.4 Technical Knowledge

Information about the actual technical implementation.

Examples:

System architecture.
Interfaces and dependencies.
Data structures.
Configuration principles.
Development conventions.
Known technical limitations.

Technical knowledge must be kept consistent with the actual implementation.

3.5 Operational Knowledge

Information required to work with and maintain the project.

Examples:

Development environment setup.
Build and deployment procedures.
Testing procedures.
Troubleshooting information.
Maintenance instructions.
3.6 Working State

Temporary information describing the current state of development.

Examples:

Current tasks.
Work in progress.
Open questions.
Temporary assumptions.
Unresolved problems.
Next development steps.

Working State information must be distinguishable from approved persistent knowledge.

It may be updated more frequently than other knowledge categories.

3.7 External Knowledge

Relevant information originating outside the project.

Examples:

External documentation.
Technical specifications.
Research findings.
Third-party APIs.
External architectural references.

External information must retain its source and, where possible, its retrieval date.

It must not automatically become an approved project decision.

4. Knowledge Lifecycle and Status Management

The Project Memory must support the complete lifecycle of information.

4.1 Information Status

Persistent knowledge must support the following logical statuses:

Proposed: Information has been submitted but not yet evaluated.
Approved: Information has been accepted as valid project knowledge.
Superseded: Information has been replaced by a newer version or decision.
Deprecated: Information is no longer recommended for use but remains relevant for historical purposes.
Archived: Information is retained for historical reference but is no longer part of the active knowledge base.
Rejected: Information has been evaluated and explicitly rejected.

Not every category requires every status.

4.2 Information Updates

When existing information changes, the system must:

Identify the affected information.
Determine the reason for the change.
Preserve the previous state.
Record the new information.
Update relevant references.
Make the change traceable.

Approved information must not be silently replaced by unreviewed suggestions.

4.3 Outdated Information

The system must be able to identify potentially outdated information.

Possible indicators include:

References to outdated software versions.
Superseded technical decisions.
Contradictions with newer approved documentation.
Expired external references.
Information that no longer matches the actual implementation.

Outdated information must be flagged for review.

The system must not automatically delete information solely because it appears outdated.

4.4 Contradictory Information

When conflicting information is identified, the system must:

Identify the conflicting records.
Preserve their original sources.
Determine whether the conflict is real or merely contextual.
Identify the responsible authority for resolving it.
Record the resolution and its reasoning.

If a conflict cannot be resolved reliably, it must remain explicitly marked as unresolved.

AI systems must never silently choose between conflicting approved decisions.

5. Knowledge Retrieval and Context Preparation

The Project Memory must provide relevant information to AI systems based on their current tasks.

The objective is not to provide the entire project history for every request.

Instead, the system must prepare a task-specific context containing the information necessary to work correctly.

5.1 Task-Oriented Retrieval

Knowledge retrieval should consider:

The current task.
The affected project components.
Relevant requirements.
Related approved decisions.
Technical dependencies.
Known constraints.
Relevant previous work.
Open issues.
5.2 Context Prioritization

Retrieved information should be prioritized according to:

Relevance to the current task.
Approval status.
Current validity.
Authority of the source.
Dependencies and relationships.
Recency, where relevant.

Recency alone must never determine whether information is authoritative.

An older approved architectural decision may remain more relevant than a newer unapproved suggestion.

5.3 Context Assembly

The system must be capable of assembling a structured context package for an AI work assignment.

Such a package should contain:

Task description.
Relevant project fundamentals.
Applicable requirements.
Relevant decisions.
Technical context.
Current working state.
Known constraints.
Open questions.
References to the original sources.

The context package must identify the origin of the information it contains.

5.4 Context Limitations

AI systems may have limited context windows or processing capabilities.

The Project Memory must therefore support selective retrieval and context reduction.

Information must not be removed solely because it is old or lengthy.

The system should preserve the most relevant information and provide references to additional knowledge when necessary.

6. Multi-AI Knowledge Integration

VIBECUBATOR must support collaboration between different AI systems.

Different providers, models and specialized AI agents may contribute knowledge to the same project.

However, their contributions must not automatically become authoritative project knowledge.

6.1 Independent Contributions

Each AI system must be treated as an independent contributor.

Its findings, suggestions and proposed changes must be identifiable and distinguishable from approved project knowledge.

6.2 Contribution Structure

AI-generated contributions should contain:

Originating AI system, where identifiable.
Relevant model or provider information, where available.
Development session reference.
Date and time.
Related task.
Referenced project information.
Proposed findings or changes.
Confidence or uncertainty information, where available.
6.3 Contribution Evaluation

Before contributions become persistent approved knowledge, they must be evaluated.

Evaluation should consider:

Technical correctness.
Consistency with existing decisions.
Evidence and source quality.
Completeness.
Potential contradictions.
Impact on existing requirements or architecture.
6.4 Merging Contributions

When multiple AI systems contribute to the same subject, the Project Memory must support consolidating their findings.

The consolidation process must:

Identify overlapping contributions.
Identify complementary findings.
Identify contradictions.
Preserve relevant original sources.
Produce a consolidated proposal.
Submit relevant changes for approval.

The system must not assume that agreement between multiple AI systems automatically proves correctness.

6.5 Human Oversight

Important project decisions and changes to approved project fundamentals must remain subject to human approval. This remains true under the proposed AUTONOMOUS execution model.

AI systems may analyze, recommend and prepare changes.

They must not independently redefine the authoritative project direction.

7. Knowledge Organization and Scalability

The Project Memory must remain manageable as the project grows.

A continuously expanding collection of unstructured documents is not an acceptable long-term solution.

7.1 Logical Knowledge Structure

Information must be organized through meaningful categories, relationships and references.

The logical structure must support navigation across related information without requiring users or AI systems to read every document.

7.2 Unique Identification

Important knowledge records should have stable identifiers.

These identifiers should allow information to be referenced independently of its physical storage location.

7.3 Relationships

The system should support relationships between different knowledge records.

Examples:

Requirement → Decision.
Decision → Implementation.
Implementation → Test.
Task → Related decisions.
Technical issue → Affected components.
New decision → Superseded decision.

These relationships must make dependencies and the history of project development understandable.

7.4 Searchability

The Project Memory must support multiple retrieval methods.

Potential methods include:

Full-text search.
Metadata-based filtering.
Relationship-based navigation.
Semantic search.
Task-specific retrieval.

The eventual implementation may combine several methods.

7.5 Archiving and Consolidation

The system must support periodically reviewing the knowledge base.

Possible activities include:

Identifying duplicate information.
Consolidating related records.
Archiving obsolete working information.
Reviewing outdated external references.
Identifying unresolved contradictions.
Checking broken references.

Consolidation must preserve relevant history and traceability.

8. Logical Information Model

The technical implementation may vary, but the Project Memory must support a common logical information model.

The following attributes establish the initial conceptual requirements for important knowledge records.

Attribute	Purpose
ID	Unique identifier
Title	Human-readable name
Category	Knowledge classification
Content	Actual information
Status	Current lifecycle status
Source	Origin of the information
Created At	Creation timestamp
Updated At	Last modification timestamp
Version	Record version
Author	Originating contributor
Related Records	References to related knowledge
Validity	Information validity or applicable period

Not every attribute must be mandatory for every record.

Additional metadata may be introduced when required by specific knowledge categories.

The logical model must remain extensible.

8.1 Source References

Where possible, knowledge records must reference their original location.

Examples include:

GitHub file paths.
Document identifiers.
Git commit hashes.
Session identifiers.
External URLs.
Task identifiers.
8.2 Versioning

Changes to important knowledge records must be versioned.

The system must be able to reconstruct previous states and identify when and why changes occurred.

Versioning must be compatible with the project's existing Git-based documentation workflow.

9. Security and Access Control

The Project Memory may contain sensitive project information.

Its design must therefore consider security from the beginning.

9.1 Access Control

The system should support differentiated permissions for:

Reading project knowledge.
Proposing changes.
Approving changes.
Modifying approved information.
Archiving information.
9.2 Data Integrity

The system must protect persistent knowledge against unauthorized or accidental modification.

9.3 External AI Systems

When project knowledge is provided to external AI services, the system must respect the project's configured data access and security policies.

Only information necessary for the respective task should be provided.

9.4 Auditability

Important modifications must be traceable.

The system should provide sufficient information to reconstruct relevant changes and their origins.

10. Technical Implementation Principles

This specification defines logical requirements rather than a final technical architecture.

The eventual implementation must satisfy the following principles:

GitHub remains the authoritative source for approved human-readable project documentation.
Structured knowledge must be derivable from or traceable to authoritative project information.
Search indexes and caches must be reproducible.
Technical storage solutions must not create competing authoritative sources.
Different AI providers must be able to access the Project Memory through provider-independent interfaces.
The system must support incremental implementation.
The architecture must remain extensible.

Potential implementation technologies may be evaluated separately.

No specific database, vector database, search engine, embedding model or API architecture is mandated by this specification.

11. Minimum Functional Requirements

The following capabilities define the minimum functional expectations for a future Project Memory implementation.

The system must be able to:

Store and retrieve structured project knowledge.
Distinguish approved knowledge from temporary working information.
Maintain source references and version history.
Identify potentially outdated information.
Detect and expose conflicting information.
Retrieve task-relevant knowledge.
Assemble structured context packages for AI systems.
Accept contributions from different AI providers.
Consolidate and evaluate multiple contributions.
Preserve the authoritative status of approved project documentation.
Support archiving and knowledge maintenance.
Protect project knowledge against unauthorized changes.

These requirements establish the functional baseline for subsequent technical planning.

12. Acceptance Criteria

The Project Memory Specification can be considered sufficiently defined when the following conditions are met:

The distinction between persistent knowledge and temporary working state is clear.
Knowledge categories and lifecycle statuses are defined.
The authority of approved GitHub documentation is established.
The handling of outdated and contradictory information is specified.
Task-oriented knowledge retrieval is defined.
Multi-AI contributions and their consolidation are addressed.
Traceability and versioning requirements are established.
Scalability and knowledge maintenance are considered.
Security and access control requirements are documented.
The specification does not unnecessarily restrict future technical implementation.
13. Future Extensions

The following subjects may require additional specifications during implementation:

Detailed knowledge schemas.
Metadata standards.
Retrieval and ranking algorithms.
Semantic indexing.
Context assembly strategies.
AI provider integration.
Automated knowledge validation.
Knowledge lifecycle automation.
Access control implementation.
Monitoring and quality assurance.

These topics are intentionally not fully specified here.

They should be addressed when the corresponding implementation requirements become concrete.

14. Document Governance

This document is part of the authoritative VIBECUBATOR project documentation.

Changes to this specification must follow the project's documentation governance rules.

The document itself must be version-controlled.

Any approved changes must be traceable and must preserve the history of previous versions.

Document Status: Draft – Pending Approval (owner feedback incorporated as unapproved proposals)

Version: 1.1-proposal

Proposed changes: FULL Project Memory scope and AUTONOMOUS bounded AI execution, based on owner feedback dated 2026-11-20.

Next Step: Owner review, revision and explicit approval or rejection of the reconstructed opening and incorporated scope/autonomy proposals.
