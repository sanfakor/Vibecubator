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

Important project decisions and changes to approved project fundamentals must remain subject to human approval.

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

Document Status: Draft – Pending Approval

Version: 1.0

Next Step: Review and approval of PROJECT_MEMORY_SPECIFICATION.md
