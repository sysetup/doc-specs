# Ordered product backlog specification

## Identity and selection

- **Specification ID:** `PRODUCT-BACKLOG@core`.
- **Purpose:** Maintain an emergent, ordered inventory of possible product work and its refinement basis.
- **Intended readers:** Product owners, developers, designers, stakeholders, and those coordinating product delivery.
- **Decision or action supported:** Order and refine possible work against the product goal and select work without confusing it with approved requirements.
- **Use when:** A product or capability uses a backlog to organize evolving work.
- **Scope boundaries:** Control product-work identity, order, refinement, dependencies, and work disposition; exclude authoritative requirement wording, iteration execution plans, action closure, and delivery acceptance.

## Authoring inputs and unresolved facts

Obtain the product boundary and current goal or gap, actual work items and sources, ordering and update authority, controlling board or record and inspected snapshot, native work-state meanings and transition rules, any selected normalization and its mapping edition, refinement and completion conventions, dependency masters, mission-dependent sizing attributes and their estimation bases, requirement and acceptance locators, and actual selection, commitment, completion, or removal evidence.

Expose unknown goal, value, order, native state, mapping, sizing, dependency, owner, or completion basis with its consequence, resolving action, and assigned owner if known. Preserve an observed unmapped native value; distinguish that from an unknown value or unknown mapping. Do not default missing quantities to zero, infer normalized completion from a label, or treat selection as commitment or acceptance. Missing information blocks only the dependent planning or completion claim under the declared rules; a draft inventory may retain visible gaps. A changed source snapshot or mapping requires reassessment. Do not invent work, requirements, authority, acceptance, or delivery evidence.

## Finished-document contract

- **Title:** Identify the product and name its ordered product backlog; a standalone document owns its H1, while a native board view follows the declared host title rule.
- **Frontmatter:** None. Omit YAML frontmatter on both surfaces. Begin standalone GFM with its H1; a native view follows the host title rule. Put product scope, as-of basis, and client context in the body, with host-owned facts referenced rather than copied as a second master. Governing source: This type's body and projection policy; no external metadata schema is prescribed.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State product goal, controlling source, state and sizing rules before the ordered inventory; follow it with selection, completion, disposition, refinement gaps, and upkeep. Heading wording may vary.
- **Presentation:** Use a compact control account and an ordered table, item blocks, or linked board view sized to the actual inventory. Required roles may share paragraphs or sections; native states, mapping limits, gaps, and source locators must remain retrievable without duplicate editable masters.

