---
title: "Operational runbook specification"
description: >-
  Defines the authoring contract for operational runbooks giving authorized operators a repeatable, ordered sequence for a specific service or system operation, troubleshooting procedure, maintenance action, or recovery task. Requires explicit invocation triggers, bounded target selectors, authority and preflight checks, execution context, ordered steps with expected observations and deviation branches, wait or retry bounds, recovery and rollback paths, completion checks, and evidence capture rules.
topics:
  - "processes"
  - "operations"
  - "operational-runbook"
  - "service-operations"
  - "preflight-checks"
  - "recovery-and-rollback"
  - "troubleshooting"
  - "execution-safety"
use_when:
  - "Operators need an ordered, repeatable procedure with preflight checks, expected observations, and rollback steps for a specific service or system."
  - "An author is documenting a maintenance, troubleshooting, or operational recovery task bound to an explicit target selector."
  - "A reviewer is checking whether a runbook prevents wrong-target execution, unbounded retries, or unverified recovery claims."
not_for:
  - "Multi-role organizational workflows spanning a broad class of recurring work, which belong in a standard operating procedure."
  - "Highly branching responses to evolving disruptions or incidents, which belong in a response playbook."
  - "Recording actual observations and outcomes of a performed run, which belong in an operational work execution record."
---

# Operational runbook specification

## Identity and selection

- **Specification ID:** `RUNBOOK@core`.
- **Purpose:** Give operators a repeatable sequence for a specific service or system operation, troubleshooting task, maintenance action, or recovery task.
- **Intended readers:** Authorized operators and the people who review or support the operation, including anyone the procedure names as a later handoff recipient.
- **Decision or action supported:** An operator can decide whether the runbook applies, prepare safely, follow the steps, respond to deviations, and check the final state.
- **Use when:** A service or system task needs ordered actions, expected observations, failure handling, and a clear target, configuration, and authority boundary.
- **Scope boundaries:** Cover one operation on a supported service or system target, with expected system observations and failure or recovery routes.

## Authoring inputs and unresolved facts

Obtain the target service or system and supported environments, invocation trigger, authorized operator role and authorization route, operational objective, dependencies, required access and tools, current safe method, expected states, failure and recovery paths, and the evidence or notifications required by the project. Inspect the applicable configuration and any real change, incident, or maintenance controls. Confirm commands and parameters against the target environment before presenting them as executable instructions.

For an unknown or not-established fact, identify the gap, reason, resolving action, and assigned owner if known. An inapplicable safeguard or rollback path needs a reason and a safe alternative when failure remains possible. If the target selector, authority boundary, required prerequisite, or critical action is unresolved, label the runbook unusable for execution until resolved. Do not invent commands, resource identifiers, approvals, backups, or expected observations. The written runbook never authorizes its own execution.

## Finished-document contract

- **Title:** Identify the operation and service or system, for example by the semantic form "Runbook: operation on target."
- **Frontmatter:** Required. Begin with a YAML 1.2 Semantic-Discovery frontmatter block delimited by `---` lines containing `title`, `description` (60 to 140 neutral retrieval words), `topics` (3 to 12 concrete lowercase kebab-case terms), `use_when` (2 to 6 neutral task conditions), and conditional `not_for` (1 to 5 grounded exclusions, omitted when empty), followed by the GFM H1 title. Exclude internal IDs, version strings, hashes, filesystem paths, build metadata, and unresolved template delimiters from frontmatter values. Operational target and authority rules belong in the body. Governing source: Collection Semantic-Discovery Frontmatter contract.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. Omit it for internal documents unless a specific project policy requires explicit negative attestation. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Put applicability and preflight controls before any action; put recovery and completion checks after the ordered procedure. Heading wording may vary.
- **Presentation:** Use compact preflight checklists, ordered steps with expected observations and deviation branches, and explicit rollback blocks sized to the operation. Required roles may share sections while keeping target selectors, preflight checks, and recovery paths immediately retrievable.

