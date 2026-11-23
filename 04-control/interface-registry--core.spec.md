---
title: "Interface registry specification"
description: >-
  Defines the authoring contract for interface registries maintaining one controlled inventory of interface identities, participating endpoints and owners, criticality classifications, registration states, pointers to authoritative interface requirement or control records, known consumers, change relationships, and open discrepancies. Keeps the registry strictly as metadata and authoritative pointers while excluding duplicated requirement wording, controlled protocol parameters, directed traceability graphs, and verification execution results.
topics:
  - "control-records"
  - "architecture-and-design"
  - "configuration-management"
  - "interface-registry"
  - "interface-inventory"
  - "endpoint-ownership"
  - "interface-criticality"
  - "boundary-catalog"
use_when:
  - "A system or program with multiple internal and external interfaces needs one controlled index of interface identities and owners."
  - "An interface steward is tracking registration status, criticality, known consumers, discrepancies, and pointers to controlling documents."
  - "An engineer needs to locate which parties own an interface and where its authoritative specification resides."
not_for:
  - "Stating detailed boundary obligations or controlled protocol parameters, which belong in interface requirements or interface control documents."
  - "Mapping end-to-end bidirectional trace edges across requirements, design, and tests, which belongs in a requirements traceability matrix."
  - "Documenting API syntax and CLI lookup tables for consumers, which belongs in a technical lookup reference."
---

# Interface registry specification

## Identity and selection

- **Specification ID:** `INTERFACE-REGISTRY@core`.
- **Purpose:** Maintain a controlled index of interface identities, participating parties, owners, registration status, criticality, definition references, and change relationships.
- **Intended readers:** Interface stewards, parties on each side of a boundary, integration and verification planners, configuration managers, and suppliers who need to locate interfaces and their definition records.
- **Decision or action supported:** Determine which interfaces are in scope, who owns each side, where a definition is controlled, and which consumers or changes are identified.
- **Use when:** Interfaces need one controlled inventory of identity and pointers to their definition records.
- **Scope boundaries:** Store registration metadata and pointers to interface definitions. Exclude requirement wording, controlled realization parameters, traceability edges, and execution or verification results.

## Authoring inputs and unresolved facts

Inspect the system or product boundary, the interface categories and registration criteria actually in use, the identifier rules, and the role that stewards the index. For each candidate interface, inspect the known endpoints and their owners, any real requirements or control records and their editions, the content or agreement state those records actually state, baseline relationships, and the integration, verification, operations, or supplier activities that consume the interface.

If an endpoint, owner, definition, agreement, criticality, or change relationship is unknown, keep the interface visible, state the gap and its effect on integration or change, and name the resolving action and actual owner if assigned. Do not invent a party, a second interface identifier, an agreement, a definition reference, a trace edge, or a verification result. If the assessed scope contains no interface that meets the registration criteria, say so. A blank row is not an interface. Do not assign `pass`, `fail`, `inconclusive`, `not-run`, or `verified`.

## Finished-document contract

- **Title:** Identify the boundary and name the document as its interface registry.
- **Frontmatter:** Required. Begin with a YAML 1.2 Semantic-Discovery frontmatter block delimited by `---` lines containing `title`, `description` (60 to 140 neutral retrieval words), `topics` (3 to 12 concrete lowercase kebab-case terms), `use_when` (2 to 6 neutral task conditions), and conditional `not_for` (1 to 5 grounded exclusions, omitted when empty), followed by the GFM H1 title. Exclude internal IDs, version strings, hashes, filesystem paths, build metadata, and unresolved template delimiters from frontmatter values. Scope, authority, and status belong in the body. Governing source: Collection Semantic-Discovery Frontmatter contract.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. Omit it for internal documents unless a specific project policy requires explicit negative attestation. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State registration rules before the index; place unresolved identities, definitions, and change conflicts after the entries. Heading wording may vary.
- **Presentation:** Use compact registers, structured item tables, or grouped lists sized to the controlled inventory without placeholder rows. Required roles may share sections while keeping stable identities, owners, states, source locators, and reconciliation gaps directly retrievable.

