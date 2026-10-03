# Problem or defect report specification

## Identity and selection

- **Specification ID:** `PROBLEM-DEFECT-REPORT@core`.
- **Purpose:** Control one observed defect, problem, or nonconformance from its description through analysis, disposition, any correction, effectiveness check, and closure.
- **Intended readers:** The owner who must disposition the departure, the people who investigate or correct it, and anyone who must confirm that closure is supported.
- **Decision or action supported:** Decide whether the departure remains open, which disposition applies, and whether closure has authority and, when a correction was implemented, an effectiveness check.
- **Use when:** An observed departure from expected behavior or from a specified obligation needs its own description, disposition, and closure record.
- **Scope boundaries:** Track one observed departure and its disposition. Exclude uncertain future exposure, active response chronologies, anomaly-only linking views, unrelated follow-up work, and general execution reporting. Include actual correcting changes or accepted limitations where they explain the departure's disposition.

## Authoring inputs and unresolved facts

Obtain the observation, who reported it or which channel detected it, when and in what version or environment it was seen, the expected behavior and the basis for that expectation, the reproduction attempt and its result, the affected subjects, and any known operational, safety, or security impact. Obtain the current classification, the analysis, the problem state, the disposition, any authorized correcting change, any completed effectiveness check, the history, and whether closure has occurred.

If a fact, time, subject, owner, authority, or check result is unknown or not established, state that, its consequence, the resolving action, and the actual owner if one is assigned. Do not invent an observation, a requirement identifier, a reproduction step, a severity, a cause, an approval, or a passing retest. Cite a requirement, execution record, change, action, or approval only when that record exists.

## Finished-document contract

- **Title:** Name the departure and identify the document as its problem or defect report.
- **Frontmatter:** None. Begin with the GFM title. Identity, state, and disposition belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State the observation before analysis. Place disposition and effectiveness after analysis. Place history and closure last. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Observed departure | Required | Give the departure a stable identity and the time this version of the report represents. State the accountable role or that none is assigned. State the factual departure without a cause. State the reporter or detection channel, the detection time, and the version or environment when known. Separate the observed behavior from the expected behavior, and name the basis of the expectation or state that the basis is unestablished. |
| Reproduction and affected scope | Required | State the reproduction result and the conditions, steps, inputs, frequency, and limits that were actually used or observed. Name each affected subject that is identified, including a controlled requirement, configuration item, interface, test case, or execution only when that record exists. State operational, safety, and security impact as assessed, not assessed, or none identified after assessment. |
| Triage and analysis | Required | State whether classification has occurred. When it has, give the project's severity or priority and the rationale. Keep known facts, hypotheses, and confirmed causes distinct, and cite investigation evidence only when it exists. State the current problem state. |
| Disposition and effectiveness | Required | State the current disposition. For a correction, state whether implementation has started and cite an authorized change only when one exists. Cite a completed effectiveness check when the state is `verified` or when closure follows an implemented correction. State when a check does not apply. |
| History and closure | Required | Record dated transitions, beginning with the opening of this departure. Include communications, recurrence checks, and related departures only when they exist. State the closure position. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Departure identity | One stable identifier for this departure. | Do not reuse it for another departure. It is not a document-lifecycle state. |
| Report time | One as-of time for this version. | Use a date-time with an explicit offset, or state that the clock time is unknown. A later update changes the as-of time and does not silently rewrite earlier history. |
| Expectation basis | One current basis for the expected behavior. | Identify a project requirement, design, interface, procedure, or other inspected project record describing the expected behavior when one exists. An unestablished basis remains visible. Do not treat that expectation as a confirmed nonconformance. |
| Affected subject | One or more statements. | Describe the subject in words when no controlled identifier exists. An unresolved subject is stated as unresolved. Do not invent an identifier to fill a list. |
| Reproduction result | Exactly one of `reproduced`, `not-reproduced`, `not-attempted`, or `not-permitted`. | `not-permitted` states why another attempt is not allowed. Record only steps and inputs that were used or observed. |
| Classification | One current classification position. | Use `not-triaged` before triage. After triage, use the project's own severity or priority and its rationale. Do not import a universal scale. Priority is separate from impact. |
| Problem state | Exactly one of `new`, `triaged`, `investigating`, `resolved`, `verified`, `closed`, `reopened`, or `rejected`. | `resolved` means a correction is implemented and is not an effectiveness result or closure. `reopened` identifies the prior resolution, verification, closure, or rejection, the reason it no longer holds, and the resumed activity. Preserve prior corrections and check results in the history. |
| Disposition | Exactly one of `undecided`, `correction-proposed`, `correction-implemented`, `limitation-proposed`, `limitation-accepted`, or `rejected`. | `new`, `triaged`, `investigating`, and `reopened` use `undecided`, `correction-proposed`, or `limitation-proposed`. `resolved` and `verified` use `correction-implemented`. `closed` uses `correction-implemented` or `limitation-accepted`. `rejected` uses `rejected`. A proposed value names no authority. `limitation-accepted` and `rejected` each name the authority and the basis. |
| Effectiveness check | Required for `verified`, and for `closed` with `correction-implemented`. | Record every completed effectiveness check that bears on the current disposition, including a failed or inconclusive check, regardless of state. Cite its evidence and result: `pass`, `fail`, or `inconclusive`. Only a result that shows the departure no longer occurs, or that the correction works, supports `verified` or that closure. A planned test is not a check. For `limitation-accepted` and `rejected`, state whether a retest applies and its basis; accepting a limitation or rejecting the report does not require a passing correction retest. |
| Closure | One current closure position. | `closed` names the criteria met, the closing authority, and the time. For `limitation-accepted`, that authority is the acceptance authority. `rejected` names the rejection authority and states that this report will not correct the departure. Every remaining state states that the departure is currently neither closed nor rejected; a reopened report retains any earlier closure or rejection as history. |
| Recurrence | One current check position. | Use `checked` with the result, `not-checked`, or `not-applicable`. Do not invent a recurrence. |
| History event | One or more events. | The first event may be the opening of the report. Each event has a time when known, an actor, and what changed. Related departures are cited only when those records exist. |

Use prose for the departure, expectation, and analysis. Use a short table for history when several transitions must be compared; each row is a real event. Do not add an empty subject, a generic document-control block, or a root cause in the observation.

## Quality criteria

- The report is about one observed departure. Facts, hypotheses, and confirmed causes stay distinct. Problem state and disposition match.
- `new`, `triaged`, `investigating`, and `reopened` carry an unresolved current disposition; historical corrections and check results remain visible. A failed or inconclusive check does not support `verified` or closure after a correction. Current closing authority is required only for `closed`; earlier authorities remain in the history.
- `verified`, and `closed` after a correction, rest on a completed supporting check. An accepted limitation or a rejection states the retest applicability and basis without implying a correction passed.
- Affected subjects, changes, approvals, and executions that are cited exist. Missing identifiers stay missing.