| Projection | Title and metadata ownership | Syntax and source authority |
| --- | --- | --- |
| Operational runbook (standalone) | Begin with the mandatory 5-key Semantic-Discovery YAML frontmatter followed by one task- or process-specific H1. Triggers, authority, scope, and maintenance ownership remain body content, inheriting corpus-level changelog/VCS versioning, declared default maintainer, and external specification provenance when governed in a unified operational corpus. | Use GFM lists, tables, or fenced commands grounded in inspected target configurations and policies. Reassess commands, parameters, and decision branches whenever target systems, tools, or controlling procedures change; written steps confer no execution authority. |

| Section role | Status and inclusion condition | Content obligation |
| --- | --- | --- |
| Purpose, trigger, and limits | Required | State the desired outcome, when to start, when not to start, supported target scope, and stop conditions. Identify the runbook edition or other unambiguous method version (including a unified corpus version in `CHANGELOG.md` plus Git revision) if multiple editions can exist. |
| Target, authority, and preflight | Required | Define how to identify and verify the intended account, tenant, environment, site, system, and resource as applicable. State each configuration, revision, or environment assumption that a command or parameter depends on, and how the operator confirms it before acting. State who may run the procedure and which authorization must be confirmed at execution time. Include a change, incident, or maintenance authorization only when that kind applies. List prerequisites, readiness checks, relevant access and tool context, and safety controls, including backup or checkpoint requirements for state-changing work when applicable. |
| Ordered procedure | Required | Give one or more ordered actions with expected observations and a response to deviation. Define all parameters and decision branches so a qualified operator can follow them without guessing. |
| Recovery and rollback | Required | State when to stop, when and how to recover or roll back, the authority needed, and limits such as irreversible changes or possible data loss. If rollback is impossible, say so and give the recovery or escalation path. |
| Completion and handoff | Required | State final checks, continued monitoring when the operation requires it, what actual execution evidence to capture, and where to record it under project practice. Name a notification or handoff recipient only when the operation requires that notice or handoff; otherwise state that none applies. Specify the checks, notifications, and handoffs to perform at execution time. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
| --- | --- | --- |
| Invocation trigger | One event, condition, or authorized request that starts this procedure. | Include a disqualifying condition or escalation route when the task is unsafe outside its normal scope. |
| Target selector | One bounded way to identify the exact target for an execution. | Parameters MAY be used, but their allowed values and pre-execution confirmation MUST be explicit. An unspecified production target cannot be acted on. |
| Authority boundary | One statement of eligible roles, required authorization checks, permitted actions, and stop limits. | Refer to the real approval route; a runbook's existence is not approval. |
| Execution context | The tools, versions, identity or privilege, location, and configuration needed to reproduce the method. | State details only where they affect behavior. Refer to secrets through approved secret storage; never embed secret values. |
| Step | One or more ordered, locally unique step IDs, each with an action and expected observation or state. | Each step MUST specify a deviation response or refer to a common failure rule. Branch destinations MUST resolve to a step, stop, recovery, or escalation. |
| Wait or retry bound | Conditional for a wait, poll, retry, or time-sensitive step. | Give duration or limit and the action on expiry; a non-waiting step does not need a fabricated timeout. |
| Evidence capture | Required for the operation as a whole; per-step detail is conditional when a step creates evidence needed for diagnosis or accountability. | Specify what to retain and how to bind it to target, method edition, time, and actual result without placing secrets in the record. |
| Recovery path | One route for each material failure state. | Include entry conditions and consequences; never imply that reversal is safe or possible without support. |

Use an ordered list or a table with meaningful action, expected-state, and deviation columns. Use code blocks for exact commands only when verified for the stated execution context; identify variable substitution and validation. A small decision table or flow is suitable for real branches. Keep actual observations and execution outcomes out of this instruction document.

## Quality criteria

- The target, configuration assumptions, and preflight checks prevent an operator from applying a valid command to the wrong environment, revision, or resource.
- Every branch is reachable and ends in a next action, safe stop, recovery, or escalation; no retry is unbounded.
- Expected observations are specific enough to detect failure, and completion checks establish the intended final state without treating planned checks as results.
- Privileges and authorization are limited to the task, and failure handling accounts for irreversible effects and data integrity where relevant.
- The sequence, tool context, and recovery instructions are consistent; unexplained placeholders or unresolved critical facts bar execution readiness.
