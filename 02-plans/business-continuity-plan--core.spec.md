---
title: "Business continuity plan specification"
description: >-
  Defines the authoring contract for business continuity plans specifying how prioritized business or service capabilities continue or recover across severe disruptions involving people, sites, suppliers, information, or manual workarounds. Covers continuity scope and ownership, prioritized activities, recovery objectives, disruption assumptions, activation and communication authority, continuity strategies, business restoration and return-to-normal decisions, and exercise, evaluation, and plan upkeep schedules so authorities decide activation and stand-down safely.
topics:
  - "planning"
  - "incident-and-continuity"
  - "operations"
  - "business-continuity"
  - "disruption-recovery"
  - "recovery-objectives"
  - "continuity-strategies"
  - "return-to-normal"
use_when:
  - "An organization needs to prioritize critical business or service capabilities and plan workarounds across people, sites, and suppliers."
  - "A continuity planner is defining activation authority, recovery objectives, communication routes, and return-to-normal criteria."
  - "A reviewer is checking whether a business continuity plan covers exercise evaluation and realistic supplier dependencies."
not_for:
  - "Technical recovery and failover for one classified information system, which belongs in an information-system contingency plan."
  - "Routine service monitoring and reliability engineering, which belong in operations or availability plans."
  - "Cybersecurity incident triage and containment preparedness, which belong in a cybersecurity incident response plan."
---

# Business continuity plan specification

## Identity and selection

- **Specification ID:** `BUSINESS-CONTINUITY-PLAN@core`.
- **Purpose:** Plan how prioritized business or service capabilities continue or are restored through disruption, including impact, dependencies, authority, strategies, return, and exercise.
- **Intended readers:** Continuity owners, business and service owners, recovery teams, suppliers, communications roles, and the authorities for activation and return to normal operation.
- **Decision or action supported:** Decide which capabilities take priority, how they will be sustained, who may activate and stand down continuity response, and when normal operation may resume.
- **Use when:** Critical products or services need a continuity arrangement spanning people, sites, suppliers, information, and workarounds.
- **Scope boundaries:** Cover continuity of prioritized business or service activities across people, sites, suppliers, information, and workarounds, with activation, restoration, return, and exercise arrangements at planning depth.

## Authoring inputs and unresolved facts

Obtain the products, services, and organizational boundaries in scope; interested parties and responsibilities; prioritized activities and dependencies; tolerable disruption and recovery objectives with the project decisions or supplied service commitments establishing them; disruptive conditions and continuity assumptions; invocation and stand-down authority; people, site, supplier, information, and workaround strategies; warning arrangements and the way authorized people reach current contacts; the interface to system recovery where it applies; return criteria and backlog handling; and the intended exercise and review method. Identify the adopted plan edition only when the project has established it.

If a priority, dependency, objective, trigger, strategy, or authority is unknown or not established, state the gap, its continuity consequence, the resolving action, and the actual owner if assigned. Distinguish a proposed objective from an approved one and identify the actual approving role and decision when established. If a resource or supplier strategy does not exist, record that limitation instead of inventing capacity or a commitment. Describe future exercises, reviews, recovery, and return decisions as planned activities with expected evidence. Identify the actual adopted plan edition without inventing adoption, approvals, contacts, or demonstrated capability.

## Finished-document contract

- **Title:** Identify the organization, mission, or service set and name its business continuity plan.
- **Frontmatter:** Required. Begin with a YAML 1.2 Semantic-Discovery frontmatter block delimited by `---` lines containing `title`, `description` (60 to 140 neutral retrieval words), `topics` (3 to 12 concrete lowercase kebab-case terms), `use_when` (2 to 6 neutral task conditions), and conditional `not_for` (1 to 5 grounded exclusions, omitted when empty), followed by the GFM H1 title. Exclude internal IDs, version strings, hashes, filesystem paths, build metadata, and unresolved template delimiters from frontmatter values. Scope, authority, and priorities belong in the body. Governing source: Collection Semantic-Discovery Frontmatter contract.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. Omit it for internal documents unless a specific project policy requires explicit negative attestation. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Establish priorities and disruption assumptions before activation and strategies; describe restoration and return before exercise and maintenance. Exact heading wording may vary.
- **Presentation:** Scale sections, tables, and schedules to the bounded effort without adding empty chapters for inapplicable concerns. Required roles may share paragraphs, lists, or compact tables while keeping planned scope, responsibilities, criteria, dependencies, and open gaps clearly separated from completed results.

