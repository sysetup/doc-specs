---
title: "Software maintenance plan specification"
description: >-
  Defines the authoring contract for software maintenance plans governing post-delivery support and controlled modification of defined software items while treating physical assets and operating routines solely as external dependencies. Covers maintenance scope and service commitments, takeover and team organization, issue and change intake, impact analysis and authorization, corrective, adaptive, perfective, and preventive modification workflows, regression assessment, release communication, migration and end-of-support coordination, and periodic plan review.
topics:
  - "planning"
  - "software-engineering"
  - "operations"
  - "software-maintenance"
  - "post-delivery-support"
  - "modification-control"
  - "regression-assessment"
  - "end-of-support"
use_when:
  - "A delivered software item requires a structured strategy for ongoing support, defect fixes, enhancements, regression testing, and re-release."
  - "A maintainer is defining intake triage, change authorization, support commitments, and end-of-support migration routes."
  - "A reviewer is checking whether post-delivery software modification workflows align with release and operational dependencies."
not_for:
  - "Initial development and pre-delivery software increments, which belong in a software development plan."
  - "Physical or infrastructure hardware upkeep and servicing, which belong in an asset maintenance plan."
  - "Full decommissioning and disposal execution, which belongs in a retirement and disposal plan."
---

# Software maintenance plan specification

## Identity and selection

- **Specification ID:** `SOFTWARE-MAINTENANCE-PLAN@core`.
- **Purpose:** Plan support and controlled modification of delivered software, from intake and analysis through change, regression, release, and end-of-support coordination.
- **Intended readers:** Maintainers, support and operations roles, development and security teams, suppliers, configuration managers, release decision makers, and the receiving organization.
- **Decision or action supported:** Route a reported problem or proposed enhancement to the right maintenance treatment, resources, assessment, and release or support decision.
- **Use when:** A defined software item requires a post-delivery support and modification strategy, including corrective, adaptive, perfective, or preventive work as applicable.
- **Scope boundaries:** Bound maintenance work to post-delivery software support and modification; include physical assets and operating or recovery activities only as dependencies or coordination needs.

## Authoring inputs and unresolved facts

Obtain the maintained products, supported versions and user groups, support periods and real service commitments; delivered configuration and architecture; ownership and handover state; maintenance obligations established in supplied agreements or internal project decisions; access and rights to source, dependencies, tools, build and test environments; supplier roles; intake and escalation channels; change and release authorities; regression and acceptance basis; migration and retirement constraints; and measures that the project actually uses. Identify the origin, revision, and locator of the configuration, commitments, and decisions used.

State unknown support scope, rights, commitments, or decision authority with the effect on service, resolving action, and actual owner if assigned. Label planned handover and unagreed service targets as proposals. If a maintenance category, data migration, or customer-property duty is genuinely outside scope, state the scoped reason; do not invent all four maintenance categories as active work. Essential missing source/build access or acceptance criteria must be exposed as a maintenance-readiness gap. Do not turn a planned fix, review, or release into an observed result.

## Finished-document contract

- **Title:** Identify the maintained software or service and name its software maintenance plan.
- **Frontmatter:** Required. Begin with a YAML 1.2 Semantic-Discovery frontmatter block delimited by `---` lines containing `title`, `description` (60 to 140 neutral retrieval words), `topics` (3 to 12 concrete lowercase kebab-case terms), `use_when` (2 to 6 neutral task conditions), and conditional `not_for` (1 to 5 grounded exclusions, omitted when empty), followed by the GFM H1 title. Exclude internal IDs, version strings, hashes, filesystem paths, build metadata, and unresolved template delimiters from frontmatter values. Support scope and plan state belong in the body. Governing source: Collection Semantic-Discovery Frontmatter contract.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. Omit it for internal documents unless a specific project policy requires explicit negative attestation. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Define support responsibility and enabling environment before intake and modification; present assessment and release before migration, end-of-support, and feedback. Exact headings may vary.
- **Presentation:** Scale sections, tables, and schedules to the bounded effort without adding empty chapters for inapplicable concerns. Required roles may share paragraphs, lists, or compact tables while keeping planned scope, responsibilities, criteria, dependencies, and open gaps clearly separated from completed results.

