# Validation evidence record specification

## Identity and selection

- **Specification ID:** `VALIDATION-EVIDENCE@core`.
- **Purpose:** Record actual observations showing whether a system or outcome was fit for identified stakeholder, user, business, or intended-use needs in the context that was assessed.
- **Intended readers:** Validation leads, need owners, user representatives, reviewers, and anyone who later relies on a fitness result.
- **Decision or action supported:** See which needs or intended-use conditions were observed, in which context, what the comparison showed, and which facets of fitness remain undemonstrated.
- **Use when:** A validation activity has acquired observations, or an assessed validation scope closed with none acquired, and those facts must be bound to the needs or intended-use conditions they address.
- **Scope boundaries:** Observed fitness for identified needs and intended-use conditions within the assessed context, with each conclusion limited to the observations and representation actually established.

## Authoring inputs and unresolved facts

Obtain the fitness question, the stakeholder, user, business, or intended-use subjects and their editions, the context actually assessed, the method and any procedure edition used, who participated or which proxy was used, the observations or artifact locations, integrity and timing, the evaluation criterion and comparison, any review that occurred, and any decision that accepted the evidence. Obtain what was planned, what was acquired, and every unfavorable result or separate reassessment.

If a need, context, participant, criterion, observation, or time is unknown, state the gap and do not treat it as demonstrated fitness. Base a fitness result on the stated need, assessed context, criterion, and actual observation. Do not reconstruct a need from memory or invent a participant, a digest, a checker, or an acceptance decision. Cite a need, scenario, procedure, run, review, or decision only when that record exists; otherwise state the need, context, or criterion in this record.

## Finished-document contract

