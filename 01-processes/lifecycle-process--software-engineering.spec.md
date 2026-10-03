# Software engineering lifecycle process specification

## Identity and selection

- **Specification ID:** `LIFECYCLE-PROCESS@software-engineering`.
- **Purpose:** Define the reusable process by which software work is developed, integrated, assured, controlled, released, and maintained.
- **Intended readers:** Software engineers, technical leads, assurance and configuration roles, release authorities, and maintainers who use or govern the process.
- **Decision or action supported:** A team can identify the required software workflow, work products, decision gates, evidence expectations, and handoffs for a software change or release.
- **Use when:** Common software lifecycle rules must guide multiple projects, products, or iterations within a defined organizational scope.
- **Scope boundaries:** Define recurring software activities, work-product requirements, decision criteria, controls, and handoffs for the covered lifecycle.

## Authoring inputs and unresolved facts

Obtain the software item and lifecycle scope, supplied project needs and decisions establishing software obligations, actual process owner, software decision rights, development and integration methods, explicit quality and security criteria, configuration and build controls, release and maintenance routes, work-product and evidence requirements, and interfaces to systems engineering, V&V, suppliers, operations, and retirement. Identify the project basis for each adopted obligation and assigned decision right. Inspect the existing tools and control systems only where their behavior determines a repeatable process rule.

For unknown facts, identify the gap, effect, resolving action, and owner if assigned. A future method or decision authority must be labeled proposed until established. Where a specialty activity is genuinely outside scope, explain the scoped reason and the actual route that covers its needed outcome. If the required decision rights, integration boundary, or release control remain unsettled, mark the process unsuitable for authoritative use. Do not invent reviews, tests, build results, release approvals, or maintenance history.

## Finished-document contract

- **Title:** Name the software engineering lifecycle process and applicable software or organization scope.
- **Frontmatter:** None. Begin with the GFM title; process edition and applicability are body content.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State scope and authority before the activity flow, then cross-cutting controls and process evolution. Headings may use local wording.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Purpose, authority, and applicability | Required | Define the reusable software work covered, process owner, applicable lifecycle and item classes, the project needs and decisions establishing software obligations, truthful edition or state when controlled, and handoffs to system-level or external participants. State exclusions and how local tailoring is decided. |
| Development and integration flow | Required | Describe how a sourced change or obligation enters design and construction, how work is reviewed and built, how components are integrated with controlled interfaces, and how integration readiness and anomalies are assessed. State roles, inputs, outputs, completion criteria, and return loops without imposing a single development model. |
| Assurance and configuration control | Required | Define software review, analysis, test, security or quality checks as applicable; the explicit criteria and evidence needed to assess them; and how source code, dependencies, build inputs, generated artifacts, and changes remain identifiable and controlled. Identify V&V and configuration management handoffs, including the exchanged information and responsible roles. |
| Release and maintenance | Required | Define release candidate composition, readiness assessment, decision authority, packaging and handoff, and what a later release record must capture. Describe maintenance intake, impact and risk review, controlled implementation, regression, re-release, and a retirement interface when relevant. Distinguish a release decision from deployment or user acceptance. |
| Process feedback and change | Required | State what a later record retains, how deviations and escaped defects feed correction, how effectiveness is reviewed, and who can approve or tailor a process change. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Software work path | One connected path from authorized intake through development, integration, assessment, release decision, and maintenance feedback. | Iteration and parallel work are allowed; define entry, hold, rework, and exit rules where they affect control. |
| Process activity | One or more activities with a local label when referenced. | Give action and intended output, responsible role, entry condition or input, completion criterion, method or control, and recipient or next action. A subject may contain several activities. |
| Assurance obligation | One or more applicable forms of review, analysis, test, or other check. | State who performs or judges it, the explicit criterion applied, what observations and limitations a later check must record, and the route when the check does not meet its criterion or cannot be concluded. |
| Controlled build or configuration | One rule for identifying the software and dependencies used in an assessment or release. | The required detail depends on reproducibility and integrity needs; do not force a tool, hash, branch model, or deployment pipeline without project basis. |
| Release decision | One route from candidate through readiness assessment to authorized release and handoff. | Separate recommendation, decision, packaging, deployment, and acceptance; identify the actual decision required for each controlled transition and the record that captures it. |
| Maintenance route | One route for defect or change intake, impact assessment, implementation, regression, and disposition. | Include escalation and support or retirement handoff where relevant. Require change authorization before controlled implementation. |
| Tailoring rule | Conditional where local process variation is allowed. | Name authority, affected obligations, rationale, consequences, and the later record that captures the decision. Require the designated authority's decision before a variation takes effect. |

Use a lifecycle flow, decision table, or concise activity table with roles, inputs, outputs, criteria, and handoffs. Prose is suitable for governing rules. Diagrams and named tools are conditional on their usefulness and actual adoption; no native companion is required.

## Quality criteria

- Development, integration, assurance, configuration, release, and maintenance each have usable entry, decision, and output rules; supporting records are identified where needed.
- A change can be traced to the assessed software configuration and release decision without treating a planned test or review as an observed result.
- System-level, V&V, configuration, and operations interfaces identify the exchanged information, responsible roles, and handoff criteria.
- Release and maintenance controls state the route when an assessment does not meet its criterion or cannot be concluded, and they cover urgent fixes and regression where applicable.
