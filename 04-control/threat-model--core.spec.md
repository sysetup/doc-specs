---
title: "Threat model specification"
description: >-
  Defines the authoring contract for threat models maintaining a living adversarial security analysis of a bounded system, service, or feature configuration. Covers scope, modeled baseline, and declared threat-identification and prioritization methodologies, system decomposition across assets, actors, attack surfaces, data flows, and trust boundaries, explicit adversarial assumptions, enumerated threat scenarios without actionable exploit instructions, mapped existing versus planned mitigations, verification status, projected versus observed residual threat exposure kept separate from formal risk acceptance, coverage gaps, and architectural reassessment triggers.
topics:
  - "control-records"
  - "security"
  - "risk-and-safety"
  - "threat-model"
  - "trust-boundaries"
  - "attack-surface"
  - "security-mitigations"
  - "adversarial-analysis"
use_when:
  - "A system, service, architecture, or material feature change requires structured adversarial threat identification across assets, data flows, and trust boundaries."
  - "A security engineer or architect is enumerating threat scenarios, mapping existing versus planned mitigations, tracking verification, and exposing residual security exposure."
  - "A reviewer or authorizing authority is auditing threat coverage, architectural assumptions, and open residual-risk decisions before release or baseline change."
not_for:
  - "Planning lifecycle security engineering activities, schedules, supplier duties, and assessment programs, which belongs in a security engineering plan."
  - "Analyzing accidental non-adversarial component failure modes and reliability criticality, which belongs in failure modes and effects analysis."
  - "Tracking safety-critical physical or system mishap hazards across a lifecycle, which belongs in a hazard log."
  - "Evaluating personal-data processing lawfulness, proportionality, and data-subject rights safeguards, which belongs in a data protection impact assessment."
  - "Tracking one discovered concrete software vulnerability case through patching and closure, which belongs in a vulnerability record."
---

# Threat model specification

## Identity and selection

- **Specification ID:** `THREAT-MODEL@core`.
- **Purpose:** Maintain a living adversarial security analysis of a bounded system, service, or feature—mapping assets, attack surfaces, data flows, and trust boundaries to enumerated threat scenarios, mitigations, verification status, residual exposure, and reassessment triggers.
- **Intended readers:** Security engineers, system and software architects, developers, operators, assurance reviewers, and authorities making risk-acceptance or release decisions.
- **Decision or action supported:** Identify credible adversarial threats across trust boundaries, prioritize security controls before or during change, track mitigation implementation and verification, expose unaccepted residual security exposure, and trigger reassessment when architecture changes.
- **Use when:** A new system, architecture revision, trust-boundary change, high-risk feature, or periodic security review requires systematic adversarial threat analysis and ongoing mitigation control.
- **Scope boundaries:** Control adversarial threat identification, decomposition, mitigation tracking, and residual-exposure visibility for one bounded system or feature configuration; exclude lifecycle security program planning, accidental failure-mode analysis, individual discovered vulnerability cases, actionable exploit instructions, and unauthorized risk acceptance.

## Authoring inputs and unresolved facts

Obtain the bounded system, service, or feature scope, exact architecture or configuration baseline (or proposed design edition), exclusions, as-of point, and accountable owner; the declared threat-identification methodology (such as STRIDE, attack trees, PASTA, or a project-defined taxonomy) and prioritization or severity rating method and scales; controlling architecture descriptions, interface specifications, data-flow diagrams, or external threat-modeling tool files by edition and locator; protected assets (data, secrets, compute, availability, integrity, auditability), external and internal actors with privilege levels, entry and exit points, data flows, data stores, and explicit trust boundaries; threat-actor classes, assumed capabilities, access preconditions, and explicit security assumptions; enumerated threat scenarios, affected components or boundaries, abuse vectors, and security impacts; existing implemented controls versus planned or proposed mitigations, assigned owners, implementation states, and actual verification evidence; residual-exposure assessments, any actual authorized residual-risk acceptance decisions with authority and scope, and architectural or operational reassessment triggers.

