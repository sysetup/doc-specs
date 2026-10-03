# Code review record specification

## Identity and selection

- **Specification ID:** `CODE-REVIEW-RECORD@core`.
- **Purpose:** Record one actual review of a source revision, including the criteria applied, the findings and their dispositions, the re-review state, and the review evidence retained.
- **Intended readers:** The reviewers, the author of the change, and anyone who later needs to know which snapshot was reviewed and what remained open.
- **Decision or action supported:** See whether the identified snapshot was reviewed, what was found, how each finding was disposed, and whether the recorded project review conditions require another review.
- **Use when:** A code review has occurred and the reviewed revision, applied criteria, findings, dispositions, re-review state, and retained evidence must be kept.
- **Scope boundaries:** Record examination of an immutable source snapshot that actually occurred. Intended checks cannot be reported as performed, and the outcome applies only to the identified snapshot and review criteria.

## Authoring inputs and unresolved facts

Obtain the repository or component; the immutable snapshot that was reviewed; any request or change identifier used only as context; the review mechanism; when the review occurred, if that time was captured; the reviewers who participated, expressed as roles or identifiers within the supplied project disclosure limits; the concrete project criteria actually applied and their requirement or decision basis and revision; the focus areas actually considered; the automation or test evidence that was inspected and the result observed; each retained finding, its location, any project-assigned severity and scale definition, its status, and its disposition; the project's explicit conditions for re-review; the review outcome; and the logs, comments, diffs, or other evidence retained.

If the snapshot, the reviewers, or the focus cannot be established, state that gap. Do not bind the outcome to later commits, and do not treat the review as complete. Do not invent a reviewer, a location, a severity, a commit, or a check result. Cite a project requirement, decision, change request, or inspected result only when it exists and supports an identified review fact.

## Finished-document contract

- **Title:** Name the component and identify the document as a code review record of the reviewed snapshot.
- **Frontmatter:** None. Begin with the GFM title. The snapshot, findings, and outcome belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Identify the snapshot and the reviewers before the criteria. Present findings before the outcome. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Review identity and source scope | Required | Identify the repository or component, the immutable snapshot reviewed, the review mechanism, when the review occurred or that the time was not captured, and the reviewers who participated. A mutable request or branch name may be added as context and does not replace the snapshot. |
| Criteria actually applied | Required | State the focus areas the reviewers considered and the concrete conditions they assessed. Identify the supplied project requirements or decisions establishing those conditions, with revision and locator when known; state any basis gap. Identify automation or test evidence that was inspected and the result observed, or state that none was inspected. |
| Findings and dispositions | Required | Give one finding for each issue or review comment retained. When the review of this snapshot finished and no finding was raised, say so and include no placeholder finding. |
| Outcome | Required | State one review outcome, its snapshot and criteria scope, and whether re-review is required. Identify retained review evidence, or state that the findings and outcome are recorded only here. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Snapshot | One immutable revision, commit, or change revision that was reviewed. | A branch name or an open request identifier is not sufficient while the reviewed content can still change. If only a mutable identifier is known, say that the snapshot is not established. The outcome applies only to the identified snapshot. |
| Review mechanism | One of `peer-review`, `pull-request-review`, `formal-inspection`, `pair-review`, or `other`. | `other` names the mechanism actually used. Describe how the identified snapshot was examined and by whom or by which automation. |
| Reviewers | The people who participated, or an explicit statement that they are not established. | Use a role or another identifier the project permits. Do not invent a participant. If no reviewer can be identified, the outcome cannot be `review-complete`. |
| Focus area | One or more areas actually considered. | Record what the reviewers examined. Do not copy a checklist that was not used. If the focus was not recorded, say that it is not established. |
| Review criterion | Zero or more explicit project criteria actually applied. | State the required condition, its assessed source scope, and its supplied requirement or decision basis, revision, and locator when established. A citation alone does not state the criterion or demonstrate that the snapshot meets it. |
| Inspected automation | Zero or more results that reviewers inspected. | State the observed result and what was inspected. An uninspected pipeline is not evidence. Explain how the result supports the review assessment. A favorable check does not dispose of a finding unless the finding's disposition says that it does. |
| Finding | Zero or more. One row or block each. | Zero is allowed only when the review of this snapshot was assessed and no finding was raised. Each finding has a stable label, the issue or comment, a reproducible location or a statement that it applies to the whole snapshot, and a status. |
| Severity | Zero or one for each finding. | State the meaning and assignment conditions of the project's scale when the project assigned a severity. If it assigned none, say so. Do not invent a scale or a rank. |
| Finding status | One of `open`, `accepted`, `resolved`, `not-applicable`, or `deferred`. | `resolved` identifies the change or action that addressed it. `accepted` means the reviewers accept the current snapshot with respect to this finding and require no code change for it. `not-applicable` and `deferred` state the rationale. `deferred` also states any internal decision rights and actual decision the project required for deferral. `open` states that no resolving disposition has been made, and it does not cite a fictitious resolution. |
| Review outcome | One of `changes-required`, `acceptable-with-open-items`, `review-complete`, or `inconclusive`. | `changes-required` means reviewers require changes before this review of the snapshot is finished, and at least one `open` finding supports that. `acceptable-with-open-items` means at least one `open` or `deferred` finding remains and the reviewers nevertheless accept the snapshot for this review's purpose. `review-complete` means the review finished and no finding remains `open` or `deferred`. `inconclusive` means the snapshot, participation, or applied criteria do not support one of the other three outcomes. |
| Re-review | One statement: required, not required, or not established. | State the concrete re-review conditions the project applied and whether they are met. Do not infer the value from the outcome unless those conditions establish the relationship. Do not default it to not required. |
| Outcome scope | One statement on every record. | Bind the outcome to the exact reviewed snapshot, focus areas, and criteria; state any unexamined source scope or unresolved assessment limit. |
| Retained evidence | Zero or more logs, comments, diffs, or test results kept for this review. | Identify what was retained. If nothing separate was retained, say that this record is the retained evidence. |

Use prose for the snapshot, the focus, and the outcome scope. Use one row or block per finding so the location, status, and disposition stay together. Do not add a blank row, a generic document-lifecycle block, or an identifier pattern.

## Quality criteria

- The outcome names the snapshot it covers. A later commit is outside that outcome unless this record reviews that commit.
- `review-complete` contains no `open` or `deferred` finding. `changes-required` is supported by at least one `open` finding. `acceptable-with-open-items` names the open or deferred items. An assessed review with no findings says so without a dummy finding.
- Finding status and disposition agree. `open` is not given a resolution that did not occur.
- Inspected automation remains inspection evidence. It replaces the reviewers only when the recorded mechanism says that the automation was the review.
- The outcome is supported by the recorded examination and finding dispositions within the stated snapshot and criteria scope. Re-review conditions and unresolved assessment limits remain explicit.
