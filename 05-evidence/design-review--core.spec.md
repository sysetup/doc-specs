# Project-defined technical review record specification

## Identity and selection

- **Specification ID:** `DESIGN-REVIEW@core`.
- **Purpose:** Record one technical or lifecycle review that was actually held under criteria the project defined for that review, including the question decided, the evidence examined, the findings and actions, and the review authority's disposition.
- **Intended readers:** The review chair, reviewers, technical authority, project leads, and anyone who later relies on what this review examined and decided.
- **Decision or action supported:** Readers can tell whether the reviewed subject met the criteria this review adopted and what the review authority decided: proceed, proceed with conditions, repeat the review, stop, or leave the matter undecided.
- **Use when:** A project-defined technical or lifecycle review has been held and its evidence and disposition must be recorded. This includes a peer review of a product, design, or lifecycle subject under a question and criteria defined for that review.
- **Scope boundaries:** Cover the project-defined review question, examined subject revision, criterion assessments, findings, actions, and disposition of one held review. Source-code inspection and examination against an assurance baseline are outside this scope. Identify examined products by edition and locator, and include only the content needed to explain the review's assessments.

## Authoring inputs and unresolved facts

Obtain the review identity; the actual date or session dates; the subject and the revision reviewed; the project boundary; the question the review was convened to decide; the chair, reviewers, and decision authority; any project-defined independence or quorum rule the project applied; the explicit entrance and success criteria established for this review, with their project record identity, edition, locator, and authorized changes; the products and evidence actually examined; findings, disagreements, and assigned actions; and the disposition the review authority made.

If the review was not held, do not write this record. If it was held but the criteria, the reviewed revision, or the decision authority cannot be established, state that gap and its effect; it cannot support `proceed` or `proceed-with-conditions`. State the complete criteria supplied in the project data for this review. Cite the reviewed revision by identity and edition, and state the evidence supporting each assessment; a locator alone leaves an assessment unsupported. Record `not-assessed` only when no assessment was performed and `not-decided` only when the review authority has not decided. A missing attendee list, action, or separate approval record stays missing unless the project actually has it. Do not invent owners, dates, evidence, dissent, or a favorable disposition.

## Finished-document contract

- **Title:** Name the reviewed subject and identify the document as a project-defined technical or lifecycle review record.
- **Frontmatter:** None. Begin with the GFM title. Review identity, criteria, and disposition belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Identify the held review and its authority before the criteria. Present entrance results before the technical assessment. Present the disposition after the findings. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Review identity and authority | Required | Identify one held review, its subject and reviewed revision, boundary, actual date or sessions, chair, reviewers, and decision authority. State the question this review was convened to decide. Record a required independence or quorum result when the project has such a rule. |
| Adopted criteria | Required | State every entrance and success criterion established by the project for this review, including its required evidence and assessment rule. Identify the project criteria record, edition, and locator. Record each authorized omission or change, its reason, and its decision maker. If no criteria were established, say so. |
| Entrance results | Required | Give one entry for each entrance criterion the review applied. Record the required product and revision, the evidence actually examined, the assessment, the rationale, and any exception. A review that applied no entrance criteria states that fact here. |
| Assessment, findings, and actions | Required | Assess the review question against each applied success criterion and the evidence examined. Record findings, their severity, and any reviewer disagreement. Record actions that were actually assigned, including owner or an explicit unassigned state, the due or hold point, and closure evidence only when closure occurred. |
| Disposition | Required | Record one disposition by the identified review authority and the activity that disposition addresses. State imposed conditions, or state that none were imposed. Its effect is limited to the review question decided. Cite a separate approval, acceptance, baseline-release, or authorization record only when that record exists, and state its actual status and effect. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Review identity | One stable identity for one held review. | Bind it to the subject, boundary, and actual date or session. A later repeat review is a different record. A planned meeting that did not occur has no review identity here. |
| Reviewed revision | One subject revision the review examined. | Identify it by project ID, title, and edition or equivalent locator. Identify a revision proposed or approved after the review separately, and bind each assessment to the revision actually examined. |
| Decision authority | One chair or deciding authority, and the reviewers who participated. | Name roles from the project. If a required independent reviewer or quorum was absent, record that defect. Do not invent a participant or an authority. |
| Criteria set | One project-established criteria set, or one explicit statement that no set was established. | State the complete entrance and success criteria, required evidence, and assessment rules. Give the project record title or ID, edition, and locator. An authorized omission names the omitted criterion, the reason, and the decision maker. |
| Entrance or success entry | One entry for each criterion the review applied. | State the explicit criterion and its project record locator, required product or evidence, evidence examined, rationale, and one assessment. Use `not-assessed` when no assessment was performed, `met` when the examined evidence satisfies the criterion, `not-met` when it does not, or `not-applicable` for a documented omission or scope limit accepted by the identified decision maker. `not-assessed` and `not-met` remain visible. Identify the reviewer's basis and any accepted exception. |
| Finding | Zero or more findings from this review. | Tie each finding to a criterion or to examined evidence, and state its severity. Record a stated disagreement, or state that no disagreement was recorded. Do not convert silence into consensus. |
| Action | Zero or more actions this review assigned. | Give the action, the owner or the fact that no owner was assigned, and the due or hold point. Closure evidence appears only for an action that was actually closed. An open action stays open. A link to an existing action register is optional. |
| Disposition | One value for this review. | Use `not-decided`, `proceed`, `proceed-with-conditions`, `repeat`, or `stop`. The identified review authority makes the disposition. A recommendation from reviewers and a decision by a different authority are both recorded when they differ. |
| Condition | Zero or more conditions the disposition imposes. | Required as explicit content when the disposition is `proceed-with-conditions`. Each condition has its hold or due point and whether examined closure evidence supports closure, the condition remains open, or it was accepted unresolved. When no condition was imposed, say so. |
| Next activity | One statement of the activity the review question addressed. | Identify that activity and the limits or hold points the review recorded. |
| Separate approval | Zero or one reference to a real approval, acceptance, baseline-release, or authorization record. | Cite it only when the record exists. `not-decided` means the review authority has not decided. If that authority decided and a separate record is still required for effect, keep the board's disposition and state that it is not effective as approval, acceptance, baseline release, or authorization. |

Use prose for the review question, authority, and narrative assessment. Use a table or equivalent entries for entrance criteria, success criteria, and actions, with columns that distinguish the adopted criterion, the evidence examined, and the assessment. A figure may show the reviewed boundary only when its source is identified. Do not add blank criterion rows, a generic document-lifecycle block, or a completion checklist.

## Quality criteria

- The record identifies a review that was held, the revision examined, the decision authority, and the project criteria edition actually applied.
- Every `met` or `not-met` assessment cites the criterion and the evidence examined. Missing criteria stay unresolved and cannot support `proceed` or `proceed-with-conditions`. Missing evidence cannot support `met` or `not-met`; a favorable disposition despite an unassessed criterion requires the documented accepted exception and its decision maker.
- `not-applicable` is limited to an authorized omission or a scope limit the project accepted. It is not a substitute for an assessment the review did not perform.
- Findings, disagreements, unmet criteria, and open actions remain visible. Closure is recorded only with closure evidence.
- The disposition matches the assessments. A favorable disposition that leaves a required criterion `not-assessed` or `not-met` also records the accepted exception and its authority.
- The review question is the one the project convened. Every project-established criterion has an entry or a documented authorized omission.
- The disposition uses one of the five defined review values and reports the authority's decision on that question. Its recorded effect respects any separate approval requirement and the actual status of that approval.
