---
title: "Observability register specification"
description: >-
  Defines the authoring contract for observability registers maintaining a controlled catalog of watched operational signals, alerting or action thresholds, accountable signal owners, and attached response instructions for a defined service or system at a stated as-of point. Surfaces monitoring blind spots and unowned signals clearly while excluding on-call duty scheduling decisions, detailed step-by-step remediation commands, active incident chronologies, and historical threshold-crossing or alert-firing telemetry results.
topics:
  - "control-records"
  - "operations"
  - "observability-register"
  - "monitored-signals"
  - "alert-thresholds"
  - "signal-ownership"
  - "monitoring-catalog"
  - "service-observability"
use_when:
  - "A service or system needs a controlled inventory of watched metrics, logs, probes, thresholds, owners, and expected responses."
  - "An operator or reliability engineer is auditing monitoring coverage gaps and verifying every alert threshold has a real owner."
  - "A team is standardizing watched operational signals separately from detailed remediation runbooks."
not_for:
  - "Step-by-step troubleshooting commands and rollback procedures triggered by an alert, which belong in an operational runbook."
  - "Reporting observed telemetry trends and service availability over a past window, which belongs in a service-period status report."
  - "Defining overall operations staffing and support commitments, which belongs in an operations and support plan."
---

# Observability register specification

## Identity and selection

- **Specification ID:** `OBSERVABILITY-REGISTER@core`.
- **Purpose:** Record the watched signals, their thresholds, their owners, and the response each signal calls for.
- **Intended readers:** The owners of those signals and the people who must know which signal is watched, at what threshold, and what response applies.
- **Decision or action supported:** Determine the controlled list of watched signals and the threshold, owner, and response for each.
- **Use when:** A service or system needs a controlled list of the signals it watches and the response attached to each threshold.
- **Scope boundaries:** Record watched signals and their established thresholds, ownership, and response instructions. Exclude operating-duty assignment decisions, detailed execution steps, event chronologies, and observed threshold-crossing or response results.

## Authoring inputs and unresolved facts

Obtain the service or system, the as-of point, and each signal that is actually watched, including its threshold, owner, and response when those facts are established. Obtain the existing assignments and response instructions that establish those fields when available.

If a signal, threshold, owner, or response is unknown, record the gap. Do not invent a metric, a threshold, an owner, or a response. A response names what to do or which existing procedure applies. Keep prescribed actions distinct from observed events. Do not assign `pass`, `fail`, `inconclusive`, or `not-run`.

## Finished-document contract

- **Title:** Identify the service or system and name the document as its observability register.
- **Frontmatter:** Required. Begin with a YAML 1.2 Semantic-Discovery frontmatter block delimited by `---` lines containing `title`, `description` (60 to 140 neutral retrieval words), `topics` (3 to 12 concrete lowercase kebab-case terms), `use_when` (2 to 6 neutral task conditions), and conditional `not_for` (1 to 5 grounded exclusions, omitted when empty), followed by the GFM H1 title. Exclude internal IDs, version strings, hashes, filesystem paths, build metadata, and unresolved template delimiters from frontmatter values. The service and as-of point belong in the body. Governing source: Collection Semantic-Discovery Frontmatter contract.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. Omit it for internal documents unless a specific project policy requires explicit negative attestation. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Identify the service before the signal list. State gaps with or after the list. Heading wording may vary.
- **Presentation:** Use compact registers, structured item tables, or grouped lists sized to the controlled inventory without placeholder rows. Required roles may share sections while keeping stable identities, owners, states, source locators, and reconciliation gaps directly retrievable.

| Projection | Title and metadata ownership | Syntax and source authority |
| --- | --- | --- |
| Observability register (standalone) | Begin with the mandatory 5-key Semantic-Discovery YAML frontmatter followed by one scope-specific H1. Control scope, as-of point, state, ownership, and authority references remain body content, inheriting corpus-level changelog/VCS versioning, declared default maintainer, and external specification provenance when governed in a unified operational corpus. | Use GFM prose, tables, or structured lists bound to controlling masters and inspected snapshots. Referenced systems, trackers, or baselines remain authoritative for their native records; changes to controlling sources require reconciliation rather than silent overwrite. |

| Section role | Status and inclusion condition | Content obligation |
| --- | --- | --- |
| Identity and scope | Required | Identify the service or system and the as-of point. Include the client or receiving-party element from this contract when applicable. Identify established assignment or response-instruction records when they explain signal ownership or response. |
| Watched signals | Required | For each watched signal, state the signal, the threshold, the owner, and the response. If no signal is watched, say so instead of adding a placeholder signal. |
| Gaps | Required | Identify missing thresholds, owners, or responses, and the next action. A missing threshold is not a silent default. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
| --- | --- | --- |
| Service or system | One service or system per register. | State the as-of point. A signal for a different service does not belong in this list. |
| Signal | Zero or more watched signals. | Name the signal and what it measures. Do not invent a metric to fill the list. |
| Threshold | The threshold that calls for a response, when established. | State the comparison and the units. An unknown threshold stays unknown. |
| Owner | One owner for each signal that has one. | The owner is accountable for the signal on this list. An unassigned owner stays unassigned. Do not invent a person or party. |
| Response | The response the threshold calls for, when established. | Name the action or an existing procedure. Describe the prescribed response without claiming it occurred. |
| Operating duty | No operating-duty description as a substitute for a signal row. | Keep signal, threshold, owner, and response fields explicit. |

Use a register table with signal, threshold, owner, and response. Prose should explain a threshold the table would make ambiguous. Do not include a blank signal row.

## Quality criteria

- Each watched signal states its known threshold, owner, and response, or the missing fact is explicit.
- Each owner or response reflects an established assignment or instruction.
- Threshold comparisons and response instructions describe when action is called for and what action is prescribed.
- Unknown thresholds, owners, and responses stay visible. The register invents no signal, threshold, owner, or party.
