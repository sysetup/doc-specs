---
title: "Interface requirements document specification"
description: >-
  Defines the authoring contract for interface requirements documents stating assessable interaction obligations, limiting conditions, side responsibilities, numerical conventions, and conformity assessment bases across identified boundaries between system elements, external systems, people, or organizations. Covers decision roles, project origins, requirement content states, coverage, open interface issues, and change rules while reserving concrete realization parameters strictly for constraints imposed by established project decisions.
topics:
  - "specifications"
  - "requirements-engineering"
  - "architecture-and-design"
  - "interface-requirements"
  - "boundary-obligations"
  - "external-interfaces"
  - "side-responsibility"
  - "conformance-basis"
use_when:
  - "Internal or external system boundaries need an authoritative statement of required interactions, limits, and responsibilities before realization."
  - "An engineer is documenting testable interface obligations, numerical conventions, and open boundary issues across participating sides."
  - "A reviewer is verifying that interface obligations define what must hold at the boundary without prematurely locking unselected implementations."
not_for:
  - "Controlling agreed physical, protocol, or schema realization parameters across parties, which belongs in an interface control document."
  - "Indexing interface identifiers, criticality, and owners across a program, which belongs in an interface registry."
  - "Documenting whole-system functional behavior unrelated to boundary exchanges, which belongs in a system requirements specification."
---

# Interface requirements document specification

## Identity and selection

- **Specification ID:** `INTERFACE-REQUIREMENTS@core`.
- **Purpose:** State assessable obligations and limiting conditions at identified interfaces between system elements, external systems, people, or organizations.
- **Intended readers:** Owners of both sides of each interface, systems and interface engineers, integrators, verification planners, and authorities that control interface requirements.
- **Decision or action supported:** Each party can determine what it must provide or tolerate at the boundary, under which conditions, and what a later conformity check would have to observe.
- **Use when:** One or more related internal or external interfaces need an authoritative statement of required interactions and constraints before or alongside realization.
- **Scope boundaries:** Define obligations at identified contact or exchange boundaries. Include a required realization detail only when a supplied project requirement or recorded project decision imposes it.

## Authoring inputs and unresolved facts

Obtain each interface's actual or proposed endpoints, boundary plane or logical boundary, direction of flows, interacting parties, operating modes, environments, and supplied project system or stakeholder obligations. Identify the project need, allocation, or decision behind each obligation, with its edition and locator when one exists. Determine the decision and change roles on each side and how conflicts between project obligations or decisions are resolved. Obtain the physical, electrical, fluid, thermal, data, software, human, security, safety, timing, or other characteristics relevant to the boundary, including engineering units, reference frames, limits, and tolerances where meaningful. Identify existing controlled requirement statements so that each obligation has one controlling version and is cited consistently.

If a boundary, responsible side, project origin or deciding role, quantitative limit, reference frame, or assessment condition is unknown, record the gap, its effect, the resolving action, and the actual owner if assigned. Keep an obligation with an undecided value or cross-party conflict visibly proposed; do not claim agreement, selection of a realization, or observed conformity without the actual decision or observation. If a coordinate system or physical property has no meaning for an interface, omit it after assessing applicability rather than inventing a value.

## Finished-document contract

- **Title:** Identify the interface or bounded group of interfaces and the document as its interface requirements document; include edition or scope where needed to distinguish it.
- **Frontmatter:** Required. Begin with a YAML 1.2 Semantic-Discovery frontmatter block delimited by `---` lines containing `title`, `description` (60 to 140 neutral retrieval words), `topics` (3 to 12 concrete lowercase kebab-case terms), `use_when` (2 to 6 neutral task conditions), and conditional `not_for` (1 to 5 grounded exclusions, omitted when empty), followed by the GFM H1 title. Exclude internal IDs, version strings, hashes, filesystem paths, build metadata, and unresolved template delimiters from frontmatter values. Interface authority, precedence, and requirement state are body content. Governing source: Collection Semantic-Discovery Frontmatter contract.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. Omit it for internal documents unless a specific project policy requires explicit negative attestation. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Define scope, decision roles, and project basis first; identify each boundary and responsibility before its requirements; place coverage, unresolved decisions, and change information after the obligations. Heading wording may vary.
- **Presentation:** Scale prose, tables, schemas, or diagrams to the subject's complexity and declared maturity without forcing empty administrative chapters. Required roles may share sections while keeping authoritative identifiers, obligations, constraints, interfaces, and explicit gaps directly retrievable.

| Projection | Title and metadata ownership | Syntax and source authority |
| --- | --- | --- |
| Interface requirements document (standalone) | Begin with the mandatory 5-key Semantic-Discovery YAML frontmatter followed by one subject-specific H1. Subject identity, applicable version or maturity, scope boundaries, and ownership remain body content, inheriting corpus-level changelog/VCS versioning, declared default maintainer, and external specification provenance when governed in a unified operational corpus. | Use GFM prose, tables, diagrams, or code blocks grounded in controlling project sources and inspected editions. External native models, schemas, or artifacts remain authoritative for their own formats; source or baseline changes require reconciliation before retaining current applicability. |

