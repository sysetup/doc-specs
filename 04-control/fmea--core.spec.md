# Failure modes and effects analysis specification

## Identity and selection

- **Specification ID:** `FMEA@core`.
- **Purpose:** Record how a bounded item or process can fail to perform its functions, with effects, causes, existing controls, and priority under one declared method, so treatment can be chosen and incomplete assessment stays visible.
- **Intended readers:** Analysts, design or process owners, treatment owners, and reviewers of the analysis.
- **Decision or action supported:** Readers can see which failure modes need treatment, which priorities rest on missing data, and which residual rankings are projections rather than observed results.
- **Use when:** A systematic failure-mode analysis is required, including criticality ranking when the declared method is a failure modes, effects, and criticality analysis.
- **Scope boundaries:** Analyze failure modes of the declared functions within the stated item or process boundary. Relate a mode to actual hazard, risk, defect, or action records when relevant. Bound priority and residual claims to the declared method and the evidence of assessment or reassessment.

## Authoring inputs and unresolved facts

Obtain the item or process boundary, configuration or revision, lifecycle, and function decomposition; the assumptions; whether the method is FMEA or FMECA; the priority or criticality rule and its scales; the responsible analyst if assigned; the functions and failure modes; local and higher-level effects; causes and their evidence; prevention and detection controls that are actually present and any basis for their effectiveness; rankings and the combination rule; recommended or committed actions; and any residual reassessment with its evidence. Inspect an existing hazard, risk, defect, or action record only when it already bears on a row.

If a function, mode, effect, cause, scale, ranking, rate, owner, or reassessment is unknown or not established, record that status, its effect on priority, the resolving action, and an actual owner if one is assigned. Do not turn a missing ranking into zero or one, invent a failure rate or mode proportion, or label a projection as demonstrated. If the method is not chosen, do not publish a priority result. When a decomposition level does not apply, say why. An analysis that has not examined the declared functions says so; it does not claim that no failure modes exist. Use an observation only when its configuration and conditions support the affected row's assessment.

## Finished-document contract

