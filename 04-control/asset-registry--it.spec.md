# IT asset registry specification

## Identity and selection

- **Specification ID:** `ASSET-REGISTRY@it`.
- **Purpose:** Maintain the governed identity, classification, ownership, custody, and lifecycle state of managed assets, together with the authority for that identity.
- **Intended readers:** Asset owners, custodians, configuration managers, and the inventory, maintenance, financial, or retirement processes that consume asset identity.
- **Decision or action supported:** Determine which assets the organization governs, who owns and holds each one, which lifecycle state has been set, and which configuration items are related without treating those identities as the same object.
- **Use when:** Managed assets need controlled identity, classification, ownership, custody, and lifecycle state.

## Authoring inputs and unresolved facts

Inspect the organizational boundary or owning entity, the asset classes actually governed, and whether any non-IT class is intentionally included. Inspect the authority that allocates identifiers and approves lifecycle changes, the master system for those identities, and the acquisition, transfer, storage, retirement, and disposal decisions that have occurred. Relate an asset to a configuration item only when that item identifier exists.

If an owner, custodian, location context, title, or lifecycle decision is unknown, keep the asset visible and unresolved. Do not invent a purchase, transfer, or disposal, and do not advance the lifecycle because an inventory saw the asset. If the scope is defined and no asset has been registered, say so. Populate consumer and relationship fields only with established process names and real item identifiers.

## Finished-document contract

- **Title:** Identify the organizational boundary and name the document as its IT asset registry.
- **Frontmatter:** None. Begin with the GFM title. Asset classes, authority, and lifecycle state belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State scope, classes, and authority before the asset index; place reconciliation exceptions after the assets. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Scope, classification, and authority | Required | Identify the organizational boundary, the governed asset classes and the meaning of each class, and any included non-IT assets. Name the identifier authority, the lifecycle decision authority, and the master system. State how acquisition, transfer, and disposal update the registry and how an inventory observation is reconciled without becoming a lifecycle transition by itself. |
| Asset index | Required | Include every asset registered in the scope, or an explicit assessed-empty statement. For each asset, give its immutable identity, class, owner, custody context, one lifecycle state supported by the actual authority, and configuration-item or consumer relationships that exist. |
| Reconciliation and open items | Required | Identify duplicate identities, assets seen in inventory but not registered, registered assets with no supporting decision, and conflicting custody or ownership. State the consequence and route, or state that the assessed scope showed none. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Asset identity | One governed asset; zero only when the scope was assessed and no asset is registered. | Use an immutable identifier and do not reuse it after transfer, retirement, or disposal. Keep it distinct from identifiers for related configuration items and individual observations. |
| Asset class | One class defined in the scope section. | Do not introduce a silent class in an entry. A data-only or non-IT asset may be registered only when the scope includes it. |
| Owner | One accountable role when assigned. | The owner is accountable for the asset. An unassigned owner remains a gap. Do not substitute the custodian, an inventory contact, or a financial owner unless that person or role is the assigned asset owner. |
| Custody | The custodian and the organizational or location context this registry governs. | State assigned custody and location context; a discovery observation alone does not establish that assignment. If custody or location context is unknown, leave it unresolved. When physical location and custodian differ, state both. |
| Lifecycle state | Exactly one of `planned`, `acquired`, `in-service`, `stored`, `transferred`, `retired`, or `disposed`. | `planned` is not yet acquired. `acquired` has title, receipt, or equivalent registration evidence and is not automatically in service. `in-service` and `stored` require the decision that placed or held the asset. Record an operating authorization only when actually granted; an `in-service` decision alone does not establish that permission. Use `transferred` only while the asset has moved and has not entered a later state; record the releasing and receiving custody. Once a later state applies, record that state and keep the transfer decision in the authority history. `retired` means withdrawn from service but still existing. `disposed` means the stated disposition occurred. Only the actual registration or transition decision and its supporting evidence establish a state. |
| Authority source | The decision or title evidence for the current state. | For `planned`, the registering decision is enough and title need not be invented. For `acquired`, `transferred`, `retired`, and `disposed`, cite the evidence that matches that state. A missing source leaves the state unresolved rather than implied by the row. |
| Configuration-item references | Zero or more identifiers of real configuration items. | For each link, give the related item's own identifier; retain asset identity and lifecycle history separately from item revisions. Record configuration-control status only when it is established for the related item. |
| Consumers | Required to address for each asset. | Name the inventory, maintenance, financial, custody, or retirement processes that actually use the identity, or state that none were identified. |

Use one row or short block per asset, with labeled fields for identity, class, owner, custody, state, authority, related configuration items, and consumers. Do not add a blank asset or substitute unclassified discovery data for registered asset entries.

## Quality criteria

- Each lifecycle state is supported by the kind of decision or evidence that state requires, and a discovery record cannot silently change it.
- Owner and custodian remain distinct unless one assigned role truly holds both responsibilities.
- Asset, configuration-item, and inventory identifiers are not treated as interchangeable.
- Retired and disposed assets are not collapsed, and disposed is used only after the disposition occurred.
