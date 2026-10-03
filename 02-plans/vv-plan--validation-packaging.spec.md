# Validation plan specification

## Identity and selection

- **Specification ID:** `VV-PLAN@validation-packaging`.
- **Purpose:** Plan how a bounded solution will be assessed for fitness against stakeholder needs or intended use in representative conditions, with traceable scenarios, criteria, and expected evidence.
- **Intended readers:** Validation leads and facilitators, stakeholder and user representatives, operators, product owners, assurance reviewers, and recipients of validation evidence.
- **Decision or action supported:** Agree which needs and use conditions will be examined, by whom and how, what observations will matter, and what the assessment can support.
- **Use when:** A project needs a plan for assessing stakeholder needs or intended-use fitness in representative conditions.
- **Scope boundaries:** Specify planned fitness-assessment activities, representative conditions, resources, criteria, and evidence routes. Each assessment must have a stakeholder or intended-use need as its basis.

## Authoring inputs and unresolved facts

Obtain the real solution and target-configuration boundary; project stakeholder, user, mission, or business needs and their origins; intended tasks and operating context; representative scenarios, users or proxies, environments and fidelity limits; evaluation criteria; access and safety constraints; schedule, resources, roles, the project decision or justified risk establishing the independence basis, evidence and anomaly rules; and actual stakeholder review or acceptance interfaces. Read each supplied need statement and its use context. Existing project scenario descriptions, procedures, or matrices may supply scenario, method, or coverage data.

For an unknown need, operating condition, representative actor, configuration, criterion, permission, independence basis, or decision right, state the affected validation question, impact on interpretation or readiness, resolving action, and actual owner if assigned. Mark an undecided choice as not established. Explain an inapplicable level or recipient obligation; do not invent a user, consent, target, observation, favorable result, acceptance, independent role, or result. State independence as required, with the established project decision or justified risk and the role separation; as not required, because neither applies; or as not established, when that basis is unknown. Do not treat an unknown project decision as a decision that no independence is required. Material gaps in the need basis, representativeness, criteria, or safe access prevent a claim that the affected validation activity is ready for a conclusive assessment.

## Finished-document contract

