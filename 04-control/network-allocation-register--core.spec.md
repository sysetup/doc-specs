---
title: "Network allocation register specification"
description: >-
  Defines the authoring contract for network allocation registers stating current in-force assignments of IP prefixes, VLAN identifiers, network names, and accountable owners across a defined allocation domain at an explicit as-of point. Explicitly separates live assignments in force from unassigned design proposals, highlights plan conflicts and allocation gaps, and excludes physical cabling connections, firewall traffic rules, raw equipment discovery scans, and configuration-execution logs.
topics:
  - "network-allocation"
  - "IP-prefix-register"
  - "VLAN-assignments"
  - "network-naming"
  - "address-management"
  - "network-operations"
use_when:
  - "Network operators need an authoritative statement of IP prefixes, VLAN IDs, names, and owners currently assigned in force."
  - "An engineer is detecting allocation conflicts between live network assignments and intended network design plans."
  - "A team is tracking network address space cleanly without mixing unassigned proposals into active allocation rows."
not_for:
  - "Designing future network topology, routing architecture, and planned addressing, which belongs in a network design description."
  - "Mapping physical cables, patch panels, and switch ports, which belongs in a cabling schedule."
  - "Tracking firewall or ACL traffic permissions, which belongs in a network access rule register."
---

# Network allocation register specification

## Identity and selection

- **Specification ID:** `NETWORK-ALLOCATION-REGISTER@core`.
- **Specification edition:** `1.0`.
- **Purpose:** State the current assignment of prefixes, VLAN identifiers, names, and owners.
- **Intended readers:** Network operators and the owners of assigned prefixes, VLAN identifiers, and names, who must use the assignment now in force.
- **Decision or action supported:** Determine which prefix, VLAN identifier, or name is assigned now, to whom, and which intended design value is not the assignment in force.
- **Use when:** A network's prefixes, VLAN identifiers, names, and owners need a controlled statement of the assignment now in force.
- **Scope boundaries:** Record assignments currently in force; keep unassigned proposals out of assignment rows. Exclude physical cable connections, traffic-permission rules, equipment observations, and configuration-execution results.

## Authoring inputs and unresolved facts

Obtain the network or allocation domain, the as-of point, and each assignment that is actually in force: prefix, VLAN identifier, name, and owner, as applicable. Obtain established intended values when available so conflicts with assignments in force can be stated.

If an assignment, owner, or identifier is unknown, record the gap. Do not invent a prefix, VLAN identifier, name, or owner. If a class has no assignment in force, say that the class has none. Do not present an intended value as an assignment now in force. Where the plan and the assignment differ, state the assignment in force and identify the conflict.

## Finished-document contract

- **Title:** Identify the network or allocation domain and name the document as its network allocation register.
- **Frontmatter:** Required. Begin with a YAML 1.2 Semantic-Discovery frontmatter block delimited by `---` lines containing `title`, `description` (60 to 140 neutral retrieval words), `topics` (3 to 12 concrete terms), `use_when` (2 to 6 neutral task conditions), and conditional `not_for` (1 to 5 grounded exclusions, omitted when empty), followed by the GFM H1 title. Exclude internal IDs, version strings, hashes, filesystem paths, build metadata, and unresolved template delimiters from frontmatter values (Rule 13). The domain and as-of point belong in the body. Governing source: Collection Semantic-Discovery Frontmatter contract (standard 3.0.0).
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. Omit it for internal documents unless a specific project policy requires explicit negative attestation. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State the domain and as-of point before the assignments. State conflicts and gaps after or with the assignments. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
| --- | --- | --- |
| Identity and scope | Required | Identify the network or allocation domain, the as-of point, the classes covered, and any class that has no assignment in force. Include the client or receiving-party element from this contract when applicable. |
| Assignments in force | Required | Record each prefix, VLAN identifier, and name that is assigned now, with its owner. If a covered class has no assignment, say so instead of adding a placeholder row. |
| Conflicts and gaps | Required | Identify any difference from the intended plan, any unknown owner or identifier, and the next action. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
| --- | --- | --- |
| Allocation domain | One bounded network or naming domain per register. | State the as-of point. An entry outside that domain does not belong here. |
| Prefix assignment | Zero or more prefixes in force. | State the prefix, its use, and its owner. An intended prefix that is not assigned is a conflict or a gap, not an assignment. |
| VLAN identifier assignment | Zero or more identifiers in force. | State the identifier, the name used with it, and the owner. Do not invent an identifier to match a design name. |
| Name assignment | Zero or more names in force. | State the name, what it denotes, and the owner. A design name pattern is not a current assignment. |
| Owner | One accountable owner for each assignment that has one. | If the owner is unassigned, mark the gap. Do not invent an owner. |
| Plan conflict | Zero or more differences between this register and the intended plan. | State both the assignment in force and the intended value. Do not silently replace either. |

Use a register table with the assignment, its class, its owner, and its state. Prose should explain a conflict that the table cannot make plain. Do not include a blank assignment row.

## Quality criteria

- Every row is an assignment now in force, or the register states that a covered class has none.
- The intended plan remains distinguishable from the assignment in force.
- Unknown owners and identifiers stay visible. The register invents no prefix, VLAN identifier, name, owner, or party.
