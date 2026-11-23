---
title: "Approval and acceptance decision record specification"
description: >-
  Defines the authoring contract for authoritative records preserving one actual authorized decision—approval, acceptance, authorization, rejection, conditional decision, or withdrawal—bound to a specific subject and revision. Covers decision kind, decision maker and authority basis, criteria and evidence examined, explicit outcome, decision timestamp, attached conditions or effectivity limits, independence notes, and follow-through evidence while ensuring pending requests, recommendations, attendance, or delivery alone never masquerade as an actual decision.
topics:
  - "evidence"
  - "quality-assurance"
  - "governance"
  - "approval-record"
  - "acceptance-decision"
  - "decision-authority"
  - "effectivity-conditions"
  - "formal-signoff"
use_when:
  - "An authorized person or governance body has made an approval, acceptance, authorization, rejection, or withdrawal decision requiring a durable record."
  - "An author is binding a formal decision outcome, authority basis, conditions, and effectivity limits to an exact subject revision."
  - "A reviewer is confirming whether a claimed signoff rests on real authority and evidence rather than a recommendation or delivery."
not_for:
  - "Recording technical architecture tradeoffs and design choices, which belong in an architecture decision record."
  - "Indexing multiple decisions across a project without full decision authority records, which belongs in a decision registry."
  - "Documenting technical review findings prior to separate formal acceptance, which belongs in a design review record."
---

# Approval and acceptance decision record specification

## Identity and selection

- **Specification ID:** `APPROVAL-ACCEPTANCE-RECORD@core`.
- **Purpose:** Record one actual authorized decision about a defined subject and revision, preserving the kind of decision, authority, basis, outcome, conditions, and effectivity.
- **Intended readers:** The deciding authority, affected owner or recipient, configuration and release roles, and anyone who must rely on or challenge the decision.
- **Decision or action supported:** Determine precisely what was approved, accepted, authorized, rejected, conditionally decided, or withdrawn and whether the decision applies to the present subject and time.
- **Use when:** An authorized person or body has actually made a bounded approval, acceptance, authorization, rejection, or withdrawal decision and it needs an authoritative record.
- **Scope boundaries:** Record an actual decision on the identified subject. A pending request, recommendation, attendance, signature image, or delivery alone does not establish that decision or its kind.

## Authoring inputs and unresolved facts

Inspect the decision event or executed project workflow; the exact subject identity, revision, configuration, and effectivity; the internal assignment or delegation of decision rights and its scope and validity period; the decision maker or constituted body and the project's explicit quorum or independence conditions; the decision kind and actual wording; the concrete criteria and evidence considered; objections or limits that materially affect interpretation; conditions, expiry, and required follow-up; the recorded decision date or time; and any earlier decision being replaced or withdrawn.

If the decision has not happened, do not write a finished decision record. If a claimed decision exists but its authority, subject revision, or authentic decision evidence cannot be established, describe the gap and do not present it as an effective approval, acceptance, or authorization. State the resolving action and actual owner if assigned. The finished document itself may be the controlled evidence when the decision maker actually executes it using the recorded project decision mechanism. When it reports a decision made elsewhere, cite that event or record. Do not invent a signature, identity, criteria, timestamp, or favorable outcome.

## Finished-document contract

- **Title:** Name the subject and decision kind, and identify the document as a decision record.
- **Frontmatter:** Required. Begin with a YAML 1.2 Semantic-Discovery frontmatter block delimited by `---` lines containing `title`, `description` (60 to 140 neutral retrieval words), `topics` (3 to 12 concrete lowercase kebab-case terms), `use_when` (2 to 6 neutral task conditions), and conditional `not_for` (1 to 5 grounded exclusions, omitted when empty), followed by the GFM H1 title. Exclude internal IDs, version strings, hashes, filesystem paths, build metadata, and unresolved template delimiters from frontmatter values. The decision and its authority are body content. Governing source: Collection Semantic-Discovery Frontmatter contract.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. Omit it for internal documents unless a specific project policy requires explicit negative attestation. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Identify the subject and authority before the assessed basis; state the decision after that basis, followed by effectivity and obligations. Heading wording may vary.
- **Presentation:** Use concise factual prose paired with structured evidence tables, chronologies, or finding lists sized to the performed activity. Required roles may share sections while keeping assessed configuration, criteria, actual observations, dispositions, and coverage limits strictly traceable.

| Projection | Title and metadata ownership | Syntax and source authority |
| --- | --- | --- |
| Approval and acceptance decision record (standalone) | Begin with the mandatory 5-key Semantic-Discovery YAML frontmatter followed by one event- or assessment-specific H1. Activity identity, assessed configuration, actual timing, authority, and observed outcomes remain body content; external specification provenance and corpus-level default maintenance metadata apply where governed in a unified corpus. | Use GFM prose, tables, or logs bound to immutable inspected snapshots, artifact revisions, and real execution or review records. Historical observations remain tied to their recorded scope and time; later retests, changes, or approvals create distinct records rather than rewriting prior evidence. |

