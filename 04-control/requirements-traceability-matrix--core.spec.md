---
title: "Requirements traceability matrix specification"
description: >-
  Defines the authoring contract for requirements traceability matrices recording directed relationships and explicitly surfacing missing required links across controlled endpoints including needs, requirements, architecture or design elements, interfaces, decisions, assessment activities, and evidence records within a declared scope. Preserves link bases, relationship semantics, and change-impact navigation while keeping endpoint wording, controlled parameters, assessment verdicts, and approval authority strictly inside their referenced endpoint records.
topics:
  - "control-records"
  - "requirements-engineering"
  - "systems-engineering"
  - "requirements-traceability"
  - "traceability-matrix"
  - "directed-relationships"
  - "impact-analysis"
  - "coverage-gaps"
use_when:
  - "A project needs bidirectional navigation across needs, requirements, design, decisions, verification activities, and evidence."
  - "A change analyst or V&V lead is performing change-impact analysis and exposing missing or disputed traceability edges."
  - "A reviewer is checking traceability completeness without duplicating endpoint requirement text or test verdicts."
not_for:
  - "Tracking per-requirement verification methods, criteria, and conformance status, which belongs in a requirements verification matrix."
  - "Tracking stakeholder need validation scenarios and fitness outcomes, which belongs in a validation matrix."
  - "Indexing requirement IDs, owners, and content states alone, which belongs in a requirements registry."
---

# Requirements traceability matrix specification

## Identity and selection

- **Specification ID:** `REQUIREMENTS-TRACEABILITY-MATRIX@core`.
- **Purpose:** Record directed relationships among needs, requirements, design or interface records, decisions, assessment activities, and evidence within a declared scope, and show where a required relationship is missing.
- **Intended readers:** Requirements and design owners, V&V leads, change analysts, and reviewers who need to navigate origins and downstream records.
- **Decision or action supported:** Find the origins and downstream records of an in-scope item, identify a missing or disputed relationship, and see which relationships a change affects.
- **Use when:** A project needs bidirectional navigation across controlled engineering records and visibility of missing relationships.
- **Scope boundaries:** Record supported relationships and their basis. Endpoint wording, controlled parameters, assessment results, and approval decisions remain content of the identified endpoint records; an edge records none of those values.

## Authoring inputs and unresolved facts

Inspect the actual need, requirement, design, interface, decision, activity, and evidence sources inside the declared scope, including their kinds, IDs, editions, locators, effectivity, and content states. Cite each source. Do not copy its wording or result into this matrix as a master. Establish the project's allowed relationship names, endpoint kinds, and direction. Obtain the basis for each asserted edge by inspecting both endpoints, not just matching IDs. Determine which parent, allocation, or downstream relationships the project actually requires at its current maturity. A required relationship to an activity or evidence record is only a link. It is not a verification or validation result.

A relationship does not change an endpoint's kind. Identify a business or mission need, business obligation, stakeholder requirement, system requirement, software requirement, or interface requirement by the kind declared in its actual project record. An interface endpoint names one real record kind: an interface requirement, an interface-control definition, or an interface-registry identity. A decision endpoint cites an existing decision with its recorded scope and state.

If an endpoint, source edition, link basis, or required-relationship rule is unknown, show the affected entity and missing relationship with its consequence and resolution action, naming a real owner if assigned. Do not manufacture a parent, design element, interface record, decision, assessment activity, or evidence record. A link to an activity that has not been executed is allowed and has no result. Link an evidence record only when that record exists. Do not assign `pass`, `fail`, `inconclusive`, `not-run`, `verified`, `not-verified`, `met`, `not-met`, or `accepted` to the edge or to the obligation. If no valid edges exist, show the inspected scope and the missing relationships rather than adding a placeholder edge or reporting that traceability is complete.

## Finished-document contract

- **Title:** Identify the project, system, or baseline scope and name the document as its requirements traceability matrix.
- **Frontmatter:** Required. Begin with a YAML 1.2 Semantic-Discovery frontmatter block delimited by `---` lines containing `title`, `description` (60 to 140 neutral retrieval words), `topics` (3 to 12 concrete lowercase kebab-case terms), `use_when` (2 to 6 neutral task conditions), and conditional `not_for` (1 to 5 grounded exclusions, omitted when empty), followed by the GFM H1 title. Exclude internal IDs, version strings, hashes, filesystem paths, build metadata, and unresolved template delimiters from frontmatter values. Relationship semantics belong in the body. Governing source: Collection Semantic-Discovery Frontmatter contract.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. Omit it for internal documents unless a specific project policy requires explicit negative attestation. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Define sources and edge semantics before the relationship view; report missing relationships and change effects after it. Heading wording may vary.
- **Presentation:** Use compact structured matrices or item-centered tables sized to the controlled scope without duplicating endpoint wording. Required roles may share sections while keeping relationship semantics, source editions, coverage accounting, and missing-link findings directly retrievable.

