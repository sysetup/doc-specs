# Assumption and dependency register specification

## Identity and selection

- **Specification ID:** `ASSUMPTION-DEPENDENCY-REGISTER@core`.
- **Purpose:** Control assumptions, dependencies, and constraints that materially affect requirements, architecture, plans, risk, schedule, or operations, including their owners, validation or resolution, impact, and disposition.
- **Intended readers:** Owners of those statements, planners and architects who rely on them, and reviewers who decide whether one must become a risk, issue, change, or decision.
- **Decision or action supported:** Determine which relied-upon statements are still open, what follows if an assumption is false or a dependency is unavailable, and what evidence or escalation their disposition requires.
- **Use when:** Assumptions, dependencies, or constraints materially affect requirements, architecture, plans, risk, schedule, or operations and need ownership, validation or resolution, and lifecycle control.

## Authoring inputs and unresolved facts

Inspect the scope in which a statement would materially affect requirements, architecture, plans, risk, schedule, or operations. Inspect why the statement is believed or relied upon, who owns its resolution, the impact if it is false or unavailable, the action or evidence that would confirm or retire it, and any real related record.

If the owner, impact, provider, or review date is unknown, keep the entry visible and state the gap, its consequence, the resolving action, and the actual owner if assigned. Do not invent a confirming result, a provider, or a risk score. If the scope was assessed and no statement qualifies, say so instead of adding a sample entry. When an entry relies on an established project obligation, identify that obligation and its project record as the related record; state the assumption, dependency, or constraint being controlled.

## Finished-document contract

- **Title:** Identify the project or system boundary and name the document as its assumption and dependency register.
- **Frontmatter:** None. Begin with the GFM title. Rules, statements, and dispositions belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State selection and disposition rules before entries; place escalation gaps after the entries. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Selection and disposition rules | Required | State what makes a statement material enough to control, the register's currency date, the review cadence or triggering events, the conditions that require a risk, issue, change, or decision record, and the evidence or authority required before an entry is confirmed, satisfied, invalidated, superseded, or closed. |
| Controlled entries | Required | Include every in-scope assumption, dependency, and constraint, or an explicit assessed-empty statement. For each entry, give its stable identity, kind, statement, source, status, owner or assignment gap, impact if false or unavailable, validation or resolution action, review timing, and related records that actually exist. |
| Escalation gaps | Required | Identify entries whose escalation condition is met while the required risk, issue, change, or decision record does not exist, and entries whose status claims evidence the closure rule requires but the entry does not cite. Give the consequence and route, or state that the assessed scope showed none. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Controlled statement | One assumption, dependency, or constraint; zero only when the scope was assessed and no statement qualifies. | Use one immutable identifier and exactly one kind: `assumption`, `dependency`, or `constraint`. Do not reuse the identifier for another statement. |
| Statement | One intelligible claim per entry. | An assumption states a condition treated as true although it is not yet an established project fact. A dependency states reliance on a provider, product, decision, or event outside the relying party's direct control and names that provider, or states that the provider is not established. A constraint states a limit on the work. |
| Source | One origin per entry. | Identify the person, record, observation, or rationale from which the statement came. Unknown origin stays unresolved. |
| Status | Exactly one of `open`, `confirmed`, `invalidated`, `satisfied`, `superseded`, or `closed`. | `open` means no later outcome is established. `confirmed` means cited evidence supports the statement, including a constraint that remains binding. `invalidated` means cited evidence contradicts it or shows that a dependency cannot be met as stated. `satisfied` means a dependency is available as needed, or a one-time constraint has been fulfilled under the closure rule; do not use it for an assumption or for a constraint that remains in force. `superseded` cites the later controlled statement that replaces it. `closed` means the closure rule is complete, including its authority; closing an entry does not by itself establish that its statement is true or that its dependency is available. Belief, a planned action, or silence is not `confirmed`, `satisfied`, or `invalidated`. |
| Owner | One accountable role once assigned. | The owner monitors or resolves the entry. An unassigned owner stays unresolved. |
| Impact if false or unavailable | One statement of potential technical, cost, schedule, operational, or assurance impact. | State the impact that would follow if the assumption is false, the dependency is unavailable, or the constraint is violated. Distinguish unknown impact from assessed impact. Do not add a likelihood or risk score here. |
| Validation or resolution action | One current action statement per entry. | State the action still required to confirm, satisfy, invalidate, or retire the entry. Cite actual evidence only when it exists. A planned action is not itself evidence. |
| Review timing | One date or an explicit timing disposition. | Use `YYYY-MM-DD` when a review or due date applies. Otherwise state that the date is unknown or not applicable and why. |
| Related record | Zero or more real requirements, architecture elements, risks, changes, plans, or evidence records. | Identify each existing record and its relationship to the entry; keep required but absent records visible as escalation gaps. |

Use one row or short block per entry. Do not add an empty entry.

## Quality criteria

- A reader can distinguish assumptions, dependencies, and constraints using the kind and statement defined for each entry.
- Status matches the kind and rests on the evidence or authority the closure rule names.
- Each active entry has an owner or a visible assignment gap, a stated impact, and a validation or resolution action that is still required, or no longer required because the status already cites its evidence.
- Escalation conditions that have been met point to a real risk, issue, change, or decision record, or remain visible as gaps.
- An `open` entry keeps the statement or dependency availability unresolved; confirmation and satisfaction cite actual supporting evidence.
