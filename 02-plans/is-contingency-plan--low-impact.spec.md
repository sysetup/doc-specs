# Low-impact information-system contingency plan specification

## Identity and selection

- **Specification ID:** `IS-CONTINGENCY-PLAN@low-impact`.
- **Purpose:** Define how one classified low-impact information system will activate contingency arrangements, recover service and data, return to routine operation, exercise the approach, and keep the plan usable.
- **Intended readers:** System owner, contingency coordinator, recovery personnel, supporting providers, and authorities who decide activation or return to service.
- **Decision or action supported:** Those roles can recognize a disruption, decide whether to activate the plan, carry out a bounded recovery, and assess readiness against established recovery objectives.
- **Use when:** The responsible authority has established a low-impact classification for the system and requires a system-specific contingency plan.
- **Scope boundaries:** Cover contingency activation, recovery, and return to routine operation for one system with an established low-impact classification. Include alternate location or storage only when the selected recovery strategy uses it.

## Authoring inputs and unresolved facts

Obtain the project classification decision and deciding role; system boundary, current recovery configuration, supported services, data, dependencies, locations, and operators; actual impact or business analysis; approved recovery time and recovery point objectives where relevant to the selected strategy; backup and restore method; activation and return-to-service authority and required operational permissions; communications and contact arrangements; selected security measures and change-control decisions; and project decisions on exercise, training, review, and protected distribution. Identify each supplied project fact or decision by its actual record, edition, or locator.

Mark a missing fact as unknown and an undecided strategy or objective as not established. For each material gap, state its effect, resolving action, and actual owner if assigned. Explain a genuinely inapplicable activity and its basis. An unestablished impact classification, recovery objective, activation authority, usable backup or recovery method, or return-to-service criterion prevents the plan from being presented as ready for activation. Do not invent target values, contact details, approvals, tests, or successful recovery.

## Finished-document contract

- **Title:** Identify the system and the low-impact information-system contingency plan.
- **Frontmatter:** None. Begin with the GFM title. System identity, plan edition, classification, and authority are operational content in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Establish scope and objectives before activation; describe recovery before reconstitution; put readiness and maintenance after the operational phases. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Scope, authority, and objectives | Required | Identify the system, plan edition or other unambiguous version, plan owner, established low-impact classification and its project decision record, supported services, scope and exclusions, operational assumptions, and recovery objectives with their decision basis. Name who may later approve the plan and activate recovery, and identify required operational permissions and their approving roles. |
| Recovery concept and responsibilities | Required | Describe the architecture and dependencies needed for recovery, the authorized recovery configuration, required people and resources, and the activation, recovery, and reconstitution phases. Give role handoffs and a protected way to reach current contact details. Identify alternate location or storage only when the selected strategy uses it. |
| Activation and notification | Required | Define observable activation triggers, the decision route, outage assessment, initial safety and security checks, notification sequence, alternate communication method, and the route when the usual authority or channel is unavailable. |
| Recovery | Required | Give prioritized actions or controlled procedure references, their prerequisites, responsible roles, expected restored states, backup or data source selection, dependency order, escalation conditions, and the evidence a later execution record must capture. Include a planned safe response when restoration cannot meet the objective. |
| Reconstitution and deactivation | Required | Define checks for restored data integrity and currency and for required functions, and the criteria a later recovery declaration must use. Name the authority for declaring recovery or continued restriction, user notification, removal or control of temporary resources, renewed backup readiness, event documentation, and the authority for deactivation and handoff to routine ownership. |
| Exercises, training, and maintenance | Required | State the selected exercise or test method and frequency, participant roles, evidence a later exercise would retain, how defects trigger plan updates, training needs, review triggers, contact and dependency refresh, and protected plan distribution. Identify the internal project decision or scheduling role setting the cadence; mark an undecided cadence as not established. |
| Supporting material | Conditional when detailed contacts, recovery instructions, impact findings, or provider arrangements are needed to execute the plan | Include the controlled material or an accessible, versioned reference. Keep sensitive contact and access information in an appropriately protected location; the plan must still tell authorized personnel how to find it during disruption. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| System and impact decision | One bounded system and one established low-impact classification. | Identify the deciding role and project decision record; reassess the recovery scope, objectives, and strategy if classification changes. |
| Recovery objective | One or more approved time, data currency, or service priorities that govern recovery. | State units, scope, and source. Explain any gap between an objective and the selected method; do not imply that an exercise proved it. |
| Activation rule | One or more observable disruption conditions and a decision authority. | A rule must lead to activate, continue assessing, or escalate, including when the usual decision maker is unreachable. |
| Recovery action | One or more ordered actions or controlled procedure references. | Each has a target or selection rule, responsible role, prerequisite, expected state, and a route when restoration cannot meet the objective or must be escalated. A referenced procedure must identify its actual location and version and remain usable during disruption. |
| Reconstitution check | At least one data or state check and one functionality check relevant to the restored service. | State the criterion, responsible role, and evidence a later execution would retain for the recovery or restriction decision. |
| Exercise and upkeep rule | One plan for exercising and maintaining the contingency method. | State method, cadence or scheduling authority, evidence a later exercise would retain, and change triggers. |

Use a short decision flow or table for activation, ordered steps or a table for recovery, and a checklist with explicit criteria for reconstitution. Use prose for assumptions and rationale. An architecture sketch MAY clarify dependencies. Detailed procedures and contacts MAY be referenced when their location and version are available during a disruption. Do not include blank form rows or secrets.

## Quality criteria

- The recovery sequence can plausibly meet the established objectives with the stated backups, resources, dependencies, and staffing, or the gap is visible and routed for decision.
- Every operational branch ends in a next action, safe stop, restriction, or escalation; reconstitution does not silently convert an unverified system into normal service.
- Planned approval, activation, recovery, exercise, and return-to-service decisions identify their prerequisites, required evidence, and responsible roles; required operational permissions are explicit.
- Contact and procedure references remain usable during the modeled outage; the plan defines protected locations and access restrictions for sensitive contact and recovery information.
