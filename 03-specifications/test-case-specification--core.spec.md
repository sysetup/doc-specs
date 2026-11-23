---
title: "Test case specification"
description: >-
  Defines the authoring contract for test case specifications defining one or more independently assessable tests before execution. Covers case set scope and controlling test basis, unique case identities, traced objectives, preconditions, concrete inputs and stimuli, local action details, expected observations and pass/fail result criteria, postconditions and cleanup, priorities, dependencies, and use limits so testers and automated suites evaluate outcomes unambiguously against defined oracles.
topics:
  - "test-case-specification"
  - "test-oracles"
  - "test-inputs"
  - "expected-observations"
  - "pass-fail-criteria"
  - "software-testing"
use_when:
  - "One test or a coherent test case set needs a stable pre-execution specification of inputs, preconditions, actions, and pass/fail criteria."
  - "A test designer is defining unambiguous expected observations and cleanup postconditions traced to requirements or risks."
  - "A reviewer is checking whether test cases isolate individual assessable oracles without bloating into long shared execution scripts."
not_for:
  - "Campaign-level test strategy, schedules, and entry/exit gates, which belong in a test plan."
  - "Deriving high-level test conditions and coverage techniques before concrete cases, which belongs in a test design specification."
  - "Ordered multi-case operational run scripts or recorded actual run outcomes, which belong in test procedures or test execution records."
---

# Test case specification

## Identity and selection

- **Specification ID:** `TEST-CASE-SPECIFICATION@core`.
- **Specification edition:** `1.0`.
- **Purpose:** Define one or more independently assessable tests, with their basis, conditions, actions, expected observations, and result criteria before execution.
- **Intended readers:** Test designers and operators, implementers, test leads, and reviewers who must understand what each case will establish.
- **Decision or action supported:** Prepare and select executable cases, identify missing prerequisites or uncertain oracles, and compare later observations with defined expectations.
- **Use when:** An individual test or coherent case set needs a stable definition of what to exercise and how to judge it, without prescribing a lengthy shared execution sequence.
- **Scope boundaries:** Define each case's local action, oracle, and result criteria for the stated item and configuration. Include shared setup or sequencing detail only where needed to make that case executable and assessable.

## Authoring inputs and unresolved facts

Obtain the item and applicable configuration, each case's objective and inspected project basis, relevant design conditions and risks, starting state, inputs or data selection rules, action or stimulus, established expected behavior and its project basis, observation method, and constraints on timing, units, tolerances, safety, or cleanup. Identify the basis by real title or ID, edition, and locator where needed. A requirement is one possible basis; an inspected need, interface contract, design decision, defect, or risk may also justify a case. Ask who owns an ambiguous expected result rather than treating an implementation's current behavior as the oracle.

For an unknown configuration, input, expected result, or criterion, identify the affected case, why the gap matters, the resolving action, and the actual owner if assigned. A case with an unresolved material oracle or unsafe prerequisite MUST be labeled unready for execution or result judgment. If a condition or cleanup step is genuinely inapplicable, explain that briefly rather than inventing one. Do not invent case references, approved priorities, execution, or pass/fail outcomes.

## Finished-document contract

