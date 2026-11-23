---
title: "Action item register specification"
description: >-
  Defines the authoring contract for action item registers tracking discrete follow-up actions across a project, team, or review effort. Covers action governance rules, uniquely identified action items, originating sources, assigned owners or explicit assignment gaps, priority, predecessor dependencies, due dates, controlled lifecycle states, explicit closure criteria, checked closure evidence, and index defects so teams monitor open follow-up load and verify closure rather than closing items on unverified claims.
topics:
  - "control-records"
  - "quality-assurance"
  - "operations"
  - "action-item-register"
  - "follow-up-tracking"
  - "action-ownership"
  - "closure-evidence"
  - "task-dependencies"
use_when:
  - "Discrete follow-up actions from reviews, audits, meetings, or operations require centralized ownership, due dates, and verified closure."
  - "A coordinator is tracking blocked predecessors, overdue items, and unresolved owner assignments in one register."
  - "A reviewer is confirming that closed actions cite checked closure evidence matching stated closure criteria."
not_for:
  - "Maintaining emergent, prioritized product backlog work items, which belong in an ordered product backlog."
  - "Tracking live execution steps and recovery state for one bounded task session, which belongs in a task execution plan."
  - "Tracking defects or nonconformances through root-cause analysis and disposition, which belongs in a problem or defect report."
---

# Action item register specification

## Identity and selection

- **Specification ID:** `ACTION-ITEM-REGISTER@core`.
- **Purpose:** Account for discrete follow-up actions, including the owner, status, due date, dependencies, and closure evidence of each action.
- **Intended readers:** Action owners, the role that assigns or closes actions, and consumers who need the current follow-up load.
- **Decision or action supported:** Determine what must be delivered, by whom and when, what is blocked, and whether closure rests on checked evidence.
- **Use when:** Discrete follow-up actions need controlled owners, status, due dates, dependencies, and closure evidence.
- **Scope boundaries:** Track discrete follow-up actions with owners, status, due dates, dependencies, and closure evidence; exclude project delivery plans, architectural decisions, and work-execution logs.

## Authoring inputs and unresolved facts

Inspect the project or team boundary, the rules for assignment, priority, due-date changes, escalation, and closure, and each real follow-up that belongs in that boundary. For each action, inspect its source, observable outcome, owner, priority, predecessors, due date or scheduling disposition, current state, and any closure check that has actually occurred.

If an owner, date, source, or predecessor is unknown, keep the action visible and state the gap, its consequence, the resolving action, and the actual owner if one is assigned. Do not invent an owner, a date, a source identifier, or closure evidence. If the stated scope was assessed and no follow-up qualifies, say so instead of adding a sample action. Record no secrets.

## Finished-document contract

- **Title:** Identify the project or team boundary and name the document as its action item register.
- **Frontmatter:** Required. Begin with a YAML 1.2 Semantic-Discovery frontmatter block delimited by `---` lines containing `title`, `description` (60 to 140 neutral retrieval words), `topics` (3 to 12 concrete lowercase kebab-case terms), `use_when` (2 to 6 neutral task conditions), and conditional `not_for` (1 to 5 grounded exclusions, omitted when empty), followed by the GFM H1 title. Exclude internal IDs, version strings, hashes, filesystem paths, build metadata, and unresolved template delimiters from frontmatter values. Scope, rules, and action state belong in the body. Governing source: Collection Semantic-Discovery Frontmatter contract.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. Omit it for internal documents unless a specific project policy requires explicit negative attestation. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State governance before the action index; place defects in the index after the actions. Heading wording may vary.
- **Presentation:** Use compact registers, structured item tables, or grouped lists sized to the controlled inventory without placeholder rows. Required roles may share sections while keeping stable identities, owners, states, source locators, and reconciliation gaps directly retrievable.

