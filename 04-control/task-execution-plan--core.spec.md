# Task execution plan specification

## Identity and selection

- **Specification ID:** `TASK-EXECUTION-PLAN@core`.
- **Specification edition:** `1.0`.
- **Purpose:** Maintain the current execution state of one bounded task for continuation, recovery, and handoff.
- **Intended readers:** The task maintainer, the operator, and an authorized receiving agent or role.
- **Decision or action supported:** Determine what remains, why decisions apply, what evidence exists, and whether the next action is ready and authorized.
- **Use when:** A task needs durable tracking, recovery, or handoff and no existing project plan or task record adequately covers it.
- **Scope boundaries:** Control living task state, including remaining work; exclude project-wide delivery planning, formal action or decision masters, execution logs, and acceptance or authorization grants. Classify by ongoing state control in `04-control`, regardless of the filename `PLAN.md`.

## Authoring inputs and unresolved facts

Inspect the task request and accepted changes, workspace and applicable instructions, existing task records, actual authorization and runtime limits, acceptance criteria, work dependencies, source revisions, decisions, check results, evidence, and outstanding blockers. Reuse an applicable project contract or formal record instead of creating a competing master.

For a missing fact, record the gap, its consequence, the resolving action, and the responsible role when known. Hold dependent work when authority, critical constraints, or required evidence are unresolved. Unknown facts remain unknown; do not invent approvals, owners, dates, source revisions, progress, or check results.

## Finished-document contract

- **Title:** Identify the bounded task and name its execution plan.
- **Frontmatter:** None. Begin with a GFM title; keep metadata in the body. Governing source: this specification's standalone Markdown contract.
- **Client or receiving party:** Identify an established external client or receiving organization in scope, or state that there is no external client. Do not invent one.
- **Order:** Present the five content groups below in order; heading wording may vary.
- **Presentation:** Use short paragraphs, lists, or a compact step table. An explicit `none` is sufficient for assessed absence; do not add sample entries or empty templates.

| Projection | Title and metadata ownership | Syntax and source authority |
|---|---|---|
| Workspace plan (standalone) | One task-specific H1. In Objective and scope, identify source specification and edition, local edition, maintenance responsibility, and currency. | GFM at workspace `PLAN.md` unless an existing project record is selected. Task instructions and cited source records remain authoritative; the plan neither grants access nor guarantees runtime loading or retention. |

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Objective and scope | Required | State intended outcome, acceptance criteria, workspace and work boundaries, constraints, authorization provenance and limits, maintenance responsibility, and currency. Separate established facts from assumptions. |
| Steps and state | Required | Give identifiable steps, outcomes, dependencies or explicit absence, current states, and completion basis. Keep completed and remaining work distinguishable; identify which evidence supports each completion claim. |
| Decisions and sources | Required | Preserve material decisions with rationale, unresolved choices with their resolving action, and relevant source paths, editions, revisions, or precise locators. Reference existing formal records when applicable rather than replacing their authority. |
| Verification and evidence | Required | Separate planned checks from executed checks. For each actual check, identify method, checked scope or revision, observed result, and evidence reference or explicit absence. Identify failures, inconclusive results, unexecuted checks, and their consequences. |
| Blockers and continuation | Required | State each blocking condition, affected steps, resolving action, responsible role when known or assignment gap, and resumption condition; state assessed absence when none exists. Give the next action, or the closure disposition when no work remains. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Maintenance and currency | One accountable role and one last-reviewed indicator for the task state. | Use a date or timestamp with timezone when needed, tied to the reviewed workspace revision or relevant source snapshot. Update after material changes; local edition identifies the plan, while currency identifies the state reviewed. Neither proves unchanged external state. |
| Authorization provenance | One account of the controlling request or decision, its scope, limits, and current gaps. | Use a retrievable locator or concise description when no stable identifier exists. Distinguish user authorization from runtime permissions. A past grant, plan entry, completion claim, or passing check does not expand authority. |
| Step | One or more stable identifiers with an observable outcome and dependencies. | Do not reuse an identifier for different work. Identify unresolved predecessors and reject self-dependencies or cycles. |
| Step state | Exactly one of `in_progress`, `completed`, `canceled`, or `deferred` per step, following host `AGENTS.md` Task Planning. | `in_progress` identifies active work. `completed` requires the stated outcome and a cited completion basis. `canceled` gives the reason and decision provenance for abandoned work. `deferred` covers unstarted, postponed, or held work and gives a reason and resumption condition, including an unmet predecessor or blocker. Do not introduce `pending` or `blocked` as step states. |
| Completion basis | One basis for each completed step. | Distinguish an implementer's claim, observed completion evidence, actual verification, and authorized acceptance. Missing or failed checks required by that step's outcome prevent completion; completion does not itself establish verification or authorization. |
| Decision and source | Zero or more material decisions, unresolved choices, and supporting references. | State rationale and relevant source locators; expose unavailable sources and uncertain revisions. Cite formal decision, action, change, approval, or evidence records when they exist; do not duplicate their full contents. |
| Check and blocker | Zero or more planned or executed checks and zero or more actual blockers. | Planned checks are not results. Actual results remain bound to their checked scope or revision. A held step uses `deferred` and links its blocker and observable release condition. |
| Continuation | One current next action or explicit closure disposition. | Identify prerequisites and remaining authority gaps. At closure, no step remains `in_progress`; retained `deferred` or `canceled` work has a reason and appropriate continuation or decision basis. Do not claim the task's full outcome when required work remains. |

Keep only state needed to continue safely. Exclude full documents, raw transcripts, secrets, sensitive access material, invented facts, and routine message history. Use authorized evidence references and project access and retention controls; a link does not authorize access to its target.

## Quality criteria

- A reader can retrieve all five groups, maintenance responsibility, currency, scope, acceptance criteria, and authorization limits without a transcript.
- Every step uses the host vocabulary, has meaningful dependencies, and supports its completion or disposition; blockers have release conditions.
- Decisions, unresolved choices, source revisions, and formal record relationships are sufficient to reassess applicability after context loss.
- Planned checks, actual results, completion claims, and authority remain distinct; unavailable evidence is visible.
- The next action is concrete and conditional on relevant prerequisites; task completion does not hide required unfinished work.
- The record is compact, contains no secrets or copied source documents, and makes no automatic loading or retention claim.
