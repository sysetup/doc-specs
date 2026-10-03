# Release record specification

## Identity and selection

- **Specification ID:** `RELEASE-RECORD@core`.
- **Purpose:** Record one actual release attempt or event, including the exact configuration targeted and any part offered, authority, distribution or deployment actions, observed checks, exceptions, and resulting state.
- **Intended readers:** Release and configuration managers, operators, support teams, recipients, and authorities who must determine what was made available and under what conditions.
- **Decision or action supported:** Identify the target configuration and any bytes or items actually made available, establish what happened at each channel or recipient, and decide whether further delivery, recovery, notification, or investigation is needed.
- **Use when:** A release action has begun or occurred and its actual scope and outcome need an accountable record. An interrupted or unauthorized attempt is recorded truthfully rather than erased.
- **Scope boundaries:** One begun release attempt or actual event, with its targeted configuration, observed actions, endpoints, and resulting state. Deployment, verification, validation, and acceptance claims each require their actual evidence for the declared scope.

## Authoring inputs and unresolved facts

Inspect the release event and its actual times; the release identity and bounded audience, units, or environments; the exact artifact or item revisions and controlled locators; any baselines that actually exist; supplied project change and release criteria, including check conditions and completion endpoints; every required decision or standing delegation that applied to this configuration and scope; the integrity, verification, validation, security, and readiness evidence actually considered; the distribution channel and recipients; deployment actions only if performed; actual checks and failures; known defects, deviations, compatibility or migration limits; established project support, recovery, notification, and retention commitments; and any subsequent stop, recall, or supersession action.

If a version, recipient, event result, authority, or check is unknown, state what is unknown, its effect on the release claim, and the resolving action and actual owner if assigned. If authorization cannot be established, record the observed action as unauthorized or authorization-unconfirmed; do not call it an authorized release. At least one release action or attempt must have begun. Cite actual related project records by identity and locator. Never infer delivery from a package build, deployment from distribution, or acceptance from receipt.

## Finished-document contract

- **Title:** Identify the release or attempted release and call the document a release record.
- **Frontmatter:** None. Begin with the GFM title. Release identity and state are substantive body content.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Identify the event and exact configuration before reporting authority and checks; place the observed outcome after the actions. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Event and scope | Required | Identify one bounded release event or attempt, its actual period, release identity, accountable role, intended and actual recipients or target scope, and whether the record is in progress or retrospective. Distinguish distribution, installation, activation, and use. |
| Release target and configuration | Required | Identify each artifact or item targeted by the actual release action or attempt by stable identity, exact revision, controlled locator, and integrity or serial identifier appropriate to its form. State whether it was offered or transferred. Give baseline references only for real baselines that define part or all of the set. State material changes, compatibility limits, and known defects or deviations that apply. |
| Authority and eligibility | Required | State the supplied project release criteria and every required authorizing decision or standing delegation, with scope, effectivity, conditions, and evidence that those conditions were met; or say why authorization is unconfirmed or absent. Identify the build, integrity, technical, security, or readiness evidence actually examined and each required check that was not completed. Release permission requires an actual decision or delegation granting it for the configuration and scope. |
| Actions and observations | Required | Record actual publication, transfer, deployment, or activation actions and attempts in order, with actors, times or bounded sequence, destinations, checks, observations, failures, and evidence locators. Record preparatory packaging as context; packaging alone does not start a release event. For an action not performed, say so rather than describing it as completed. |
| Result, restrictions, and follow-up | Required | State the actual release state, what was published or reached whom, what remains unavailable or unverified, operating restrictions and open obligations. Record recovery, rollback, recall, support transfer, notification, retention, and supersession only when applicable; separate the planned route from any action actually taken. Name follow-up owners only when assigned. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Release event | One bounded release or attempted release. | At least one publication, transfer, deployment, or activation action or attempt must have begun. A build, packaging step, or proposed deployment alone is not a release event. Give the actual date or bounded period, without inventing timestamp precision. |
| Release scope | One intended scope and one observed scope. | Identify audiences, channels, environments, units, or sites that matter. Keep intended recipients separate from confirmed recipients. |
| Artifact or item | One or more exact items targeted by an actual release action or attempt. | Give identity, immutable revision or serial/effectivity, retrievable controlled locator, and whether each item was offered or transferred. A failed attempt may leave all items untransferred. For byte artifacts, record a digest and algorithm when available or required; a digest is not required for a physical item. Include a composition or inventory locator when an actual inventory covers the targeted items. |
| Baseline reference | Zero or more applicable controlled baselines. | Cite each real baseline's identity, revision, and the released items it covers. The exact release item list remains required even without a separate baseline record. |
| Authorization | Every project authorizing decision or standing grant required for the declared configuration and scope, or an explicit missing/unconfirmed state. | Identify the decision maker or delegating role, decision or delegation source, configuration, scope, time, and conditions, and show that a standing grant's conditions were met. The decision or grant must explicitly permit the recorded release action. Missing required authorization prevents an `authorized` claim. |
| Eligibility evidence | Zero or more actual evidence items, plus the status of applicable required checks. | Tie each examined item to the released configuration and criterion. State a required check as not performed or inconclusive when that is the fact. Do not claim successful verification or validation from a plan or expected evidence. |
| Release action | One or more actual actions in sequence. | Distinguish publication, delivery, deployment, activation, stop, recovery, and recall. Give actor and destination when known and a result or explicit uncertainty for each action. |
| Resulting state | One observed state: `in-progress`, `completed`, `partial`, `failed`, or `recalled`, or an explicitly unresolved state. | `Completed` means the declared release endpoint was reached, whether publication to a channel or delivery to named recipients, and applicable completion checks were met. It does not imply every audience member received or used a public release. `Partial` names missing endpoints, recipients, or steps. `Failed` names the failed attempt; `recalled` cites the actual withdrawal action. A successful retest does not remove an earlier failure. |
| Exception or restriction | Zero or more actual conditions after assessment. | Give affected items and recipients, the decision or evidence behind each exception, and operational effect. A known defect or residual risk is not silently accepted. |
| Recovery and retention | Conditional on an applicable recovery or preservation obligation. | State the feasible path and trigger; if recovery was executed, give its separate observation and result. Identify support and retention commitments only when established. Do not promise rollback where no safe reversal exists. |

Use an item table for multiple artifacts and an event log for actions and checks. Use prose for authorization limits and outcome. A diagram may clarify a staged rollout but cannot replace the item identities or event evidence. Do not insert a generic document-control block or empty artifact rows. Record actual authorizations with their evidence locators.

## Quality criteria

- The exact configuration, observed scope, and action sequence are traceable. A mutable branch name or package label alone does not identify released bytes.
- Every required authorization matches the configuration, recipient scope, conditions, and timing claimed. An unconfirmed grant remains visibly unconfirmed.
- Check results are observations tied to criteria and evidence. Skipped or failed checks remain visible, including after a later success.
- Distribution, deployment, receipt, support handoff, and acceptance are not conflated. 
- The stated outcome matches observed publication or delivery and checks. Open defects, restrictions, and recovery obligations remain actionable without fabricated closure.
