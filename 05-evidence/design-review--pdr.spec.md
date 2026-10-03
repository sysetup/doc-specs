# Preliminary design review record specification

## Identity and selection

- **Specification ID:** `DESIGN-REVIEW@pdr`.
- **Purpose:** Record one Preliminary Design Review that was actually held, including whether the board judges the preliminary design consistent with the system of interest requirements at preliminary-design maturity, with the risk and constraints the project applies, and whether that design is an adequate basis for detailed design.
- **Intended readers:** The review chair, reviewers, design leads, technical authority, project leads, and anyone who later relies on this gate's evidence and disposition.
- **Decision or action supported:** Readers can tell whether the reviewed preliminary design is a sufficient basis to proceed into detailed design, under the requirements, risk, and constraints the review applied, and what the review authority decided.
- **Use when:** A Preliminary Design Review has been held and its entrance evidence, design assessment, findings, actions, and disposition must be recorded.
- **Scope boundaries:** Cover the held review's assessment of the identified preliminary design as a basis for detailed design. Identify examined material by edition and locator rather than reproducing it. Record only the assessment, conditions, and decision actually made.

## Authoring inputs and unresolved facts

Obtain the review identity and actual date or sessions; the system-of-interest boundary; the preliminary-design edition reviewed and the requirements edition it was assessed against; the risk picture and the cost, schedule, or other constraints the review applied; the chair, reviewers, decision authority, and any project-defined independence or quorum rule; the complete entrance and success criteria established for this review, including their text, project-record identity, edition, locator, and authorized changes; the products and evidence examined; findings, disagreements, and actions; and the disposition made.

State each established entrance and success criterion explicitly, including the required product or evidence, the condition for satisfying it, and any scope limit. Account for every criterion and every authorized omission or change. Include integration plans, verification and validation plans, interface definitions, runtime-environment targets, analyses, and prior-review dispositions as examined evidence when the review's criteria require them; identify each examined edition and locator. An assessment requires the evidence actually examined and the reviewer's rationale. If the review was not held, do not write this record. If the design edition, the requirements edition, the criteria, or the decision authority is unknown, state the gap and do not record `proceed` or `proceed-with-conditions`. Do not invent margins, interface agreement, risk acceptance, or a favorable disposition.

## Finished-document contract

