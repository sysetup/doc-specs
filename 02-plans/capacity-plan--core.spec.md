---
title: "Capacity plan specification"
description: >-
  Defines the authoring contract for capacity plans arranging future workload demand modeling, resource headroom targets, bottleneck and scaling-cliff identification, automated and manual scaling triggers, procurement and quota lead times, cost boundaries, and load-validation readiness across a declared planning horizon for a bounded service or infrastructure scope. Separates empirical baseline utilization measurements from modeled growth or burst forecasts and exposes missing telemetry, inelastic failure points, and approval cutoffs before committing provisioning investments.
topics:
  - "planning"
  - "operations"
  - "networking-and-infrastructure"
  - "capacity-plan"
  - "demand-forecasting"
  - "resource-headroom"
  - "scaling-triggers"
  - "bottleneck-analysis"
use_when:
  - "A service, platform, or infrastructure scope requires a forward-looking plan aligning workload growth forecasts with compute, storage, network, or quota headroom."
  - "A reliability or infrastructure engineer is identifying scaling cliffs, provisioning lead times, load-validation tests, and exhaustion triggers across a planning horizon."
  - "A reviewer or service owner is verifying that scaling investments and cost envelopes rest on transparent baseline observations and labeled forecast assumptions."
not_for:
  - "Planning overall routine service staffing, support commitments, backups, and day-to-day maintenance, which belongs in an operations and support plan."
  - "Analyzing component failure modes, redundancy failover architectures, and degraded-operation modes for uptime, which belongs in a service or system availability plan."
  - "Specifying mathematical service level indicators, error budgets, and burn-rate alerting policies, which belongs in a service level objective and error budget specification."
  - "Reporting historical observed production utilization and service metrics for a past period, which belongs in a service-period status report."
---

# Capacity plan specification

## Identity and selection

- **Specification ID:** `CAPACITY-PLAN@core`.
- **Purpose:** Plan how a bounded service, platform, or infrastructure scope forecasts demand, maintains resource headroom, resolves scaling bottlenecks, triggers provisioning within lead times, and validates capacity across a defined planning horizon.
- **Intended readers:** Capacity and reliability engineers, infrastructure and platform owners, service and product owners, operators, and budget or procurement decision makers.
- **Decision or action supported:** Choose defensible headroom margins, scaling actions, architectural bottleneck mitigations, procurement cutoffs, and load-validation work before resource saturation degrades service reliability.
- **Use when:** A service, workload, or infrastructure boundary faces organic growth, seasonal peaks, launch events, failover reserve needs, hardware or cloud-quota lead times, or nonlinear scaling limits requiring structured forward-looking capacity management.
- **Scope boundaries:** Plan future demand scenarios, resource capacity models, headroom targets, scaling triggers, lead times, cost tradeoffs, and planned load checks for the defined boundary and horizon; exclude routine operations staffing, standalone SLO contracts, detailed runtime environment build specifications, and past-period operational status reports.

## Authoring inputs and unresolved facts

Obtain the service or infrastructure boundary, included environments, regions, tiers, and exclusions; planning horizon, review cadence, and accountable owner; empirical baseline workload and utilization observations with capture periods, peak definitions, and telemetry source locators; business, seasonal, batch, failover, and architectural demand drivers and forecast assumptions; resource dimensions in scope (such as compute, memory, storage, IOPS, network bandwidth, connection or concurrency limits, external API quotas, or software licenses) and known architectural bottlenecks or scaling cliffs; established reliability or latency objectives from controlling SLO specifications or availability plans when they exist; autoscaling limits, manual provisioning workflows, and vendor, hardware, or quota lead times; cost unit rates, budget constraints, and expenditure approval authorities when cost is in scope; and planned load-testing or capacity-monitoring interfaces.

If baseline utilization, workload growth drivers, resource-consumption ratios, vendor lead times, scaling ceilings, or budget approval authorities are unknown or unmeasured, record the gap explicitly with its saturation consequence, resolving action, and actual owner only when assigned. Do not present unmeasured estimates, synthetic launch projections, or linear extrapolations as empirical baseline observations. Missing baseline telemetry or unvalidated load curves block committing irreversible procurement or claiming verified headroom beyond measured operating ranges. Distinguish planned load tests and proposed scaling investments from completed capacity validations or approved budgets.

