# Technical analysis report specification

## Identity and selection

- **Specification ID:** `TECHNICAL-ANALYSIS-REPORT@core`.
- **Purpose:** Record a technical analysis that was performed, so its question, inputs, method, assumptions, results, uncertainty, limitations, and conclusions can be reviewed and traced.
- **Intended readers:** The analyst, a reviewer of the analysis, and anyone who may rely on the result when making a later decision.
- **Decision or action supported:** See what question was asked, what work was done, what was observed, how uncertain the result is, and which conclusions or recommendations the recorded work supports.
- **Use when:** Analysis work has started or finished, and the question, sources, method, assumptions, results, uncertainty, reproducibility, limitations, and conclusions must be recorded. A partial report covers only work already performed.
- **Scope boundaries:** Performed technical analysis of a stated question within a defined configuration, environment, and period. Findings and recommendations cover only the work actually performed.

## Authoring inputs and unresolved facts

Obtain the technical question; whether the work on that question is partial or complete; the system or configuration, environment, period, and exclusions; the inputs actually used and their versions; the assumptions the results depend on; the method, including equations, algorithms, tooling, and configuration that affects the result; who or what performed the work; tool versions when they affect reproduction; the filtering, transformations, exclusions, units, and quality checks actually applied; the limitations and threats to validity; the observations and the interpretations drawn from them; the uncertainty the method supports; artifacts retained; anomalies, failed runs, and data-quality issues that occurred; the conclusions and any recommendations; whether this report has been technically reviewed; and any decision that actually uses the analysis.

If an input version, a tool version, a unit, a performer, or an uncertainty basis is unknown, state that gap and limit every conclusion that depends on it. Do not invent a measurement, a bound, a precision, a successful rerun, or a decision. Cite a model, dataset, trade study, decision record, risk entry, or approval only when it exists and was used or issued.

## Finished-document contract

- **Title:** Name the question and identify the document as a technical analysis report.
- **Frontmatter:** None. Begin with the GFM title. The question, method, results, and conclusions belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State the question and inputs before the method. State results before conclusions. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Question and basis | Required | State one technical question, whether the work on that question is partial or complete, and the configuration, environment, period, and exclusions. Identify the inputs actually used. State each assumption the results depend on, or state that the assumptions were assessed and none were identified. |
| Method used | Required | State the method and the configuration that affects the result, who or what performed the work, the data handling actually applied, and the known limitations and threats to validity. Identify each tool version that is material to reproduction, or state that the version is unknown. |
| Results | Required | Separate observations from interpretations. State the uncertainty, sensitivity, bounds, or qualitative limits the method supports. Identify retained artifacts, or state that the result is contained in this report. Retain anomalies, failed runs, and data-quality issues that occurred, or state that those were assessed and none occurred. |
| Conclusions and decision boundary | Required | State conclusions supported by the recorded results. State the recommendations that follow, or state that none are made. State the technical-review state of this report. Cite a decision that uses the analysis only when that decision exists. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Question | One technical question this analysis addresses. | State the technical property, behavior, cause, prediction, or constraint being examined. Keep alternative-selection decisions, requirement-conformity determinations, and intended-use acceptance determinations outside the question's scope. |
| Progress | One statement: partial or complete for the stated question. | Partial means some of the stated work has been performed and the rest has not. Complete means this report claims the stated question was analyzed to the extent it describes. A plan with no performed work is neither, and it is not this report. |
| Scope | One configuration, environment, period, and exclusion statement. | Results and conclusions do not extend outside that scope by silence. |
| Input | One or more inputs actually used. | Identify the version, edition, or revision, or state that the version is unknown. A source that was not used is not an input. When the analysis uses stated premises and no separate source, those premises are the inputs and are written here. Unidentified inputs make a dependent conclusion not traceable. |
| Assumption | Zero or more after assessment. | Record each assumption the result depends on. An assessed finding of none is an explicit statement. Omitting the statement does not mean there were no assumptions. |
| Method | One method actually used. | Include the equation, algorithm, procedure, or equivalent, and the configuration that changes the result. A method that was only planned is not the method of this report. |
| Performer | One statement of who or what performed the analysis. | Name the people, roles, or tools that did the work. If that fact was not captured, say so. Do not invent an analyst. |
| Tool version | Zero or more, and required for each tool whose version is material to reproduction. | Record the version used, or state that it is unknown. Do not guess a version. A tool that was not used is not listed. |
| Data handling | One account of the treatment actually applied. | State the filters, transformations, exclusions, units, and quality checks that were applied. If none were applied, say so after that assessment. |
| Limitation | One or more known limits or threats to validity. | Include method and data limits that are known. State an unknown threat as unknown rather than as absent. |
| Result | One summary of what the analysis produced. | Label observations separately from interpretations. Give units for quantities. Do not add precision, rounding, or significant figures the method did not produce. |
| Uncertainty | One statement. | Report a bound, sensitivity, or confidence statement only when the recorded method supports it. Otherwise state the qualitative limit. Do not invent an interval or a confidence level. |
| Artifact | Zero or more retained plots, models, datasets, logs, notebooks, or equivalent evidence. | Identify what was retained and where it can be found. If nothing separate was retained, say that the result is only in this report. |
| Anomaly | Zero or more after assessment. | A run of this analysis that did not complete, an excluded data-quality issue, or another anomaly that occurred stays visible. A later successful run does not remove it. Assessed absence is an explicit statement. Describe the event and its effect on the analysis result. |
| Conclusion | One or more statements. | Each statement identifies the recorded result that supports it. A partial analysis does not answer the part of the question that was not analyzed. An unsupported numerical conclusion is not included. |
| Recommendation | Zero or more, with an explicit statement when none are made. | Label proposed next steps as recommendations and identify the recorded results that support them. |
| Review state | One of `not-reviewed`, `in-review`, `reviewed`, or not established. | `reviewed` identifies who reviewed this report and what they examined. The state records examination of this analysis within that review scope. Do not default the state to `not-reviewed` when the state is unknown. |
| Decision reference | Zero or more decisions that use this analysis. | Cite a decision only when it exists. Identify the actual decision and how it used the analysis; do not infer a decision from a recommendation. |

Use prose for the question, method, limitations, and conclusions. Use a table or one block per item when several inputs, artifacts, or anomalies must stay distinct. Do not add a blank row, a generic document-lifecycle block, or an identifier pattern.

## Quality criteria

- Every conclusion stays inside the stated scope, inputs, and method. A quantity that depends on an unknown version or unit shows that gap.
- Observations can be distinguished from interpretations. Uncertainty is not stronger than the method that was recorded.
- Anomalies and failed runs that occurred remain in the report. Assessed absence is explicit and is not inferred from an empty section.
- Recommendations remain proposals supported by the recorded conclusions. Review state records actual examination of this analysis, with the reviewer and review scope identified.
- Cited inputs, artifacts, and decisions exist, and input citations match the versions that were used.
