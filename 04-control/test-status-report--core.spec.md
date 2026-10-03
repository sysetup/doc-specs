# Test status report specification

## Identity and selection

- **Specification ID:** `TEST-STATUS-REPORT@core`.
- **Purpose:** Report one period of an active test effort: actual progress, results to date, coverage, anomalies, blockers, risks, and forecast.
- **Intended readers:** The test lead and the people who decide what the effort does next.
- **Decision or action supported:** See what progressed in the period, what is blocked now, what is only a forecast, and which decisions are still needed.
- **Use when:** An active test campaign or other bounded test effort needs a progress report for a stated period.
- **Scope boundaries:** Summarize observed progress and current impediments for the stated period, with forecasts and next-period work explicitly labeled as prospective.

## Authoring inputs and unresolved facts

Obtain the test effort, the period start, the as-of time, the item or baseline under test when known, and the test-plan edition when one is cited. Obtain the source of every progress count, the coverage basis when coverage is claimed, the anomaly masters and their as-of times, the present blockers, the risks and forecast, the decisions still needed, the next period's planned work, and any action records that already exist.

If a count, baseline, plan, master, owner, or decision is unknown, state the gap and keep the affected claim unestablished. Do not treat an omitted run list as proof that no run occurred, and do not treat a missing count as zero. Derive `pass`, `fail`, `inconclusive`, and `not-run` counts from actual bounded execution records or another identified observed source. Do not invent a pass, a coverage percentage, an anomaly total, a blocker, or a decision. Cite a plan, run, anomaly view, problem record, risk, or action only when it exists.

## Finished-document contract

- **Title:** Name the test effort and the reporting period, and identify the document as its test status report.
- **Frontmatter:** None. Begin with the GFM title. Period, progress, and forecast belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State the period and sources before the counts. Place anomalies and blockers before forecast. Place the next period last. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Period and sources | Required | State the test effort, the period start, and the as-of time. State the item or baseline under test, or that it is unknown. Cite a test-plan edition only when one is used. Name the source and time of every execution summary. Cite individual runs when the report depends on them. |
| Progress and coverage | Required | Separate planned scope, work never selected into a run, and outcomes taken from cited run records or another named observed source. `pass`, `fail`, and `inconclusive` count attempts only. `not-run` counts cases selected for a run whose stimulus or result assertion was not performed, including a case blocked before the stimulus. Planned work never selected into a run is remaining scope, not `not-run`. State whether each count is cases, attempts, or runs. Bind each outcome count to actual execution and its observed source. State coverage only against a named basis, or state that coverage is not established. |
| Anomalies and blockers | Required | Summarize departures by the named master's current state at its as-of time, or state that those counts are not established. Use `closed` only for a closure position of `closed`. Keep `resolved`, `verified`, `rejected`, and `reopened` under those states. Do not add a reopened count on top of another state count unless the report says the counts overlap. State each present blocker separately, or that the period was assessed and none was identified. A blocker is not an outcome count and does not by itself create a `not-run` count. |
| Forecast and next period | Required | Label forecast as forecast. State schedule, resource, and limitation concerns that are still uncertain, and the decisions the report is asking for. State the next period's planned work as planned. Cite an existing action when one is the corrective or replanning record. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Reporting period | One start and one as-of time for this report. | Use date-times with an explicit offset, or state that a clock time is unknown. The as-of time is the cutoff for the reported status. |
| Summary source | One named source for the execution summary. | Identify the records, query, export, or person, and the time of that source. A numeric claim without a source is not established. An empty run list does not mean that no run occurred. |
| Progress count | One set of counts for the stated unit. | Keep planned scope and unselected remaining scope separate from `not-run`, `pass`, `fail`, and `inconclusive`. `pass` is an attempted comparison supported by observations meeting an established criterion; `fail` is an attempted comparison with an observed miss; `inconclusive` is an attempted comparison without a usable basis for judgment. `not-run` identifies a case selected for a bounded run whose stimulus or result assertion was not performed, with the reason; it is not an attempt. Bind counts to actual execution and its observed source. Unknown is not zero. A later retest does not erase an earlier result; say whether both attempts are counted. |
| Coverage | One statement. | Name the requirement, risk, or other basis and its edition. State what was covered and the counting unit; for a percentage, state the numerator and denominator. Omit a percentage when the basis or the arithmetic is unknown. |
| Anomaly summary | One summary taken from masters. | Name each problem register or anomaly reference used, with its as-of time. Report each current problem state from those masters. Use `closed` only when the master's closure position is `closed`. Keep `resolved`, `verified`, `rejected`, and `reopened` visible under those states, and do not add a reopened count on top of another state count unless the report says the counts overlap. Give a trend only when an earlier period was actually compared. Keep the summary to recorded states, counts, trends, and test impact, preserving each recorded disposition. |
| Blocker | Zero after an assessed-empty period; otherwise one per present impediment. | State what testing is stopped or narrowed, and the cause when known: a cited defect, environment, resource, data, authority, or unknown. A blocker is a present impediment. It may explain a `not-run` entry or work that was never selected; it is not itself either count. An uncertain future effect is a risk, not a blocker. |
| Forecast | One projection for the remaining effort. | Mark it as a forecast. Include the assumption it depends on, or state that the assumption is unstated and the forecast is not established. |
| Decision needed | Zero or more requests. | State each unresolved question as a request and name the owner if one exists. Do not give the request a decision identifier. |
| Next-period work | One plan for the following period. | Describe work as planned. Do not report it as executed. |
| Action citation | Zero or more existing actions. | Cite a real action record only when that action exists. A described next step without a record is not given an identifier. An empty citation list is not a claim that no action exists unless the report says the actions were assessed. |

Use prose for the period, forecast, and decisions needed. Use a compact count table when several progress units must be compared. Use one row per blocker. Do not add an empty run, a generic document-control block, or a run log.

## Quality criteria

- Every result claim falls inside the stated period and names its source, or is marked unestablished.
- Planned scope, unselected remaining scope, `not-run`, `pass`, `fail`, and `inconclusive` are not substituted for one another. Executed outcomes name a run record or another observed source. A blocker is not an outcome count.
- Anomaly totals match the named master's current state. `resolved`, `verified`, and `rejected` are not reported as closed. A reopened count is not added on top of another state count unless the overlap is stated. Blockers and risks are not collapsed into the outcome counts.
- Forecast, decisions needed, and next-period work stay prospective; counts and coverage describe observed status through the as-of time.
- Every cited plan, run, anomaly view, problem record, risk, or action exists and is identifiable from its citation.
