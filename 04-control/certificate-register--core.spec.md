# Certificate register specification

## Identity and selection

- **Specification ID:** `CERTIFICATE-REGISTER@core`.
- **Purpose:** Record certificate identity, scope, custodian, expiry, and installed location.
- **Intended readers:** Certificate custodians and the operators who must know where a certificate is installed and when it expires.
- **Decision or action supported:** Determine which certificate is in scope, who keeps it, when it expires, and where it is installed.
- **Use when:** Certificates for a bounded set of systems or services need a controlled register of identity, scope, custodian, expiry, and installed location.
- **Scope boundaries:** Cover certificate metadata and installed locations within the declared system or service set. Exclude private keys and other secret values.

## Authoring inputs and unresolved facts

Obtain the set of systems or services the register covers, the as-of point, and each certificate's subject or other identity, issuer, serial or equivalent identifier, scope, custodian, not-before and not-after times, and installed location, as those facts are actually known.

If identity, scope, custodian, expiry, or installed location is unknown, record the gap. Do not invent a certificate, a custodian, a date, or a location. This register has no secret-value field. Do not record a private key, a passphrase, a key file's contents, or any other secret. A fingerprint of the certificate MAY identify the certificate. It is not a private key and MUST NOT be accompanied by key material. An account that uses a certificate may be named as a usage relationship attached to that certificate's entry.

## Finished-document contract

- **Title:** Identify the system or service set and name the document as its certificate register.
- **Frontmatter:** None. Begin with the GFM title. The covered set and as-of point belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Identify the covered set before the certificate entries. State gaps with or after the entries. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Identity and scope | Required | Identify the systems or services covered and the as-of point. Include the client or receiving-party element from this contract. |
| Certificates | Required | For each certificate, record its identity, scope, custodian, expiry, and installed location when those facts are known. If none are in scope, say so instead of adding a placeholder certificate. |
| Gaps | Required | Identify missing custodians, expiry, scope, or installed locations, and the next action. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Covered set | One bounded set of systems or services per register. | State the as-of point. Do not silently add certificates from outside that set. |
| Certificate identity | One identity per certificate entry. | State subject or equivalent name, issuer, and serial or another established identifier. A certificate fingerprint MAY be included. Do not record a private key. |
| Scope | The names, hosts, or uses the certificate is for, when known. | State the scope. An unknown name or use stays a gap. |
| Custodian | One custodian when one is assigned. | The custodian keeps the certificate. An unassigned custodian stays unassigned. Do not invent a person or party. |
| Expiry | The not-after time, and the not-before time when it matters. | Use the dates from the certificate or from an established record. Do not invent an expiry. |
| Installed location | Each known place the certificate is installed. | State the host, service, or store location. The location is not the contents of a key file. Do not record a private key, passphrase, key-file contents, or other secret, and do not add a column for key material. |

Use a register table with identity, scope, custodian, expiry, and installed location. Prose should explain a gap. Do not include a blank certificate row or a private-key column.

## Quality criteria

- Each entry is a certificate, with its known identity, scope, custodian, expiry, and installed location.
- An account association identifies certificate use and preserves the certificate's identity.
- The register contains no private key and no other secret value, and it has no field whose content is a secret value.
- Unknown custodians, dates, and locations stay visible. The register invents no certificate, date, location, or party.
