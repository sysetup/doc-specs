# Retirement and disposal plan specification

## Identity and selection

- **Specification ID:** `RETIREMENT-PLAN@conditional`.
- **Purpose:** Plan the controlled withdrawal of a defined system, service, product, or asset from its current role, including dependent capability, data, access, support, records, and disposition.
- **Intended readers:** System and service owners, operators, asset and configuration managers, data and records owners, security and safety roles, receiving parties, suppliers, and retirement decision makers.
- **Decision or action supported:** Determine what may be withdrawn, under whose authority, in what order, with which retained obligations and proof needed for closure.
- **Use when:** A system, service, product, or asset is to be decommissioned, transferred, reused, disposed of, or removed from support under a planned end state.
- **Scope boundaries:** Cover controlled withdrawal and disposition of the existing capability, with dependency, data, access, support, and closure conditions. Include withdrawal actions and disposition gates beyond end-of-support dates. Exclude introducing a replacement into service and routine upkeep as primary activities; treat replacement readiness as a dependency when continued service requires it.

## Authoring inputs and unresolved facts

Obtain the current asset or service scope and configuration; approved or proposed retirement decision and its actual decision maker; affected users and dependent systems; continued service and support obligations; data classes, custodians, supplied retention and transfer requirements and active preservation holds; records and archive duties; access and external connectivity; supplied supplier, warranty, lease, ownership, and return terms where applicable; physical safety and environmental constraints of the scoped handling activities; replacement or receiving arrangements; and feasible isolation, disposal, and closure criteria. Identify actual project decision or agreement records, their editions, and locators for retained duties and disposition rights.

State an unknown inventory item, dependency, obligation, authority, or disposal route with its consequence, resolving action, and actual owner if assigned. Treat retirement authorization, transfer terms, dates, and destruction method as proposed until established. If the asset boundary, data or records duty, dependent service, or withdrawal authority is uncertain, identify the affected activity as not ready for irreversible action. Explain inapplicable physical disposal or migration from the actual asset scope and intended end state. Describe withdrawal, access revocation, sanitization, transfer, configuration closure, and checks as planned activities with expected evidence and authorization still needed. Identify any established prior authorization by its actual decision record.

## Finished-document contract

- **Title:** Identify the system, service, product, or asset and name its retirement or disposal plan.
- **Frontmatter:** None. Begin with the GFM title; identity, authority, and retained obligations belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Establish scope, dependencies, and authority before irreversible withdrawal; describe disposition before closure evidence. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Retirement boundary and decision basis | Required | Identify what will leave service, its controlled identity and current role, included and excluded components, reason and intended end state, accountable owner, and real authority for withdrawal or approval still needed. State continued service obligations and constraints on timing. |
| Dependencies and stakeholder continuity | Required | Identify users, downstream systems, interfaces, contracts, support functions, and other dependencies affected by withdrawal. Define notice, replacement or alternate service, migration or transfer interface, and hold conditions where an obligation would otherwise be stranded. |
| Data, records, and access disposition | Required | Define data owners, classes or sensitivity where relevant, retention periods and checks for active preservation holds with their supplied project decision or agreement locators, archive or transfer destination, access and credential revocation, external connectivity removal, and planned evidence. State who may authorize deletion or sanitization and when retained copies remain necessary. |
| Withdrawal sequence and gates | Required | Give ordered isolation, service termination, dependency removal, data and configuration actions, physical handling if any, roles, prerequisites, holds, safe-state or recovery response, and criteria for progressing through irreversible steps. State the planned authorization rule for each irreversible step and the safe-state or recovery action when a step cannot continue. |
| Asset and supplier disposition | Conditional: physical assets, supplier property, transfer, reuse, recycling, or destruction is in scope | Define the chosen route, ownership and custody, return or reuse conditions, physical handling hazards and protective measures, environmental containment and disposal controls, required sanitization or inspection, expected evidence, and the supplied recipient or contractor terms. Identify audit or disposal rights only when established by an actual agreement. |
| Support and configuration closure | Required | Define how maintenance, licensing, subscriptions, accounts, monitoring, documentation, registries, baselines, and support obligations will be ended or transferred without losing needed history. Specify the records to preserve and their custodian. |
| Verification and closure decision | Required | Define criteria and methods for checking service absence, dependency removal, access revocation, data or asset disposition, retained records, and residual obligations. Name expected evidence, responsible reviewer, open-item handling, and the role authorized to declare closure or receive transfer, with the prerequisites for that decision. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Retirement subject | One bounded system, service, product, or asset scope; multiple items only when governed as one coordinated retirement. | Identify current configuration and operating role, exclusions, and intended end state such as transfer, reuse, decommissioning, recycling, or destruction. |
| Dependency or continuing obligation | One per material affected service, party, or obligation. | State owner, impact, replacement or transfer route, required notice or evidence, and condition before disconnection. Unknown dependencies require investigation before irreversible work. |
| Data or record class | One per materially different retention, transfer, or sanitization treatment. | Identify custodian, retention period and its start or end condition, supplied retention or transfer decision or agreement, any active preservation hold, destination, access after retirement, method decision, and expected proof. Active-copy deletion must preserve required copies and archives through their retention end condition and until any active hold is released. |
| Withdrawal stage | One or more ordered stages. | State prerequisites, owner, affected configuration or service, action at planning depth, hold or point of no return, check, and fallback or safe-state route. |
| Disposition route | Conditional per asset or transferable item. | Identify actual owner and recipient or vendor, intended custody or disposal method, physical handling protections, environmental controls, access and sanitization measures, and proof expected for the scoped route. A physical disposal method is not mandatory for a purely logical service. |
| Closure criterion | One or more criteria covering all in-scope withdrawal outcomes. | State the observable condition a planned check must show, the expected evidence, and the reviewer. Identify which evidence supports a closure or transfer decision and who may make that decision. |

Use an item/dependency table when multiple services or assets are affected, an ordered withdrawal sequence for irreversible actions, and a data/record disposition table when treatments differ. A flow diagram may clarify transfer and retention paths. Do not include empty disposal rows, generic approval blocks, or executable deletion commands in the finished plan.

## Quality criteria

- The plan identifies the withdrawn capability and every material dependency, owner, continued duty, and end state without assuming that a replacement is already live.
- Data transfer, retention, sanitization, access revocation, and physical disposal are assigned only where applicable and do not conflict with each other.
- Irreversible actions have a real authority gate, prerequisite checks, and a safe response to an unresolved dependency, data duty, or custody issue.
- Expected verification evidence and record locations cover the prerequisites for a closure or transfer decision, including residual obligations and open items.
- Planned activities state criteria, evidence expectations, and authorization gates without asserted execution results. Any prior decision cited as established has an actual record locator.
- The withdrawal sequence accounts for replacement readiness, continued service, and custody wherever these affect the safe retirement of the existing capability.
