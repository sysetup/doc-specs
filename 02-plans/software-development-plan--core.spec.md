# Software development plan specification

## Identity and selection

- **Specification ID:** `SOFTWARE-DEVELOPMENT-PLAN@core`.
- **Purpose:** Plan the work, resources, controls, and evidence needed to develop and deliver defined software, including secure development practices.
- **Intended readers:** Software and system leads, developers, security and quality roles, configuration managers, suppliers, release decision makers, and receiving maintainers.
- **Decision or action supported:** Coordinate project-specific development increments and determine what must be ready for a controlled software release and support handoff.
- **Use when:** A defined project or delivery effort needs to assign software development work from requirements and design through implementation, integration, assessment, and release preparation.
- **Scope boundaries:** Cover project software development, controlled build and integration, planned assessment, release preparation, and support handoff for the selected delivery effort and increments.

## Authoring inputs and unresolved facts

Obtain the software item and delivery boundary; stakeholder needs and allocated technical requirements; product and development-infrastructure security needs; established project decisions and supplied agreement scope; architecture and interface constraints; lifecycle and increment strategy; team, supplier, schedule, resource, and decision rights; source, dependency, build, integration, and test environments; configuration and quality interfaces; explicit release criteria and receiving-party needs. Obtain the selected secure-development practices with their scope, required actions, parameters, and assessment criteria. Identify each obligation or selected practice's project need, allocation, decision, or supplied agreement basis by record ID, version, and accessible locator.

Identify an unknown fact or undecided choice with its effect, resolving action, and actual owner if assigned. Mark an assumed requirement, date, gate, or method as proposed until established; explain genuine inapplicability within the stated scope. If essential scope, technical basis, release criterion, or decision authority is unresolved, identify the resulting planning or readiness limit. State planned work and expected evidence explicitly, and identify any existing evidence or decision with its actual record locator and affected configuration. Do not invent security controls, supplier commitments, test outcomes, approval, or acceptance.

## Finished-document contract

- **Title:** Identify the project or software item and name its software development plan.
- **Frontmatter:** None. Begin with the GFM title; project boundary and plan state belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Establish delivery scope and authority before the work strategy; present build and assurance controls before release and handoff. Exact heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Delivery scope and planning basis | Required | Identify software items or increments, intended users and operating context, delivery and acquisition boundaries, excluded work, established project obligations and explicit criteria with project-record IDs and versions, lifecycle approach, assumptions, and the actual planning and release decision roles. Distinguish established obligations from proposals. |
| Work organization and schedule | Required | Define requirements allocation and change handling, design and interface work, implementation, integration, review, and expected outputs. Assign roles, resources, dependencies, milestones or increment gates, and an action for schedule uncertainty. Coordinate system and supplier work through actual scope, responsibilities, handoffs, and decision rights. |
| Development environment and configuration | Required | Define repositories, branching or change integration rules when relevant, controlled source and dependency inputs, toolchain and environment boundaries, build and integration method, reproducibility or integrity needs, and how a candidate maps to its requirements and configuration. Name tool-specific settings only when selected. |
| Secure development and third parties | Required | Plan how development infrastructure is protected and how product security obligations enter design, code, review, build, test, and vulnerability remediation. Describe each selected practice's scope and required actions, owners, explicit criteria, and expected evidence at the level needed by the project; include communication and evidence duties for actual third-party components or suppliers when applicable. |
| Assessment and quality gates | Required | Explain risk-based review, analysis, testing, verification and validation interfaces, environments, coverage basis, anomaly handling, retest, and gate criteria. State who evaluates evidence and decides whether unresolved findings block or condition progression. Identify each gate's planning state, prerequisites, expected evidence, and required decision record. |
| Release and support transition | Required | Define candidate composition and identification, package and dependency information appropriate to the delivery, integrity and vulnerability checks, release-readiness basis, the authority that may later approve or release, expected delivery evidence, and handoff to operations or maintenance. State the prerequisites, criteria, deciding role, and required record for release, deployment, and receiving-party acceptance when in scope, and identify each decision's actual state. |
| Plan control and change response | Required | State who maintains this project plan and how scope, requirements, supplier, schedule, toolchain, or risk changes cause replanning and communication to affected roles. Include actual approval references only if such decisions exist. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Software delivery scope | One bounded project or effort; one or more software items or increments. | Identify item and delivery configuration or versioning approach, interfaces, exclusions, and whether work is developed, acquired, or integrated. Do not imply a release already exists. |
| Development work item or increment | One or more planned units of work. | Connect the work to its obligation or planning basis, output, responsible role, dependency, expected timing or gate, and review or completion criterion. A date or estimate is proposed until committed. |
| Development infrastructure and product security obligations | One treatment of each concern, with concrete controls only where selected. | State source/build environment protection and the software's own security requirements with their respective scopes. Relate each selected practice to an established project need, allocation, or decision with record ID and version, owner, planned actions, explicit criterion, and expected evidence. |
| Third-party obligation | Conditional for an acquired component, service, or supplier. | Identify the real agreement or selection state, applicable security and technical requirement, receiving role, needed evidence, and escalation for a gap. A plan cannot grant audit rights or bind a supplier. |
| Assessment or release gate | One or more gates appropriate to the delivery strategy. | Define entry basis, target configuration, criterion, responsible assessor or decision role, expected evidence, planning state, required decision record, and the planned response when a later check does not meet its criterion or cannot be concluded. |
| Handoff | One route from delivered software to the actual receiving function. | Identify support materials, configuration and dependency information, open issues, update and vulnerability route, and acceptance interface when applicable. Identify existing component or dependency records by configuration, version, and locator when used. |

Use prose for strategy and rationale, a milestone or work mapping table when several increments must be coordinated, and a flow or diagram when it clarifies build, gate, or handoff dependencies. Use a practice-to-obligation mapping only for practices actually selected, identifying scope, required actions, owner, criterion, and expected evidence.

## Quality criteria

- Every planned increment has an identifiable basis, responsible role, output, dependency, and decision or completion criterion; unresolved choices remain visible.
- The software security, configuration, quality, and V&V interfaces have coherent scope, responsibilities, inputs, outputs, and criteria; selected development practices have explicit actions and assessment routes.
- Build inputs, candidate configuration, assessment criteria, and release decision rights are traceable; planned work and pending decisions have explicit states, and any existing evidence or decision has its actual locator and affected configuration.
- Third-party commitments, evidence, and access rights are limited to actual agreements or explicitly proposed terms.
- Support handoff covers the configuration, dependency, support, open-issue, update, vulnerability, and acceptance information the receiving maintainers need, with assigned responsibilities and expected timing.
