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
- **Frontmatter:** None. Begin with the GFM title. Identity, scope, and state belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State intake scope and handling rules before entries; follow entries with triage, routing, and reconciliation. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Intake boundary and handling | Required | Identify scope, channels, as-of point, steward or assignment gap, triage rules, access, retention, redaction, and client or receiving-party element. Explain excluded request classes and their actual routes. |
| Input entries | Required | Give every in-scope input a stable key, source or permitted locator, received time or gap, minimized description, context and version when known, uncertainty, and assigned triage owner or gap. An assessed-empty scope has an explicit no-inputs statement. |
| Triage and disposition | Required | Record classification, duplicates or themes, current triage state, decision basis, and authoritative downstream destination when established. Preserve original input meaning and conflicting interpretations. Routed feedback is not delivered functionality or a closed defect. |
| Reconciliation and upkeep | Required | Identify stale triage, missing source or destination, duplicate mistakes, and unresolved ownership; give next resolving actions, review triggers, and history for changed dispositions. State whether no discrepancies were identified after assessment. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
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
