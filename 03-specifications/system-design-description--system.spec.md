# System design description specification

## Identity and selection

- **Specification ID:** `SYSTEM-DESIGN-DESCRIPTION@system`.
- **Purpose:** Define how a bounded system or subsystem is to be realized and integrated at the design maturity claimed, including elements, allocations, behavior, interfaces, physical or deployment constraints, and rationale.
- **Intended readers:** System and subsystem designers, hardware and software leads, interface and integration engineers, implementers, maintainers, and technical reviewers.
- **Decision or action supported:** Implement or refine the system design, coordinate element and interface ownership, and assess whether the proposed realization carries its allocated project requirements and constraints.
- **Use when:** A whole system or subsystem needs a realizable design across its relevant physical, software, human, and enabling elements.
- **Scope boundaries:** Describe the realization of the bounded system or subsystem at the stated maturity. Identify allocated obligations and controlled interface parameters by their project record and edition, without creating conflicting copies.

## Authoring inputs and unresolved facts

Obtain the system boundary; actual project requirements and constraints or a clearly identified provisional basis; architecture and interface decisions if they exist; element responsibilities and allocations; relevant physical and logical models, drawings, deployment arrangements, and configurations; behavior and operating conditions; and safety, security, support, integration, and verification concerns. Inspect the controlled editions of referenced project design data.

If an allocation, design parameter, interface owner, feasibility assumption, or configuration is unknown, state its impact on implementation or integration and the next resolving action and actual owner if assigned. Label candidate solutions and unapproved changes as proposed. State build readiness, implemented configuration, verification evidence, or formal baseline approval only when established by actual project records or decisions. Identify controlled requirements and interface parameters by their project record and edition, without creating conflicting copies. Omit domain-specific physical details only after assessing their applicability.

## Finished-document contract

- **Title:** Name the system or subsystem and identify the document as its system design description.
- **Frontmatter:** None. Begin with the GFM title. Design scope and maturity are body content.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Establish scope and project design basis before decomposition; describe interfaces and behavior after elements; end with integration, design rationale, and limitations. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Scope, maturity, and design basis | Required | Identify the system boundary, intended configuration or product position, design maturity, project requirements and constraints, inherited architectural choices, and controlled models or drawings with their applicable editions. Distinguish an approved baseline from a candidate basis. |
| Elements and allocation | Required | Define the system decomposition and responsibility of each significant element, including human, hardware, software, or enabling elements where they carry system behavior. Show which project requirements, constraints, or design decisions each element is allocated to carry, and how cross-element resources or functions are allocated. Identify controlled requirement statements by project record, identity, and edition when available, without copying their wording. |
| Interfaces and integration | Required | Describe material internal and external connections, direction and ownership, compatibility assumptions, and the intended integration sequence or dependency. Give the implementation parameters needed at the stated design maturity. Cite any actual project interface record that controls these parameters, by identity and edition, without creating a conflicting copy. Label parameters proposed here as realization intent and state their decision status. |
| System behavior and constraints | Required | Explain how elements cooperate across relevant modes, states, timing, resource limits, failure or degraded conditions, and environmental conditions. Include applicable physical, deployment, data, safety, security, maintainability, and support constraints; state why an expected category is inapplicable when that omission could affect integration. |
| Realization and design rationale | Required | Give enough build-to, buy-to, configure-to, or implement-to direction for the claimed maturity, with controlled project artifact editions when available. Explain consequential design choices, evaluated constraints and alternatives, and expected feasibility basis. Identify the scope and limitations of any supporting analysis or prototype observation. |
| Integration and open design issues | Required | State how the elements are expected to be brought together and which intended checks would address allocated project requirements and constraints. Describe intended checks by their conditions and expected observations, without assigning execution results. State which interfaces or margins remain uncertain and what changes would affect allocations or controlled project records. Link actual test or review evidence only when it exists, without copying its outcome. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Design scope | One coherent system or subsystem realization per document. | State included and external elements, lifecycle or design maturity, and applicable configuration. A provisional design is not labeled a completed build definition. |
| Design basis | At least one real project requirement, constraint, or recorded design decision relevant to the scope. | Identify its project origin or state that the proposed basis remains to be agreed. Cite the source obligation without creating a conflicting copy or silently rewriting it as a design decision. |
| Design element | One or more identifiable, responsibility-bearing elements. | For each, give identity, role, parent when relevant, key realization characteristics, project design basis, interfaces, and significant rationale. A support or integration element may be justified by a design constraint or derived need rather than a fabricated one-to-one requirement ID. Decomposition must be acyclic. |
| Interface or exchange | Each connection material to integration or system behavior. | Name endpoints, direction, medium or exchanged item, limits and compatible editions where known, and responsible party. Identify any project record controlling the interface by identity and edition. Label a limit proposed here as design intent and state its decision status. |
| Behavior and resource rule | Each mode, transition, limit, fault response, or shared resource rule that materially affects design. | State conditions, expected behavior and allocated responsibility; use units and tolerances for meaningful numeric limits. Distinguish expected performance from an observed result. |
| Realization artifact | Each project drawing, model, configuration, or other artifact that controls a design detail. | Identify its edition and the design detail it controls. A hash or native file is included only when it exists and is needed to bind exact content; do not invent one. |

Use a decomposition diagram and element-allocation table when they clarify a nontrivial system. Use interface tables, state or sequence diagrams, and physical or deployment views where needed to make interactions or constraints implementable. Prose MAY suffice for a small, simple subsystem, but a diagram cannot replace the explicit limits, responsibilities, or rationale. Identify separately maintained project design artifacts by version and precedence for the affected detail.

## Quality criteria

- Allocated project requirements, constraints, and consequential derived needs can be followed to responsible elements, interfaces, and intended checks; unexplained elements and uncovered obligations are visible.
- Decomposition, interface ownership, behavior, resource assumptions, and integration order are mutually consistent at the stated design maturity.
- Physical and operational conditions that affect realization, support, safety, or security are addressed proportionately, without forcing hardware-specific fields onto an inapplicable system.
- Design decisions and parameters carry their actual proposed or approved status. Feasibility projections identify their assumptions; any implemented configuration or observed verification claim identifies the actual configuration and supporting evidence.
- The description is detailed enough to coordinate the next implementation or integration step, with unresolved parameters and their effects visible. Intended checks state conditions and expected observations without assigning `pass`, `fail`, `inconclusive`, or `not-run`.
