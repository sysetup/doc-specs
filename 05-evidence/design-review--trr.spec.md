# Test readiness review record specification

## Identity and selection

- **Specification ID:** `DESIGN-REVIEW@trr`.
- **Purpose:** Record one Test Readiness Review that was actually held for a specified test or series of tests, including whether the test article, test facility or environment, support personnel, and test procedures are ready for testing and for the data acquisition, reduction, and control that test requires.
- **Intended readers:** The review chair, reviewers, test lead, technical authority, project leads, and anyone who later relies on this gate's evidence and disposition.
- **Decision or action supported:** Readers can tell whether the reviewed test or series was ready to start under the objectives, controls, resources, and authority the review applied, and what the review authority decided.
- **Use when:** A Test Readiness Review has been held and its entrance evidence, readiness assessment, findings, actions, and disposition must be recorded.
- **Scope boundaries:** Record readiness to start the specified test or series, bound to the reviewed article configuration, procedures, environment, personnel, and controls. Identify examined editions without reproducing them. State the scope and conditions of the authority's actual readiness decision.

## Authoring inputs and unresolved facts

Obtain the review identity and actual date or sessions; the system or item boundary; the specified test or series, including its objectives; the test-article configuration and the procedure, environment, and facility editions reviewed; the personnel, safety, and open-issue dispositions the review examined; the chair, reviewers, decision authority, and any independence or quorum rule; the project's adopted entrance and success criteria, including each criterion's text, satisfaction conditions, scope limits, criteria-set identity and edition, and authorized changes or omissions; the products and evidence examined; findings, disagreements, and actions; and the disposition made.

Account for every criterion in the supplied project criteria set and every authorized omission. Record the criteria explicitly rather than substituting a thematic summary or citation. Objectives, configuration control, resources, safety, training, and discrepancy disposition are entrance or success evidence only when the adopted criteria require them. Identify each examined edition without reproducing it, and support readiness claims with evidence actually examined. If the review was not held, do not write this record. If the test scope, the article configuration, the criteria, or the decision authority is unknown, state the gap and do not record `proceed` or `proceed-with-conditions`. Do not invent procedure approval, personnel qualification, a closed discrepancy, or a favorable disposition. Do not record observations from a test that has not been run.

## Finished-document contract

