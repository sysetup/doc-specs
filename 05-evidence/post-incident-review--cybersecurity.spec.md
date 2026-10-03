# Cybersecurity post-incident review specification

## Identity and selection

- **Specification ID:** `POST-INCIDENT-REVIEW@cybersecurity`.
- **Purpose:** Review one stabilized cybersecurity incident for supported causes, control outcomes, response effectiveness, dwell time, eradication confirmation, notification handling, and improvements.
- **Intended readers:** Security responders, affected resource and control owners, and the roles responsible for disclosure decisions and improvement follow-through.
- **Decision or action supported:** Assess what failed or worked, what remains uncertain, and what corrective work or further investigation is justified.
- **Use when:** A cybersecurity incident has stabilized and retrospective analysis has been performed, including when some causes, eradication checks, or follow-up actions remain unresolved.
- **Scope boundaries:** Retrospective analysis of one stabilized cybersecurity incident, bounded by the reviewed resources, configuration, and evidence cutoff.

## Authoring inputs and unresolved facts

Inspect incident identity, affected resources and configuration, stabilization basis, review date and participants, evidence cutoff, incident records if present, relevant timeline and impact, and disputed or unavailable evidence. Obtain the causal analysis, control expectations and observed outcomes, response and recovery objectives and results, timing estimates and their derivation, eradication checks, and supplied project notification assignments for customers, regulators, and other identified audiences, including recipients, triggers, timing, disclosure decision makers, and actual sending evidence. Obtain lessons, action assignments, dissemination restrictions, and any review decision or effectiveness check.

Unknown causes, compromise times, control failures, assignments, or notification duties MUST remain explicitly unknown or not established, with consequences and a resolving action and assigned owner if one exists. Inapplicability needs a reason. Do not manufacture a failed control, treat an unknown interval as zero, or assert eradication from restored service. Identify the supplied project notification assignments and actual disclosure decisions, including recipients, triggers, deadlines, and decision roles; unresolved details remain explicit. Cite underlying evidence and state any missing incident record when needed.

## Finished-document contract

