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
- **Frontmatter:** None. Begin with the GFM title. Applicable configuration and decision state belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Identify the entity and drivers before presenting views; state correspondences, rationale, and unresolved issues after the views. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Entity, scope, and basis | Required | Identify the primary entity, its boundary and environment, described configuration or proposed stage, purpose and audience, actual project requirements or decisions shaping the architecture, and any applicable baseline. Cite a project requirement or decision by identity and edition when that record exists; summarize its architectural effect. State each driver's origin and established, proposed, or unresolved basis. State what the description excludes. |
| Stakeholders, concerns, and drivers | Required | Identify the roles whose concerns shape the architecture; explain the material concerns and functional, quality, interface, operational, or lifecycle drivers. Distinguish binding constraints from design preferences. |
| Viewpoint choices | Required | For each chosen viewpoint, state the concern it addresses, intended audience, interpretation rules and notation or modeling convention if used. Explain any material concern that the selected views do not yet address. A custom viewpoint may be described directly here. |
| Architecture views | Required | Present one or more views that together show the relevant major elements and their responsibilities, relationships, interactions, allocations, and boundaries. Include structural, behavioral, information, deployment, or other views according to the actual concerns; do not impose every view category on every architecture. Describe interfaces by their architectural role, boundary, interaction direction, and relevant constraints; link to established project interface records for controlled details. Identify the scope and applicable edition of any referenced project model or diagram. |
| Cross-view consistency and decisions | Required | Explain how shared elements, interfaces, allocations, and constraints correspond across views. State significant choices and rationale, material alternatives or tradeoffs actually considered, and the impact on stated drivers. Identify inconsistent or unassessed relationships rather than implying consistency from matching names. Limit each correspondence assessment to the identified views and consistency rule. |
| Limitations and change implications | Required | State unresolved concerns, model limits, assumptions, risks, and changes that would affect requirements, interfaces, detailed designs, or other views. Identify the actual decision route when one exists. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
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
