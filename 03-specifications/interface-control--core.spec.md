# Interface control document specification

## Identity and selection

- **Specification ID:** `INTERFACE-CONTROL@core`.
- **Purpose:** Define and control a versioned interface realization and the cross-party decisions needed to keep its two sides compatible.
- **Intended readers:** Responsible organizations on both sides, interface and integration engineers, implementers, configuration managers, and verification personnel.
- **Decision or action supported:** Each party can implement the same interface edition, identify who controls each side, and determine whether a proposed change or version combination is permitted.
- **Use when:** Parties need a shared, controlled definition of an interface's chosen physical, information, or behavioral realization, whether still proposed or actually agreed.
- **Scope boundaries:** Control the selected or proposed interface parameters, their ownership, version combinations, and joint decisions for the identified boundary.

## Authoring inputs and unresolved facts

Obtain the interface identity, endpoints and configurations, responsible parties, supplied project requirements, allocations or design decisions, and the selected or proposed design information. Inspect supplied drawings, schemas, protocol definitions, configurations, timing and fault models, security and safety controls, compatibility decisions, and the intended compatibility check. Determine which project artifacts control each parameter, their editions and effectivity, who may approve changes, and whether both sides have actually agreed. Cite an as-built observation or a verification record only when one exists.

If an endpoint, parameter, version, decision role, compatibility rule, or agreement decision is unknown, record the gap, its effect on implementation or integration, the resolving action, and the actual owner if assigned. A draft may state a proposed realization, but it MUST NOT label that realization bilaterally agreed, as built, or verified without a real decision or a real record. Identify the interface and project basis directly, with each cited obligation or decision identified by its existing record and scope. State the selected or proposed parameters explicitly. Omit physical, data, or other technical categories that are genuinely inapplicable after assessment, and explain an omission that could affect compatibility.

## Finished-document contract

- **Title:** Name the interface and identify the document as its interface control document; include the controlled edition or configuration range when needed to distinguish it.
- **Frontmatter:** None. Begin with the GFM title. Agreement state, applicability, and effectivity are substantive body content.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Establish interface identity and decision basis before the controlled definition; put agreement, the intended check, compatibility, and change control after the definition. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Interface identity and control boundary | Required | Identify the interface, endpoints, participating parties and their responsibilities, applicable configurations or editions, document control identity, supplied project obligations or design decisions, and authority for joint changes. State which side owns each parameter or artifact and how conflicts between controlled project definitions are resolved. Identify each cited obligation or interface identity by its actual record, edition, and scope, maintaining one controlling statement for each. |
| Controlled realization | Required | Define the selected or proposed connection and exchange characteristics needed for both sides to interoperate: relevant geometry, connector and pin assignments, electrical or fluid limits, data and signal formats, protocol or medium, message sequencing, timing, initialization, state changes, error and degraded behavior, security or safety controls, and environmental constraints. Give units, tolerances, directions, and controlling project drawing or schema editions where they matter. |
| Compatibility and intended check | Required | State permitted endpoint or protocol version combinations, dependencies, and migration or transition rules when versions can coexist. State the compatibility check for this definition directly, or identify a real project procedure or check record by its edition and locator. Specify the observation that would be needed for each intended check without assigning an execution result to it. |
| Agreement, effectivity, and change | Required | State whether the realization is proposed, agreed, superseded, or disputed, and cite the actual decision evidence for any agreement claim. Identify any known as-built or implemented condition by its real observation record and configuration. Identify any cited verification evidence by its actual record and assessed scope, without copying its result. Identify the applicable baseline, effectivity conditions or dates, proposed or approved changes, impact assessment, and the route for notifying and obtaining decisions from affected sides. Unresolved parameter or decision-role conflicts remain visible. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Interface identity | One bounded interface or a tightly coupled set under the same parties and change authority. | Use stable IDs consistent with actual project records for the same interface; otherwise identify the boundary directly. Identify the controlling definition and version relationship for that identity, keeping unresolved definition conflicts visible. |
| Endpoint and responsibility | Two or more actual sides or participating roles. | Identify provider or consumer direction, ownership of each side, integration responsibility, and who can accept or reject a parameter change. A contact name is not a substitute for decision authority. |
| Project basis | At least one supplied project requirement, allocation, internal mandate, or recorded design decision that justifies the controlled definition. | Give a usable title or ID, edition, locator, and covered scope. Identify the actual controlling obligation or decision without duplicating its statement as a separately controlled version. |
| Controlled parameter or artifact | One or more versioned physical, electrical, information, behavioral, or other characteristics needed for interoperability. | For each relevant characteristic, state the value or rule, units and tolerance where meaningful, direction or side, and controlling project artifact edition. A drawing or machine-readable file MAY be referenced; the Markdown document must state the characteristic it defines, its version, and how conflicting parameter definitions are resolved. |
| Compatibility rule | One rule for the applicable endpoint or configuration pair, with additional rules when versions or modes differ. | State allowed and excluded combinations and transition behavior when multiple editions can coexist. An unspecified combination is not implicitly compatible. |
| Agreement state | One truthful state for the controlled definition. | Use proposed, agreed, superseded, or disputed, or state that agreement is not established. Joint agreement requires actual decisions from both responsible sides. Record agreement independently of any observed construction or verification condition. |
| As-built citation | Conditional on a real configuration or observation record. | Cite that record, edition, and scope. State only the observed condition supported by that record. Leave construction or verification unknown when no supporting observation is supplied. |
| Intended check or verification citation | One intended compatibility check for each material interface behavior, or a citation to the real project procedure, check definition, or evidence record that holds it. | State which side and configuration the check concerns and what observation would be required. If neither the check nor a real record is established, record that gap. Do not assign `pass`, `fail`, `inconclusive`, `not-run`, `verified`, or `not-verified` to the intended check. Any cited claim of successful integration testing requires an actual observation tied to the tested configuration. |
| Change and effectivity | One route for changing the controlled interface and identifying its applicable edition. | Identify decision roles for both sides, affected baselines and versions, impact and transition treatment, and the actual effective date or condition when decided. |

Use a boundary or pinout drawing, message or signal table, state or sequence diagram, or protocol flow when it makes the controlled realization clearer. Tables should name the parameter, direction or side, value or rule, units or tolerance, and controlling edition where relevant. A diagram or separately stored project schema MUST identify its implementation-controlling role and version if it controls implementation. Include physical connector details only for interfaces that have a physical connection, and keep technical detail tied to the identified interface boundary.

## Quality criteria

- The chosen or proposed realization is precise enough for both sides to implement consistently, including version, ownership, units, timing, failure behavior, and other characteristics material to this boundary.
- Project obligations, selected parameters, agreement state, as-built observations, and verification citations each have their actual basis, configuration, and scope identified. Proposed parameters remain labeled as proposed until the responsible parties decide them.
- Both parties' assumptions and compatibility rules agree. Missing counterpart decisions, incompatible versions, and uncontrolled artifacts are explicit issues.
- Changes identify affected versions, requirements, parties, and effectivity. A cross-party agreement claim has actual evidence from the responsible decision authorities.
