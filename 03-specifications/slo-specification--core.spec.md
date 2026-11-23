---
title: "Service level objective and error budget specification"
description: >-
  Defines the authoring contract for service level objective and error budget specifications establishing measurable user-visible reliability contracts for a bounded service or user journey. Covers service scope, vantage points, and agreement state kept distinct from external contractual service level agreements, exact mathematical service level indicator definitions and missing-telemetry rules, target thresholds, compliance windows, derived error budgets, multi-window burn-rate alerting tiers, agreed error-budget exhaustion policies with exception authorities, and conditional bindings to validated machine-readable SLO or alerting manifests.
topics:
  - "specifications"
  - "operations"
  - "quality-assurance"
  - "slo-specification"
  - "service-level-indicator"
  - "error-budget"
  - "burn-rate-alerting"
  - "reliability-targets"
use_when:
  - "A service or critical user journey needs exact mathematical service level indicators, reliability targets, compliance windows, error budgets, and exhaustion policies."
  - "A reliability engineer or service owner is aligning multi-window burn-rate alert thresholds with product-engineering error-budget governance."
  - "A reviewer is checking whether SLI denominators, missing-data handling, and companion machine-readable SLO manifests are unambiguous and distinct from external SLAs."
not_for:
  - "Planning architectural failure analysis, redundancy failover mechanisms, and degraded-operation investments, which belongs in a service or system availability plan."
  - "Cataloging all general watched operational signals, owners, and response pointers across a service, which belongs in an observability register."
  - "Reporting actual observed reliability, telemetry coverage, and incidents over a past operating period, which belongs in a service-period status report."
  - "Planning multi-horizon workload demand forecasts, headroom reserves, and scaling lead times, which belongs in a capacity plan."
---

# Service level objective and error budget specification

## Identity and selection

- **Specification ID:** `SLO-SPECIFICATION@core`.
- **Purpose:** Define unambiguous Service Level Indicators (SLIs), Service Level Objectives (SLOs), compliance windows, error budgets, burn-rate alerting tiers, and error-budget exhaustion policies for a bounded service or user journey.
- **Intended readers:** Site reliability and platform engineers, service and product owners, developers, operators, alerting maintainers, and engineering leadership.
- **Decision or action supported:** Measure user-visible reliability consistently, configure actionable burn-rate alerts, and trigger agreed engineering prioritization, release controls, or escalations when error budgets burn rapidly or exhaust.
- **Use when:** A service, API, data pipeline, or critical user journey requires quantified reliability objectives and shared error-budget governance across product and engineering roles.
- **Scope boundaries:** Specify SLI formulas, SLO thresholds, compliance windows, error budgets, burn-rate alert rules, and budget-exhaustion policies for one bounded service or tightly coupled journey set; exclude external contractual SLA terms, resilience engineering plans, general alert catalogs, remediation command steps, and historical compliance reports.

## Authoring inputs and unresolved facts

Obtain the service boundary, covered user journeys or machine interfaces, measurement vantage points (client, edge, server, or pipeline), exclusions, accountable engineering and product owners, and current agreement state; external contractual SLA obligations when they exist (strictly to verify internal SLO margins without conflating the two); telemetry sources, metric names, event or time-slice populations, exact good-event and valid-event definitions, excluded traffic or error classes, sampling or aggregation rules, and missing-telemetry treatment; target reliability thresholds, rolling or calendar compliance window durations and timezones, derived error budgets, and upstream or downstream dependency reliability limits; multi-window burn-rate alert tiers, routing destinations, and controlling runbook or observability-register locators; error-budget exhaustion and warning actions, exception-granting authority, escalation route, and review cadence; and for any selected machine-readable SLO or alerting manifest (such as OpenSLO, Sloth, or Prometheus rules), its format, version, artifact locator, mapping, validator, and check status.

If a telemetry source, valid-event denominator, missing-data rule, dependency reliability ceiling, product-engineering policy agreement, exception authority, or manifest validation check is unknown or undecided, expose the gap explicitly with its measurement or governance consequence, resolving action, and assigned owner only when known. Keep unagreed thresholds or draft exhaustion policies visibly marked as `proposed`; do not enforce release freezes or publish SLA compliance claims from proposed objectives. Missing or blind telemetry intervals cannot be silently treated as good events.