- **Title:** Identify the incident and call the document a cybersecurity post-incident review.
- **Frontmatter:** None. Begin with the GFM title. Review scope and findings belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Give scope and evidence first, then causal and cybersecurity assessments, then lessons and follow-through. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Review scope and evidence | Required | Identify the incident, resources and configuration, stabilization basis, actual review date and roles, and evidence cutoff. Summarize relevant timeline and impact with sources, disputed facts, and limits. Cite the actual incident record when available. |
| Causal and response assessment | Required | Present the analysis, supported causes, contributing conditions, hypotheses, and open alternatives. Compare detection, response, and recovery with established objectives or disclose the basis and limits of retrospective judgment. Retain strengths as well as failures. |
| Control outcomes and timing | Required | Assess failed, bypassed, missing, or ineffective controls against their intended operation; distinguish controls that worked and causal uncertainty. Define and assess the relevant undetected or active intervals, with bounds, evidence, method, and uncertainty or explicit indeterminacy. |
| Eradication assessment | Required | State what eradication work and confirmation checks occurred, their scope, who checked, when, method, evidence, findings, and remaining limitations. State incomplete, unconfirmed, or inapplicable work explicitly. |
| Notification assessment | Required | Assess supplied project notification assignments for customers and regulators separately, plus any other identified audience class. For each duty, compare the assigned timing and audience with the actual status and evidence. Retain missed or unresolved obligations. |
| Lessons and improvements | Required | Tie lessons and recommendations to findings, with applicability limits. Record proposed or agreed actions and their follow-up; explicitly state assessed absence. |
| Dissemination and review disposition | Required | Identify permitted audiences, confidentiality and evidence-access restrictions, actual distribution if any, review completion, approval state under any supplied project approval condition, and remaining investigation or effectiveness checks. Give review status, incident status, and action status their respective evidence and as-of times. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Review context | One bounded review of one cybersecurity incident. | Identify actual review date, participants or contributing roles, reviewed configuration and scope, stabilization basis, and evidence cutoff. Stabilization is not full recovery, eradication, or closure. |
| Evidence and finding | Zero or more identified findings, with one assessment of the reviewed scope. | Each finding has a stable local identity, claim, supporting evidence, reasoning, and uncertainty. Classify causal claims as supported causes, contributing conditions, or hypotheses. Identify relevant source revisions or observation times and locators; retain conflicting accounts. State when no cause is established. |
| Control assessment | Zero or more control findings plus an explicit assessment result. | For each, identify the control or intended objective, expected operation and its basis, observed outcome, evidence, and relationship to the incident. Distinguish absent, bypassed, failed, ineffective, and worked as assessed descriptions rather than assumed causes. A conclusion of no failed control identified needs the assessed scope and basis. An unassessed control set is not that conclusion. |
| Dwell or activity interval | Zero or more estimates plus an explicit applicability and determinability statement. | Define each interval's start and end events; distinguish time until detection from time until containment or other activity endpoint. Give timestamp sources, timezones when known, units, calculation or estimation method, bounds, and uncertainty. Earliest observed activity is not automatically first compromise; containment is not automatically the last malicious activity. Unknown endpoints remain unknown or bounded. Do not invent timestamp precision or negative durations. |
| Eradication confirmation | One assessment as of the evidence cutoff. | State `confirmed`, `incomplete`, `unconfirmed`, or `not-applicable`, with a basis. Confirmation identifies what was removed or remediated, the assessed resources, checker, date/time, method, actual evidence, and limits. Distinguish not performed from performed but unconfirmed checks. Confirmation covers that scope and does not prove universal absence of compromise. |
| Notification applicability | One assessment each for customers and regulators, and for any other identified audience class. | State `duties-identified`, `none-apply`, or `unresolved`, with the supplied project assignment or disclosure decision and supporting evidence. No notification rows are needed for a class with no assigned duty, but the determination remains explicit. An unavailable or incomplete assignment stays `unresolved`. Do not supply a fictional audience. |
| Notification duty and result | Zero or more actual project notification duties. | Each identifies audience, assigned requirement, assigning project role and assignment locator, deadline or trigger, actual status (`pending`, `sent`, `not-sent`, or `unknown`), disclosure decision maker, and evidence. Sent notices identify sending time and evidence; sending alone does not establish receipt or timeliness. Assess timeliness only when both the assigned requirement and actual timing are established. Explain missed obligations and the actual follow-up state. |
| Lesson or recommendation | Zero or more after assessment. | Identify the finding, lesson, proposed improvement or practice to retain, expected benefit, and limits. Any adopted improvement identifies the actual decision, scope, and decision maker; a proposal stays proposed. |
| Improvement action | Zero or more proposed or agreed actions. | Give identity, originating finding or lesson, action, priority with basis, owner, target date or trigger, state, and intended effectiveness check. Unassigned owners and unset dates stay explicit. Cite an action master only when it exists. Use `proposed`, `planned`, `in-progress`, `blocked`, `completed`, or `cancelled`; identify blockers, completion evidence, or cancellation reasons as applicable. |
| Effectiveness follow-up | One account per action. | Distinguish the planned check from a performed check. State effectiveness as not assessed, supported, not supported, or inconclusive; assessed results include method, date, evidence, and limitations. Implementation completion alone does not establish effectiveness. |
| Disclosure and review disposition | One as-of account. | Identify dissemination restrictions and actual distribution separately from incident notification. Cite restricted evidence rather than copying credentials, personal data, sensitive indicators, or unnecessary vulnerability details. State open or complete review work, remaining issues, follow-up responsibility or assignment gaps, and revisit triggers if set. Include approval when a supplied project approval condition requires it; identify the condition, decision role, scope, and actual state, distinguishing pending from granted approval. |

Use prose for causal reasoning and evidence limits. Use tables or distinct blocks for controls and interval estimates. When several duties or actions exist, use tables showing the fields above, with one real duty or action per row. A timeline or causal diagram MAY explain findings but MUST label uncertain times and hypothesized links. Do not add empty control or notification rows or a generic document-control block.

## Quality criteria

- Findings are supported within the reviewed scope and evidence cutoff. No mandatory field forces a control failure, exact compromise time, notification, or confirmed eradication.
- Dwell estimates have explicit endpoints and uncertainty. Detection, containment, eradication, service recovery, and incident closure are not treated as interchangeable events.
- Confirmation identifies actual checks and limits. Customer and regulator applicability are separately assessed, and every sent or timely-notification claim has the required evidence.
- Lessons and actions trace to findings; action completion and demonstrated effectiveness each have their own evidence. Open actions and residual recurrence risk remain explicit at the review cutoff.
- Sensitive evidence stays under its actual restrictions. Source discrepancies are surfaced for reconciliation, references exist.
