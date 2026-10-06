# Engineering delivery status report specification

## Identity and selection

- **Specification ID:** `ENGINEERING-STATUS-REPORT@core`.
- **Purpose:** Report bounded engineering delivery progress, impediments, resource facts, and forecast.
- **Intended readers:** Project leads, engineering coordinators, product owners, delivery decision makers, and receiving stakeholders.
- **Decision or action supported:** Replan delivery or resolve impediments using sourced progress and explicit forecast assumptions.
- **Use when:** An active engineering delivery effort needs a current period or as-of status view.
- **Scope boundaries:** Maintain delivery status and forward decisions for development or engineering work; exclude test-only outcome accounting, routine service health, unsupported productivity claims, and acceptance decisions.

## Authoring inputs and unresolved facts

Inspect the delivery scope, reporting period and cutoff, plan or backlog snapshots, actual progress and completion sources, resource and effort evidence when used, blockers, dependencies, risks, forecast assumptions, changes in scope, decisions needed, and next-period work.

Expose unknown baseline, count, completion criterion, source, forecast premise, or owner with its effect and resolving action. Unknown counts are not zero; claimed completion without a completion basis remains unconfirmed. Keep forecasts prospective and do not invent cost, productivity, approval, or acceptance.

## Finished-document contract

- **Title:** Identify the delivery effort and reporting period and name its engineering delivery status report.
- **Frontmatter:** None. Begin with the GFM title. Identity, scope, and state belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State period and source basis before progress; put impediments before forecast, decisions, and next-period work. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Period, scope, and sources | Required | Identify delivery scope, period and cutoff, baseline or plan edition, changes to the counting scope, units, actual sources and their as-of times, and client or receiving-party element. |
| Planned and actual delivery | Required | Compare planned work with observed work in progress and established completed outputs. Cite completion criteria and evidence, preserve unfinished or cancelled scope, and explain denominators, overlap, and measurement limits for counts or percentages. |
| Resources, blockers, and dependencies | Required | Record sourced effort, cost, or capacity facts only when used; distinguish resource forecasts from observations. Identify current impediments and their impact, known dependency and risk masters, owner or gap, and assessed absence where applicable. |
| Forecast, decisions, and next work | Required | State remaining-work forecast, changed assumptions, confidence limits, schedule and scope scenarios when used, requested decisions, and planned next-period actions. Link actual action masters; do not invent decisions or claim planned work occurred. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Reporting basis | Exactly one period, cutoff, and source account in Period, scope, and sources. | Preserve time precision and versions; comparisons across changing scope disclose the change. |
| Progress measure | Zero or more measures in Planned and actual delivery. | State unit, source, completion rule, numerator and denominator when used; unknown or partial coverage cannot be presented as full progress. |
| Resource fact | Zero or more in Resources, blockers, and dependencies. | Identify source, unit, period, and observed versus forecast state; time logged alone is not delivered value or individual productivity. |
| Impediment | Zero or more assessed blockers, dependency issues, or risk citations in Resources, blockers, and dependencies. | State present blocker versus uncertain future risk and actual decision route; preserve authoritative downstream states. |
| Forecast and decision request | Exactly one forecast account and zero or more requests in Forecast, decisions, and next work. | Record assumptions and uncertainty or that no supported forecast exists; a requested decision is not made. |
| Next-period action | Zero or more planned actions in Forecast, decisions, and next work. | Give responsible role if assigned and source links when real; expected actions have no completion result. |

Use prose for forecast and decisions and a small plan-versus-actual table for repeatable measures. A burndown, schedule chart, or dashboard may supplement the view when its units, source, and cutoff are explicit. The report summarizes delivery masters without rewriting requirements, backlog, effort, or test results.

## Quality criteria

- Scope, cutoff, baseline, units, and sources make each period claim recoverable.
- Actual progress and percentages have completion evidence and a bounded counting basis.
- Resources and impediments retain sources, ownership gaps, and observed-versus-forecast distinctions.
- Forecasts, decisions needed, and next-period actions remain prospective and preserve uncertainty.