## Finished-document contract

- **Title:** Name the service or user journey scope and identify the document as its service level objective and error budget specification.
- **Frontmatter:** Required on standalone GFM documents; omitted on selected machine-readable native SLO or alerting-rule manifests whose formats manage metadata natively. Begin standalone GFM documents with a YAML 1.2 Semantic-Discovery frontmatter block delimited by `---` lines containing `title`, `description` (60 to 140 neutral retrieval words), `topics` (3 to 12 concrete lowercase kebab-case terms), `use_when` (2 to 6 neutral task conditions), and conditional `not_for` (1 to 5 grounded exclusions, omitted when empty), excluding internal IDs, version strings, hashes, filesystem paths, build metadata, and unresolved template delimiters from frontmatter values, followed by the H1 title. Service scope, agreement state, SLI formulas, policy rules, and native check status belong in the body. Governing source: Collection Semantic-Discovery Frontmatter contract and this type's projection policy.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. Omit it for internal documents unless a specific project policy requires explicit negative attestation. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Establish service scope, vantage points, and agreement state before SLI definitions; define SLIs before SLO targets, compliance windows, and error budgets; place burn-rate alerting tiers and error-budget policy after objectives, followed by any native manifest binding. Heading wording may vary.
- **Presentation:** Use concise structured tables for SLIs, SLO targets, error budgets, and burn-rate alert tiers paired with brief policy prose sized to the service. Required roles may share sections while keeping mathematical denominators, missing-data rules, SLA boundaries, policy authorities, and native validation status directly retrievable.

| Projection | Title and metadata ownership | Syntax and source authority |
| --- | --- | --- |
| SLO and error budget specification (standalone) | Begin with the mandatory 5-key Semantic-Discovery YAML frontmatter followed by one service-specific H1. Service scope, agreement state, mathematical definitions, error-budget governance, and corpus-level governance inheritance where applicable remain body content. | Use GFM prose and tables grounded in inspected telemetry sources, dependency limits, and stakeholder agreements. This specification controls human reliability definitions and policy agreements; changes to telemetry instrumentation, dependencies, or native manifests require reconciliation and reassessment. |
| Native SLO or alerting manifest (native) | A machine-readable native manifest (such as OpenSLO YAML, Sloth YAML, or Prometheus recording and alerting rules) omits Semantic-Discovery YAML frontmatter and retains its format-native schema metadata without injected Markdown headings. | Each selected manifest format and version controls its native syntax, query grammar, and automated validation. Validator status covers only the checked artifact, format version, and mapping; GFM prose never establishes manifest syntax validity, and prose or manifest edits require re-checking. |

