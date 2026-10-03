# Integration plan specification

## Identity and selection

- **Specification ID:** `INTEGRATION-PLAN@core`.
- **Purpose:** Plan how identified components, subsystems, or increments will be combined into a defined assembly or system and checked at each integration boundary.
- **Intended readers:** Integration leads and performers, component and interface owners, configuration and assurance roles, test leads, suppliers, and gate decision makers.
- **Decision or action supported:** Coordinate the integration sequence, prerequisites, responsibilities, environment, checks, and the response when a step does not meet its criterion or is unsafe, before work begins.
- **Use when:** A project must plan assembly and interface bring-up across one or more integration stages, including their configurations and readiness gates.
- **Scope boundaries:** Cover assembly and interface bring-up for the identified integration stages, including configuration selection, prerequisites, readiness gates, checks, safe recovery, and handoff. Deployment into receiving operations is outside this integration scope.

## Authoring inputs and unresolved facts

Obtain the target assembly and integration boundary; controlled component identities and candidate versions; interface definitions and compatibility constraints; supplied project technical requirements and integration risks; available facilities, environments, tools, simulators, and personnel; component delivery and access dependencies; identified hazards, safety measures, security restrictions, and configuration-control decisions; assessment methods and criteria; project schedule and integration decision rights. Inspect the actual project baselines used for component and interface selection or state that they are not yet established.

For an unavailable item, unresolved interface, unselected configuration, or unconfirmed facility, state the gap, affected stage, consequence, resolving action, and actual owner if assigned. Proposed sites, dates, methods, permissions, and component versions remain proposed. A stage cannot be represented as ready to execute if its indispensable interface definition, safe environment, authority, or entry/exit criterion remains unresolved. Do not invent an executed check, authorized location, accepted assembly, or rollback capability.

## Finished-document contract

- **Title:** Identify the target system or assembly and name its integration plan.
- **Frontmatter:** None. Begin with the GFM title; configurations, locations, and gate authority belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Establish scope and configuration basis before the sequence; give each stage's readiness, activities, checks, and response route before final handoff. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Integration objective and boundaries | Required | Identify target assembly or system, incoming items and existing receiving assembly, lifecycle stage, included and excluded interfaces, intended integrated capability, and the role responsible for the plan. Explain the integration effort's dependencies and milestones within the larger project. |
| Configuration, interface, and planning basis | Required | Identify component and interface identities, candidate revisions or selection rules, supplied project technical requirements and their versions, compatibility assumptions, dependencies, and configuration control. State how changes to any basis are assessed before continuing. |
| Strategy and sequence | Required | Explain incremental build or other chosen assembly order, dependency and risk rationale, enabling products, planned locations or environments, responsible parties, and schedule or readiness windows. Show where tests or inspections influence the next stage. |
| Integration stages | Required: one or more stages | For each stage, identify the items and versions or selection rule, receiving assembly, interface or behavior being established, facility and equipment needs, entry prerequisites, ordered integration work at planning depth, hold points, checks and exit criteria, owner and decision role, expected evidence, and the next-stage dependency. Identify existing detailed procedures and environment records by location and version when used. If a necessary method or environment capability is not established, state the gap and its readiness consequence. |
| Missed criteria, unfinished checks, and unsafe work | Required | Define the planned response when a check does not meet its criterion, cannot be concluded, or is unsafe: stop or hold triggers, anomaly and configuration capture, containment or safe-state route, rework and reassessment authority, and how a later attempt is distinguished from the earlier attempt. State rollback constraints; where reversal is impossible, plan isolation, repair, or another justified safe disposition. |
| Integrated-result and handoff interface | Required | Define what configuration and evidence will be offered to downstream verification, validation, transition, or acceptance, who reviews integration exit criteria, and how open defects or constraints travel with the assembly. State the planned handoff prerequisites and the receiving decision role. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Target assembly | One bounded assembly, subsystem, or system integration scope. | Identify the receiving configuration and incoming item set; integration of a single incoming item into an existing assembly still has an interface boundary. |
| Integration stage | One or more ordered, distinct stages. | Use a stable stage label within this plan, inputs, expected output configuration, dependencies, responsible role, and planned gate. Do not reuse a label for a different stage, and do not duplicate a stage to fill a form. |
| Component or interface selection | One or more relevant items per stage. | Tie item identity to revision or version-selection rule and compatible interface edition. A hash, serial number, or precise site is required only when the chosen control method or work needs it. |
| Environment and support equipment | One environment treatment per stage; equipment entries only when needed. | State capabilities, controls, access and calibration or simulator fidelity where material. Identify required permissions, availability, and any supporting environment record by location and version; distinguish confirmed access from proposed access. |
| Stage check | One or more checks sufficient to assess the stage's exit. | State the observable, criterion, method or real procedure reference, responsible evaluator, target configuration, and expected evidence. Identify any required method still to be established. |
| Response to a missed, unfinished, or unsafe check | One planned response for each material condition in which a check does not meet its criterion, cannot be concluded, or is unsafe. | Identify the trigger, safe-state or rollback feasibility, decision role, defect record, and re-entry criterion. Do not assume physical integration is reversible. |

Use a stage table or ordered stage subsections when multiple stages exist, an interface or configuration matrix when several items must be matched, and a dependency diagram when sequence is complex. Prose should explain strategy and failure handling. A plan may reference detailed procedures, but it must remain usable as a planning document without copying command sequences or empty test rows.

## Quality criteria

- Every stage has a known intended input and output configuration, interface boundary, owner, prerequisite, check, and downstream dependency.
- The sequence respects component availability, interface compatibility, environment and equipment readiness, and safety or security constraints that actually apply.
- Entry and exit criteria are assessable. Planned responses preserve defects and configuration history when a check does not meet its criterion or cannot be concluded. The plan does not assume a favorable result or a successful later attempt.
- The planned integration order and checks support the intended assembly boundary; the handoff identifies the configuration, evidence, unresolved constraints, and receiving decision role.
- Proposed and ready-to-execute stages are distinguishable by their configuration, permissions, environment readiness, and entry criteria; planned outputs and evidence are identified for later execution.
