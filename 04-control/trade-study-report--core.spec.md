# Trade study report specification

## Identity and selection

- **Specification ID:** `TRADE-STUDY-REPORT@core`.
- **Purpose:** Compare credible alternatives against mandatory gates and explicit criteria, and record the assumptions, evidence, sensitivity, risks, and recommendation or decision handoff.
- **Intended readers:** The analyst, the decision authority, and later readers who need to see whether the comparison can support a choice.
- **Decision or action supported:** Judge which alternatives remain viable and whether the stated recommendation is robust enough to take to the decision authority.
- **Use when:** A choice depends on comparing credible alternatives against gates, criteria, evidence, uncertainty, and risk.
- **Scope boundaries:** Address one decision question through a comparison of credible alternatives. Label the recommendation as proposed and cite any actual authorized decision separately.

## Authoring inputs and unresolved facts

Inspect the system or subject, the decision question, the lifecycle point, the boundaries, and the comparison baseline, which is the reference state or no-change option used for evaluation; the goals, objectives, requirements, and constraints, with mandatory gates distinguished from preferences and each gate tied to a supplied project need, requirement, constraint, or decision; each criterion's meaning, scale, preference direction or threshold, data quality, and weight or rank when the method uses one; the comparison method and the information available to it; every input the results depend on, including provenance, assumptions, cost when cost is a criterion, and uncertainty; the feasible alternatives, the baseline or no-change option when it is credible, and the screened-out options with reasons; the calculations or the analysis artifact that contains them; sensitivity, ties, and unquantified factors; material risks; the selection rule and whether it was fixed before the results were known; the recommendation, or the decision body's instruction to withhold one; and any authorized decision that already exists.

When a fact is unknown or not established, keep it unknown, state its consequence, the resolving action, and the actual owner if assigned. An unknown mandatory criterion does not mean an alternative meets that gate. Record each gate comparison as meets, does not meet, or not established. Do not invent an alternative, a weight, a score, a source, a check, or a decision.

## Finished-document contract

