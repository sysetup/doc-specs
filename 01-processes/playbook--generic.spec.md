# Generic response playbook specification

## Identity and selection

- **Specification ID:** `PLAYBOOK@generic`.
- **Purpose:** Coordinate a branching response to a bounded operational or business situation.
- **Intended readers:** Response leads, participating teams, escalation authorities, and people receiving a transition or handoff.
- **Decision or action supported:** A responder can decide when to activate the playbook, assess the situation, select an authorized response path, and decide when to halt, escalate, or transition.
- **Use when:** Conditions may change during a response and different observed states require different coordinated actions.
- **Scope boundaries:** Cover coordinated response choices and handoffs. Exclude cybersecurity incidents, vulnerability treatment, and operations with no material branching choice.

## Authoring inputs and unresolved facts

Obtain the covered situation and exclusions, activation signals, desired outcome, affected functions or assets, decision authority, participating roles, information available for assessment, response options and limits, escalation channels, transition criteria, and the project's recordkeeping practice. Confirm any referenced operational method against its actual owner and edition.

For an unknown or not-established fact, state the gap, its effect on response, the resolving action, and the owner when known. An unknown trigger threshold, decision authority, or safety limit MUST lead to a safe assessment or escalation path; it cannot silently select an action. If a critical response path cannot be made safe or actionable, identify the playbook as unready for that path. Omit inapplicable scenarios after defining the selection boundary. Do not invent project authorities, contacts, capabilities, observations, or actual response results.

## Finished-document contract

- **Title:** Name the situation or response domain, using a title such as “Playbook: [situation].”
- **Frontmatter:** None. Begin with the GFM title; scope and response authority belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State applicability and authority before assessment and response choices; put transition and record instructions after response paths. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Purpose and activation | Required | State the situation, intended outcome, covered and excluded cases, activation signals, and when to use a different response route. Identify the applicable edition when more than one can be active. |
| Roles, authority, and communication | Required | Name the response lead or role, decision rights, participating roles, escalation route, and communication responsibilities. Distinguish coordination from authority to perform a disruptive action. |
| Assessment and decisions | Required | State what information to collect, how to treat uncertainty, and the conditions that select each response path. Include a route for insufficient information, out-of-scope events, and material change in conditions. |
| Response paths | Required | Describe conditional actions, constraints, expected outcomes, handoffs, and halt or reassessment points. Identify an existing detailed method when needed and available; otherwise supply enough safe action detail or mark that path unready. |
| Stabilization and transition | Required | Define how to judge stabilization, who decides to deactivate or transition, the receiving role, and what unresolved work follows the handoff. |
| Recording and improvement | Required | Specify what decisions, observations, actions, times, and communications a later project record must capture, and the condition that starts a later review or improvement action. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Activation condition | One or more observable signals or authorized requests that bring the situation into scope. | Distinguish a signal requiring assessment from a decision to perform a response action. |
| Decision point | At least one branching choice with two or more explicit outcomes, including an uncertainty or escalation outcome where needed. | Use conditions that a qualified responder can assess; avoid overlapping outcomes without a priority rule. |
| Response path | One or more paths selected by decision conditions. | Each path has a locally unique label, condition, responsible role, permitted action, constraints, expected state, and next decision, transition, halt, or escalation. |
| Authority check | One check for each action whose impact requires permission beyond routine coordination. | Identify the role or existing authorization route; the playbook's existence does not grant permission. |
| Time or resource bound | Conditional when a wait, retry, expiring condition, or limited resource affects a decision. | State the limit and what happens when it is reached. |
| Response record | One project-defined route for recording actual decisions and actions. | Specify the information a later record captures and protect sensitive details. |

A decision table, labeled flow, or numbered conditional list MUST show the branches and their destinations. Use prose for purpose, authority, and rationale. A detailed command belongs here only if it is necessary, verified for the stated target, and controlled under the actual execution authority; a reference to a real method is often clearer. Do not add blank branch rows or sample incidents to the finished playbook.

## Quality criteria

- Activation signals and branch conditions define the covered situation, its exclusions, and the material choices responders must make.
- Every decision has a determinable next route, including unknown, unsafe, out-of-scope, and changed conditions; no branch ends in an unexplained gap.
- Roles and authority match each action's impact, and communication and handoff responsibilities are explicit.
- The stated expected outcomes can be assessed without treating them as observations that have already occurred.
- The transition criteria and required response record preserve unresolved issues and actual decisions for later work.
