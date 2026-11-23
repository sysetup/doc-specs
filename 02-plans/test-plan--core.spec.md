---
title: "Test plan specification"
description: >-
  Defines the authoring contract for test plans organizing scope, objectives, inspectable test basis, test levels, techniques, coverage rules, responsibilities, environments, data dependencies, schedules, measurable entry, exit, suspension, and resumption gates, anomaly triage, and evidence reporting for a bounded test effort prior to execution. Keeps planning at campaign or level coordination depth while referencing detailed test designs, cases, and execution procedures as explicit planning dependencies.
topics:
  - "planning"
  - "testing"
  - "verification-and-validation"
  - "test-plan"
  - "test-strategy"
  - "coverage-rules"
  - "entry-exit-criteria"
  - "test-resources"
use_when:
  - "A test campaign, test level, or release requires an agreed scope, strategy, schedule, resources, and gate criteria before testing starts."
  - "A test lead is aligning stakeholders on test basis coverage, environment dependencies, and evidence expectations."
  - "A reviewer is verifying that entry, exit, suspension, and resumption criteria are observable and assigned to real decision authorities."
not_for:
  - "Deriving detailed test conditions, cases, or step-by-step execution scripts, which belong in test design, case, and procedure specifications."
  - "Planning broader multi-method verification or intended-use validation programs beyond testing, which belong in V&V plans."
  - "Reporting mid-campaign progress or ended-campaign outcomes, which belong in test status or test completion reports."
---

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

- **Title:** Identify the test effort and the document as its test plan; "Test Plan" alone is insufficient when several efforts may exist.
- **Frontmatter:** Required. Begin with a YAML 1.2 Semantic-Discovery frontmatter block delimited by `---` lines containing `title`, `description` (60 to 140 neutral retrieval words), `topics` (3 to 12 concrete lowercase kebab-case terms), `use_when` (2 to 6 neutral task conditions), and conditional `not_for` (1 to 5 grounded exclusions, omitted when empty), followed by the GFM H1 title. Exclude internal IDs, version strings, hashes, filesystem paths, build metadata, and unresolved template delimiters from frontmatter values. Test scope and decision rules are substantive body content. Governing source: Collection Semantic-Discovery Frontmatter contract.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. Omit it for internal documents unless a specific project policy requires explicit negative attestation. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Establish scope and basis before strategy; define resources and controls before evidence and reporting. Heading wording may vary.
- **Presentation:** Scale sections, tables, and schedules to the bounded effort without adding empty chapters for inapplicable concerns. Required roles may share paragraphs, lists, or compact tables while keeping planned scope, responsibilities, criteria, dependencies, and open gaps clearly separated from completed results.

| Projection | Title and metadata ownership | Syntax and source authority |
| --- | --- | --- |
| Test plan (standalone) | Begin with the mandatory 5-key Semantic-Discovery YAML frontmatter followed by one scope-specific H1. Plan scope, baseline assumptions, ownership, and readiness criteria remain body content, inheriting corpus-level changelog/VCS versioning, declared default maintainer, and external specification provenance when governed in a unified operational corpus. | Use GFM prose, structured tables, or dependency diagrams referencing controlling requirements, baselines, and schedules by edition and locator. Planned commitments remain distinct from execution evidence; baseline or scope changes require plan reassessment. |

| Section role | Status and inclusion condition | Content obligation |
| --- | --- | --- |
| Objective, scope, and test basis | Required | Identify the test item and applicable configuration, objectives, included features or levels and material exclusions if any, constraints and assumptions, and the inspected basis for each objective. Explain risk priorities and the rationale for material exclusions. |
| Strategy and coverage | Required | State the selected test levels, types, techniques, and depth; explain how coverage of the basis and important risks will be determined and traced. Identify planned coverage units and the activity that will define detailed conditions and cases when pending. State regression approach and independence needs when they affect the effort. |
| Resources and environment | Required | Assign planning and execution responsibilities by real role; identify competence, tools, facilities, test data, environment configuration, readiness dependencies, and acquisition or setup needs. Reference existing detailed environment or case definitions when useful. |
| Schedule and decision controls | Required | State activities, sequencing, dependencies, milestones or time windows, and reporting cadence. Define measurable entry, exit, suspension, and resumption criteria, who decides each gate, and how plan or basis changes are assessed and communicated. |
| Evidence, anomalies, and reporting | Required | Define how execution will record the actual item build, environment, data, case or procedure edition when one exists, actual result, anomalies, retests, and supporting evidence. State retention, access, review, defect triage, escalation, and progress or completion reporting rules. Do not report planned outcomes as actual results. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
| --- | --- | --- |
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
