---
title: "Configuration management plan specification"
description: >-
  Defines the authoring contract for project-specific configuration management plans assigning controlled item identification, baselining strategies, change and exception routing, status accounting, integrity audits, tooling, supplier configuration duties, retention rules, and milestones to a defined product, service, or lifecycle effort. Translates organizational configuration obligations into concrete project authority, schedules, deliverables, baseline release criteria, and review checkpoints before controlled configurations or baselines are established.
topics:
  - "planning"
  - "configuration-management"
  - "configuration-management-plan"
  - "baseline-strategy"
  - "change-control"
  - "status-accounting"
  - "supplier-configuration"
  - "integrity-audits"
use_when:
  - "A project needs to assign configuration management responsibilities, tools, baseline milestones, and supplier rules for a bounded scope."
  - "A configuration lead is planning item classes, change routes, integrity checks, and retention timing before project execution."
  - "A reviewer is checking whether project configuration authority and baseline release criteria are concretely defined."
not_for:
  - "Setting organization-wide mandatory configuration direction, which belongs in a configuration management policy."
  - "Defining a reusable cross-project workflow without project schedules, which belongs in a configuration management lifecycle process."
  - "Listing live controlled items or recording an established baseline snapshot, which belong in control registers or baseline records."
---

# Configuration management plan specification

## Identity and selection

- **Specification ID:** `CONFIGURATION-MANAGEMENT-PLAN@core`.
- **Purpose:** Plan project-specific identification, baselining, change control, status accounting, integrity checks, and retention of controlled configurations.
- **Intended readers:** Configuration and engineering leads, item and change owners, suppliers, quality or audit roles, project managers, and release authorities.
- **Decision or action supported:** Determine which project items and states require control, how a later change or discrepancy will be decided and recorded, and which criteria and decision roles control later use or release of a baseline.
- **Use when:** A project must assign configuration-management work, authority, tools, deliverables, and timing to its products, services, or lifecycle stages.
- **Scope boundaries:** Cover project-specific configuration-management work, decision rights, resources, records, and milestones for the selected product, service, or lifecycle stages at planning depth.

## Authoring inputs and unresolved facts

Obtain the product or service boundary, lifecycle, and configurations in scope; supplied project configuration requirements and the needs or decisions establishing them; candidate item classes; existing repositories and identifier rules; baseline and release decision authorities; internal change and emergency-change rules; engineering, quality, operations, and supplier interfaces; tools and access rights; needed status, integrity, audit, archival, and retention records; and project milestones. Use supplied supplier agreements to establish deliverables, data rights, change duties, and permitted oversight; mark any additional proposed term for negotiation.

For an unknown item boundary, authority, schedule, tool, or project control criterion, state the gap, its consequence, resolving action, and actual owner if assigned. Mark a proposed baseline class, decision gate, or supplier term as proposed. Explain why an activity or formal audit method is inapplicable and how the underlying integrity need is addressed. Missing item-scope or change authority prevents a claim that controlled work is ready to start. Keep planned baseline establishment, audits, deviation decisions, and releases distinct from actual approvals, checks, decisions, and observed configuration states; do not invent those facts.

## Finished-document contract

- **Title:** Name the project or controlled product and its configuration management plan.
- **Frontmatter:** Required. Begin with a YAML 1.2 Semantic-Discovery frontmatter block delimited by `---` lines containing `title`, `description` (60 to 140 neutral retrieval words), `topics` (3 to 12 concrete lowercase kebab-case terms), `use_when` (2 to 6 neutral task conditions), and conditional `not_for` (1 to 5 grounded exclusions, omitted when empty), followed by the GFM H1 title. Exclude internal IDs, version strings, hashes, filesystem paths, build metadata, and unresolved template delimiters from frontmatter values. Applicability and authority belong in the body. Governing source: Collection Semantic-Discovery Frontmatter contract.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. Omit it for internal documents unless a specific project policy requires explicit negative attestation. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Define scope, authority, and item selection before baseline and change rules; follow with accounting, integrity, interfaces, and planned milestones. Heading wording may vary.
- **Presentation:** Scale sections, tables, and schedules to the bounded effort without adding empty chapters for inapplicable concerns. Required roles may share paragraphs, lists, or compact tables while keeping planned scope, responsibilities, criteria, dependencies, and open gaps clearly separated from completed results.