| Projection | Title and metadata ownership | Syntax and source authority |
| --- | --- | --- |
| Software maintenance plan (standalone) | Begin with the mandatory 5-key Semantic-Discovery YAML frontmatter followed by one scope-specific H1. Plan scope, baseline assumptions, ownership, and readiness criteria remain body content, inheriting corpus-level changelog/VCS versioning, declared default maintainer, and external specification provenance when governed in a unified operational corpus. | Use GFM prose, structured tables, or dependency diagrams referencing controlling requirements, baselines, and schedules by edition and locator. Planned commitments remain distinct from execution evidence; baseline or scope changes require plan reassessment. |

| Section role | Status and inclusion condition | Content obligation |
| --- | --- | --- |
| Maintenance scope and commitments | Required | Name software, supported versions and users, support period and boundaries, applicable maintenance categories, established maintenance obligations and their agreement or internal project-decision basis, established response or repair commitments, exclusions, and interfaces to operations, contingency, and physical asset maintenance. Identify unagreed targets as unresolved rather than commitments. |
| Organization and takeover | Required | Identify maintainer, developer, supplier, acquirer, support, and decision roles as applicable; how responsibility and open issues transfer; and the access, rights, repositories, tools, dependencies, environments, and knowledge needed to build and test a modified version. Distinguish planned handover from performed acceptance. |
| Intake, analysis, and authorization | Required | Define how problems, vulnerabilities, and change requests enter the queue; how they are classified, prioritized, analyzed for cause and impact, assigned, and escalated; how affected users or interfaces are identified; and who may authorize normal or urgent work. A report alone is not change approval. |
| Modification and assessment | Required | Plan controlled implementation, affected-baseline and dependency identification, review, security and compatibility checks, regression selection, retest after a check does not meet its criterion, and the evidence a later conformance decision would use. Define the route for unresolved defects or risk and the criteria, evidence, and deciding role needed for modification acceptance after implementation. |
| Release and support communication | Required | Define candidate identification, readiness checks, rollback or recovery coordination when relevant, the role that may later decide release, distribution or deployment interface, user notification, retained records, and update of supported-version information. Identify the criteria, evidence, and responsible role for deployment, release authorization, and customer acceptance separately. |
| Migration and end-of-support route | Required | Identify triggers and decision owners for version or platform migration and retirement, including compatibility, data conversion and verification, preservation, user notice, support withdrawal, and archival when applicable. Give a detailed migration or retirement method only when that work is in scope and planned. |
| Monitoring and plan review | Required | Define workload, response, repair, defect recurrence or other selected measures and their data sources; how feedback, changed dependencies or obligations, and observed failures lead to plan review. Do not invent numeric service targets or actual performance. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
| --- | --- | --- |
| Supported software scope | One bounded item or service, with one or more supported versions or an explicit version-selection rule. | State user, deployment, supplier, and lifecycle boundaries; identify any unsupported version or period without implying support was promised. |
| Maintenance category | Only categories applicable to the stated scope. | Explain how corrective, adaptive, perfective, and preventive work is classified or why a category is excluded; a label alone does not set priority or authority. |
| Service commitment | Conditional on an actual agreement or authorized internal target. | State source, affected service and period, measure, threshold, and responsible party. If no target is established, describe the decision needed without inventing one. |
| Change route | One normal route and a conditional urgent route if allowed. | Connect intake, impact and security assessment, authorization, controlled implementation, regression, candidate, release decision, and notification. Urgency does not supply authorization. |
| Modification acceptance basis | One route for each class of material change. | Identify affected configuration, criterion, assessor or receiving authority, expected evidence, and the planned response when a later check does not meet its criterion or cannot be concluded. Require assessment evidence and a decision by the assigned role before treating a modification as accepted. |
| Migration or retirement trigger | One decision route for foreseeable support-ending or compatibility change. | Define owner, affected versions and users, preservation or data handling, communication, and evidence expected when invoked. No unplanned migration procedure is required. |

Use prose for support boundaries and responsibility, a flow or decision table for intake and emergency change, and a mapping table when several versions, commitments, or suppliers differ.

## Quality criteria

- A maintainer can determine which software and users are covered, what commitments really apply, and how to obtain the controlled source and build context.
- Intake and modification routes preserve authorization, baseline identity, regression coverage, security escalation, and separate criteria, evidence, and roles for assessment and release decisions.
- Transition dependencies and rights gaps are visible rather than assumed resolved; supplier obligations do not exceed actual agreements.
- Migration and end-of-support planning addresses affected users and information without forcing fictional projects or completed events.
- Measures have a source and interpretation; planned targets are not presented as measured performance or accepted service levels.
