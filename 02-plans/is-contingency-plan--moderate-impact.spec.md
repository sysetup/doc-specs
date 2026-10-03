# Moderate-impact information-system contingency plan specification

## Identity and selection

- **Specification ID:** `IS-CONTINGENCY-PLAN@moderate-impact`.
- **Purpose:** Define coordinated activation, recovery, reconstitution, exercise, and maintenance for one classified moderate-impact information system, including the selected offsite data and alternate processing arrangements.
- **Intended readers:** System and mission owners, contingency coordinator, recovery teams, storage and processing providers, and authorities responsible for activation and return to service.
- **Decision or action supported:** Those roles can choose the recovery route, restore prioritized functions and data within established objectives, coordinate dependencies, and decide when normal operation may resume.
- **Use when:** The responsible authority has established a moderate-impact classification and requires a system-specific contingency plan.
- **Scope boundaries:** Cover contingency arrangements for the established moderate-impact system, including an offsite-data disposition and an alternate-processing disposition. Exclude concurrent processing.

## Authoring inputs and unresolved facts

Obtain the classification decision and deciding role; system boundary, critical functions, data, interconnections, current recovery configuration, and service dependencies; actual impact or business analysis; approved recovery time and recovery point objectives and their service priorities; selected recovery and backup strategies; offsite storage and alternate processing arrangements or recorded project decisions permitting alternatives; provider commitments; activation and recovery-declaration authorities; contact and alternate communication routes; project security and change controls; and exercise, training, maintenance, and protected distribution arrangements. Identify the edition and locator of each supplied project record.

Mark missing evidence unknown and an undecided arrangement not established, with consequence, resolving action, and actual owner if assigned. Explain inapplicability only from an actual scope or internally authorized alternative decision. An unresolved classification, objective, activation authority, viable recovery method, storage disposition, alternate-processing disposition, or restored-service criterion blocks a claim that the plan is activation ready. If the selected arrangement cannot meet a required objective, show the gap and escalation or the recorded decision that addresses it; do not hide it behind a generic alternative. Do not invent approvals, capacity, recovery results, or provider commitments. Mark activation, recovery, exercises, checks, and required authorizations as planned; identify any actual prior decision by its real record.

## Finished-document contract

- **Title:** Identify the system and the moderate-impact information-system contingency plan.
- **Frontmatter:** None. Begin with the GFM title. Plan control and operational authority belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Put system scope, objectives, and recovery strategy before activation; put reconstitution after recovery; end with readiness and maintenance. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Scope, authority, and objectives | Required | Identify the system, plan edition, owner, established moderate-impact classification and its decision record, supported functions and material exclusions, assumptions, recovery priorities, time and data objectives with units, and who may approve and activate the plan. State required authorization gates and any approval still needed. |
| Recovery concept, dependencies, and roles | Required | Describe system and data flows relevant to recovery, interdependent systems and providers, authorized recovery configuration, team responsibilities and handoffs, and protected access to current contacts. State how chosen storage and processing paths support the objectives and which external parties must coordinate. |
| Offsite storage and alternate processing disposition | Required | Identify the selected offsite backup or data storage arrangement or an actual internally authorized alternative, accessibility and integrity controls, and the plan for returning or renewing protected copies after recovery. Identify the selected alternate processing location or method, or a recorded project decision permitting a viable alternative. For each alternative, name the decision, deciding role, and viable method. If neither a selected method nor such a decision is established, state that the disposition is not established. Do not invent a location, method, or decision. An unsupported assertion of inapplicability is insufficient. |
| Activation and notification | Required | Define observable triggers, authorized invocation, outage and dependency assessment, initial safety and security checks, ordered notifications, alternate channels, provider contact, and reassessment or escalation when duration or scope changes. |
| Prioritized recovery | Required | State the dependency-aware order for restoring critical functions, data, access, and connectivity; responsible team and resources for each action; controlled procedure or step; expected state; planned checkpoint and criterion; fallback path; and evidence to capture during execution. Coordinate the alternate location or storage path when it is selected. |
| Reconstitution and deactivation | Required | Define how recovered data currency and integrity, transactions where applicable, system functions, access controls, and interconnections will be checked against stated criteria. State the authority and evidence needed for a recovery declaration, restriction notice, cleanup of temporary resources, renewal of backups and offsite copies, event documentation, and return of ownership to routine operations. |
| Exercise, training, and maintenance | Required | Define an exercise that demonstrates the selected restoration path and tests a backup or data recovery element against stated criteria; state participants, frequency or scheduling authority, expected evidence, deficiency handling, training needs, plan review triggers, contact refresh, and secure distribution. |
| Supporting material | Conditional when detailed contacts, procedures, impact findings, provider commitments, or location instructions are needed | Include the controlled material or a usable versioned reference, with access available to authorized recovery roles during disruption. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| System and impact decision | One bounded system and one established moderate-impact classification. | Identify the deciding role and decision record; a changed classification requires reassessment of plan scope and recovery arrangements. |
| Recovery objective | One or more approved function-specific time and data-currency targets. | Give units, priority, source, and any conflict among objectives, dependencies, and actual capability. A target is not a measured result. |
| Storage disposition | One selected offsite data arrangement or actual authorized alternative for the scoped data. | Identify custody, access during disruption, integrity or restore check, and renewal after use; do not embed storage credentials or sensitive coordinates. |
| Alternate processing disposition | One disposition account: a selected recovery location or method, a recorded project decision permitting a viable alternative, or an explicit statement that the disposition is not established. | An alternative account names the decision, deciding role, and viable method. Do not invent a location, method, or decision. An unsupported assertion of inapplicability is insufficient. When a method or decision is stated, give dependencies, capacity assumptions, security boundary, provider role, and how the route is invoked. |
| Activation and escalation rule | One or more observable conditions and decision authorities. | Each branch must lead to activation, continued assessment, safe restriction, or escalation. |
| Recovery action | One or more ordered actions or controlled procedure references. | Bind each to a target, responsible role, prerequisite, expected state, evidence to capture during execution, and the route when the action cannot continue. Give the procedure's edition and location accessible to recovery roles during disruption. |
| Reconstitution check | Data, function, and security checks for each restored critical service. | State the planned criterion, responsible role, expected evidence, and decision route for satisfactory, deficient, or unresolved recovery conditions. |
| Exercise and upkeep rule | One coherent schedule or event trigger for practice and plan refresh. | Include the planned restoration demonstration, evidence to retain during the exercise, defect handling, and revision after material system or dependency change. |

Use a small dependency or recovery-priority table when several functions compete for resources. Use a decision flow for activation, ordered steps or controlled procedure references for recovery, and a criteria checklist for reconstitution. A system or location diagram MAY clarify interfaces. Keep protected contacts and sensitive configuration in controlled supporting material with an outage-access route. Do not include blank form rows or credential values.

## Quality criteria

- The offsite data and alternate processing dispositions agree with stated recovery objectives and recorded project decisions; an alternative path identifies its authorizing role and decision. An undecided disposition is stated as not established and is not treated as a selected method.
- Function priorities, dependency order, team handoffs, provider commitments, and resource assumptions agree, or the unresolved gap is explicit.
- Reconstitution criteria require restored data currency, integrity, and usability checks in addition to confirming media availability.
- Readiness gaps, authorization gates, and planned activities are explicit. Prior decisions cited as established have actual records; planned checks have criteria and expected evidence without asserted execution results.
