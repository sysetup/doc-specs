# Operational post-incident review specification

## Identity and selection

- **Specification ID:** `POST-INCIDENT-REVIEW@generic`.
- **Purpose:** Review one stabilized operational incident for supported causes, contributing conditions, response and recovery effectiveness, lessons, and improvement actions.
- **Intended readers:** Incident responders, affected service or operational owners, and people responsible for deciding and tracking improvements.
- **Decision or action supported:** Understand what the incident reveals and decide what should change, with evidence and limits visible.
- **Use when:** An operational incident that is not being handled as a cybersecurity incident has stabilized and a retrospective review has been performed.
- **Scope boundaries:** Retrospective analysis of one stabilized operational incident within the affected operation, configuration, and evidence cutoff stated in the review.

## Authoring inputs and unresolved facts

Obtain the incident identity, affected scope and configuration, stabilization basis, review date and participants, and the evidence available at the review's cutoff. Inspect the incident record when it exists, relevant timeline events and impact, disputed accounts, causal analysis, actual response and recovery, and the objectives against which effectiveness was assessed. Obtain lessons, recommendations, assigned actions, dissemination restrictions, and any actual review decision or follow-up results.

When a fact, cause, objective, assignment, or decision is unknown or not established, state the gap, its effect on the conclusion, and the resolving action with the actual owner if assigned. State inapplicability with a reason. A cause need not have been established for a review to record useful findings. Do not invent a root cause, lesson, action, approval, or separate incident record. When no incident record exists, identify the underlying evidence directly and state the record gap.

## Finished-document contract

- **Title:** Identify the incident and call the document an operational post-incident review.
- **Frontmatter:** None. Begin with the GFM title; incident and review facts belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Establish scope and evidence before analysis; place lessons and follow-through after the analysis. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Review scope and evidence | Required | Identify the incident, affected operation and configuration, stabilization basis, review date, participants or contributing roles, and evidence cutoff. Cite the incident record if available. Summarize only the timeline and impact needed to understand the analysis, with disputed facts and evidence limitations. |
| Causes and contributing conditions | Required | Explain the analysis performed, supported causal factors, contributing conditions, hypotheses, and unresolved alternatives. State when no cause is established. Tie conclusions to examined evidence. |
| Response and recovery assessment | Required | Compare actual response and recovery with established objectives. Identify strengths, failures, delays, and constraints where supported. If objectives were not established, state that limitation and identify the basis of any retrospective judgment. |
| Lessons and recommendations | Required | State the lessons and systemic improvement opportunities derived from findings, with limits of applicability. An assessed statement that no lesson or change is yet supported is valid. |
| Improvement and follow-through | Required | Account for actions, priorities, owners, target dates, and effectiveness criteria; state explicitly when no action was derived. Describe permitted dissemination and supplied project reporting assignments, including audiences and timing. State review completion, any approval required by a supplied project condition, remaining uncertainty, and how open actions and effectiveness checks will be followed. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Review context | One incident and one bounded review account. | Identify the reviewed incident state and evidence cutoff so later findings are not silently attributed to the earlier review. Give the actual review date and roles; do not invent meeting attendance. Stabilization does not imply full recovery or incident closure. |
| Evidence reference | One or more inspected sources supporting the account, or an explicit evidence gap. | Identify the source and relevant revision or observation time and locator. Distinguish observations from disputed accounts and inference. Summarize the chronology relevant to the analysis. New factual conflicts identify the source entry needing reconciliation. |
| Causal finding | Zero or more findings, with an explicit analysis result. | Each has a stable local identity, claim, supporting evidence, and classification as a supported cause, contributing condition, or hypothesis. Explain the reasoning and material alternatives or limitations. Temporal sequence alone does not establish causation. An unresolved cause stays unresolved. |
| Effectiveness finding | Zero or more findings plus an overall assessment. | Tie each judgment to actual response or recovery evidence and an identified objective or stated assessment basis. Metrics carry units, interval definitions, and uncertainty. A recovery observation is not a decision to accept the restored operation. |
| Lesson or recommendation | Zero or more, after assessment. | Tie each to a finding and identify the proposed improvement or useful practice to retain, intended benefit, and applicability limits. A recommendation is not an approved change. Avoid unsupported personal blame. |
| Improvement action | Zero or more actions actually proposed or agreed. | Give a local or existing master identity, originating finding or lesson, action, priority and its basis, owner, target date or trigger, status, and intended effectiveness check. Missing assignments and dates remain explicit. Cite an action master only when it exists. |
| Action status and evidence | One current state per action. | Use `proposed`, `planned`, `in-progress`, `blocked`, `completed`, or `cancelled`. Distinguish a proposal from an agreed assignment. Blocked actions name the blocker; cancelled actions give the reason. Completed actions cite completion evidence. State effectiveness separately as not assessed, supported, not supported, or inconclusive, with the actual check and evidence when assessed. |
| Dissemination | One account of permitted audiences, restrictions, and any required reports. | Distinguish intended distribution from actual sending. Identify supplied project reporting assignments, their assigning role, recipients, timing, and assignment locator; unknown details remain explicit. Restrict sensitive operational details and personal information; use controlled evidence locators where needed. |
| Review disposition | One as-of account of completed review work and remaining work. | State whether the review is complete or still open, and why. Identify any supplied project approval condition. Include the actual approval decision maker, decision, scope, and date when approval occurred; otherwise state pending, unknown, or not required with a basis. Identify who tracks outstanding actions, or the assignment gap, and any revisit trigger. Review completion and action effectiveness are separate conclusions. |

Use prose for causal reasoning and limitations. Use tables or distinct blocks for findings and lessons. When several actions exist, use an action table with identity, origin, action, priority, owner, target, status, and effectiveness check. A short timeline or causal diagram MAY clarify the analysis; distinguish hypothesized relationships from supported ones. Do not add empty rows, a generic document-control block, or sections unrelated to the assessed operational incident.

## Quality criteria

- The review addresses a stabilized operational incident and has an explicit evidence boundary and retrospective analysis.
- Every causal and effectiveness conclusion has a stated basis; conflicting evidence, alternatives, and uncertainty remain visible. No finding requires a single root cause or personal blame.
- Recommendations and actions trace to findings. An assessed absence of findings or actions is represented without fabricated items.
- Completion evidence and effectiveness evidence are distinguished. Incident status, open actions, and residual recurrence risk remain explicit at the review cutoff.
- Dissemination follows the actual restrictions. References identify existing project records or observed evidence.
