# Test anomaly reference specification

## Identity and selection

- **Specification ID:** `TEST-ANOMALY-REFERENCE@core`.
- **Purpose:** Provide a controlled linking view of the test anomalies in one stated test scope, including each anomaly's observation source, any authoritative problem record, test impact, derived disposition, and any retest or closure evidence.
- **Intended readers:** The test lead and anyone who must see which runs, problem records, retests, and testing constraints belong together.
- **Decision or action supported:** See which anomalies affect this test scope, which testing is blocked or selected for retest, and whether each linked disposition is authorized in its problem record.
- **Use when:** Test anomalies need a status and reference view across executions, problem records, dispositions, retests, and closure evidence.
- **Scope boundaries:** Each entry links an observed anomaly to its testing impact, existing problem disposition, and any retest or closure evidence within the stated test scope.

## Authoring inputs and unresolved facts

Obtain the test scope this view covers and the time through which it was checked. For each anomaly in that scope, obtain a short identification of what was observed, the run in which it was observed, any existing problem record and its revision, the effect on this test scope, the disposition shown by that problem revision, any testing-specific constraint, and any retest or closure evidence that already exists.

If the scope was assessed and no anomaly belongs in it, say so. If a run, problem record, disposition, or evidence item is missing, state the gap and its effect on the link. Do not invent an execution identifier, a problem identifier, an authorized disposition, or a retest result. Cite a record only when it exists.

## Finished-document contract

- **Title:** Name the test scope and identify the document as its test anomaly reference.
- **Frontmatter:** None. Begin with the GFM title. Scope, links, and derived disposition belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State the scope before the links. Keep each anomaly's links together. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| View scope | Required | State the bounded test effort this view covers, the as-of time, and the basis on which anomalies were included or left out. State when the scope was assessed and no anomaly is linked. |
| Anomaly links | Required | For each linked anomaly, identify the observation, the run, any problem record, the test impact, the derived disposition, testing-specific constraints, and any real retest or closure evidence. An assessed-empty scope has no link rows and says that no anomaly is linked. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Test scope | One bounded test effort for this view. | Name the campaign, cycle, or other effort, and what is outside it. The as-of time is a date-time with an explicit offset, or the clock time is stated as unknown. |
| Anomaly link | Zero after an assessed-empty scope; otherwise one per anomaly in the scope. | Give each link a stable label inside this view. The label is not a problem-record identifier unless that record is the one cited. |
| Observation pointer | One short identification per link. | State what was noticed and where. When an execution record exists, cite it and the affected attempt when the observation belongs to an attempt. Do not cite a `not-run` entry as the observation: a `not-run` reason says the stimulus did not occur. If the run ended before any case was selected, cite the run and say that no attempt exists. When no execution record exists, identify the observation by the known facts and state that no execution record is cited. Identify the observation separately from the cited problem disposition. Do not paste the run log or invent an identifier. |
| Problem citation | One citation position per link. | When a problem record exists, cite its identity and revision. When none exists, state that no authoritative problem record is cited. Keep the citation concise and use it to locate supporting analysis, reproduction details, and closure narrative. |
| Test impact | One current impact statement per link. | State the effect on this scope, including present blocked testing, retest selection, and reporting, or state that the impact is unknown. A case never selected into a run is remaining scope, not `not-run`. A blocked test is a present testing constraint, not a campaign forecast. |
| Derived disposition | One view per link, taken only from the cited problem revision. | Use `not-established` when no problem record is cited, the cited revision is unknown, or that revision's disposition is `undecided`. Use `not-authorized` when the disposition is `correction-proposed` or `limitation-proposed`. Use `authorized` for `limitation-accepted` or `rejected` only with the authority and basis that revision shows, and for `correction-implemented` only when that revision shows the authority it relies on. If `correction-implemented` does not show authority, cite the disposition and state that authority is not shown; do not call it `authorized`. State the disposition value itself and derive it from that revision's recorded decision. State when the cited revision is unknown, because the view may then be stale. |
| Testing constraint | Zero or more constraints that apply inside this test scope. | Record a retest selection, a blocked case, or a reporting limit when one applies here. A blocked case named here is a constraint, not a `not-run` outcome. Describe only effects on the stated test scope. |
| Retest citation | Zero or more later runs. | Cite a later run only when it occurred, and cite the attempt identity when that run has one. Label a selected but unstarted retest as planned. A planned retest is not closure evidence. A retest `pass` does not erase the earlier attempt and does not close the departure. |
| Closure evidence | Zero or more citations. | Cite closure evidence only when the problem record's closure position is `closed` and the evidence exists. `verified`, `rejected`, or a retest result is not closure unless that record says `closed`. The citation does not itself close the departure. |

Use one row or short block per anomaly link. Repeat citations inside the link when a link has several runs or constraints. Keep observation summaries and impact constraints concise, and cite supporting analysis. Do not add an empty link or a generic document-control block.

## Quality criteria

- The view stays inside one stated test scope. An assessed-empty view says the scope was checked.
- Each link identifies the observed facts and their location, citing the run and affected attempt when they exist. A run-level observation with no selected case states that no attempt exists; a missing execution record is stated explicitly. A `not-run` entry is not an observation pointer.
- `authorized` matches the cited problem revision's disposition and the authority that revision shows. `undecided` and a proposal are not authorized. A missing revision is marked, not treated as current.
- Retests and closure evidence are cited only when they exist. A retest pass does not close the departure. Planned work stays labeled as planned. `verified` or `rejected` is not closure unless the problem record says `closed`.
- Every cited execution, problem report, retest, or closure record exists and is identifiable from its citation.
