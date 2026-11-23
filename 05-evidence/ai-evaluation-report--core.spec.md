---
title: "AI evaluation report specification"
description: >-
  Defines the authoring contract for AI evaluation reports preserving an actually performed empirical evaluation of an identified AI model, checkpoint, or compound AI system configuration. Covers evaluated system snapshots and decoding settings, benchmark, rubric, human-evaluation, and adversarial red-team suites with versions and data-contamination disclosures, scoring and judge-calibration methods, observed capability, safety, robustness, and operational metrics with statistical uncertainty and disaggregated error slices, execution anomalies, validity limits, retained artifact integrity, and bounded conclusions kept strictly separate from deployment approval.
topics:
  - "evidence"
  - "ai-and-ml"
  - "verification-and-validation"
  - "ai-evaluation"
  - "model-benchmarking"
  - "red-teaming"
  - "evaluation-metrics"
  - "judge-calibration"
use_when:
  - "An AI model, checkpoint, or compound AI system has undergone empirical capability, safety, robustness, or red-team evaluation requiring a traceable evidence report."
  - "An AI engineer or evaluator is recording exact evaluated snapshots, benchmark editions, judge calibration, stochastic run variance, and subgroup error slices."
  - "A reviewer or release authority is assessing what claims observed AI evaluation scores support and which contamination, coverage, or validity limits remain open."
not_for:
  - "Disclosing an AI model or system's intended uses, composition, provenance summary, and oversight obligations to deployers, which belongs in an AI model or system card."
  - "Recording deterministic technical requirement conformance verdicts alone, which belongs in a verification evidence record."
  - "Summarizing an ended deterministic software test campaign against test-plan exit criteria, which belongs in a test completion report."
  - "Documenting a curated evaluation or training dataset's provenance, composition, and licensing, which belongs in a dataset specification."
---

# AI evaluation report specification

## Identity and selection

- **Specification ID:** `AI-EVALUATION-REPORT@core`.
- **Purpose:** Preserve an empirical AI model or system evaluation that was actually performed, binding evaluated configurations, suites, scoring methods, observed metrics, uncertainty, failure slices, and validity limits into one auditable evidence record.
- **Intended readers:** AI and machine-learning engineers, safety and alignment evaluators, product and system owners, independent reviewers, and authorities deciding readiness or further testing.
- **Decision or action supported:** Determine what capabilities, safety behaviors, failure modes, and comparative deltas were observed for an exact AI configuration, assess measurement reliability, and bound downstream claims or deployment decisions.
- **Use when:** An AI model, fine-tuned checkpoint, prompt or retrieval pipeline, or compound AI system has started or completed empirical evaluation and the observed results must be traced to exact inputs, configurations, and limits.
- **Scope boundaries:** Report empirical AI evaluation work actually performed on identified snapshots within stated suites, methods, and operating conditions; exclude planned-only evaluation schedules, unexecuted benchmarks, weaponized exploit payloads, and automatic release or safety certification.

## Authoring inputs and unresolved facts

Obtain the evaluation question and campaign completion state (partial or complete); the exact evaluated model, checkpoint, weights digest, or compound AI system snapshot including system prompts, retrieval corpus revision, tool permissions, runtime guardrails, serving stack, and decoding or inference parameters; any comparison baselines and whether they ran under identical harness conditions; each executed benchmark, dataset, rubric, red-team, or human-evaluation suite with exact edition, split, sample size, prompt template, and known contamination or leakage basis; the evaluation harness version, performer or evaluator roles, independence facts, execution window, and repeated-run seeds; scoring formulas, deterministic verifiers, model-based judge configurations and calibration evidence, or human-rater protocols and inter-rater agreement; observed aggregate and disaggregated slice metrics, variance or confidence bounds, operational measurements, failure modes, and execution anomalies; retained artifact locators and SHA-256 digests when preserved as byte sequences; technical review status; and any separate decision that consumes this report.

If a model revision, decoding parameter, harness version, dataset edition, contamination status, judge calibration, rater agreement, or sample size is unknown, state that gap explicitly and bound every metric or comparison that depends on it. Do not treat unexecuted suites as passing, unreported failure slices as safe, uncalibrated model-based judge scores as ground truth, or single stochastic runs as deterministic behavior. Keep failed, truncated, or filtered evaluation runs visible alongside any reruns. Do not invent baseline parity, statistical significance, safety clearance, or deployment approval. Cite dataset specifications, system cards, or downstream authorization records only when they actually exist.

