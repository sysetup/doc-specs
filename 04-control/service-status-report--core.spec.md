# Service-period status report specification

## Identity and selection

- **Specification ID:** `SERVICE-STATUS-REPORT@core`.
- **Purpose:** Maintain a bounded view of observed service-period results, data coverage, trends, and follow-up decisions.
- **Intended readers:** Service owners, operators, support leads, security roles, and service decision makers.
- **Decision or action supported:** Assess current service results and request follow-up without treating missing telemetry as healthy operation.
- **Use when:** An operating service needs periodic or as-of status, including periods with no incidents.
- **Scope boundaries:** Summarize actual production-period results and their interpretation limits; exclude operating plans, signal definitions, incident chronologies, delivery progress, and unsupported contractual compliance claims.

## Authoring inputs and unresolved facts

Inspect service and actual configuration changes, reporting period and cutoff, agreed objectives and definitions or gaps, telemetry and support sources with coverage, reliability and capacity observations, maintenance and change records, incident masters, comparable prior periods, actual forecast assumptions, and follow-up responsibilities.

Expose unknown objective, denominator, telemetry interval, source, version, or decision right with its consequence and resolving action; name only assigned owners. Missing data is not zero incidents, full uptime, or met objectives. A forecast cannot repair missing observations. Do not invent outages, healthy states, targets, causes, or service acceptance.

## Finished-document contract

- **Title:** Identify the service and period and name its service-period status report.
- **Frontmatter:** None. Begin with the GFM title. Identity, scope, and state belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State service, period, and data coverage before results; place incidents and changes before trends, forecasts, and follow-up decisions. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Service, period, and objective basis | Required | Identify service, environments and configuration range, operating and measurement windows, period and cutoff, actual objective editions and agreement state or gaps, exclusions, and client or receiving-party element. |
| Sources and data coverage | Required | Identify queries, telemetry and support sources, capture times, units, sampling, covered and missing intervals, denominator rules, and data-quality issues. Preserve unavailable or stale signals and permission limits. |
| Observed results | Required | Report sourced reliability, availability, performance, capacity, support, and security facts relevant to the service. Compare against objectives only when definition, scope, coverage, and measurement basis support comparison; otherwise state that it cannot be concluded. |
| Incidents, changes, and maintenance | Required | Summarize real incident, change, and maintenance facts with source links and bounded impact. A no-incidents statement identifies the assessed source scope and its limits; do not create an incident record for a healthy period. |
| Trends, forecast, and follow-up | Required | Give trends only against actual comparable periods and explain configuration or measurement changes. Label forecasts and assumptions separately, request actual decisions, and identify follow-up actions or assignment gaps without claiming them completed. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Service reporting window | Exactly one bounded period and cutoff in Service, period, and objective basis. | Distinguish supported hours, observation windows, and objective measurement periods; preserve recorded time precision. |
| Objective | Zero or more sourced objectives in Service, period, and objective basis. | State definition, unit, agreement state, conditions, and measurement window; no invented SLO or compliance conclusion. |
| Measurement and coverage | One source and coverage account per reported measure in Sources and data coverage and Observed results. | Identify numerator and denominator where relevant, excluded periods, sampling, and missing data; unknown is not a favorable observation. |
| Operational event summary | Exactly one assessed account in Incidents, changes, and maintenance. | Link actual incident and work masters; absence of a listed event is not evidence of event-free operation. |
| Trend or forecast | Zero or more in Trends, forecast, and follow-up. | Trends require actual comparable history; forecasts identify assumptions and cannot substitute for observed period results. |
| Follow-up request | Zero or more in Trends, forecast, and follow-up. | Name requested decision, owner if assigned, and actual action link when available; a request is not authorization or completed remediation. |

Use a compact measurement table with definition, period, source, coverage, value, and qualified interpretation, plus short event and decision notes. Dashboards may be referenced by actual query and snapshot. This report controls the bounded status summary while telemetry definitions, incidents, operations plans, and action masters retain their authority.

## Quality criteria

- Service configurations, reporting and measurement windows, objectives, and agreement states bound the results.
- Each measurement exposes source, units, denominator, sampling, and missing coverage; absent telemetry is not healthy status.
- Incident, change, and maintenance summaries match actual masters and bounded assessed-empty claims.
- Trends use comparable actual history, forecasts are labeled, and follow-up requests preserve pending decision and assignment state.
