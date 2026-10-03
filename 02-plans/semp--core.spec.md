# Systems engineering management plan specification

## Identity and selection

- **Specification ID:** `SEMP@core`.
- **Purpose:** Plan how one project will organize, tailor, resource, and control systems engineering across the system lifecycle.
- **Intended readers:** Project and systems engineering leads, discipline and supplier leads, technical authorities, assurance roles, and people preparing or deciding technical reviews.
- **Decision or action supported:** Coordinate cross-discipline technical work and determine the planned basis, responsibility, and evidence for technical decisions and lifecycle gates.
- **Use when:** A defined project needs a project-specific systems engineering approach spanning needs, requirements, architecture, interfaces, integration, verification, validation, transition, and support or retirement interfaces as applicable.
- **Scope boundaries:** Cover project-level systems engineering strategy, lifecycle work, cross-discipline responsibilities and interfaces, technical controls, resources, expected outputs, and planned decision gates.

## Authoring inputs and unresolved facts

Obtain the system-of-interest boundary and mission or intended use; lifecycle and acquisition scope; actual project mandate, established needs, allocated requirements, decisions, and supplied agreement scope; stakeholder and technical baselines or their decision state; architecture and external interfaces; technical teams, suppliers, decision rights, and handoffs; project work structure, schedule, resources, and constraints; selected engineering methods; technical risks and specialty needs; planned reviews, assessment routes, expected evidence, transition and support needs. Identify supporting project records by ID, version, and accessible locator, and expose conflicts among the supplied obligations or decisions.

Identify unknown facts and unmade decisions with their consequence, resolving action, and actual owner if assigned. State genuinely inapplicable lifecycle work or specialties with a scope-based reason; an established project requirement may be tailored only through the actual project decision authority. Treat an unselected method, resource, date, or gate as proposed. An unresolved system boundary, project obligation, decision authority, or essential gate criterion limits the plan's readiness for the affected work. Identify expected outputs, pending gates, proposed changes, and actual decisions by their state, with locators for existing records. Do not invent performed engineering, evidence, approvals, or accepted risk.

## Finished-document contract

- **Title:** Identify the project or system and name its systems engineering management plan.
- **Frontmatter:** None. Begin with the GFM title; system scope, plan responsibility, and project planning basis belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Establish the system and project obligations before tailoring and work assignment; present the technical work before review, resource, and change controls. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| System, purpose, and lifecycle boundary | Required | Identify the system of interest, mission or intended outcome, external context and interfaces, lifecycle stages covered, exclusions, key performance or support constraints, and the current or proposed technical baseline. Name the project role responsible for maintaining this plan. |
| Project basis and tailoring | Required | State established project obligations and criteria, their supporting needs, allocations, decisions, or supplied agreement scope, and project-record IDs and versions; distinguish established obligations from proposals and resolve or expose conflicts. State the chosen lifecycle and development approach, why its engineering depth fits project scale and risk, each material tailoring choice, and the actual project authority that may authorize a change to an established obligation. Identify proposed tailoring and existing tailoring decisions by their actual state and record. |
| Organization and technical interfaces | Required | Assign systems engineering leadership, technical and decision authority, discipline and supplier responsibilities, and cross-boundary handoffs. Explain how technical work coordinates with project management, configuration, quality, safety, security, logistics, operations, and support where applicable. A plan cannot grant rights absent from the actual project arrangement. |
| Technical work and outputs | Required | Plan how needs and operating concepts lead to requirements, architecture, trade decisions, allocations, interface control, integration, verification, validation, and transition. Identify work owners, inputs, outputs, dependencies, and decision points; cover modification, support, or retirement work when within this project's scope. Describe the selected methods or their selection route, inputs, and expected outputs; identify existing detailed project method records by version and locator when useful. |
| Technical risk, configuration, and evidence controls | Required | Define how technical uncertainties are identified, assessed, escalated, and followed; how candidate and approved baselines and changes remain distinct; and how planned evidence connects to obligations, system configuration, and later review decisions. State verification criteria against technical obligations and validation criteria against intended-use needs, including how gaps or conflicting evidence reach the responsible decision role. |
| Technology insertion | Conditional: a new, immature, or changed technology affects the system | Define the maturity question, evidence needed, alternatives or fallback, insertion decision authority, and risk retirement or reassessment point. If no such technology is in scope, omit the section rather than inventing a readiness score. |
| Specialty engineering | Conditional: an established project specialty obligation or material technical risk applies | Name the specialty, its project need, allocated requirement, or decision basis, owner, required analyses or controls, interfaces, and expected outputs. Safety, cybersecurity, human factors, reliability, and environmental work appear only when actually relevant. |
| Reviews, resources, and project integration | Required | Define technical milestones and planned review or audit gates with their purpose, entry basis, explicit criterion, decision role, expected evidence, and the route if a future review does not support proceeding or is deferred. Include staffing, facilities, enabling equipment, schedule and budget interfaces, and material margin assumptions. Select gate names and audit scope for the actual project; identify their planning state, dependencies, required decision records, and restrictions pending a decision. |
| Plan upkeep and unresolved decisions | Required | Define change triggers, coordination and update responsibility, and how a changed requirement, interface, baseline, risk, supplier scope, or resource assumption reaches affected work. List material unresolved decisions with their effect and next action; cite actual approval only when one exists. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| System and lifecycle scope | One bounded project/system scope, with all included lifecycle stages identified. | Distinguish the system from its enabling and external systems; mark candidate versus approved baselines and excluded stages. |
| Project obligation | One or more established obligations for the project. | State the obligation and explicit criterion, supporting need, allocation, decision, or supplied agreement scope, project-record ID and version, affected scope, and priority or conflict where material. |
| Tailoring decision | One per material deviation from an otherwise applicable engineering obligation. | State affected obligation or method, rationale, consequence, and actual authority or unresolved disposition; do not treat a proposed exception as authorized. |
| Technical work or handoff | One per material work stream or cross-role interface. | Connect input or obligation, output, responsible role, dependency, expected timing or gate, and receiving role or decision use. |
| Technical review or gate | One or more according to the actual lifecycle strategy. | Define subject and target configuration, entry evidence, criterion, decision authority, expected output and decision record, planning state, and the route when a future review does not support proceeding or is deferred. Identify any existing decision by its recorded scope and configuration. |
| Technology or specialty treatment | Zero or more, only when applicable. | Connect the real trigger or obligation to owner, method, expected evidence, and decision point; give a reason for material exclusions. |

Use prose to explain strategy and tailoring. Use a work/authority mapping when several teams or suppliers interact, a gate or milestone table when sequence matters, and an obligation-to-implementation-and-expected-evidence matrix when numerous established project obligations need coordination. Label planned coverage and unresolved allocations explicitly. Diagrams may clarify system context or handoffs.

## Quality criteria

- The plan makes the system boundary, lifecycle scope, selected technical approach, and actual project decision rights explicit.
- Requirements, design, interfaces, integration, V&V, configuration, risk, review, and transition work have coherent owners, dependencies, and expected outputs; specialty work has explicit inputs, outputs, criteria, and responsible roles.
- Tailoring, technology maturity, technical risk, resource limits, and unresolved decisions remain visible at the gates they affect.
- Review criteria and expected evidence can be traced to an established project need, allocation, decision, or supplied agreement scope and target configuration; planned outputs and pending decisions have explicit states, and any existing evidence or decision has its actual record locator and scope.
- The plan can be updated as baselines and project conditions change without rewriting actual evidence or silently changing an approved obligation.