| Projection | Title and metadata ownership | Syntax and source authority |
| --- | --- | --- |
| Requirements traceability matrix (standalone) | Begin with the mandatory 5-key Semantic-Discovery YAML frontmatter followed by one scope-specific H1. Control scope, as-of point, state, ownership, and authority references remain body content, inheriting corpus-level changelog/VCS versioning, declared default maintainer, and external specification provenance when governed in a unified operational corpus. | Use GFM prose, tables, or structured lists bound to controlling masters and inspected snapshots. Referenced systems, trackers, or baselines remain authoritative for their native records; changes to controlling sources require reconciliation rather than silent overwrite. |

| Section role | Status and inclusion condition | Content obligation |
| --- | --- | --- |
| Scope, sources, and relationship rules | Required | Identify the included entity kinds and controlled sources with editions or as-of point, boundary and exclusions, and baseline or effectivity assumptions. Define each allowed relationship type, its source and target kinds, and its direction. State which of those relationships the project requires. If that rule is not established, say so rather than inventing it. State how reverse navigation is obtained from one stored edge. State that an edge has no verification, validation, or acceptance state. |
| Directed relationships | Required | Record each supported unique source–relationship–target edge with resolvable endpoint references, applicable editions, and a concise semantic basis. Distinguish a link to an activity that has not been executed from a link to an existing evidence record. If there are no valid edges, state that fact and its scope. |
| Missing relationships and change impact | Required | Review the required incoming and outgoing relationships for each in-scope entity, including entities that have no edge row. Report missing relationships, stale or conflicting endpoints, and disputed edges, with action and owner if assigned. Identify edges affected by a changed source or baseline. A statement that the required relationships are present is only a statement about links. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
| --- | --- | --- |
| Endpoint | Two per edge: one source and one target. | Cite the entity kind, stable ID, authoritative record, edition or applicable configuration, and locator. Allowed kinds, when in scope, are a business or mission need, business requirement, stakeholder requirement, system requirement, software requirement, interface requirement, interface-control definition, interface-registry identity, design element, configuration item, decision, assessment activity, and evidence record. Do not copy the authoritative wording or controlled parameters. A missing endpoint is not a valid edge. |
| Relationship type | One declared type per edge. | Define the verb, direction, and valid endpoint kinds. A derived item may use the project's derivation verb, such as `derives-from`, toward a source need or requirement. An element may `satisfy` or `realize` a requirement only as design or allocation, not as a verified or validated result. `constrains` and `rationale-for` cite a real constraint or decision relationship. Any activity or evidence verb is a pointer to that record. Do not label the edge `gap`, `partial`, `planned`, `verified`, `not-verified`, `accepted`, `pass`, `fail`, `inconclusive`, `not-run`, `met`, or `not-met`. |
| Directed edge | Zero or more unique assertions; one row per distinct source–type–target relationship. | Give a stable link ID when links are controlled individually, plus endpoint references and the inspected basis. Do not create a separately maintained mirror row for reverse lookup, and do not count duplicate links as extra relationships. The edge has no coverage field and no acceptance field. |
| Link basis | One meaningful basis per asserted edge. | Explain which part of the source the target addresses, and cite the relevant record or review. An identifier match, shared keyword, or title alone does not establish the relationship. Describe the semantic correspondence supported by the inspected endpoints; do not infer that the addressed obligation was assessed. |
| Activity or evidence endpoint | Conditional when activities or evidence are in scope. | Say whether the activity has not been executed, or cite an evidence record that exists. Keep assessment results out of the edge, and do not call the link `not-run`. |
| Relationship rule and finding | One coherent rule set and zero or more findings. | State which layers require parents, allocations, or other links, with justified exceptions. Check both outgoing and incoming views, edition compatibility, and entities that have no edge row. A missing required relationship is a finding naming the affected entity and required link. |

Use a table or graph-backed list with source ID and kind, relationship and direction, target ID and kind, editions, and basis. A diagram MAY help readers see a small relationship network, but the inspectable edge list and missing-relationship findings remain authoritative. A requirement-centered summary MAY show both incoming and outgoing links from that single edge list. Do not duplicate need, requirement, or interface statements, and do not use a link-status color as a result.

## Quality criteria

- Every edge has real compatible endpoints, an unambiguous direction, and a basis that matches the inspected content on both sides.
- Bidirectional navigation is possible without contradictory mirror rows. Duplicate links and stale source editions are visible.
- The relationship review includes entities with no rows. It does not treat a link, an identifier match, or a count of edges as verification, validation, or acceptance.
- Need, requirement, interface-requirement, interface-control, and interface-registry endpoints stay distinct. `satisfy` and `realize` do not mean `verified` or `met`.
- Missing relationships, exclusions, and change effects name the affected entities and a practical resolution route. They do not report that traceability, conformance, or acceptance is complete.
