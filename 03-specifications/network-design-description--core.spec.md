# Network design description specification

## Identity and selection

- **Specification ID:** `NETWORK-DESIGN-DESCRIPTION@core`.
- **Purpose:** State the required topology, segmentation, routing, intended addressing, wireless design, and network services for one enterprise or data-center network.
- **Intended readers:** Network designers, systems engineers who allocate the network as a system element, implementers, and reviewers who must see what the network is required to be.
- **Decision or action supported:** Realize the network from a controlled design with explicit intended configuration, design choices, and unresolved decisions.
- **Use when:** One enterprise or data-center network needs a design that states how it is segmented, routed, addressed, served, and, when in scope, provided by wireless.
- **Scope boundaries:** Specify one network's intended topology, segment and trust relationships, forwarding paths, addressing, wireless access when in scope, and service dependencies.

## Authoring inputs and unresolved facts

Obtain the network's boundary, the sites or facilities it covers, the system elements it connects, the trust boundaries the project actually requires, the routing relationships, the intended address plan, the network services the design depends on, and the wireless requirement if wireless is in scope. Inspect supplied project system context, interface definitions, and requirements that identify network allocations or constraints, including their editions or locators when available.

If topology, a segment, a route, an address plan, a wireless parameter, or a service is unknown, record the gap, its effect on realization, the resolving action, and the actual owner if assigned. Label a proposed choice as proposed. If wireless is outside the network's scope, say so with the scope reason and do not invent radios, channels, or controllers. If no address plan is established, say that the intended addressing is unresolved. Identify any cited current assignment by its actual allocation record and configuration, and label intended changes explicitly. State each design choice as a required configuration or behavior, with diagrams used to illustrate it. Do not invent parties, approvals, or verification results.

## Finished-document contract

- **Title:** Identify the network and name the document as its network design description.
- **Frontmatter:** None. Begin with the GFM title. Network identity and design state belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State identity and scope before topology and segmentation. State routing, intended addressing, wireless design, and network services before unresolved decisions. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Identity and scope | Required | Identify the network, its boundary, included sites or facilities, connected system elements, exclusions, and design state. Include the client or receiving-party element from this contract. Identify its allocation and connection relationships within the supplied project system context, citing the actual project record and edition when one exists. |
| Topology and segmentation | Required | State the required topology and the segments or zones, including what each segment is for and which trust boundary it represents. State which classes of traffic the design intends to keep apart and how the intended topology establishes those boundaries. |
| Routing | Required | State the required routing relationships, including how segments reach one another, any default or external path, and the failure behavior the design requires. Leave an undecided path as a gap. Do not paste a device configuration as a substitute for the requirement. |
| Intended addressing | Required | State the intended address plan: which prefixes or ranges serve which segments, and how names are intended to be assigned. Identify the decision state of intended allocations and label any cited current assignment by its actual record and configuration. Where the plan is unresolved, say so. |
| Wireless design | Conditional: the network includes wireless access or a wireless segment | State the required wireless roles, coverage intent, separation from other segments, and the control or authentication approach the design requires. If wireless is out of scope, omit this section and record the scope reason under identity. Do not invent radios, channels, or controllers. |
| Network services | Required | State the network services the design requires, such as name resolution, address assignment service, time, or load distribution, and which segments use them. For a service class that is out of scope, say so. An unresolved service remains a gap. |
| Unresolved design decisions | Required | List material gaps and proposed choices with their effect on realization and the next action. A diagram, if used, illustrates these statements. It does not replace them. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Network boundary | One network per document. | Name what is inside and outside, including external connections. Do not expand the boundary to cover an undescribed network. |
| Segment or zone | One or more required segments, or an explicit statement that segmentation is unresolved. | Give each segment a stable name, its purpose, and its trust relationship to the others. The name identifies the logical zone; state any intended VLAN identifier and its decision state separately when relevant. |
| Route requirement | One or more required paths, or an explicit gap for a path the design must decide. | State the source, destination, and intended forwarding or failure behavior. A vendor command list is not the requirement. |
| Intended prefix or name plan | Zero or more intended allocations; a gap when the plan is not established. | Bind each intended prefix, range, or name pattern to a segment or service. Do not present a current assignment as the intended plan. |
| Wireless requirement | Zero when wireless is out of scope; otherwise the required wireless design. | State role, coverage intent, segment attachment, and control approach. Omit parameters that do not apply, and do not invent them. |
| Network service | Each service the design requires, plus each material service class the design excludes. | State who consumes it and which segment provides it. An excluded class needs a scope reason. |
| Diagram | Optional illustration of topology, segmentation, or paths. | The prose or tables remain authoritative. A loose diagram does not replace a required statement. |

Use prose for design intent and a table when several segments, prefixes, or services must be compared. A diagram MAY clarify topology. It MUST NOT be the only statement of topology, segmentation, routing, intended addressing, wireless design, or network services.

## Quality criteria

- The required network configuration and behavior are explicit in prose or tables, with design state and any cited current configuration identified.
- Topology, segmentation, routing, intended addressing, and network services are each stated or explicitly unresolved. Wireless is stated or excluded with a scope reason.
- Intended prefixes and names are not written as the assignment now in force.
- Each topology, segment, route, allocation, wireless, or service statement is tied to the identified network boundary and intended configuration.
- Unknown and proposed facts stay visible. The document invents no party, approval, or verification result.
