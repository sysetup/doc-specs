# High-impact information-system contingency plan specification

## Identity and selection

- **Specification ID:** `IS-CONTINGENCY-PLAN@high-impact`.
- **Purpose:** Define how one classified high-impact information system sustains or recovers critical functions, controls failover and data integrity, reconstitutes normal service, exercises the selected strategy, and keeps the plan ready.
- **Intended readers:** Mission and system owners, contingency and recovery leaders, data and infrastructure teams, external providers, and authorities for activation, restriction, and return to service.
- **Decision or action supported:** Those roles can invoke a coordinated recovery, control parallel or alternate processing if selected, reconcile data and transactions, and decide whether protected normal operation may resume.
- **Use when:** The responsible authority has established a high-impact classification and requires a system-specific contingency plan.
- **Scope boundaries:** Cover continuity and recovery of one system with an established high-impact classification. Offsite data and alternate processing each require an explicit disposition. Include concurrent processing only when the selected strategy uses it.

## Authoring inputs and unresolved facts

Obtain the project classification decision and deciding role; system boundary and critical mission functions; current architecture, data flows, dependencies, interconnections, and authorized recovery configurations; actual impact or business analysis; approved continuity, recovery time, and recovery point objectives; capacity and resource assumptions; offsite storage and alternate processing arrangements or internal project decisions permitting authorized tailoring; backup, restore, and transaction-reconciliation methods; failover and return authorities and required operational permissions; security controls at recovery locations; provider commitments; protected contact and alternate communication routes; and project decisions on exercise, training, maintenance, and protected distribution. Identify each supplied project fact or decision by its actual record, edition, or locator.

Mark missing evidence unknown and undecided design or authority not established, with impact, resolving action, and actual owner if assigned. Explain inapplicability from a real scope or internal tailoring decision. An unresolved impact decision, critical-function objective, sufficient recovery route or capacity, storage or alternate processing disposition, integrity criterion, or activation or return authority bars a claim of activation readiness. Show conflicts between target and capability as explicit decision issues. Never invent failover tests, recovery results, approvals, or provider commitments.

## Finished-document contract

