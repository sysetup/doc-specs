# Verification evidence record specification

## Identity and selection

- **Specification ID:** `VERIFICATION-EVIDENCE@core`.
- **Purpose:** Record actual observations showing whether identified technical requirements or specifications were met at a stated configuration.
- **Intended readers:** Verification leads, requirement owners, reviewers, and anyone who later relies on a conformance result.
- **Decision or action supported:** See which conformance subjects were observed, under which configuration and method, what the comparison showed, and which facets remain undemonstrated.
- **Use when:** A verification activity has acquired observations, or an assessed verification scope closed with none acquired, and those facts must be bound to the technical subjects they address.
- **Scope boundaries:** Observed conformity with identified technical obligations at the assessed configuration, with each conclusion limited to the facets and conditions actually examined.

## Authoring inputs and unresolved facts

Obtain the conformance question, the technical subjects and their editions, the configuration the conclusion applies to, the method and any procedure edition actually used, the observations or artifact locations, integrity and timing, the criterion and comparison, who performed the work, any review that occurred, and any decision that accepted the evidence. Obtain what was planned, what was acquired, and every failure or separate retest.

If a subject, configuration, criterion, observation, digest, or time is unknown, state the gap and do not treat it as a pass. Do not reconstruct a requirement from memory or invent a digest, a checker, an identifier, or an acceptance decision. A planned procedure is not an observation. Cite a requirement, specification, procedure, run, review, or decision only when that record exists; otherwise state the subject, method, or criterion in this record.

## Finished-document contract

- **Title:** Name the item or requirement set and identify the document as a verification evidence record.
- **Frontmatter:** None. Begin with the GFM title. Subjects, configuration, and results belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State the package boundary before the evidence items. State sufficiency and limitations after the items. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Evidence package boundary | Required | State the conformance question, the configuration baseline the conclusions apply to, and the independence arrangement actually used or that it was not required or not established. State the established access permissions, sensitive-data handling conditions, and retention periods for the evidence, identifying any that are unknown. Separate planned evidence from acquired evidence. Keep failed observations and later retests as separate facts. |
| Evidence items | Required | Give one item for each distinct observation, analysis, or assessment attempt. When no assessment was attempted and no observation acquired, say so without fabricating an acquired item. If an attempt occurred but its observation was not captured, record the attempt and the gap as inconclusive. Include a proposed or planned item only when needed to identify expected work that did not occur; it has no result. |
| Sufficiency and limitations | Required | State which specified-requirement or specification facets and conditions the acquired observations demonstrated, and which they did not. State uncertainty, sampling, configuration drift, unexamined aspects, and unresolved findings. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Package question | One conformance question for this record. | State the conformity to be assessed with identified technical requirements or specifications. |
| Subject | One or more subjects on each item. | Identify the technical requirement or specification by title or ID, edition, and locator when that record exists. When no separate record exists, state the exact technical obligation in the item. Do not invent an identifier. |
| Procedure or method | One method for each attempted item. | Identify the method actually used to assess the stated technical obligation. Cite the procedure or conformance-method record and its edition when one was used; otherwise state the method in the item. Identify how the method produced the observation used for the comparison. A `pass` requires an identified method and an actual observation supporting the criterion comparison. |
| Locator | One location for each acquired item that has a separate artifact. | Name the artifact actually acquired. A planned path is not a locator. When the observation is written only in this item, say that no separate artifact exists. |
| Digest | Zero or one SHA-256 for an acquired item whose evidence is one preserved byte sequence. | Record 64 lowercase hexadecimal digits of those bytes. When the evidence is not one preserved byte sequence, do not invent a digest; the integrity statement names the binding actually used. A digest of a different file is not this evidence. |
| Integrity | One statement per attempted item. | Cover the known acquisition, provenance, custody, clock or calibration limits, and retention limits. If capture failed, say so; state an unknown limit as unknown. No acquisition or custody statement is required for a merely proposed or planned item. |
| Configuration | One actual configuration and the conditions each attempted item's conclusion applies to. | Distinguish the planned configuration from the observed one. A proposed or planned item has only a target configuration, not an assessed one. If the actual configuration is unknown, the result cannot be `pass`. Identify a synthetic fixture as synthetic; it supports a `pass` only for that fixture. |
| Execution identity | One performer or tool for each attempted item, with the observation time if captured. | Use a date-time with an explicit offset when a time was captured. If the time was not captured, say so. Do not estimate it. |
| Evidence state | One state per item. | Use `proposed`, `planned`, `executed`, `checked`, `accepted`, or `superseded`. `proposed` identifies a suggested assessment; `planned` identifies selected or scheduled work. Both mean the assessment was not performed and have no result. `executed` means an assessment was attempted, even if capture failed. `checked` requires a review that occurred. `accepted` requires a real evidence-acceptance reference. `superseded` identifies the replacing item and keeps the original result visible. |
| Result | One result for each attempted assessment; none for proposed or planned items. | Use `pass`, `fail`, or `inconclusive` only when the state is `executed`, `checked`, `accepted`, or `superseded`. `pass` requires a named criterion, an identified actual configuration, and an observation that meets the criterion. `fail` requires an observation showing the criterion was missed. `inconclusive` explains why an attempted comparison is not supportable, including a missing observation or criterion. Selected but unattempted work has no evidence result. Accepting or superseding the evidence does not change its result. |
| Criteria comparison | One comparison for each attempted assessment. | State the expected value or condition and the observed value when captured, with units, bounds, and uncertainty where the criterion uses them. State explicitly when the observation or criterion is missing, and name any uncovered facet of that subject. |
| Review | One statement per item. | Name the checker, date, checks, and limits when a review occurred. If none occurred, say that review has not occurred. Do not invent an independent reviewer. Claimed independence must match who performed the work and who checked it. |
| Evidence acceptance | Zero or one reference. | Cite a real decision that accepted this evidence item. Required when the state is `accepted`. State the decision maker, date, evidence scope accepted, and conditions of that decision. When no such decision exists, say so. |
| Coverage | One statement for the package. | Name the technical facets and conditions actually demonstrated and those not demonstrated. A pass on one facet is not coverage of the subject or of the wider requirement set. |
| Limitation | One statement for the package. | Keep sampling, drift, conflicting observations, and unresolved findings visible. A later retest is a different item and does not erase the earlier result. |

Use prose for the question, the planned-versus-acquired split, and the limitations. Use one row or block per evidence item so the subject, configuration, comparison, and result stay visible. Do not add a blank row, a generic document-lifecycle block, or an identifier pattern.

## Quality criteria

- Every `pass` or `fail` names the technical subject, the criterion, the actual configuration, and the observation. Unknown configuration or an unnamed criterion is not a `pass`.
- Proposed or planned items have no result. An attempted assessment without a usable observation is `inconclusive`; selected work that was never attempted is not reported as an evidence result.
- For an acquired item, a digest matches its bytes or is omitted with an integrity statement. Failures and separate retests both remain.
- Coverage identifies demonstrated and undemonstrated facets and conditions, with conclusions bounded by the acquired observations.
- A cited requirement, specification, procedure, run, review, or acceptance decision exists and identifies the actual record and edition used.