- **Title:** Name the test or series and identify the document as a Test Readiness Review record.
- **Frontmatter:** None. Begin with the GFM title. Review identity, criteria, and disposition belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Identify the held review, the test scope, and the authority before the criteria. Present entrance results before the readiness assessment. Present the disposition after the findings. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Review identity and authority | Required | Identify one held Test Readiness Review, the item or system boundary, the specified test or series and its objectives, the article configuration, the actual date or sessions, the chair, reviewers, and decision authority. State any independence or quorum result the project requires. Identify the scope of the authority's readiness decision. |
| Adopted criteria | Required | Identify the project's entrance and success criteria set and its edition. State each criterion's text, satisfaction conditions, scope limits, and locator within the set. Record each authorized omission or change, its reason, and its deciding authority. If no criteria were established, say so. |
| Entrance results | Required | Give one entry for each applied entrance criterion, including the required product and revision, the evidence examined, the assessment, and the rationale. Identify the article, procedures, environment or facility, personnel readiness, and safety or open-issue dispositions when the adopted criteria require them. Bind each evidence locator to the examined artifact and edition. |
| Readiness assessment, findings, and actions | Required | Assess whether the reviewed test or series is ready to start with the resources, controls, criteria, and authority the review applied. Assess each applied success criterion. Record objectives, procedure and environment adequacy, configuration, personnel readiness, safety, and unresolved discrepancies when the adopted criteria include them. Record findings, severity, disagreements, and actions actually assigned. Do not copy the procedure or record a test observation. |
| Disposition | Required | Record one disposition by the identified review authority and the activity it addresses. State imposed conditions, or state that none were imposed. A decision to proceed addresses readiness to start the reviewed test or series only to the extent the authority recorded. Identify any separately granted approval by its actual authority and decision record. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Review identity | One stable identity for one held TRR. | Bind it to the specified test or series, the article configuration, and the actual date or session. A later repeat review, and a review of a different test or series, are different records. |
| Test scope | One test or one defined series this review examined. | State the objectives and the boundary of the test. Keep the assessment within the scope actually reviewed. |
| Article configuration | One configuration of the item under test. | Identify the as-built or controlled configuration the review examined, by title or ID, edition, and locator. Bind the assessment to that configuration and the review date; identify any later change separately. |
| Procedures and environment | The procedure, facility, and environment editions the review examined. | Identify each by title or ID, edition, and locator without reproducing it. Support each readiness assessment with examined evidence. A procedure or environment the adopted criteria require and the review did not examine stays `not-assessed`. |
| Personnel, safety, and open issues | The readiness of the people who will perform the test, the safety provisions examined, and the disposition of known discrepancies. | Record the examined status. An open discrepancy stays open unless the review examined a real disposition. Do not convert a planned closure into a closed item. |
| Decision authority | One chair or deciding authority, and the reviewers who participated. | Record a missing required independent reviewer, test authority, or quorum as a review-control defect. Do not invent a participant. |
| Criteria set | One adopted project TRR criteria set, or one explicit statement that none was established. | Give title or ID, edition, and locator. Include the complete criterion text, satisfaction conditions, and scope limits. Account for each adopted criterion and each authorized omission. |
| Entrance or success entry | One entry for each criterion the review applied. | State the criterion, its locator within the project set, satisfaction conditions, required product or evidence, evidence examined, and one assessment: `not-assessed` for an unevaluated criterion, `met` when examined evidence satisfies it, `not-met` when it does not, or `not-applicable` for an accepted omission or scope limit. `not-applicable` requires a documented reason and the authority that accepted it. The rationale names the reviewer basis and any exception. |
| Readiness assessment | One assessment of readiness to start the reviewed test or series. | Address article, procedures, environment, personnel, controls, and authority to the extent of the adopted success criteria. State the readiness conclusion, examined evidence, and remaining uncertainty for the reviewed test scope. |
| Finding | Zero or more findings from this review. | Tie each finding to a procedure, configuration, criterion, or examined evidence, and state severity. Record a stated disagreement, or state that none was recorded. |
| Action | Zero or more actions this review assigned. | Give the action, owner or unassigned state, and due or hold point. Record closure evidence only when closure occurred. |
| Disposition | One value for this review. | Use `not-decided`, `proceed`, `proceed-with-conditions`, `repeat`, or `stop`. Record a reviewer recommendation and a different authority's decision separately when both exist. |
| Condition | Zero or more conditions the disposition imposes. | Required as explicit content when the disposition is `proceed-with-conditions`. Each condition states whether examined closure evidence supports closure, the condition remains open, or it was accepted unresolved. When none was imposed, say so. |
| Next activity | One statement of the activity the review question addressed. | Name the reviewed test activity the authority judged ready to start and the scope and conditions of that judgment. |
| Separate approval | Zero or one reference to a real approval or acceptance record. | Cite it only when it exists, with its authority, scope, and effective status. Establish any effective product acceptance or operational authorization from its actual separate decision evidence. `not-decided` means the review authority has not decided. If an additional recorded decision is required for the disposition to take effect, retain the actual disposition and identify the pending decision and resulting limit on its effect. |

Use prose for the readiness conclusion and authority. Use a table or equivalent entries for criteria and actions, separating the adopted criterion, the evidence examined, and the assessment. Do not add blank rows, a generic document-lifecycle block, a criteria table the project did not adopt, or a table of test results.

## Quality criteria

- The record is a TRR that was held for an identified test or series, against an identified article configuration and an identified project criteria edition whose criteria are explicit in the record.
- The assessment covers readiness to start the reviewed test, within the adopted success criteria. Unexamined required products stay `not-assessed`.
- Every `met` or `not-met` result cites evidence examined at the review. A thematic list of article, procedures, environment, and personnel is incomplete while an adopted criterion has no entry and no authorized omission.
- Open discrepancies, unmet criteria, disagreements, and open actions remain visible. An accepted exception names its authority. Planned test activity is not an observed result.
- The disposition matches the assessments. `proceed` or `proceed-with-conditions` with a required criterion `not-assessed` or `not-met` also records the accepted exception and its authority.
- The disposition uses `not-decided`, `proceed`, `proceed-with-conditions`, `repeat`, or `stop`, identifies its deciding authority, and states its scope, conditions, and effective status. The readiness assessment stays bound to the reviewed test scope and article configuration.