- **Title:** Identify the system and the high-impact information-system contingency plan.
- **Frontmatter:** None. Begin with the GFM title. Plan identity, authorities, and recovery architecture are body content.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Establish objectives and chosen continuity strategy before activation; recover before reconstitution; put practice and upkeep after the operational phases. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Scope, authority, and objectives | Required | Identify the system, plan edition, owner, established high-impact classification and its project decision record, critical functions and data, scope and exclusions, material assumptions, continuity and recovery priorities, time and data objectives with units, and who may later approve the plan and activate recovery. Identify required operational permissions and their approving roles. |
| Continuity and recovery concept | Required | Describe authorized primary and recovery configurations, critical asset and dependency map, required capacity and staffing, team handoffs, provider commitments, and protected access to contacts. Explain how critical functions continue or resume and how the strategy limits data loss and unsafe split operation. If concurrent processing is not selected, say so here without inventing a procedure. |
| Storage and alternate processing disposition | Required | State the selected offsite data and alternate processing arrangements, separation or shared-failure concerns, accessibility, capacity, security controls, invocation, and restoration of protected copies. If an internal project decision permits tailoring of either arrangement, identify that decision, approving role, approved disposition, and viable alternative; classification alone is insufficient to establish such an exception. |
| Activation and notification | Required | Define observable triggers, outage and mission impact assessment, decision authority, initial safety and security checks, ordered team and stakeholder notifications, alternate channels, provider coordination, and reassessment when conditions exceed the chosen strategy. |
| Continuity, failover, and recovery | Required | State the dependency-aware order for continuing or restoring critical functions, data, access, and connectivity; required resources and roles; controlled actions or procedure references; expected states; integrity checkpoints; fallback and escalation routes; and evidence a later execution record must capture. Define the transition to an alternate location when selected. |
| Reconstitution and return to normal | Required | Define checks for data currency, integrity, transaction completeness, functions, security controls, and interconnections against established criteria. State the authority and evidence a later declaration of recovery or restriction must use, and the planned user notice, reconciliation or retirement of temporary processing, renewal of backups and offsite copies, event documentation, and deactivation. |
| Concurrent processing | Conditional when the selected recovery strategy operates two locations or instances concurrently | State entry authority, duration or exit condition, data ownership and write controls, conflict or split-brain prevention, reconciliation, planned checks, and cutover or rollback criteria. Identify the deciding roles and required evidence for entry, cutover, rollback, and exit. |
| Exercise, training, and maintenance | Required | Plan an end-to-end exercise of the selected recovery path, including alternate processing and return where applicable; state safety limits, participants, expected evidence, frequency or scheduling authority, defect and untested-scope handling, role training, review triggers, contact refresh, and protected distribution. |
| Supporting material | Conditional when detailed contacts, procedures, site arrangements, impact findings, or provider commitments are needed | Include the controlled material or an accessible versioned reference and an outage-access route for authorized recovery personnel. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| System and impact decision | One bounded system and one established high-impact classification. | Identify the deciding role and project decision record; reassess the recovery scope, objectives, and strategy if classification changes. |
| Critical function and objective | One or more prioritized functions with approved continuation or recovery targets. | Give units, source, dependencies, maximum interruption or data-loss limits where established, and the consequence when capability cannot meet them. |
| Recovery configuration and capacity | One selected primary-to-recovery transition path, with alternatives only when authorized. | Define required capacity, location and connectivity assumptions, data source, security boundary, and failure route; do not equate an untested design with proven capability. |
| Offsite storage and alternate processing | One selected arrangement for each, or an actual internal project decision permitting authorized tailoring to a viable alternative. | Cover accessibility during disruption, integrity, custody, and renewal or return after use. Do not publish secrets or sensitive site details unnecessarily. |
| Activation or transition rule | One or more observable conditions and authorized decision makers. | Each branch leads to continued assessment, failover to the recovery configuration, in-place recovery, restriction, or escalation. State reassessment timing or escalation triggers for continued assessment; there is no silent indefinite wait. |
| Recovery action | One or more ordered actions or controlled procedure references. | Bind target, responsible role, prerequisite, expected state, evidence a later record must capture, and the route when the action cannot continue. References must identify an actual accessible procedure and edition. |
| Reconciliation rule | Conditional for transactions, replication, or simultaneous processing that may diverge. | Define authoritative data source, permitted writes, conflict detection, decision authority, and criterion for cutover or rollback. |
| Reconstitution check | Data, function, and security checks for each critical restored service. | Define criteria, responsible role, and evidence a later execution would retain for the recovery or restriction decision. |
| Exercise and upkeep rule | One method for practicing and refreshing the strategy. | Cover the selected failover and return path, evidence a later exercise would retain, limitations, the corrective-action route, and change-driven review. |

Use a dependency diagram or table when it clarifies critical paths, a decision flow for activation and failover, ordered recovery actions or controlled procedure references, and a criteria checklist for reconstitution. Use a reconciliation table or flow only when parallel data paths exist. Keep sensitive contacts, topology, and access details in protected material that remains reachable during an outage. Do not include blank forms or credential values.

## Quality criteria

- Continuity and recovery objectives, selected capacity, provider commitments, backup currency, alternate processing, and exercise scope are mutually consistent, or the gap is routed to actual authority.
- Failover and return paths prevent unsafe dual writes or data loss beyond the established data-loss objective; any selected concurrent processing has explicit reconciliation and exit rules.
- A later declaration that normal operation may resume requires data, critical functions, and security state to meet established criteria, or a named deciding role to accept a stated restriction; the plan identifies the evidence needed for that decision.
- Activation and return-to-service roles, required operational permissions, and unresolved readiness conditions are explicit.
- Concurrent processing is included only when selected in the recovery strategy. When it is not selected, the continuity and recovery concept records that decision.