## Finished-document contract

- **Title:** Identify the service, platform, or infrastructure scope and planning horizon and name the document as its capacity plan.
- **Frontmatter:** Required. Begin with a YAML 1.2 Semantic-Discovery frontmatter block delimited by `---` lines containing `title`, `description` (60 to 140 neutral retrieval words), `topics` (3 to 12 concrete lowercase kebab-case terms), `use_when` (2 to 6 neutral task conditions), and conditional `not_for` (1 to 5 grounded exclusions, omitted when empty), followed by the GFM H1 title. Exclude internal IDs, version strings, hashes, filesystem paths, build metadata, and unresolved template delimiters from frontmatter values. Scope, horizon, baseline observations, forecasts, and approval state belong in the body. Governing source: Collection Semantic-Discovery Frontmatter contract.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. Omit it for internal documents unless a specific project policy requires explicit negative attestation. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Establish scope, horizon, and empirical baseline before demand forecasts; place resource modeling and bottlenecks before scaling triggers, lead times, and conditional cost tradeoffs; place load validation, monitoring, and reassessment rules last. Heading wording may vary.
- **Presentation:** Scale sections, resource-dimension tables, and scenario schedules to the bounded system without adding empty chapters for unconstrained resource classes. Required roles may share sections while keeping observed baselines, modeled forecasts, inelastic cliffs, lead-time cutoffs, and open gaps clearly separated from completed results.

| Projection | Title and metadata ownership | Syntax and source authority |
| --- | --- | --- |
| Capacity plan (standalone) | Begin with the mandatory 5-key Semantic-Discovery YAML frontmatter followed by one scope-specific H1. Planning horizon, baseline snapshots, forecast assumptions, ownership, and approval boundaries remain body content, inheriting corpus-level changelog/VCS versioning, declared default maintainer, and external specification provenance when governed in a unified operational corpus. | Use GFM prose, scenario tables, or bottleneck diagrams referencing controlling telemetry snapshots, SLO specifications, availability plans, and external forecast workbooks by edition and locator. External modeling spreadsheets or telemetry queries remain authoritative for raw calculations; architectural, traffic, or quota changes require plan reassessment. |