If an architecture boundary, data flow, authentication mechanism, threat-prioritization scale, mitigation owner, verification result, or risk-acceptance authority is unknown or not established, record that gap explicitly with its security consequence, resolving action, and actual owner only when assigned. Do not invent topology, threat ratings from an undefined scale, implemented controls, verification passes, or residual-risk acceptance. Omit actionable exploit payloads, live credentials, or operational attack procedures. An unexamined component or trust boundary stays visibly unanalyzed and cannot be represented as threat-free. Treat completion of the threat model, a `low` rating, or a `mitigate` plan as distinct from verified risk reduction or authorized residual-risk acceptance.

## Finished-document contract

- **Title:** Name the modeled system, service, or feature and its covered baseline or edition and identify the document as its threat model.
- **Frontmatter:** Required. Begin with a YAML 1.2 Semantic-Discovery frontmatter block delimited by `---` lines containing `title`, `description` (60 to 140 neutral retrieval words), `topics` (3 to 12 concrete lowercase kebab-case terms), `use_when` (2 to 6 neutral task conditions), and conditional `not_for` (1 to 5 grounded exclusions, omitted when empty), followed by the GFM H1 title. Exclude internal IDs, version strings, hashes, filesystem paths, build metadata, and unresolved template delimiters from frontmatter values. Modeled baseline, methodology, threat states, and risk-acceptance citations belong in the body. Governing source: Collection Semantic-Discovery Frontmatter contract.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. Omit it for internal documents unless a specific project policy requires explicit negative attestation. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Establish scope, baseline, and methodology before system decomposition and trust boundaries; state adversarial assumptions before threat scenarios; place mitigations, verification, and residual exposure after threat scenarios, followed by coverage limits and reassessment triggers. Heading wording may vary.
- **Presentation:** Use structured asset, trust-boundary, and threat-to-mitigation tables paired with concise architecture or data-flow diagrams sized to the system's attack surface without placeholder rows. Required roles may share sections while keeping trust boundaries, existing versus planned mitigations, verification evidence, residual exposure, and open gaps directly retrievable.

| Projection | Title and metadata ownership | Syntax and source authority |
| --- | --- | --- |
| Threat model (standalone) | Begin with the mandatory 5-key Semantic-Discovery YAML frontmatter followed by one system-specific H1. Modeled baseline, as-of point, methodology, ownership, and risk-acceptance references remain body content, inheriting corpus-level changelog/VCS versioning, declared default maintainer, and external specification provenance when governed in a unified operational corpus. | Use GFM prose, diagrams, and threat registers bound to inspected architecture baselines, interface definitions, and verification records. Referenced external threat-modeling tool files or architecture diagrams remain authoritative for their native models when declared as masters; baseline, interface, or exposure changes require reassessment rather than silent carryover. |

