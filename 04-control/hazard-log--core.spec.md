# Hazard log specification

## Identity and selection

- **Specification ID:** `HAZARD-LOG@core`.
- **Purpose:** Maintain a stable identity for each system hazard across development and operation, including its mishap, controls, verification status, residual exposure, and disposition.
- **Intended readers:** Safety analysts, control owners, people assessing verification, and the authority that reviews closure or residual exposure.
- **Decision or action supported:** Readers can see which hazards are open, which controls are credited, which verification is still planned or missing, and which residual exposure has not been accepted.
- **Use when:** The project needs to track individual hazards with a stable identity, control linkage, verification linkage, residual exposure, status, and acceptance trace across the lifecycle.
- **Scope boundaries:** Each entry tracks a condition that can cause harm in the stated system configuration, the associated mishap, and the current control and disposition evidence.

## Authoring inputs and unresolved facts

Obtain the established project safety need or requirement and assigned decision roles; the system, configuration or baseline, and lifecycle boundary; the project method for mishap severity, with its category meanings and classification criteria, and any likelihood or risk category that method uses; each identified condition, its cause, and the harm it can produce; controls and whether any are credited; planned verification and any performed results; residual-exposure results; the project closure and acceptance rules, including their evidence and decision criteria; and any real closure or acceptance decision. Obtain existing project records that bear on a hazard, with their locators and relevant facts.

If the project safety need or requirement, method, condition, severity, owner, control, verification result, or decision is unknown or not established, record that status, its effect on control of the hazard, the resolving action, and an actual owner if one is assigned. Do not invent a severity category, likelihood, control, passing result, closure, or acceptance. If the project method does not use likelihood, omit it. If no control is credited, do not state a residual exposure after controls. An assessed-empty log requires a real assessment of the stated boundary that gives its method, date, and limit. An unassessed draft states that assessment is unresolved and makes no claim that hazards are absent.

## Finished-document contract

- **Title:** Identify the system or bounded configuration and the document as its hazard log.
- **Frontmatter:** None. Begin with the GFM title. Scope, hazard state, and safety decisions belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Give scope, method, and disposition rules before the entries. Present open exposure and review with or after the entries. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Scope, method, and disposition rules | Required | State the system boundary, configuration or baseline, lifecycle coverage, and the established project safety need or requirement or its unresolved state. Define the project mishap-severity method, including category meanings, classification criteria, and method version, or an explicit unresolved method. Include likelihood or another risk category only when that method uses it, and define its meanings and criteria. State the review cadence or event trigger, the evidence and decision criteria required before closure or supersession, and the assigned decision role, conditions, and criteria for accepting residual exposure. Record an unassigned decision role as a gap. Closure and residual-exposure acceptance have separate dispositions. Name the role accountable for the log, or record the assignment gap. |
| Hazard entries | Required | Record each identified hazard with a stable ID, the condition and its basis, cause, the mishap or harm to which severity applies, severity, control disposition, verification disposition, current state, and related records that exist. State residual exposure only where controls are credited. State acceptance only where the project acceptance rule requires it. If a real assessment found no hazards, state that assessment and its limit instead of adding a placeholder hazard. |
| Open exposure and review | Required | Summarize hazards whose control, verification, residual assessment, owner, closure, or acceptance is unresolved. Give the latest real review when one occurred and the next review or trigger. Apply the closure rule only to hazards actually closed or superseded. Identify acceptance only where the named authority made that decision, including its scope and reference. A document lifecycle state is not closure or acceptance. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Hazard entry | Zero after a stated real assessment that found none; otherwise one per identified hazard. An unassessed log has no placeholder row and makes no claim that the scope is free of hazards. | Give every entry a stable ID and never reuse it for a different condition. The subject is a condition, internal or external to the system, that can cause harm in the stated configuration. |
| Condition basis | One per entry. | State whether the condition was observed, is present in the specified design, or remains a hypothesis, and give the evidence or assumption. A project may use its own labels when their meanings are stated. Do not relabel a hypothesis as observed. |
| Cause | One or more mechanisms, or one explicit unknown. | Separate an established mechanism from a hypothesis. State uncertainty rather than inventing a cause. |
| Mishap or harm | One or more effects per entry. | State who or what can be harmed and how. If several effects exist, identify the effect to which the severity applies. |
| Severity | One current classification per active entry, or an explicit unresolved state. | Use the project scale and its basis. Do not invent category names or treat severity as acceptance. |
| Likelihood or risk category | Conditional on the project method. | Record it when that method uses it. Unknown remains unresolved and is not a default low value. |
| Control disposition | One per entry. | Identify credited or candidate controls in words or by locator to their established project definition, including its version, or state that none are identified or none are credited. An empty reference list does not say which of those is true. Keep a recommendation separate from a control that is credited. A linked control must be identifiable without duplicating its full definition. |
| Verification disposition | One per credited control, or one explicit gap for the entry. | Use not planned, planned, performed, or not established. A planned method is not a performed result. A performed result states the actual outcome, cites the evidence, and may be unfavorable. |
| Residual exposure | Conditional on at least one credited control. | Use the stated project safety method and label a design forecast separately from an observed reassessment. State the remaining uncertainty. Omit it when no control is credited. |
| Entry state | One current state per entry. | Define the local meanings. `closed` or `superseded` needs the evidence and disposition the stated project closure rule requires. Record residual-exposure acceptance separately. An open state does not need an acceptance reference. |
| Acceptance | Conditional on the project acceptance rule; record a decision only when it actually occurred. | When the rule requires acceptance, cite the assigned decision role, actual scope, and decision, or mark it not established. When the rule does not require acceptance, say so. A null token is not a decision. Acceptance covers only the stated residual exposure; it does not authorize operation or release the named baseline. Closure does not supply acceptance. |
| Accountability | One role for the log, or one role per open hazard when accountability is divided. | If neither is assigned, record the gap and the escalation route. Do not invent a person. |
| Related record | Zero or more per entry. | Cite a failure-mode analysis, defect, risk, requirement, or other analysis only when that record exists. |
| Review point | The latest real review when one occurred, and a next trigger for the active log. | A cadence or due date is not evidence that a review happened. A review that occurred may be cited with its date, scope, and hazard-related decisions. |

Use a register table with meaningful ID, condition, mishap, severity, control and verification state, residual exposure, and disposition columns. Use linked detail or short prose where cause, evidence, or uncertainty will not fit without ambiguity. Do not include blank rows, a generic document-lifecycle block, a synthetic-data flag, or an imposed acceptance signature.

## Quality criteria

- The boundary and severity method are stated, so a reader can interpret every classification; likelihood appears only when the method uses it.
- Every active entry identifies the hazardous condition, its basis, and the mishap or harm to which its severity applies.
- Credited controls, recommendations, planned verification, performed verification, forecast residual exposure, observed reassessment, closure, and acceptance are distinguishable. Performed verification has an actual outcome and evidence. Closure and residual-exposure acceptance are recorded separately.
- Each open hazard has an accountable role or a visible assignment gap, and a usable next review or escalation trigger.
- Closure and acceptance have the evidence and authority their rules require. An empty reference list, a low severity, or a document state does not supply them.
- An assessed-empty log states its limit and does not claim the system has no hazards beyond that assessment. 
