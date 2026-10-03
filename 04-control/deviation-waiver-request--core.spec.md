# Deviation or waiver request specification

## Identity and selection

- **Specification ID:** `DEVIATION-WAIVER-REQUEST@core`.
- **Purpose:** Request a bounded departure from an identified project requirement, baseline, process, or criterion while that obligation stays in force, and track justification, impact, effectivity, authority, and closure.
- **Intended readers:** The requester, the assessors of impact and residual exposure, the authority who can grant or refuse the departure, and the role that closes or restores compliance.
- **Decision or action supported:** Grant, refuse, bound, expire, or close one requested departure without changing the underlying obligation.
- **Use when:** A specific obligation should remain in force while a scoped, time-bounded or item-bounded departure is requested or its disposition is tracked.
- **Scope boundaries:** Bound the requested departure while retaining the underlying obligation and baseline. Track an actual grant or refusal with its decision maker and evidence; a request remains pending until a decision is made.

## Authoring inputs and unresolved facts

Inspect the requester, the obligation and its exact text or locator, whether the nonconforming result already exists, the departure asked for and what remains mandatory, the alternatives considered including restoration or a change to the obligation, the justification, the affected items and environments, the impact across safety, security, function, interfaces, quality, cost, schedule, support, and contract, any assessed risk record, the compensating controls and their limits, the authority that can decide, any actual grant or refusal, the requested and granted effectivity, the conditions and notices, and any expiry, restoration, or closure evidence.

When a fact is unknown or not decided, state that, its consequence, the resolving action, and the actual owner if assigned. Do not invent an obligation identifier, a control, a risk score, an authority, a date, or a restoration result. A departure whose obligation or bound is not identified is not ready to grant.

## Finished-document contract

- **Title:** Name the affected obligation or subject and identify the document as the deviation or waiver request for that departure.
- **Frontmatter:** None. Begin with the GFM title. The departure type, request state, effectivity, and authority belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State the definition in use, the obligation, and the departure before impact. State impact and controls before authority. Place effectivity and conditions with the authority. Place closure last. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Obligation and departure | Required | Give the request a stable identity, requester, request date when known, and current state. State the departure-type definition in use and apply one type. Identify each affected obligation, the specific departure, the requested extent, and what remains mandatory. Give the justification, the alternatives considered, and why compliance or a change to the obligation is not proposed. |
| Impact and controls | Required | For safety, security, function, interfaces, quality, cost, schedule, support, and contractual effect, state the assessed impact, that no impact was identified, or that the concern is not assessed. State residual exposure. Cite a risk record only when one exists. State the compensating controls, their limits, and how they will be checked, or state that none are proposed and the consequence. Record an actual check only when it has occurred. |
| Authority and effectivity | Required | State whether a grant or refusal exists. A grant identifies the authority, the obligation, the departure type, the scope, and the effectivity, and it is no broader than the assessed request. A refusal identifies the authority and reason. State the conditions and who must be told. Separate a requester withdrawal from a refusal. |
| Closure | Required | State the closure path: expiry, replacement by a later decision, restoration, and the closure authority. For `closed`, cite the restoration or final-disposition evidence. For `expired`, state the end condition and whether restoration evidence exists. For every earlier state, state which of these facts are not yet established. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Request identity | One identifier. | Keep it stable and identify this departure request distinctly from any related obligation, baseline, or decision. |
| Request state | Exactly one of `requested`, `assessed`, `authorized`, `rejected`, `expired`, or `closed`. | `requested` means impact is not complete. `assessed` means every named concern and the control position are addressed and no grant or refusal exists. `authorized` cites a grant covering this obligation, type, scope, and effectivity. `rejected` cites the refusing authority and reason. `expired` means the granted effectivity has ended. `closed` means the closure authority has accepted restoration or the final disposition. A withdrawal before a decision stays `requested` or `assessed`, names its actor and date, and is not `rejected`. Use before a grant does not make the state `authorized`. |
| Departure type | Exactly one of `deviation` or `waiver`, under one stated definition. | By default, a deviation is a planned departure requested before the nonconforming result exists; a waiver is a disposition of a nonconformity that already exists. If supplied project data establishes a different adopted definition, use it instead and state that complete definition, its project decision and revision when recorded, and the classification conditions for both types. A definition based on configuration-control status is used only when the project supplied and adopted it. Apply the stated definition consistently. The obligation stays in force under either type. |
| Affected obligation | One or more project requirements, baselines, processes, criteria, or configuration items. | State the affected obligation's complete requirement or criterion, including criteria from an internal project standard, and its edition, with a project-record locator when available. Use a controlled identifier when one exists. When none exists, name the obligation and say that it has no controlled identifier. Say what remains mandatory outside the departure. |
| Departure extent | One requested bound, and a granted bound when a grant exists. | Identify units, versions, environments, and start or end conditions that limit the departure. The granted bound is no broader than the assessed request. An unbounded departure is not ready to authorize. |
| Justification | One account. | Give the reasons, the alternatives actually considered, and why compliance or a change to the obligation is not the proposal. When no alternative was considered, say so. |
| Impact concern | The nine concerns named in the impact section. | Each is an assessed impact, no identified impact, or not assessed. Do not treat an unassessed concern as acceptable. |
| Compensating control | Zero or more real controls, or an explicit statement that none are proposed. | For each control, state its limit and the planned check. Cite a completed check only when it occurred. When none are proposed, state the consequence for residual exposure. |
| Risk citation | Zero or more real risk records. | Cite a record only when this request relies on it. The citation does not replace the residual-exposure statement and does not accept the risk. |
| Grant or refusal | Zero until an authority decides; one when it does. | The request text is not the decision. Identify the authority, date if known, obligation, type, and scope. A refusal is recorded as a refusal, not as a grant identifier. |
| Conditions and notices | One account. | State the constraints on the departure and who must be told. Later interpretation does not widen the grant. |
| Closure evidence | Required for `closed`; otherwise only evidence that exists. | Cite the restoration or final-disposition evidence the closure authority accepted. Planned checks are not results. `rejected` does not require restoration evidence. `expired` states whether restoration evidence exists. |

Use prose for the departure, justification, and conditions. Use a short list for obligations, controls, and evidence citations. Use a concern table only when each row has a real assessed, none-identified, or not-assessed value. Do not add an empty obligation or a generic document-control block.

## Quality criteria

- The obligation, the departure, what remains mandatory, and the requested bound identify one departure an authority can grant or refuse.
- The type uses the single complete definition the document states. Under the default definition, a planned departure requested before the nonconforming result exists is a `deviation`, and a disposition of an existing nonconformity is a `waiver`. Under a project-supplied adopted alternative, the type meets that definition's stated classification conditions.
- `assessed` and `authorized` require assessed impact concerns and an explicit control position. A rejection, withdrawal, or closure without a grant does not require invented completed assessments. On expiry or closure after a grant, retain the actual assessment basis and any gaps rather than implying that elapsed effectivity proved acceptability.
- `authorized` cites a grant whose scope and effectivity are no broader than the assessed request. The request text is not that grant.
- `rejected`, requester withdrawal, `expired`, and `closed` stay distinct, and each cites the actor and evidence that state requires.
- The obligation and the baseline remain unchanged by this request; each granted departure is bounded against their identified edition.
- Residual exposure is visible even when no risk record is cited. A missing authority, date, or restoration result stays missing.