| Projection | Title and metadata ownership | Syntax and source authority |
| --- | --- | --- |
| Configuration management plan (standalone) | Begin with the mandatory 5-key Semantic-Discovery YAML frontmatter followed by one scope-specific H1. Plan scope, baseline assumptions, ownership, and readiness criteria remain body content, inheriting corpus-level changelog/VCS versioning, declared default maintainer, and external specification provenance when governed in a unified operational corpus. | Use GFM prose, structured tables, or dependency diagrams referencing controlling requirements, baselines, and schedules by edition and locator. Planned commitments remain distinct from execution evidence; baseline or scope changes require plan reassessment. |

| Section role | Status and inclusion condition | Content obligation |
| --- | --- | --- |
| Configuration scope and authority | Required | Define controlled product or service, lifecycle and item classes, exclusions, project configuration requirements with their establishing needs or decisions, accountable CM role, baseline and change decision rights, separation or escalation of conflicting duties, and interfaces with engineering, assurance, release, and operations. Define terms such as item, baseline, revision, release, deviation, and waiver where local usage could change a decision. |
| Identification and baseline strategy | Required | State criteria for selecting and naming configuration items; how versions and relationships are identified; where the authoritative item information resides; which baseline types are needed; how candidate, approved, effective, and observed states are distinguished; and how baseline establishment, protection, and effectivity are decided and evidenced. |
| Change and exception control | Required | Plan submission, impact assessment, affected-party review, the authority that may later authorize the change, implementation, the planned check that implementation matches the decision, baseline update, and closure for ordinary changes. Define urgent change limits and reconciliation if an urgent route is allowed. State how deviations, waivers, unauthorized changes, and approved-versus-actual discrepancies are contained and decided. |
| Status accounting and integrity | Required | Define how item versions, approved baselines, change decisions, actual implementation, deviations, and releases remain linked and queryable; how records and artifacts are protected; and which checks compare controlled information with actual state. Define formal functional or physical audits only when the product scope or an established project requirement calls for them; state their criteria. |
| Resources, interfaces, and supplier control | Required | Assign responsible roles, required tool or repository access, planned records, and communications with technical, quality, operations, and project roles. State supplier deliverables, data rights, assigned configuration duties, and permitted oversight explicitly for the supplied scope and agreements; expose gaps for negotiation. |
| Milestones, retention, and plan upkeep | Required | Tie baseline establishment, change-board or review events, audits when applicable, status reports, and configuration deliverables to project milestones. Define the project's transfer, archival, retention, and decontrol criteria and decision roles for controlled information at migration or retirement; state plan review and change triggers. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
| --- | --- | --- |
| Controlled item class | One or more classes or an explicit selection rule pending classification. | Identify selection criterion, owner, identifier/version rule, authoritative location, and relationships to other items. Do not populate a fictional register. |
| Baseline rule | At least one rule for a controlled state or set. | Identify contents or selection rule, approving authority, effective point, protection method, permitted changes, and expected establishment record. State the evidence and authorization required for approval and release. |
| Change route | One normal route, plus a conditional urgent route if permitted. | Separate proposal, impact, decision, execution, verification, accounting, and closure, with actual decision roles and response to rejection or unresolved discrepancies. |
| Status account | One connected model of item, revision, baseline, request, decision, implemented state, and release. | Make the authoritative source and update responsibility clear; a request or approval does not prove implementation. |
| Integrity check or audit | One or more planned checks proportionate to scope. | State trigger or frequency, compared states or criteria, reviewer, expected evidence, discrepancy route, and recheck. Include a formal functional or physical audit only when the product scope or an established project requirement calls for it. |
| Supplier configuration duty | Conditional when supplied items or services are in scope. | Tie required identifiers, baseline information, change notice, records, access, and receiving criteria to actual or explicitly proposed terms; the plan cannot create contract rights. |

Use prose for scope and decision rights, a change-state flow where transitions or exceptions are complex, and a table for item classes, baselines, or milestones when several must be compared. Identify actual item and baseline record locators and the states or relationships they supply when those records inform planning.

## Quality criteria

- Item selection, identifier rules, baseline authority, and change authority are explicit enough to tell controlled state from an uncontrolled candidate.
- Proposed, authorized, implemented, checked, baselined, and released states remain distinct, including for urgent changes; each transition has explicit criteria and a decision or recording role.
- Status accounting links decisions to affected items and observed state, with a route to contain and reconcile mismatches.
- Integrity and audit plans identify criteria, expected evidence, discrepancy handling, and recheck; each selected formal audit has a stated product-scope or project-requirement basis.
- Supplier duties, data rights, schedules, and retention follow real agreements and project constraints.
