# Work instruction specification

## Identity and selection

- **Specification ID:** `WORK-INSTRUCTION@core`.
- **Purpose:** Give a qualified worker an executable method for one bounded, repeatable task, including controls, checks, and the required output.
- **Intended readers:** Workers who perform the task, supervisors or checkers who release hold points, and the next process recipient.
- **Decision or action supported:** A worker can confirm the task applies, prepare the right item and resources, perform the method, identify nonconforming work, and hand off the expected result.
- **Use when:** One repeatable task needs detailed technique, tools, checks, and an acceptance condition. Its work context may be a process, a work order, or the trigger and authority stated in this instruction.
- **Scope boundaries:** Cover one bounded task's technique, tools, tolerances, and acceptance checks for its identified item or station.

## Authoring inputs and unresolved facts

Obtain the task objective and boundaries, project workflow or work authorization where one exists, qualified role, item or work-station selector, accepted input condition, current project drawings and supplied task technical data, tools and materials, relevant configuration and tolerances, hazards and controls, detailed actions, in-process and final checks, nonconforming-work route, required record, and receiving handoff. Identify the actual method, drawing, or technical-data editions where an obsolete version would change the task. Define the task's trigger and execution-time authorization route.

For an unknown or not-established fact, state the gap, its consequence, the resolving action, and the owner if known. An unknown tolerance, critical safety control, item identity, method step, or release authority makes the affected task unready; specify safe stop and escalation. If a hazard control, in-process check, hold, or signoff is inapplicable, give the reason where omission might affect safe or acceptable output. A final acceptance condition remains required; the receiving handoff criterion may be that condition. Never invent commands, settings, measurements, signatures, or observed results. The instruction does not authorize an actual work order or report its completion.

## Finished-document contract

- **Title:** Identify the single task and the item, station, or work context it applies to.
- **Frontmatter:** None. Begin with the GFM title; task scope and authority belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Put applicability, authority, and preparation before the work steps; put acceptance and handoff after them. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Task and applicability | Required | State the one task, intended output, trigger, covered item or station, limits, and any project process or work authorization that actually exists. Identify the method edition when version selection matters. |
| Authorization and preparation | Required | Define the eligible role, the work authorization required at execution time, and how the worker confirms the item or station. When the task depends on a configuration, revision, drawing edition, or equipment setup, state the check that confirms it; otherwise state that configuration selection does not change the task. List tools and materials, source drawings or parameters when they affect the task, readiness checks, and applicable hazards and controls. |
| Detailed method | Required | Give ordered actions at the level needed to perform the task, with settings or tolerances only when established, in-process observations, and clear branch destinations. Include figures or identified details from project drawings, models, or task technical data when spatial or technical detail cannot be safely conveyed in prose. |
| Quality and deviation control | Required | State assessable in-process and final acceptance checks, applicable hold points and release authority, and what to do with failed, missing, or ambiguous results. Include protection or containment for nonconforming work. |
| Completion and handoff | Required | Define cleanup or restoration, expected deliverable and final condition, recipient and handoff criteria, and what measurements, item identity, decisions, and signoffs workers must record under actual project practice. Do not assert that these actions already occurred. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Task boundary | One narrow, repeatable operation with a defined input and output. | Limit the method to that task; separate independent operations into individually bounded tasks. |
| Work item selector | One way to identify the item, configuration, or station for an execution. | State how a worker confirms the correct item before changing it; never use an unspecified production target. |
| Authority and competence | One or more eligible roles and an execution-time authorization route; checker or release role when required. | Document existence is not permission to work. Keep performer, independent checker, and release authority distinct when the real process does. |
| Resource or technical reference | One or more tools, materials, drawings, settings, or method, drawing, and technical-data editions necessary for the task. | Include only details that affect safe or acceptable execution. State units, ranges, and applicable configuration for a meaningful tolerance. |
| Step | One or more ordered, locally identifiable actions. | Supply the action and its expected observation or the check that follows it; every conditional branch ends in a step, hold, stop, rework, or escalation. |
| Check or hold | At least one final acceptance check; in-process checks and holds where the work requires them. | The receiving handoff criterion may be the final check. Give the criterion and the response to failure. A hold requires an identified release role and evidence; do not fabricate a hold for an ordinary observation. An inapplicable hazard control or signoff states the reason instead of a fabricated control. |
| Deviation route | At least one route for unsafe, failed, or uncertain work. | State containment, notification, disposition authority, and how rework or resumption is controlled. |
| Work record and handoff | One recording route and one completion or receiving condition. | Name what actual item, measurement, result, and authorization to capture; require signoff only when established. This instruction is not the completed record. |

Use a numbered sequence or a table with action, check, and failure-route columns. Use a labeled diagram or figure when orientation or assembly detail matters. Exact commands or machine settings MUST be verified for the stated equipment and configuration before inclusion. Avoid blank checklists or copied fill-in forms in the finished instruction.

## Quality criteria

- A qualified worker can identify the correct item, the method edition when more than one can apply, and the execution authority without guessing.
- Actions, checks, and tolerances are specific enough to detect a wrong or unsafe result, with units and the method, drawing, technical-data, or configuration context where relevant.
- Every failure or uncertain result has a safe next route; a missing signoff or failed hold cannot be interpreted as release.
- The method stays within one task while its project workflow or work authorization and receiving handoff remain clear.
- The output contract distinguishes instructions and expected checks from measurements, approvals, and work evidence that occur later.
