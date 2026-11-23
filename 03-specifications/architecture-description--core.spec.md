---
title: "Architecture description specification"
description: >-
  Defines the authoring contract for architecture descriptions explaining the organizing structure, behavior, interactions, allocations, and governing technical decisions of a system or software entity through explicit viewpoints tailored to stakeholder concerns. Covers entity scope and design basis, stakeholder concerns and architectural drivers, viewpoint selection, architecture views and models, cross-view correspondence and consistency checks, key decisions, and architectural limitations or change implications while keeping build-to and code-level implementation details outside architectural scope.
topics:
  - "specifications"
  - "architecture-and-design"
  - "systems-engineering"
  - "architecture-description"
  - "architectural-views"
  - "viewpoints"
  - "stakeholder-concerns"
  - "cross-view-consistency"
use_when:
  - "An architect needs to document cross-cutting structure, behavior, allocations, and tradeoffs across explicit stakeholder viewpoints."
  - "A team is evaluating whether a proposed architecture satisfies its drivers and checking cross-view correspondence."
  - "A reviewer is assessing architectural change impact without diving into low-level build-to or module implementation details."
not_for:
  - "Detailed module, data structure, algorithm, or runtime implementation design, which belongs in software or system design descriptions."
  - "Recording a single isolated technical choice and its alternatives, which belongs in an architecture decision record."
  - "Stating testable system or software obligations, which belong in requirements specifications."
---

# Architecture description specification

## Identity and selection

- **Specification ID:** `ARCHITECTURE-DESCRIPTION@core`.
- **Purpose:** Explain the organizing structure, behavior, relationships, and governing choices of a system or software entity from the views needed to address stakeholder concerns.
- **Intended readers:** Stakeholders with architecture concerns, architects, system and software designers, integrators, technical reviewers, and change authorities.
- **Decision or action supported:** Evaluate whether the proposed architecture addresses its drivers, coordinate detailed design across boundaries, and understand the impact of architectural change.
- **Use when:** Cross-cutting structure, allocation, interactions, or quality tradeoffs need a coherent architecture-level account with explicit viewpoints and rationale.
- **Scope boundaries:** Describe major structure, behavior, allocations, interfaces, and architectural choices at the abstraction level needed to address the stated concerns. Keep build-to and code-level detail outside that level.

## Authoring inputs and unresolved facts

Obtain the entity of interest and its environment; relevant stakeholder roles and concerns; actual project requirements, constraints, decisions, and quality drivers; the architectural maturity and any applicable baseline; major elements and interfaces; existing models or diagrams; and the rationale for selected structures and allocations. Inspect referenced project records at the editions used for this architecture.

If a driver, boundary, allocation, relationship, or decision is unsettled, mark it as proposed or unresolved, state the consequence for affected views, and identify the next resolving action and actual owner if assigned. If two project records or views conflict, show the conflict rather than silently choosing one. Summarize requirements and controlled interface constraints as architectural drivers, with links to their identified project records and editions.

## Finished-document contract

- **Title:** Name the entity and identify the document as its architecture description.
- **Frontmatter:** Required. Begin with a YAML 1.2 Semantic-Discovery frontmatter block delimited by `---` lines containing `title`, `description` (60 to 140 neutral retrieval words), `topics` (3 to 12 concrete lowercase kebab-case terms), `use_when` (2 to 6 neutral task conditions), and conditional `not_for` (1 to 5 grounded exclusions, omitted when empty), followed by the GFM H1 title. Exclude internal IDs, version strings, hashes, filesystem paths, build metadata, and unresolved template delimiters from frontmatter values. Applicable configuration and decision state belong in the body. Governing source: Collection Semantic-Discovery Frontmatter contract.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. Omit it for internal documents unless a specific project policy requires explicit negative attestation. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Identify the entity and drivers before presenting views; state correspondences, rationale, and unresolved issues after the views. Heading wording may vary.
- **Presentation:** Scale prose, tables, schemas, or diagrams to the subject's complexity and declared maturity without forcing empty administrative chapters. Required roles may share sections while keeping authoritative identifiers, obligations, constraints, interfaces, and explicit gaps directly retrievable.

| Projection | Title and metadata ownership | Syntax and source authority |
| --- | --- | --- |
| Architecture description (standalone) | Begin with the mandatory 5-key Semantic-Discovery YAML frontmatter followed by one subject-specific H1. Subject identity, applicable version or maturity, scope boundaries, and ownership remain body content, inheriting corpus-level changelog/VCS versioning, declared default maintainer, and external specification provenance when governed in a unified operational corpus. | Use GFM prose, tables, diagrams, or code blocks grounded in controlling project sources and inspected editions. External native models, schemas, or artifacts remain authoritative for their own formats; source or baseline changes require reconciliation before retaining current applicability. |