| Section role | Status and inclusion condition | Content obligation |
| --- | --- | --- |
| Subject and decision scope | Required | Identify exactly one decision, its kind, subject ID and immutable revision or configuration, affected parties, boundary, and the question submitted to authority. For a withdrawal, identify the prior decision being withdrawn. |
| Authority and basis | Required | Identify the actual decision maker or body, its role, assigned or delegated decision rights, scope and validity, the concrete criteria, and the evidence it considered. State any required project independence, quorum, or delegation conditions and their observed satisfaction or gap. State any evidence or authority gap explicitly. |
| Decision and conditions | Required | Record the actual decision wording and outcome, the decision date or time as recorded, the scope and effectivity, and any conditions, exclusions, expiry, or limits. Make the effect of an unmet condition explicit. Separate a conditional grant from a completed unconditional grant. |
| Evidence and follow-through | Required | Provide the authentic decision evidence: this executed record or a real signed/workflow record with locator. Identify notification, responsible follow-up, condition verification, and supersession or appeal route when the recorded decision or explicit project decision procedure requires them. State whether effect is current, pending a condition, expired, or withdrawn when that can be established. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
| --- | --- | --- |
| Decision | Exactly one actual bounded decision per record. | Do not combine unrelated subject revisions, authorities, or decisions in a single row. A later reversal or materially new decision gets its own traceable event or revision under project rules. |
| Decision kind | One type of authority exercised. | Use the project's precise kind, such as document approval, baseline establishment, release authorization, change authorization, waiver, risk acceptance, product acceptance, review-gate disposition, operational authorization, or closure. `Other` needs a specific name and authority. These kinds do not substitute for each other. |
| Subject | One exact entity or bounded set and immutable revision/configuration. | Identify effectivity by time, unit, location, recipient, or other relevant boundary. A mutable title or branch alone does not bind the decision. |
| Decision maker | One identifiable person or constituted body, with role. | State the authority basis and actual participation. A role label without evidence that the holder decided is not a decision. When a body acts, state any required project quorum or delegation condition and its observed result. |
| Authority basis | One or more internal assignments or delegations when the decision rights depend on an authority chain. | State who assigned or delegated which decision rights to whom, the subject boundary, validity period, and any restrictions. Identify each actual assignment record's title or ID, revision, relevant entry, and locator. An unestablished assignment limits the claimed authority. |
| Criteria and evidence | The actual basis considered, or an explicit statement that a discretionary decision used no technical assessment. | State each criterion's concrete required condition, identify the evidence version, and describe any unmet or unassessed condition material to the outcome. Identify the supplied project requirement, allocation, or decision that established a criterion when known. |
| Outcome | One actual disposition in the authority's terms. | `Approved` applies to approval, `accepted` to acceptance, and `authorized` to permission; `rejected` denies the requested effect. A `conditional` outcome must name the underlying decision kind, conditions, verifier, and when effect begins. `Withdrawn` identifies the prior decision and the actual withdrawal authority and effectivity. Do not default to a favorable value. |
| Decision time | One date or timestamp actually recorded. | Preserve the source's precision and timezone if it records a time. Do not invent seconds or an offset from a date-only record. |
| Decision evidence | One authentic controlled record or workflow event, which may be this finished document. | Identify execution or approval mechanism, decision maker, revision, and locator. A typed name or image of a signature does not prove authority by itself. |
| Condition or limit | Zero or more, stated explicitly when the decision is conditional. | Give each condition's required result, responsible party if assigned, deadline or trigger when imposed, verifier, and actual closure state. An unmet condition cannot be silently treated as satisfied. |
| Independence | Conditional on an explicit project separation-of-duties or independent-assessment condition. | State the required separation or assessor relationship and its observed satisfaction or gap. Do not add a generic independence assertion when no such condition applies. |

Use prose for the decision and rationale. Use a compact table only when several conditions, criteria, or evidence items must be tracked separately. Do not add a blank decision row, a generic lifecycle block, or a fabricated signature panel.

## Quality criteria

- The decision is one real act by an identifiable authority on an exact subject revision and bounded effectivity.
- Decision kind and outcome agree. The claimed effect is limited to the rights actually exercised and the subject, revision, and conditions actually decided.
- Favorable outcomes do not hide unmet criteria, absent evidence, expired authority, or open conditions. State the actual operative effect.
- The record's execution evidence identifies the actual decision maker, mechanism, and subject revision. A draft record cannot itself create the decision it describes.
- Any withdrawal or supersession preserves the earlier decision and explains what ceased to apply, when, and by whose authority.
