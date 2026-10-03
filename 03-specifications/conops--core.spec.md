# Concept of operations specification

## Identity and selection

- **Specification ID:** `CONOPS@core`.
- **Purpose:** Explain how an envisioned system will be used and supported to achieve a stated mission or stakeholder outcome across relevant operating conditions.
- **Intended readers:** Stakeholders, users, operators, maintainers, system engineers, and people deciding whether the proposed operational concept meets their needs.
- **Decision or action supported:** Agree on the intended operating model, expose gaps and constraints, and develop or assess subsequent requirements and architecture.
- **Use when:** A project needs a stakeholder-facing account of intended operation, human and system roles, scenarios, modes, environment, and support before or while design is refined.
- **Scope boundaries:** Describe intended operation, roles, conceptual exchanges, and support at the level needed to understand the operating model. Keep scenario steps conceptual and detailed implementation parameters or operator instructions outside that level.

## Authoring inputs and unresolved facts

Obtain the actual problem or mission basis; affected stakeholder groups and intended users; the system of interest and its boundary; current and proposed operating context; desired outcomes; known project constraints and assumptions; external systems and human roles; credible normal and disrupted situations; relevant environments; and support and lifecycle expectations. Inspect supplied project observations, stakeholder accounts, and decisions directly, identifying their origin and the scope they establish.

If a role, condition, operational response, success measure, or support assumption is unknown or has not been agreed, state what remains open, its effect on the concept, and the next resolving action and actual owner if assigned. Label a proposed concept as proposed. Keep expected outcomes, planned capabilities, and scenario steps labeled as intended; mark any unagreed role, target, or commitment as proposed. Treat genuinely inapplicable lifecycle or impact topics briefly with a reason; do not fill them with invented project facts.

## Finished-document contract

- **Title:** Identify the system or capability and the document as its concept of operations.
- **Frontmatter:** None. Begin with the GFM title. Scope and concept maturity belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Establish the need and boundary before describing the envisioned operation; present scenarios after roles, modes, and interactions; conclude with implications and unresolved issues. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Purpose, basis, and scope | Required | State the problem or mission, intended outcomes, operational decision scope, system boundary and exclusions, concept maturity, known constraints, and material assumptions. Distinguish current operation from envisioned operation when both are discussed. Identify confirmed project decisions and established operating or delivery constraints separately from assumptions and background information. |
| Operating context and participants | Required | Describe users, operators, support roles, external systems, enabling services, and their responsibilities and interactions across the boundary. Explain the operational capabilities and human versus system contributions without prematurely specifying the implementation. |
| Modes, conditions, and environment | Required | Explain materially different operating states or modes, triggers and transitions, relevant operating and support environments, and the conditions under which the system is expected to operate, degrade, or survive. If formal mode distinctions are unnecessary, say how operation and interruption are understood. |
| Operational scenarios | Required | Provide representative time-ordered nominal scenarios and credible off-nominal or degraded situations that expose materially different behavior, human decisions, conceptual exchanges, recovery, or safety concerns. State the intended outcome of each and any unagreed target as proposed. Leave an unresolved coverage gap visible when a material situation cannot yet be described. |
| Support and lifecycle concept | Required | Describe how deployment, training, staffing, maintenance or other support, changes, and retirement affect the envisioned operation where relevant. State the expected support responsibility and dependencies; do not turn these concepts into a task schedule or a commitment not yet authorized. |
| Impacts, operational success, and open issues | Required | State how stakeholders would recognize intended operational success, relevant organizational, environmental, or scientific and technical effects, key operational risks and assumptions, and decisions or information still needed. Express each success indication as an intended recognition condition. Distinguish predicted impact from observed effect. State any decision accepting residual exposure only with its actual decision maker, scope, and project-record locator; otherwise leave its disposition open. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| System and boundary | One coherent system or capability scope per document. | Name what lies inside and outside the concept, including external people, systems, and enabling services. Do not imply that an external party is controlled by the system. |
| Outcome and success indication | At least one sourced intended outcome and a way stakeholders could recognize it. | Use stakeholder language and observable conditions where known. Identify the originating project need, stakeholder statement, or decision by usable identity and locator. An undecided target is proposed or open; state the target's actual agreement scope and describe it as intended. |
| Participant and responsibility | Each role or external party material to a scenario or support arrangement. | State what the participant supplies, receives, decides, or supports in the envisioned operation; separate a proposed role from an agreed one. |
| Scenario | One or more nominal paths plus each identified materially distinct off-nominal path needed to understand the concept. | Give a stable label when cross-reference helps, the starting condition or trigger, actors, significant sequence and conceptual exchanges, mode changes, intended outcome, and relevant assumption or gap. Describe the path as envisioned operation, with material human decisions, recovery actions, and safety conditions at that level. |
| Operating condition or mode | Each condition or state that changes expected behavior or responsibility. | Identify entry, exit, and transitions where they matter; distinguish expected normal operation, degraded operation, and mere survival where the environment warrants those distinctions. |
| Source or assumption | Every material project decision, constraint, premise, or prediction used to justify the concept. | Identify the supplied project fact, observation, stakeholder account, or decision and its edition or locator when one exists. State who must resolve an unsupported premise. |

Use prose and a small set of named scenarios as the main form. A context diagram, timeline, interaction flow, or mode/state diagram SHOULD be included when prose alone leaves actors, exchanges, or transitions ambiguous. Use tables for role responsibilities, operating conditions, or scenario coverage when they make comparisons clearer; do not force separate acronym, glossary, or document-control appendices.

## Quality criteria

- The scenarios collectively cover the stated mission, principal conceptual exchanges, human decisions, support dependencies, and known consequential abnormal conditions at the declared concept maturity.
- The operating boundary, role allocations, modes, conditions, and expected outcomes agree across the context description and scenarios.
- The concept stays at intended-use level; current operation, proposed roles or capabilities, agreed operating expectations, and predicted effects retain their stated basis and maturity.
- Material uncertainties and competing stakeholder expectations remain visible with their operational consequence and resolution path.
