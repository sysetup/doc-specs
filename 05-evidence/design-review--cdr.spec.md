# Critical design review record specification

## Identity and selection

- **Specification ID:** `DESIGN-REVIEW@cdr`.
- **Purpose:** Record one Critical Design Review that was actually held, including whether the board judges the detailed design mature enough for fabrication, assembly, integration, and test, and whether the technical effort is on track to meet the functional and performance requirements within the cost, schedule, and risk constraints the review applied.
- **Intended readers:** The review chair, reviewers, design leads, technical authority, project leads, and anyone who later relies on this gate's evidence and disposition.
- **Decision or action supported:** Readers can tell whether the reviewed detailed design is mature enough for the fabrication, assembly, integration, and test the review considered, under the requirements and constraints the review applied, and what the review authority decided.
- **Use when:** A Critical Design Review has been held and its entrance evidence, design-maturity assessment, findings, actions, and disposition must be recorded.
- **Scope boundaries:** Cover the detailed-design maturity question, evidence examined, findings, actions, and disposition of one held review. Identify examined products by edition and locator, and include only the content needed to explain the review's assessments.

## Authoring inputs and unresolved facts

Obtain the review identity and actual date or sessions; the system-of-interest boundary; the detailed-design edition reviewed and the requirements edition it was assessed against; the cost, schedule, margin, resource, and risk constraints the review applied; the chair, reviewers, decision authority, and any project-defined independence or quorum rule; the explicit entrance and success criteria established for this review, with their project record identity, edition, locator, and authorized changes; the products and evidence examined; findings, disagreements, and actions; and the disposition made.

State the complete criteria supplied in the project data for this review and account for every criterion and authorized omission. Interfaces, margins, product-baseline documentation, verification and validation planning, integration and test planning, runtime-environment targets, and risk treatment are entrance or success evidence only when those criteria require them. Cite each examined edition and state the evidence that supports each assessment; a locator alone leaves an assessment unsupported. If the review was not held, do not write this record. If the design edition, the requirements edition, the criteria, or the decision authority is unknown, state the gap and do not record `proceed` or `proceed-with-conditions`. Do not invent margins, interface agreement, baseline completeness, or a favorable disposition.

## Finished-document contract

