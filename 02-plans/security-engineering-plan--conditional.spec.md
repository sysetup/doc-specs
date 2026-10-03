# Security engineering plan specification

## Identity and selection

- **Specification ID:** `SECURITY-ENGINEERING-PLAN@conditional`.
- **Purpose:** Plan a project's technical security work from protection needs and threat or risk analysis through requirements, design, implementation, assessment, vulnerability handling, and operational handoff.
- **Intended readers:** Security and system engineers, developers, operators, supplier and assurance roles, project decision makers, and any actual security authorization authority.
- **Decision or action supported:** Coordinate security design and assessment against an established protection basis and assign work, evidence, and risk-decision interfaces through the project lifecycle.
- **Use when:** The project has an established responsibility for coordinated technical security engineering of a defined system or software item, whether imposed by an agreement, organizational direction, or project decision.
- **Scope boundaries:** Cover technical protection objectives, threat and risk work, security requirements and controls, planned assessments, vulnerability handling, operational handoff, and reassessment of the selected system or software item.

## Authoring inputs and unresolved facts

Obtain the system or item boundary and planned configurations; stakeholders and protection needs; assets, data, trust boundaries, interfaces, and operating environment; established project security requirements, decisions, selected controls and parameter values; threat and risk inputs or a justified plan to develop them; architecture and development or integration approach; supplied supplier scope and responsibilities; permitted assessment targets, methods, limits, and authorization conditions; vulnerability and incident interfaces; operations and maintenance owners; decision rights; and assigned receiving-party review or authorization interfaces. Identify each obligation's project need, allocation, decision, or supplied agreement scope by record ID, version, and accessible locator, and distinguish established requirements from candidate controls or recommendations.

Mark unavailable facts unknown and unmade choices not established, with effect, resolving action, and actual owner if assigned. If threat analysis or control selection is pending, define how it will be completed and which decisions depend on it. Explain genuine inapplicability based on scope and actual project decision rights. Do not invent controls, test permission, security classification, acceptance thresholds, or authorization. Missing protection objectives, established project obligations, assessment criteria, or decision authority prevent a claim that the affected security work is ready for conclusive assessment or release. Identify proposed controls, expected evidence, pending assessments, and unmade decisions by their actual state; cite existing evidence or decisions only with their record locators.

## Finished-document contract

- **Title:** Identify the system or item and name its security engineering plan.
- **Frontmatter:** None. Begin with the GFM title. Security scope, obligations, and decision rights belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Establish protection context, project obligations, and criteria before design work; place planned assessment before operational handoff and change control. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Security scope, objectives, and authority | Required | Define the system or item, configurations, lifecycle and trust boundaries, assets and stakeholders, protection objectives, explicit established project obligations and criteria with project-record IDs and versions, exclusions, accountable roles, and actual security decision or escalation rights. Distinguish a selected requirement or control from a candidate. |
| Threat and risk work | Required | Define how threats, attack paths or misuse conditions, weaknesses, dependencies, and security risks will be identified, assessed, updated, and linked to protection objectives. State sources, method, assumptions, treatment route, and who decides unresolved or residual risk. Avoid operational exploit instructions or invented ratings. |
| Requirements and secure design strategy | Required | Explain how security needs become assessable requirements and selected controls, how architecture and trust-boundary decisions address them, and how secure design, build, supplier, and integration work will be performed and reviewed. State established organization-defined parameter values, their scope, and project decision basis; identify missing values and their resolution route. |
| Verification and assurance strategy | Required | Map established security requirements or controls, or define the rule for mapping future selections, to authorized inspection, analysis, test, demonstration, or review. Specify configuration, explicit criterion, scope permission, responsible role, expected evidence, review, and the planned response when a later check does not meet its criterion, cannot be concluded, or leaves a coverage gap. Independence is conditional on an established project requirement or risk decision. Identify each assessment's planning state, prerequisites, and completion criteria. |
| Vulnerability, operations, and handoff | Required | Plan vulnerability intake, applicability and prioritization, treatment, verification, and escalation; define monitoring and operational security responsibilities, protected handoff of open risks and restrictions, and interfaces to incident response and contingency work. |
| Change and security decision control | Required | Define how changed requirements, code, suppliers, configurations, threats, exceptions, secure updates, and decommissioning trigger reassessment; how evidence and unresolved findings remain tied to the affected baseline; and which authority may approve an exception, accept residual risk, or authorize deployment when such a decision is required. State the criteria, prerequisites, restrictions pending a decision, and record needed for each decision; identify an existing decision only by its actual record and affected configuration. |
| Receiving-party assessment or authorization interface | Conditional when supplied project scope, agreement, or decision assigns a security submission, review, or authorization interface to a receiving party | Identify the assigned obligation, planned submission and review products, timing, decision owner, and disposition route for findings or conditions. |
| Terms and protected supporting material | Conditional when specialized terms or sensitive diagrams and contacts are needed | Define necessary terms and point to accessible controlled material without exposing credentials or unnecessary sensitive topology. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Protection objective | One or more established needs or obligations for the selected scope. | State the protected asset, function, data, or stakeholder interest and its source; avoid unsupported conformance claims. |
| Threat or risk input | One or more known inputs, or an explicit method and milestone to establish them. | Tie each to the relevant boundary, assumptions, owner, and decision route; do not present a planned analysis as a completed finding. |
| Security requirement or control | Zero or more established items while selection is pending; the plan must define how material items will be selected and assessed. | For each established item, state its obligation, supporting project need, allocation, or decision with record ID and version, configuration or component scope, parameter values when defined, assessment criterion, responsible role, and selection state. |
| Engineering work item | One or more planned design, build, supplier, or integration activities. | Bind objective or requirement, output, responsible role, dependency, review, and change trigger. |
| Planned security assessment | One route for each established material requirement or control, plus a rule for later additions. | Specify authorized method and target, criterion, expected evidence, assessor, planning state, prerequisites, and the planned response when a later check does not meet its criterion or cannot be concluded. Do not imply testing authority from the plan itself. |
| Vulnerability decision route | One intake-to-decision path for the covered product or service. | Include applicability, urgency, assigned treatment, retest, the authority that may later release or restrict, the required decision record, and the route to incident response when exploitation is suspected. |
| Operational handoff | One route to actual operators or maintainers. | Name configuration, monitoring and update obligations, open findings, restrictions, evidence access, and receiving role; handoff is planned until performed. |

Use prose for the security rationale and roles, a boundary diagram when it clarifies trust relationships, and a mapping table when several requirements, controls, or assessments are in scope. A flow may clarify vulnerability decisions and handoff. Identify an existing project control set or threat analysis by version and locator when appropriate; state the selected obligations and criteria explicitly, and protect sensitive attack details.

## Quality criteria

- Protection objectives, threat assumptions, selected requirements, engineering tasks, and assessments form a traceable chain; candidates and gaps are visible.
- Planned assessment scope is authorized and tied to a controlled target and explicit criterion, with expected evidence and completion conditions identified; existing evidence has its actual locator and assessed configuration.
- Security decision interfaces have explicit prerequisites, criteria, accountable roles, pending restrictions, and required decision records; existing decisions are identified by their actual state and recorded scope.
- Operational monitoring, vulnerability response, and change rules have named responsibility and feed material findings back to design and risk decisions.
- Security obligations on suppliers match supplied agreement scope, assigned engineering responsibilities, required evidence, and actual assessment or authorization rights; proposed commitments remain identified as proposed.
