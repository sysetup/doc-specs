# Error handling specification

## Identity and selection

- **Specification ID:** `ERROR-HANDLING-SPECIFICATION@core`.
- **Purpose:** Define required detection, propagation, response, recovery, and observable behavior for technical faults in a bounded system or software scope.
- **Intended readers:** Implementers, interface owners, operators, security and safety reviewers, testers, and maintainers.
- **Decision or action supported:** Implement consistent fault behavior, coordinate what callers and operators can expect, and assess whether failure responses meet the project's stated reliability, security, safety, and interface obligations.
- **Use when:** Error conditions or failure classes need explicit behavioral contracts across components, interfaces, or user and operator boundaries.
- **Scope boundaries:** Cover technical failure conditions and required behavior at affected boundaries, including permitted recovery actions and their limits within the stated system or software scope.

## Authoring inputs and unresolved facts

Obtain the system or software boundary, modes, state and trust boundaries, actual failure sources and dependencies, supplied project reliability, security, safety, and interface obligations, existing error codes or schemas, and the audiences that receive fault information. Inspect supplied interface definitions, operating constraints, recovery authorization, state consistency requirements, and intended verification conditions. Determine which failures are recoverable, which are transient, which can be retried safely, and which require degradation, isolation, escalation, or termination. If a controlled project error definition supplies shared codes or behavior, identify its edition, covered conditions, and relationship to the behavior specified here.

If a failure condition, severity, detection threshold, ownership, outward behavior, recovery rule, or assessment criterion is unknown, state the gap, its consequence, the resolving action, and the actual owner if assigned. Label unapproved behavior as proposed. Do not invent a code, latency target, required retry count, verification result, or fault occurrence. State each condition's required behavior and identify any supplied controlled definition that provides its shared codes or semantics, including the edition and covered scope. Direct detection or external propagation may be inapplicable to a particular condition, but the document must still say how that condition is recognized and what an affected actor sees or does when relevant.

## Finished-document contract

- **Title:** Identify the bounded product or service and document as its error handling specification; include an applicable edition or configuration when needed.
- **Frontmatter:** None. Begin with the GFM title. Error semantics, applicability, and decisions are body content.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Establish scope, boundaries, and shared classification before individual fault contracts; place assessment and compatibility rules after the behavior they cover. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Scope and failure model | Required | Identify affected components, interfaces, users or operators, operating modes, and trust or safety boundaries. Define the relevant error classes, severity or priority meanings where used, transient versus persistent distinctions, and who owns detection and response. Limit the failure model to technical faults within the stated operating boundary. |
| Fault behavior contracts | Required | Give one distinguishable contract per material failure condition or class: trigger and detection, classification, affected state, behavior at each relevant boundary, safe or constrained response, recovery or unrecoverable disposition, observability, and user or operator action where applicable. Common rules may be stated once with explicit applicability and per-condition exceptions. |
| Assessment basis | Required | Identify the expected observable outcomes and conditions for checking detection, response timing, propagated information, state integrity, negative cases, and recovery. State a method directly or refer to a real procedure when one exists. Identify any cited actual observation by its record and assessed configuration. Record an intended check without assigning `pass`, `fail`, `inconclusive`, or `not-run` to it. |
| Compatibility and change | Conditional: include when error codes, schemas, messages, or behavior are exposed to other components or users | State the applicable contract edition, consumer expectations, allowed or excluded combinations, and how changes are coordinated with affected interface owners. When more than one edition is in use, state the migration effects. Identify each separately controlled exposed parameter by its definition, edition, and locator, maintaining one controlling definition for that parameter. |
| Open decisions and limits | Required | Identify unresolved error behavior, unsupported failure cases, operational limits, and the actual decision or resolution route. If the known scope has no unresolved fault decision, say so; do not invent an open item. State the risk of relying on a proposed or unverified contract. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Failure condition or class | One or more distinct technical fault contracts within the defined scope. | Give each a stable local or project identifier, triggering condition, relevant mode and actor, and classification. Keep that identifier for the same triggering condition. Do not reuse it for a different condition. Group equivalent causes only when their outward behavior and recovery obligations genuinely match. |
| Detection | One recognition rule per contract. | Identify the observer, signal or condition, threshold, confidence or latency where these affect the required behavior. When the fault cannot be detected directly, state the proxy, timeout, or externally reported condition instead of implying certain detection. |
| Propagation and disclosure | One outward rule per affected boundary; internal-only handling may have no external propagation. | State the recipient, status or error code and message semantics when applicable, causal context needed for diagnosis, and information that must be withheld across trust boundaries. Identify any separately controlled code, schema, or parameter by its definition and edition. State the value or semantics here when this contract controls that parameter. |
| Immediate response | One defined response per contract, with branches for materially different modes or severity. | State what work stops or continues, what state or resources are protected, what happens to partial results, and any safe fallback or degradation. Retries, backoff, timeout budgets, and idempotence rules are required only where retry is permitted; retries MUST be bounded and their effects on state made explicit. |
| Recovery and terminal outcome | One recoverability decision per contract. | State restart, rollback, reconciliation, escalation, or operator intervention conditions when applicable; state the terminal behavior for an unrecoverable condition. Do not promise restoration when no mechanism or authority exists. |
| Observability and actor guidance | One account of what must be recorded or surfaced for each contract; user or operator instructions when the actor must respond. | State meaningful logs, metrics, alerts, correlation, retention or redaction constraints where applicable. Keep diagnostic detail appropriate to its audience; do not expose secrets or sensitive internal context through messages or logs. |
| Project basis and assessment | Each contract has a supplied project requirement, interface decision, or explained derivation and at least one assessable expected outcome. | Identify the project basis and its edition or locator when one exists. Explain any derivation from the supplied needs, allocations, or decisions. State the expected observation and check conditions, linking any cited method or actual observation to its relevant configuration. |

Use a table with meaningful condition, detector, outward effect, response, recovery, and check columns for compact contracts. Use per-condition subsections, state diagrams, or decision flows when branches, partial state, or cross-component propagation would be ambiguous in a table. A diagram MUST NOT be the only statement of externally observable error behavior. Give concrete code or schema formats only when they are part of the actual contract.

## Quality criteria

- Material fault classes have distinguishable triggering conditions, responsible detectors, outward results, and terminal or recovery behavior; no essential branch depends on a reader guessing the intended action.
- Retry, fallback, and recovery rules are bounded and consistent with state integrity, idempotence, trust boundaries, and stated project safety or security constraints.
- Users, callers, and operators receive the information and action needed for their roles without disclosing protected internal detail.
- Exposed errors agree with real interface and version decisions. Each separately controlled code or protocol has an identified definition and edition; any change to it is explicit and coordinated with its owner.
- Specified and proposed behavior are identified accurately. Any cited fault occurrence or observation is tied to its actual record and configuration; expected outcomes remain prospective.
