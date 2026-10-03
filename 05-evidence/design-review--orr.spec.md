# Operational readiness review record specification

## Identity and selection

- **Specification ID:** `DESIGN-REVIEW@orr`.
- **Purpose:** Record one Operational Readiness Review that was actually held, including whether the system and its support elements reflect the deployed state under review and are operationally ready. Support elements include the hardware, software, personnel, procedures, supporting capabilities, and user documentation the operation requires.
- **Intended readers:** The review chair, reviewers, operations leads, technical authority, project leads, and anyone who later relies on this gate's evidence and disposition.
- **Decision or action supported:** Readers can tell whether the reviewed system and its support organization were operationally ready under the constraints and residual risk the review applied, and what the review authority decided.
- **Use when:** An Operational Readiness Review has been held and its entrance evidence, readiness assessment, findings, actions, and disposition must be recorded.
- **Scope boundaries:** Cover the operational-readiness question, evidence examined, findings, actions, and disposition of one held review. Identify examined products by edition and locator, and include only the content needed to explain the review's assessments.

## Authoring inputs and unresolved facts

Obtain the review identity and actual date or sessions; the system boundary and the deployed configuration reviewed; the support organization and the operational products, procedures, training, and facilities the review examined; the verification status and residual-risk evidence the review applied; the chair, reviewers, decision authority, and any project-defined independence or quorum rule; the explicit entrance and success criteria established for this review, with their project record identity, edition, locator, and authorized changes; the products and evidence examined; findings, disagreements, and actions; and the disposition made.

State the complete criteria supplied in the project data for this review and account for every criterion and authorized omission. Flight and ground support are separate elements only when the reviewed system has that split. Cite each examined edition and state the evidence that supports each assessment; a locator alone leaves an assessment unsupported. If the review was not held, do not write this record. If the deployed configuration, the criteria, or the decision authority is unknown, state the gap and do not record `proceed` or `proceed-with-conditions`. Do not invent training completion, a closed anomaly, accepted residual risk, or a favorable disposition.

## Finished-document contract

