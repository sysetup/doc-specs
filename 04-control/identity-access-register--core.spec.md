# Identity and access register specification

## Identity and selection

- **Specification ID:** `IDENTITY-ACCESS-REGISTER@core`.
- **Purpose:** Record accounts, groups, and privileges for one directory or host set.
- **Intended readers:** The directory or host-set owner, account administrators, and reviewers who must see who holds which privilege.
- **Decision or action supported:** Determine which accounts and groups exist in the stated directory or host set, and which privileges they hold.
- **Use when:** One directory or host set needs a controlled record of its accounts, groups, and privileges.
- **Scope boundaries:** Cover account identities, group memberships, and assigned privileges. Equipment and certificate artifacts are excluded from account entries. Secret values are excluded from the register.

## Authoring inputs and unresolved facts

Obtain the directory or host set, the as-of point, and the accounts, groups, and privileges that actually exist there. Identify the owner of the directory or host set when one is assigned.

If an account, group, membership, or privilege is unknown, record the gap. Do not invent an account, a group, or a privilege. Do not enter equipment as an account. This register has no secret-value field. Do not record a password, passphrase, key, token, recovery code, secret hash, or other secret value. A recorded privilege identifies an authorization held by an account or group; it is not proof that the privilege was exercised.

## Finished-document contract

- **Title:** Identify the directory or host set and name the document as its identity and access register.
- **Frontmatter:** None. Begin with the GFM title. The directory or host set and the as-of point belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Identify the directory or host set before accounts, groups, and privileges. State gaps with or after those entries. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Identity and scope | Required | Identify the one directory or host set, the as-of point, and the owner of that set when assigned. Include the client or receiving-party element from this contract. Limit account entries to identities in that set, excluding equipment and certificate artifacts. |
| Accounts, groups, and privileges | Required | Record each account and group in scope, the membership that is known, and the privileges held. If none are established, say so instead of adding a placeholder account. |
| Gaps | Required | Identify unknown memberships, unknown privileges, and unassigned owners. State the next action. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Directory or host set | One directory or one defined host set per register. | Do not mix a second directory into the same register without making a separate register. |
| Account | Zero or more accounts in that set. | Give the account identifier and its status, such as active or disabled, when the status is known. Include only account identities, excluding equipment and certificate artifacts. |
| Group | Zero or more groups in that set. | Give the group identifier and the known members. An unknown membership stays a gap. |
| Privilege | Zero or more privileges held by an account or group. | State the privilege and who holds it. Do not treat the privilege as evidence that it was used. Do not record a password, passphrase, key, token, recovery code, secret hash, or other secret value, and do not add a credential column. |
| Owner | The owner of the directory or host set, and an owner for an account only when one is actually assigned. | An unassigned owner stays unassigned. Do not invent a person or party. |

Use tables for accounts, groups, and privileges when several must be compared. Prose should state the directory or host set and the meaning of a privilege. Do not include a blank account row or a secret-value column.

## Quality criteria

- The register covers one directory or host set and separates accounts, groups, and privileges.
- Account entries identify accounts in the stated directory or host set; equipment and certificate artifacts are excluded.
- The register contains no secret value and no field whose content is a secret value.
- Unknown memberships and privileges stay visible. The register invents no account, group, privilege, or party.
- A recorded privilege is not evidence that it was exercised.
