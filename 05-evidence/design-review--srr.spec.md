# System requirements review record specification

## Identity and selection

- **Specification ID:** `DESIGN-REVIEW@srr`.
- **Purpose:** Record one System Requirements Review that was actually held, including whether the system of interest's functional and performance requirements, and the planned technical work needed to satisfy them, are credible enough to proceed.
- **Intended readers:** The review chair, reviewers, requirements authors, technical authority, project leads, and anyone who later relies on this gate's evidence and disposition.
- **Decision or action supported:** Readers can tell whether the reviewed requirements are responsive to the project's needs and parent requirements, reflect the intended use, and are credible within the project scope, and what the review authority decided.
- **Use when:** A System Requirements Review has been held and its entrance evidence, success assessment, findings, actions, and disposition must be recorded.
- **Scope boundaries:** Record the held SRR's assessment of the reviewed requirements and planned technical work. Identify examined material by edition and locator without reproducing it. Bind the disposition to the activity, scope, and conditions the review authority actually decided.

## Authoring inputs and unresolved facts

Obtain the review identity and actual date or sessions; the system-of-interest boundary; the requirements edition and any project needs, parent requirements, or intended-use material actually reviewed; the planned technical work the review examined; prior review dispositions the adopted entrance criteria require; the chair, reviewers, decision authority, and any independence or quorum rule; the project's adopted entrance and success criteria, including each criterion's text, satisfaction conditions, scope limits, criteria-set identity and edition, and authorized changes or omissions; the evidence examined; findings, disagreements, and actions; and the disposition made.

Account for every criterion in the supplied project criteria set and every authorized omission. Record the criteria explicitly rather than substituting a summary or citation. Identify the reviewed requirements, project needs, parent requirements, intended-use material, concepts, and plans by identity, edition, and locator without reproducing their wording. Bind each assessment to evidence actually examined. If the review was not held, do not write this record. If the requirements edition, the criteria, or the decision authority is unknown, state the gap and do not record `proceed` or `proceed-with-conditions`. Do not invent traceability, feasibility, open-item plans, concurrence, or a favorable disposition.

## Finished-document contract

