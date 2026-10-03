# Configuration item register specification

## Identity and selection

- **Specification ID:** `CONFIGURATION-ITEM-REGISTER@core`.
- **Purpose:** Account for the identity, ownership, configuration-control state, controlled revisions, and relationships of real candidate, controlled, and retained former configuration items.
- **Intended readers:** Configuration managers, item owners, change authorities, and consumers who must locate a controlled item and determine its actual control state and revision effectivity.
- **Decision or action supported:** Determine which items are controlled, who owns each one, which revisions are under control and for what effectivity, and how an item relates to its parents or to a real baseline.
- **Use when:** Configuration items need controlled status accounting of identity and control state.
- **Scope boundaries:** Cover candidate, controlled, and retained former items within the stated product or service boundary, with each item's identity, control state, revisions, and actual relationships.

## Authoring inputs and unresolved facts

Inspect the product or service boundary, the criteria and authority for selecting and decontrolling configuration items, the identifier rules, and the system that holds each item's controlled definition. For each real candidate, controlled item, or retained former item, inspect its class, owner, control decision, revisions actually placed under control, effectivity, parent relationships, and any baseline, inventory, or composition records that already exist.

If control selection has not been decided for a real candidate, record it as `proposed`. If an existing item's control state cannot be established, mark that state `unconfirmed` and give the evidence and resolution action. A missing owner, locator, revision, or effectivity remains a gap attached to the item's established control state; it does not turn a controlled, decontrolled, or retired item into a proposal. State the consequence and actual resolving owner if assigned. Do not invent a revision, a baseline membership, or a repository path. If the selection rules were applied and no candidates, controlled items, or retained former items fall in scope, say so instead of adding a sample item. Do not record secrets or credentials in a locator.

## Finished-document contract

- **Title:** Identify the project or product boundary and name the document as its configuration item register.
- **Frontmatter:** None. Begin with the GFM title. Selection rules, control state, and revisions belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State selection and update rules before the item index; place discrepancies after the items. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Selection and status-accounting rules | Required | State the criteria for putting an item under control, the authority for selection and decontrol, identifier rules, the system of record, update triggers, access, and consumers. State how item identities, revisions, and relationships are reconciled with actual inventory or composition observations when those are available. Define control state and effectivity so that candidate, controlled, effective, unconfirmed, and observed conditions cannot be confused. |
| Configuration item index | Required | Include every real candidate under assessment, controlled item, and retained former item in the declared scope, or an explicit assessed-empty statement. For each item, give its immutable identity, name, class, owner or assignment gap, authoritative locator or gap, control state and basis, controlled revisions and effectivity or gaps, and parent or baseline relationships that actually exist. |
| Discrepancies and open items | Required | Identify items with unconfirmed control state, missing owner or controlled locator, unknown revisions or effectivity, dangling parent or baseline references, and conflicts with an inventory or composition record that was actually compared. Give the consequence and route, or state that the assessed scope showed none. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Configuration item | One governed identity; zero only when the declared scope was assessed and has no real candidate, controlled item, or retained former item. | Use one immutable identifier and do not reuse it for another item or for a new revision of the same item. A revision is not a new item identity. |
| Name and class | One name and one class per item. | Use `hardware`, `software`, `firmware`, `document`, `data`, `service`, `model`, or `other`. For `other`, state the actual class. The class does not by itself place the item under control. |
| Owner | One accountable role when assigned. | An unassigned owner stays unresolved. Record the actual configuration-control assignment; a custody or ownership assignment alone does not establish that role. |
| Authoritative locator | One location for the controlled definition, required to address. | Identify the repository, product-data system, drawing vault, or document control location appropriate to the class, or state that it is not established. A version-control or product-lifecycle system is not required for every class. The locator identifies the definition and MUST NOT contain a secret. |
| Control state | One established state, or `unconfirmed` when the actual state cannot be established. | Use `proposed`, `controlled`, `decontrolled`, or `retired` only when the corresponding state is supported. `Proposed` requires a real candidate without a completed selection decision. `Controlled`, `decontrolled`, and `retired` require their actual decisions. `Unconfirmed` names the evidence gap; presence in the register does not make an item `controlled`. Support the recorded state with the candidate rationale, actual control decision, or explicit evidence gap, independently of installation observations or lifecycle dates. |
| Control basis | One statement per item. | Give the selection rationale, authority, and boundary of what is inside the item. A proposed item states why it is a candidate; a decontrolled or retired item retains the actual decision and effectivity of that change. An unconfirmed state names the conflicting or missing evidence. |
| Controlled revision | Required to address for each item. | For `proposed`, state that no revision has yet been placed under control. For other states, identify revisions actually placed under control, including retained history after decontrol or retirement, and their effectivity. If the revision or effectivity is unknown, state the gap without changing the control state or implying that no revision exists. Do not collapse distinct effectivities into one undocumented "latest" label. |
| Parent references | Zero or more references to other configuration items. | Cite a different item in this register or in a named external register. A self-reference, cycle, or unknown parent remains an open discrepancy. Absence of a parent is valid for a top-level item. |
| Baseline references | Zero or more references to real baseline records. | Cite a baseline only when that record exists and identifies this item. Naming a desired baseline does not establish membership. |

Use one row or short block per item. Where an item has more than one controlled revision or effectivity, give each revision its own line under that item. Keep revisions and effectivities attached to their item, and do not add an empty item.

## Quality criteria

- Item identity stays stable across revisions. Established control states match actual decisions; an unknown state remains unconfirmed instead of being presented as a proposal or an authorized state.
- Controlled revisions and differing effectivities remain distinct. Missing details are visible gaps attached to the correct item and state.
- Existing record citations and installation observations retain their actual meaning; a control state requires its own candidate rationale, decision basis, or explicit evidence gap.
- Parent and baseline references resolve to real records or stay visibly unresolved.
