---
title: "Test completion report specification"
description: >-
  Defines the authoring contract for test completion reports summarizing one ended test campaign or phase—including campaigns stopped early with unmet exit criteria. Covers campaign closure and controlling source baseline, adopted completion criteria, citations to supporting execution runs, reconciled result counts, actual coverage achieved, deviations and retests, anomaly summaries, per-criterion completion assessments, residual risks and limitations, archive references, completion-review disposition, and recommendations for next testing.
topics:
  - "evidence"
  - "testing"
  - "verification-and-validation"
  - "test-completion-report"
  - "test-campaign-summary"
  - "exit-criteria-assessment"
  - "test-coverage"
  - "anomaly-reconciliation"
use_when:
  - "A bounded test campaign or phase has ended and requires a reconciled summary against adopted exit criteria."
  - "A test lead is aggregating run outcomes, anomalies, coverage gaps, residual risks, and recommendations for stakeholders."
  - "A reviewer is evaluating whether campaign exit criteria were satisfied or which unmet criteria require further testing."
not_for:
  - "Reporting periodic mid-campaign progress and forecasts while testing is still active, which belongs in a test status report."
  - "Recording detailed per-case observations from one single test run, which belongs in a test execution record."
  - "Planning test scope and exit criteria before testing begins, which belongs in a test plan."
  - "Reporting empirical AI benchmark metrics, probabilistic run variance, judge methodologies, and safety probing outcomes, which belongs in an AI evaluation report."
---

# Test completion report specification

## Identity and selection

- **Specification ID:** `TEST-COMPLETION-REPORT@core`.
- **Purpose:** Summarize one test campaign or phase that has ended: the scope actually covered, the reconciled results, anomalies, coverage, limitations, and what remains unresolved.
- **Intended readers:** The test lead, the people who adopted the completion criteria, and anyone who must decide what testing, if any, happens next.
- **Decision or action supported:** Judge the ended campaign against its completion criteria, see which criteria remain incomplete, and identify the further testing supported by the evidence.
- **Use when:** A defined test campaign or phase has ended, whether it met its exit criteria or stopped with criteria still open, and that ending needs one summary tied to the runs that support it.
- **Scope boundaries:** One ended test campaign or phase, including an effort stopped before its completion criteria were met. Summarize the actual tested scope and observations, assess completion, and state the remaining work and limitations.

## Authoring inputs and unresolved facts

Obtain the campaign or phase identity, the end condition and period, the levels and items, the configurations the runs actually tested, the exclusions, and the completion criteria that were adopted, including who adopted them. Obtain the adopted plan identity and edition when one exists, the execution records when they exist, the observed count source, the coverage basis, the anomaly masters, the deviations and retests, the unresolved anomalies and residual risks, the archive and retention facts, any completion-review decision, and any action records that already exist.

The campaign must have ended. If a criterion, count, run, tested configuration, master, or decision is unknown, state the gap and keep the affected claim unestablished. Do not treat a missing count as zero, an omitted run list as proof that no run occurred, a planned version as the tested configuration, or an incomplete criterion as met. Derive `pass`, `fail`, `inconclusive`, and `not-run` counts only from recorded observations under the outcome definitions below. Do not invent a pass, a coverage result, an anomaly total, a recommendation outcome, or a decision. Cite a plan, run, anomaly view, problem record, risk, approval, or action only when it exists.

## Finished-document contract

- **Title:** Name the test campaign or phase and identify the document as its test completion report.
- **Frontmatter:** Required. Begin with a YAML 1.2 Semantic-Discovery frontmatter block delimited by `---` lines containing `title`, `description` (60 to 140 neutral retrieval words), `topics` (3 to 12 concrete lowercase kebab-case terms), `use_when` (2 to 6 neutral task conditions), and conditional `not_for` (1 to 5 grounded exclusions, omitted when empty), followed by the GFM H1 title. Exclude internal IDs, version strings, hashes, filesystem paths, build metadata, and unresolved template delimiters from frontmatter values. Scope, results, and the recommendation belong in the body. Governing source: Collection Semantic-Discovery Frontmatter contract.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. Omit it for internal documents unless a specific project policy requires explicit negative attestation. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State the ended campaign and its sources before the results. State unresolved items before the recommendation. Place archive and disposition last. Heading wording may vary.
- **Presentation:** Use concise factual prose paired with structured evidence tables, chronologies, or finding lists sized to the performed activity. Required roles may share sections while keeping assessed configuration, criteria, actual observations, dispositions, and coverage limits strictly traceable.

