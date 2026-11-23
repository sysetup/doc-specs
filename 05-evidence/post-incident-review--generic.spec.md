---
title: "Operational post-incident review specification"
description: >-
  Defines the authoring contract for retrospective reviews of one stabilized operational incident not handled as a cybersecurity incident. Covers review scope and evidence cutoff, supported causes and contributing conditions, response and recovery effectiveness findings, evidence-bounded lessons and recommendations, concrete improvement actions with tracking references, dissemination boundaries, and review disposition so operational owners decide justified changes with clear visibility of analytical limits.
topics:
  - "evidence"
  - "operations"
  - "incident-and-continuity"
  - "post-incident-review"
  - "operational-retrospective"
  - "root-cause-analysis"
  - "recovery-effectiveness"
  - "incident-lessons"
use_when:
  - "A non-cybersecurity operational incident has stabilized and a retrospective analysis of causes, response, and recovery has been performed."
  - "A service owner is capturing contributing conditions, recovery effectiveness, and concrete improvement actions backed by evidence."
  - "A reviewer is confirming that causal findings reflect inspected evidence and distinguish supported conclusions from speculation."
not_for:
  - "Contemporaneous event chronologies and live response status, which belong in an operational incident record."
  - "Retrospective analysis of cybersecurity incidents involving dwell time or eradication, which belongs in a cybersecurity post-incident review."
  - "Non-incident project retrospectives, which belong in a lessons learned record."
---

# Operational post-incident review specification

## Identity and selection

- **Specification ID:** `POST-INCIDENT-REVIEW@generic`.
- **Purpose:** Review one stabilized operational incident for supported causes, contributing conditions, response and recovery effectiveness, lessons, and improvement actions.
- **Intended readers:** Incident responders, affected service or operational owners, and people responsible for deciding and tracking improvements.
- **Decision or action supported:** Understand what the incident reveals and decide what should change, with evidence and limits visible.
- **Use when:** An operational incident that is not being handled as a cybersecurity incident has stabilized and a retrospective review has been performed.
- **Scope boundaries:** Retrospective analysis of one stabilized operational incident within the affected operation, configuration, and evidence cutoff stated in the review.

## Authoring inputs and unresolved facts

Obtain the incident identity, affected scope and configuration, stabilization basis, review date and participants, and the evidence available at the review's cutoff. Inspect the incident record when it exists, relevant timeline events and impact, disputed accounts, causal analysis, actual response and recovery, and the objectives against which effectiveness was assessed. Obtain lessons, recommendations, assigned actions, dissemination restrictions, and any actual review decision or follow-up results.

When a fact, cause, objective, assignment, or decision is unknown or not established, state the gap, its effect on the conclusion, and the resolving action with the actual owner if assigned. State inapplicability with a reason. A cause need not have been established for a review to record useful findings. Do not invent a root cause, lesson, action, approval, or separate incident record. When no incident record exists, identify the underlying evidence directly and state the record gap.

## Finished-document contract

- **Title:** Identify the incident and call the document an operational post-incident review.
- **Frontmatter:** Required. Begin with a YAML 1.2 Semantic-Discovery frontmatter block delimited by `---` lines containing `title`, `description` (60 to 140 neutral retrieval words), `topics` (3 to 12 concrete lowercase kebab-case terms), `use_when` (2 to 6 neutral task conditions), and conditional `not_for` (1 to 5 grounded exclusions, omitted when empty), followed by the GFM H1 title. Exclude internal IDs, version strings, hashes, filesystem paths, build metadata, and unresolved template delimiters from frontmatter values. Incident and review facts belong in the body. Governing source: Collection Semantic-Discovery Frontmatter contract.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. Omit it for internal documents unless a specific project policy requires explicit negative attestation. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Establish scope and evidence before analysis; place lessons and follow-through after the analysis. Heading wording may vary.
- **Presentation:** Use concise factual prose paired with structured evidence tables, chronologies, or finding lists sized to the performed activity. Required roles may share sections while keeping assessed configuration, criteria, actual observations, dispositions, and coverage limits strictly traceable.

| Projection | Title and metadata ownership | Syntax and source authority |
| --- | --- | --- |
| Operational post-incident review (standalone) | Begin with the mandatory 5-key Semantic-Discovery YAML frontmatter followed by one event- or assessment-specific H1. Activity identity, assessed configuration, actual timing, authority, and observed outcomes remain body content; external specification provenance and corpus-level default maintenance metadata apply where governed in a unified corpus. | Use GFM prose, tables, or logs bound to immutable inspected snapshots, artifact revisions, and real execution or review records. Historical observations remain tied to their recorded scope and time; later retests, changes, or approvals create distinct records rather than rewriting prior evidence. |

