---
title: "Network access rule register specification"
description: >-
  Defines the authoring contract for network access rule registers recording active, proposed, disabled, or superseded ACL, firewall, and security-zone enforcement rules within a stated network enforcement boundary. Covers boundary identity and currency, individual rule specifications, accountable rule owners, stated operational or security intent, current enforcement status, and visibility of undocumented or orphaned rules while excluding secret values, credentials, and live verification test results.
topics:
  - "control-records"
  - "networking-and-infrastructure"
  - "security"
  - "network-access-rules"
  - "firewall-register"
  - "acl-rules"
  - "zone-policies"
  - "rule-ownership"
use_when:
  - "A bounded network enforcement perimeter requires a controlled register of firewall, ACL, or zone rules with owners and intent."
  - "Network or security reviewers need to determine which traffic rules are proposed, active, disabled, or superseded and why each exists."
  - "An operator is surfacing unowned, ambiguous, or legacy access rules for cleanup."
not_for:
  - "Designing overall network topology, segmentation architecture, and routing, which belongs in a network design description."
  - "Tracking live IP prefixes, VLAN identifiers, and DNS names, which belongs in a network allocation register."
  - "Recording firewall penetration-test or rule-verification outcomes, which belongs in a verification evidence record."
---

# Network access rule register specification

## Identity and selection

- **Specification ID:** `NETWORK-ACCESS-RULE-REGISTER@core`.
- **Purpose:** Record ACL, firewall, or zone rules with owner, intent, and status.
- **Intended readers:** Rule owners, network and security engineers, and reviewers who must see which access rule is in force and why it exists.
- **Decision or action supported:** Determine the rule base now recorded, who owns each rule, what it is for, and whether it is proposed, in force, disabled, or superseded.
- **Use when:** ACL, firewall, or zone rules for a bounded network need a controlled rule base with owner, intent, and status.
- **Scope boundaries:** Include ACL, firewall, and zone rules within the stated enforcement boundary. Exclude secret values and test results.

## Authoring inputs and unresolved facts

Obtain the boundary the rules cover, the as-of point, and each rule's identity, match, action, owner, intent, and status as actually established. Obtain any established design intent or implementation context cited by a rule, including the actual record identity and locator.

If an owner, intent, match, or status is unknown, record the gap. Do not invent a rule, an owner, or a status. A rule entry requires an established rule identity; an `in force` status requires evidence that the rule is active at the stated enforcement boundary. This register has no secret-value field. Do not record a password, shared secret, key, token, or other secret value. A status is an administrative state of the rule. It is not `pass`, `fail`, `inconclusive`, or `not-run`.

## Finished-document contract

- **Title:** Identify the network or enforcement boundary and name the document as its network access rule register.
- **Frontmatter:** Required. Begin with a YAML 1.2 Semantic-Discovery frontmatter block delimited by `---` lines containing `title`, `description` (60 to 140 neutral retrieval words), `topics` (3 to 12 concrete lowercase kebab-case terms), `use_when` (2 to 6 neutral task conditions), and conditional `not_for` (1 to 5 grounded exclusions, omitted when empty), followed by the GFM H1 title. Exclude internal IDs, version strings, hashes, filesystem paths, build metadata, and unresolved template delimiters from frontmatter values. The boundary and as-of point belong in the body. Governing source: Collection Semantic-Discovery Frontmatter contract.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. Omit it for internal documents unless a specific project policy requires explicit negative attestation. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State the boundary and status meanings before the rules. State gaps with or after the rules. Heading wording may vary.
- **Presentation:** Use compact registers, structured item tables, or grouped lists sized to the controlled inventory without placeholder rows. Required roles may share sections while keeping stable identities, owners, states, source locators, and reconciliation gaps directly retrievable.

| Projection | Title and metadata ownership | Syntax and source authority |
| --- | --- | --- |
| Network access rule register (standalone) | Begin with the mandatory 5-key Semantic-Discovery YAML frontmatter followed by one scope-specific H1. Control scope, as-of point, state, ownership, and authority references remain body content, inheriting corpus-level changelog/VCS versioning, declared default maintainer, and external specification provenance when governed in a unified operational corpus. | Use GFM prose, tables, or structured lists bound to controlling masters and inspected snapshots. Referenced systems, trackers, or baselines remain authoritative for their native records; changes to controlling sources require reconciliation rather than silent overwrite. |

| Section role | Status and inclusion condition | Content obligation |
| --- | --- | --- |
| Identity and scope | Required | Identify the enforcement boundary, the as-of point, the rule classes included, and the meaning of each status used. Include the client or receiving-party element from this contract when applicable. |
| Rules | Required | Record each rule with its identity, match, action, owner, intent, and status. If no rule is established, say so instead of adding a placeholder rule. |
| Gaps | Required | Identify missing owners, intents, or statuses, and any rule whose match is unresolved. State the next action. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
| --- | --- | --- |
| Enforcement boundary | One bounded set of ACL, firewall, or zone enforcement per register. | State where the rules apply. Do not mix an unrelated boundary into the same status meanings without saying so. |
| Rule | Zero or more rules. | Give each rule a stable identity, the match, and the action. Do not invent a match. |
| Owner | One owner for each rule that has one. | The owner is accountable for the rule. An unknown owner stays unknown. |
| Intent | The reason the rule exists, when established. | State the intent in operational language. Record a segmentation objective only when it is an established reason for this rule. |
| Status | One administrative status per rule, or an explicit gap. | Use the register's stated meanings, such as proposed, in force, disabled, or superseded. Status is not a test result. Do not record a password, shared secret, key, token, or other secret value. Name a separate store only when the project already has one, without copying its contents. |

Use a rule table with identity, match, action, owner, intent, and status. Prose should explain a status meaning or a gap. Do not include a blank rule row, and do not add a column for a secret value.

## Quality criteria

- Each rule has an identity, a match or an explicit gap, an action, an owner or an explicit gap, an intent or an explicit gap, and a status or an explicit gap.
- Each `in force` status is supported by the rule's established activation at the stated enforcement boundary.
- Status is administrative. The register assigns no `pass`, `fail`, `inconclusive`, or `not-run`.
- The register contains no secret value and no field whose content is a secret value.
- The register invents no rule, owner, or party.
