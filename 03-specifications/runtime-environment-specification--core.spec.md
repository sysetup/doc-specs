# Runtime environment specification

## Identity and selection

- **Specification ID:** `RUNTIME-ENVIRONMENT-SPECIFICATION@core`.
- **Purpose:** Define the required state and readiness criteria for a bounded development, integration, staging, or production enabling environment.
- **Intended readers:** Environment owners, software and system engineers, operators, security and data stewards, integrators, and readiness reviewers.
- **Decision or action supported:** Configure or procure the intended environment, check whether a particular instance meets its requirements, and identify gaps that prevent its intended use.
- **Use when:** An environment class needs an explicit, controlled target definition covering applicable platform, tooling, data, connectivity, capacity, and access conditions. The same document may record an actual readiness assessment of a named instance when that assessment was made.
- **Scope boundaries:** Cover enabling platform state and readiness for the stated environment class. Detailed test-execution setup and instrumentation are outside this scope.

## Authoring inputs and unresolved facts

Obtain the environment's intended use, supported product or service boundary, class, users, lifecycle stage, supplied project requirements and decisions, and applicable configuration or edition. Inspect actual platform and dependency decisions, needed tools, network or trust separation, data classes and handling rules, capacity expectations, access roles, secret-management arrangements where credentials are needed, and existing project interface definitions. Obtain the conditions under which the environment can be used and who decides readiness; inspect observations only if reporting an actual assessment.

If a required target parameter, threshold, dependency, access rule, or readiness criterion is unknown or undecided, identify the gap, its effect on intended use, the resolving action, and the actual owner if assigned. Mark an undecided choice as proposed; do not present a desired configuration as installed, assessed, or approved. Assess whether tools, separate zones, secrets, or external interfaces actually apply before including their detailed rules. An environment with no project data or no secret-bearing access should state that boundary when its absence affects readiness. Do not place credentials, private keys, or secret values in the finished document.

## Finished-document contract

- **Title:** Identify the target environment and its class as a runtime environment specification; include an edition or configuration identifier when needed to distinguish the target.
- **Frontmatter:** None. Begin with the GFM title. Environment class, target configuration, and any actual readiness state are body content.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Define scope and intended use before required state; place readiness criteria after the requirements and any actual assessment after its criteria. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Environment identity and scope | Required | Identify one bounded target environment, its class, intended use, supported system or software, users, lifecycle context, applicable edition, responsible decision boundary, and material exclusions or assumptions. Distinguish a class-level target from a named deployed instance. |
| Required environment state | Required | State applicable compute, operating-system, runtime, storage, network, and platform characteristics; required versions or capabilities; data sources and handling; capacity, quotas, and scaling limits; access roles and paths; and dependencies or interfaces. Include tooling, distinct deployment or trust zones, monitoring, backup, or secret-management mechanisms when the intended use or supplied project requirements and decisions require them. Specify capabilities and configuration conditions required for readiness, with precise values, ranges, or compatibility rules where they affect readiness. |
| Readiness criteria and use limits | Required | Give assessable criteria for the required state, the configuration to which each applies, the intended check or evidence source, and conditions or limitations on use. State the decision authority for declaring the environment usable. Planned checks specify expected conditions; only actual observations support an assessment. |
| Current readiness assessment | Conditional: include only when the document reports an actual assessment | Identify the assessed instance and configuration, observation time, each criterion actually checked, the evidence, unresolved gaps, conditions, and the actual readiness decision. State for each criterion whether the required condition was met, not met, or not assessed. If no assessment has occurred, omit this section; do not imply one through a preset status. Limit the assessment to the named instance, assessed configuration, and observation time. |
| Change and effectivity | Required | Identify how the applicable target edition is distinguished and how consequential changes to platform, tools, data, capacity, access, or dependencies affect readiness and the parties using the environment. State unresolved decisions and their resolution route. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Environment target and class | One coherent target per finished document; one primary class: development, integration, staging, production, or a clearly defined other class. | Identify supported use and boundaries. The class integration means an enabling environment for integration work. If the same infrastructure serves multiple classes, state the applicable constraints and separation; do not silently treat one class's readiness as another's. A project identifier is included when one exists or is needed for control, without imposing a universal identifier pattern. |
| Required characteristic | One or more assessable configuration or capability rules for every relevant facet of the target. | State the required property, applicability, value or range, units and tolerance where meaningful, version or compatibility constraint where needed, and its supplied project requirement or decision basis. Do not require a product version or platform component that the intended use does not need. |
| Tool or dependency | Zero or more actual required tools, services, or interfaces. | Name the capability and compatible edition or constraint when it matters. Identify external owners and actual project interface definitions when they exist, and state the environment's dependency rule directly. |
| Zone and access rule | At least one applicable rule for who or what may use the environment; add distinct network, trust, deployment, or availability zones when separation matters. | State roles, permitted access paths, least-privilege and boundary controls, and audit or approval conditions that govern use. Describe credential or secret retrieval by controlled mechanism only when needed; never record the secret material. |
| Data rule | One scope-level account of data the environment may store, process, or exchange; detail each relevant data class. | State source, allowed use, volume or lifecycle limits, masking or synthetic-data requirements when applicable, and protection or retention constraints. An assessed absence of project data can satisfy this account. |
| Readiness criterion | One or more distinct criteria for intended use. | For each, state an expected condition and method or evidence basis, including performance limits or security conditions when applicable. A numeric target has units and operating conditions. Do not cite a procedure or observation that does not exist. A cited procedure is not an observation. |
| Readiness observation or decision | Zero or more sourced assessments; include only if performed. | Bind each observation to an instance, configuration, criterion, observation time, and evidence. Say whether that criterion was met, not met, or not assessed. If summarizing the instance, identify the actual decision authority and use `not-assessed` when the recorded assessment did not judge readiness; `not-ready` when required conditions are unmet and prevent intended use; `ready-with-conditions` when use is permitted within explicit limits or outstanding conditions; or `ready` when the criteria for intended use are met. Omit the section when no assessment exists. Do not use `pass`, `fail`, `inconclusive`, or `not-run`. A desired target state alone cannot establish `ready`. |

Use prose for scope, rationale, and limitations. A table is suitable for requirements or readiness criteria when its columns identify facet, required condition, applicability, and check. Use a topology or deployment diagram when zones or dependencies cannot be explained clearly in prose; identify its edition and whether it controls any requirement. State required target rules in prose or tables, using actual configuration or provisioning data to support stated values when available.

## Quality criteria

- Every requirement is tied to the intended environment use and is precise enough to configure or assess; conditional facets are included because they matter to that use.
- Required platform, data, capacity, access, and dependency rules agree with each other and with supplied project requirements and decisions or identified proposals. Version and compatibility limits are clear where different editions could change readiness.
- Readiness criteria check the target state under stated conditions. Actual assessments identify their instance, configuration, observations, and decision; expected conditions remain distinguishable from observed conditions.
- Gaps, limitations, and changed conditions that could invalidate readiness are visible to the responsible users and decision authority.
- No secret values or unverified deployment claims appear in the finished document.
