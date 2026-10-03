# Architecture decision record specification

## Identity and selection

- **Specification ID:** `ADR@core`.
- **Purpose:** Record one architecture or technical decision, including its question, context, alternatives, rationale, state, consequences, and follow-through.
- **Intended readers:** The decision authority, the architects and implementers who must apply the choice, and later readers who need to know whether it still stands.
- **Decision or action supported:** See whether an option has been selected, why the other considered options were set aside, what the choice requires, and when it must be reconsidered.
- **Use when:** One architecture or technical choice needs a durable record of context, alternatives, rationale, status, consequences, and follow-through.

## Authoring inputs and unresolved facts

Inspect the decision question and scope; the relevant architecture baseline or the fact that none is established; the stakeholders and concerns actually involved; each material driver and binding constraint and its source; the credible alternatives, including no-change when it is credible, and any option screened out before comparison; the criteria and evidence used to compare them; any trade study that already holds the calculations; the option selected or the fact that none is authorized; the rationale, including rejected options; positive and adverse consequences, risks, and affected obligations; implementation responsibility and checks when a selection is authorized; reversal conditions, expiring assumptions, and reevaluation triggers; the decision state; the authority evidence; any prior decision this one replaces and any successor; and the architecture entities, concerns, views, or models actually affected.

When a fact is unknown or not established, state that, its consequence, the resolving action, and the actual owner if assigned. Do not invent an alternative, a criterion, a score, an authority, a successor, an implementation result, or a date. If no credible alternative was found, say so.

## Finished-document contract

- **Title:** Name the decision question or the selected option and identify the document as an architecture decision record.
- **Frontmatter:** None. Begin with the GFM title. Identity, state, and relationships belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State the question and context before the alternatives. State the alternatives and comparison before the rationale treats one option as selected. Place consequences with the decision. Place follow-through after the decision statement. Place the decision state where a reader can find it without inferring it from tone. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Question and context | Required | Give the record a stable identity. State the decision question and scope, the architecture baseline or that none is established, the stakeholders and concerns that bear on the choice, and each material driver or binding constraint with its source or an explicit unknown. |
| Alternatives and comparison | Required | Identify each alternative actually considered, including no-change when it is credible, and each option screened out before comparison with the reason. Compare the remaining alternatives against the criteria actually used. Cite a trade study when one holds the calculations or uncertainty analysis. When the comparison is only the qualitative reasoning in this record, say so. |
| Decision, rationale, and consequences | Required | For `accepted`, state the selected option. For `superseded`, preserve the historical choice and rationale, identify it as superseded, and point to the successor. For `rejected`, state what was refused. For `proposed`, label a preferred option as a recommendation or state that none is preferred. Explain the tradeoffs and the evidence, including why rejected options were not selected. Address favorable effects, adverse effects, risks, and affected obligations, and say when one of those is not assessed. |
| Follow-through and revisit | Required | For `accepted`, identify the changes the decision requires, the accountable implementers, and how conformance will be checked, or state that implementation is not yet established. For `proposed` and `rejected`, state that implementation is not authorized. For `superseded`, state that further implementation follows the successor. State reversal conditions, assumptions that expire, and reevaluation triggers, or state that none are identified. |
| State and relationships | Required | Give exactly one decision state. For `accepted`, identify the authority, the date if known, and the scope of the disposition. For `rejected`, identify the refusing authority and reason. For `superseded`, identify the successor. Cite a prior decision only when this record replaces one. Cite affected architecture subjects when they are known. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Record identity | One stable identifier. | Keep it stable across revisions of the same decision. Record a revision only when the project already controls one. |
| Decision state | Exactly one of `proposed`, `accepted`, `rejected`, or `superseded`. | `proposed` means no authority has selected or refused an option. `accepted` names one selected option and the authority that selected it. `rejected` means an authority refused the proposed selection or closed the question without adopting an option. `superseded` means a later decision replaces this one. Publication of this record is a separate fact from this state. |
| Alternative | One or more options actually considered, or an explicit statement that none was credible. | Name and describe each option. Include no-change when it is a credible option. Name screened-out options and the reason they were not compared. Do not add a filler option. |
| Comparison | One account of how the compared alternatives fare against the criteria used. | Use the criteria this record actually applied. Identify any supporting calculation or comparison record and its locator when one exists. Give each judgment's basis; use numerical scores only when the criteria, method, and supporting evidence are established. |
| Decision statement | One statement matching the state. | An `accepted` statement names the selected option. A `proposed` statement calls any preferred option a recommendation. A `rejected` statement says what was refused. A `superseded` statement keeps the historical choice and points to the successor. |
| Authority evidence | Required for `accepted` and `rejected`. | Identify who decided, the scope, and the date when known. Cite a separate approval record only when one exists. While `proposed`, cite a review only as a review. A review is not a selection or a refusal. |
| Consequences | One account of favorable effects, adverse effects, risks, and affected obligations. | Address all four. For any of them that was not assessed, say so. Label expected effects as expected. |
| Implementation | One statement whose content depends on the state. | `accepted` identifies required changes, accountable roles, and the conformance check, or says implementation is not established. `proposed` and `rejected` state that implementation is not authorized. `superseded` points further work to the successor and identifies work already done only when that work occurred. Do not invent a commit, owner, or verification result. |
| Revisit condition | One or more conditions, or an explicit statement that none is identified. | Include reversal conditions, expiring assumptions, and reevaluation triggers when they exist. Do not invent a review date. |
| Prior decision | Zero or one. | Cite the decision this record replaces only when it does. Coexistence is not replacement. |
| Successor | Required when the state is `superseded`; otherwise zero or one. | Name the decision that replaces this one. When the successor is not established, the state remains the earlier state and the gap stays visible. |
| Architecture subject | Zero or more real entities, concerns, views, or models. | Cite subjects this decision affects. When the affected subject is not identified, say so. After assessment, an empty list means none were identified. |

Use prose for context, rationale, and consequences. Use a list or table for alternatives, with the disposition of each option visible. Use a comparison table only when the criteria and judgments are real. Do not add an empty option row or a generic document-control block.

## Quality criteria

- The record answers one decision question. A second unrelated choice is a separate record.
- `accepted` names one option and an authority whose scope covers that option. `proposed` text keeps any preferred option labeled as a recommendation.
- `rejected` cites a refusal. Absence of a decision remains `proposed`.
- `superseded` identifies the successor and leaves further implementation to that successor.
- Considered alternatives, including those set aside, remain visible in the rationale.
- Adverse consequences and risks are stated or explicitly not assessed.
- No score, approval, implementation result, or conformance claim appears without an identified source.