| Projection | Title and metadata ownership | Syntax and source authority |
| --- | --- | --- |
| Test completion report (standalone) | Begin with the mandatory 5-key Semantic-Discovery YAML frontmatter followed by one event- or assessment-specific H1. Activity identity, assessed configuration, actual timing, authority, and observed outcomes remain body content; external specification provenance and corpus-level default maintenance metadata apply where governed in a unified corpus. | Use GFM prose, tables, or logs bound to immutable inspected snapshots, artifact revisions, and real execution or review records. Historical observations remain tied to their recorded scope and time; later retests, changes, or approvals create distinct records rather than rewriting prior evidence. |

| Section role | Status and inclusion condition | Content obligation |
| --- | --- | --- |
| Campaign close and source baseline | Required | Identify one ended campaign or phase, how it ended, and the period. State the test levels, items, and exclusions. Identify the configurations the cited runs actually used, or state that the tested configuration is not established. A planned version is not a tested configuration. State the adopted completion criteria and who adopted them. Identify the adopted plan edition when one exists. Cite each execution record that supports the summary, or state that the run set was assessed and name the result of that assessment. |
| Results and completion assessment | Required | Reconcile planned scope, remaining unselected scope, and outcomes taken from cited run records. `pass`, `fail`, and `inconclusive` count attempts only. `not-run` counts cases selected for a run for which neither the stimulus nor a result assertion was performed, including a case blocked before the stimulus. Planned work never selected into a run is remaining scope, not `not-run`. A run total does not hide mixed case outcomes. If no observed source exists, mark those counts unestablished. State coverage only against a named basis. Account for deviations, retests, and anomalies without erasing an earlier result. Assess each adopted completion criterion and leave every incomplete criterion explicit. |
| Unresolved items | Required | State the unresolved anomalies, residual risks, and limitations that remain after the campaign ended, with their actual status or uncertainty. When a class of unresolved item was assessed and none was found, say that. |
| Recommendation, archive, and disposition | Required | Give one testing recommendation and label it as a recommendation. Identify the versioned plans, assets, environments, runs, and evidence that actually exist, with the established project retention periods, preservation arrangements, and access restrictions, or a statement that retention is not established. Record a completion-review decision only when one occurred. Cite outstanding actions only when those records exist. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
| --- | --- | --- |
| Campaign identity | One ended campaign or phase. | Bind the report to its items, period, and the configurations the cited runs actually tested, or state that the tested configuration is not established. A different phase is a different report. A campaign supported by one run may still have this summary; retain citations to its supporting observations. |
| End condition | One statement of how the campaign or phase ended. | Say whether the adopted work finished, the effort stopped, or the phase was closed. Ending is not the same as meeting every completion criterion. |
| Completion criteria | One adopted set, or one statement that no criteria were established. | State the adopted criteria and the project role or people who adopted them. Identify any plan holding them by title or ID and edition. Do not invent a plan identifier. A report with no established criteria cannot treat the campaign as having met its exit. |
| Run citation | Zero after an assessed-empty run set; otherwise one per execution record used. | Cite each actual execution record used, with its identity and time. When the assessment found no runs, say so; do not invent a run identifier. An empty citation list is not proof that no run occurred unless the report says the run set was assessed. |
| Result counts | One reconciled set, with the unit of each count named. | Keep planned scope and unselected remaining scope separate from `not-run`, `pass`, `fail`, and `inconclusive`. Count `pass` when an established expected result and supporting observation agree; `fail` when an observation demonstrates a missed established criterion; `inconclusive` when a stimulus or result assertion was attempted but the comparison cannot be supported; and `not-run` only for a selected case with neither stimulus nor result assertion performed. The first three count attempts; `not-run` counts unattempted selected cases. Unknown is not zero. A known zero is allowed only when the run set was assessed and the report says so. A later retest does not erase an earlier result; say whether both are counted. Name the observed count source and its time. |
| Coverage | One statement. | Name the requirement, risk, or other basis and its edition. State the covered and uncovered portions of that basis. Omit a percentage when the basis or the arithmetic is unknown. Coverage describes the extent tested; satisfaction of a criterion requires its own supported assessment. |
| Deviation or retest | Zero or more real deviations or distinct retests. | Identify the affected run or case and the earlier result that remains visible. A retest pass does not delete the deviation. |
| Anomaly summary | One summary taken from masters, or one statement that the summary is not established. | Name each problem register or anomaly reference and its as-of time. Report each current problem state from those masters. Use `closed` only when the master's closure position is `closed`. Keep `resolved`, `verified`, `rejected`, and `reopened` visible under those states, and do not add a reopened count on top of another state count unless the report says the counts overlap. Summarize the recorded states and retain locators for their supporting details; do not alter a recorded disposition while summarizing it. |
| Criterion assessment | One entry for each adopted completion criterion. | State the criterion, whether it is met, not met, or not assessable, and the evidence for that judgment. An incomplete or unassessed criterion stays visible. The judgment applies to that criterion and the assessed test scope. |
| Residual risk or limitation | The unresolved exposure and the limits on the summary. | Separate an observed unresolved anomaly from a residual risk that is still uncertain. A limitation names missing runs, missing evidence, excluded scope, an unknown tested configuration, or configuration drift that the counts do not remove. |
| Recommendation | One recommendation about further testing. | Label it as a recommendation. It may advise more testing, no further testing in this scope, or that the recommendation cannot be made. Treat it as a proposal, with any actual completion-review decision recorded separately. |
| Archive | One statement of the records and assets to be retained. | Name only plans, data, environments, runs, and evidence that exist, with their versions. State the established project retention periods, preservation arrangements, and access restrictions for those objects. When retention is not established, say so. A described archive is not proof that the objects were preserved. |
| Completion-review decision | Zero or one actual decision. | Cite the decision and identify its actual decision maker when a completion review occurred. When none occurred, say so. State the decided test-completion position, its scope, and any conditions. |
| Action citation | Zero or more existing actions. | Cite a real action record only when that action exists. A described next step without a record is not given an identifier. An empty list is not a claim that no action exists unless the actions were assessed. |

