# Software design description specification

## Identity and selection

- **Specification ID:** `SOFTWARE-DESIGN-DESCRIPTION@software`.
- **Purpose:** Define the design of a bounded software item so implementers can realize its responsibilities, interfaces, data, behavior, deployment, and failure handling against its allocated project obligations.
- **Intended readers:** Software designers and implementers, integration and operations engineers, security and test reviewers, and maintainers.
- **Decision or action supported:** Implement or review the software item, coordinate module and interface contracts, and assess design coverage and change impact.
- **Use when:** A software item needs implementation detail for modules, data, algorithms, runtime behavior, or deployment configuration.
- **Scope boundaries:** Cover the software item's responsibilities and implementation choices, with its boundary to hardware, people, and services stated explicitly.

## Authoring inputs and unresolved facts

Obtain the software-item boundary and actual project requirement or decision basis; inherited architecture and allocated interfaces if they exist; module responsibilities; input, output, and data ownership; relevant behavior, state, algorithms, dependencies, and deployment assumptions; and quality, security, resilience, observability, support, and verification concerns. Inspect supplied project designs, schemas, configurations, and code editions when they exist.

If an interface contract, data rule, algorithm, dependency version, operational assumption, or responsibility is undecided, mark the design portion as proposed or unresolved, state its effect, and give the next resolving action and actual owner if assigned. Do not infer that a described module is implemented, deployed, secure, or tested. Identify supplied project requirements and interface definitions by stable identity and edition; state design choices and their basis without altering the cited obligation. A preimplementation design may refer to planned artifacts; source-code paths, hashes, and deployed versions are included only when real and relevant.

## Finished-document contract

- **Title:** Name the software item and identify the document as its software design description.
- **Frontmatter:** None. Begin with the GFM title. Design maturity and applicable versions belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Establish scope and basis before module detail; describe interfaces, data, and behavior before deployment and change implications. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Software scope and design basis | Required | Identify the software item, external boundary, applicable configuration or maturity, supplied software requirements or allocated system obligations, architectural constraints, runtime assumptions, and editions of the project records used as a design basis. Separate approved choices from proposals. |
| Components and responsibility allocation | Required | Define significant modules, services, processes, or other software elements, their responsibilities and dependencies, and how they collectively carry the allocated project obligations. Cite each supplied obligation by identity and edition without duplicating its wording. Identify ownership of cross-cutting behavior rather than assigning the same responsibility ambiguously to several components. |
| Interfaces and data | Required | Define provided and required interfaces, inputs and outputs, data meaning and ownership, relevant schemas or formats, input checks, persistence and lifecycle, and compatibility rules. Include identity, trust, authorization, and error semantics where they affect a boundary. For supplied project interface or error definitions used, give identity and edition and state which definition controls each affected design choice; identify conflicting definitions as unresolved. Describe the software item's intended interface behavior. |
| Behavior and algorithms | Required | Explain significant processing flows, state and mode transitions, concurrency, timing, resource use, and error or recovery behavior. Describe algorithms and decision rules at the detail needed for consistent implementation; omit trivial algorithm narration. Show how abnormal inputs or dependency failures are handled where material. Describe intended behavior and expected effects. |
| Runtime and deployment design | Conditional — when execution depends on deployment topology, configuration, platform services, or external dependencies | State process or service placement, dependency and configuration assumptions, version compatibility, startup or shutdown behavior, data migration or rollback implications, and operational observability relevant to the software item. Label assumptions as intended deployment conditions and cite the actual project environment configuration used as their basis when available. |
| Rationale, assurance, and open design issues | Required | Explain consequential choices and tradeoffs; address relevant performance, security, reliability, maintainability, and testability implications; identify uncovered obligations, unresolved contracts, assumptions, and change impacts. Link actual analysis or test evidence only when available, and distinguish it from intended checks. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Software item and basis | One bounded software design scope and at least one real project obligation or decision basis. | Identify the project origin and edition when available; if approval of the basis is unsettled, label it as proposed. Cite the obligation without duplicating its wording. |
| Software element | One or more identifiable modules, services, processes, or comparable units. | For each, state responsibility, interfaces and dependencies, relevant design basis, and significant rationale. Identify the project obligations allocated to the element. Parent-child decomposition must be acyclic; do not create artificial modules or identifiers to fill a list. |
| Interface contract | Each externally visible or cross-element interaction material to implementation. | Identify provider and consumer, direction, inputs and outputs, input checks, failure behavior, and version or compatibility rule as relevant. A named API alone does not define its behavior. Define the conditions under which input checks accept or reject data. Cite actual project interface definitions used by identity and edition, preserving their stated meaning. |
| Data definition and ownership | Each persistent or exchanged data structure whose semantics affect behavior or compatibility. | State meaning, schema or format and edition, source of truth, integrity or retention rule, and migration or deletion behavior when relevant. Keep derived and authoritative data distinct. |
| Behavior or algorithm | Each nontrivial processing rule, state transition, or failure path needed for consistent implementation. | Specify inputs, conditions, effects, limits, and ownership. Identify the supplied project constraints used; do not claim an algorithm's performance or correctness without actual evidence. |
| Dependency or runtime configuration | Each platform, library, service, or configuration choice that materially constrains implementation or operation. | Identify the intended version or compatibility range when decided and the responsible boundary. Use supplied version-specific API and product facts; mark uncertain behavior unresolved. |

Use a component/dependency diagram, interface or data table, sequence or state diagram, or focused pseudocode when it clarifies a consequential interaction or algorithm. State diagram meaning and versioned source when one controls implementation. Use prose to explain responsibility and design intent; cite real project schemas, code, or configuration by identity, edition, and locator when present rather than copying them wholesale.

## Quality criteria

- Allocated project obligations have a plausible design path through named components, interfaces, data, and behavior. Unallocated or speculative features remain visible.
- Interface contracts, data ownership, error paths, and runtime assumptions agree across component descriptions and with any separately controlled source.
- Security boundaries, failure behavior, concurrency, resource limits, and deployment concerns are covered where they affect the software's actual job.
- Proposed choices, approved choices, intended behavior, and any actual implementation, test observations, or acceptance decisions retain their stated maturity and evidential basis.
- The detail supports consistent implementation and review at the claimed maturity without forcing source-file hashes or platform choices that have not been established.