- **Title:** Name the decision question and identify the document as the trade study for that question.
- **Frontmatter:** None. Begin with the GFM title. The subject, criteria, results, and recommendation belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State the question and the gates before the measures. State the measures and method before the results. State screened and compared alternatives before the recommendation. Place the selection rule with the recommendation. Place the decision handoff after the recommendation. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Decision question and constraints | Required | Identify the subject, decision question, lifecycle point, boundaries, and comparison baseline, or state that none is established. Define that baseline as the reference state or no-change option used for evaluation. State the goals and constraints. Separate mandatory gates from preferences, state each gate's explicit criterion and project need, requirement, constraint, or decision basis, and identify its source or mark it not established. |
| Criteria, measures, and method | Required | Define each criterion used to gate or rank alternatives, including how it is observed or judged, its threshold or preference direction, its scale, and its data quality. State a weight or rank only when the method uses one, with the reason. Name criteria that were considered and then excluded, with the reason. State the method, why it fits the information available, and its limits. |
| Alternatives | Required | Identify the alternatives that were gated or ranked, the baseline or no-change option when it is credible, and the options screened out before full evaluation with the reasons. When only one option remains viable, show that screening. Include doing nothing when it was considered. |
| Results, uncertainty, and risk | Required | For each alternative that remains after screening, give the result against each criterion. Put the calculation in the report or cite the analysis artifact that contains it, and state whether the arithmetic or tool output was checked. State whether uncertainty could change a gate or the ranking, what was varied, any tie or close rank, and unquantified factors. State the material risks of the alternatives and of following the recommendation, or cite an assessed risk record when one holds that statement. |
| Selection rule and recommendation | Required | State the rule, including hard gates, and whether it was fixed before the results were known. Apply gates before preference scores. State the recommendation and its limitations, or state that the decision body asked for the comparison without a recommendation. When the recommended option is not the highest scored option, explain why. When uncertainty could change the ranking, name the close alternatives. |
| Decision handoff | Required | Cite an authorized decision only when one exists, including a decision made before this report was written. Otherwise state that no authorized decision is recorded. Identify the decision authority the recommendation is for when that authority is known. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Subject and question | One subject and one decision question. | Bind the lifecycle point, boundaries, and comparison baseline. That baseline is the reference state or no-change option used in the comparison. Keep the evaluated alternatives and recommendation within this question. |
| Gate | Zero or more mandatory criteria, each with a source or an explicit gap. | State the criterion and its supplied project need, requirement, constraint, or decision basis. For each alternative, record whether it meets the gate, does not meet the gate, or the comparison is not established. Not established does not mean the alternative meets the gate. An alternative that does not meet a gate is screened out of preference ranking. Use only these three comparison states for the gate result. |
| Criterion | One or more criteria used, plus any considered and then excluded. | State meaning, observation or judgment method, threshold or preference direction, and data quality. A normalized or ordinal scale needs an operational definition of each step. A weight or rank appears only when the method uses it and the reason is stated. An ordinal label is not a physical measurement. |
| Method | One method actually used. | Name the method and its limits. Select it for this decision and the information in hand. A tool's scale is explained in the report rather than trusted from the tool name. |
| Input | Every input the results depend on. | Give provenance, the assumption it carries, and its uncertainty. When cost is a criterion, include the cost basis. When the study uses no external data, say so and identify the judgment it relies on. |
| Alternative | Each option considered. | Separate screened-out options from options that were evaluated. Give the screening reason. Do not add a second scored option to fill a table. Doing nothing is recorded when it was considered. |
| Result | One result per evaluated alternative per criterion used. | Show the calculation or cite the artifact that contains it and its edition or location. State whether the arithmetic or tool output was checked. An unchecked result stays unchecked. |
| Uncertainty and sensitivity | One account. | State whether a plausible change in inputs could change a gate or the ranking, what was varied, ties, close ranks, and unquantified factors. When sensitivity was not assessed, say so. Silence is not a robustness claim. |
| Risk statement | One account, which may cite a risk record. | Cover material risks of the evaluated alternatives and of following the recommendation. Cite a risk register entry only when one exists. The citation does not replace the statement of how the risk affects the comparison. |
| Selection rule | One rule. | Include the hard gates and the ranking rule. Say whether the rule was fixed before the results were known. When criteria or weights change after scores are seen, state the change and the decision-maker concurrence when that concurrence exists. |
| Recommendation | One recommendation, or an explicit statement that none was requested. | Label the choice as recommended, state its limitations, and identify the decision authority when known. Name close alternatives when uncertainty could change the rank. Explain a recommendation that departs from the highest score. |
| Decision citation | Zero until an authorized decision exists; one when it does. | Cite the decision, its scope, and its authorizing role. Record it separately from the recommendation and comparison results. A decision made under time pressure may predate the finished report; preserve its actual identity and timing. |

Use prose for the question, method limits, and recommendation. Use a table for criteria and for alternative-by-criterion results when those values are real. Use a list for screened-out options and evidence citations. Do not add an empty score, a fabricated alternative, or a generic document-control block.

## Quality criteria

- Mandatory gates are applied before preference scores, and an unknown gate does not mean the alternative meets it.
- Each scale used for ranking has an operational meaning, and an ordinal score is not presented as a physical measurement.
- The results can be recomputed from the report or from a cited analysis artifact. An arithmetic or tool check is claimed only when it was done.
- The recommendation matches the stated rule, or the departure from the highest score is explained.
- Close alternatives stay visible when uncertainty could change the ranking.
- The recommendation is labeled as proposed and the authorized decision is separately identified and cited. A missing decision stays missing.
- Screened options and their reasons remain visible. The study does not invent a competitor for a single viable option.
- No weight, score, risk, or conformance claim appears without an identified basis.