- **Title:** Name the system of interest and identify the document as a Critical Design Review record.
- **Frontmatter:** None. Begin with the GFM title. Review identity, criteria, and disposition belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Identify the held review, the detailed-design edition, and the authority before the criteria. Present entrance results before the design-maturity assessment. Present the disposition after the findings. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Review identity and authority | Required | Identify one held Critical Design Review, the system boundary, the detailed-design edition, the requirements edition used as the assessment basis, the actual date or sessions, the chair, reviewers, and decision authority. State any independence or quorum result the project requires. |
| Adopted criteria | Required | State every entrance and success criterion established by the project for this CDR, including its required evidence and assessment rule. Identify the project criteria record, edition, and locator. Record each authorized omission or change, its reason, and its decision maker. If no criteria were established, say so. |
| Entrance results | Required | Give one entry for each applied entrance criterion, including the required product and revision, the evidence examined, the assessment, and the rationale. Cite the detailed design when the adopted criteria require it. Cite build-to data, verification and validation products, support products, an integration plan, a runtime-environment target, and prior-review dispositions when those criteria require them. Explain how the examined evidence supports the assessment. |
| Design-maturity assessment, findings, and actions | Required | Assess whether the detailed design is mature enough for fabrication, assembly, integration, and test, and whether the technical effort is on track to meet the functional and performance requirements within the cost, schedule, and risk constraints the review applied. Assess each applied success criterion, including margins, interfaces, resources, product baseline, verification and validation, integration and test planning, and risks when the adopted criteria include them. Record findings, severity, disagreements, and actions actually assigned. |
| Disposition | Required | Record one disposition by the identified review authority and the activity it addresses. State imposed conditions, or state that none were imposed. A decision to proceed records a detailed-design maturity judgment for the work the review considered; its effect is limited to that judgment. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Review identity | One stable identity for one held CDR. | Bind it to the system, the detailed-design edition, and the actual date or session. A later repeat review is a different record. |
| Detailed-design edition | One design definition the review examined. | Identify it by title or ID, edition, and locator. Name a baseline only when that is the actual status of the examined edition. Identify any proposed or subsequently changed edition separately. |
| Requirements basis | One requirements edition against which the design was assessed. | Identify its title or ID and edition. Do not assess the design against requirements that were not in that edition unless the review records them as an explicit exception. |
| Constraints and risk | The cost, schedule, margin, resource, and risk picture the review applied. | Identify the examined source and its date or edition. A constraint the project did not apply is not added. An unexamined constraint that the adopted criteria require stays `not-assessed`. |
| Decision authority | One chair or deciding authority, and the reviewers who participated. | Record a missing required independent reviewer or quorum as a review-control defect. Do not invent a participant. |
| Criteria set | One project-established CDR criteria set, or one explicit statement that none was established. | State the complete entrance and success criteria, required evidence, and assessment rules. Give the project record title or ID, edition, and locator. Account for each criterion and authorized omission. |
| Entrance or success entry | One entry for each criterion the review applied. | State the explicit criterion and its project record locator, required product or evidence, evidence examined, rationale, and one assessment. Use `not-assessed` when no assessment was performed, `met` when the examined evidence satisfies the criterion, `not-met` when it does not, or `not-applicable` for a documented omission or scope limit accepted by the identified decision maker. Identify the reviewer's basis and any accepted exception. |
| Design-maturity assessment | One assessment of the reviewed detailed design. | Explain the evidence supporting maturity for fabrication, assembly, integration, and test, and whether the technical effort is on track to meet the cited functional and performance requirements within the constraints the review applied, to the extent of the adopted success criteria. |
| Finding | Zero or more findings from this review. | Tie each finding to a design element, requirement, criterion, or examined evidence, and state severity. Record a stated disagreement, or state that none was recorded. |
| Action | Zero or more actions this review assigned. | Give the action, owner or unassigned state, and due or hold point. Record closure evidence only when closure occurred. |
| Disposition | One value for this review. | Use `not-decided`, `proceed`, `proceed-with-conditions`, `repeat`, or `stop`. Record a reviewer recommendation and a different authority's decision separately when both exist. |
| Condition | Zero or more conditions the disposition imposes. | Required as explicit content when the disposition is `proceed-with-conditions`. Each condition states whether examined closure evidence supports closure, the condition remains open, or it was accepted unresolved. When none was imposed, say so. |
| Next activity | One statement of the activity the review question addressed. | Identify the fabrication, assembly, integration, or test activity for which the board assessed detailed-design maturity, and the limits or hold points it recorded. |
| Separate approval | Zero or one reference to a real approval, acceptance, or baseline-release record. | Cite it only when it exists. `not-decided` means the review authority has not decided. If that authority decided and a separate record is still required for effect, keep the board's disposition and state that it is not effective as baseline release, fabrication authorization, or acceptance. |

Use prose for the design-maturity conclusion and authority. Use a table or equivalent entries for criteria and actions, separating the adopted criterion, the evidence examined, and the assessment. A figure may identify the reviewed design boundary when its source edition is stated. Do not add blank rows, a generic document-lifecycle block, or a criteria table the project did not adopt.

## Quality criteria

- The record identifies a CDR that was held, the detailed-design edition examined, the requirements edition, and the project criteria edition actually applied.
- The assessment covers detailed-design maturity for fabrication, assembly, integration, and test, and the requirements and constraints the review applied, within the adopted success criteria. Unexamined required products stay `not-assessed`.
- Every `met` or `not-met` result identifies the explicit criterion and cites evidence examined at the review. Every project-established criterion has an entry or a documented authorized omission.
- Open items, unmet criteria, disagreements, and open actions remain visible. An accepted exception names its authority.
- The disposition matches the assessments. `proceed` or `proceed-with-conditions` with a required criterion `not-assessed` or `not-met` also records the accepted exception and its authority.
- The disposition uses one of the five defined review values and reports the board's detailed-design maturity judgment. Its recorded effect respects any separate approval requirement and the actual status of that approval.
