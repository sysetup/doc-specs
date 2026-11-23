---
title: "Service or system availability plan specification"
description: >-
  Defines the authoring contract for availability plans specifying how a service or system measures, sustains, safely degrades, and improves availability against established service objectives. Covers availability scope and objectives, measurement methods and exclusions, dependency and single-point-of-failure analysis, resilience provisions and degraded-operation handling, monitoring and incident interfaces, and periodic review triggers so service owners, reliability engineers, and operators choose defensible reliability investments for real operating contexts.
topics:
  - "planning"
  - "operations"
  - "incident-and-continuity"
  - "availability-planning"
  - "service-reliability"
  - "degraded-operation"
  - "failure-analysis"
  - "resilience"
use_when:
  - "A service or system needs explicit availability objectives, measurement rules, dependency failure analysis, and resilience provisions."
  - "An architect or reliability engineer is planning degraded-operation behaviors and monitoring thresholds before sustained operation."
  - "A reviewer is verifying that availability targets align with concrete measurement methods and realistic failure scenarios."
not_for:
  - "Broad day-to-day staffing, support, and routine operations models, which belong in an operations and support plan."
  - "Enterprise-wide disruption workarounds spanning sites and business units, which belong in a business continuity plan."
  - "Reporting actual observed availability metrics for a past period, which belongs in a service-period status report."
---

# Service or system availability plan specification

## Identity and selection

- **Specification ID:** `AVAILABILITY-PLAN@core`.
- **Purpose:** Plan how a defined service's availability will be measured, sustained, degraded safely, and improved against established objectives.
- **Intended readers:** Service and product owners, availability and reliability engineers, operators, support and incident roles, suppliers, and objective owners.
- **Decision or action supported:** Choose defensible availability provisions, measurement, response thresholds, and review actions for the service's actual operating context.
- **Use when:** A service or system needs explicit availability objectives, dependency and failure analysis, resilience provisions, or degraded-operation planning.
- **Scope boundaries:** Cover availability objectives, measurement rules, failure analysis, resilience provisions, degraded behavior, and assessment for the defined service or system at planning depth.

## Authoring inputs and unresolved facts

Obtain the service boundary, users and critical functions; operating and maintenance windows; objectives and exclusions established by supplied service agreements or internal project decisions; measurement points, telemetry and data quality; architecture and dependencies; credible failure and common-cause conditions; capacity constraints; planned resilience, failover, degraded modes and recovery interfaces; incident thresholds and roles; and existing performance or test evidence if it informs design. Identify the agreement or decision establishing any SLA or numerical objective.

If an objective, measurement definition, dependency behavior, or decision authority is unknown or not established, identify the gap, consequence, resolving action, and actual owner if assigned. A plan may set out a proposed method while the objective is being decided, but must not present that method as an agreed SLA. If a failure mode is out of scope or a resilience technique is not selected, state the reason and residual limitation. Identify a historic observation and its locator when it informs design; distinguish that observation from future tests, failovers, and expected evidence.

## Finished-document contract

- **Title:** Identify the service or system and name its availability plan.
- **Frontmatter:** Required. Begin with a YAML 1.2 Semantic-Discovery frontmatter block delimited by `---` lines containing `title`, `description` (60 to 140 neutral retrieval words), `topics` (3 to 12 concrete lowercase kebab-case terms), `use_when` (2 to 6 neutral task conditions), and conditional `not_for` (1 to 5 grounded exclusions, omitted when empty), followed by the GFM H1 title. Exclude internal IDs, version strings, hashes, filesystem paths, build metadata, and unresolved template delimiters from frontmatter values. Objectives and scope belong in the body. Governing source: Collection Semantic-Discovery Frontmatter contract.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. Omit it for internal documents unless a specific project policy requires explicit negative attestation. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Define the service and measurement basis before failure analysis and provisions; place assessment and improvement after the planned operating method. Exact heading wording may vary.
- **Presentation:** Scale sections, tables, and schedules to the bounded effort without adding empty chapters for inapplicable concerns. Required roles may share paragraphs, lists, or compact tables while keeping planned scope, responsibilities, criteria, dependencies, and open gaps clearly separated from completed results.

