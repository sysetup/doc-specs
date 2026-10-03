# System, product, or asset maintenance plan specification

## Identity and selection

- **Specification ID:** `ASSET-MAINTENANCE-PLAN@core`.
- **Purpose:** Plan upkeep of identified systems, products, or assets through selected maintenance strategies, triggers, resources, work controls, and return-to-service criteria.
- **Intended readers:** Asset owners, maintainers, operators, engineering and safety roles, suppliers, stores or logistics teams, and return-to-service decision makers.
- **Decision or action supported:** Decide when and how maintenance is initiated, resourced, controlled, assessed, and escalated over the asset's useful life.
- **Use when:** A system, product, or physical or infrastructure asset needs a maintenance strategy before servicing or repair.
- **Scope boundaries:** Cover upkeep and servicing of identified systems, products, or physical or infrastructure assets at planning depth, including task purposes, work controls, and return-to-service criteria. Software changes are outside the maintained-work scope.

## Authoring inputs and unresolved facts

Obtain the maintained asset or asset-class boundary and configuration, operating context and lifecycle; supplied project maintainability, reliability, availability, safety, and security requirements and the needs or decisions establishing them; supplied manufacturer or engineering task data, instructions, limits, and editions where relevant; known failure and condition data; maintenance access, hazards, permits, isolation and configuration controls; task triggers or intervals and their basis; competence, facilities, spares, tools, calibration and supplier support; service-disruption constraints; return-to-service criteria and decision authority; and project recording and obsolescence needs.

For an unknown interval, asset state, hazard, support right, return-to-service criterion, or authority, state the gap, affected work and consequence, resolving action, and actual owner if assigned. Do not choose a plausible interval or declare a task instruction authorized without a real basis. If a maintenance mode, permit, calibration control, or disposal duty is inapplicable, explain the scoped reason. Keep planned servicing, checks, and expected evidence distinct from established asset condition and supplied work history; do not infer fitness for service from intended work.

## Finished-document contract

- **Title:** Identify the maintained system, product, asset, or asset class and name its maintenance plan.
- **Frontmatter:** None. Begin with the GFM title; asset identity and plan scope belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Establish asset scope and obligations before strategy and tasks; give work controls before return-to-service and lifecycle review. Exact heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Asset scope and maintenance basis | Required | Identify covered assets or asset classes, configuration or selection rule, operating context, lifecycle period, exclusions, owner, project performance and safety requirements with their established basis, origin, edition, and limits of maintenance instructions, and relevant failure or condition history. |
| Strategy and task program | Required | Explain the basis and tradeoffs for preventive, condition-based, corrective, or other selected approaches. For each maintained asset or class, define inspections or interventions, trigger or interval and its source, action at planning depth, service effect, task owner, and route for an abnormal finding. Do not force every strategy onto every asset. |
| Support and logistics | Required | Identify needed competence, staffing, facilities, access, technical data, tools, calibration where material, spares or replacement supply, supplier dependencies, and constraints that could prevent timely work. |
| Work initiation and control | Required | Plan work request and authorization, scheduling or outage coordination, hazard and isolation controls where applicable, permits, configuration and change control, task-instruction interface, anomaly escalation, and records expected from performance. Identify authorization required before execution and configuration changes; describe task purposes and controls at planning depth. |
| Assessment and return to service | Required | Define post-work inspections or functional checks, the criteria a later return-to-service decision must use, restoration of safety and configuration controls, evidence expected, unresolved-defect handling, and the role that may later return the asset to service. Require the specified checks, evidence, and decision before operation resumes; repair completion alone does not establish fitness. |
| Performance, revision, and end-of-life interface | Required | Define how later failure, condition, work, cost, or downtime data will be reviewed; how strategy and intervals change under authority; and how obsolescence, support loss, withdrawal, or retirement is escalated for decision. Detailed disposal measures apply only when within this plan's actual scope. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Maintained item | One or more identified assets or justified asset classes. | Bind each to an operating context and configuration or selection rule; distinguish planned coverage from established asset identity and condition. |
| Maintenance approach | At least one selected approach per item or class. | Name the failure or condition addressed, selection basis, limitations, and response when the approach cannot be executed. A corrective-only approach needs a detection and response route. |
| Maintenance activity | Each recurring or condition-triggered activity needed by the selected approach. | State task purpose, trigger or interval with source, responsible role, access or outage needs, work-instruction reference if real, and expected record. Do not invent time-based intervals. |
| Work control | One route for normal work and a conditional urgent route when allowed. | Define initiator, required authorization, hazard or isolation check where needed, configuration capture, anomaly hold or escalation, and preservation of the as-found state. |
| Return-to-service basis | One route for each materially different maintained item or work class. | State the required check, criterion, decision role, the planned response when a later check does not meet its criterion or cannot be concluded, and the evidence expected. Distinguish task completion from the decision permitting return to service. |
| Support dependency | Each supplier, spare, tool, skill, or facility whose absence materially blocks maintenance. | Identify availability or right to use, lead time or readiness constraint where established, and escalation or alternative; do not imply contractual rights. |

Use prose for strategy and decision authority, a task matrix when assets or triggers differ, and a flow or decision table for work authorization and failed return-to-service checks. Identify existing task instructions and work-history records by locator and edition or date when used as technical input.

## Quality criteria

- A maintainer can identify the covered configuration, project requirements, task trigger, responsible role, enabling resources, and required authority before work starts.
- Intervals and repair-or-replace decisions have a source or clear decision gap, not an arbitrary schedule.
- Hazards, access, permits, isolation, configuration, and service outage effects are addressed where the asset and work make them material.
- A later check that does not meet its criterion, an unresolved defect, and unavailable support have escalation paths. Return to service requires the specified criteria, evidence, and decision role.
- Planned checks and return-to-service decisions specify the evidence and authorization needed before an asset is treated as fit for service.
- Maintenance strategy, task triggers, support needs, work controls, and lifecycle escalation remain consistent with the covered assets and operating context.