- **Title:** Name the system of interest and identify the document as a System Requirements Review record.
- **Frontmatter:** None. Begin with the GFM title. Review identity, criteria, and disposition belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Identify the held review, the requirements edition, and the authority before the criteria. Present entrance results before the requirements assessment. Present the disposition after the findings. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Review identity and authority | Required | Identify one held System Requirements Review, the system boundary, the requirements edition reviewed, the actual date or sessions, the chair, reviewers, and decision authority. State any independence or quorum result the project requires. Identify the scope of the authority's decision. |
| Adopted criteria | Required | Identify the project's entrance and success criteria set and its edition. State each criterion's text, satisfaction conditions, scope limits, and locator within the set. Record each authorized omission or change, its reason, and its deciding authority. If no criteria were established, say so. |
| Entrance results | Required | Give one entry for each applied entrance criterion, including the required product and revision, the evidence examined, the assessment, and the rationale. Identify requirements, technical plans, and any concept, risk, or prior-review material the adopted criteria require, at the maturity those criteria state. Bind each evidence locator to the examined artifact and edition. |
| Requirements assessment, findings, and actions | Required | Assess whether the reviewed requirements are responsive to the project's needs and parent requirements, reflect intended use, and are credible within the project scope, together with the planned technical work the review examined. Assess each applied success criterion. Record traceability gaps, unresolved items, and open-item plans when the adopted criteria address them. Record findings, severity, disagreements, and actions actually assigned. Do not copy the requirements text. |
| Disposition | Required | Record one disposition by the identified review authority and the activity it addresses. State imposed conditions, or state that none were imposed. A decision to proceed states the assessed credibility of the reviewed requirements and its effective scope. Identify any separately granted approval by its actual authority and decision record. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Review identity | One stable identity for one held SRR. | Bind it to the system, the requirements edition, and the actual date or session. A later repeat review is a different record. |
| Requirements edition | One requirements set the review examined. | Identify the specification or equivalent source by title or ID, edition, and locator. Do not copy its wording. Proposed wording that was not in the reviewed edition stays outside the assessed set. |
| Project need or parent requirement | The needs and parent requirements the review used as the responsiveness basis. | Identify their edition and locator. If the project has no parent requirements, state the project need actually used. Do not invent a parent document. |
| Decision authority | One chair or deciding authority, and the reviewers who participated. | Record a missing required independent reviewer or quorum as a review-control defect. Do not invent a participant. |
| Criteria set | One adopted project SRR criteria set, or one explicit statement that none was established. | Give title or ID, edition, and locator. Include the complete criterion text, satisfaction conditions, and scope limits. Account for each adopted criterion and each authorized omission. |
| Entrance or success entry | One entry for each criterion the review applied. | State the criterion, its locator within the project set, satisfaction conditions, required product or evidence, evidence examined, and one assessment: `not-assessed` for an unevaluated criterion, `met` when examined evidence satisfies it, `not-met` when it does not, or `not-applicable` for an accepted omission or scope limit. `not-applicable` requires a documented reason and the authority that accepted it. The rationale names the reviewer basis and any exception. |
| Credibility assessment | One assessment of the reviewed requirements and the planned technical work examined with them. | Address responsiveness, consistency with intended use, and credibility within scope, as the adopted success criteria require. Support the assessment with examined evidence without copying requirement wording. An open item needs its examined disposition: accepted plan, unresolved, or outside the adopted criteria. |
| Finding | Zero or more findings from this review. | Tie each finding to a requirement, criterion, or examined evidence, and state severity. Record a stated disagreement, or state that none was recorded. |
| Action | Zero or more actions this review assigned. | Give the action, owner or unassigned state, and due or hold point. Record closure evidence only when closure occurred. |
| Disposition | One value for this review. | Use `not-decided`, `proceed`, `proceed-with-conditions`, `repeat`, or `stop`. Record a reviewer recommendation and a different authority's decision separately when both exist. |
| Condition | Zero or more conditions the disposition imposes. | Required as explicit content when the disposition is `proceed-with-conditions`. Each condition states whether examined closure evidence supports closure, the condition remains open, or it was accepted unresolved. When none was imposed, say so. |
| Next activity | One statement of the activity the review question addressed. | Name the activity the review authority judged credible to proceed toward and the scope and conditions of that judgment. |
| Separate approval | Zero or one reference to a real approval or acceptance record. | Cite it only when it exists, with its authority, scope, and effective status. Establish any effective requirements-baseline approval or detailed-design authorization from its actual separate decision evidence. `not-decided` means the review authority has not decided. If an additional recorded decision is required for the disposition to take effect, retain the actual disposition and identify the pending decision and resulting limit on its effect. |

Use prose for the credibility conclusion and authority. Use a table or equivalent entries for criteria and actions, separating the adopted criterion, the evidence examined, and the assessment. Do not add blank rows, a generic document-lifecycle block, or criteria the project did not adopt.

## Quality criteria

- The record is an SRR that was held, against an identified requirements edition and an identified project criteria edition whose criteria are explicit in the record.
- Responsiveness, intended use, and credibility are assessed against the project needs, parent requirements, intended-use material, and planned technical work the review examined. Missing examined material or missing criteria remains a limitation.
- Every `met` or `not-met` result cites evidence examined at the review. `not-assessed` is not success. `not-applicable` has an accepted reason.
- Traceability gaps and unresolved items stay visible when the adopted criteria cover them. An accepted plan for an open item is identified; an absent plan is not described as accepted.
- The disposition matches the assessments. `proceed` or `proceed-with-conditions` with a required criterion `not-assessed` or `not-met` also records the accepted exception and its authority.
- Open actions and recorded disagreements remain visible. The disposition uses `not-decided`, `proceed`, `proceed-with-conditions`, `repeat`, or `stop`, identifies its deciding authority, and states its scope, conditions, and effective status. The credibility assessment stays bound to the reviewed requirements edition and planned technical work.