| Section role | Status and inclusion condition | Content obligation |
| --- | --- | --- |
| Entity, scope, and basis | Required | Identify the primary entity, its boundary and environment, described configuration or proposed stage, purpose and audience, actual project requirements or decisions shaping the architecture, and any applicable baseline. Cite a project requirement or decision by identity and edition when that record exists; summarize its architectural effect. State each driver's origin and established, proposed, or unresolved basis. State what the description excludes. |
| Stakeholders, concerns, and drivers | Required | Identify the roles whose concerns shape the architecture; explain the material concerns and functional, quality, interface, operational, or lifecycle drivers. Distinguish binding constraints from design preferences. |
| Viewpoint choices | Required | For each chosen viewpoint, state the concern it addresses, intended audience, interpretation rules and notation or modeling convention if used. Explain any material concern that the selected views do not yet address. A custom viewpoint may be described directly here. |
| Architecture views | Required | Present one or more views that together show the relevant major elements and their responsibilities, relationships, interactions, allocations, and boundaries. Include structural, behavioral, information, deployment, or other views according to the actual concerns; do not impose every view category on every architecture. Describe interfaces by their architectural role, boundary, interaction direction, and relevant constraints; link to established project interface records for controlled details. Identify the scope and applicable edition of any referenced project model or diagram. |
| Cross-view consistency and decisions | Required | Explain how shared elements, interfaces, allocations, and constraints correspond across views. State significant choices and rationale, material alternatives or tradeoffs actually considered, and the impact on stated drivers. Identify inconsistent or unassessed relationships rather than implying consistency from matching names. Limit each correspondence assessment to the identified views and consistency rule. |
| Limitations and change implications | Required | State unresolved concerns, model limits, assumptions, risks, and changes that would affect requirements, interfaces, detailed designs, or other views. Identify the actual decision route when one exists. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
| --- | --- | --- |
| Entity of interest | One primary coherent architecture scope; related entities may appear as context or nested subjects. | Give a stable name, boundary, environment, and applicable configuration or maturity. Do not use a collection of unrelated systems as one architecture merely to fill a view. |
| Concern and driver | Each material stakeholder question, obligation, or quality tradeoff the architecture must address. | Attribute to an actual stakeholder role, project need, requirement, or decision. State the concern and its architectural implications separately from the chosen solution. Each material concern must be covered by a view or listed as unresolved. |
| Viewpoint | One or more conventions for constructing and reading the selected views. | Link each to its concerns, audience, and interpretation rules. Define any model-kind identifier, notation, symbols, and relationship conventions needed to interpret the view. |
| View or model | One or more actual architecture representations. | Identify the viewpoint, represented entity and scope, major elements and relations, and version or locator when external. A view may use prose, a table, a diagram, or a versioned model; a separate native file is not mandatory. |
| Element and relationship | Each major responsibility-bearing element and consequential connection shown by a view. | Explain responsibilities and interaction or allocation direction at the architectural level. Keep shared names consistent across views. Link to established project requirement or interface records by identity and edition, summarizing their architectural implications without repeating their controlled wording or detailed parameters. |
| Decision and correspondence | Each material architectural choice and each cross-view relation needed to judge consistency. | Give rationale and affected drivers. State a consistency rule and its assessment when one is used; do not require a machine-checkable predicate or invent an assessment record. When an assessment is recorded, use `not-assessed`, `consistent`, or `inconsistent` for the views compared. Matching names are not consistency. Do not record that assessment as `pass`, `fail`, `inconclusive`, `not-run`, `verified`, or `validated`. |

Use diagrams for topology, flows, or deployment when spatial or interaction relationships would otherwise be hard to follow. Include a legend or interpretation rule for non-obvious notation. Tables MAY map concerns to views or compare allocations and choices. Every diagram or referenced project model used to define the architecture must identify its edition and scope; state precedence when multiple representations describe the same element.

## Quality criteria

- The views answer the named stakeholder concerns at the stated abstraction level and allow readers to identify responsibility, significant interfaces, and architectural tradeoffs.
- Shared elements, names, allocations, assumptions, and interface directions are consistent across views, or discrepancies are explicit.
- Drivers retain their project basis, structures and allocations retain their decision state, and correspondence assessments identify the views and consistency rules actually assessed.
- The description provides enough rationale and change context to assess downstream design impact without expanding into build-to or code-level detail.
