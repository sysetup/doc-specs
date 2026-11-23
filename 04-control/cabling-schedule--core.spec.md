---
title: "Cabling schedule specification"
description: >-
  Defines the authoring contract for physical cabling schedules identifying every cable, patch panel, port assignment, and connected endpoints across a bounded network or facility cabling plant. Requires explicit distinction between planned and as-built row states, plant identity and as-of currency, and transparent visibility of missing or unverified port records so designers, installers, and maintenance technicians trace physical cable paths accurately without conflating planned runs with installed reality.
topics:
  - "cabling-schedule"
  - "physical-cabling"
  - "patch-panels"
  - "port-mapping"
  - "as-built-records"
  - "network-infrastructure"
use_when:
  - "Network engineers, installers, or facility operators need a controlled schedule mapping cables, patch panels, ports, and endpoints."
  - "An author is documenting planned or as-built physical cabling paths while exposing unverified connections or plant gaps."
  - "A technician needs to determine exact panel-to-endpoint cabling connectivity at a stated as-of point."
not_for:
  - "Recording logical IP prefix, VLAN, and hostname assignments, which belongs in a network allocation register."
  - "Designing logical network topology, routing, and security zones, which belongs in a network design description."
  - "Tracking firewall or ACL traffic rules, which belongs in a network access rule register."
---

# Cabling schedule specification

## Identity and selection

- **Specification ID:** `CABLING-SCHEDULE@core`.
- **Specification edition:** `1.0`.
- **Purpose:** Identify each cable, panel, port, and the endpoints it connects, whether the row is planned or as built.
- **Intended readers:** The people who design, install, or maintain the cabling plant, and anyone who must find which port a cable uses.
- **Decision or action supported:** Determine the planned or as-built path of a cable from panel and port to its endpoints.
- **Use when:** A cabling plant needs a controlled schedule of cables, panels, ports, and endpoints.
- **Scope boundaries:** Limit entries to cable connection paths and their planned or as-built state.

## Authoring inputs and unresolved facts

Obtain the plant or site the schedule covers, the as-of point, and each cable's identity, panels, ports, and endpoints that are actually known. Determine whether each row is planned or as built. Inspect actual equipment observations when the schedule needs to identify equipment endpoints.

If a cable, panel, port, or endpoint is unknown, record the gap. Do not invent an endpoint, port, or label. A planned row MUST be labeled planned. An as-built row MUST be labeled as built and MUST rest on an observation or installation record the project actually has. Do not present a plan as as built.

## Finished-document contract

- **Title:** Identify the site or plant and name the document as its cabling schedule.
- **Frontmatter:** Required. Begin with a YAML 1.2 Semantic-Discovery frontmatter block delimited by `---` lines containing `title`, `description` (60 to 140 neutral retrieval words), `topics` (3 to 12 concrete terms), `use_when` (2 to 6 neutral task conditions), and conditional `not_for` (1 to 5 grounded exclusions, omitted when empty), followed by the GFM H1 title. Exclude internal IDs, version strings, hashes, filesystem paths, build metadata, and unresolved template delimiters from frontmatter values (Rule 13). Plant identity and the as-of point belong in the body. Governing source: Collection Semantic-Discovery Frontmatter contract (standard 3.0.0).
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. Omit it for internal documents unless a specific project policy requires explicit negative attestation. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State the plant and the meaning of planned and as built before the cable rows. State gaps after or with the rows. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
| --- | --- | --- |
| Identity and scope | Required | Identify the site or plant, the as-of point, the space the schedule covers, and what it excludes. Include the client or receiving-party element from this contract when applicable. |
| Cable rows | Required | For each cable in scope, identify the cable, the panel, the port, and the endpoints, and label the row planned or as built. If no cable is yet identified, say so instead of adding a placeholder row. |
| Gaps | Required | Identify missing ports, endpoints, or labels, and any row whose planned or as-built state is not established. State the next action. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
| --- | --- | --- |
| Plant scope | One site or cabling plant per schedule. | State the as-of point and the spaces included. |
| Cable | Zero or more cables in that plant. | Give each cable a stable identity within the schedule. Do not reuse an identity for a different cable. |
| Panel and port | The panel and port for each stated end that has them. | Name the panel and the port. A missing port stays a gap. Do not invent a port number. |
| Endpoints | The two ends the cable connects, when known. | Name each end, including the equipment identity when that end connects to known equipment. An unknown end stays unknown. |
| Row state | One state per cable: planned or as built. | Planned is not as built. As built requires an actual observation or installation fact. A row with no established state is a gap, not as built. |

Use a schedule table with cable, panel, port, endpoints, and planned or as-built state. Prose should explain a gap or a plant boundary the table cannot carry. Do not include a blank cable row.

## Quality criteria

- Each cable row states its cable, the known panel and port, the known endpoints, and whether it is planned or as built.
- A planned row cannot be read as as built.
- Unknown ports and endpoints stay visible. The schedule invents no cable, port, endpoint, or party.
