# Configuration baseline record specification

## Identity and selection

- **Specification ID:** `CONFIGURATION-BASELINE@core`.
- **Purpose:** Identify one actually established, controlled configuration snapshot and the exact item revisions and effectivity it fixes.
- **Intended readers:** Configuration managers, item owners, change and release authorities, builders, operators, and reviewers who need to know the controlled configuration.
- **Decision or action supported:** Reproduce, compare with, change, or release the exact controlled definition for its established effectivity.
- **Use when:** A functional, allocated, product, software, infrastructure, operational, or document configuration has actually been placed under baseline control.
- **Scope boundaries:** Identify the established controlled definition and its effectivity. Claims about a deployed instance's conformity require evidence for that instance.

## Authoring inputs and unresolved facts

Inspect the actual baseline-establishment decision and explicit project configuration-control conditions; baseline identity, kind, revision, boundary, and effectivity; the item set fixed by that decision; each item's identity, exact revision or serial/effectivity, and controlled locator; integrity or origin evidence appropriate to its form; supplied project requirements, interface definitions, and design decisions that constrain the configuration, and approved effective deviations; any prior baselines; the comparison or change that produced this snapshot; and any actual release relationship or restriction. Check whether different units or environments use different established item revisions and how their effectivities are partitioned.

If establishment has not occurred, do not title a proposed collection an actual baseline. If the establishment decision or any material item revision is unknown, state the gap and do not claim an exact established snapshot for the affected scope. Identify the resolution action and assigned owner if one exists. Cite actual item identities, approval decisions, changes, and releases with their revisions and locators when they establish a fact about this snapshot. Do not invent an item, digest, approval, build recipe, or release constraint to fill a gap.

## Finished-document contract

- **Title:** Identify the bounded configuration and call the document a configuration baseline record.
- **Frontmatter:** None. Begin with the GFM title. Baseline identity, effectivity, and control state belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State the snapshot identity and authority before the item set; put relationships, integrity limits, and supersession after the item set. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Baseline identity and control | Required | State one baseline ID and revision, kind, controlled boundary, establishment date or event, effective units/environments/period, internal controlling role and its decision rights, explicit project change-control conditions, and current baseline state. Identify the actual decision that established it; if the project requires approval, state that condition and show the actual approval's exact scope. |
| Controlled item set | Required | Give the complete controlled set for the stated boundary: item identity, name or role, exact revision or serial/effectivity, controlled locator, and integrity or provenance basis appropriate to the item. Explain an intentionally empty snapshot only when authority actually established one. |
| Configuration constraints and deviations | Conditional when supplied project requirements, interface definitions, design decisions, or deviations determine the baseline's meaning | State the concrete constraints and identify the project records and revisions that established them, and any approved, effective deviations or waivers. State which item or scope each constrains or changes. Do not list a requested or expired deviation as effective. |
| Integrity and relationships | Required | Describe how the snapshot was frozen, retrieved, compared, and protected against silent changes. Identify every direct predecessor baseline when one exists, with the change or comparison basis and no supersession cycle. State known gaps or integrity limits. |
| Use and release relationship | Conditional when this baseline has use restrictions, release implications, or a real release reference | State restrictions, known exceptions, and the relationship to any actually released package or affected units. A release is cited only when it happened; baseline establishment alone does not say that distribution occurred. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Baseline identity | One stable baseline identity with an exact snapshot revision. | A changed member set, member revision, or effectivity creates a new controlled snapshot or revision under project rules; do not silently rewrite the established set. |
| Baseline kind and boundary | One defined configuration purpose and scope. | Use the project's kind, such as functional, allocated, product, software, infrastructure, operational, or document. The kind does not impose software-only fields on physical or conceptual items. |
| Establishment and state | One actual establishment event and current state. | Identify deciding authority, date, source, and effectivity. `Established`, `superseded`, or `retired` requires actual control history. `Proposed` is not an established baseline. `Released` is a separate release event unless the project expressly defines a baseline release state and records that event. |
| Controlled item | One or more per ordinary baseline; zero only for a deliberately authorized empty snapshot. | For each effective slice, a configuration-item identity resolves to one exact revision. If different revisions apply to different units or environments, state disjoint effectivities. Do not allow duplicate rows to hide competing versions. |
| Item revision and locator | One exact immutable revision or serial/effectivity and one controlled retrieval or evidence locator per item. | A label such as `latest` is insufficient. A locator may be a repository revision, document vault entry, drawing record, physical-item record, or equivalent. Do not put credentials in it. |
| Integrity basis | One suitable basis per item. | For controlled bytes, give a digest with its algorithm when available or required. For physical or conceptual items, use serial, drawing/configuration revision, inspection or controlled evidence as appropriate. A hash is not universally required and does not itself prove origin or approval. |
| Configuration constraint | Zero or more actual project requirements, interface definitions, or design decisions constraining the item set. | State the relevant required condition, affected item or scope, and project record identity, revision, entry, and locator. Include only constraints that define this configuration. |
| Deviation or waiver | Zero or more approved, effective departures. | Identify the obligation, affected item and effectivity, actual decision, and expiry or limits. A pending request is not an effective deviation. |
| Prior baseline | Zero or more direct predecessors in the controlled lineage; one is usual for a linear revision. | Identify each predecessor's exact revision, or state that this is the initial baseline. Do not create a cycle or erase a prior snapshot. Branches and merges require explicit lineage and effectivity. |
| Reproduction or comparison | One account of how this snapshot can be reconstructed or checked. | A build/assembly recipe is conditional on that being the way the item is produced. For an irreproducible physical state, explain the controlled observation or compensating evidence. State untested reproducibility as untested. |
| Release relationship | Zero or more actual releases using this baseline. | Identify the actual release event, exact package or units, baseline revision used, and any restricted scope. State distribution or deployment facts only when supported by evidence for that event. |

Use an item table with columns for identity, revision, effectivity, locator, and integrity basis. Add a short lineage table when more than one predecessor or branch matters. A diagram may clarify assemblies or allocation but does not replace the exact member set. Do not add filler items, a generic document-control block, or a forced SHA-256 field for non-byte items.

## Quality criteria

- The baseline identifies one frozen, controlled snapshot and an actual establishment decision. It does not present a proposed collection as established.
- Every item revision and effectivity is unambiguous, including unit or environment variants. The stated set can be retrieved or its gaps are explicit.
- Integrity evidence fits the item form. A physical item is not assigned a fabricated byte digest, and a byte digest is not treated as provenance by itself.
- Prior-baseline and change relationships preserve history. Applicable deviations have real decisions and have not expired for the stated scope.
- Claims about item membership and revisions match the established controlled set; claims about actual use are bounded by the identified event, units, and evidence.