| Section role | Status and inclusion condition | Content obligation |
| --- | --- | --- |
| Purpose, scope, decision roles, and project basis | Required | Identify document edition or other control identity, interface set, both sides and their responsible roles, purpose, applicable configuration and conditions, exclusions, and the roles that decide requirement content. Identify supplied project needs, allocations, and decisions with editions or locators and the scope of each obligation they support. State how conflicting obligations or party decisions are resolved and who can decide the disputed content. |
| Interface boundaries and conventions | Required | For each interface, give a stable identity, endpoints, boundary or plane, flow direction, category, and responsibility on each side. Define engineering units, reference frames, coordinate systems, tolerances, and conversion rules when needed to interpret numerical obligations. Describe relevant modes, environments, and assumptions without duplicating obligation text. |
| Interface requirements | Required | State one authoritative, individually assessable boundary obligation per distinct required interaction or limit. Identify its interface, obligated side or parties, origin, content state, applicability conditions, and the observation a later verification would have to make. Include only relevant functional, structural, mechanical, fluid, thermal, electrical, signal, software or data, environmental, human, safety, and security concerns. State compatible values or ranges on both sides where the interaction demands them. Do not assign a verification result. |
| Coverage, open issues, and control | Required | Relate the obligations to supplied project system or stakeholder requirements and to both sides of each interface by citation, keeping each controlling statement and edition unambiguous. Identify conflicts, missing counterpart obligations, undecided limits, and excluded concerns with effects and resolution routes. State how the applicable requirement set is identified and changed across parties; cite actual agreement or approval only for the wording, edition, and scope decided. Identify any cited observation of conformity by its actual record and assessed configuration. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
| --- | --- | --- |
| Interface identity and boundary | One or more interfaces, each with one stable ID unique within the controlled set. | Identify endpoints, direction, exchange or contact type, and the plane or logical point where responsibility changes. Use one consistent identity if another real record refers to the same interface. |
| Side responsibility | Both sides of each interface, plus any custodian or integrator when relevant. | State which party provides, receives, tolerates, or controls each affected property, and any responsibility for a later check. A common requirement may name both sides. Do not leave a compatibility obligation with no responsible party. |
| Interface requirement | One or more distinct obligations, each with one stable requirement ID. | State one boundary behavior, transfer, property, limit, or compatibility condition, with obligated side, mode, stimulus, and expected response where relevant. Use consistent obligation wording that makes the required behavior or limit explicit. A required range, unit, or compatibility condition is the obligation. Require a particular connector, pin assignment, message schema, or protocol configuration only when a supplied project requirement or recorded project decision imposes that realization. |
| Project origin and content decision role | At least one supplied project origin or documented derivation per requirement. | Identify the actual system requirement, stakeholder requirement, need, allocation, internal mandate, or decision with edition and locator when needed, and who may approve a derived or disputed value. Cite the project basis and explain any derivation. Maintain one controlling statement for each obligation. Establish bilateral agreement from actual decisions of both responsible sides. |
| Numerical convention | Conditional for every numerical boundary property. | State units, allowable range or limit, tolerance, direction or sign convention, and reference frame and conversion when needed. Ensure counterpart values use compatible conventions. An unspecified tolerance cannot be guessed from an example. |
| Assessment basis | One assessable basis per active requirement. | State the observation a later verification would have to make, including conditions, units, and limits where they matter. A direct inspection, analysis, demonstration, or test basis may be stated here. Link to a separate method only if one exists. Keep the expected observation prospective; do not assign `pass`, `fail`, `inconclusive`, or `not-run` to the basis. |
| Requirement state and change | One truthful set state, with per-item state where mixed. | Distinguish proposed, agreed or approved, superseded, and rejected content under actual project vocabulary. Identify change authority and affected sides. Do not claim agreement from document completion. Do not use `validated`, `pass`, `fail`, `inconclusive`, `not-run`, or `verified` as a content state. Content approval applies to the identified wording, edition, and scope; any claim about observed implementation conformity requires an actual cited observation. |
| Open interface issue | Zero or more gaps, conflicts, or pending cross-party decisions. | State the affected interface and requirements, the integration or verification consequence, the actual decision authority, and the resolution action. |

Use a boundary table or diagram when it clarifies endpoints, directions, and responsibilities. Use a numbered list or table with meaningful interface ID, requirement ID, responsible side, statement, project origin, state, and assessment columns for obligations. A diagram or drawing MAY carry geometry or flow details but MUST have a stated status and MUST NOT be the only controlling expression of a requirement. Identify any cited project interface definition, identity record, traceability endpoint, or observation by its actual locator, edition where needed, and relationship to the obligation. Do not add blank technical-category tables or a generic document-control block.

## Quality criteria

- Every active obligation is at the interface boundary, identifies the responsible side, applies under stated conditions, and can be assessed without guessing units, limits, or expected response.
- Both sides' obligations are compatible in direction, timing, units, ranges, modes, and fault behavior where those properties matter. Missing counterpart decisions remain visible.
- Each obligation states the boundary-specific interaction or limit and has one controlling statement. Any required realization detail has an identified project basis.
- Project-origin citations identify their actual scope and edition where relevant. Assessment expectations, requirement approval, any cited realization decision, and observations of conformity each retain their own basis and scope.
