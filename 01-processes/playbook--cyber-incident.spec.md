---
title: "Cybersecurity incident response playbook specification"
description: >-
  Defines the authoring contract for branching cybersecurity incident response playbooks coordinating triage, declaration thresholds, evidence preservation, containment decisions, eradication, recovery gates, stakeholder notifications, and deactivation under real incident-response authority. Covers activation readiness, disruptive-action controls, communication routing, and post-response learning handoffs while explicitly excluding routine pre-exploitation vulnerability intake. Enables security and operations responders to select authorized actions dynamically as incident indicators and blast radius evolve.
topics:
  - "processes"
  - "security"
  - "incident-and-continuity"
  - "cybersecurity-incident"
  - "response-playbook"
  - "incident-triage"
  - "containment"
  - "eradication"
use_when:
  - "A security team needs a branching playbook for suspected or confirmed cybersecurity incidents requiring coordinated triage and containment."
  - "An author is defining incident declaration thresholds, evidence preservation duties, disruptive-action approvals, and recovery gates."
  - "A reviewer is verifying that a cybersecurity playbook covers notification decisions and deactivation criteria without inventing authority."
not_for:
  - "Pre-incident organizational preparedness, severity taxonomy, and exercise governance, which belong in a cybersecurity incident response plan."
  - "Ordinary vulnerability intake and remediation without suspected exploitation, which belong in a vulnerability response playbook."
  - "Contemporaneous incident logging or retrospective incident analysis, which belong in incident records or post-incident reviews."
---

# Cybersecurity incident response playbook specification

## Identity and selection

- **Specification ID:** `PLAYBOOK@cyber-incident`.
- **Purpose:** Coordinate conditional response to a suspected or confirmed cybersecurity incident under the organization's actual incident-response authority.
- **Intended readers:** Incident lead, security and operations responders, service owners, communications and legal roles when applicable, and receiving recovery teams.
- **Decision or action supported:** Responders can triage a report, determine escalation and response authority, choose containment and recovery paths, protect evidence, and decide when to transition or close response work.
- **Use when:** A security event may require incident declaration, coordinated containment, investigation, eradication, recovery, or incident communications.
- **Scope boundaries:** Cover conditional triage, containment, investigation, eradication, recovery, communication, and closure for suspected or confirmed cybersecurity incidents. Exclude ordinary vulnerability intake and remediation where exploitation is not suspected.

## Authoring inputs and unresolved facts

Obtain the organization's incident-response decision roles and mandates, covered systems and data, declaration and severity criteria, detection and reporting channels, available containment and recovery capabilities, evidence handling controls, project-established notification recipients, triggers, channels, timing and disclosure constraints, and criteria for returning services to operation. Identify the response configuration or edition when more than one is active. Confirm detailed response methods and access boundaries with their owners.

If facts are unknown or not established, state the gap, its operational consequence, resolving action, and owner when known. Uncertain incident classification MUST route to triage and the proper authority rather than an unsupported declaration or dismissal. Unresolved notification recipients, channels, or timing MUST be referred to the responsible legal or response decision role; do not invent recipients or deadlines. If a critical containment, evidence, or recovery method lacks authority or safe detail, mark that route unready and provide an escalation path. Do not invent incident observations, indicators, actions, approvals, or results.

## Finished-document contract

- **Title:** Identify the covered incident scenario or incident class, such as "Cybersecurity incident playbook: <scenario>."
- **Frontmatter:** Required. Begin with a YAML 1.2 Semantic-Discovery frontmatter block delimited by `---` lines containing `title`, `description` (60 to 140 neutral retrieval words), `topics` (3 to 12 concrete lowercase kebab-case terms), `use_when` (2 to 6 neutral task conditions), and conditional `not_for` (1 to 5 grounded exclusions, omitted when empty), followed by the GFM H1 title. Exclude internal IDs, version strings, hashes, filesystem paths, build metadata, and unresolved template delimiters from frontmatter values. Classification, scope, and authority rules belong in the body. Governing source: Collection Semantic-Discovery Frontmatter contract.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. Omit it for internal documents unless a specific project policy requires explicit negative attestation. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Put scope and activation before investigative or disruptive actions; put recovery and closure criteria after response branches. Heading wording may vary.
- **Presentation:** Use crisp trigger criteria, decision tables, or branching checklists sized to the response scope so responders can act under pressure without wading through administrative boilerplate. Required roles may share sections while keeping triggers, authority limits, branches, and escalation visible.