| Projection | Title and metadata ownership | Syntax and source authority |
| --- | --- | --- |
| Service or system availability plan (standalone) | Begin with the mandatory 5-key Semantic-Discovery YAML frontmatter followed by one scope-specific H1. Plan scope, baseline assumptions, ownership, and readiness criteria remain body content, inheriting corpus-level changelog/VCS versioning, declared default maintainer, and external specification provenance when governed in a unified operational corpus. | Use GFM prose, structured tables, or dependency diagrams referencing controlling requirements, baselines, and schedules by edition and locator. Planned commitments remain distinct from execution evidence; baseline or scope changes require plan reassessment. |

| Section role | Status and inclusion condition | Content obligation |
| --- | --- | --- |
| Availability scope and objectives | Required | Define the service boundary, critical functions and user perspectives, operating periods, affected dependencies, source and status of objectives, and permitted maintenance or exclusion rules. Show unresolved objective decisions without invented thresholds. |
| Measurement method | Required | Define what counts as available, unavailable, and degraded; measurement point, time basis, calculation, sampling, data source, missing-data treatment, exclusions, reporting period, and responsibility. Keep a partial-service condition visible rather than silently counting it as full availability. |
| Failure and dependency analysis | Required | Describe credible failure modes, single points and shared or common-cause dependencies, capacity or maintenance effects, and the expected user impact. Identify assumptions and the basis for prioritizing provisions. |
| Availability provisions and degradation handling | Required | Plan the selected health checks, redundancy, failover, capacity reserve, maintenance coordination, or other measures; identify trigger, owner, expected service state, and limits for each. State safe degraded behavior, escalation, and restoration interface. A technique appears only if selected for this service. |
| Monitoring and incident interface | Required | Plan alert thresholds and routing, evidence integrity, incident classification or escalation, communication to affected users, and how an availability breach or near miss is investigated. Identify existing procedure locators when useful; describe response triggers, responsibilities, and interfaces at planning depth. |
| Assessment and improvement | Required | Define how objectives will be compared with later measured results, how planned resilience or recovery checks will be evaluated, who reviews uncertainty, and how changes to design or operating provisions are decided. Bind historic design inputs to their observations and record locators; specify the evidence later measurements and checks must retain. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
| --- | --- | --- |
| Availability scope | One bounded service or system; several critical functions may need distinct measures. | State user perspective, operating windows, environment, and dependency boundary. A component's uptime is not automatically user-visible service availability. |
| Availability objective | One entry per established or proposed measure relevant to the scope. | State source and decision status, target and interval only when established, applicable users or functions, exclusions, and review authority. Do not invent an SLA. |
| Measurement rule | One complete rule for each reported availability measure. | Define eligible time or requests, the criterion for counting the service available, degraded state, numerator and denominator or equivalent calculation, timezone when time-based, sampling, missing-data handling, and data source. |
| Failure scenario | Each material failure or common-cause condition considered. | Connect dependency or cause, affected function, expected degradation, detection, selected provision or explicit unresolved gap, and escalation. Avoid implying every failure is recoverable by failover. Do not treat an unresolved gap as an accepted limitation. |
| Availability provision | Each selected measure needed to meet or assess the objective. | Define trigger or use condition, responsible role, expected behavior, limits, planned check and evidence. Redundancy and failover are conditional choices, not universal requirements. |
| Review trigger | One or more conditions that cause reassessment. | Include a later measurement that does not meet the objective, a measurement that cannot be completed, and material service, dependency, workload, or maintenance changes where applicable; name the decision route. |

Use prose for rationale and limitations, a measurement table for several objectives, and a scenario-to-provision table or diagram when dependencies are complex. A planned check may name its observable criterion and expected evidence; do not insert empty result rows or claim that a failover occurred.

## Quality criteria

- Two readers applying the stated measurement rule to the same reliable data would classify downtime, degradation, exclusions, and missing data consistently.
- Objectives are traceable to an established service agreement or internal project decision, or clearly marked proposed, and the design responds to the users and functions those objectives cover.
- Failure analysis includes material shared dependencies and maintenance or capacity effects rather than assuming independent redundant components.
- Degraded operation, alerting, escalation, and restoration have a bounded route; planned resilience checks do not imply proven capability.
- Planned measurements and resilience checks state their criteria and expected evidence; historic design inputs retain their observation locators.
- Objectives, measurement rules, failure scenarios, provisions, and review triggers cover the same service boundary and operating periods.
