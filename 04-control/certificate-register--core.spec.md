---
title: "Certificate register specification"
description: >-
  Defines the authoring contract for certificate registers tracking public-key or TLS certificate metadata across a bounded set of systems or services, including certificate identity, covered scope or subject names, responsible custodian, expiration date, installed locations, currency as-of point, and visibility of missing or unverified entries. Explicitly prohibits storing private keys, passphrases, or secret material inside the register so operators manage certificate renewals safely.
topics:
  - "control-records"
  - "security"
  - "operations"
  - "certificate-register"
  - "tls-certificates"
  - "certificate-expiry"
  - "custodian-tracking"
  - "pki-inventory"
use_when:
  - "A bounded set of services or hosts requires a controlled register of certificate identities, scopes, custodians, expiries, and locations."
  - "Operators need reliable visibility into upcoming certificate renewals and where each certificate is installed."
  - "A security reviewer is verifying that certificate metadata is tracked accurately without exposing private keys or secrets."
not_for:
  - "Storing private keys, secret tokens, or credential material, which belong strictly in approved secret managers."
  - "Tracking user accounts, system groups, and authorization privileges, which belongs in an identity and access register."
  - "Executing step-by-step certificate rotation commands, which belongs in an operational runbook."
---

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
- **Frontmatter:** Required. Begin with a YAML 1.2 Semantic-Discovery frontmatter block delimited by `---` lines containing `title`, `description` (60 to 140 neutral retrieval words), `topics` (3 to 12 concrete lowercase kebab-case terms), `use_when` (2 to 6 neutral task conditions), and conditional `not_for` (1 to 5 grounded exclusions, omitted when empty), followed by the GFM H1 title. Exclude internal IDs, version strings, hashes, filesystem paths, build metadata, and unresolved template delimiters from frontmatter values. The covered set and as-of point belong in the body. Governing source: Collection Semantic-Discovery Frontmatter contract.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. Omit it for internal documents unless a specific project policy requires explicit negative attestation. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Identify the covered set before the certificate entries. State gaps with or after the entries. Heading wording may vary.
- **Presentation:** Use compact registers, structured item tables, or grouped lists sized to the controlled inventory without placeholder rows. Required roles may share sections while keeping stable identities, owners, states, source locators, and reconciliation gaps directly retrievable.

| Projection | Title and metadata ownership | Syntax and source authority |
| --- | --- | --- |
| Certificate register (standalone) | Begin with the mandatory 5-key Semantic-Discovery YAML frontmatter followed by one scope-specific H1. Control scope, as-of point, state, ownership, and authority references remain body content, inheriting corpus-level changelog/VCS versioning, declared default maintainer, and external specification provenance when governed in a unified operational corpus. | Use GFM prose, tables, or structured lists bound to controlling masters and inspected snapshots. Referenced systems, trackers, or baselines remain authoritative for their native records; changes to controlling sources require reconciliation rather than silent overwrite. |

| Section role | Status and inclusion condition | Content obligation |
| --- | --- | --- |
| Identity and scope | Required | Identify the systems or services covered and the as-of point. Include the client or receiving-party element from this contract when applicable. |
| Certificates | Required | For each certificate, record its identity, scope, custodian, expiry, and installed location when those facts are known. If none are in scope, say so instead of adding a placeholder certificate. |
| Gaps | Required | Identify missing custodians, expiry, scope, or installed locations, and the next action. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
| --- | --- | --- |
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
