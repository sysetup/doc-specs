# Test procedure specification

## Identity and selection

- **Specification ID:** `TEST-PROCEDURE@core`.
- **Purpose:** Define a repeatable, bounded test execution sequence with prerequisites, actions, expected checkpoints, evidence capture, failure branches, and restoration.
- **Intended readers:** Test operators and automation implementers, environment owners, test leads, and reviewers of execution readiness and reproducibility.
- **Decision or action supported:** Prepare an authorized run, follow the correct sequence, stop or recover safely when conditions fail, and capture evidence sufficient to interpret the result.
- **Use when:** A test needs an explicit ordered sequence, setup, safety controls, shared-asset handling, or failure and recovery branches.
- **Scope boundaries:** Specify the execution path for the stated objective, item, and configuration, including the checkpoints and recording rules needed to interpret a run.

## Authoring inputs and unresolved facts

Obtain the test objective and its established project basis, supplied case definitions where relevant, item and configuration, starting and intended end state, target environment, data, tools or scripts and their editions, required roles and permissions, concrete safety or isolation limits, expected checkpoints, observation and evidence needs, stop conditions, and restoration constraints. Identify the project records used by edition and locator. State the objective, target, prerequisites, and expected outcomes at the detail needed to execute and interpret the sequence.

If a target, authority, prerequisite, script edition, expected checkpoint, failure path, or restoration limit is unknown, identify the affected step, risk or result impact, resolving action, and actual owner if assigned. Mark the procedure unready for execution where the gap prevents safe or interpretable work. A procedure may describe intended authority checks; it cannot grant execution authority. Do not include credentials or private access material, imply that setup was performed, or invent observations and outcomes. Explain why a step has no wait limit, evidence capture, or rollback only when that absence could affect safe execution or interpretation.

## Finished-document contract

- **Title:** Identify the test item or effort and name the document as its test procedure; distinguish the procedure edition when later runs must cite it.
- **Frontmatter:** None. Begin with the GFM title. Target, revision, and execution limits belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Define scope and prerequisites before the ordered sequence; put recording and restoration rules after the actions they govern, with critical stop rules visible at the point of use. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Scope, test basis, and applicability | Required | Identify the tested item, applicable build or selection rule, objective, established project expected-behavior basis, supplied case identities and locators where relevant, supported environment or configuration, and material exclusions. State the edition of scripts or procedure-controlled assets that affects repeatability. |
| Preconditions, authority, and setup | Required | Specify the required starting state, environment and data readiness, access or execution permission checks when applicable, tools and measurement capability, safety or isolation limits, and setup steps. State how an operator recognizes a failed prerequisite and what action follows. |
| Ordered execution and checkpoints | Required | Give one or more ordered, stable locally identified steps. For each material action, state target and inputs, expected observation or state, planned evidence capture, and next action or branch. Specify wait limits, retries, or timing only when they affect correctness, safety, or result interpretation. |
| Abnormal handling and restoration | Required | Define stop, hold, escalate, retry, or rollback paths for meaningful failed checks or unexpected states; state when continuing is prohibited and who decides a consequential exception if such authority exists. Define the intended end state, cleanup or reset, and how restoration will be checked when the test changes state. |
| Run recording rule | Required | Define what each actual run must capture: the item, environment, and data actually used; the procedure edition; the actor or tool; timestamps where needed; observations with units; evidence locators; deviations; anomalies; and attempt linkage. Identify the recording destination or form and the comparison needed to interpret the run. Define how an actual attempt's state and evidence determine `pass`, `fail`, `inconclusive`, or `not-run`; leave the outcome unassigned in the planned procedure. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Procedure objective and basis | One bounded purpose and one or more inspectable expected-behavior sources. | State the objective and pass/fail criteria with their established project basis. Identify supplied cases and their editions and locators where they contribute to the sequence or criteria. |
| Test target and configuration | One defined test item or coherent set, with applicable configuration and environment rule. | Give edition, range, or selection method at the precision needed for a reproducible run. This is the intended target. An environment reference alone does not establish actual readiness, authorization, or the configuration a run used. |
| Prerequisite and setup check | One or more checks sufficient to establish safe, interpretable starting conditions. | Include personnel competence, permission, calibration, isolation, and data checks only where they matter. State the observable check and failed-check branch, not just the word “ready.” |
| Controlled asset | Zero or more scripts, harnesses, simulators, datasets, or tools used by the method. | Identify a real edition or controlled selection rule and the configuration parameters needed for repeatability. Never include secret values. |
| Step | One or more ordered actions, each with a stable local label. | State actor or tool, target, action, inputs, expected checkpoint, and planned observation or evidence. A step label need only be unique within the procedure. Make branches explicit and avoid an implicit continue after a failed gate. |
| Failure and retry rule | One rule for each material abnormal condition or branch class. | Say whether to stop, hold, investigate, retry within a bounded condition, or restore; identify when retesting requires a fresh attempt identity. A retry MUST NOT overwrite a failed attempt or repeat a state-changing action blindly. |
| End state and restoration | One intended terminal state, with conditional cleanup or rollback actions. | State checks for a changed environment or data set. If restoration is unnecessary, explain why no consequential state remains. |
| Evidence capture | One coherent rule set for what actual execution must record. | Specify observations, units, timestamps, raw evidence locators, deviations, and result comparison needed to interpret the run. Label expected checkpoints as planned values; bind recorded observations and outcomes to the actual attempt. |

Use a numbered sequence for the normal path and explicit decision branches for alternate paths. A step table MAY help when each step needs the same action, expected checkpoint, capture, and failure columns. A flow diagram MAY clarify branching, but its transitions and stop rules must be readable in text. Commands or scripts included as instructions must name intended target and applicable parameters; their presence is not permission to execute them. Do not add blank step rows or an empty execution log.

## Quality criteria

- An operator can establish the correct target and starting state and follow the sequence without guessing a missing case, environment, or script reference.
- Expected checkpoints and capture rules support later result interpretation; waits, retries, and state changes have bounded, safe behavior where relevant.
- Failed prerequisites and abnormal observations have explicit routes, and restoration requirements agree with the test's actual potential effects.
- The objective, expected-behavior basis, and result comparison agree with the sequence and evidence capture rules.
