# Software requirements specification

## Identity and selection

- **Specification ID:** `SOFTWARE-REQUIREMENTS@core`.
- **Purpose:** State the obligations allocated to a defined software item, including its behavior, interfaces, data, quality, operation, and justified constraints.
- **Intended readers:** Software engineers, affected system and interface owners, testers, reviewers, and the authority that controls the software requirements.
- **Decision or action supported:** Readers can determine what the software must do under which conditions, why each obligation exists, and how conformity can be assessed.
- **Use when:** Software-level obligations need a controlled, traceable statement before or during realization and verification.
- **Scope boundaries:** Include obligations allocated to the identified software item. State an implementation choice as a requirement only when an established project decision imposes it.

## Authoring inputs and unresolved facts

Obtain the software item and applicable edition or configuration; its allocated responsibilities and boundary within the larger system; actual users, operating modes, environments, and external interfaces; an established project need, allocated system requirement, or project decision as the basis for each proposed obligation; relevant data and quality concerns; and the project's requirement-control and verification approach. Determine which constraints are genuinely imposed and which implementation choices remain open. Inspect existing project interface or requirements records that control the same obligation, and identify the controlled statement rather than duplicating it.

For an unknown fact, state the gap, its effect on the affected requirement, the resolving action, and the actual owner if assigned. Mark an unmade allocation, threshold, or approval as not established. A direct software obligation may have an identified project need or decision as its basis without a parent requirement ID; do not invent a parent or method record. An inapplicable concern may be omitted after assessment; explain a non-obvious exclusion that affects completeness. A requirement with unresolved behavior, applicability, authorization of its project basis, or verification condition MUST remain visibly proposed and MUST NOT be represented as a baselined obligation.

## Finished-document contract

- **Title:** Identify the software item and document as its software requirements specification; include the applicable edition or configuration where needed to disambiguate it.
- **Frontmatter:** None. Begin with the GFM title. Software scope, requirement status, and authority are substantive body content.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Establish software scope and context before the requirements; place coverage and change information after the authoritative requirement statements. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Identity, scope, and context | Required | Identify the software item, document edition or other unambiguous control identity, its purpose, boundary, included and excluded responsibilities, relationship to the larger system, relevant users, modes, environments, assumptions, dependencies, and material limitations. Identify the authority for the requirement set and its actual decision state without implying approval from the document's existence. |
| Software requirements | Required | Give one controlled statement for each software obligation, with a stable identifier, conditions of applicability, project need, allocation, or decision as its originating basis, and a way to assess conformity. Group requirements by useful concern. Address functional behavior, external interactions, data handling, usability, performance and capacity, reliability and availability, security, operational behavior, deployment or site adaptation, and design constraints when applicable. Do not force empty categories or duplicate a detailed interface obligation in an identified project record. |
| Traceability and coverage | Required | Show how included obligations relate to their inspected sources and any real allocations, interfaces, or downstream verification definitions. Explain how the chosen set covers the allocated software responsibilities and identify gaps, conflicts, or deferred obligations. A link to a real planned method or relationship view may be cited. It cannot replace the requirement statement and does not carry an assessment result. |
| Review, unresolved decisions, and change | Required | Identify unresolved requirements or disputed assumptions, their impact and resolution route; distinguish content review from approval. State how the applicable requirement set or baseline is identified and how a change to it is evaluated and communicated. Include actual endorsement or approval references only when they exist and matter to its status. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Software boundary | One bounded item and allocation context for this document. | State what the software controls, consumes, and exposes, and distinguish its responsibilities from system, hardware, operator, and external-service responsibilities. |
| Requirement | One or more separately identifiable software obligations. | Each has one stable, unique ID; a single assessable obligation; triggering or operating conditions; observable behavior or quality criterion; and a real source or reasoned derivation. Use the project's normative wording consistently. Do not embed solution design unless an authorized constraint requires it. |
| Source and authority | At least one inspected project need, allocation, decision, or explicitly documented derivation for each requirement; identify the project decision authority for derived or disputed content. | Give an ID/title, applicable edition, and locator when needed. A source link explains origin; it does not by itself prove approval. |
| Rationale and priority | Rationale is required for a derived obligation or a non-obvious constraint; priority is conditional when the project uses one to make scope decisions. | Record the reason and actual decision basis. Define any priority vocabulary locally; priority is not a substitute for mandatory wording or authority. |
| Requirement state | One truthful set state, with per-item state when items differ. | State what each state means under the project process. Content review, content approval, product verification, and user validation are different decisions. Do not use `pass`, `fail`, `inconclusive`, `not-run`, or `verified` as a content state. If every item shares one state, state it once. |
| Verification condition | One assessable condition or planned verification basis per active requirement. | Specify the observation a later verification would have to make, with operating conditions, units, and tolerance where relevant. A method may be described directly; reference a separate method or case only if one exists. The condition does not assign `pass`, `fail`, `inconclusive`, or `not-run`. A missing threshold or an undecided method remains a visible gap. |
| Interface or allocation link | Zero or more real links per requirement when another controlled boundary or realization element is affected. | Identify the authoritative interface statement or allocation where one exists, and avoid conflicting duplicate requirements. |
| Deferred obligation | Zero or more obligations allocated to a later edition or another component. | State the boundary, reason, actual disposition authority, and consequence for current coverage; do not silently omit it. |

Use prose for context and rationale, and a numbered list or table with meaningful ID, statement, source, applicability, state, and verification columns for requirements. A diagram MAY clarify a real boundary, mode, or interface, but it MUST NOT carry the only authoritative wording of an obligation. Definitions and references belong at their point of use or in a short dedicated section when readers need them; do not add blank category tables or a generic document-control block.

## Quality criteria

- Every active requirement is within the software boundary, unambiguous, feasible under stated assumptions, internally consistent, and assessable without guessing an expected result.
- Coverage reaches the software responsibilities and relevant quality and interface concerns; genuine exclusions, deferred work, and unresolved allocations remain visible.
- Each controlled requirement statement appears once, and its source, allocation, and planned verification links agree with it.
- Requirement content states accurately identify proposed, reviewed, approved, or superseded wording. Every approval claim identifies the actual decision and its scope; assessment conditions remain planned observations.
