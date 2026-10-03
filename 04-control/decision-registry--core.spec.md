# Decision registry specification

## Identity and selection

- **Specification ID:** `DECISION-REGISTRY@core`.
- **Purpose:** Provide one index of controlled decisions so a reader can find each decision's master record, the status and supersession stated there, and the scope that master affects.
- **Intended readers:** The registry steward, decision authorities, and consumers who need to know which decisions are current without reading every master.
- **Decision or action supported:** Locate the authoritative decision record, see the status and review point carried by its cited revision, and detect conflicts or missing masters.
- **Use when:** Multiple controlled decisions need a single index and status view while each substantive decision remains in its master.
- **Scope boundaries:** Index authorized decisions using summaries, status, scope, supersession, and review points from their cited master revisions. Keep rationale, alternatives, and detailed consequences out of the index; listing an entry does not authorize a decision.

## Authoring inputs and unresolved facts

Inspect which decision classes and authorities are in scope, where those masters are kept, and the identifier and update rules. For each candidate, inspect the master record, its immutable revision or the absence of one, the decision statement and status in that revision, the affected scope, any supersession the master states, and the review trigger or expiry the master states.

If a master, revision, status, or trigger is missing, keep the gap visible and state its consequence, the resolving action, and the actual steward if assigned. Do not invent a decision, a rationale, a status, a supersession, or a review date. If the scope was assessed and no controlled decision qualifies, say so instead of adding a sample entry. Do not index a question that has no authorized decision record.

## Finished-document contract

- **Title:** Identify the project or decision scope and name the document as its decision registry.
- **Frontmatter:** None. Begin with the GFM title. Classes, masters, and index status belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State index rules before entries; place conflicts and gaps after the entries. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Index rules | Required | State the decision classes and accountable authorities included, the registry steward, where masters live, the identifier policy, how new, revisited, and superseded decisions are added, how conflicting masters are shown, and who consumes the index. State the date through which the index was checked against those masters. |
| Decision index | Required | Include every in-scope decision that has a master, or an explicit assessed-empty statement. For each entry, give the index identity, the master reference and revision, an index summary taken from that revision, the status stated by that revision, the affected scope, any supersession that revision states, and the review trigger stated by that revision. |
| Conflicts and gaps | Required | Identify missing or unstable revisions, status or triggers not stated by the cited master, index values that differ from the master, and two masters that disagree. Name which record prevails only when an authorized decision says so. Give the consequence and route, or state that the assessed scope showed none. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Index entry | One row for one master decision; zero only when the scope was assessed and no controlled decision qualifies. | Use an immutable index identifier that is not presented as the decision's own identity. Do not add a row for a recommendation, review, or undecided question. |
| Master reference | One controlled decision record per entry. | Cite the actual authorized decision record that holds the decision and its rationale. If that record does not exist, there is no index entry. |
| Master revision | One cited revision per entry. | Identify the master location and the immutable revision checked. If the master has no revision, state that limit and do not invent one. Status and summary in the row MUST match this revision. |
| Index summary | One short statement of what was decided. | Take it from the cited revision. It orients the reader and is not a second master. If the master text is unavailable, say so; the row then cannot stand in for the decision. |
| Decision status | The status stated by the cited master revision. | Quote or faithfully restate the master's own status. Do not apply a separate registry lifecycle. If the master states no status, write that it is not stated. |
| Affected scope | One statement of what the cited revision says is affected. | Report the architecture, requirements, baselines, or other subjects the master actually names. Do not force those examples when the master names different subjects. If it names none, say so. |
| Supersession | Zero or more relationships stated by the master. | Identify each predecessor or successor and the relationship direction only when the cited revision or an authorized update says so. An intermediate decision may both replace an earlier decision and be replaced by a later one; cite the update revision when it supplies that relationship. Do not infer supersession from dates or from coexistence in the index. |
| Review trigger | The next review trigger or expiry taken from the master. | If the master states none, say so. Do not invent an expiry and do not change the trigger independently of the master. |

Use one row or short block per decision. Do not add an empty entry or copy the master's rationale, alternatives, or consequences into the index.

## Quality criteria

- Every row cites a real master and a revision a reader can retrieve, or the row visibly states that the revision is not established.
- The summary, status, affected scope, supersession, and review trigger agree with that cited revision.
- The index does not create, authorize, or reverse a decision by listing it.
- Conflicting masters remain visible until an authorized decision selects one.
- Each entry identifies an authorized decision; candidates awaiting a decision remain visible as gaps rather than decision entries.
