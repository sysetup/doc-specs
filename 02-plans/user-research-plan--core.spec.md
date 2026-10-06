# User research and discovery plan specification

## Identity and selection

- **Specification ID:** `USER-RESEARCH-PLAN@core`.
- **Purpose:** Plan exploratory research into unknown user needs, behavior, and operating contexts.
- **Intended readers:** Researchers, analysts, product owners, designers, research operations, and privacy or ethics reviewers.
- **Decision or action supported:** Decide which questions to investigate, how to recruit and collect information, and whether a research round is ready.
- **Use when:** Unknown user needs or contexts require a bounded discovery effort.
- **Scope boundaries:** Arrange exploratory discovery and its access, analysis, and evidence handling; exclude established-solution fitness assessment, participant notices, collection instruments, and observed findings.

## Authoring inputs and unresolved facts

Obtain the decision to inform, known evidence and unknowns, lifecycle position, user or stakeholder population, setting, recruitment access, constraints, proposed methods and instrument editions, analysis strategy, resources, responsibilities, and actual privacy, ethics, and permission requirements.

Expose each unknown population, permission, data arrangement, method, or decision right with its consequence, resolving action, and assigned owner or assignment gap. Keep choices proposed until established. Unresolved safe access, consent arrangements, or sensitive-data protection block the affected collection; unknown recruitment feasibility limits readiness. Do not invent participants, permissions, responses, or findings.

## Finished-document contract

- **Title:** Identify the discovery subject and name its user research and discovery plan.
- **Frontmatter:** None. Begin with the GFM title. Identity, scope, and state belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State the decision and questions before population and methods; establish access and protection before scheduling collection; put analysis, sharing, and replanning last. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Purpose, scope, and questions | Required | Identify the subject, intended decision, lifecycle phase, setting, known basis, exclusions, and separately identifiable research questions. Include the client or receiving-party element. Distinguish exploratory questions from a solution's acceptance criteria. |
| Population and recruitment | Required | Define included groups or source corpus, selection rationale, exclusions, recruitment route, planned sample or stopping rationale, representativeness limits, and accessibility needs. Identify missing perspectives without inventing representation. |
| Methods and instruments | Required | Map each question to collection method, instrument edition or instrument-development gap, planned context, capture route, and responsible role. Explain why the method can answer the question; planned outputs have no observations or results. |
| Access, ethics, and data handling | Required | State permission and ethics review applicability, consent and withdrawal arrangements for human participation, recording choices, minimization, access, sharing, retention and deletion rules, sensitive-data handling, and suspension conditions. Link actual participant information when available. |
| Rounds, resources, and readiness | Required | Plan rounds, responsibilities, resources, timing, dependencies, and entry, stop, and resumption conditions. Distinguish a recruitment target from confirmed participation and a plan from authorization. |
| Analysis, communication, and upkeep | Required | Define how sources will be interpreted, contradictions retained, uncertainty bounded, and findings shared with decision makers. State update ownership and triggers from changed questions, access, populations, or evidence. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Research question | One or more questions in Purpose, scope, and questions. | Each names an unknown and the decision it informs; do not require a pre-established solution or favorable outcome. |
| Population and sample | Exactly one bounded population or corpus; one selection rationale per included group. | Population and recruitment specifies planned counts or stopping rules and unrepresented groups; targets are not attendance. |
| Method mapping | One per research question in Methods and instruments. | Connect question, method, instrument or gap, context, capture, and responsible role; do not assign execution results. |
| Access and protection arrangement | One per collection context in Access, ethics, and data handling. | Define what must be established before collection; distinguish participant information, actual consent, organizational access, and ethical review. |
| Research round | One or more planned rounds in Rounds, resources, and readiness. | Each identifies prerequisites, resources, timing or scheduling gap, and an explicit stopping or replanning route. |
| Analysis and sharing route | Exactly one strategy in Analysis, communication, and upkeep. | Specify evidence-to-interpretation handling and permitted audiences; discovery findings cannot establish statistical generalization without a supporting design. |

Use connected prose and a question-to-method table when several questions differ. Cite separately controlled instruments and participant information by edition when available; state the planned method directly when no separate record exists. The plan controls proposed arrangements, while later collection and findings records control observations.

## Quality criteria

- Questions, population, and selection rationale identify the unknowns and unrepresented contexts the effort will examine.
- Every question has a method and instrument route or an explicit gap; no planned observation is presented as acquired.
- Permissions, consent arrangements, accessibility, and data handling agree with collection; missing critical arrangements prevent readiness.
- Rounds have resources, roles, dependencies, and stopping conditions; targets do not imply participation or authorization.
- Analysis, permitted sharing, uncertainty, and update triggers preserve discovery evidence and decision boundaries.
