# Provisioning governance companion specification

## Identity and selection

- **Specification ID:** `PROVISIONING-COMPANION@core`.
- **Purpose:** Define the governance and operational controls around an authoritative provisioning codebase or machine artifact, without restating its executable desired state.
- **Intended readers:** Provisioning maintainers, deployment operators, reviewers, security and change authorities, and people responsible for recovery or deprovisioning.
- **Decision or action supported:** A reader can identify the authoritative source and permitted targets, assess readiness and approvals, follow controlled provisioning stages, verify intended outcomes, and route drift or failure.
- **Use when:** Infrastructure or other resources are provisioned by versioned code or machine artifacts and a human-readable companion is needed for source binding, target restrictions, deployment gates, evidence expectations, drift, and lifecycle controls.
- **Scope boundaries:** Specify source binding, target restrictions, authorization gates, deployment stages, verification, recovery, drift, and deprovisioning controls for the managed resources. Summarize desired-state intent without reproducing executable configuration.

## Authoring inputs and unresolved facts

Inspect the actual provisioning source and its repository or artifact identity, supported toolchain and dependency constraints, desired-state requirements, permitted environment and account selectors, deployment authorization, identity and secret handling, state storage and concurrency controls, validate and deployment stages, review criteria, outcome checks, failure recovery, drift response, and project teardown permissions and retention decisions. Obtain the project's evidence-capture fields, storage locations, access controls, and sensitive-artifact retention periods. Name a real source revision or the rule for binding one at execution; a mutable branch alone cannot prove what code was deployed. Check tool-specific commands against the project's supported version before including them. No particular provisioning stack, provider, or pipeline is assumed.

For unknown or not-established facts, record the gap, effect, resolving action, and owner when known. An unresolved source identity, target boundary, deployment authority, state protection, or destructive-action control MUST make the affected deployment path unready. An unsupported rollback or teardown path needs an explicit prohibition or escalation route, not a guessed command. Mark controls inapplicable only with a reason grounded in the actual architecture. Never include secret values, invent execution observations, approvals, or results, or present a planned verification as a successful result.

## Finished-document contract

