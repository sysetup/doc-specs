# Supplier assurance plan specification

## Identity and selection

- **Specification ID:** `SUPPLIER-ASSURANCE-PLAN@conditional`.
- **Purpose:** Plan how an acquirer or receiving organization will evaluate, govern, assess, receive, and transition specified supplier work against actual agreements and technical acceptance criteria.
- **Intended readers:** Acquisition and technical leads, contracting and supplier managers, quality and specialist assurance roles, receiving or operations teams, and the actual acceptance authority.
- **Decision or action supported:** Coordinate supplier selection or onboarding when pending, requirement flow-down, oversight, issue escalation, delivery assessment, and receiving-party decisions for the supplied scope.
- **Use when:** A defined supplier or acquisition scope requires coordinated technical assurance of supplied items or services. The supplier may be external or another organization with an established supply agreement.
- **Scope boundaries:** Limit assurance activities to the specified supplier work and its receiving interfaces, including specialist checks tied to that scope.

## Authoring inputs and unresolved facts

Obtain the acquisition need and supplied item or service boundary; supplier status and criticality; supplied agreement, statement of work, technical requirements and change authority; explicit quality, security, safety, item-origin, and interface obligations established in supplied agreements or internal project decisions; roles and permitted insight or audit access; selection criteria if selection remains open; planned deliverables and milestones; configuration and data-rights terms; verification and acceptance criteria; nonconformity and dispute routes; transition, support, and retained-record needs. Identify each agreement, requirement, or decision used by origin, revision, locator, and binding, proposed, or informative state.

Mark missing facts unknown and proposed agreement terms not established, with their effect, resolving action, and actual owner if assigned. If the supplier is already selected, document the established selection basis or known qualification limits and omit a fictional future competition. If no enforceable access, notification, or evidence right exists, expose the assurance gap and route it to the real contracting authority; do not make the plan itself grant the right. An unresolved deliverable, acceptance criterion, receiving decision authority, or essential evidence access prevents a claim that the affected delivery is ready for acceptance. Do not invent supplier commitments, audit outcomes, rights, or decisions.

## Finished-document contract

- **Title:** Identify the acquisition or supplier scope and name its supplier assurance plan.
- **Frontmatter:** None. Begin with the GFM title. Agreement state and assurance responsibility are body content.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Establish scope and agreement state before oversight; place delivery assessment before receiving decision and transition. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Acquisition scope and authority | Required | Define supplied items or services, boundaries, criticality and affected interfaces, supplier or selection state, actual agreement and revision or proposal status, acquirer and supplier roles, decision rights, planned milestones, and material exclusions. Distinguish technical reviewers from the authority that can change terms or accept delivery. |
| Selection and due diligence | Conditional when supplier selection, renewal, or qualification remains to be decided | State applicable evaluation criteria, evidence, evaluators and decision authority, with proportionate quality, security, safety, capacity, and supply-chain risk checks. If selection is complete, record only the established basis or known limits in the scope section. |
| Obligations, deliverables, and flow-down | Required | Map each material supplied output or service to its actual or proposed requirements, interfaces, configuration and evidence obligations, acceptance criterion, delivery point, and responsible party. Identify which terms bind the supplier and which still require negotiation or contractual action. Include subcontractor flow-down only when applicable. |
| Oversight and issue control | Required | Plan progress and technical reviews, permitted audit or inspection access, evidence review, change and deviation routes, nonconformity and corrective-action escalation, and notification of material incidents or supplier changes when an established project obligation requires it. Address authenticity and item-origin checks when item type and risk justify them, identifying required origin or custody evidence, the review method, criteria for accepting that evidence, and the route for unverifiable or suspect items. State the evidence and criteria used to assess conformity. |
| Delivery assessment and receiving decision | Required | Define how the receiving organization will later check item identity, configuration, delivery integrity, documentation, cited verification records, open defects, and agreed acceptance criteria; who records findings; who may accept, reject, conditionally receive, or seek a contract change under actual authority; and how unresolved conditions are tracked. Identify the receiving-party decision, required assessment evidence, and authorized deciding role separately from supplier declarations. |
| Transition, support, and records | Required | Plan handoff to integration or operation, access to necessary data and rights, support and update obligations, continuity or exit arrangements when relevant, and custody and retention of required records. State what happens to open issues at handoff or supplier exit. |
| Specialist assurance interface | Conditional when explicit safety, security, or independent quality obligations are established for the supplied scope | State each obligation and its supplied agreement or internal project-decision basis, assigned reviewer, assessment criteria, required evidence, timing, and effect on delivery or acceptance. Identify unresolved criteria or access as assurance gaps. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Supplier scope | One bounded acquisition or supplier relationship; several suppliers may be covered only if their duties and decisions remain distinguishable. | Identify supplied item or service, technical boundary, status, and receiving organization. |
| Agreement or project decision | One or more supplied agreements, proposals, project requirements, or authorized internal decisions. | Label each as binding, proposed, or informative; give revision, locator, and decision authority. Mark a proposed change to an agreed term as pending until the role with change authority approves it. |
| Deliverable-to-obligation mapping | One entry for each material supplied output or service obligation. | Show requirement source, configuration or interface, due point, expected evidence, acceptance criterion, and responsible party; expose gaps rather than inventing terms. |
| Supplier evaluation | Conditional for pending selection, renewal, or qualification. | Use established criteria and authorized process; a selected supplier does not need a fictional selection exercise. |
| Oversight activity | One or more proportionate reviews, inspections, audits, or evidence checks. | State purpose, timing or trigger, access basis, reviewer, expected record, and escalation; an audit right must come from the actual arrangement. |
| Delivery decision route | One planned receiving-party decision route for each deliverable or acceptance unit. | Separate supplier completion, a later technical check, receipt, conditional use, formal acceptance, and payment or contract action where they differ; identify the evidence and deciding role for each decision. |
| Open issue and exit route | One route for nonconformities and for handoff or supplier exit. | Name containment or restriction, correction authority, evidence, recheck, receiving owner, and retained-record access. |

Use a deliverable-to-obligation table when several outputs or criteria exist, with columns for agreement or project-decision basis and state, supplier duty, expected evidence, receiver check, criterion, and decision owner. Use a schedule or flow when selection, reviews, delivery, and transition have dependencies. Prose should explain authority, risk-based oversight, and exception handling. Identify the locator and revision of each supplied agreement used and state the concrete obligations relevant to the supplied work.

## Quality criteria

- Every planned supplier check has an established agreement or internal project-decision basis or an explicit proposed-term status, a feasible access route, and an owner; unresolved rights are visible and routed to the role that can establish them.
- Oversight is proportionate to supplied criticality and risk, and specialist safety, security, quality, or item-origin checks have explicit scope, criteria, evidence, and reviewers.
- Deliverables, configurations, evidence, criteria, nonconformities, and receiving decisions remain linked through changes and handoff.
- Supplier claims, acquirer verification, physical or service receipt, contractual acceptance, and plan approval remain separate facts.
- Open issues and support or exit duties have a planned route with an owner, required evidence, and disposition criteria.
