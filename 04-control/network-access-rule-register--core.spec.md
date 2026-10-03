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
- **Frontmatter:** None. Begin with the GFM title. The boundary and as-of point belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State the boundary and status meanings before the rules. State gaps with or after the rules. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Identity and scope | Required | Identify the enforcement boundary, the as-of point, the rule classes included, and the meaning of each status used. Include the client or receiving-party element from this contract. |
| Rules | Required | Record each rule with its identity, match, action, owner, intent, and status. If no rule is established, say so instead of adding a placeholder rule. |
| Gaps | Required | Identify missing owners, intents, or statuses, and any rule whose match is unresolved. State the next action. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
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