| Projection | Title and metadata ownership | Syntax and source authority |
| --- | --- | --- |
| Action item register (standalone) | Begin with the mandatory 5-key Semantic-Discovery YAML frontmatter followed by one scope-specific H1. Control scope, as-of point, state, ownership, and authority references remain body content, inheriting corpus-level changelog/VCS versioning, declared default maintainer, and external specification provenance when governed in a unified operational corpus. | Use GFM prose, tables, or structured lists bound to controlling masters and inspected snapshots. Referenced systems, trackers, or baselines remain authoritative for their native records; changes to controlling sources require reconciliation rather than silent overwrite. |

| Section role | Status and inclusion condition | Content obligation |
| --- | --- | --- |
| Action governance | Required | State the project or team scope, the date through which status was checked, and the rules for owner assignment, the priority vocabulary, due-date changes, escalation, and closure authority. Priority expresses follow-up urgency using this register's vocabulary. |
| Action index | Required | Include every in-scope follow-up, or an explicit assessed-empty statement. For each action, give its stable identity, source, observable outcome, owner or assignment gap, one priority or an unresolved priority, predecessors, the authorized due date or scheduling disposition, state, and closure basis. |
| Index defects | Required | Identify dependency cycles, self-dependencies, closure or cancellation claims that lack the required authority or evidence, and blocked actions whose blocking condition is unnamed. Give the consequence and route, or state that the assessed scope showed none. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
| --- | --- | --- |
| Action | One accountable follow-up; zero only when the scope was assessed and no action qualifies. | Use one immutable identifier and do not reuse it. The outcome is a specific deliverable or observable result. A vague intention is not an action. |
| Source | One originating event or record per action. | Identify the review, incident, risk, meeting, decision, or other real source and its locator. Describe the source when no controlled identifier exists. Do not invent one. |
| Owner | One accountable role once assigned. | The project may also name a person. An unassigned owner stays unresolved. The owner is not, by that assignment alone, the closure authority. |
| Priority | One of `urgent`, `high`, `normal`, or `low` when assigned. | Use only this vocabulary for follow-up urgency. Do not default a missing priority to `normal`. |
| Predecessor | Zero or more other actions. | Identify each predecessor and its actual source; cite its register entry when one exists. Describe a predecessor without an established identifier by its source and outcome. Cycles and self-references are defects. An unknown predecessor stays unresolved. |
| Due date | One current scheduling fact per action. | Use `YYYY-MM-DD` for an authorized date, or state the explicit scheduling disposition when no date is authorized. A changed date identifies the current authorized date; do not invent the earlier date when it is unknown. |
| State | Exactly one of `open`, `in-progress`, `blocked`, `done`, `closed`, or `cancelled`. | `done` is the implementer's completion claim. `closed` requires checked evidence and a closure basis. `cancelled` requires the cancelling authority and reason. `blocked` names the predecessor or external condition. The state describes the follow-up outcome and its disposition. |
| Closure basis | One statement per action. | For `open`, `in-progress`, and `blocked`, state that closure has not occurred. For `done`, record the claim and that authorized closure has not occurred. For `closed`, name the reviewer, closure authority, date, criterion, and actual evidence. When the project's closure decision requires independence, the reviewer must differ from the implementer; identify that decision. For `cancelled`, name the authority and reason. |
| Closure evidence | Required for `closed`; otherwise only evidence that actually exists. | Cite a real record of the checked outcome. An empty evidence list on a `closed` action is a defect. Expected evidence is not actual evidence. |

Use one row or short block per action. List each predecessor on its own line when an action has several. Do not add an empty action row.

## Quality criteria

- Every action has one stable identity, one observable outcome, and a source a reader can find or an explicit source gap.
- `done`, `closed`, and `cancelled` match the claim, evidence, and authority defined for those states.
- Predecessor links resolve without cycles, and a blocked action identifies what blocks it.
- The currency date, due dates, and escalation rule are sufficient to see which open actions are overdue and who must escalate them.
