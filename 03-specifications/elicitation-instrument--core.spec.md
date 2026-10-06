# Elicitation instrument specification

## Identity and selection

- **Specification ID:** `ELICITATION-INSTRUMENT@core`.
- **Purpose:** Define the questions, prompts, observation cues, and capture rules used to collect information.
- **Intended readers:** Researchers, requirements analysts, facilitators, observers, and reviewers of collection methods.
- **Decision or action supported:** Prepare and consistently administer a questionnaire, interview guide, or observation guide within its declared scope.
- **Use when:** A bounded elicitation activity needs a reusable, versioned information-collection instrument.
- **Scope boundaries:** Define one coherent questionnaire, interview, or observation instrument and its administration; exclude study-wide planning, acquired raw evidence, interpreted findings, and controlled requirements.

## Authoring inputs and unresolved facts

Obtain the elicitation questions and decision use, target population or observation context, selected method and risks, instrument identity and edition, literal item wording, response representation, order and routes, participant choices, administration and accessibility conditions, permission and data arrangements, and actual review, pilot, equivalent-check, or revision evidence. Establish the edition-specific readiness criterion and why its check method fits the method, population, and consequences of error.

Expose unresolved wording, answerability, population, response representation, routes, accessibility, permission, or readiness evidence with its consequence, resolving action, and assigned owner if known. A draft may retain gaps; ambiguous routes, missing required permissions, or unmet readiness checks prevent administration of the affected scope. Label unpiloted material as unpiloted. Do not invent a pilot, participant response, permission, comprehension result, or favorable finding.

## Finished-document contract

- **Title:** Identify the elicitation subject and instrument kind.
- **Frontmatter:** None. Begin with the GFM title. Identity, scope, edition, and readiness belong in the body. Governing source: Type-owned policy in ELICITATION-INSTRUMENT@core; no external metadata schema is selected.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State identity and collection purpose before administration; make prerequisites and the readiness disposition visible before use, put items in administration order, then explain capture and review. Heading wording may vary.
- **Presentation:** Combine semantic roles in short prose, item lists, or routing tables when every prompt, choice, prerequisite, and readiness limit remains retrievable; headings need not repeat every role.

| Projection | Title and metadata ownership | Syntax and source authority |
|---|---|---|
| Standalone information (standalone) | The document owns one descriptive H1. Identity and edition are body facts; no YAML frontmatter is supplied. | Use GFM for the written edition. The identified item wording and edition control administration. If a native form is selected, name its controlling version and reconcile wording, response fields, and routes before use; the GFM view does not certify native conformance. Changed wording, routes, context, or source edition require an impact check and renewed affected readiness checks. |

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Identity, purpose, and applicability | Required | Identify the instrument kind, edition, collection purpose and question or decision basis, intended participants or observation setting, exclusions, and client or receiving-party element. State whether it is draft, not-ready, or ready-for-administration and the scope to which that disposition applies. |
| Administration and participant conditions | Required | Define administrator role, literal introduction or observation setup, context, timing, accessibility, necessary permission checks, participation and skip choices where applicable, and stop or escalation conditions. Link actual notices and consent arrangements by edition when available. A readiness disposition or administration instruction does not establish consent or authorize collection. |
| Items and routing | Required | Give each item's unique stable label, exact question or observation cue, purpose mapping, response form, and required or optional status. Define administration order, decidable branch triggers, and existing item, skip, completion, or stop destinations, including nonresponse paths. Separate open prompts and permitted neutral follow-up from fixed choices; avoid wording that presumes a conclusion. |
| Capture and interpretation boundaries | Required | Define the recording format, response vocabulary and units, distinct missing, declined, not-observed, and inapplicable handling, provenance including instrument edition and source locator, redaction, and established storage or handoff route. Distinguish participant statements, observed behavior, and administrator inference; a missing view is not evidence that an action did not occur. |
| Review and revision basis | Required | State actual wording, response-form, routing, accessibility or translation review, pilot status, and limitations, or that these checks have not occurred. Define a method- and risk-bound readiness criterion covering clarity, answerability or observability, response representation, and representative routes including skipping and stopping. Identify whether a participant pilot or an equivalent check is needed and its rationale; for unpiloted use, state why the performed equivalent check suffices for the bounded context and what remains untested. Bind actual check method, outcome, evidence or evidence gap, and readiness disposition to the edition. Keep draft representation separate from administration readiness. Identify edition changes, their effect on comparing collections, and which checks require renewal. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Instrument edition | Exactly one current edition in Identity, purpose, and applicability. | Bind wording, routes, capture, and readiness evidence to this edition and context; retain the edition actually used in each collection. Changes require impact assessment, not reuse of an earlier edition's pass. |
| Collection item | One or more items in Items and routing. | Each has unique local identity, literal prompt or cue, purpose mapping, response form, and inclusion rule. |
| Route | Zero or more conditional routes in Items and routing. | Each has a decidable trigger and an existing item, skip, completion, or stop destination, with explicit nonresponse behavior; unsupported loops, ambiguous triggers, or dangling destinations prevent affected administration. |
| Capture value | One representation per collection item in Capture and interpretation boundaries. | Specify valid responses and units when relevant. Keep missing, declined, not-observed, and inapplicable distinct; a silence or unavailable observation cannot become an affirmative or negative finding. |
| Administration safeguard | One or more applicability and stop rules in Administration and participant conditions. | Apply permissions and participant choices actually established; do not promise anonymity or withdrawal beyond the established arrangement. |
| Review record | Exactly one account in Review and revision basis; zero or more actual review or pilot citations. | Keep planned and performed checks distinct, identify the actual method, edition, result, and limitations, and cite evidence only when it exists. No participant pilot is universally required; a pilot alone does not establish validity, permission, or readiness. |
| Readiness disposition | Exactly one edition- and context-bound disposition, draft, not-ready, or ready-for-administration, stated in Identity, purpose, and applicability and supported in Review and revision basis. | Draft represents unsettled design without administration support; not-ready records failed or unresolved required checks or prerequisites; ready-for-administration requires the declared risk- and method-bound checks and necessary arrangements to be satisfied for that scope. Record the basis for any change in disposition; changed inputs reopen affected checks. A passing static check does not establish participant comprehension. |

Use numbered literal prompts, item tables, and branch destinations at administration depth. Neutral interview follow-up may vary within declared limits while core items stay identifiable. Keep any selected native form separately versioned, state which artifact controls administration, and record the edition and consistency-check scope. A compact readiness account may link actual review evidence rather than reproduce a study plan.

## Quality criteria

- An administrator can retrieve the applicable edition, context, prerequisites, participant choices, and stopping rules before collection; the declared readiness scope agrees with actual arrangements.
- Every item is uniquely labeled, purpose-linked, answerable or observable, and free of presumed findings; an administrator can follow representative response, skip, nonresponse, and stop routes to defined destinations.
- Capture rules preserve units, response forms, missingness, edition and source provenance, and observation versus inference without unnecessary sensitive data or unsupported absence claims.
- The readiness criterion matches method and risk and has actual edition-bound pilot or equivalent-check evidence, or a visible unmet-check gap. Unpiloted use has a bounded justification; draft or planned checks are not reported as administration readiness or participant comprehension.
- Edition changes identify comparison limits and renewed checks; earlier results and the version used for actual collections remain recoverable.
