# Business or mission needs specification

## Identity and selection

- **Specification ID:** `BUSINESS-NEEDS@core`.
- **Purpose:** Establish a sourced account of a business or mission problem or opportunity, the affected stakeholders, and the outcomes sought before solution obligations are fixed.
- **Intended readers:** The business or mission sponsor, affected stakeholder representatives, analysts, and decision makers who will decide whether and how to address the need.
- **Decision or action supported:** Readers can judge the need's basis, importance, and boundaries, decide what remains to be learned, and use the established outcomes to frame later requirements or option analysis.
- **Use when:** A business or mission need must be understood and assessed before committing to particular solution requirements.
- **Scope boundaries:** Describe the problem or opportunity and the effects sought before fixing solution obligations. Keep candidate options at the level needed to judge the need, with their actual evaluation and decision state.

## Authoring inputs and unresolved facts

Obtain the actual business or mission purpose, sponsor or requesting authority if identified, decision scope and time horizon, current operating condition, evidence of the problem or opportunity, affected stakeholder groups and their inspected perspectives, drivers, desired outcomes, and available baseline measures. Identify established project limits, including resource, schedule, operating, or delivery limits, dependencies on outside parties or services, and uncertain premises that materially shape the need. Determine whether any outcome, target, or source has actually been endorsed, remains a candidate, or is disputed. Inspect existing project analyses or decisions if they establish options or boundaries.

For an unknown baseline, stakeholder position, measure, target, source, or authority, state what is unknown, why it matters, the action to resolve it, and the actual owner if assigned. Mark a desired outcome as proposed when its authority or target is not established; do not invent a measurement, sponsor, interview, or endorsement. An inapplicable constraint or option-analysis section may be omitted after assessing its relevance. If a claimed constraint lacks an identifiable project decision or factual basis, present it as a premise or candidate constraint, not as an established limit. Keep an attractive option visibly exploratory until an actual selection decision exists.

## Finished-document contract

- **Title:** Name the business or mission subject and identify the document as a statement of needs; a generic “Business Needs” title is insufficient.
- **Frontmatter:** None. Begin with the GFM title. The scope, source, and decision state of the need belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Establish purpose and current condition before desired outcomes; present any options after the needs they might address. Put unresolved decisions and confirmation state after the substantive analysis. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Purpose, scope, and decision frame | Required | State the business or mission purpose, the bounded activity or population, included and excluded concerns, the intended decision or later work this needs statement will inform, and the document's actual edition or draft state where controlled. Identify the requesting or sponsoring authority when established. |
| Current condition and need | Required | Describe the present capability or situation, the problem or opportunity, its drivers and consequences, and the evidence or observation supporting each material claim. Distinguish observed conditions from interpretations and uncertain premises. Explain the gap between the current condition and what is sought. |
| Stakeholders and perspectives | Required | Identify the materially affected stakeholder groups, their interests or impacts, and the real sources of those perspectives. Record disagreement or unrepresented groups that could change the need; do not imply that a group was consulted when it was not. |
| Desired outcomes and effectiveness | Required | State one or more separately identifiable desired business or mission effects, each linked to a need and source. Give an assessable measure or observation basis, relevant conditions and time horizon, known baseline, and desired target or decision criterion when established. Clearly label candidate targets and measurement gaps. |
| Boundaries, constraints, and assumptions | Conditional when a material limit, dependency, or uncertain premise affects interpretation or feasibility | Identify each established project constraint, including resource, schedule, operating, or delivery limits, with its project basis, responsible party, and scope; distinguish it from an assumption or design preference. Explain material capability gaps and dependencies when they affect the outcomes. |
| Solution space and options | Conditional when credible solution classes have been considered or the decision requires option framing | Characterize feasible classes at a level useful for later analysis, including no change when relevant. If options were evaluated, state the actual criteria, evidence, tradeoffs, and decision state. Do not imply that an unevaluated class is feasible or an explored option is selected. |
| Confirmation and unresolved matters | Required | State which need and outcome claims are established, proposed, or disputed, the basis and scope of any actual sponsor or stakeholder confirmation, and material missing facts or decisions with resolution paths. Established means the claim has a real source, not that the outcome was achieved. Explain how changed evidence or priorities would prompt reconsideration. Refer to real downstream requirements or decisions only when they exist. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Need scope | One coherent business or mission problem or opportunity area per document. | Identify the organization, mission, activity, population, and time horizon only to the extent they define applicability. Do not combine unrelated investments under a vague common heading. |
| Need statement | One or more distinct problem, opportunity, or capability-gap statements. | Give each a stable local label or project ID, affected context, actual source, and consequence. Phrase the need without prescribing a particular system or implementation. |
| Stakeholder group | One or more materially affected groups. | State the group's interest or impact and identify inspected evidence or an explicitly unconfirmed perspective. A list of names alone does not establish a need. |
| Desired outcome | One or more distinct effects, each with a stable label or ID. | Relate it to a need and source. State what observable change would indicate progress, over which population or conditions and period. Label the target's established, proposed, or disputed state; the target states what is sought and does not claim attainment. |
| Effectiveness measure and target | One assessable basis for each outcome; a numeric target is conditional on an actual decision. | Give units, collection or observation method, and timeframe where meaningful. Identify the known baseline or its absence; do not substitute zero for unknown. Qualitative criteria may be used when they are observable and their interpretation is clear. The measure states what would indicate progress. It does not assign `pass`, `fail`, `inconclusive`, or `not-run`. |
| Constraint or assumption | Zero or more, included when material. | A constraint has an identifiable project decision, commitment, or operating fact as its basis and a stated applicability. An assumption states an unconfirmed premise, its effect, and the action needed to test it. |
| Option or forward relationship | Zero or more real options or links. | Identify the option's source and decision state. For an established relationship to a project requirement, analysis, or decision, identify the related record and the need or outcome it addresses. |

Use prose for context, evidence, and uncertainty. A compact table with need/outcome ID, effect, measure, baseline, target or gap, and source is suitable for repeated outcomes. A simple current-to-desired flow or context diagram MAY clarify a complex boundary, but it MUST NOT replace the explanatory need statements. Use an option comparison only when options have actually been analyzed; do not create empty candidate rows.

## Quality criteria

- The problem or opportunity, affected groups, and desired effects are understandable without first choosing a solution; each outcome traces to a real need or source.
- Measures and targets distinguish known baselines, proposed aspirations, and authorized decisions. A plan to measure is not evidence that an outcome was achieved.
- Need and outcome statements describe sought effects and measurement bases with explicit proposal or confirmation states.
- Constraints have an established project basis and assumptions remain visibly uncertain. Options retain their actual evaluation and selection state.
- Conflicting evidence, missing stakeholder perspectives, and unresolved authority or measurements are visible with their consequences and resolution routes.
- Any confirmation or endorsement is limited to its actual scope; authorship, circulation, or a draft status does not establish endorsement or attainment of the proposed outcomes.