| Section role | Status and inclusion condition | Content obligation |
| --- | --- | --- |
| Capacity scope, horizon, and baseline | Required | Define the bounded service, platform, or infrastructure scope, included environments, regions, or tiers, exclusions, planning horizon, review cadence, accountable owner, and client or receiving-party element when applicable. Record observed baseline workload and resource utilization with exact units, measurement periods, peak definitions, and telemetry source locators, or state explicitly that the service lacks production baseline observations. |
| Demand drivers and workload forecast | Required | Identify primary business, user, seasonal, batch, and failover demand drivers. Define explicit forecast scenarios (such as baseline growth, expected peak, burst event, and regional failover load), forecasting method, assumptions, units, and uncertainty bounds. Keep historical trends strictly distinct from modeled projections and cite any external forecast model by edition and locator. |
| Resource model, bottlenecks, and headroom targets | Required | Map each demand scenario to constrained resource dimensions (compute, memory, storage, IOPS, network bandwidth, concurrency, external quotas, or licenses) with conversion assumptions. Identify target utilization and headroom margins (including N+1 or regional failover reserves where required), nonlinear scaling cliffs, and inelastic bottlenecks. Reference controlling SLO specifications or availability plans when they establish performance thresholds rather than inventing targets. |
| Scaling strategy, provisioning triggers, and lead times | Required | Define automated and manual scaling mechanisms, exact threshold triggers, maximum scaling ceilings, and procurement, hardware, cloud-quota, or architectural-remediation lead times. Establish decision cutoffs preceding projected exhaustion and define load-shedding, queueing, or graceful-degradation fallbacks if demand exceeds available capacity. |
| Cost envelope and resource tradeoffs | Conditional when infrastructure budget, unit-economics bounds, or procurement approval constraints are in scope | Estimate resource expenditure per forecast scenario with explicit unit-cost basis and date, state budget ceilings and optimization levers (such as rightsizing, tiering, or commitment terms), and identify the authority required to approve incremental spend before commitment. |
| Load validation, monitoring, and plan reassessment | Required | Specify planned load, stress, or soak validation checks with target configurations, pass criteria, and expected evidence; identify saturation telemetry and alert interfaces (linking controlling observability registers when present); and define concrete triggers (forecast divergence, architectural change, vendor quota change, or capacity incident) that require revising the plan. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
| --- | --- | --- |
| Capacity scope and horizon | Exactly one bounded service or infrastructure scope and explicit start-to-end planning horizon in Capacity scope, horizon, and baseline. | Name included environments, tiers, regions, and exclusions; do not extrapolate capacity claims outside stated tiers or dates. |
| Baseline utilization observation | One observed baseline account per in-scope resource dimension in Capacity scope, horizon, and baseline, or an explicit unmeasured-baseline gap. | State exact units, aggregation statistic (such as p95 peak or sustained mean), measurement window, and telemetry source locator; never substitute assumed load for observed utilization. |
| Demand scenario | One or more named forward-looking workload scenarios in Demand drivers and workload forecast. | State drivers, units, time intervals, assumptions, and uncertainty range; label every forecast explicitly as a projection. |
| Resource dimension and headroom target | One entry per constrained resource class in Resource model, bottlenecks, and headroom targets. | Define unit, current limit, target utilization ceiling, required reserve or failover headroom, and basis linking to established reliability or latency objectives when they exist. |
| Bottleneck or scaling cliff | Zero or more identified nonlinear limits or inelastic components in Resource model, bottlenecks, and headroom targets. | State the limiting component, threshold where degradation begins, expected failure mode, and planned architectural mitigation or explicit unresolved gap. Assessed absence of known cliffs within the horizon requires an explicit basis. |
| Scaling action and lead time | One provisioning or remediation route per constrained resource dimension in Scaling strategy, provisioning triggers, and lead times. | State trigger threshold, automated versus manual execution, scaling ceiling, realistic lead time, decision cutoff date or utilization mark, responsible owner, and fallback behavior if exhausted. |
| Cost and approval boundary | Conditional on Cost envelope and resource tradeoffs being included; one account per budgeted scenario. | State cost basis, currency, time period, assumptions, and actual approving authority; a modeled estimate is not budget approval. |
| Planned capacity check and review trigger | One or more planned load checks or explicit non-testing limits, plus one or more reassessment triggers in Load validation, monitoring, and plan reassessment. | Distinguish planned load tests and expected evidence from completed performance results; state who reviews forecast-versus-actual variance and when. |

Use a resource-dimension table mapping baseline utilization, forecasted peak demand, headroom ceiling, lead time, trigger threshold, and exhaustion date across scenarios, paired with concise prose for forecasting assumptions, architectural cliffs, and fallback tradeoffs. Diagrams may clarify multi-tier fan-out or failover redistribution. Keep detailed alert routing in observability registers and step-by-step scaling commands in operational runbooks; omit executable provisioning scripts and blank scenario rows.

## Quality criteria

- Scope, environments, regions, planning horizon, and accountable ownership bound every baseline observation and forecast scenario.
- Empirical baseline measurements specify exact units, aggregation statistics, time windows, and telemetry locators, remaining strictly distinct from labeled projections and synthetic assumptions.
- Resource models expose constrained dimensions, failover reserve needs, nonlinear scaling cliffs, and external quota ceilings rather than assuming uniform linear scaling.
- Scaling triggers account for actual hardware, quota, or architectural lead times with explicit decision cutoffs and load-shedding fallbacks before exhaustion.
- Cost estimates state their unit-cost basis and required approval authority whenever budget constraints are in scope without implying expenditure authorization.
- Planned load validations, saturation monitoring interfaces, and forecast-divergence review triggers state observable criteria and expected evidence without claiming completed test results.
