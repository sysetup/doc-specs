# Engineering meeting record specification

## Identity and selection

- **Specification ID:** `MEETING-RECORD@core`.
- **Purpose:** Preserve an ordinary meeting's actual subjects, discussion, decisions, open questions, and assigned follow-up.
- **Intended readers:** Participants, coordinating roles, affected owners, and authorized readers needing the meeting context.
- **Decision or action supported:** Recover what was discussed and assigned without inferring technical-review disposition or approval.
- **Use when:** A held engineering or coordination meeting has information that needs durable preservation.
- **Scope boundaries:** Record one actual ordinary meeting or coherent session series; exclude planned agendas alone, technical reviews governed by assessment criteria, authoritative decision masters, and automatic consensus claims.

## Authoring inputs and unresolved facts

Inspect the actual meeting purpose and date precision, participants when recorded, source notes or permitted recording, subjects actually discussed, distinct positions and unresolved questions, actual decisions and authority when established, action assignments, and permitted distribution.

Expose missing time, participants, source, decision authority, owner, or due date with its effect, resolving action, and assigned owner if known. A meeting that was not held has no finished meeting record. Unconfirmed recollection stays unconfirmed; silence, attendance, and draft minutes establish neither consensus nor approval. Do not invent statements, actions, signatures, or decisions.

## Finished-document contract

- **Title:** Identify the meeting subject and actual date or date gap and name its meeting record.
- **Frontmatter:** None. Begin with the GFM title. Identity, scope, and state belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State held-event identity and purpose before subjects and discussion; put actual decisions and open questions before follow-up and record limitations. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Held meeting and evidence basis | Required | Identify purpose, actual date or session dates and precision, meeting scope, participants or participation gap, note or recording basis, audience limits, and client or receiving-party element. |
| Subjects and factual discussion | Required | Summarize actual subjects and material factual discussion, distinguishing speaker positions, observations, proposals, and uncertainty. Preserve recorded disagreement; do not turn an unused agenda item into discussion. |
| Decisions and open questions | Required | State actual decisions with deciding role, scope, and authority basis when established, or that none were recorded. Identify unresolved questions, rejected proposals where actually decided, and existing decision masters; a proposal has no decision status. |
| Follow-up and record limitations | Required | State actions actually assigned, deliverable, owner or gap, due date or scheduling disposition, and actual action links. Include source, capture, confidentiality, correction, and confirmation limits and any actual review of the minutes without implying institutional approval. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Meeting event | Exactly one held meeting or bounded related session series in Held meeting and evidence basis. | No planned-only event qualifies; date precision and participants come from actual sources. |
| Discussion subject | One or more actual subjects in Subjects and factual discussion. | Preserve facts versus proposals and recorded dissent; unrecorded speech is not reconstructed as quotation. |
| Meeting decision | Zero or more in Decisions and open questions. | State actual deciding authority and scope or explicit authority gap; substantive decision masters remain controlling when they exist. |
| Open question | Zero or more in Decisions and open questions. | Name what remains undecided and its resolving route; silence is not a decision. |
| Assigned follow-up | Zero or more in Follow-up and record limitations. | Give actual deliverable, assignment or owner gap, and scheduling basis; do not invent closure or create a duplicate action master. |
| Record limitation or correction | Exactly one limitations account and zero or more actual corrections in Follow-up and record limitations. | Keep uncertainty, restricted disclosure, and original-to-corrected meaning traceable; minutes review is distinct from approval of meeting proposals. |

Use a concise narrative or subject table with separate decisions, questions, and follow-up lists. Routine meetings need records only when the information purpose warrants them. Minimize participant data and link decision or action masters instead of duplicating their current states.

## Quality criteria

- The meeting occurred, and date, participants, source basis, and permitted audience are established or visible gaps.
- Actual subjects and discussion preserve proposals, observations, disagreement, and capture uncertainty.
- Decisions and open questions retain actual authority and pending state without inferred consensus or approval.
- Follow-up, corrections, and limitations match actual assignments and source records; no invented closure appears.