| Projection | Title and metadata ownership | Syntax and source authority |
| --- | --- | --- |
| Interface registry (standalone) | Begin with the mandatory 5-key Semantic-Discovery YAML frontmatter followed by one scope-specific H1. Control scope, as-of point, state, ownership, and authority references remain body content, inheriting corpus-level changelog/VCS versioning, declared default maintainer, and external specification provenance when governed in a unified operational corpus. | Use GFM prose, tables, or structured lists bound to controlling masters and inspected snapshots. Referenced systems, trackers, or baselines remain authoritative for their native records; changes to controlling sources require reconciliation rather than silent overwrite. |

| Section role | Status and inclusion condition | Content obligation |
| --- | --- | --- |
| Registration scope and authority | Required | Identify the boundary, interface categories, registration and exclusion criteria, steward, identifier rules, and who may change a registration or a cross-party relationship recorded in this index. State how updates are triggered and how the index stays aligned with baselines and with design or integration work. State the criticality criteria before any ranked criticality is used. State that registration status, interface-requirement content state, and realization agreement are different facts. |
| Interface index | Required | Include every interface that meets the criteria, or an explicit assessed-empty statement. For each interface, give one immutable identifier, the known endpoints and side ownership, criticality, registration status and its dated source, and the definition references that actually exist. Where a referenced record states a content or agreement state, cite that state separately for the requirements record and the control record. State the consumers and change relationships, or state that none were identified. |
| Discrepancies and open items | Required | Identify missing endpoints, duplicate identities, definitions that are absent or in conflict, a registration status not supported by a decision, and unresolved change impact. State the consequence and the resolving route, or state that the assessed scope showed none of these gaps. Do not resolve a conflict by copying requirement wording or realization parameters into the index. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
| --- | --- | --- |
| Interface identifier | One stable identifier per registered interface. | Keep it immutable within this index and do not reuse it for a different interface. If an established project interface identity already exists, use that identity. A local row key is allowed only when the existing interface identity cannot itself identify the row, and it MUST NOT be presented as a second interface. |
| Endpoints and ownership | At least the sides known for that interface. | Name each participating party or endpoint and which role owns that side's inputs to the definition. An unknown side remains unresolved. Naming an owner does not state the obligation or the realization. Do not substitute a person's name for decision authority. |
| Criticality | One value per interface, required to address. | Use `unassessed` until the stated project criteria have been applied. A ranked value requires those criteria and an actual assessment. Do not treat criticality as agreement, requirement approval, or verification. |
| Registration status | One current status per interface, with its dated source. | Use the project's vocabulary for whether this identity is active in the index, superseded by another identity, or withdrawn. A status that means superseded or withdrawn requires the corresponding decision or source. This status does not mean the interface requirements are approved and does not mean the realization is agreed. An identifier for a requirements or control document does not establish either agreement. |
| Definition references | Zero or more references per interface. | Cite each established project interface definition with its record identity, edition, and locator. If a cited record states a content state or an agreement state, cite that state and its dated source with the record it belongs to. Do not merge a requirements state and a realization state into one value. Do not copy wording or controlled parameters. If none exists, say the definition is not established. |
| Consumers | Required to address for each interface. | Name the integration, verification, operations, or supplier activities that actually depend on it, or state that none were identified. Record activity identities and their dependency on the interface, without execution results. Do not create those activities to fill the index. |
| Change relationship | Required to address for each interface. | Cite a real change, baseline, or compatibility decision and say how it affects the interface, or state that no such relationship was identified. The index does not authorize the change and does not store a requirements-traceability edge. |

Use one row or short block per interface, with labeled fields for identifier, endpoints and ownership, criticality, registration status and source, definition references, consumers, and change relationships. Use metadata and locators in entries; omit drawings and parameter tables. Do not add a blank interface to make the list look populated.

## Quality criteria

- Every registered interface has a distinct identity, and its entries contain registration metadata and definition locators.
- Registration status, interface-requirement content state, and realization agreement remain separate and, when claimed, trace to a dated source.
- Ranked criticality is used only under the criteria stated in the same document.
- Missing endpoints, missing definitions, and unresolved change impact stay visible.
- The registry stores no requirement wording, no controlled parameters, no trace edge, and no `pass`, `fail`, `inconclusive`, `not-run`, or `verified` result.