| Section role | Status and inclusion condition | Content obligation |
| --- | --- | --- |
| Scope, configuration baseline, and methodology | Required | Identify the bounded system, service, or feature, exact modeled baseline or proposed design edition, exclusions, as-of point, accountable owner, and client or receiving-party element when applicable. Declare the threat-identification methodology (such as STRIDE, attack trees, or a project-defined approach) and the prioritization or severity rating scales and rules, or mark the rating method unresolved without inventing scores. Identify any external threat-modeling artifact and its edition if maintained as a companion or master. |
| System decomposition, assets, and trust boundaries | Required | Enumerate protected assets, actors and privilege levels, entry and exit points (attack surfaces), processes, data stores, data flows, and explicit trust boundaries where control, authentication, privilege, or network domain changes. Reference controlling architecture descriptions or interface specifications by edition and locator without exposing credentials or fabricating unverified topology. |
| Adversarial assumptions and threat actors | Required | Define in-scope threat-actor classes, assumed capabilities, and access preconditions alongside explicit security assumptions (such as trusted host layers, managed identity boundaries, or excluded physical access) whose violation invalidates dependent threat conclusions. |
| Threat scenarios and impact analysis | Required | Record each identified threat with a stable identifier, affected asset, component, or trust boundary, threat actor and precondition, analytical abuse path or attack vector (without operational exploit payloads), security impact (confidentiality, integrity, availability, authenticity, or accountability), current priority under the declared scale or unresolved state, and evidential or architectural basis. After real analysis of a scope with no credible threat in a category, state the assessed basis rather than adding placeholder rows. |
| Mitigations, verification, and residual exposure | Required | For each threat, map existing implemented controls separately from planned or proposed mitigations, naming accountable owners, implementation state (`not-started`, `planned`, `implemented`, `verified`, or `not-mitigated`), and actual verification citations when verified. State treatment disposition (`mitigate`, `avoid`, `transfer`, or `accept-proposed`) and residual exposure, labeling forecast residual exposure separately from observed post-verification reassessment. Cite actual residual-risk acceptance only when an authorized decision maker recorded it with scope and conditions. |
| Coverage limits, open gaps, and reassessment triggers | Required | Summarize unanalyzed components, unverified assumptions, unresolved threats blocking release or authorization, latest actual review (if one occurred), and concrete triggers—such as architecture, trust-boundary, authentication, dependency, or exposure changes, or security incidents—that require updating the threat model. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
| --- | --- | --- |
| Modeled baseline and method | Exactly one bounded system configuration edition, threat-identification methodology, and rating scale (or explicit unresolved rating scale) in Scope, configuration baseline, and methodology. | Conclusions apply strictly to the stated baseline edition; missing rating scales block numeric or ranked priority claims. |
| Protected asset | One or more tangible or logical assets requiring protection in System decomposition, assets, and trust boundaries. | Identify data, secrets, functions, or service properties at risk and their security objectives (confidentiality, integrity, availability, authenticity, accountability). |
| Trust boundary and attack surface | One or more explicit trust boundaries and entry or exit points in System decomposition, assets, and trust boundaries. | Mark where privilege, tenant isolation, authentication, or network trust changes; every external or cross-privilege data flow crosses a named boundary. |
| Threat actor and assumption | One or more modeled actor profiles and explicit security assumptions in Adversarial assumptions and threat actors. | State actor capability and access preconditions; mark unverified assumptions explicitly because their failure reopens threat exposure. |
| Threat scenario | One per identified credible adversarial threat (or an assessed-empty basis per examined boundary) in Threat scenarios and impact analysis. | Assign one stable ID; connect actor, precondition, trust boundary, abuse vector, and asset impact analytically without weaponized exploit instructions or secrets. |
| Mitigation disposition | One control-mapping and treatment account per threat scenario in Mitigations, verification, and residual exposure. | Use `not-started`, `planned`, `implemented`, `verified`, or `not-mitigated` for control state; `verified` requires actual test, audit, or review evidence bound to the assessed configuration. Planned controls cannot be credited as implemented. |
| Residual threat exposure | One post-mitigation exposure statement per active threat scenario in Mitigations, verification, and residual exposure. | Separate design forecast from observed post-verification reassessment; omit post-mitigation reduction claims when no control is implemented. |
| Risk-acceptance citation | Zero until an authorized decision exists; one citation per formally accepted residual threat in Mitigations, verification, and residual exposure. | Identify the authorized decision maker, recorded scope, conditions, expiry or review trigger, and decision record locator. A `low` rating, `accept-proposed` label, or document review is not acceptance. |
| Reassessment trigger | One or more concrete invalidation triggers in Coverage limits, open gaps, and reassessment triggers. | Include architecture, trust-boundary, authentication, third-party dependency, or threat-landscape changes and relevant security incidents, naming who initiates reassessment. |

Use a data-flow or trust-boundary diagram when component interactions and privilege transitions would otherwise be unclear, paired with structured tables for protected assets and threat-to-mitigation tracking (ID, boundary, scenario, impact, priority, controls, state, verification, residual exposure, disposition). Keep detailed lifecycle security schedules in security engineering plans, per-control compliance catalogs in control implementation records, and discovered product vulnerabilities in vulnerability records. Do not embed credentials, operational exploit code, or blank threat rows.

## Quality criteria

- Scope, modeled baseline edition, threat-identification methodology, and prioritization scales bound every threat scenario; missing scales leave priorities unresolved.
- System decomposition makes assets, actors, entry points, data flows, and trust boundaries explicit enough to trace every threat to a concrete boundary or component.
- Threat actors, preconditions, and security assumptions remain visible so reviewers can evaluate what happens if an assumption fails.
- Every threat scenario states its analytical abuse vector and security impact without actionable exploit payloads or secrets; assessed-empty boundaries state their basis explicitly.
- Existing implemented controls, planned mitigations, observed verification evidence, projected residual exposure, observed reassessment, and authorized residual-risk acceptance remain strictly distinguishable.
- Unanalyzed components, blocking unresolved threats, review history, and concrete architectural reassessment triggers remain visible and traceable.