## Finished-document contract

- **Title:** Name the evaluated AI model or system, its snapshot or release scope, and identify the document as an AI evaluation report.
- **Frontmatter:** Required. Begin with a YAML 1.2 Semantic-Discovery frontmatter block delimited by `---` lines containing `title`, `description` (60 to 140 neutral retrieval words), `topics` (3 to 12 concrete lowercase kebab-case terms), `use_when` (2 to 6 neutral task conditions), and conditional `not_for` (1 to 5 grounded exclusions, omitted when empty), followed by the GFM H1 title. Exclude internal IDs, version strings, hashes, filesystem paths, build metadata, and unresolved template delimiters from frontmatter values. Evaluated configurations, suites, observed scores, and limits belong in the body. Governing source: Collection Semantic-Discovery Frontmatter contract.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. Omit it for internal documents unless a specific project policy requires explicit negative attestation. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Establish evaluation scope and exact evaluated snapshots before suites and scoring methodology; present observed results and disaggregated slices before failure analysis, validity limits, retained artifacts, and decision boundaries. Heading wording may vary.
- **Presentation:** Use concise factual prose paired with structured configuration, suite, metric, and slice tables sized to the evaluation campaign. Required roles may share sections while keeping evaluated snapshots, harness parity, uncertainty, execution anomalies, and validity limits directly retrievable.

| Projection | Title and metadata ownership | Syntax and source authority |
| --- | --- | --- |
| AI evaluation report (standalone) | Begin with the mandatory 5-key Semantic-Discovery YAML frontmatter followed by one evaluation-specific H1. Evaluated snapshot identity, harness configuration, timing, independence, and observed outcomes remain body content; external specification provenance and corpus-level default maintenance metadata apply where governed in a unified corpus. | Use GFM prose, tables, or logs bound to immutable evaluated snapshots, benchmark editions, and retained raw evaluation outputs. Historical measurements remain attached to their tested configuration and time; changed models, prompts, guardrails, or harnesses require a new evaluation record rather than rewriting prior evidence. |