| Projection | Title and metadata ownership | Syntax and source authority |
|---|---|---|
| Standalone GFM (standalone) | The document supplies one product-backlog H1. The body states scope, as-of point, source snapshot, and client context. | Use GFM prose, ordered rows, or item blocks. Name the controlling record and inspected edition or immutable snapshot. A read-only export preserves identities, order, and native values; source changes require reconciliation before using its derived planning or completion account. |
| Native board view (native) | The identified host owns the board title; do not add a redundant H1 where that surface excludes it. The host owns its item identities, order, native states, and current snapshot; body context identifies their inspected locators and ownership. | Use the selected board surface's actual syntax and inspected edition; this contract prescribes no provider schema or machine export. The board remains controlling. State native transition rules and any separately chosen normalization, mapping edition, conditions, and information loss; unknown or unmapped states remain visible and cannot authorize a derived transition. |

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Product goal and control rules | Required | Identify product scope, goal and its decision state, as-of point, ordering and update roles, authoritative board or record and snapshot, native work-state and transition meanings, refinement and completion rules, exclusions, and client or receiving-party element. State whether normalization and sizing are used, which mission requires them, and their governing rules or gaps. |
| Ordered work inventory | Required | List each item with stable identity, sourced problem or expected value, relative order and rationale for active work, refinement readiness or gaps, actual native state or state gap, dependencies, and applicable sizing attributes with units and basis or explicit gaps. Preserve native values alongside any derived normalized view. Link actual requirements and acceptance criteria without creating a second master. State an assessed-empty inventory explicitly. |
| Selection, completion, and disposition | Required | Record actual selection, progress, completion, reopening, and removal under the declared native rules and evidence; do not force native values into five states. When normalization is selected, show its mapping and mapped, unmapped, or unknown disposition independently. Distinguish selection from delivery commitment and acceptance, and completion claims from completion supported by the declared basis. Preserve prior completion evidence and removed-item reasons; order and estimates do not create promises. |
| Refinement and upkeep | Required | Expose unanswered questions, missing criteria or required sizing, unknown or unmapped states, stale snapshots or mappings, conflicting order, self-dependencies, and cycles with their consequence and resolving route. State assessed absence when none were found. Identify update roles or gaps and triggers for changed goals, native rules, mapping, evidence, or priority. Preserve history and relationships to downstream masters. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Product goal | Exactly one current goal or explicit goal gap in Product goal and control rules. | Identify proposed or established state; a desired outcome is not an achieved result. |
| Backlog item | Zero or more possible-work items in Ordered work inventory. | Each has an immutable identity and sourced problem or value; assessed-empty is explicit and requirements or feedback keep separate masters. |
| Order and refinement | One order position and one refinement account per active item in Ordered work inventory. | Define ties and active-item membership using the actual rules. Preserve known prior order for disposed items when relevant. Readiness identifies criteria and dependency knowledge or gaps; it is not assurance or acceptance. |
| Sizing attribute | Zero or more mission-selected dimensions per item in Ordered work inventory, with zero or one current estimate per dimension. | Identify dimension, value or gap, unit, method or source, assumptions, and as-of basis. Distinguish relative size, elapsed time, consumed effort, and remaining effort; do not add, substitute, or default unlike or unknown quantities. Required sizing gaps block only decisions needing those quantities. |
| Native work state | Exactly one observed native value or explicit state gap per item in Ordered work inventory and Selection, completion, and disposition. | Preserve the controlling source's vocabulary, meanings, and transition rules, including blocked or review states when present. A native completion label without the established completion basis is an unresolved claim; removal and reopening retain reason and prior evidence. |
| Normalization and mapping | Zero or one selected normalized vocabulary and versioned mapping account in Product goal and control rules and Selection, completion, and disposition; one mapping disposition per item when selected. | Normalization is optional and derived. Declare each native-to-normalized mapping, condition and information loss; many-to-one mappings preserve the native value. A known unsupported value is unmapped, while an unknown value or insufficient mapping basis is unknown; neither defaults to candidate, completed, or any other normalized state. Derived changes follow reassessed source facts, not independent board mutations. |
| Selection, commitment, and completion basis | One disposition account per item in Selection, completion, and disposition. | Actual iteration or release selection requires its source; absent selection is stated. Delivery commitment and acceptance require their separate actual decisions and never follow from order, sizing, selection, a mapping, or completion. Supported completion requires the declared criterion and evidence; missing evidence blocks that claim. |
| Dependency and master link | Zero or more real relationships per item in Ordered work inventory and Refinement and upkeep. | Identify direction and actual record or explicit gap. Self-dependencies and cycles are planning defects; unknown, blocked, or unmapped conditions cannot silently become schedulable work. |

Use an ordered table, compact item blocks, or a linked board view with a controlling source and inspected snapshot. Show native state and optional derived state in distinct fields with accessible mapping locators. Put additional sizing dimensions together only when the mission uses them. Keep this view read-only when a board controls the work. Apply Scrum-specific commitment and completion terminology only when that approach is actually selected; iteration execution plans and decision masters retain their authority.

## Quality criteria

- A reader can locate product goal, authority, source snapshot, native rules, sizing applicability, and update responsibility or explicit gaps.
- A reader can retrieve each item's identity, value, order, refinement basis, native state, source and dependencies, or an explicit assessed-empty inventory.
- Optional normalization preserves native values, declares mapping conditions and loss, and exposes unmapped and unknown separately; no missing mapping manufactures a state or transition.
- Mission-selected sizing records dimension, quantity or gap, unit, source and as-of basis; missing estimates do not become zero and unlike quantities are not combined.
- Selection, supported completion, commitment, acceptance, removal and reopening are distinguishable by their actual rules and evidence; missing completion basis prevents a supported-completion claim.
- Source changes, unresolved refinement, state and sizing gaps, dependency cycles and self-links have visible consequences and resolving routes without duplicate masters.