- **Title:** Identify the solution or intended-use scope and name the document as its validation plan.
- **Frontmatter:** None. Begin with the GFM title. Need basis, context, and decision rules belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State needs and intended use before scenarios and criteria; place resources and readiness before evidence and decision interfaces. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Purpose, scope, and need basis | Required | Identify the solution and planned configuration, lifecycle and project boundary, established project stakeholder or intended-use needs with origins, editions and locators, objectives, material exclusions, and project scope decisions. State the fitness-in-use questions to be assessed and any unresolved conflicts among needs or scope decisions. |
| Use context and validation strategy | Required | For each need question whose context is established, describe representative tasks, actors or justified proxies, operating conditions, interfaces, environments, scenarios, and why they can answer that question. State simulation, sampling, and fidelity limits. Leave an unanswered question as an explicit gap. Select applicable end-item, integrated-system, or program-level scope only where it serves the use question. |
| Need and scenario mapping | Required | For each in-scope need or distinct use question, give scenario, participant or actor, configuration, conditions, method, observable evaluation criterion, responsible role, planned event, and expected evidence when those facts are established. Show an uncovered need or exclusion and its consequence. Do not invent a missing scenario, actor, or criterion, and do not enter a result. |
| Execution resources and readiness | Required | Define schedule and dependencies, representative products or services, environments and data, participants and competence, access or consent and safety rules when applicable, and observable entry, suspension, resumption, and exit rules with decision authority. State the independence conclusion: required, with the established project decision or justified risk and the role separation; not required, because neither applies; or not established, when that basis is unknown. State how a changed need or use condition triggers replanning. |
| Evidence packaging, anomalies, and interpretation | Required | Define capture and review rules retaining actual configuration, use context, participant or proxy, observations and feedback origins, criteria, deviations, limits, and review. Define event and attempt states for planned reporting: `not-run` applies only to a scenario selected for a bounded event that received no validation action; unselected planned work has no attempt state. An attempted assessment can receive `pass`, `fail`, or `inconclusive`. A missing observation or an invalidating condition on an attempt requires `inconclusive`; do not classify it as `not-run` or introduce a separate invalid result. Preserve each retest as a distinct later attempt linked to the earlier result. Define how fitness findings, limitations, and unresolved items will reach stakeholders and identify the receiving-party decision role and review or handoff gates. |
| Acceptance or certification interface | Conditional: an established project delivery obligation supports a receiving-party or certification decision | State expected validation products, recipient, decision role, explicit product and handoff criteria, and how findings will support the planned decision. |
| Terms and acronyms | Conditional: terminology could change interpretation | Define only terms needed to read the use context and evaluation criteria; no empty glossary or mandatory appendix. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Validation subject | One bounded solution or set of configurations and a selection rule for assessment. | Actual events must later identify what was evaluated; a planned configuration is not an observation. |
| Need or use question | One or more project stakeholder needs or intended-use questions when they are established; otherwise one explicit source gap. | Give the supplied project need record, edition, and locator when needed. If stated locally, identify its real origin. A technical requirement ID alone is insufficient, and a missing need is not invented. |
| Representative scenario | One scenario for each distinct use question that has an established scenario; none when that scenario is still a gap. | When established, specify actor or proxy, task, conditions, relevant interfaces and data, and why the scenario represents intended use; state omitted or simulated conditions. An in-scope question without a credible scenario stays visible as a gap. Do not invent the actor, conditions, or criterion. |
| Validation mapping | One visible account for each in-scope need or distinct use question. | Connect need, scenario, configuration, evaluation method and criterion, responsible role, planned event, and expected evidence when established. Leave a missing element visible as a gap. A planned row has no result. |
| Evaluation criterion | One observable or reviewable rule for each use question whose criterion is established; none while that criterion remains a gap. | Use established thresholds or a defined qualitative rubric with an observation basis. A favorable evaluation is not itself formal acceptance. |
| Participant or actor role | One or more roles for each established scenario; none for a question that is still a gap. Named individuals only when actually assigned and appropriate. | Give selection or proxy rationale where representativeness matters. Planned participation does not establish consent or attendance. |
| Planned evidence | One defined capture route for each scenario that is actually planned; none for a gap. | Specify observation or feedback capture with configuration, conditions, actor or proxy, method edition, criterion, limitations, and reviewer. Define retention of failed attempts and distinct linked retests. |

Use a need-to-scenario-to-criterion table for multiple needs, with columns that expose actor, conditions, configuration, planned event, responsibility, and expected evidence. For a short scope, explicit mapped items may suffice. An existing controlled project validation matrix may be cited by edition and locator with a coverage summary; otherwise include the mapping here. A journey or flow may clarify use conditions, but its assumptions and criteria must remain in text. Keep mapping rows at planning depth, with method descriptions and expected evidence fields rather than blank observation fields or copied execution steps.

## Quality criteria

- Every established validation question has an inspected need basis. A question whose need was not inspected stays a source gap and does not gain an invented need. A question with an established path also has a representative scenario, evaluation criterion, configuration rule, responsible role, and evidence path. An uncovered question stays an explicit gap.
- Users or proxies, setting, data, and operational conditions limit the fitness conclusion a later record may draw. Fidelity and sample limits remain visible. This plan states no fitness conclusion.
- Resources, permissions, safety controls, and readiness rules agree with the proposed events or remain explicit blockers.
- The independence conclusion is required, not required, or not established. An unknown project decision is not a decision that independence is unnecessary, and an independent role is not invented.
- This plan assigns no `pass`, `fail`, `inconclusive`, or `not-run`. Each planned fitness judgment requires need-linked observations under the stated use conditions.
- Planned stakeholder interpretation, receiving-party decisions, certification, and document approval have explicit roles and gates; the plan does not claim completed assessments or decisions.
