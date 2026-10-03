# Systems engineering lifecycle process specification

## Identity and selection

- **Specification ID:** `LIFECYCLE-PROCESS@systems-engineering`.
- **Purpose:** Define the reusable system-level technical process from stakeholder need through requirements, architecture, integration, verification, validation, transition, and technical decisions.
- **Intended readers:** Systems engineers, discipline leads, technical and review authorities, integrators, and transition recipients.
- **Decision or action supported:** Teams can coordinate technical work across disciplines and know what information and criteria are needed before a lifecycle decision or handoff.
- **Use when:** A common cross-discipline systems engineering process is needed for a defined class of systems or lifecycle stages.
- **Scope boundaries:** Define recurring technical activities, information flows, lifecycle decision criteria, and handoffs across the participating disciplines and covered system lifecycle stages.

## Authoring inputs and unresolved facts

Obtain the actual system-of-interest and lifecycle scope, supplied stakeholder needs and mission decisions, established project obligations and their basis, process owner, technical authority and review rights, participating disciplines, requirements and interface control routes, architecture and integration approach, V&V and transition interfaces, explicit gate criteria, and process improvement or tailoring authority. Identify the supplied project decision and assigned role establishing each decision right, with its locator when available.

For an unknown fact, state what is missing, why it matters, the resolving action, and owner if known. Distinguish an unsettled gate criterion from an established criterion that requires holding or reworking the subject under review. A planned review is not an actual decision. If scope, technical authority, or criteria for a consequential handoff are unsettled, mark that portion of the process proposed and unsuitable for an authorized gate until resolved. Explain genuinely inapplicable lifecycle subjects and their boundary; do not invent requirements, baselines, review outcomes, or evidence.

## Finished-document contract

- **Title:** Name the systems engineering lifecycle process and its system or organizational scope.
- **Frontmatter:** None. Begin with the GFM title; applicability and process edition belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Establish the system boundary and authority before the lifecycle flow; place gate rules after the work that supplies their inputs; end with transition and process feedback. Exact heading wording is flexible.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| System scope and technical authority | Required | Define system classes and lifecycle coverage, interfaces with disciplines and organizations, process owner, the project basis for adopted obligations and decision rights, truthful edition or state when controlled, and the authority for technical decisions and tailoring. Identify the activities, decisions, and exclusions within the process boundary. |
| Technical management and definition | Required | Describe technical planning and control, risk and interface coordination, decision rationale, stakeholder need and requirement definition, allocation and change control, architecture development and evaluation, and the handoffs among them. State who produces and accepts each information flow and how unresolved conflicts are escalated. |
| Realization and assessment flow | Required | Describe integration readiness and sequencing, cross-boundary interface checks, verification against specified technical obligations, validation against stakeholder or intended-use needs, anomaly disposition, and return loops. Keep verification and validation questions and evidence separate even when work is coordinated. |
| Lifecycle reviews and decisions | Required | Define the applicable future review or gate triggers, entry information, assessable exit or hold criteria, participating and deciding roles, the names of possible future outcomes, and the follow-up route. Name a specific gate only if the process actually uses it. |
| Transition and process feedback | Required | Define readiness for transfer to operation, use, support, or another lifecycle owner; required handoff information and recipient; unresolved-item handling; and how process performance, deviations, and changes are reviewed. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| System boundary | One definition of the system of interest, external interfaces, lifecycle scope, and relevant exclusions. | Keep allocations to software or other disciplines explicit where they affect a handoff. |
| Technical activity | One or more connected activities with local labels when cross-referenced. | State responsible and deciding roles, input and entry criteria, method or action, output and completion criteria, and handoff or rework route. |
| Requirement and architecture control | One route from sourced need through system obligations, allocation, architecture decisions, and change impact. | Distinguish proposed requirements or architecture options from an authorized baseline and identify the decision needed for that transition. Retain links to affected interfaces and assessment basis. |
| Integration route | One rule for assembling and checking interacting elements. | Define readiness, configuration identity, interface responsibility, discrepancy handling, exit criteria, and the observations and limitations a later integration must record. |
| Verification and validation interfaces | One route for each distinct assessment purpose. | Verification addresses conformity to specified technical obligations; validation addresses fitness for stakeholder or intended-use needs. Define basis, responsible interface, expected evidence, and disposition of gaps. |
| Review or gate | One or more where decisions are part of the adopted lifecycle. | Define trigger, decision authority, entry and exit criteria, the names of possible future outcomes, the record a later review would produce, and open-action treatment. For each adopted path, such as proceed, hold, or rework, state the criterion and designated role required to authorize it. |
| Transition handoff | One route to the next system owner or operational context. | Define receiving role, readiness criteria, configuration and support information, open limitations, and disposition. Identify the actual decisions and deciding roles required for acceptance, baseline release, and operational authorization where applicable. |

Use a flow or activity table when it clarifies dependencies across disciplines; use a decision table for gates and hold/rework paths. A narrative may suffice for a small process. Diagrams are conditional and need only carry the semantics of roles, decisions, and handoffs; no particular modeling notation or native resource is required.

## Quality criteria

- Technical management, requirements, architecture, integration, verification, validation, transition, and lifecycle decisions form a coherent path with explicit return loops.
- System-level authority and cross-discipline interfaces identify allocations, exchanged information, responsible roles, and handoff criteria.
- Every gate identifies its decision maker, entry information, evidence basis, criteria, and authorized outcome routes.
- A requirement change or integration discrepancy has an impact and escalation route; transition cannot silently discard unresolved obligations or limitations.
