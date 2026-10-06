# Research participant information specification

## Identity and selection

- **Specification ID:** `RESEARCH-PARTICIPANT-INFORMATION@core`.
- **Purpose:** Explain a planned study and its participation and data arrangements to prospective participants.
- **Intended readers:** Prospective research participants and any representatives established for the study.
- **Decision or action supported:** Decide whether to participate and how to ask questions, decline, or exercise established withdrawal options.
- **Use when:** Research involving people needs information before their participation decision.
- **Scope boundaries:** Provide advance participant-facing information for one study; exclude internal research planning, evidence of consent, invented legal rights, and proof of participation.

## Authoring inputs and unresolved facts

Obtain the study identity and responsible organization or role, purpose and invited population, activities and duration, actual recording choices, established effects and compensation, voluntary participation, category-specific data uses, recipients, retention and deletion, withdrawal limits, real contact routes, notice edition, and required accessible delivery. Obtain the risk- and audience-bound retrieval and understanding criterion, any checked equivalent edition, and actual assessment evidence or its absence.

Expose missing activity, contact, recording, data-use, retention, withdrawal, accessible delivery, or required assessment facts with their consequence, resolving action, and assigned owner if known. A draft may show gaps; unresolved material arrangements or unmet required delivery and understanding checks prevent participant-facing readiness for the affected decision. Do not invent confidentiality guarantees, compensation, approvals, legal rights, consent, reachable contacts, or participant comprehension.

## Finished-document contract

- **Title:** Name the study and identify the document as information for prospective research participants.
- **Frontmatter:** None. Begin with the GFM title. Identity, scope, edition, and readiness belong in the body. Governing source: Type-owned policy in RESEARCH-PARTICIPANT-INFORMATION@core; no external metadata schema is selected.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Explain study identity and activities before participation choices; put data and withdrawal information before contacts and edition applicability. Heading wording may vary.
- **Presentation:** Use short participant-facing paragraphs, meaningful headings, and concise lists; combine roles where choices remain easy to find. Keep internal assessment details in their actual evidence record, with only the edition's use limits in the notice.

| Projection | Title and metadata ownership | Syntax and source authority |
|---|---|---|
| Standalone information (standalone) | The document owns one descriptive H1. Identity and edition are body facts; no YAML frontmatter is supplied. | Use GFM for the written edition. Bind this written notice to the study's sourced arrangements and the edition actually supplied. A checked oral, translated, or accessible equivalent retains those meanings and identifies its relationship to this edition; it is not a separate source of consent or data terms. Changed arrangements or delivery content require a new applicability and readiness assessment. |

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Study identity and purpose | Required | Explain the study, responsible organization or role, purpose, who is invited, intended use of findings, and client or receiving-party element in language the prospective participant can understand. Integrate the client relationship or no-external-client statement into ordinary study context. |
| Activities, recording, and effects | Required | Describe what participation involves, location or medium, expected duration, tasks or questions, recordings and optional choices, known discomfort or risks and expected benefits without promises. State compensation only when offered under established terms. |
| Voluntary choice and stopping | Required | Explain how to accept or decline, skip where permitted, stop participation, and raise concerns. State any established consequences of declining; do not imply that reading this information or attending establishes consent. |
| Data use, sharing, and retention | Required | Describe collected data, identifiers, recording uses, who can access material, permitted sharing or publication, confidentiality limits, protection, retention and deletion arrangements, and re-use only where actually arranged. |
| Withdrawal, questions, and applicability | Required | Give actual contact and withdrawal routes, timing limits, and what can and cannot be removed after anonymization, pooling, or publication when applicable. Identify accessibility support, the notice edition actually supplied, and any checked equivalent delivery edition. State material gaps and whether the edition is draft, not-ready, or ready-for-participant-use for the stated audience and delivery mode. Identify the required observable retrieval and understanding check and actual assessment status or evidence route; internal detail may remain in its actual record. A favorable disposition requires established material arrangements, usable delivery, and satisfied required checks; information supply, author review, or an available contact alone does not establish comprehension. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Study and notice edition | Exactly one study and one notice edition in Study identity and purpose and Withdrawal, questions, and applicability. | Bind applicability and any readiness claim to the edition actually supplied and the study arrangement sources; the notice is information rather than a consent record. A changed arrangement reopens affected assessment. |
| Participation activity | One or more activities in Activities, recording, and effects. | State expected duration and recording choices; do not imply unsupported risk-free participation or guaranteed benefit. |
| Participation choice | One or more established choices in Voluntary choice and stopping. | Explain accept, decline, and stop routes and applicable limits without inventing rights or institutional commitments. |
| Data arrangement | One account per collected data category in Data use, sharing, and retention. | Identify use, permitted audience, identifiability, retention, and deletion; pseudonymized material is not automatically anonymous. |
| Contact and withdrawal route | One or more actual routes in Withdrawal, questions, and applicability. | Include reachable channels and established timing and removal limits; explain the effect of pooling or anonymization only when arranged. Unknown routes prevent participant-facing readiness; a placeholder is not a reachable contact. |
| Retrieval and understanding assessment | Exactly one audience-, risk-, and edition-bound criterion and assessment account in Withdrawal, questions, and applicability; zero or more actual evidence citations. | Check whether a prospective participant can locate the activities, recording choices, data use, voluntary and stopping options, withdrawal limits, and contacts, and explain the material choices or consequences accurately using the supplied edition and delivery mode. Record the actual assessment method, context, observations, outcome and limitations, or that it has not occurred and the resolving action. Set evidence sufficiency for the context; planned checks and author-only inspection do not establish participant understanding. Failed or unresolved required checks prevent favorable readiness. |
| Equivalent delivery edition | Zero or more oral, translated, or accessible equivalents identified in Withdrawal, questions, and applicability when needed or supplied. | Bind each equivalent to the written edition and arrangement sources; check preserved meaning, activities, recording, data, choices, withdrawal, contacts, and usable delivery for the intended audience. Preserve material limits in the supplied equivalent. Unknown equivalence or delivery feasibility prevents its use; an equivalence check alone does not establish comprehension. |

Use short plain-language paragraphs, meaningful headings, and concise lists of activities, data uses, and choices. Present the client element as ordinary study context. Cite actual assessment evidence without burdening participants with internal protocols; include the concrete use limit when a required check remains unresolved. Check oral, translated, or accessible equivalents against the supplied edition when needed. Signed or recorded consent remains a separate actual permission record tied to the notice edition; receipt, attendance, or an understanding check is not consent.

## Quality criteria

- Study identity, audience, purpose, and notice edition are understandable and grounded in actual arrangements.
- Activities, recording choices, duration, effects, and offered compensation reflect the study without unsupported assurances.
- Voluntary choices and stopping routes are explicit; information delivery is not presented as consent.
- Data uses, recipients, identifiability, protection, and retention are specific enough to inform participation.
- Contacts and withdrawal limits are usable, accessible, and established; unresolved material arrangements block use.
- Using the supplied edition and delivery mode, a prospective participant can locate the activities, recording choices, data use, voluntary and stopping options, withdrawal limits, and contacts and explain their material consequences. A comprehension claim cites an actual assessment; not-performed, failed, or limited assessments and their readiness consequences remain explicit.
- Any oral, translated, or accessible equivalent preserves the sourced arrangements and identifies its checked relationship to the applicable notice edition; its delivery feasibility and unresolved checks are visible. Author review, information delivery, and comprehension assessment never substitute for consent.