| Section role | Status and inclusion condition | Content obligation |
| --- | --- | --- |
| Evaluation scope and evaluated subject | Required | State the evaluation question, whether the campaign is complete or partial, execution dates, performers and independence arrangement, exclusions, and the client or receiving-party element when applicable. Bind every evaluated subject to its immutable identity: model or checkpoint version, weights digest when available, system prompt and orchestration revision, retrieval index edition, enabled tools, runtime safeguards, inference runtime, and decoding parameters. Identify each comparison baseline at the same precision and state any configuration or harness differences. |
| Evaluation datasets, suites, and methodology | Required | Identify every benchmark, custom evaluation set, human-review protocol, or adversarial suite actually run, with exact edition, split, sample size, prompt-formatting edition, harness version, and data-contamination or leakage disclosure. Define every metric formula, threshold, aggregation rule, and stochastic sampling protocol. For automated model-based judges, state judge model, version, prompt, and actual calibration against human ground truth or mark calibration absent; for human raters, state rater criteria, blinding, and observed inter-rater agreement. |
| Observed results and disaggregated slices | Required | Report observed capability, quality, safety, robustness, calibration, and operational measurements (such as latency, throughput, or token cost when measured) per suite and evaluated subject. Report stochastic variance across seeds or repeated trials and confidence intervals only when the statistical method supports them. Present disaggregated results across relevant subgroups, languages, domains, difficulty tiers, or risk categories so aggregate scores do not conceal localized regressions or disparities. |
| Failure analysis, anomalies, and red-team findings | Conditional when adversarial red-teaming, safety probing, qualitative error categorization, or execution anomalies occurred | Summarize observed failure modes, refusal and false-refusal patterns, severe safety or policy failures without reproducing hazardous operational exploit instructions, and any harness errors, rate-limit truncations, timeout retries, or excluded samples with exact counts and effects on reported scores. Keep earlier failed runs visible beside any reruns. |
| Validity limits, retained artifacts, and decision boundary | Required | State known threats to internal and external validity, including benchmark saturation, contamination uncertainty, judge bias, synthetic-to-production gap, unexamined modalities or populations, and configuration drift. Cite retained raw outputs, logs, scripts, and SHA-256 digests where preserved as byte sequences, or state retention limits. Record technical review state, bounded conclusions supported strictly by observed results, clearly labeled recommendations, and separate citations to any actual release or deployment decision without implying authorization. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
| --- | --- | --- |
| Evaluated AI snapshot | One or more immutable evaluated configurations in Evaluation scope and evaluated subject. | Capture exact model or checkpoint version, compound-system components (prompts, retrieval, tools, guardrails), serving runtime, and decoding parameters. Missing configuration parameters block reproducible comparison claims. |
| Comparison baseline | Zero or more reference models, prior releases, or human baselines in Evaluation scope and evaluated subject and Observed results and disaggregated slices. | State whether the baseline ran under the exact same harness, prompt edition, and dataset split or cite external published scores with explicit non-comparability caveats. |
| Evaluation suite | One or more actually executed benchmarks, datasets, rubrics, or red-team suites in Evaluation datasets, suites, and methodology. | Identify exact edition, split, sample count, source or dataset specification locator, and whether execution was full or sampled. Planned but unexecuted suites are excluded from results and listed as uncovered scope. |
| Contamination disclosure | One account per evaluation suite in Evaluation datasets, suites, and methodology. | State assessed training-data overlap, decontamination checks actually performed and their limits, or explicitly record contamination status as unknown. Unknown overlap is never reported as clean. |
| Scoring and judge apparatus | One explicit scoring definition per reported metric in Evaluation datasets, suites, and methodology. | Distinguish deterministic exact or programmatic scorers, model-based judges, and human raters. Model-based judge scores require explicit judge identity, prompt edition, and calibration evidence or an explicit uncalibrated-judge limitation. |
| Observed metric and uncertainty | One observed account per executed metric-subject pair in Observed results and disaggregated slices. | State exact units, sample denominator, number of runs or seeds, observed value, and method-supported spread or confidence interval. Do not report fabricated precision or claim statistical significance without a recorded test. |
| Disaggregated slice | Zero or more subgroup, domain, language, or risk-category breakdowns in Observed results and disaggregated slices. | State slice definition, sample count, and observed metric. Flag small-sample instability explicitly; state when disaggregation was not performed and the resulting blind spot. |
| Failure or anomaly record | Zero or more categorized failure clusters, red-team outcomes, or execution anomalies in Failure analysis, anomalies, and red-team findings. | Record exact counts, severity basis if declared, affected slice, and impact on validity without including actionable exploit payloads. Preserve failed or truncated runs rather than silently dropping them. |
| Retained evaluation artifact | Zero or more immutable raw outputs, prompt logs, scoring tables, or environment manifests in Validity limits, retained artifacts, and decision boundary. | Give actual storage locator, format, access or retention limits, and 64-character lowercase SHA-256 digest when preserved as a single byte sequence. If raw outputs were not retained, state that limit explicitly. |
| Bounded conclusion and decision citation | One or more conclusions, zero or more labeled recommendations, and zero or more actual decision citations in Validity limits, retained artifacts, and decision boundary. | Every conclusion cites its supporting observed metrics and stays inside evaluated scope and validity limits. Separate technical review state from release, safety, or deployment authorization; cite a decision only when it actually occurred. |

Use structured tables for evaluated snapshots, executed suites, aggregate-versus-slice metric comparisons, and retained artifact manifests, paired with concise prose for methodology, failure patterns, validity threats, and bounded conclusions. Retain raw logs, model responses, and automated harness outputs as separate immutable artifacts bound by locator and digest rather than pasting large transcript dumps into the Markdown report. Do not include blank result rows, invented baselines, or embedded operational exploit scripts.

## Quality criteria

- Every reported score binds to an exact evaluated model or compound AI system snapshot, inference configuration, suite edition, split, and sample denominator; unknown parameters bound dependent claims.
- Baseline comparisons disclose exact harness and prompt parity or explicitly mark non-comparable external numbers.
- Contamination checks, stochastic run variance, deterministic versus model-judge versus human scoring methods, and judge calibration or rater agreement are explicitly stated or exposed as gaps.
- Aggregate metrics are accompanied by relevant disaggregated slices or an explicit disaggregation gap, and execution anomalies, truncated runs, and excluded items remain visible.
- Failure and red-team summaries document concrete failure patterns and risk boundaries without reproducing hazardous operational exploit instructions.
- Conclusions and recommendations remain strictly bounded by observed data and validity limits; technical review state and any external deployment or release decision are recorded separately from empirical scores.
