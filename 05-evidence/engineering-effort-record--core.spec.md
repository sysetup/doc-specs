---
title: "Engineering effort and work-time record specification"
description: >-
  Defines the authoring contract for engineering effort records preserving actual work time and effort consumed across a bounded period and purpose, including counting rules, duration units, work attribution, sources, reconciled totals, corrections, review status, and explicit interpretation limits. Supports proportionate planning and authorized accounting while strictly separating consumed effort from remaining estimates, functional completion, operational execution histories, and individual worker surveillance or productivity scoring.
topics:
  - "evidence"
  - "commercial-and-supplier"
  - "software-engineering"
  - "engineering-effort"
  - "work-time-record"
  - "effort-attribution"
  - "effort-reconciliation"
  - "planning-actuals"
use_when:
  - "An engineering activity has consumed effort that requires a proportionate, auditable record of actual time, units, and attribution."
  - "A coordinator or performer is reconciling effort totals, recording corrections, and stating counting rules for authorized accounting."
  - "A reviewer is checking that effort actuals stay distinct from completion claims, remaining estimates, or productivity judgments."
not_for:
  - "Reporting delivery progress, impediments, and schedule forecasts, which belongs in an engineering delivery status report."
  - "Estimating future effort or pricing for a client offer, which belongs in a technical and commercial proposal."
  - "Recording technical work performed on an operational target, which belongs in an operational work execution record."
---

# Engineering effort and work-time record specification

## Identity and selection

- **Specification ID:** `ENGINEERING-EFFORT-RECORD@core`.
- **Purpose:** Record engineering effort actually consumed and its attribution, units, source, and correction basis.
- **Intended readers:** Performers, engineering coordinators, project leads, and authorized cost or planning reviewers.
- **Decision or action supported:** Reconcile consumed effort for planning or authorized accounting without inferring work completion or worker productivity.
- **Use when:** An engineering activity has consumed effort that needs a bounded, proportionate record.
- **Scope boundaries:** Preserve actual effort entries for a defined period and purpose; exclude remaining estimates, functional completion, operational target-action histories, and worker surveillance.

## Authoring inputs and unresolved facts

Inspect the permitted reporting purpose, period, activity or work-item identities, performer attribution appropriate to the audience, actual time-entry sources and precision, duration units, overlap or aggregation rules, corrections, review facts, access, and retention. Obtain billing classifications only when authorized and established.

Expose unknown duration, source, activity, attribution, overlap, or correction with its consequence, resolving action, and assigned owner if known. Missing effort is not zero and may not be reconstructed from presumed productivity. Unreviewed entries remain unreviewed; billing readiness requires its actual agreement and accounting basis. Do not introduce camera, microphone, keystroke, or activity monitoring as required evidence.

## Finished-document contract

- **Title:** Identify the engineering scope and period and name its effort and work-time record.
- **Frontmatter:** Required. Begin with a YAML 1.2 Semantic-Discovery frontmatter block delimited by `---` lines containing `title`, `description` (60 to 140 neutral retrieval words), `topics` (3 to 12 concrete lowercase kebab-case terms), `use_when` (2 to 6 neutral task conditions), and conditional `not_for` (1 to 5 grounded exclusions, omitted when empty), followed by the GFM H1 title. Exclude internal IDs, version strings, hashes, filesystem paths, build metadata, and unresolved template delimiters from frontmatter values. Identity, scope, and state belong in the body. Governing source: Collection Semantic-Discovery Frontmatter contract.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. Omit it for internal documents unless a specific project policy requires explicit negative attestation. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State scope, purpose, and counting rules before effort entries; put totals, reconciliation, and corrections after entries. Heading wording may vary.
- **Presentation:** Use concise factual prose paired with structured evidence tables, chronologies, or finding lists sized to the performed activity. Required roles may share sections while keeping assessed configuration, criteria, actual observations, dispositions, and coverage limits strictly traceable.

| Projection | Title and metadata ownership | Syntax and source authority |
| --- | --- | --- |
| Engineering effort and work-time record (standalone) | Begin with the mandatory 5-key Semantic-Discovery YAML frontmatter followed by one event- or assessment-specific H1. Activity identity, assessed configuration, actual timing, authority, and observed outcomes remain body content; external specification provenance and corpus-level default maintenance metadata apply where governed in a unified corpus. | Use GFM prose, tables, or logs bound to immutable inspected snapshots, artifact revisions, and real execution or review records. Historical observations remain tied to their recorded scope and time; later retests, changes, or approvals create distinct records rather than rewriting prior evidence. |

| Section role | Status and inclusion condition | Content obligation |
| --- | --- | --- |
| Scope, purpose, and counting rules | Required | State effort purpose, period, as-of point, audience, units, precision, inclusion and overlap rules, access, retention, and the client or receiving-party element when applicable. Use only permitted performer detail. |
| Actual effort entries | Required | Record each actual activity entry with stable identity, work reference or description, permitted performer attribution, activity period or duration, unit, source, and observation or self-report basis. State assessed-empty scope explicitly; missing entries remain gaps. |
| Totals and reconciliation | Required | Sum effort under the stated overlap and attribution rules, distinguish incomplete coverage from zero, and identify double counts, inconsistent units, and unresolved entries. Distinguish consumed effort, elapsed calendar time, remaining estimate, and completion evidence. |
| Corrections, review, and use limits | Required | Preserve original entries and correction source, reason, date precision, and reviewer when a review occurred. State actual review or accounting status and limits on using totals for billing, forecast, or performance interpretations. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
| --- | --- | --- |
| Effort period | Exactly one bounded period in Scope, purpose, and counting rules. | Use recorded precision and timezone when a clock time exists; do not invent start or finish times. |
| Effort entry | Zero or more entries in Actual effort entries. | Each records actual consumed effort and its source; an assessed-empty scope is distinct from missing reports. |
| Duration and attribution | One duration with unit and one attribution basis per entry in Actual effort entries. | Units and source precision are explicit; concurrent work by several people contributes person effort under the declared rules rather than elapsed time. |
| Effort total | Exactly one bounded total or incompleteness statement in Totals and reconciliation. | Recalculate from included entries with declared rounding and overlap treatment; hours do not establish percent functionality complete. |
| Correction and review | Zero or more corrections and exactly one review account in Corrections, review, and use limits. | Corrections retain original source and reason; self-report, supervisory review, approved billing, and work acceptance are different facts. |

Use an activity-and-duration table with a bounded total and short reconciliation notes. A selected timekeeping system remains the source of truth; identify export scope and snapshot rather than creating a second editable master. Minimize personal data and use role or permitted attribution codes; effort capture does not require surveillance.

## Quality criteria

- Period, permitted purpose, units, precision, privacy, and counting rules bound the record.
- Each effort entry has a real activity, attribution, duration, and source with missing data distinguishable from zero.
- Totals reconcile units and overlap without substituting effort for elapsed time, remaining estimates, or completed functionality.
- Corrections preserve original entries, and actual review and billing status match their supporting authority and sources.
