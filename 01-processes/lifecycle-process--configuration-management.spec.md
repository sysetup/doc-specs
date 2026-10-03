# Configuration management lifecycle process specification

## Identity and selection

- **Specification ID:** `LIFECYCLE-PROCESS@configuration-management`.
- **Purpose:** Define the reusable process for identifying controlled configurations, establishing and changing baselines, accounting for status, checking integrity, and retaining configuration history.
- **Intended readers:** Configuration managers, change and baseline authorities, item owners, auditors, and teams that create or use controlled items.
- **Decision or action supported:** A team can route an item or proposed change through the right controls and determine which state and record are authoritative.
- **Use when:** A recurring configuration management process is needed across projects or lifecycle stages within a stated scope.
- **Scope boundaries:** Define recurring configuration controls, state transitions, and record requirements for the stated item classes and lifecycle stages.

## Authoring inputs and unresolved facts

Obtain the supplied project decisions establishing the configuration control mandate; process owner; lifecycle and organizational scope; controlled item classes; identifier and repository rules; baseline and change decision authorities; affected-party interfaces; status and audit needs; explicit record retention requirements; and the established exception or tailoring route. Inspect how an item moves from proposed through approved and actual states, including urgent changes. Identify the project decision and its locator for each assigned decision right or adopted control.

When a fact is unknown, state the gap, its consequence, resolving action, and owner if assigned. Mark an unestablished rule as a proposed decision, not an operative control. Explain why an activity or audit method is inapplicable and how its necessary integrity objective is met; do not erase an intrinsic subject without analysis. If item scope, change authority, or baseline decision rights remain unresolved, mark the process unsuitable for controlled use until they are settled. Do not invent authorities, approved baselines, audit findings, or performed changes.

## Finished-document contract

- **Title:** Name the configuration management lifecycle process and its governing scope.
- **Frontmatter:** None. Begin with the GFM title; process applicability and edition belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Establish authority and applicability before the activity flow; present decision controls and records before effectiveness and tailoring. Exact heading words are flexible.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Process authority, scope, and interfaces | Required | State the reusable outcome, owner, truthful process edition or state when controlled, applicable item classes and lifecycle boundaries, the project decisions establishing the control mandate, and interfaces with engineering, release, suppliers, or operations. Identify exclusions and the route for a scoped applicability decision. |
| Configuration activity flow | Required | Define identification, baseline establishment and protection, change control, status accounting, integrity checks or audits, configuration records, and tailoring. For each subject, give entry conditions, responsible role, key inputs, actions or decision points, expected outputs, completion criteria, and handoffs. Activities may be combined in one flow if every subject remains findable. |
| Decision and discrepancy controls | Required | Distinguish the future states of change proposal, impact assessment, authorization, implementation, verification of the changed state, and baseline update. State who may later decide each transition, how affected parties learn of decisions, how urgent changes are controlled when allowed, and how unauthorized or mismatched actual state is contained and resolved. |
| Records, assurance, and evolution | Required | Identify the authoritative item, baseline, change, status, and audit information; how records link an approved decision to an actual configuration; retention or transfer expectations; process monitoring and correction; and who may tailor or revise the process and on what basis. Name actual storage or retention rules only when established. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Controlled item class and identity | One or more classes of hardware, software, data, documents, or other items actually in scope, with an identification rule for each. | State selection criteria and the authority for adding or removing an item; a global identifier regex is required only if a real control system needs one. |
| Baseline rule | At least one rule for establishing, identifying, changing, and protecting an approved set or state. | Distinguish candidate, approved, and observed state; require the actual approval decision to establish an approved baseline. |
| Change route | One normal route, plus a conditional urgent or exceptional route if allowed. | Define request content, impact on affected items and interfaces, decision authority, implementation control, and post-change reconciliation. Urgency never supplies authority by itself. |
| Status account | One description of how item versions, baselines, change decisions, implementation state, and discrepancies remain queryable. | Preserve the relation among item, change, decision, and observed state; avoid treating a requested change as implemented. |
| Integrity check or audit | One process rule for checking that required controlled information and actual state agree; a formal functional or physical audit is conditional on the applicable scope. | Define trigger, explicit criteria, responsible role, the information a later check must record, and how a discrepancy is routed. |
| Process activity | One or more connected activities, each with a locally distinct label when cross-referenced. | Give entry and exit conditions, responsible role, input, output or record, decision point, and next handoff where meaningful. Do not require a separate row for a label this process does not use. |
| Tailoring decision | Conditional when a scope exception or variation is allowed. | State proposer, reason, affected controls, impact, decision authority, the later record, and review trigger. Require an actual decision by the designated authority before an exception takes effect. |

Use prose for rules and a flow or table with meaningful role, input, decision, output, and handoff columns for the recurring path. A diagram may clarify complex branches but is not required; a precise narrative is sufficient. Refer to actual change or baseline records when they exist.

## Quality criteria

- A qualified reader can determine which items are controlled, which state is authoritative, and who can move it to a new baseline.
- The normal and exceptional paths do not confuse request, decision, implementation, reconciliation, and evidence; discrepancies have an owner and disposition route.
- Identification, change, baseline, accounting, integrity, records, and tailoring obligations are present without seven duplicated fill-in forms.
- Interfaces with software, systems, release, and operations participants identify each handoff's trigger, information, sender, and recipient.
