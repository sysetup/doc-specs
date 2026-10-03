# Test environment specification

## Identity and selection

- **Specification ID:** `TEST-ENVIRONMENT-SPECIFICATION@core`.
- **Purpose:** Define the conditions and readiness criteria of an environment used for a bounded test effort, including test-specific interfaces, instrumentation, data, fidelity, and reset needs.
- **Intended readers:** Test designers and operators, environment owners, integrators, data and security stewards, and people who decide whether testing may begin or continue.
- **Decision or action supported:** Build or select a suitable test environment, assess it against explicit criteria, and determine which tests and conclusions its limitations permit.
- **Use when:** Test execution depends on a controlled configuration, simulated or real interfaces, measurement capability, protected data, or a readiness decision that needs an explicit definition.
- **Scope boundaries:** Define target configurations, capabilities, and readiness criteria for the stated tests. Include a bounded readiness assessment only when actually performed, limited to the identified instance, observation time, criteria checked, and resulting use conditions.

## Authoring inputs and unresolved facts

Obtain the test item, test level and objectives, applicable item build or configuration, intended tests, relevant runtime and interface constraints, required environment components and versions, real or simulated dependencies, instrumentation and measurement needs, data classes, accounts and access rules, safety or isolation limits, and expected readiness decision maker. Inspect the required fidelity relative to the operational setting and the source of any readiness observations. Determine how changes, drift, and restoration affect test validity.

If a required configuration, interface behavior, instrument capability, data rule, readiness criterion, or decision authority is unknown, state the gap, effect on testing, resolving action, and actual owner if assigned. Mark a proposed target as such. Do not present an intended setup as installed, checked, or authorized. A readiness assessment appears only when real observations exist, and authorization appears only when the applicable decision actually occurred. Bind assessment conclusions to the observed instance, time, and checks. State why a component, calibration, simulator, or separate authorization is inapplicable when that absence could affect interpretation. Never include credentials, keys, or secret values.

## Finished-document contract

- **Title:** Name the bounded test item or effort and its test environment specification; identify the target edition or configuration when needed.
- **Frontmatter:** None. Begin with the GFM title. Configuration, readiness, and authority belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Establish test scope and target environments before readiness criteria; place actual assessment, if any, after its criteria and fidelity and change limits before conclusions about use. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Test scope and environment identity | Required | Identify the tests or test levels supported, the item/configuration under test, one or more target environments, their distinct roles or variants, and the target edition. State material exclusions and who owns the target definition and test-use decision when established. |
| Required configuration and test capabilities | Required | For each target, specify applicable compute, software, services, network, interfaces, tools, instrumentation, timing sources, test data and account rules, isolation, and safety controls with values or compatibility limits where they affect results. Distinguish real, simulated, and stubbed behavior and its fidelity limits. State setup or reset state required for repeatability. |
| Readiness criteria and permitted use | Required | Define observable checks, expected results, evidence basis, allowed tests, conditions, and authority for deciding test use. Include calibration, clock accuracy, data preparation, interface availability, and restoration checks when they affect measurement or safety. A proposed check is not a passed check. |
| Actual readiness assessment | Conditional: include only if the document reports one or more real assessments | Bind each assessment to the actual instance, target edition, observation time, checks performed, results and evidence, deviations, and actual decision or limitation. Identify the decision maker and authorization reference only when authorization was required and granted. Limit conclusions to the environment characteristics actually observed at that time. |
| Fidelity, change, and restoration | Required | State known differences from the relevant operational setting, effects on permissible conclusions, how target or instance drift is detected, when readiness must be rechecked, and how the environment returns to a defined state after tests. Include unresolved dependencies and their resolution route. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Target environment | One or more distinguishable test configurations within one bounded effort. | Give each a stable local or project identity, supported tests, target edition, and applicability. A shared infrastructure may have multiple test configurations; do not transfer readiness from one to another without an explicit rule. |
| Required characteristic | One or more assessable rules for each relevant configuration facet. | Specify capability or version, value or range, units and tolerance when needed, and compatibility constraints that affect test validity. Do not require exact versions, tools, or zones with no effect on this test scope. |
| Interface and fidelity rule | One account per material real, simulated, stubbed, or disconnected dependency. | State behavior needed by the test, counterpart or simulator, limitations, and which conclusions may not be drawn. A simulator is not silently equivalent to the operational interface. |
| Instrumentation and timing rule | Zero or more tools, sensors, logs, or time sources needed to observe results. | State edition, resolution, calibration, synchronization, or uncertainty when it affects pass criteria or event ordering. If no special instrumentation is needed, describe the ordinary observation method. |
| Data, access, and safety rule | One coherent account per target; detail applicable data classes and privileged paths. | State allowed data classes, their preparation and cleanup conditions, access roles, isolation, safety limits, and the secret retrieval mechanism where relevant. Identify a materialized dataset only when its actual edition and availability are established. Do not expose secrets or assume production authorization or run authorization from test readiness. |
| Readiness criterion | One or more explicit checks for each target. | Identify the expected condition, method or evidence, configuration to which it applies, and any use restriction after a conditional result. |
| Readiness state, observation, and decision | State is optional for a target; include observations only when an assessment occurred. | `planned` describes the target before setup; `prepared` means setup reported; `checked` means checks performed without implying a pass; `authorized` requires an actual test-use decision for that environment and is not execution authorization for a run, a case outcome, or production authorization; `withdrawn` means a prior decision was revoked. Bind observed checks to the instance, target edition, time, criterion, and evidence. State outcomes and conditions separately; a state word alone is not evidence. |
| Change and restoration rule | One approach for drift and reset across the bounded tests. | State triggers for recheck, ownership of consequential changes, and the reset or cleanup state needed before another attempt. Note when destructive or stateful tests require an isolated or restored instance. |

Use a configuration table when several components or target variants must be compared; columns should expose target, required condition, reason, and readiness check. A topology or measurement diagram MAY clarify interface and instrumentation paths when prose is insufficient; identify its edition and limits. Use a criterion-to-observation table only for an actual assessment. No diagram, inventory, or provisioning code silently replaces the target rules.

## Quality criteria

- Each target environment states the configuration, capabilities, and readiness rules needed to select or prepare it for its specific tests.
- Measurement, fidelity, data, isolation, and reset rules are tied to the conclusions or safe execution they affect.
- Readiness criteria are observable, and any actual assessment names its real instance and evidence. Prepared or checked is not silently promoted to authorized.
- Drift, deviations, restoration, and changed test conditions have an explicit effect on readiness and interpretation.
- Intended configuration, actual observations, test-use authorization, production authorization, and test results remain distinct.
- Assessment conclusions remain bound to the observed instance, configuration, instrumentation, data conditions, time, and checks; use decisions state their actual scope and limits.
