# Test plan specification

## Identity and selection

- **Specification ID:** `TEST-PLAN@core`.
- **Purpose:** Define the scope, objectives, strategy, resources, control points, and evidence for a bounded test effort before its execution.
- **Intended readers:** Test lead and team, product or system owners, reviewers, and people who decide readiness or completion.
- **Decision or action supported:** Stakeholders can agree what will be tested, why and how, what resources are needed, and what evidence will support readiness and completion decisions.
- **Use when:** A test campaign, level, release, or other bounded effort needs a coordinated plan before testing.
- **Scope boundaries:** Define effort-level scope, strategy, dependencies, and decision controls; use detailed conditions, cases, and steps only to identify planned coverage, resources, or execution dependencies.

## Authoring inputs and unresolved facts

Obtain the test item and applicable configuration or release, test objectives and basis, relevant project requirements or risks, included and excluded scope, chosen test levels and methods, expected coverage, roles, resources, environments, data, dependencies, schedule constraints, decision authorities, and internal project rules for evidence and anomalies. A test basis may be a supplied project requirement, design, risk, user need, or other inspectable project record; identify its applicable edition or locator and the concrete statement that supports the objective.

Mark missing evidence as unknown and undecided planning choices as not established. For each material gap, state the impact, resolving action, and actual owner if assigned. Explain genuine inapplicability rather than filling a section with invented activity. Unresolved item identity, basis, scope, entry or exit criteria, or essential environment readiness prevents a claim that the plan is ready to govern execution. Do not invent results, approvals, case IDs, or dates.

## Finished-document contract

- **Title:** Identify the test effort and the document as its test plan; “Test Plan” alone is insufficient when several efforts may exist.
- **Frontmatter:** None. Begin with the GFM title. Test scope and decision rules are substantive body content.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Establish scope and basis before strategy; define resources and controls before evidence and reporting. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Objective, scope, and test basis | Required | Identify the test item and applicable configuration, objectives, included features or levels and material exclusions if any, constraints and assumptions, and the inspected basis for each objective. Explain risk priorities and the rationale for material exclusions. |
| Strategy and coverage | Required | State the selected test levels, types, techniques, and depth; explain how coverage of the basis and important risks will be determined and traced. Identify planned coverage units and the activity that will define detailed conditions and cases when pending. State regression approach and independence needs when they affect the effort. |
| Resources and environment | Required | Assign planning and execution responsibilities by real role; identify competence, tools, facilities, test data, environment configuration, readiness dependencies, and acquisition or setup needs. Reference existing detailed environment or case definitions when useful. |
| Schedule and decision controls | Required | State activities, sequencing, dependencies, milestones or time windows, and reporting cadence. Define measurable entry, exit, suspension, and resumption criteria, who decides each gate, and how plan or basis changes are assessed and communicated. |
| Evidence, anomalies, and reporting | Required | Define how execution will record the actual item build, environment, data, case or procedure edition when one exists, actual result, anomalies, retests, and supporting evidence. State retention, access, review, defect triage, escalation, and progress or completion reporting rules. Do not report planned outcomes as actual results. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Test item and configuration | One bounded item or set of items, with the version, baseline, or selection rule that will bind executions. | An unresolved build may be a planning dependency, but the plan MUST say how it will be fixed before testing. |
| Test objective | One or more outcomes the testing is intended to examine. | Each objective MUST connect to at least one inspected basis or stated risk and to a coverage approach; it is not a claim that the outcome has been met. |
| Test basis reference | One or more inspectable project requirements, designs, risks, user needs, or other supplied project records for the objectives. | Use a title or ID, applicable edition, and locator when needed; state the concrete statement or risk addressed by the objective. |
| Scope exclusion | Zero or more material exclusions. | Give reason, risk or consequence, and decision owner when the exclusion affects a commitment or gate. |
| Coverage rule | One or more rules that show how the chosen tests address the basis and risks. | Specify the unit and threshold or review rule where measurable; do not use an unexplained percentage as proof of adequacy. |
| Resource or dependency | One or more roles, environments, tools, data sources, or external dependencies required by the approach. | Name the responsible role and readiness condition for a dependency that can block execution. |
| Gate criterion | Entry, exit, suspension, and resumption conditions, each covered by at least one explicit rule. | State observable evidence and decision authority; unresolved thresholds cannot silently count as met. |
| Case and environment references | Zero or more existing detailed definitions. | If they do not exist yet, state the design or setup activity and its dependency instead of inventing references. |
| Evidence and anomaly rule | One coherent recording and triage approach. | Distinguish expected results from observed results and keep failures and retests traceable. Name the item-build, environment, and data identities to capture from each actual execution, and the case or procedure edition when one exists. |

Use concise prose for strategy and rationale. Tables are suitable for objective-to-basis coverage, responsibilities and dependencies, schedule, and gate criteria when those relationships are complex. A timeline or flow MAY clarify sequencing or suspension and resumption. Identify pending case-definition or step-definition work as a planning activity with its owner and dependency.

## Quality criteria

- Scope, objectives, basis, approach, and coverage agree; excluded work is visible and its consequence is not hidden.
- Resource and environment commitments are feasible against schedule and entry criteria, or are identified as unresolved dependencies.
- Gate criteria are observable and assign a real decision authority, with the evidence required for each readiness or completion decision.
- The evidence approach binds each actual execution to the item, environment, data, and method edition while preserving expected and observed results as distinct fields.
