# System requirements specification

## Identity and selection

- **Specification ID:** `SYSTEM-REQUIREMENTS@core`.
- **Purpose:** State assessable technical obligations of a defined system of interest, including its behavior, performance, external interactions, qualities, lifecycle support, and imposed constraints.
- **Intended readers:** System owners, architects, element and interface owners, safety and security specialists, verification planners, and authorities that control the system requirements.
- **Decision or action supported:** Readers can determine what the whole system must satisfy, under which conditions, why each obligation exists, and how conformity will be assessed before allocating lower-level work.
- **Use when:** Stakeholder expectations or direct project decisions must be translated into controlled system-level obligations.
- **Scope boundaries:** State obligations of the defined system as a whole, with its external interactions and allocated responsibilities identified. Include a design constraint only when an actual project decision imposes it.

## Authoring inputs and unresolved facts

Obtain the system-of-interest boundary, applicable edition or configuration, intended functions and use scenarios, users and external systems, modes, operating and physical environments, enabling or support products, and inspected stakeholder expectations or direct project decisions. Inspect constraints established for the project, safety and security concerns, relevant interface ownership, existing controlled project requirements, and actual decisions about allocation and verification. Determine which life-cycle, human interaction, performance, reliability, maintainability, information, transport, or environmental concerns apply to this system.

For an unknown source, threshold, mode, interface boundary, constraint, or decision, record the gap, its effect on affected obligations, resolving action, and actual owner if assigned. Keep an incompletely specified or unauthorized statement visibly proposed; it MUST NOT be treated as a baselined obligation. Explain non-obvious exclusions that affect system coverage. A direct project decision may originate a system obligation without a parent requirement ID; do not invent one, a verification record, or evidence of conformity.

## Finished-document contract

- **Title:** Name the system of interest and identify the document as its system requirements specification; add edition or configuration where needed to disambiguate it.
- **Frontmatter:** None. Begin with the GFM title. System scope, content state, and authority are substantive body content.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Establish system boundary and derivation context before the authoritative requirements; put coverage, assessment, and control information after them. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| System identity, scope, and context | Required | Identify the system, document edition or other control identity, purpose, boundary, included and excluded responsibilities, external actors and systems, operating and lifecycle conditions, assumptions, dependencies, and actual requirement-set authority or proposal state. Define material terms and distinguish the system from its elements. |
| System requirements | Required | State one authoritative obligation per distinct system-level behavior, quality, interaction, or imposed constraint, with a stable ID, source, applicability, and assessable condition. Assess relevant functional, performance, capacity, human interaction, reliability, availability, maintainability, safety, security, physical/environmental, information, operational, sustainment, transport, and interface concerns. Include only applicable concerns; explain material gaps rather than creating empty categories. |
| Coverage, allocation, and verification basis | Required | Relate the system obligations to inspected stakeholder outcomes, direct project decisions, modes, constraints, and external interactions. Identify real links to element allocations or controlled project interface records when established, without duplicating their detailed obligations. State what a later verification would have to observe for each active system requirement, and identify coverage gaps or conflicts. Keep assessment conditions expressed as planned observations. |
| Authority, unresolved decisions, and change | Required | Identify who can decide derived or disputed content, the applicable set or baseline and its change route, and open issues with effects and resolution actions. Cite actual content review or approval only when it exists; distinguish those decisions from implementation, verification, stakeholder validation, and acceptance. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| System boundary | One bounded system of interest and its applicable configuration or edition. | Identify what the system controls, receives, exposes, and relies on; name external interfaces and human responsibilities needed to understand the obligations. |
| System requirement | One or more distinct obligations, each with one stable ID unique within the controlled set. | State the obligated system, required outcome or limit, and triggering/operating conditions. Use consistent normative wording. A requirement may constrain a design only when an actual project decision imposes the constraint; otherwise leave realization choices open. |
| Source and authority | At least one inspected stakeholder expectation, project decision, or documented derivation for each requirement. | Identify title/ID, edition, and locator when needed, plus the project role that can authorize derived or disputed content. A link shows origin, not automatic approval. |
| Assessment condition | One assessable condition or planned verification basis for each active requirement. | State the expected observation, operating mode, stimulus, environment, units, limits, and tolerance where relevant. Identify a method directly or link to an existing project method. An undefined threshold is an open issue. The condition does not assign `pass`, `fail`, `inconclusive`, or `not-run`. |
| Requirement content state | One truthful set state, with per-item state when items differ. | Define project vocabulary if used. A review or baseline decision concerns requirement content, not achieved system conformity, validation, or acceptance. Do not use `pass`, `fail`, `inconclusive`, `not-run`, or `verified` as a content state. |
| Rationale and priority | Rationale for a derived obligation or non-obvious constraint; priority only if used for scope decisions. | Explain necessity or tradeoff; priority does not waive an authorized obligation. |
| Allocation or interface relationship | Zero or more real links when an element, interface, or verification definition is controlled elsewhere. | Identify the master and affected side without restating its detailed requirement. If allocation or interface ownership is undecided, show the resulting gap. |
| Deferred or conflicting concern | Zero or more exclusions, later-edition obligations, conflicting sources, or undecided assumptions. | State impact on coverage, actual decision authority, and resolution route. Do not treat silence as nonapplicability. |

Use prose for context and a numbered list or compact table with meaningful ID, statement, source, applicability, state, and assessment columns for requirements. A boundary or mode diagram MAY clarify interactions, but it MUST NOT replace controlled requirement text. Group by function or concern only when it improves use; do not repeat requirements in overview fields, force a project-origin category that does not apply, or add generic document-control blocks.

## Quality criteria

- Every active obligation applies to the stated system boundary, is clear and individually assessable under explicit conditions, and has a real origin or documented derivation.
- The set covers relevant system behavior, crosscutting qualities, interfaces, operating modes, and lifecycle constraints; exclusions and unresolved safety or security concerns remain visible.
- Each obligation states an outcome or constraint at the defined system boundary. Allocation and traceability links identify the affected project records without duplicating controlled statements.
- Every active requirement has an explicit planned verification basis. Content review and baseline claims identify the actual decision and scope; assessment conditions remain planned observations.