- **Title:** Name the system of interest and identify the document as a Preliminary Design Review record.
- **Frontmatter:** None. Begin with the GFM title. Review identity, criteria, and disposition belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Identify the held review, the preliminary-design edition, and the authority before the criteria. Present entrance results before the design assessment. Present the disposition after the findings. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Review identity and authority | Required | Identify one held Preliminary Design Review, the system boundary, the preliminary-design edition, the requirements edition used as the assessment basis, the actual date or sessions, the chair, reviewers, and decision authority. State the project-defined independence or quorum rule and its observed result when required. |
| Adopted criteria | Required | State every entrance and success criterion established for this PDR, its required product or evidence, satisfaction condition, and scope limit. Identify the project criteria record by title or ID, edition, and locator. Record each authorized omission or change, its reason, and its decision maker. If no criteria were established, say so. |
| Entrance results | Required | Give one entry for each established entrance criterion, including the required product and revision, the evidence examined, the assessment, and the rationale. Record an authorized omission as `not-applicable` with its reason and decision maker. Identify the examined preliminary design, supporting plans, interface material, runtime-environment target, and prior-review dispositions by edition and locator when the criterion requires them. |
| Design assessment, findings, and actions | Required | Assess whether the preliminary design is consistent with the identified requirements at preliminary-design maturity, with the risk and the constraints the project applied, and whether it is an adequate basis for detailed design. Assess each established success criterion, including expected performance, interfaces, and open-item plans when the review criteria include them. Record findings, severity, disagreements, and actions actually assigned. Summarize the assessed design and requirement relationships with locators to the examined editions. |
| Disposition | Required | Record one disposition by the identified review authority and the activity it addresses. State imposed conditions, or state that none were imposed. Define the decision's extent and effective status: `proceed` records the board's judgment that the reviewed preliminary design is an adequate basis for detailed design within the recorded scope and conditions. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Review identity | One stable identity for one held PDR. | Bind it to the system, the preliminary-design edition, and the actual date or session. A later repeat review is a different record. |
| Preliminary-design edition | One preliminary-design definition the review examined. | Identify it by title or ID, edition, and locator. Bind each design assessment to that examined edition and its preliminary-design maturity. |
| Requirements basis | One requirements edition against which the design was assessed. | Identify its title or ID and edition. Do not assess the design against requirements that were not in that edition unless the review records them as an explicit exception. |
| Risk and constraints | The risk picture and the cost, schedule, or other constraints the review applied. | Identify the examined source and its date or edition. A constraint the project did not apply is not added. An unexamined risk or constraint that the adopted criteria require stays `not-assessed`. |
| Decision authority | One chair or deciding authority, and the reviewers who participated. | Record a missing required independent reviewer or quorum as a review-control defect. Do not invent a participant. |
| Criteria set | One project-established PDR criteria set, or one explicit statement that none was established. | Give its project-record title or ID, edition, and locator, and state the complete criterion text and satisfaction conditions. Account for every entrance and success criterion and each authorized omission or change. |
| Entrance or success entry | One entry for each established criterion, including authorized omissions. | State the criterion, project-record locator, required product or evidence, satisfaction condition, scope limit, evidence examined, and one assessment: `not-assessed`, `met`, `not-met`, or `not-applicable`. `not-assessed` means required evidence was not examined or the criterion was not evaluated; `met` means examined evidence supports its satisfaction condition; `not-met` means the assessment identifies an unmet condition. `not-applicable` requires a documented reason and the authority that accepted the omission or scope limit. The rationale names the reviewer basis and any exception. |
| Design-basis assessment | One assessment of the reviewed preliminary design. | Address consistency with the identified requirements at preliminary-design maturity, the risk and constraints the review applied, and adequacy as the basis for detailed design, to the extent of the established success criteria. State the reviewer's conclusion and rationale with examined evidence and edition locators. |
| Finding | Zero or more findings from this review. | Tie each finding to a design element, requirement, criterion, or examined evidence, and state severity. Record a stated disagreement, or state that none was recorded. |
| Action | Zero or more actions this review assigned. | Give the action, owner or unassigned state, and due or hold point. Record closure evidence only when closure occurred. |
| Disposition | One value for this review. | Use `not-decided`, `proceed`, `proceed-with-conditions`, `repeat`, or `stop`. Record a reviewer recommendation and a different authority's decision separately when both exist. |
| Condition | Zero or more conditions the disposition imposes. | Required as explicit content when the disposition is `proceed-with-conditions`. Each condition states whether examined closure evidence supports closure, the condition remains open, or it was accepted unresolved. When none was imposed, say so. |
| Next activity | One statement of the activity the review question addressed. | Name detailed design as the work assessed and state the scope and conditions of the board's judgment that the preliminary design is adequate to support it. |
| Approval effect | Zero or one reference to a real approval or acceptance decision affecting this disposition. | Cite it only when it exists. `not-decided` means the review authority has not decided. If that authority decided but a further project approval is required for effect, retain the board's disposition and state its pending effective status. Identify the required decision maker and the approval's recorded extent, including any acceptance or baseline effect actually granted. |

Use prose for the design-basis conclusion and authority. Use a table or equivalent entries for criteria and actions, separating the established criterion, the evidence examined, and the assessment. A figure may identify the reviewed design boundary when its source edition is stated. Populate entries with established criteria, actual findings, and assigned actions; omit unused blank rows.

## Quality criteria

- The record identifies a PDR that was held, its preliminary-design edition, requirements edition, and complete project-established criteria with their record identity and edition. Unknown criteria are explicit and prevent a favorable disposition.
- The assessment covers requirement satisfaction, the risk and constraints the project applied, and adequacy as a basis for detailed design, within the adopted success criteria. Unexamined required products stay `not-assessed`.
- Every `met` or `not-met` result cites evidence examined at the review and explains how it supports the assessment. Every established criterion has an entry, including a reason and decision maker for each authorized omission.
- Open items, unmet criteria, disagreements, and open actions remain visible. An accepted exception names its authority.
- The disposition matches the assessments. `proceed` or `proceed-with-conditions` with a required criterion `not-assessed` or `not-met` also records the accepted exception and its authority.
- The disposition uses `not-decided`, `proceed`, `proceed-with-conditions`, `repeat`, or `stop`, names its deciding authority, and states its scope, conditions, and effective status. The design assessment remains bound to the reviewed preliminary-design edition and maturity.
