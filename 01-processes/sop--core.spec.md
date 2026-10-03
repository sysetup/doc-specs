# Standard operating procedure specification

## Identity and selection

- **Specification ID:** `SOP@core`.
- **Purpose:** Define a repeatable organizational or operational procedure that coordinates roles, inputs, decisions, controls, handoffs, and required records.
- **Intended readers:** Process participants, the process owner, supervisors, and people responsible for a hold, escalation, or receiving handoff.
- **Decision or action supported:** A participant can decide whether the procedure applies, perform their assigned activities in order, obtain required release decisions, and route abnormal work.
- **Use when:** A bounded recurring organizational or operational workflow needs a common method for roles, decisions, controls, and records. One performing role is enough for that workflow.
- **Scope boundaries:** Bound the procedure by the recurring class of work and its entry, handoff, and completion conditions. A single production target does not define that class.

## Authoring inputs and unresolved facts

Obtain the workflow's objective, trigger, covered and excluded cases, process owner, participating and receiving roles, required inputs and outputs, decision rights, prerequisites, resources, project-defined safety limits and work commitments, hold criteria, abnormal conditions, escalation route, recordkeeping requirements, and review or change triggers. Identify the supplied project requirements, decisions, and method editions that establish the workflow's activities and controls. State the actions and assessable conditions needed for each activity.

For an unknown or not-established fact, state the gap, its effect, the resolving action, and the owner when known. If an authority, safety limit, release condition, or critical handoff remains unresolved, mark the affected route unready for use and give a safe stop or escalation. Explain why a proposed hold or safety control is inapplicable when its applicability was in question; do not invent an approving role or project commitment. The procedure describes intended work, not performed activities, approvals, or outcomes.

## Finished-document contract

- **Title:** Name the recurring procedure and its organizational or operational scope.
- **Frontmatter:** None. Begin with the GFM title; applicability and process authority belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Establish scope and responsibility before prerequisites and activities; state abnormal routes before completion and record instructions. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Purpose and applicability | Required | State the outcome, trigger, process boundary, and exclusions. The boundary is the recurring class of work. When execution depends on a specific target or configuration, state the selection rule used at execution time. State the condition for using a different method, or that no alternative method is designated. Identify the method and edition to use when multiple methods may be active. |
| Roles and decision authority | Required | Identify the process owner and the performing roles. Identify a receiving role, a release role, and segregation or an independent check only when the workflow has that role or check. State decision rights and escalation authority. |
| Inputs and readiness | Required | Define accepted inputs, competence and permissions, needed resources or facilities, preflight checks, and the conditions that prevent work from starting. State the concrete controls needed to meet the workflow's established safety limits and supplied work commitments. |
| Ordered workflow and handoffs | Required | Give one or more ordered activities, each with its responsible role, entry condition, action or decision, expected output, and next recipient or route. Specify decisions and their outcomes so work does not depend on guessed handoffs. |
| Holds and abnormal routes | Required | State applicable quality, safety, or authority holds, the evidence and role needed to release each hold, and what happens on failed checks, missing inputs, nonconforming work, or unsafe conditions. If no hold of a named class applies, explain the assessed boundary rather than inventing one. |
| Completion, records, and maintenance | Required | Define completion and handoff criteria; what actual work and decisions participants must record, where and by whom; any applicable retention or access control; and when the procedure is reviewed or revised. Do not claim that records or signoffs already exist. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Trigger and scope | One or more bounded triggers and one applicability statement for the recurring workflow. | Distinguish out-of-scope cases and identify who resolves an ambiguous case. |
| Role and authority | One accountable process owner and one or more performing roles; receiving and release roles as applicable. | A role's participation MUST NOT be treated as authority to approve or release a hold unless that right is established. |
| Input and output | One or more required inputs and expected outputs for the workflow; intermediate items where they control handoffs. | State acceptance or readiness criteria and the receiving role for each material output. |
| Activity | One or more ordered, locally identifiable activities. | State the responsible role, entry condition, action or decision, expected output, and next activity or handoff. Include the task detail needed to perform the activity and assess its output for handoff. |
| Decision or hold | Conditional for each branch or actual control point. | Give assessable conditions, release or refusal authority, and routes for failed, missing, or uncertain evidence. A hold cannot be released by silence. |
| Abnormal route | At least one route covering invalid inputs, failed checks, unsafe work, or unexpected results as relevant. | State containment or safe stop, escalation, responsibility, and how work may resume. |
| Work record | One or more record types or project-defined recording routes needed to make work accountable. | Specify what to capture and the responsible role; retention, confidentiality, and signoff apply only when established. These are future recording instructions, not execution evidence. |
| Procedure review | One change or review trigger, plus any established periodic interval. | Include ownership and how participants learn of a changed method; do not invent a calendar interval. |

Use an ordered list, swimlane, or table with meaningful role, action, condition, output, and next-route columns. A decision table or compact flow is suitable where routing matters. Use prose for scope and authority. Do not copy empty form rows, a generic document-control block, or execution results into the finished procedure.

## Quality criteria

- The workflow's recurring class of work, entry conditions, activities, and completion boundary are clear; selecting one production target does not substitute for that boundary.
- Each activity has a responsible role and a valid next route; handoffs specify what the receiver needs.
- Holds and exceptions have observable conditions and a real decision authority; unsafe or unresolved states cannot silently proceed.
- Inputs, resources, competence, and defined controls support the stated activities and their acceptance conditions.
- Record and review instructions support accountability without presenting planned work as completed evidence.
