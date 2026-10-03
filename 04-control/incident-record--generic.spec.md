# Operational incident record specification

## Identity and selection

- **Specification ID:** `INCIDENT-RECORD@generic`.
- **Purpose:** Record the facts, chronology, impact, response actions, evidence handling, current status, and closure of one suspected or confirmed operational incident that is not being handled as a cybersecurity incident.
- **Intended readers:** The incident lead, authorized responders, affected service owners, and anyone who must act on the current account or preserve it for later review.
- **Decision or action supported:** Direct the response, see what is contained or restored, and decide whether the incident remains open, using a chronology that can be corrected without rewriting history.
- **Use when:** A suspected or confirmed operational incident needs a contemporaneous record and is not being handled as a cybersecurity incident. Retain the account if the event is later determined not to be an incident.
- **Scope boundaries:** Cover contemporaneous operational response facts and status. Exclude cybersecurity-specific detection, indicator, eradication, and notification content, and retrospective causal analysis or lessons.

## Authoring inputs and unresolved facts

Obtain the current factual situation, discovery source, discovery and declaration times, affected scope, severity or category, declaration authority, incident lead, authorized responders, target or environment, and permitted actions. Obtain each timeline event's time, type, actor, description, impact, and any real evidence. Obtain what evidence was collected, its custody and access limits, the current containment state, the current recovery state, open issues, and whether a closure decision exists.

If a fact, time, actor, authority, or impact is unknown or not established, state that, its operational consequence, the resolving action, and the actual owner if assigned. Do not invent an observation, a timestamp, a person, an approval, a containment result, or a closure. A described action is not permission to repeat it. Cite a playbook, runbook, defect report, or review only when that record exists.

## Finished-document contract

- **Title:** Name the incident and identify the document as its operational incident record.
- **Frontmatter:** None. Begin with the GFM title. Incident identity, declaration, and status belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State declaration and command before the chronology. Place evidence handling before current status. Place closure last. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Declaration and command | Required | Give the incident a stable identity and the time this version of the record represents. State the current situation, discovery source, discovery and declaration times, and affected scope, including what is still unknown. State the severity or category, whether an authority has declared the incident, and who holds command, which responders may act, the target or environment, and which actions are permitted. |
| Chronology | Required | Append observations, decisions, actions, communications, and corrections in recording order, preserving each event's occurrence time separately. A late-reported event states that delay; unknown occurrence times remain unknown. A correction is a later entry that identifies the earlier event and the change. For each event, state the actor and authority basis, label any hypothesis, and state the impact known then, that no additional impact was established, or that impact is unknown. |
| Evidence handling | Required | State what was collected or that nothing was collected. Cover collection authority, provenance, integrity, custody and transfers, confidentiality, retention, and access. Retain known limitations and conflicts. Do not place secrets or unnecessary sensitive raw evidence in the record; give a locator and the handling restriction instead. |
| Status and closure | Required | State containment and service or operational recovery as separate current states, plus open issues and the next update time when one exists. If the incident is open, say that closure has not occurred. If it is closed, state the criteria met, the closing authority, and the time. Cite a later review only when one exists. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Incident identity | One stable identifier for this incident. | Do not reuse it for another incident. It is not a document-lifecycle state. |
| Record time | One as-of time for this version of the record. | Use a date-time with an explicit offset, or state that the clock time is unknown. State clock confidence when a time is given. A later update changes the as-of time and does not silently rewrite earlier events. |
| Accountable role | One incident lead, or an explicit gap. | Name the role and its limit. Do not invent a person. Permitted actions are authority limits, not actions already taken. |
| Declaration | One current declaration position. | State `not-declared`, `declared`, or `determined-not-an-incident`, the authority, and the time when known. Reclassification to a cybersecurity incident records that decision and identifies any actual continuation record. Severity remains the project's own category. |
| Affected scope | One current scope account. | Name the services, sites, people, or other operational subjects affected, or state that the scope is unresolved. A finding of no affected subjects identifies the assessed scope, evidence, and limitations; an empty list alone is not that finding. |
| Timeline event | One or more events. | Each has a stable local identity, a description, an occurrence time and a recording time, each with an explicit unknown when unavailable. The first event may be the opening of the record when the occurrence time is unknown, and it must say so. Each event has one type: `observation`, `decision`, `action`, `communication`, or `correction`. Each event states the actor and authority basis, or states that the actor or authority basis is unknown. Known timestamps include an offset and clock confidence; retain partial times or bounds explicitly without inventing precision. Evidence references cite real evidence only. Record operational stakeholder notices as communication events. |
| Evidence account | One handling account. | Separate material not collected, material collected, and material whose custody is unknown. A planned preservation step is not custody of an artifact. |
| Containment state | One current state. | State whether the harmful condition is contained, not contained, unknown, or not applicable, and the basis. Inapplicability requires evidence that no harmful condition needs containment in the assessed scope. This is not service recovery and not closure. |
| Recovery state | One current state. | State whether the affected operation is restored, partially restored, not restored, unknown, or not applicable, with a basis. Inapplicability requires evidence that no operation needs restoration in the assessed scope. Restoration is not a decision to accept the restored operation. |
| Closure | One current closure position. | `open` identifies remaining issues and does not name a closing authority. `closed` cites the criteria, authority, and time. Lessons are outside this record. |

Use prose for the situation, command, and evidence handling. Use a chronology table when several events must be compared; each row is a real event. Do not add an empty event, a generic document-control block, or cybersecurity detection, indicator, eradication, or notification sections.

## Quality criteria

- The record is about one suspected or confirmed operational incident, retaining any later rejection of that classification, and does not carry cybersecurity-only detection, indicator, eradication, or notification content.
- Declaration, severity, command, and permitted actions are either sourced or visibly unresolved. A hypothesis is labeled as a hypothesis.
- The chronology retains superseded statements through correction events. Each event states its actor and authority basis, or states that the actor or authority basis is unknown. Impact is not invented for an event that has none.
- Containment, recovery, and closure are separate. An open incident does not claim a closing authority.
- Evidence handling matches the artifacts actually identified. Missing custody, time, or authority stays missing.
- A cited playbook, runbook, defect report, action, or review exists.
