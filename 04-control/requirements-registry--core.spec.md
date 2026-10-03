# Requirements registry specification

## Identity and selection

- **Specification ID:** `REQUIREMENTS-REGISTRY@core`.
- **Purpose:** Maintain a current index of requirement identity, authoritative source, content state, and ownership across controlled requirement sets without creating a second statement master.
- **Intended readers:** Requirements stewards, change authorities, requirement owners, and people reconciling source sets or consuming their IDs.
- **Decision or action supported:** Locate the controlling requirement, identify its applicable edition and owner, detect source or state conflicts, and route changes to the proper authority.
- **Use when:** Requirements in multiple controlled specifications need one cross-source identity and status view.
- **Scope boundaries:** Index controlled requirement obligations and their identity, source, content state, and ownership. Exclude editable requirement statements, need-only labels, directed trace relationships, assessment results, and baseline approval decisions.

## Authoring inputs and unresolved facts

Inspect the in-scope requirement specifications and their exact editions, requirement IDs and locators, applicable baselines or effectivity, requirement layers, content states, actual ownership assignments, change decisions, and the project's identifier and state conventions. Establish the authoritative source for each statement and the role that maintains the registry. Obtain consumer references only where they exist. Compare source revisions with any prior registry entries before calling the index current.

If a source, edition, identifier, owner, state, or change decision is unknown, record the affected item, the gap, its effect on use of the index, and the resolving action with an actual owner if assigned. A requirement found in two purported masters or with conflicting states remains disputed until the controlling authority resolves it. Do not infer approval from a source document's title or a status copied from an older edition. If no controlled requirements are found in the assessed scope, state the inspected scope and limitation; do not create a filler entry or claim that a usable populated registry exists.

## Finished-document contract

- **Title:** Identify the project or system boundary and name the document as its requirements registry.
- **Frontmatter:** None. Begin with the GFM title. Source authority, scope, and state are substantive body content.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State scope and source rules before the index; place reconciliation findings and pending changes after the entries. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Scope, authority, and source rules | Required | Identify the indexed project or system boundary, requirement layers and source sets, edition or as-of point, ID namespace and uniqueness rule, source-of-truth rule, registry steward, content-state vocabulary, and how changes or source revisions reach the registry. State exclusions and effectivity where they change interpretation. |
| Requirement index | Required | Give one entry for every in-scope requirement found in the inspected authoritative sets, or an explicit assessed-empty/gap statement. Index each requirement by stable source ID, exact source locator and edition, layer, current content state, and accountable owner or visible assignment gap. Link to real consumer views or change decisions only when useful and established. Do not independently maintain editable requirement wording. |
| Reconciliation and open items | Required | State how the index was compared with its sources, identify missing, duplicate, superseded, conflicting, or stale entries, and give their consequence and resolution route. Distinguish a requirement content decision from implementation, verification, validation, and acceptance. Do not record `pass`, `fail`, `inconclusive`, or `not-run`. State when and how the next reconciliation occurs. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Indexed source set | Two or more controlled requirement specifications in normal use of this type. | Identify each by title or ID, edition, accessible locator, and applicable baseline or effectivity. Index only statements established as requirement obligations; exclude need-only entries. A hash MAY bind a digital snapshot when available; it is not universally required. |
| Requirement entry | One per in-scope authoritative requirement; zero only with an explicit assessed-empty or unresolved-source explanation. | Use the requirement's stable source ID as the registry key. A separate registry row ID is optional and MUST NOT obscure or replace that source ID. Prevent duplicate keys within the declared namespace. |
| Source and layer | One authoritative requirement document, exact requirement locator, edition, and declared level for each entry. | The locator must let a reader recover the actual statement. Use the source's declared level, such as business, stakeholder, system, software, or interface. Identify source conflicts rather than selecting a master by guesswork. Do not copy the statement as a second editable obligation, and do not index a need label as a requirement. |
| Content state | One current state per entry, or an explicit unresolved state. | Use the source specification's content-state vocabulary, such as proposed, agreed, approved, superseded, or rejected, and cite an actual decision for approval or disposition. Do not translate stakeholder agreement into technical approval or into a validation result. This state concerns requirement content, not product conformance. Do not store `pass`, `fail`, `inconclusive`, `not-run`, `verified`, or `validated`. |
| Accountable owner | One assigned person or role per entry when established; otherwise a visible assignment gap. | Distinguish the owner of the requirement from the registry steward, implementation performer, verification performer, and approval authority. |
| Change and consumer references | Zero or more real links per entry. | Cite an actual change decision when it explains a current or superseded state. Use consumer links to locate existing uses or assessments of the requirement. Store the locator rather than a directed trace relationship or assessment result. Keep missing links visible. |
| Reconciliation finding | Zero or more specific discrepancies; one stated reconciliation basis for the index as a whole. | Record affected IDs, inspected source editions, discrepancy, impact, and resolving action. A clean comparison is a bounded finding, not proof of project-wide completeness beyond the inspected scope. |

Use a compact table with requirement ID, source and locator, edition, layer, content state, and owner. Add change or consumer columns only when they help users locate real records; use short notes for conflicts or revision history that would overload cells. Do not add a generic approval block, copied requirement statements, or empty rows.

## Quality criteria

- Every listed ID resolves to one inspected authoritative statement and applicable edition; duplicate or conflicting masters remain visible as issues.
- The index covers the declared source scope and has an explicit reconciliation basis; omitted, stale, and uncertain entries cannot silently appear current.
- Status and ownership answer the registry's stated purpose, including visible gaps where those facts have not been established.
- Each entry states the requirement's content state, with implementation progress and assessment or acceptance results excluded from that field. No entry assigns `pass`, `fail`, `inconclusive`, or `not-run`.
- A change to an authoritative statement or baseline has a usable route to update or invalidate affected entries without editing a duplicate statement here.