| Section role | Status and inclusion condition | Content obligation |
| --- | --- | --- |
| Review scope and evidence | Required | Identify the incident, affected operation and configuration, stabilization basis, review date, participants or contributing roles, and evidence cutoff. Cite the incident record if available. Summarize only the timeline and impact needed to understand the analysis, with disputed facts and evidence limitations. |
| Causes and contributing conditions | Required | Explain the analysis performed, supported causal factors, contributing conditions, hypotheses, and unresolved alternatives. State when no cause is established. Tie conclusions to examined evidence. |
| Response and recovery assessment | Required | Compare actual response and recovery with established objectives. Identify strengths, failures, delays, and constraints where supported. If objectives were not established, state that limitation and identify the basis of any retrospective judgment. |
| Lessons and recommendations | Required | State the lessons and systemic improvement opportunities derived from findings, with limits of applicability. An assessed statement that no lesson or change is yet supported is valid. |
| Improvement and follow-through | Required | Account for actions, priorities, owners, target dates, and effectiveness criteria; state explicitly when no action was derived. Describe permitted dissemination and supplied project reporting assignments, including audiences and timing. State review completion, any approval required by a supplied project condition, remaining uncertainty, and how open actions and effectiveness checks will be followed. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
| --- | --- | --- |
| Review context | One incident and one bounded review account. | Identify the reviewed incident state and evidence cutoff so later findings are not silently attributed to the earlier review. Give the actual review date and roles; do not invent meeting attendance. Stabilization does not imply full recovery or incident closure. |
| Evidence reference | One or more inspected sources supporting the account, or an explicit evidence gap. | Identify the source and relevant revision or observation time and locator. Distinguish observations from disputed accounts and inference. Summarize the chronology relevant to the analysis. New factual conflicts identify the source entry needing reconciliation. |
| Causal finding | Zero or more findings, with an explicit analysis result. | Each has a stable local identity, claim, supporting evidence, and classification as a supported cause, contributing condition, or hypothesis. Explain the reasoning and material alternatives or limitations. Temporal sequence alone does not establish causation. An unresolved cause stays unresolved. |
| Effectiveness finding | Zero or more findings plus an overall assessment. | Tie each judgment to actual response or recovery evidence and an identified objective or stated assessment basis. Metrics carry units, interval definitions, and uncertainty. A recovery observation is not a decision to accept the restored operation. |
| Lesson or recommendation | Zero or more, after assessment. | Tie each to a finding and identify the proposed improvement or useful practice to retain, intended benefit, and applicability limits. A recommendation is not an approved change. Avoid unsupported personal blame. |
| Improvement action | Zero or more actions actually proposed or agreed. | Give a local or existing master identity, originating finding or lesson, action, priority and its basis, owner, target date or trigger, status, and intended effectiveness check. Missing assignments and dates remain explicit. Cite an action master only when it exists. |
| Action status and evidence | One current state per action. | Use `proposed`, `planned`, `in-progress`, `blocked`, `completed`, or `cancelled`. Distinguish a proposal from an agreed assignment. Blocked actions name the blocker; cancelled actions give the reason. Completed actions cite completion evidence. State effectiveness separately as not assessed, supported, not supported, or inconclusive, with the actual check and evidence when assessed. |
| Dissemination | One account of permitted audiences, restrictions, and any required reports. | Distinguish intended distribution from actual sending. Identify supplied project reporting assignments, their assigning role, recipients, timing, and assignment locator; unknown details remain explicit. Restrict sensitive operational details and personal information; use controlled evidence locators where needed. |
| Review disposition | One as-of account of completed review work and remaining work. | State whether the review is complete or still open, and why. Identify any supplied project approval condition. Include the actual approval decision maker, decision, scope, and date when approval occurred; otherwise state pending, unknown, or not required with a basis. Identify who tracks outstanding actions, or the assignment gap, and any revisit trigger. Review completion and action effectiveness are separate conclusions. |

Use prose for causal reasoning and limitations. Use tables or distinct blocks for findings and lessons. When several actions exist, use an action table with identity, origin, action, priority, owner, target, status, and effectiveness check. A short timeline or causal diagram MAY clarify the analysis; distinguish hypothesized relationships from supported ones. Do not add empty rows, a generic document-control block, or sections unrelated to the assessed operational incident.

## Quality criteria

- The review addresses a stabilized operational incident and has an explicit evidence boundary and retrospective analysis.
- Every causal and effectiveness conclusion has a stated basis; conflicting evidence, alternatives, and uncertainty remain visible. No finding requires a single root cause or personal blame.
- Recommendations and actions trace to findings. An assessed absence of findings or actions is represented without fabricated items.
- Completion evidence and effectiveness evidence are distinguished. Incident status, open actions, and residual recurrence risk remain explicit at the review cutoff.
- Dissemination follows the actual restrictions. References identify existing project records or observed evidence.