- **Title:** Name the system of interest and identify the document as an Operational Readiness Review record.
- **Frontmatter:** None. Begin with the GFM title. Review identity, criteria, and disposition belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Identify the held review, the deployed configuration, and the authority before the criteria. Present entrance results before the operational-readiness assessment. Present the disposition after the findings. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Review identity and authority | Required | Identify one held Operational Readiness Review, the system boundary, the deployed configuration reviewed, the support organization in scope, the actual date or sessions, the chair, reviewers, and decision authority. State any independence or quorum result the project requires. |
| Adopted criteria | Required | State every entrance and success criterion established by the project for this ORR, including its required evidence and assessment rule. Identify the project criteria record, edition, and locator. Record each authorized omission or change, its reason, and its decision maker. If no criteria were established, say so. |
| Entrance results | Required | Give one entry for each applied entrance criterion, including the required product and revision, the evidence examined, the assessment, and the rationale. Cite operational products, procedures, training, support capability, verification status, residual-risk evidence, and a runtime-environment target when the adopted criteria require them. Explain how the examined evidence supports the assessment. |
| Operational-readiness assessment, findings, and actions | Required | Assess whether the system and the support elements the review examined reflect the deployed state and are operationally ready, including unresolved constraints and residual risk when the adopted criteria address them. Assess each applied success criterion. Record findings, severity, disagreements, and actions actually assigned. |
| Disposition | Required | Record one disposition by the identified review authority and the activity it addresses. State imposed conditions, or state that none were imposed. A decision to proceed records an operational-readiness judgment only to the extent the authority recorded; its effect is limited to that judgment. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Review identity | One stable identity for one held ORR. | Bind it to the system, the deployed configuration, and the actual date or session. A later repeat review is a different record. |
| Deployed configuration | One configuration the review examined for operations. | Identify the actual deployed state by title or ID, edition, and locator. Identify a proposed target or a configuration changed after the review separately, and bind each readiness assessment to the state actually examined. |
| Support elements | The hardware, software, personnel, procedures, supporting capabilities, and user documentation in the review's operational scope. | Identify the elements examined. Flight and ground support are distinguished only when the system has that split. An element the adopted criteria require and the review did not examine stays `not-assessed`. |
| Verification and residual risk | The verification or validation status and the residual-risk evidence the review applied. | Identify the examined project evidence and its date or edition. Report the existing verification or validation status, distinguishing completed results from planned work. State residual risk as accepted only when the record identifies the decision maker who accepted it in a real decision and the scope of that acceptance. If no such decision exists, residual risk stays unaccepted. |
| Decision authority | One chair or deciding authority, and the reviewers who participated. | Record a missing required independent reviewer or quorum as a review-control defect. Do not invent a participant. |
| Criteria set | One project-established ORR criteria set, or one explicit statement that none was established. | State the complete entrance and success criteria, required evidence, and assessment rules. Give the project record title or ID, edition, and locator. Account for each criterion and authorized omission. |
| Entrance or success entry | One entry for each criterion the review applied. | State the explicit criterion and its project record locator, required product or evidence, evidence examined, rationale, and one assessment. Use `not-assessed` when no assessment was performed, `met` when the examined evidence satisfies the criterion, `not-met` when it does not, or `not-applicable` for a documented omission or scope limit accepted by the identified decision maker. Identify the reviewer's basis and any accepted exception. |
| Operational-readiness assessment | One assessment of the reviewed system and support organization. | Explain the evidence supporting whether the examined elements reflect the deployed state and are ready for the operations in scope, to the extent of the adopted success criteria. |
| Finding | Zero or more findings from this review. | Tie each finding to an operational element, criterion, or examined evidence, and state severity. Record a stated disagreement, or state that none was recorded. |
| Action | Zero or more actions this review assigned. | Give the action, owner or unassigned state, and due or hold point. Record closure evidence only when closure occurred. |
| Disposition | One value for this review. | Use `not-decided`, `proceed`, `proceed-with-conditions`, `repeat`, or `stop`. Record a reviewer recommendation and a different authority's decision separately when both exist. |
| Condition | Zero or more conditions the disposition imposes. | Required as explicit content when the disposition is `proceed-with-conditions`. Each condition states whether examined closure evidence supports closure, the condition remains open, or it was accepted unresolved. When none was imposed, say so. |
| Next activity | One statement of the activity the review question addressed. | Identify the operations for which the board assessed readiness and the limits or hold points it recorded. |
| Separate approval | Zero or one reference to a real approval, release, or authorization record. | Cite it only when it exists. `not-decided` means the review authority has not decided. If that authority decided and a separate record is still required for effect, keep the board's disposition and state that it is not effective as release or operational authorization. |

Use prose for the operational-readiness conclusion and authority. Use a table or equivalent entries for criteria and actions, separating the adopted criterion, the evidence examined, and the assessment. Do not add blank rows, a generic document-lifecycle block, or a criteria table the project did not adopt.

## Quality criteria

- The record identifies an ORR that was held, the deployed configuration examined, and the project criteria edition actually applied.
- The assessment covers the system and the support elements the review examined, within the adopted success criteria. Unexamined required products stay `not-assessed`.
- Every `met` or `not-met` result identifies the explicit criterion and cites evidence examined at the review. Every project-established criterion has an entry or a documented authorized omission.
- Open constraints, unmet criteria, disagreements, and open actions remain visible. Accepted residual risk names its authority. Verification status is the status examined, not a planned campaign.
- The disposition matches the assessments. `proceed` or `proceed-with-conditions` with a required criterion `not-assessed` or `not-met` also records the accepted exception and its authority.
- The disposition uses one of the five defined review values and reports the board's operational-readiness judgment. Its recorded effect respects any separate approval requirement and the actual status of that approval.
