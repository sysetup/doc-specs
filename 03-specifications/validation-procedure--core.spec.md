# Validation procedure specification

## Identity and selection

- **Specification ID:** `VALIDATION-PROCEDURE@core`.
- **Purpose:** Define a repeatable assessment of whether a bounded solution is fit for identified stakeholder needs or intended use under representative conditions.
- **Intended readers:** Validation designers and facilitators, users or stakeholder representatives, operators, product owners, and reviewers of intended-use evidence.
- **Decision or action supported:** Prepare a credible use scenario, conduct the planned assessment, capture relevant observations, and judge what the event can or cannot show about stakeholder need satisfaction.
- **Use when:** A stakeholder, user, mission, or business need calls for a planned validation event with explicit context, participants or representative actors, steps, and evaluation criteria.
- **Scope boundaries:** Define the intended-use question, representative context, scenario actions, and fitness criteria for the bounded solution. Limit planned conclusions to the needs and conditions the scenario can assess.

## Authoring inputs and unresolved facts

Obtain the established project stakeholder need or intended-use statement and its origin and edition, the solution and configuration to be evaluated, intended users or other relevant actors, operational setting and representative scenarios, environmental and data conditions, known risks and use limitations, a suitable observation method, concrete criteria for judging the need, safety and access constraints, and evidence and decision responsibilities. Determine which real conditions can be reproduced, simulated, or only observed elsewhere. State the need, its project basis and locator, and the criteria at the detail needed to assess the scenario.

If a need, success criterion, representative condition, participant role, safety prerequisite, or use right is unknown or undecided, state the affected validation question, its impact on interpretation, the resolving action, and actual owner if assigned. If the event uses a proxy user, simulated environment, or limited sample, state what that substitution cannot establish. Do not invent participant identities, consent, observations, acceptance, or a validation result. If real people or sensitive data are involved, apply actual project permission and protection rules before asserting the event is ready.

## Finished-document contract

- **Title:** Identify the solution or bounded intended-use scope and name the document as its validation procedure; distinguish the procedure or scenario edition when later results will cite it.
- **Frontmatter:** None. Begin with the GFM title. Need basis, scenario, and evaluation criteria belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State the need and use context before the scenario and criteria; define prerequisites before actions and evidence and decision rules after the actions. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Validation question and need basis | Required | Identify the solution and applicable configuration, one or more established project stakeholder or intended-use needs with their origins and editions, the fitness question to answer for each, scope and exclusions, and the limits of the planned conclusion. |
| Representative use context and criteria | Required | Define the scenario, relevant user or actor roles, tasks, operating setting, interfaces, data, workload or environmental conditions, why they represent intended use, and known fidelity limits. State observable evaluation rules for each need and how qualitative judgments will be grounded in observations. Distinguish a criterion met, a criterion missed, and an unsupported comparison; an unexercised condition leaves its need unassessed. |
| Preconditions and participants | Required | Specify starting state, required environment and data as intended conditions, participant role or proxy and its selection basis, briefing or competence needs, access or consent rules when applicable, safety and stop conditions, and checks before the event. An environment target or a data definition is not the configuration or materialized data an event used. Name actual participants only if known and appropriate to disclose; a role definition does not claim attendance. |
| Ordered validation activity | Required | Give one or more stable locally identified scenario steps: actor and action, condition or stimulus, expected observable, capture method, and branch for invalid, unsafe, or deviating conditions. Include realistic handoffs, reset, and repeated trials only where the need requires them. Identify the edition and step locators of any project-controlled execution sequence used, with its entry, capture, and return conditions. Map each action to the need, context, and fitness criterion it assesses. A failed prerequisite, unsafe stop, or event that does not occur leaves the affected fitness question unassessed. |
| Evidence and decision boundary | Required | State which observations, user feedback, measurements, context facts, deviations, and limitations a later result record must retain, and how they will be compared with each criterion. Define review or stakeholder interpretation where needed. Make clear which party, if any, may separately decide formal acceptance; this procedure does not make that decision. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Need and validation question | One or more sourced needs, each with a bounded question about fitness for intended use. | State each need and its real project origin, with edition and locator when needed. If a technical requirement ID is used to identify a need, explain the stakeholder need it represents. |
| Solution and context of use | One bounded solution configuration and one or more representative scenarios. | State operational roles, tasks, environment, interfaces, data, and stressors that affect fitness. Explain omitted or simulated conditions and the resulting limits on conclusions. |
| Evaluation criterion | One or more observable rules for each material validation question. | State expected outcome, measurement or judgment method, threshold or qualitative rubric when established, and how conflicting observations will be handled. Do not invent a target or call the criterion a stakeholder acceptance decision. |
| Participant or actor role | One or more roles needed to conduct or observe the event; actual named participants are conditional. | Define relevant user characteristics, proxy rationale, operator/facilitator responsibilities, and eligibility or briefing needs at the level that changes representativeness. A human participant is not mandatory when a valid operational surrogate can answer the stated question. |
| Prerequisite and safety rule | One coherent set of checks for the event. | Include actual permission, consent, data protection, safe stop, and recovery conditions when applicable. A planned check is not proof of consent, readiness, or authorization. |
| Scenario step | One or more ordered steps, each with a stable local label. | State actor, action, intended-use condition, expected observable, observation capture, and branch for deviations or unsafe states. The label need only be unique in this procedure. |
| Expected evidence and result rule | One coherent planned account of what an actual event must record. | Bind later observations to solution edition, scenario/context, participant role or proxy, procedure edition, times where material, criteria, and limitations. Include feedback provenance and an investigation or disposition route when the comparison is not supportable. Label expected observations as planned. Define how an actual event's state and evidence determine `pass`, `fail`, `inconclusive`, or `not-run`; leave the outcome unassigned in the planned procedure. |
| Acceptance relationship | One explicit boundary when a project has a separate receiving-party acceptance decision. | Identify the real decision authority and basis if established. A favorable validation observation neither creates acceptance nor substitutes for a later authorization. If no such decision is in this scope, say only what the validation assessment can support. |

Use a scenario narrative or ordered steps for the use flow. A need-to-scenario-to-criterion table is useful when several needs or use conditions are assessed; meaningful columns include need, actor, condition, expected observation, criterion, and capture. A journey, state, or flow diagram MAY clarify interactions, with its fidelity limits and criteria stated in text. Do not prefill participant responses, expected artifacts as if collected, or empty result rows.

## Quality criteria

- Every validation question traces to an inspected stakeholder need and an observable criterion under a stated intended-use condition.
- Scenarios and participants or proxies are representative enough for the planned conclusion, and fidelity, sampling, and setting limits are visible.
- Steps, safety rules, capture methods, and criteria support a repeatable event with observable readiness and consent checks where needed.
- Each fitness conclusion is limited to the observed conditions and criterion comparison; receiving-party acceptance, when relevant, has an identified decision maker and basis.
- Unresolved needs, criteria, permissions, or context gaps are visible and prevent a stronger conclusion than the available basis can support.
