# Observability register specification

## Identity and selection

- **Specification ID:** `OBSERVABILITY-REGISTER@core`.
- **Purpose:** Record the watched signals, their thresholds, their owners, and the response each signal calls for.
- **Intended readers:** The owners of those signals and the people who must know which signal is watched, at what threshold, and what response applies.
- **Decision or action supported:** Determine the controlled list of watched signals and the threshold, owner, and response for each.
- **Use when:** A service or system needs a controlled list of the signals it watches and the response attached to each threshold.
- **Scope boundaries:** Record watched signals and their established thresholds, ownership, and response instructions. Exclude operating-duty assignment decisions, detailed execution steps, event chronologies, and observed threshold-crossing or response results.

## Authoring inputs and unresolved facts

Obtain the service or system, the as-of point, and each signal that is actually watched, including its threshold, owner, and response when those facts are established. Obtain the existing assignments and response instructions that establish those fields when available.

If a signal, threshold, owner, or response is unknown, record the gap. Do not invent a metric, a threshold, an owner, or a response. A response names what to do or which existing procedure applies. Keep prescribed actions distinct from observed events. Do not assign `pass`, `fail`, `inconclusive`, or `not-run`.

## Finished-document contract

- **Title:** Identify the service or system and name the document as its observability register.
- **Frontmatter:** None. Begin with the GFM title. The service and as-of point belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Identify the service before the signal list. State gaps with or after the list. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Identity and scope | Required | Identify the service or system and the as-of point. Include the client or receiving-party element from this contract. Identify established assignment or response-instruction records when they explain signal ownership or response. |
| Watched signals | Required | For each watched signal, state the signal, the threshold, the owner, and the response. If no signal is watched, say so instead of adding a placeholder signal. |
| Gaps | Required | Identify missing thresholds, owners, or responses, and the next action. A missing threshold is not a silent default. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Service or system | One service or system per register. | State the as-of point. A signal for a different service does not belong in this list. |
| Signal | Zero or more watched signals. | Name the signal and what it measures. Do not invent a metric to fill the list. |
| Threshold | The threshold that calls for a response, when established. | State the comparison and the units. An unknown threshold stays unknown. |
| Owner | One owner for each signal that has one. | The owner is accountable for the signal on this list. An unassigned owner stays unassigned. Do not invent a person or party. |
| Response | The response the threshold calls for, when established. | Name the action or an existing procedure. Describe the prescribed response without claiming it occurred. |
| Operating duty | No operating-duty description as a substitute for a signal row. | Keep signal, threshold, owner, and response fields explicit. |

Use a register table with signal, threshold, owner, and response. Prose should explain a threshold the table would make ambiguous. Do not include a blank signal row.

## Quality criteria

- Each watched signal states its known threshold, owner, and response, or the missing fact is explicit.
- Each owner or response reflects an established assignment or instruction.
- Threshold comparisons and response instructions describe when action is called for and what action is prescribed.
- Unknown thresholds, owners, and responses stay visible. The register invents no signal, threshold, owner, or party.
