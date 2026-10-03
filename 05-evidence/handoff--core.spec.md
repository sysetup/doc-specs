# Handoff and transfer record specification

## Identity and selection

- **Specification ID:** `HANDOFF@core`.
- **Purpose:** Record one actual transfer of responsibility, custody, work, knowledge, configuration, or access between identified parties, including what moved, what remains open, and the receiving party's actual response.
- **Intended readers:** Delivering and receiving owners, operations and support roles, project leads, and authorities responsible for unresolved obligations.
- **Decision or action supported:** Determine who has which responsibility or custody now, what the receiver can use, what is pending, and whether further acceptance, access, training, or closure action is needed.
- **Use when:** A bounded transfer has begun or occurred and its actual contents, parties, receipt, and open obligations need a traceable record.
- **Scope boundaries:** Record the bounded transfer's actual events, contents, parties, and effective responsibility or custody. Receipt and receiving response require evidence beyond sending material.

## Authoring inputs and unresolved facts

Inspect the actual transfer event or sequence; the subject and boundary of responsibility or custody; delivering and receiving parties and their authority; what was actually delivered or demonstrated; versions, controlled locations, and access rights where relevant; effective time or overlap period; receipt evidence; agreed handover or readiness criteria and their satisfaction conditions; training or knowledge-transfer activity that occurred; unresolved defects, risks, exceptions, and assigned work; support and escalation arrangements; the receiving party's explicit handoff response, if any; and the project's retention and closure conditions. Identify the actual agreement, authorized assignment, or recorded event that shifted responsibility, its effective scope and time, independently of physical delivery.

If a receiver, item revision, receipt, authority, or handoff response is unknown, state the gap and its consequence, with a resolving action and actual owner if assigned. A handoff in progress may be recorded as partial; do not mark it complete by filling every section. When only knowledge or responsibility transfers, no product baseline or package is required. Cite an existing release, baseline, or acceptance record only if it exists. Do not include passwords, tokens, recovery codes, or other secrets; record the approved access-transfer mechanism and status instead.

## Finished-document contract

- **Title:** Identify the transferred subject and the parties or boundary, and call the document a handoff or transfer record.
- **Frontmatter:** None. Begin with the GFM title. Transfer scope, parties, and response belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Define transfer scope and parties before the transferred items and actions; put receipt, response, responsibility effect, and closure after those actions. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Transfer identity, scope, and parties | Required | Identify one bounded handoff, its actual date or period, delivering and receiving parties, their roles and authority, subject, exclusions, and intended versus effective responsibility or custody boundary. State any overlap or staged transfer. |
| Items and knowledge transferred | Required | List each actual deliverable, responsibility, work item, or knowledge component, with exact revision or scope and controlled locator when one exists. Distinguish offered, transferred, and still outstanding items. Include demonstrations, training, and support materials only when relevant and actually supplied. |
| Access and open obligations | Required | State access, ownership, licensing, and credential-transfer status where applicable without disclosing secrets. Record open defects, residual risks, exceptions, dependencies, and work with current and proposed owners; state an assessed absence if there are no open items in the declared scope. |
| Receipt and readiness | Required | State the evidence and scope of receipt, or that receipt is not confirmed. State each agreed readiness criterion and its satisfaction conditions when such criteria exist; assess examined evidence as not assessed, unmet, or met. Record any actual product or contractual acceptance by its deciding authority, scope, date, and decision evidence. |
| Receiving response and closure | Required | Record whether the receiving party agreed to assume the stated handoff scope and obligations: accepted, accepted with stated conditions, rejected, or not decided, with authority and date only when an actual response exists. State the effective responsibility or custody boundary independently, unresolved obligations, escalation or support route, and the actual or pending closure state. Bind the response to the handoff scope and obligations the receiver actually agreed to assume. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Handoff event | One bounded actual transfer process. | At least one real offer, transfer, demonstration, receipt, or responsibility-change event must have occurred. A plan alone is not this record. Record actual dates or sequence without fabricated precision. |
| Party | One delivering and one receiving party, with relevant roles. | A team or organization may act through an authorized representative. Identify the actual receiver; a proposed receiver does not prove custody or responsibility changed. |
| Transferred element | One or more actual elements. | Identify type, exact version or scope where relevant, controlled locator, sender, receiver, and status: `offered`, `transferred`, `received`, or `outstanding`. These states are distinct; the same element may progress through them with dated evidence. |
| Baseline or package | Conditional on transfer of a controlled configuration or delivery package. | Identify its exact revision and manifest or location when it exists. A pure duty, knowledge, or work transfer does not require a baseline or a bill of materials. |
| Access transfer | Conditional on access or license rights being part of the handoff. | State granting authority, scope, recipient, status, validation, and revocation or overlap of old access when relevant. Name a secure credential-transfer mechanism, not the credential itself. |
| Knowledge transfer | Conditional on training, demonstrations, instructions, or support overlap being material. | Record what actually occurred, who participated, and what remains pending. A planned session is not competence evidence. |
| Open item | Zero or more after assessment. | Identify each issue, risk, exception, dependency, or remaining task, its impact and current owner, and the receiving owner's obligation only if agreed or imposed by authority. An assessed-empty statement is permitted. |
| Receipt | One status for the declared transfer scope: `confirmed`, `partial`, `not-confirmed`, or explicitly unresolved. | Cite acknowledgment or observed access to the exact elements received. Bind receipt to those elements and the observed date; state readiness, receiving response, and responsibility effect using the evidence required for each field. |
| Readiness assessment | Conditional on an agreed criterion or gate. | State the criterion and satisfaction conditions, evidence actually examined, assessor, result, and open condition. Use `not-assessed` when no assessment occurred, `unmet` when examined evidence does not satisfy the criterion, or `met` when it does. If no agreed readiness gate exists, state that fact without inventing one. |
| Receiving response | One state about the handoff scope and obligations: `accepted`, `accepted-with-conditions`, `rejected`, or `not-decided`. | A favorable response identifies the actual authorized receiving party, scope, date, and conditions it agreed to assume. `not-decided` records the absence of a decision. Cite an actual product or contractual acceptance decision only with its authority, scope, and basis. |
| Responsibility effect and closure | One statement of effective responsibility and one closure status. | Identify the actual agreement, authorized assignment, or recorded event that shifted ownership and its effective scope and time. `closed` requires the actual closure conditions and evidence; open obligations and an undecided response remain visible. Record supplied retention conditions and the party responsible for retaining the record. |

Use an item table when multiple deliverables or duties have different receipt states, and an action list for open obligations. A timeline helps staged transfers or overlap. Prose explains authority, responsibility effect, and limits. Do not add a blank deliverable, generic document-control block, or acceptance signature panel without an actual project rule.

## Quality criteria

- A reader can tell exactly what transferred, what remains with the sender, and who is responsible now. Each material item has a version or bounded scope and an actual status.
- Receipt, readiness, the handoff response, product acceptance when applicable, and responsibility transfer each have their own evidence and authority. None is inferred from sending a file or completing a section.
- Access rights are recorded without secrets. Pending access, failed validation, and old access that remains active are visible when material.
- Open defects, risks, and work keep an accountable route; absent owners and unresolved receiving responses are not silently filled.
- A handoff can be partial or pending without claiming closure. A release or baseline reference is used only when the corresponding record or event exists.
