---
title: "Discovery input and product feedback register specification"
description: >-
  Defines the authoring contract for discovery input and product feedback registers capturing raw sourced feedback, suggestions, support observations, and field notes through structured intake, deduplication, theme linking, triage state tracking, and downstream routing to authoritative records. Preserves source provenance and context while clearly separating untriaged feedback from approved requirements, prioritized delivery backlogs, defect closure tracking, and ordinary customer service-request fulfillment.
topics:
  - "control-records"
  - "product-and-discovery"
  - "product-feedback"
  - "discovery-intake"
  - "feedback-triage"
  - "theme-linking"
  - "downstream-routing"
  - "source-provenance"
use_when:
  - "Ongoing user feedback, support observations, suggestions, or discovery notes need centralized intake and triage before formal work creation."
  - "A product analyst is linking duplicates, grouping themes, and routing triaged items to requirements, backlogs, or defect records."
  - "A reviewer is checking that raw feedback retains provenance and is never confused with approved commitments."
not_for:
  - "Prioritizing and refining selected product delivery work, which belongs in an ordered product backlog."
  - "Reporting synthesized outcomes from a formal user research round, which belongs in user and context research findings."
  - "Tracking confirmed defects through reproduction and closure, which belongs in a problem or defect report."
---

# Discovery input and product feedback register specification

## Identity and selection

- **Specification ID:** `PRODUCT-FEEDBACK-REGISTER@core`.
- **Purpose:** Maintain sourced discovery inputs and feedback through triage and routing to authoritative downstream records.
- **Intended readers:** Researchers, analysts, product owners, support personnel, and requirements or defect stewards.
- **Decision or action supported:** Identify untriaged inputs, duplicates, themes, and disposition without treating feedback as approved work.
- **Use when:** Discovery notes, suggestions, support feedback, or ambiguous product observations need ongoing intake before formal disposition.
- **Scope boundaries:** Control raw input identity, provenance, triage, and downstream routing; exclude approved requirements, ordered delivery work, defect closure, and ordinary service-request fulfillment.

## Authoring inputs and unresolved facts

Inspect the intake boundary, real channels and source material, received dates and precision, product or context versions when known, permitted identifying information, triage roles and vocabulary, duplicates, themes, actual disposition decisions and downstream links, access and retention rules, and update triggers.

Expose unknown source, time, context, owner, classification, or disposition with its consequence and resolving action; name only assigned owners. Keep unresolved inputs visible rather than defaulting them to accepted or dismissed. Restrict sensitive raw evidence to its permitted location. Do not invent downstream records, approval, reporter identities, or resolution.

## Finished-document contract

- **Title:** Identify the discovery or product boundary and name its input and feedback register.
- **Frontmatter:** Required. Begin with a YAML 1.2 Semantic-Discovery frontmatter block delimited by `---` lines containing `title`, `description` (60 to 140 neutral retrieval words), `topics` (3 to 12 concrete lowercase kebab-case terms), `use_when` (2 to 6 neutral task conditions), and conditional `not_for` (1 to 5 grounded exclusions, omitted when empty), followed by the GFM H1 title. Exclude internal IDs, version strings, hashes, filesystem paths, build metadata, and unresolved template delimiters from frontmatter values. Identity, scope, and state belong in the body. Governing source: Collection Semantic-Discovery Frontmatter contract.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. Omit it for internal documents unless a specific project policy requires explicit negative attestation. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State intake scope and handling rules before entries; follow entries with triage, routing, and reconciliation. Heading wording may vary.
- **Presentation:** Use compact registers, structured item tables, or grouped lists sized to the controlled inventory without placeholder rows. Required roles may share sections while keeping stable identities, owners, states, source locators, and reconciliation gaps directly retrievable.

| Projection | Title and metadata ownership | Syntax and source authority |
| --- | --- | --- |
| Discovery input and product feedback register (standalone) | Begin with the mandatory 5-key Semantic-Discovery YAML frontmatter followed by one scope-specific H1. Control scope, as-of point, state, ownership, and authority references remain body content, inheriting corpus-level changelog/VCS versioning, declared default maintainer, and external specification provenance when governed in a unified operational corpus. | Use GFM prose, tables, or structured lists bound to controlling masters and inspected snapshots. Referenced systems, trackers, or baselines remain authoritative for their native records; changes to controlling sources require reconciliation rather than silent overwrite. |

| Section role | Status and inclusion condition | Content obligation |
| --- | --- | --- |
| Intake boundary and handling | Required | Identify scope, channels, as-of point, steward or assignment gap, triage rules, access, retention, redaction, and the client or receiving-party element when applicable. Explain excluded request classes and their actual routes. |
| Input entries | Required | Give every in-scope input a stable key, source or permitted locator, received time or gap, minimized description, context and version when known, uncertainty, and assigned triage owner or gap. An assessed-empty scope has an explicit no-inputs statement. |
| Triage and disposition | Required | Record classification, duplicates or themes, current triage state, decision basis, and authoritative downstream destination when established. Preserve original input meaning and conflicting interpretations. Routed feedback is not delivered functionality or a closed defect. |
| Reconciliation and upkeep | Required | Identify stale triage, missing source or destination, duplicate mistakes, and unresolved ownership; give next resolving actions, review triggers, and history for changed dispositions. State whether no discrepancies were identified after assessment. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
| --- | --- | --- |
| Input | Zero or more entries in Input entries. | Use one immutable key per received input; do not silently merge distinct reports or overwrite their origins. |
| Source and context | One provenance account per input in Input entries. | Store minimized content and permitted locators, not unrestricted sensitive transcripts; unknown context is not a default product version. |
| Triage state | Exactly one of untriaged, in-triage, deferred, routed, duplicate, or dismissed per input in Triage and disposition. | Move from untriaged to in-triage before a disposition; deferred may return to in-triage. Routed requires an existing destination, duplicate an existing counterpart, and dismissed a recorded reason and deciding role. Reopening a disposition returns to in-triage with history. |
| Theme or duplicate link | Zero or more in Triage and disposition. | A theme is an analyst grouping rather than evidence of prevalence; duplicate links retain each original source and cannot form cycles. |
| Downstream relationship | Zero or more actual record links in Triage and disposition. | Identify each requirement, backlog item, defect, change, or action master and routing reason; a candidate destination is proposed and cannot support routed. |
| Currency and history | Exactly one reconciliation basis and zero or more changed-disposition events in Reconciliation and upkeep. | State sources and as-of point; preserve prior disposition and reason when re-triaged. |

Use one row or compact block per input with origin, context, uncertainty, owner, triage state, and destination. Link to restricted raw records and established downstream masters. The register controls intake and routing; requirements, backlog, defect, and service-request masters retain their own obligations and outcomes.

## Quality criteria

- Scope, channels, access, retention, and steward assignment govern the actual intake without exposing restricted source data.
- Entries preserve immutable identity, source, time precision, context, and uncertainty; an empty assessment is explicit.
- State transitions have their required reason and destination; themes and duplicate relationships do not manufacture prevalence or approved work.
- Reconciliation exposes stale or broken routing and retains changed dispositions with their actual history.
