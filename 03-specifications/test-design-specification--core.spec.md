# Test design specification

## Identity and selection

- **Specification ID:** `TEST-DESIGN-SPECIFICATION@core`.
- **Purpose:** Translate a bounded test basis into test conditions, a justified design approach, planned cases, and assessable coverage.
- **Intended readers:** Test designers, implementers of cases and procedures, test leads, product or system owners, and reviewers of coverage.
- **Decision or action supported:** Select the cases and test conditions to develop, identify the environment and data they need, and decide whether the proposed design covers its stated basis and risks.
- **Use when:** Objectives or obligations for a bounded item need a coherent test design before detailed cases and execution steps are finalized.
- **Scope boundaries:** Define test conditions, techniques, planned cases, and coverage for the bounded item and test basis. Include data, environment, and sequencing needs at the detail required to establish feasibility and interpret the proposed design.

## Authoring inputs and unresolved facts

Obtain the item and configuration to be tested, objectives, applicable project requirements and other established test basis, relevant risks, expected behavior or other result oracles, constraints on test level and technique, and the coverage commitment from the actual project plan or responsible decision when one exists. Inspect feature and interface boundaries, modes, representative and boundary conditions, meaningful negative paths, dependencies, needed test data, environment capabilities, and known exclusions. Record the edition and locator of each real basis; do not infer a requirement or coverage commitment absent from the supplied or inspected project facts.

When the basis, expected behavior, feasibility, or coverage decision is unknown or not established, identify the affected condition or objective, the resulting gap, the resolving action, and the actual owner if assigned. A proposed case may be described as proposed; do not assign it a nonexistent controlled case reference. If no case can yet be derived for a material objective, state the uncovered objective and do not claim the design is complete. Explain an inapplicable technique or condition instead of manufacturing a case. Do not invent test results, coverage achieved in execution, or approvals.

## Finished-document contract

- **Title:** Identify the test item or bounded effort and name the document as its test design specification; distinguish the applicable configuration or edition when it changes the design.
- **Frontmatter:** None. Begin with the GFM title. Item identity, basis, and design state are body content.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Establish scope and basis before conditions and technique; show case derivation before coverage assessment and unresolved design limits. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Design scope and basis | Required | Identify the item and target configuration the design assumes, test level or boundary, objectives, project-basis editions, relevant risks, assumptions, and material exclusions. Distinguish established test-basis obligations from proposed design choices. |
| Test conditions and design model | Required | Enumerate distinguishable conditions or condition classes, their source and priority, applicable modes or partitions, expected behavior or oracle, and the selected techniques and rationale. Address normal, boundary, and adverse conditions that matter to the stated basis; explain omissions. If no condition or technique can yet be derived, state that gap instead of inventing one. |
| Case derivation and dependencies | Required | Map each covered material condition to one or more planned cases or case classes with an intent and discriminating expected outcome. A material condition with no feasible case is an explicit coverage gap, not a fabricated case. Identify an actual controlled case reference when one exists; otherwise use a local design label, which does not mean a case document exists. State data, environment, instrumentation, ordering, and setup dependencies only where they affect feasibility or interpretation. |
| Coverage and design limits | Required | Show how objectives, source obligations, conditions, and planned cases relate; state the coverage rule, gaps, overlap that matters, untested assumptions, and disposition or decision route for material omissions. Separate designed coverage from executed coverage. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Test item and basis | One bounded item or coherent set, with one or more real test-basis sources. | Identify the target configuration the design assumes, plus the source edition and locator where needed. A basis may be a requirement, design decision, risk, user need, or other inspectable project fact; a requirement reference is not mandatory when the test is legitimately based on something else. |
| Test objective | One or more outcomes the design is intended to examine. | Link each to an inspected basis or explained risk and to its planned coverage. An objective is not evidence that a test passed. |
| Test condition | Zero when no distinguishable condition can yet be derived and that gap is explicit; otherwise one or more distinct observable situations or behavior facets. | Give each a stable local or project label, source, priority or risk basis when used, expected behavior or oracle, and applicable input, mode, partition, boundary, or fault conditions. Do not collapse materially different expected outcomes into an ambiguous row. |
| Technique or model | Zero when no technique has been selected and that fact is stated; otherwise one or more selected derivation approaches for the scope. | State where a partition, boundary analysis, state or decision model, sampling rule, or other chosen technique applies and why; no named technique is universally required. Define coverage units before using a numeric target. |
| Planned case or case class | Zero when every material condition is an explicit gap; otherwise one or more distinguishable design outputs for the covered conditions. | State intent, relevant condition, discriminating expected outcome, and needed setup or data constraints. A material condition with no feasible case remains a coverage gap. A local design label is not a claim that a controlled case document exists. Include action detail only where it affects derivation or feasibility. |
| Dependency and sequencing rule | Zero or more actual constraints on setup, environment, data, instrumentation, prior state, or order. | Include only when the dependency changes feasibility, result interpretation, or safe execution. Refer to an existing definition by edition where useful; otherwise state the needed capability here. |
| Coverage assessment | One reconciliation of the stated scope. | Map basis and objectives through conditions to planned cases; identify gaps, exclusions, and the decision or action needed for each material gap. Count planned cases separately from actual runs and do not infer adequacy from a bare case count. Designed coverage is not executed coverage. |

Use a trace table when many basis items, conditions, and cases must be reconciled; meaningful columns include basis, objective, condition, expected behavior, planned case, and gap. Use prose for technique rationale and limits. A state, decision, or input-partition diagram MAY clarify a complex model, but its labels and coverage meaning must remain explicit in the document. Do not copy full executable cases or blank case rows into this specification's finished document.

## Quality criteria

- Each material objective has a traceable test condition and a feasible planned case, or an explicit uncovered gap with a resolution route.
- Conditions and expected outcomes are discriminating enough to derive cases and later judge results; coverage units and any target are defined against the actual basis.
- Data, environment, interface, and ordering assumptions agree with the intended tests, and a change in the item or basis has an identifiable impact on the design.
- Proposed cases and designed coverage are labeled with their design state; actual execution coverage claims require observations for the identified item configuration and cases.
- Omissions, limitations, and the person or authority responsible for a material coverage decision are clear when actually established.