- **Title:** Name the solution or need set and identify the document as a validation evidence record.
- **Frontmatter:** None. Begin with the GFM title. Needs, context, and results belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State the package boundary before the evidence items. State sufficiency and limitations after the items. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Evidence package boundary | Required | State the fitness question, the intended context, the configuration or environment the conclusions apply to, and the independence arrangement actually used or that it was not required or not established. State the established access permissions, sensitive-data handling conditions, and retention periods for the evidence, identifying any that are unknown. Separate planned evidence from acquired evidence. Keep unfavorable observations and later reassessments as separate facts. |
| Evidence items | Required | Give one item for each distinct observation, scenario execution, or assessment attempt. When no assessment was attempted and no observation acquired, say so without fabricating an acquired item. If an attempt occurred but its observation was not captured, record the attempt and the gap as inconclusive. Include a proposed or planned item only when needed to identify expected work that did not occur; it has no result. |
| Sufficiency and limitations | Required | State which stakeholder, user, business, or intended-use facets and conditions the acquired observations demonstrated, and which they did not. State uncertainty, sampling, unrepresentative context, configuration drift, unexamined aspects, and unresolved findings. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Package question | One fitness question for this record. | State the fitness to be assessed for identified stakeholder, user, business, or intended-use needs in an identified context. |
| Subject | One or more subjects on each item. | Identify the need, intended-use condition, or operational scenario by title or ID, edition, and locator when that record exists. When no separate record exists, state the exact need or condition in the item. Do not invent an identifier. Identify any technical requirement cited as supporting context and state the need or intended-use condition whose fitness is assessed. |
| Context and participants | One assessed context for each attempted item. | State the scenario or use condition actually exercised, the environment, and the participants or the proxy that stood for them. If the context or participation is unknown, the result cannot be `pass`. A laboratory condition stands for intended use only to the extent the record states that representation and its limit. |
| Procedure or method | One method for each attempted item. | Identify the method actually used to assess the stated need or intended-use condition in the assessed context. Cite the procedure and its edition when one was used; otherwise state the method in the item. Identify the observations used for the fitness comparison and explain any limits on what the method demonstrated. |
| Locator | One location for each acquired item that has a separate artifact. | Name the artifact actually acquired. A planned path is not a locator. When the observation is written only in this item, say that no separate artifact exists. |
| Digest | Zero or one SHA-256 for an acquired item whose evidence is one preserved byte sequence. | Record 64 lowercase hexadecimal digits of those bytes. When the evidence is not one preserved byte sequence, do not invent a digest; the integrity statement names the binding actually used. A digest of a different file is not this evidence. |
| Integrity | One statement per attempted item. | Cover the known acquisition, provenance, custody, clock or calibration limits, and retention limits. If capture failed, say so; state an unknown limit as unknown. No acquisition or custody statement is required for a merely proposed or planned item. |
| Configuration | One actual configuration and the conditions each attempted item's conclusion applies to. | Distinguish the planned configuration from the observed one. A proposed or planned item has only a target configuration, not an assessed one. If the actual configuration is unknown, the result cannot be `pass`. Identify a synthetic fixture or simulated user as such; it supports a `pass` only within the representation the record states. |
| Execution identity | One performer or tool for each attempted item, with the observation time if captured. | Use a date-time with an explicit offset when a time was captured. If the time was not captured, say so. Do not estimate it. This identity does not replace the participants or proxy in the assessed context. |
| Evidence state | One state per item. | Use `proposed`, `planned`, `executed`, `checked`, `accepted`, or `superseded`. `proposed` identifies a suggested assessment; `planned` identifies selected or scheduled work. Both mean the assessment was not performed and have no result. `executed` means an assessment was attempted, even if capture failed. `checked` requires a review that occurred. `accepted` requires a real evidence-acceptance reference. `superseded` identifies the replacing item and keeps the original result visible. |
| Result | One result for each attempted assessment; none for proposed or planned items. | Use `pass`, `fail`, or `inconclusive` only when the state is `executed`, `checked`, `accepted`, or `superseded`. `pass` requires an established fitness criterion, an identified context and participant or proxy, an identified actual configuration, and an observation that meets the criterion in that context. `fail` requires an observation showing the need or condition was not met. `inconclusive` explains why an attempted comparison is not supportable, including a missing observation or criterion. Selected but unattempted work has no evidence result. Accepting or superseding the evidence does not change its result. |
| Criteria comparison | One comparison for each attempted assessment. | State the expected fitness outcome and the observed outcome when captured, with units or qualitative bounds where the criterion uses them. State explicitly when the observation or criterion is missing, and name any uncovered facet of that need or condition. |
| Review | One statement per item. | Name the checker, date, checks, and limits when a review occurred. If none occurred, say that review has not occurred. Do not invent an independent reviewer or a user representative. Claimed independence must match who performed the work and who checked it. |
| Evidence acceptance | Zero or one reference. | Cite a real decision that accepted this evidence item. Required when the state is `accepted`. State the decision maker, date, evidence scope accepted, and conditions of that decision. When no such decision exists, say so. |
| Coverage | One statement for the package. | Name the need or intended-use facets and conditions actually demonstrated and those not demonstrated. A pass in one scenario is not coverage of the need or of the wider need set. |
| Limitation | One statement for the package. | Keep sampling, unrepresentative conditions, drift, conflicting observations, and unresolved findings visible. A later reassessment is a different item and does not erase the earlier result. |

Use prose for the fitness question, the context, and the limitations. Use one row or block per evidence item so the need, context, comparison, and result stay visible. Do not add a blank row, a generic document-lifecycle block, or an identifier pattern.

## Quality criteria

- Every `pass` or `fail` names the need or intended-use condition, the context or its absence, the criterion, and the observation. Unknown context, unknown participation, or an unnamed criterion is not a `pass`.
- Proposed or planned items have no result. An attempted assessment without a usable observation is `inconclusive`; selected work that was never attempted is not reported as an evidence result. Each fitness result is supported by a comparison against the stated need in the assessed context.
- For an acquired item, a digest matches its bytes or is omitted with an integrity statement. Unfavorable results and later reassessments both remain.
- Coverage identifies demonstrated and undemonstrated facets and conditions, with conclusions bounded by the acquired observations.
- A cited need, scenario, procedure, run, review, or acceptance decision exists and identifies the actual record and edition used.