| Projection | Title and metadata ownership | Syntax and source authority |
| --- | --- | --- |
| Business continuity plan (standalone) | Begin with the mandatory 5-key Semantic-Discovery YAML frontmatter followed by one scope-specific H1. Plan scope, baseline assumptions, ownership, and readiness criteria remain body content, inheriting corpus-level changelog/VCS versioning, declared default maintainer, and external specification provenance when governed in a unified operational corpus. | Use GFM prose, structured tables, or dependency diagrams referencing controlling requirements, baselines, and schedules by edition and locator. Planned commitments remain distinct from execution evidence; baseline or scope changes require plan reassessment. |

| Section role | Status and inclusion condition | Content obligation |
| --- | --- | --- |
| Scope and responsibilities | Required | Define critical products or services, organizational boundaries, exclusions, interested parties, and continuity responsibilities. State assumptions about what remains available during disruption. |
| Priorities and disruption risk | Required | Present the business impact analysis: prioritized activities, dependencies, tolerable disruption, and recovery objectives with their originating project decision or service commitment and whether each objective is proposed or approved. Identify disruptive conditions and assumptions whose failure would change the strategy. |
| Activation and communications | Required | State invocation and deactivation authority, observable triggers, escalation, and response-team coordination. Describe warning arrangements, who may communicate, how authorized people reach current contacts during disruption, and alternate channels. Do not publish secrets or an unrestricted sensitive contact list. |
| Continuity strategies | Required | For the priority activities, describe the people, sites, suppliers, information, and operational workarounds that sustain them, including known limits. Restoring technology does not by itself sustain a business activity. |
| Restoration and return to normal | Required | Define the order for restoring business activities and the interface to information-system recovery where that recovery is in scope. State return criteria, the authority that may later decide, backlog or work reconciliation, stakeholder considerations, and evidence needed for that decision. Return to normal requires those criteria and the authorized decision; restoring infrastructure alone is insufficient. |
| Exercise, evaluation, and maintenance | Required | Plan exercise objectives, scenarios, participants, and records a later exercise would keep. State how later results and changes to priorities, dependencies, or strategies will be reviewed, and who may amend the plan. Identify the plan edition adopted by the project; otherwise state that no adopted edition is established. Keep exercise objectives and expected evidence distinct from demonstrated capability. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
| --- | --- | --- |
| Priority activity | One or more activities whose interruption the plan addresses. | Identify the business or service effect, dependencies, tolerable disruption when established, and the consequence of exceeding it. |
| Recovery objective | Zero or more approved time, capacity, or information objectives. | Give units, the establishing project decision or service commitment, and the approving role. An unapproved target is a proposal or gap, not a commitment. |
| Disruption assumption | One or more conditions the strategies rely on. | State what changes if the assumption fails, or that this route is unresolved. |
| Activation rule | One or more triggers and the roles that invoke and stand down continuity response. | Each material trigger has a deciding role, required authorization, and an escalation path. |
| Continuity strategy | One or more ways to sustain priority activities. | Name the activities covered, resources, known limits, and whether the strategy is selected, proposed, or unavailable. |
| Business restoration concern | One or more ordered restoration concerns at planning depth. | Identify the business activity to restore, its dependencies, and the order and limits of restoration. Include system or server recovery interfaces only when that recovery supports an activity in scope. |
| Return decision | One set of criteria and an authority for leaving continuity mode. | Include backlog reconciliation and stakeholder effects the project must actually handle, the evidence needed, and the required authorization. Technical restoration alone does not establish readiness to leave continuity mode. |
| Exercise plan | One planned practice method. | Cover objectives, scenario, participants, evidence a later exercise would retain, and untested scope. Do not record that an exercise occurred. |

Use prose for authority and assumptions, a priority or dependency table when several activities differ, and a short decision flow for activation and return. Keep sensitive contacts and site detail in protected material that remains reachable during disruption. Do not include blank rows, generic document-control fields, or credential values.

## Quality criteria

- A reader can tell which activities continue first, what they depend on, who may activate response, and which conditions allow return to normal business operation.
- Strategies cover the people, locations, suppliers, information, and workarounds the priority activities actually require.
- Approved objectives, proposals, assumptions, and capability gaps stay distinct.
- Exercises state objectives, scenarios, participants, expected evidence, and untested scope; the identified plan edition reflects an actual adoption decision or an explicit gap.
- Restoration order, backlog reconciliation, stakeholder effects, return criteria, and decision authority cover the priority activities and their dependencies.
