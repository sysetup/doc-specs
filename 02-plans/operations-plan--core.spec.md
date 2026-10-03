# Operations and support plan specification

## Identity and selection

- **Specification ID:** `OPERATIONS-PLAN@core`.
- **Purpose:** Plan routine operation and support of a defined service or system, including ownership, observability, capacity, data protection, upkeep, and escalation interfaces.
- **Intended readers:** Service owners, operators, support teams, security and change roles, suppliers, and managers responsible for service readiness.
- **Decision or action supported:** Establish how the service will be operated, monitored, supported, and kept within its agreed operating boundaries.
- **Use when:** A service or system needs a coordinated operating and support model before or during sustained use.
- **Scope boundaries:** Define sustained operating and support arrangements through roles, coverage, controls, decision thresholds, and handoffs.

## Authoring inputs and unresolved facts

Obtain the service boundary, environments, users and operating windows; ownership and support commitments; architecture, dependencies, workload and capacity basis; actual service objectives and escalation thresholds; observability and logging constraints; data and configuration requiring protection; backup and restore obligations; access and security responsibilities; maintenance, change, incident, problem, and continuity arrangements; and existing operational evidence or procedures where relevant, with their actual editions and locators.

If an owner, commitment, threshold, recovery objective, retention rule, or dependency is unknown or not established, state the gap, its operational effect, the action to resolve it, and the actual owner if assigned. Distinguish a proposed target from an agreed commitment. If the service has no persistent state, explain the resulting backup disposition rather than inventing a backup schedule. Describe intended controls, alerts, restore checks, and support actions as planned activities with expected evidence and any authorization needed.

## Finished-document contract

- **Title:** Identify the service or system and name its operations and support plan.
- **Frontmatter:** None. Begin with the GFM title; operational scope and responsibilities belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Establish service scope and responsibility before monitoring and routine controls; describe escalation and review after the operating methods. Exact heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Service scope and operating basis | Required | Define the service, included environments, users, operating windows, exclusions, important dependencies, agreed service commitments, and assumptions. Distinguish supported hours from the period over which availability is measured. |
| Ownership and support model | Required | Identify accountable service ownership, operating and support roles, handoffs, coverage, escalation route, external support dependencies, and access or decision authority needed for routine and urgent work. State unresolved coverage or supplier commitments. |
| Observability and security operations | Required | Plan indicators, monitoring points, alert conditions, routing, log sources and correlation, access to telemetry, sensitive-data handling, retention basis, and security event or vulnerability escalation. State who reviews noise, gaps, and false alerts. |
| Capacity, performance, and availability interface | Required | Describe demand and capacity assumptions, performance measures, headroom or saturation indicators, review and scaling decisions, and the operating provisions that use availability objectives when those objectives are established. Identify each objective's actual project basis and agreement state. If none are established, state that gap and the operating limits that are known. |
| Data and configuration protection | Required | Identify what must be backed up or reconstructed, the protection methods, retention periods and access controls, who owns the activity, and how restore readiness and recovery objectives will be checked. If backup is inapplicable to part of the scope, explain why and how that part is recovered or rebuilt. |
| Routine maintenance and controlled change | Required | Describe upkeep windows, preventive or corrective operating activities, patch and configuration-change interfaces, prerequisites for authorized work, expected records, and coordination with software or physical-asset maintenance where applicable. Identify the edition and locator of each detailed operating procedure used. |
| Incident, problem, and continuity interfaces | Required | Define detection-to-triage routing, escalation for service degradation or security events, linkage of recurring problems to corrective change, and handoff to recovery or continuity arrangements when their activation criteria apply. State receiving roles, decision rights, and required handoff information. |
| Readiness, evidence, and plan review | Required | Identify the planned evidence of monitoring, backup, maintenance, support, and change activities; who reviews performance and gaps; and triggers for revising the plan after service, dependency, workload, or obligation changes. Identify any available observations by their actual record locators. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Service boundary | One bounded service or system scope; identify constituent environments or tiers where their handling differs. | Name users, operating periods, dependencies, exclusions, and the owner; avoid treating a proposed service as already in production. |
| Support commitment | One entry per distinct actual coverage or response commitment, if any. | Identify source, supported population and hours, triggering event, responsible party, and escalation. A target lacking agreement is a proposal or gap. |
| Operational signal | One or more signals sufficient to detect material service or security conditions. | For each, give the measured condition, source, interpretation or threshold, alert route, reviewer, and limitations. An SLO is included only when established. |
| Operational dependency | Each dependency whose loss materially affects service or support. | Identify dependency owner or interface, effect of failure, observation or escalation route, and any supplier support limitation. |
| Protected state | Each material data or configuration set, or a reasoned no-persistent-state disposition. | Identify protection and restore method at planning depth, retention and access basis, responsible role, recovery criterion, and expected check evidence; do not assume backup success. |
| Operational handoff | One route for each material change, incident, maintenance, or continuity boundary. | State the trigger, receiving role, information transferred, authority needed, and the hold, escalation, or recovery route for work that did not complete or remains unresolved. |

Use prose for the operating model, a responsibility or coverage table where several teams share work, and a signal or dependency table when multiple items differ. A compact flow or decision table may clarify escalation. Identify controlled operating procedures by their editions and locators. Omit executable commands.

## Quality criteria

- A reader can identify what is operated, by whom, during which hours, under which real commitments, and how a material alert reaches a decision maker.
- Monitoring, logging, security handling, capacity review, and data protection have owners, observable criteria, and bounded evidence expectations.
- Backup and recovery planning covers actual state and obligations; a stateless or excluded component has an explained recovery route.
- Routine operating controls support stated availability objectives; maintenance, change, incident escalation, and recovery handoffs identify triggers, receiving roles, information, and authorization needed.
- Agreed targets, proposed targets, planned controls, and actual operational evidence remain distinguishable. Planned activities state criteria and expected evidence without asserted execution results.
