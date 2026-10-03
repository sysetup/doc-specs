# Risk register specification

## Identity and selection

- **Specification ID:** `RISK-REGISTER@core`.
- **Purpose:** Maintain the current assessment, ownership, treatment, and monitoring of uncertain events or conditions that may adversely affect stated objectives.
- **Intended readers:** Risk owners, project or operational decision makers, treatment action owners, and reviewers of the affected objectives.
- **Decision or action supported:** Readers can prioritize exposure, assign or escalate treatment, watch for triggers, and see which residual-risk decisions remain open.
- **Use when:** A bounded set of project, service, or operational risks needs ongoing identity and control across reviews.
- **Scope boundaries:** Entries describe uncertain events or conditions affecting stated objectives, with their current assessment, treatment stage, and monitoring. A realized occurrence may inform an entry but cannot be represented as an uncertain event. Risk ratings and closure states do not establish residual-risk acceptance.

## Authoring inputs and unresolved facts

Obtain the objectives and scope at risk, assessment horizon, established project risk criteria and assigned decision roles, evidence behind identified conditions, the project's likelihood and consequence method, treatment options and actual decisions, accountable risk owners, monitoring observations, and review history. Inspect real action, issue, or hazard records when they affect a risk. Establish who may accept residual exposure, the recorded assignment of that role, and the conditions and scope of its decision rights; a score or document state does not grant those rights.

If a condition, rating, owner, treatment, or acceptance decision is unknown or not established, record that status, its consequence, the resolving action, and an actual owner if assigned. Do not create a numeric rating from an undefined scale or treat planned mitigation as implemented. If a category or trigger has no useful application, explain the reason where omission would hide exposure. An empty register MAY report that no risks were identified only when the assessed scope, method, date, and next review are explicit; it MUST NOT imply that the scope is risk-free. Unresolved assessment criteria or ownership prevent a claim that the register supports an authorized acceptance decision. Keep treatment details tied to the affected risk, actual decision status, action owner, target condition, and timing.

## Finished-document contract

- **Title:** Identify the project, service, or bounded scope and the document as its risk register.
- **Frontmatter:** None. Begin with the GFM title. Scope, review state, and risk decisions belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Give scope and assessment rules before entries; present current disposition and review information with or after the entries. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Scope and assessment method | Required | State the objectives, organizational or system boundary, time horizon, review owner, assessment date or as-of point, and established project risk criteria. Define the scales, thresholds, rating calculations, prioritization and escalation rules, and conditions for residual-risk acceptance needed to interpret and act on the entries. Identify the project method's edition or adoption decision when established. Name the assigned decision role, its recorded assignment, scope, and limits. Mark unresolved criteria or decision rights explicitly. |
| Risk entries | Required | Record each identified risk with a stable ID, cause or condition, uncertain event, consequence for an objective, evidence or origin, current assessment and uncertainty, accountable owner, treatment decision or pending choice, indicators, and current state. If no risk is identified after a real assessment, state the assessed scope and its limitation instead of adding a placeholder risk. |
| Treatment, residual exposure, and review | Required | For each entry, identify its actual treatment stage; distinguish proposed actions, authorized actions, completed actions, forecast residual exposure, and reassessment supported by observed results when each exists. Record action completion and observed effectiveness separately. Give a monitoring or review route, escalation on a material trigger, next review point, and the latest real review or decision if one occurred. Cite actual acceptance of residual risk only where the assigned decision role made that decision within its recorded scope and conditions. `closed`, `retain`, and a low rating are not that acceptance. Summarize unresolved ratings, owners, or decisions that block prioritization or closure. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Assessment rule or scale | One coherent project method; one or more dimensions only if that method uses them. | Give rating values or quantitative units, anchors, ordering, horizon, combination rule, thresholds, and the established project method edition or adoption decision. Define the rating meanings needed to interpret entries. If no scale is established, leave ratings unresolved. Use only dimensions and combinations established for the stated scope. A score is an exposure assessment, not permission to accept risk; `pass`, `fail`, `inconclusive`, and `not-run` are not risk rating values. |
| Risk entry | Zero or more assessed or emerging risks within the stated scope. | Give every entry a unique stable ID and one intelligible cause/condition → uncertain event → consequence chain. The event MUST remain uncertain; cite a realized occurrence when it changes this risk's basis or state, and identify the remaining uncertainty. |
| Current assessment | One current assessment per active entry, or an explicit pending state. | Show likelihood and consequence or other method-specific values, basis, confidence or material uncertainty, and the method edition or scale used. Reassess when the basis or scope materially changes. |
| Risk owner | One accountable role or person per risk once assigned. | Distinguish the accountable owner from action performers and the acceptance authority. If unassigned, mark the gap and escalation rather than inventing an owner. |
| Treatment | One strategy or explicit undecided state per active risk; zero or more actions under a chosen strategy. | State avoid, reduce, share, retain, or the project's actual option with decision status, action owner, target condition, and timing when committed. `retain` is a treatment choice. It is not residual-risk acceptance. Linked action IDs are optional when no separate action record exists. Record a committed action as completed only with its actual completion evidence and date. |
| Indicator and response | One or more observable indicators or a justified absence of a detectable precursor, with a review route. | Define how a trigger is observed, its threshold where meaningful, and who responds or escalates. A monitoring date is not evidence that a review happened. |
| Residual exposure | Conditional on a chosen or implemented treatment. | Label a forecast as forecast; label an observed reassessment with its evidence and date. State remaining uncertainty. Do not record a post-treatment result when treatment has not occurred. |
| State and decision | One current state per entry; acceptance reference conditional on an actual required decision. | Define local state meanings. `closed` needs a recorded reason and evidence or authorized disposition. Closure and residual-risk acceptance are distinct: an acceptance reference identifies the actual decision maker, assigned decision rights, scope, conditions, and decision record. Interpret the cited decision only within that recorded scope. |
| Review event | Zero or more dated real reviews per entry; a next review point for each active risk. | Preserve material changes in assessment, triggers, treatment, and decision. Do not fabricate review history for a newly identified risk. Identify a review that occurred by its date, participants or responsible role, findings affecting the risk, and resulting entry changes. |

Use a register table with meaningful ID, event, consequence, assessment, owner, treatment/state, and next-review columns. Use linked detail or short prose per entry when evidence, action status, or uncertainty will not fit without ambiguity. A risk matrix or chart MAY show priorities when the declared method supports it; the register entries remain authoritative. Do not include blank rows, duplicated generic control fields, or an imposed acceptance signature block.

## Quality criteria

- Ratings are interpretable from the defined scales, anchors, horizon, and calculation rules, or the missing scale is explicit.
- Every active entry separates the uncertain event from a realized issue, and its consequence connects to a stated objective.
- Treatment decisions, actual action completion, forecast residual exposure, observed reassessment, and formal acceptance are distinguishable.
- Each active risk has an accountable owner or a visible assignment gap, a usable monitoring route, and an actual next review or escalation trigger.
- Closure and acceptance claims have real decision evidence; low ratings, expired dates, `retain`, or a closed document state do not imply residual-risk acceptance.