- **Title:** Identify the item or process and name the document an FMEA or an FMECA according to the method actually used.
- **Frontmatter:** None. Begin with the GFM title. The method, worksheet, and review belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Give scope, method, and scales before the rows. Present review and maintenance with or after the rows. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Scope and method | Required | State the boundary, lifecycle, configuration or revision, decomposition, assumptions, as-of point, and the responsible analyst or the assignment gap. Choose FMEA or FMECA. FMEA records failure modes, effects, causes, controls, and treatment priorities. FMECA additionally ranks criticality using at least consequence severity and the other importance measures declared in the method. State the complete priority or criticality rule. Declare each scale that rule uses, or state that the method is unresolved and give no invented scale. For FMECA, state the criticality basis. |
| Failure-mode rows | Required | If the decomposition is unresolved, say so and do not invent functions or modes. Otherwise, for each declared function, record each identified mode or an explicit conclusion that no credible mode was identified, with the basis for that conclusion. Each mode states its function, mode and conditions, effects, causes or an explicit gap, existing controls or an explicit none, rankings or unresolved rankings, and a priority result or an unresolved priority. Separate recommended actions from existing controls. Give residual rankings and a residual state only as the evidence supports. Do not add a placeholder mode. |
| Review and maintenance | Required | State coverage against the decomposition, interfaces, assumptions, high-consequence modes, and incomplete data. State what triggers an update. Cite a specific design change, test, incident, or field record as a trigger only when that record exists. State how prior rows are retained or superseded. If a controlled worksheet or database is the master, identify its revision, locator, and responsible internal role, and keep the representations consistent. Summarize rows whose cause, ranking, or residual state blocks a treatment decision. A review date belongs only to a review that occurred. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Scale | One per dimension the declared method uses. None while the method is unresolved. | Before a row uses a scale, give its name, allowed values, meaning, direction, and evidence expectation. State the project's method-selection decision and revision when recorded; otherwise identify the selection gap. Do not invent an approval. |
| Priority or criticality rule | One rule for the analysis. | State the complete qualitative decision rule, criticality matrix, or risk priority number (RPN) formula used, its inputs, and any threshold actually used. Define qualitative levels, matrix cells, or arithmetic operations so each result can be reproduced from the stated inputs. A missing input stays unresolved. |
| Criticality basis | Required when the method is FMECA; absent from the ranking when the method is FMEA. | Include failure rates, mode proportions, exposure, and their uncertainty only when the chosen criticality method uses them. Do not compute a result from inputs that were not established. |
| Failure-mode row | One per identified mode. A function may instead have one documented conclusion that no credible mode was identified. | Give every mode a stable ID. The mode is how the stated function fails under stated conditions. Identify related project records and their locators when they support the effects, causes, controls, or actions. |
| Effects | Local, next-level, and end effect for each mode, except a level the decomposition makes inapplicable. | Keep applicable levels distinguishable. Tie any severity word to the declared scale. |
| Cause | Zero or more mechanisms, plus an explicit gap when none is established. | Label a hypothesis as a hypothesis and give its source or assumption. Do not fill the gap with a generic cause. |
| Existing control | The prevention and detection controls available to credit for that mode, or an explicit statement that none are identified. | State coverage and the basis for any effectiveness claim. A recommended or unimplemented action is not an existing control. |
| Ranking | One per declared scale for an assessed mode, or an explicit unresolved ranking. | The value is one allowed value of the referenced scale, with the data or uncertainty behind it. |
| Priority result | One per assessed mode, or an explicit unresolved result. | Show the rule and the inputs that were used. Do not combine undefined scales. |
| Action | Zero or more recommendations or commitments. | State owner and timing when the action is committed. Describe it in the row when no separate action record exists. A reference is optional. Recording the action does not show that it was completed. |
| Residual ranking | Conditional on a projected or demonstrated reassessment. | Label a projection as a projection. A demonstrated value cites the evidence of the observed reassessment. `not-assessed` has no residual ranking presented as a result. |
| Residual state | One per mode: `not-assessed`, `projected`, or `demonstrated`. | `not-assessed` means no residual reassessment is established. `projected` describes an expected reassessment outcome. `demonstrated` cites evidence of an observed reassessment, which may show that the projected improvement was not achieved. An action identifier alone establishes no reassessment. |
| Row owner | One analyst or owner once assigned. | This role is not the review authority. If unassigned, record the gap rather than inventing a person. |
| Review statement | One for the analysis. | Say what was examined and what was not. Include a review date only for a review that occurred. |
| Master representation | One statement. | The Markdown worksheet is sufficient. Identify an external worksheet or database when that artifact is the master. Do not require an embedded JSON copy or maintain two conflicting masters. |

Use a worksheet table with meaningful function, mode, effects, causes, controls, priority, and residual-state columns. Define the scales before the ratings that use them. Use linked detail or short prose when a ranking basis, effect chain, or uncertainty will not fit without ambiguity. Do not include blank rows, a generic document-lifecycle block, or a synthetic-data flag.

## Quality criteria

- The method, scales, and combination rule are sufficient to interpret every stated priority, or the missing piece is explicit.
- FMECA rows carry the criticality measures that method declares. FMEA rows do not present a criticality result.
- Where more than one effect level applies, local, next-level, and end effects remain distinguishable.
- Existing controls, recommended actions, projected residual rankings, and demonstrated evidence are distinguishable.
- A missing cause, rate, or ranking stays unresolved; a numeric zero requires data supporting that value. A conclusion that no credible failure mode was identified requires examination of the declared function and a stated basis.
- Completed treatment and observed residual reassessment are stated only when supported by actual evidence, with configuration, conditions, and locators. A demonstrated residual value must be supported by that evidence.