Use prose for the end condition, the recommendation, and the limitations. Use a count table when several units must be compared, and one row per completion criterion. Do not add an empty run, a generic document-control block, or a run log.

## Quality criteria

- The report covers one campaign or phase that has ended, including a campaign supported by a single run. Its summary cites the run records, with their supporting observations traceable.
- Planned scope, unselected remaining scope, `not-run`, `pass`, `fail`, and `inconclusive` are not substituted for one another. Executed outcomes name a run record or another observed source and its time. Unknown is not zero.
- Tested configurations come from the cited runs. The plan's intended version is not substituted for them.
- Every adopted completion criterion has a met, not-met, or not-assessable judgment. A campaign that ended with open criteria does not read as if those criteria were met.
- Anomaly totals match the named master's current state. `resolved`, `verified`, and `rejected` are not reported as closed. A reopened count is not added on top of another state count unless the overlap is stated. Deviations and earlier failed attempts remain visible beside any retest.
- The recommendation records proposed further testing. A completion-review decision identifies the actual decision maker and the scope of the decided test-completion position. Cite existing requirement-conformity or intended-use assessment results when they inform that position, with their scope and evidence locators.
- Each cited plan, run, anomaly view, problem record, risk, decision, or action exists and has a locator and the edition or as-of time needed to identify the cited content.