| Section role | Status and inclusion condition | Content obligation |
| --- | --- | --- |
| Service scope, user journeys, and agreement state | Required | Identify the bounded service, critical user journeys or interfaces, measurement vantage point, exclusions, accountable engineering and product owners, agreement state (`proposed`, `agreed`, `under-review`, `deprecated`, or `superseded`) with actual decision basis, client or receiving-party element when applicable, and explicit separation between these internal engineering SLOs and any external contractual SLA. |
| Service level indicator definitions | Required | For each SLI, specify its unique label, reliability dimension (such as availability, latency, correctness, freshness, or throughput), exact mathematical ratio or threshold formula (`good events / valid events` or time-slice equivalent), included and excluded traffic or failure classes, telemetry data source and aggregation rule, missing-telemetry handling, and known vantage-point blind spots. |
| Objectives, compliance windows, and error budgets | Required | For each SLI, state the target threshold with exact precision, compliance window type (`rolling` or `calendar`), duration and timezone where calendar-based, resulting error budget expressed in concrete units (bad events or downtime), dependency reliability ceiling or rationale, and `proposed` versus `agreed` status. |
| Burn-rate alerting and response tiers | Required | Define burn-rate alert tiers (such as urgent fast-burn paging and non-urgent slow-burn ticketing) with exact burn-rate multipliers, short and long evaluation windows, fraction of budget consumed per alert, severity, notification routing, and references to controlling runbooks or observability registers without embedding operational command sequences. |
| Error budget policy and governance | Required | Define concrete operational and delivery actions triggered at budget milestones (warning, rapid burn, exhaustion)—including reliability prioritization, release-gating conditions, and post-incident review triggers—along with the explicit authority required to invoke actions or grant time-bounded exceptions, escalation routes, and periodic SLO calibration cadence. |
| Native manifest binding | Conditional when one or more machine-readable SLO, SLI query, or burn-rate alerting manifests are selected | For each selected manifest, state its format and version, controlling artifact locator and revision, mapping between prose rules and native queries or thresholds, precedence on discrepancy, validator tool, and actual check status (`pass`, `fail`, `inconclusive`, or `not-run`). Re-check after any query, threshold, or prose edit. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
| --- | --- | --- |
| Service journey and vantage point | One or more bounded user journeys or service interfaces and their measurement vantage points in Service scope, user journeys, and agreement state. | Distinguish client-side, edge, server-side, and pipeline measurement perspectives; server uptime alone does not represent client-visible availability when network or edge failures are unobserved. |
| Service level indicator (SLI) | One or more unambiguously defined quantitative indicators in Service level indicator definitions. | Specify numerator (good), denominator (valid), explicit exclusions, units, telemetry source, aggregation, and missing-data rule so independent evaluators compute identical values from identical data. |
| Service level objective (SLO) | One or more reliability targets bound to defined SLIs in Objectives, compliance windows, and error budgets. | State exact target percentage or bound, compliance window type and length, rationale, dependency ceiling, and `proposed` versus `agreed` state. Do not invent targets or silently copy external SLAs without margin analysis. |
| Error budget | Exactly one derived error budget per SLO in Objectives, compliance windows, and error budgets. | Express as `1 - SLO target` over the stated compliance window in concrete failure-count or downtime units, with explicit reset or rolling-recovery behavior. |
| Burn-rate alert tier | One or more alerting tiers per active SLO (or an explicit statement that burn-rate alerting is not yet configured) in Burn-rate alerting and response tiers. | State burn-rate multiplier, short and long window durations, budget share consumed, severity, and routing; link runbooks rather than embedding remediation commands. |
| Error budget policy rule | One coherent governance policy covering warning, exhaustion, exceptions, and periodic recalibration in Error budget policy and governance. | Name concrete trigger thresholds, required actions, deciding authority, and exception expiration; a proposed policy cannot be presented as active release-gating authority. |
| Agreement and SLA boundary | Exactly one governance-state and SLA-separation account in Service scope, user journeys, and agreement state. | State who agreed to the SLOs and policy (or mark undecided); explicitly state that SLO breaches do not automatically determine external contractual SLA liability unless separately governed. |
| Native SLO manifest | Zero or more bound machine-readable SLO or alerting files in Native manifest binding. | Each entry binds format, version, artifact locator, revision, mapping, conflict precedence, validator, and own check status; checks do not transfer across files or edits. |

Use compact tables for SLI formulas (ID, journey, dimension, good/valid rule, source, missing-data rule), SLO targets and error budgets, burn-rate alert tiers, and native manifest bindings, paired with concise prose for error-budget policy rules and dependency tradeoffs. Keep step-by-step incident mitigation in operational runbooks, broad non-SLO signal inventories in observability registers, and historical observed attainment in service-period status reports. Do not insert blank rows, invented query outputs, or observed past-period attainment scores presented as contract definitions.

## Quality criteria

- Two engineers applying each SLI formula to the same telemetry dataset would classify good events, valid events, exclusions, and missing telemetry identically.
- Every SLO specifies an exact target, compliance window type and duration, derived error budget, dependency rationale, and `proposed` versus `agreed` state while staying distinct from external contractual SLAs.
- Burn-rate alerting tiers specify consistent multipliers, dual evaluation windows, budget-consumption fractions, and routing pointers without embedding runbook command procedures.
- Error-budget exhaustion actions, exception authorities, escalation routes, and recalibration cadences are explicit and backed by recorded agreement or clearly marked proposed.
- Missing telemetry, vantage-point blind spots, and unfeasible dependency ceilings remain visible rather than hidden behind optimistic targets.
- Any bound native SLO or alerting manifest declares its format, version, artifact locator, mapping, conflict precedence, validator, and actual check status without treating GFM prose as manifest validation.