- **Title:** Identify the test item or bounded case set and name the document as its test case specification; distinguish the applicable item or case edition when it changes interpretation.
- **Frontmatter:** Required. Begin with a YAML 1.2 Semantic-Discovery frontmatter block delimited by `---` lines containing `title`, `description` (60 to 140 neutral retrieval words), `topics` (3 to 12 concrete terms), `use_when` (2 to 6 neutral task conditions), and conditional `not_for` (1 to 5 grounded exclusions, omitted when empty), followed by the GFM H1 title. Exclude internal IDs, version strings, hashes, filesystem paths, build metadata, and unresolved template delimiters from frontmatter values (Rule 13). Case identity and source editions belong in the body. Governing source: Collection Semantic-Discovery Frontmatter contract (standard 3.0.0).
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. Omit it for internal documents unless a specific project policy requires explicit negative attestation. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Establish the scope and oracle basis before the cases; put use limits and unresolved case dependencies after the case definitions. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
| --- | --- | --- |
| Case set scope and basis | Required | Identify the item and applicable configuration, the case set's boundary, project-basis editions, the established basis and decision owner for expected behavior, and material assumptions or exclusions. State how cases are identified or revised when later runs must resolve their edition. |
| Case definitions | Required | Define one or more distinct cases. For each, state objective and basis; initial state and prerequisites; input values or reproducible selection rules; action or condition to apply; expected observable outcomes and pass/fail rule; observation method; and any necessary end state or cleanup. Keep each case independently identifiable and assessable. |
| Dependencies and use limits | Required | Identify unresolved or conditional data, environment, access, instrumentation, sequence, safety, or oracle dependencies that affect execution or interpretation. State the resolving action and actual decision owner when established. Do not report a planned test as performed. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
| --- | --- | --- |
| Case identity | One stable project or local identity per case; one or more cases per coherent specification. | An identity must distinguish a case from other cases and allow a run to identify the applicable edition. A globally prescribed ID pattern is unnecessary unless the project has one. Separate cases with different objectives or result criteria. |
| Objective and basis | One assessable purpose and at least one inspectable basis or explained risk per case. | Link the case to a requirement when a requirement actually governs it; do not force a requirement reference for a legitimate non-requirement test. A case purpose alone does not establish coverage adequacy. |
| Preconditions | One defined starting-state rule per case, including relevant configuration, permissions, data state, and prior actions. | State observable readiness checks and the effect of a failed prerequisite. If no special setup applies, identify the ordinary starting state. Treat the stated configuration as required setup; a claim of readiness requires actual check observations. Label an unmet prerequisite as blocking execution or result judgment rather than assigning a case pass or fail. |
| Inputs and stimulus | One or more inputs, states, or triggers sufficient to distinguish the case. | Give exact values or controlled selection rules, bounds and units when meaningful, and real data edition or generator parameters when needed. Describe the action that applies them. |
| Expected observation and criterion | One or more assessable expected outcomes per case. | For each material assertion, state what will be observed, the oracle and its established project basis, comparison rule, and timing, tolerance, or measurement uncertainty when these change the verdict. A vague expected outcome such as “works” is insufficient. |
| Action detail | One concise sequence or triggering action per case; detailed steps only when necessary for unambiguous execution. | A case MAY identify an actual procedure and its edition for shared setup or complex steps. State the case's action, prerequisites, and observation rule explicitly enough to determine what is executed and assessed. |
| Postcondition and cleanup | Conditional: required for stateful, destructive, resource-consuming, or sequenced cases. | State the required end or restored state and how to recognize it. Do not force a cleanup action for a read-only case with no consequential state change. |
| Priority and dependencies | Conditional: include when used to select, sequence, or authorize testing. | Give the real risk or decision basis and identify blocking data, environment, tool, or authority conditions. Do not fabricate a priority ranking to fill a field. |

Use a separate labeled block or a row plus supporting detail for each case. A case table is useful for a compact set when columns preserve identity, basis, preconditions, stimulus, expected observation, and criterion. Use ordered steps only when sequence matters; a decision or state diagram MAY clarify a complex case, with its inputs and outcome rules stated in text. Do not add empty case rows. Keep case blocks focused on the defined conditions, actions, and expected observations.

## Quality criteria

- Each case has an inspectable basis, a discriminating action or condition, and an expected outcome that a later operator can compare with observations.
- Initial state, inputs, observation method, tolerances, and end state are precise enough for the risk and test purpose; unresolved material dependencies visibly limit readiness.
- Case identities and editions can be cited in an execution record, and materially different outcomes are not hidden in one ambiguous case.
- Expected outcomes are labeled as expectations; actual result claims require observations for the identified case edition and configuration.
- Case definitions state the data and environment constraints needed for execution, and their actions, prerequisites, and criteria agree with those constraints.
