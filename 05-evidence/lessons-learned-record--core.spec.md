# Lessons learned record specification

## Identity and selection

- **Specification ID:** `LESSONS-LEARNED-RECORD@core`.
- **Purpose:** Retain evidence-based lessons from non-incident engineering, delivery, operations, maintenance, or project work, including the observation, its interpretation, the reusable recommendation, and any improvement action actually derived from it.
- **Intended readers:** People who may repeat the work, practice or process owners, and anyone deciding whether to adopt a recommended practice or improvement.
- **Decision or action supported:** See what was observed, how far the interpretation goes, where the lesson is believed to apply, and which follow-up actions were proposed or taken. Decide whether a separate controlled change is needed.
- **Use when:** Non-incident work has produced one or more evidence-based lessons that should be retained, including a retained practice or a proposed improvement.
- **Scope boundaries:** Retain lessons from a bounded non-incident activity, with factual observations supported by examined evidence, interpretations limited by that evidence, and recommendations identified as proposed changes or practices to retain.

## Authoring inputs and unresolved facts

Inspect one bounded non-incident activity, such as a milestone, iteration, phase, deployment, maintenance window, or other stated subject, and the period it covers. Inspect the records, metrics, review notes, or other evidence; the roles or sources of the observations; and each lesson's observation, interpretation, recommendation, and limits of applicability. Inspect any improvement action actually derived, its owner, and its state. Inspect where the retained lesson was published, if anywhere, and whether a revisit or effectiveness check was set. Identify related project decisions, practices, changes, and evidence by their actual identity, edition where relevant, and locator.

If evidence, an observation source, a cause, an owner, or a publication location is unknown, say so and limit the claim. Do not invent causation, a contributor, an action, or an approved process change. If the activity has no evidence-based lesson to retain, do not open this record to hold a placeholder. Keep the activity scope non-incident and identify the actual event from which each lesson arose.

## Finished-document contract

- **Title:** Identify the activity and call the document a lessons learned record.
- **Frontmatter:** None. Begin with the GFM title. The activity, lessons, and action state belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Give the activity and its evidence before the lessons. Place derived actions and reuse after the lessons they depend on. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Activity and evidence context | Required | Identify one bounded non-incident activity, the period covered, the evidence examined, and the roles or sources of the observations. State gaps, conflicts, and unrecorded sources. |
| Lessons | Required | Include at least one lesson. For each, give a stable identity, the observation and its evidence, the interpretation with its uncertainty, the recommendation, and where the lesson is believed to apply, including known limits. |
| Improvement actions | Required | Record each action derived from a lesson in this record. When none was derived, say so after that assessment. |
| Knowledge reuse | Required | State where each retained lesson can be found, or that it has not been published. State the revisit or effectiveness check, or that none was set. Cite a related decision or controlled document only when it exists. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Activity | One bounded non-incident subject and one actual period or date. | State the subject specifically enough to find the underlying work. Preserve the known precision of the period and the non-incident scope. |
| Evidence | The records, metrics, notes, or observations that support the lessons. | Every statement offered as fact traces to evidence identified in the context or in the lesson. A statement without that trace is labeled unsupported and is not written as fact. Conflicting evidence stays visible. |
| Participant or source | Zero or more roles or sources that contributed observations. | Include identifying information only within the project's supplied disclosure permissions; use role labels or controlled locators for sensitive contributor details. When the source of an observation was not recorded, say so. An empty list is not a claim that nobody contributed. |
| Lesson | One or more lessons retained from the activity. | Each has a stable identity within the record. Keep the observation, the interpretation, and the recommendation separate. The observation says what the evidence shows. The interpretation says why it matters and stops short of causation the evidence does not support. |
| Recommendation | One recommendation per lesson. | Use one of three forms: a proposed reusable change, a practice to retain, or an explicit statement that no reusable change is recommended, with the reason. State any actual adoption or approval decision separately with its authority, date, scope, and evidence. |
| Applicability | One scope and its limits per lesson. | Say where the lesson is believed to apply and where that belief stops. Do not generalize beyond the evidence and the stated context. |
| Action | Zero or more actions actually derived from lessons in this record. | Each names the lesson or lessons it comes from, the action, the responsible role or an unassigned gap, and one status: `proposed`, `planned`, `in-progress`, `blocked`, `completed`, or `cancelled`. `proposed` is not an approved change. `blocked` names the blocker. `completed` identifies what finished and the evidence of completion. `cancelled` states the reason. Include a controlled action-register identity only when that entry exists. An assessed statement that no action was derived is valid. Do not invent an action to fill the section. |
| Knowledge destination | One account of where the retained lessons were made available. | Give a real location, record, or channel for each retained lesson, or state that it has not been published. Record the actual publication state and any reuse that was confirmed. |
| Review trigger | One or more revisit or effectiveness conditions, or one explicit statement that none was set. | Use a real date, event, or condition. When none was set, state what that leaves unchecked. |
| Related reference | Zero or more real project decisions, practices, changes, or evidence records. | Cite each existing record by identity, edition where relevant, and locator, and state its relationship to the lesson. Record a proposed change as proposed until an actual decision establishes its adopted state. |

Use one block or table row per lesson, with observation, evidence, interpretation, recommendation, and limits visible. Use an action table when more than one action is recorded, with the lesson, action, owner, and status as columns. Use prose for the limits of applicability and the actual state and decision basis of any recommended change. Do not add a blank lesson, a blank action, a document-lifecycle block, or a generic completion checklist.

## Quality criteria

- Each factual observation points to examined evidence. Unsupported statements are labeled and do not carry the recommendation.
- The interpretation is no stronger than the evidence. Causation, blame, and a universal practice remain out of the observation unless the evidence and the stated limits support them.
- Recommendation and action states remain explicit. An approved change identifies the actual decision, its authority, and the scope adopted.
- Every recorded action names its lesson. Completed, blocked, and cancelled actions carry the basis the status requires. The absence of an action is stated after assessment rather than filled with a placeholder.
- Each lesson stays bound to the non-incident activity, its observation evidence, and its stated reuse limits. Action closure claims identify actual completion evidence and any existing tracking entry.