- **Title:** Name the provisioning system or resource scope and identify the document as its governance companion.
- **Frontmatter:** None. Begin with the GFM title; source and target binding belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Identify the authoritative source and permitted targets before readiness and stages; put failure, drift, and deprovisioning after the deployment and verification paths. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Source, desired-state boundary, and applicability | Required | Identify the authoritative code or artifact and repository/path, its revision binding rule, managed resource classes, relevant requirements, excluded resources, and which source wins on conflict. Summarize the managed intent and boundary without duplicating executable configuration. |
| Targets, authority, and security | Required | Define allowed account, tenant, environment, region, or resource selectors as applicable; selection and confirmation rules; roles and change authority; identity and least-privilege rules; secret references; and protection of state, plans, logs, and outputs that may expose sensitive data. |
| Readiness and controlled stages | Required | State supported tool and dependency context, backend and lock/readiness checks where applicable, prerequisites, and the ordered stages validate, preview or plan, review, approval, apply, and verify as supported by the actual stack. Describe each of those stages the stack supports. Declare each of those names the stack does not support as `not-used-by-stack` with the stack basis. Do not invent a command for an unsupported stage. Give hold and reapproval rules when source, target, or plan changes. |
| Outcome verification and evidence | Required | Define desired-versus-actual checks, relevant checks of service behavior and stated provisioning controls, unacceptable variance, evidence a later record must capture with source, target, and run identity, and who may decide release or handoff. State the criteria and decision route for unmet or unresolved checks. |
| Failure and recovery | Required | Define conditions that halt an apply, partial-apply handling, recovery or forward-fix options, data or state risks, and decision authority. State rollback limits; an older revision or teardown MUST NOT be presumed to reverse all effects. |
| Drift and controlled change | Required | Define detection or review triggers, distinction between planned change and unexpected drift, investigation and disposition routes, reconciliation authority, and evidence expectations. |
| Deprovisioning | Required | Define whether teardown is supported, prohibited, or decided case by case; the authority and preconditions for any supported teardown; data retention, dependency, credential revocation, outcome checks, and inventory or custody update. A prohibition MUST give an escalation or transition route. |
| Known check limitations | Conditional when a cited prepublication check or inaccessible environment limits confidence in this companion | Identify the check's identity, source revision, context, and the limitation that affects confidence. Include a stable locator for supporting observation evidence when available. State which environments remain untested. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Authoritative source | One codebase or machine-artifact set for this companion, with a stable locator and revision binding rule. | State how an immutable revision is selected for execution; identify relevant module/provider or dependency locks when they affect reproducibility. |
| Desired-state boundary | One bounded description of managed resource classes and excluded or externally owned state. | Identify the actual requirement or design decision and its locator when it establishes the managed scope; summarize the boundary without duplicating executable configuration. |
| Target selector | One or more allowed target classes or explicitly bounded targets. | State how the operator or automation confirms account, tenant, environment, and resource before an apply or destroy. An unspecified production target is invalid. |
| Deployment authority | One actual approval route for each material change stage and destructive action. | Require approval for the source revision, target, and change stage to be applied; a completed plan preview or approval for another revision cannot satisfy this check. |
| State and secret control | One treatment for state or equivalent deployment metadata and one for credentials; additional controls as applicable. | Cover access, sensitive output handling, and concurrency/locking where the stack uses shared state. Never embed credentials or sensitive state snapshots. |
| Stage | One or more ordered, locally identifiable stages with entry check, action, expected artifact or state, and failure route. | Commands are conditional on verified stack and version. For an unsupported readiness-stage name, use `not-used-by-stack` with the actual stack basis and omit execution fields for that name. Do not invent a command for it. Bounded waits/retries and timeout response are required wherever automation waits or retries. State hold and resumption conditions. |
| Verification check | One or more checks against the desired outcome after an apply. | Give the criterion and the evidence a later record must retain. State the route when the observed state does not meet the criterion or the comparison cannot be concluded. Do not substitute a clean plan for observed state. |
| Recovery route | One route for each material partial application or application that stopped before the intended state. | Identify whether revert, repair, forward fix, or escalation is feasible and who may authorize it; account for retained data and irreversible changes. |
| Drift disposition | One monitoring or review trigger and one route for each detected variance. | Distinguish authorized change, error, and unexplained drift; do not silently overwrite manual changes or treat drift as authorized by default. |
| Deprovision decision | One supported, prohibited, or case-specific policy for the managed scope. | If permitted, require dependency and data-retention checks, explicit authority, and post-action confirmation; destruction is never an implicit rollback. |

Use a compact source/target binding table and an ordered stage table or flow with hold points. A decision table is suitable for an apply that stopped before the intended state, for drift, and for deprovision choices. Link to real code and controlled artifacts by stable locator and edition. Include exact commands only when verified for the stated stack and target; otherwise describe the stage and mark the missing method as unready. Do not copy plan output, credentials, blank execution logs, or sample deployments into the companion.

## Quality criteria

- The authoritative executable source and its managed-resource boundary are identifiable, and the companion's intent summary matches that source.
- Source revision, dependency context, target selection, and change authority can be bound to each actual deployment.
- Each validate, preview or plan, review, approval, apply, and verify stage the actual stack supports is distinguishable, and each of those names the stack does not support is declared `not-used-by-stack` with the stack basis. The evidence rule tells a later record what was deployed and what was observed.
- Failure, drift, and deprovision routes respect partial state, data retention, sensitive artifacts, and destructive-action authority.
- Each prepublication limitation identifies the actual check, bound source revision, context, evidence locator when available, and confidence limit. Unsupported readiness-stage names use `not-used-by-stack` with the stack basis and no execution fields.
