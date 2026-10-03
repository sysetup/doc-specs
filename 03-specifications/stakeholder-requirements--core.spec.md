# Stakeholder requirements specification

## Identity and selection

- **Specification ID:** `STAKEHOLDER-REQUIREMENTS@core`.
- **Purpose:** State the stakeholder-visible outcomes, capabilities, use conditions, and constraints required of a defined system of interest, so later validation can judge fitness for intended use before technical obligations are allocated.
- **Intended readers:** Stakeholder representatives, business and mission authorities, systems engineers, and reviewers who agree the expected result or derive system requirements.
- **Decision or action supported:** Readers can judge whose need each stakeholder requirement serves, what outcome is expected under which conditions, whether stakeholders have agreed to the wording, and what technical derivation must address.
- **Use when:** Elicited stakeholder needs, scenarios, constraints, and success measures must become a controlled stakeholder-level set that can feed validation.
- **Scope boundaries:** State stakeholder-visible outcomes and use constraints for the defined system. Include a technical constraint only when an actual stakeholder decision imposes it.

## Authoring inputs and unresolved facts

Obtain the system-of-interest boundary and intended lifecycle use; actual stakeholder groups, roles, and sources of their expressed needs; relevant mission or business objectives; operational activities, environments, users, scenarios, information dependencies, modes, support and retirement concerns; constraints established by stakeholder or project decisions; and the project role that can reconcile competing expectations. Inspect any established success measures, decisions, assumptions, requirement vocabulary, and controlled relationship records. Determine what observation or stakeholder assessment would show each required outcome is met, and whether endorsements or downstream allocations have actually occurred.

If a stakeholder, source, operating condition, success criterion, or decision is unknown, identify the gap, its effect on the affected requirement, the resolving action, and the actual owner if assigned. Distinguish an unelicited expectation from a confirmed absence of need. Mark a disputed or unendorsed requirement as proposed; do not imply that source attribution is endorsement. If a context category is inapplicable after assessment, omit it; explain an exclusion that could affect coverage. Do not invent requirements, stakeholder consent, measures, or validation results, and do not assign `pass`, `fail`, `inconclusive`, or `not-run`.

## Finished-document contract

- **Title:** Name the system or mission subject and identify the document as its stakeholder requirements specification; include scope or edition when needed to distinguish the set.
- **Frontmatter:** None. Begin with the GFM title. Stakeholder identity, obligation state, and authority are substantive body content.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Establish stakeholder and use context before the authoritative obligations; follow them with coverage, unresolved decisions, and control information. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Identity, purpose, and stakeholder boundary | Required | Identify the system of interest, document edition or other unambiguous control identity, included lifecycle/use scope, exclusions, relevant stakeholder groups and their roles, intended outcomes, and actual authority or proposal state. Define terms that affect interpretation. |
| Operational and lifecycle context | Required | Describe the use situations, actors, environment, interactions, information needs, modes, and constraints needed to interpret the obligations. Include scenarios or use cases when they determine conditions, exceptions, or success measures; summarize only pertinent project business rules supplied for the authoring task and identify the actual decision or operating record that establishes them. Do not turn the context into a second requirements list. |
| Stakeholder requirements | Required | State one authoritative stakeholder requirement per distinct stakeholder outcome, capability, quality expectation, or use constraint. Identify its beneficiary or accountable stakeholder, real origin, applicability, observable success condition, and content state. Keep technical allocation and design choices out unless an actual stakeholder authority imposes a constraint. |
| Coverage and stakeholder assessment | Required | Relate the requirements to inspected needs, goals, scenarios, and material constraints; show unresolved conflicts and uncovered expectations. State the intended validation basis for each active requirement, including measures and conditions where established. That basis can feed a later validation; it assigns no result. Cite actual endorsement and its scope only when it exists. |
| Authority, open decisions, and change | Required | Identify who may settle competing stakeholder positions and how the applicable set or baseline is recognized and changed. Record open decisions, effect on requirements, and resolution route. Distinguish review or agreement about requirement wording from later validation of a delivered system and from acceptance. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Stakeholder group or role | One or more real groups or roles whose use, support, oversight, or other project interest drives the set. | Identify each group's interest and relevant lifecycle phase. A project sponsor does not automatically speak for every user or affected party. |
| Stakeholder requirement | One or more distinct stakeholder-level requirements, each with one stable ID unique within the controlled set. | State one stakeholder-visible outcome or constraint, subject, triggering/operating condition, and assessable expectation per statement. Use the project's normative wording consistently. Identify whether the wording is proposed or agreed, and include a technical constraint only when the actual stakeholder decision establishes it. |
| Origin and decision authority | At least one inspected stakeholder need, project decision, or documented derivation per requirement. | Give a usable title/ID, edition and locator when needed; identify the stakeholder or project role that may confirm or resolve the statement. An expectation may be directly recorded here with its origin. |
| Success or assessment basis | One assessable basis for each active requirement, in or beside its statement. | Name the condition, measure, threshold, or qualitative judgment rule a later validation would use. Use units, timeframe, population, and tolerance when material. Proposed values remain visibly proposed. This is an intended validation basis, not a claim that validation occurred, and it does not assign `pass`, `fail`, `inconclusive`, or `not-run`. |
| Requirement content state | One truthful set state, with per-item state when items differ. | Define project terms if used. Distinguish elicited, proposed, agreed, superseded, and rejected wording from system verification, stakeholder validation, and acceptance. Cite an actual decision for an agreement claim. Do not use `validated`, `pass`, `fail`, `inconclusive`, or `not-run` as a content state. |
| Rationale and priority | Rationale when derivation or a constraint is not evident; priority only when used for real scope decisions. | Explain why the outcome matters. Define any priority vocabulary locally; priority does not create or cancel authority. |
| Relationship to system obligations | Zero or more real downstream links per requirement when derivation has occurred. | Identify the linked system obligation or allocated concern without copying it here. An unmade allocation is an open decision, not a fabricated link. |
| Open stakeholder issue | Zero or more conflicting, unconfirmed, or deferred expectations. | State affected stakeholders and coverage, consequence, resolving decision or action, and actual owner if assigned. |

Use prose and focused scenarios for operating context, and a numbered list or table with meaningful ID, stakeholder, statement, source, condition, state, and assessment columns for obligations. A context diagram or flow MAY clarify actors and interactions but MUST NOT be the only authoritative expression of an obligation. A relationship view may support coverage; it is not another master of the requirement text. Do not add generic document-control blocks, empty context categories, or a separate checklist of performed validation.

## Quality criteria

- Each active stakeholder requirement states a stakeholder-visible expectation, has a real origin and project decision authority, and can feed validation without guessing its conditions or measure.
- Coverage includes affected stakeholder classes and relevant lifecycle use, with conflicts, excluded contexts, and unresolved expectations visible. An endorsement claim has an actual decision basis and defined scope.
- Context, scenarios, measures, and downstream links agree with the one controlled statement per stakeholder requirement. Every imposed technical constraint has an actual stakeholder decision basis.
- Proposed and agreed wording are distinguishable. Agreement claims identify the actual decision and scope, and each active requirement has a planned validation basis with explicit conditions and measures.
