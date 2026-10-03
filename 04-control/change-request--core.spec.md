# Change request specification

## Identity and selection

- **Specification ID:** `CHANGE-REQUEST@core`.
- **Purpose:** Propose one change to a controlled product, service, or baseline and track its reason, impact, risk, affected configuration, implementation and rollback intent, authorization, implementation, and closure.
- **Intended readers:** The requester, impact assessors, the change authority, implementers, and the role that verifies closure.
- **Decision or action supported:** Decide whether the stated change should proceed and, after an actual decision, see whether implementation, baseline update, and verified closure have occurred.
- **Use when:** A controlled product, service, configuration item, or baseline is proposed for change and the proposal, impact, affected configuration, implementation and rollback intent, and required authorization must be controlled together.
- **Scope boundaries:** Cover one proposed change and its authorization, execution, baseline-update, and closure status. Identify the actual decision and any triggering problem or defect record when they exist.

## Authoring inputs and unresolved facts

Inspect the requester, date, trigger, and source; the current controlled configuration; the proposed before-and-after; alternatives actually considered; technical, assurance, and delivery impacts; change-specific uncertainty; intended implementation and rollback; and any real authorization, implementation, baseline, verification plan, or closure evidence.

If a fact is unknown or not yet decided, state that status, its consequence, the resolving action, and the actual owner if assigned. Do not invent an affected identifier, an impact, an authorization, a commit or work order, a baseline, a test result, or a rollback procedure. A dimension that was not assessed stays `not assessed`. Record no secrets.

## Finished-document contract

- **Title:** Identify the controlled product or service and name the document as the change request for one stated change.
- **Frontmatter:** None. Begin with the GFM title. Identity, proposal, impacts, and change state belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Identify the request and proposal before impact; place authorization and implementation after impact; place verification and closure last. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Request identity and proposal | Required | Give the request a stable identity and proposal revision, the current change state, the requester, date, trigger, and inspected source, the problem or opportunity, the consequence of not changing, the before-and-after and affected obligations, the expected benefit labeled as expected, the alternatives disposition, and each affected configuration object. |
| Impact and risk | Required | Address technical impact, assurance impact, and delivery impact. For each, state the assessed impact, an assessed finding of no impact, or that it is not assessed. State the change-specific uncertainty that could make the change unsafe, ineffective, or hard to reverse, or state that risk is not assessed. Cite a risk, verification, or test record only when it exists. |
| Authorization and implementation | Required | State whether an authorization exists and, when it does, its scope, conditions, and the proposal revision it covers. State the intended implementation and rollback or reversal approach, including when rollback is not available and what follows from that. Separate that intent from actual execution. Identify the resulting baseline only when one now contains the change. |
| Verification and closure | Required | State the closure authority, residual restrictions, notifications, unimplemented portions, and retest or verification results that actually exist. For a `closed` request, cite the checked evidence for the implemented scope. For every earlier state, state which of these facts are not yet established. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Request identity | One identifier and one current proposal revision. | Keep the identifier stable. The proposal revision changes when the before-and-after changes. It is not an implementing commit or a baseline identifier. |
| Change state | Exactly one of `proposed`, `assessed`, `authorized`, `rejected`, `implemented`, or `closed`. | `proposed` means the impact is not complete. `assessed` means every impact dimension and the change-specific risk have been assessed and no authorization exists. `authorized` cites an authorization that covers this proposal revision. `rejected` cites the rejecting authority and reason. `implemented` means the authorized change was carried out. `closed` means implemented work has verified closure. A requester withdrawal or deferral before authorization stays `proposed` or `assessed`, names its actor and date, and is not `rejected`. After authorization, a change to authorized scope, deferral, or withdrawal requires the change authority's disposition; implementation and closure states require their actual execution and closure evidence. Work done before authorization is recorded as unauthorized execution and does not make the state `implemented`. |
| Affected configuration | One or more baselines, configuration items, requirements, interfaces, or other controlled product or service objects. | Use a real identifier when one exists. If none exists, name the object and state that it has no controlled identifier. Do not invent an identifier. A request that names no affected object is not ready to assess. |
| Alternatives | One disposition, plus zero or more considered alternatives. | Record alternatives that were considered and why the proposal is preferred. If none were considered, or none were credible, say which of those is true. Silence is not that statement. Cite any existing analysis used to select the proposal. |
| Impact statement | Three dimensions: technical; assurance; delivery. | Technical covers function, interfaces, compatibility, performance, and architecture. Assurance covers verification and validation, safety, security, quality, reliability, and effects on explicit project obligations and supplied delivery commitments, with the evidence used. Delivery covers cost, schedule, suppliers, operations, maintenance, data, training, and retirement. Use only the effects that were assessed and say when a named concern has no identified impact. |
| Authorization | Zero until a decision exists; one when the change is authorized. | Cite the actual decision, scope, and conditions. The request text is not that decision. A rejection is recorded as rejection, not as an authorization identifier. An authorization does not update a baseline or prove implementation. |
| Implementation intent and result | One intent statement, and an actual result only after execution. | State how the change is to be made and how it would be rolled back or why rollback is unavailable. Before execution, state that execution has not occurred; identify a planned revision or work order only when it exists and label it as planned. After any execution, identify the actual revision, commit, work order, or equivalent and the observed result, including partial, failed, rolled-back, or unauthorized work. These results alone do not establish authorized implementation or closure. |
| Resulting baseline | Zero or one real baseline. | Cite a baseline only when that approved baseline contains this change. Authorization alone does not create the reference. State when no baseline update applies or it has not occurred. |
| Closure evidence | Required for `closed`; otherwise only evidence that exists. | Cite checked evidence for the implemented scope. Planned verification references are not results. `rejected` does not require passing implementation evidence. |
| Closure conditions | One statement of what remains. | Cover residual restrictions, notifications, unimplemented portions, and retest results when those facts exist. At closure, say explicitly whether any authorized scope remains unimplemented and cite the change authority's disposition for any such remainder; do not present a partial result as full implementation. Do not invent a passing retest. |

Use prose for the proposal and impact narrative. Use a short list for affected objects, alternatives, and evidence citations. Do not add an empty evidence row or a second change inside this request.

## Quality criteria

- The before-and-after, affected objects, and proposal revision identify one change a reviewer can accept or reject.
- `assessed`, `authorized`, `implemented`, and `closed` rest on assessed technical, assurance, delivery, and risk statements. A rejection or requester withdrawal may occur before assessment is complete; the unassessed concerns remain explicit.
- `authorized`, `implemented`, and `closed` each cite the distinct decision, execution, and closure evidence those states require.
- The cited authorization covers the current proposal revision. A later edit of the before-and-after is not left in `authorized`.
- Rollback intent is present even when execution has not occurred, and actual execution is not inferred from the intent.
- Changes to affected obligations and configuration objects are stated as proposed or established according to their actual authorization and execution status.