| Projection | Title and metadata ownership | Syntax and source authority |
| --- | --- | --- |
| Cybersecurity incident response playbook (standalone) | Begin with the mandatory 5-key Semantic-Discovery YAML frontmatter followed by one task- or process-specific H1. Triggers, authority, scope, and maintenance ownership remain body content, inheriting corpus-level changelog/VCS versioning, declared default maintainer, and external specification provenance when governed in a unified operational corpus. | Use GFM lists, tables, or fenced commands grounded in inspected target configurations and policies. Reassess commands, parameters, and decision branches whenever target systems, tools, or controlling procedures change; written steps confer no execution authority. |

| Section role | Status and inclusion condition | Content obligation |
| --- | --- | --- |
| Scope, activation, and readiness | Required | State covered incident signals and assets, exclusions, declaration and severity decision route, lead and supporting roles, available response capability, secure communications, and authority needed for disruptive action. Identify the response configuration or edition when more than one is active. |
| Triage and evidence | Required | Direct responders to assess report credibility, affected scope, impact, and uncertainty; preserve relevant observations and evidence before actions that may destroy them when feasible and safe. State escalation for suspected exploitation, incomplete visibility, or rapidly increasing impact. |
| Containment decisions | Required | Define conditions for each containment option, responsible decision authority, expected security effect, service or safety tradeoff, evidence-preservation constraint, and when to reassess. Include a path when containment cannot safely continue. |
| Eradication and recovery | Required | State how responders determine what cause or persistence must be addressed, choose authorized remediation and restoration methods, check restored integrity and function, and monitor for recurrence. If the cause remains uncertain, state the restricted recovery or escalation decision instead of implying eradication. |
| Coordination and notification | Required | Specify internal decision and communication routes, handoffs, and information to record. For each project-established notification, state recipients, triggers, channels, timing, disclosure constraints, and the deciding role or authorized decision that establishes them. |
| Deactivation, records, and learning | Required | Define incident-response closure or transition criteria, deciding authority, unresolved risk handoff, what actual observations, decisions and actions a later record retains, and the trigger for later review or improvement. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
| --- | --- | --- |
| Activation or declaration threshold | One or more project-defined conditions for triage, escalation, and formal incident declaration where used. | Suspected and confirmed incidents MUST remain distinguishable; classification is a decision, not a fact inferred from a playbook title. |
| Incident branch | One or more conditional response paths, with at least two explicit outcomes at a material decision point. | Label each path; state its observed condition or uncertainty, decision role, permitted action, evidence to preserve, expected result, and next decision or escalation. |
| Disruptive action | Conditional for isolation, shutdown, credential action, restore, or another action with material effect. | State the applicable authority check, service and evidence tradeoff, and halt or reversal limit. Require the established operational permission before execution. |
| Evidence handling | One response-wide rule, with additional case-specific rules when needed. | Identify what to capture, where authorized records are kept, access controls, and custody or integrity controls when forensic or legal use requires them. Avoid placing secrets or sensitive raw evidence in the playbook. |
| Notification decision | Conditional for each project-established internal or external notification. | Name the deciding role, triggering condition, project decision and its locator, authorized channel, and established deadline or timing. Mark unresolved notification details and give the responsible decision route. |
| Recovery gate | One or more criteria recorded observations must satisfy before the designated authority may return the service to operation. | Include integrity, essential function, monitoring, and unresolved-risk checks appropriate to the affected service, and the decision route when a criterion is unmet or cannot yet be assessed. |

Use a decision table or labeled flow for triage, containment, and recovery choices; concise prose can explain authority and evidence rules. Exact commands MAY appear only when verified for a defined target and controlled under the project's execution rules; otherwise identify the real method or state the safe escalation. Record instructions MUST say how a later record captures actual times, decisions, actions, communications, observations, and each attempt, including an attempt that did not achieve the expected state or was repeated.

## Quality criteria

- A suspected event can be handled without prematurely declaring or dismissing an incident, and material new evidence sends responders back to assessment.
- Containment, eradication, and recovery choices distinguish expected security benefit from service disruption and evidence loss.
- Each notification route has project-established recipients, triggers, channels, timing, and disclosure constraints, or identifies the unresolved decision and its responsible role.
- Every disruptive branch has a decision role, a safe halt or escalation route, and a way for a later record to retain the actual decision and action.
- Recovery and closure decisions require stated criteria, an identified deciding authority, and a route for unresolved evidence or risk.
