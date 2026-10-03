# Software composition record specification

## Identity and selection

- **Specification ID:** `SOFTWARE-COMPOSITION-RECORD@core`.
- **Purpose:** Record the components of one software item, with version, origin, and license.
- **Intended readers:** The owner of that software item and anyone who must know which components, versions, origins, and licenses it contains.
- **Decision or action supported:** Determine the components of one software item at a stated version, where each component came from, and which license applies when that license is known.
- **Use when:** One software item needs a controlled statement of its components, their versions, origins, and licenses.
- **Scope boundaries:** Identify components actually contained in the stated software item and version. Component inclusion records composition and does not establish component approval.

## Authoring inputs and unresolved facts

Obtain the software item and the version this record covers, and each component's name, version, origin, and license as those facts are actually known. Inspect the component's own notice or the project's record of origin when it exists.

If a component, version, origin, or license is unknown, record the gap. Do not invent a version, an origin, or a license. Do not assign a license identifier the project has not established. A component's notice may be named when it was inspected. Do not record a secret value.

## Finished-document contract

- **Title:** Identify the software item and version, and name the document as its software composition record.
- **Frontmatter:** None. Begin with the GFM title. The item, version, and as-of point belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Identify the software item before the component entries. State gaps with or after the entries. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Identity and scope | Required | Identify the one software item, the version this record covers, and the as-of point. Include the client or receiving-party element from this contract. |
| Components | Required | For each component, state its name, version, origin, and license when those facts are known. If no component is established, say so instead of adding a placeholder component. |
| Gaps | Required | Identify missing versions, origins, and licenses, and the next action. An unknown license stays unknown. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Software item | One software item and one version per record. | Do not merge a second item into the same component list without saying the record has changed subject. |
| Component | Zero or more components of that item. | Give each component a name that distinguishes it within the record. |
| Version | The component version when known. | State the version that is in the item. An unknown version stays unknown. Do not copy a baseline revision and call it this version unless it is the component version. |
| Origin | Where the component came from, when known. | State the project, supplier, or other established source. Do not invent a registry identity. |
| License | The license that applies, when established. | State the license from the inspected notice or other established record. An unknown license is unknown, not a guessed identifier. |
| Component context | Optional context attached to identified components; none as a substitute for a component row. | Deployment locations or an existing project baseline identifier may be cited. Each component still requires its known version, origin, and license, with gaps explicit. |

Use a component table with name, version, origin, and license. Prose should explain an unknown license or an origin limit. Do not include a blank component row.

## Quality criteria

- The record is one software item at a stated version, and each component shows its known version, origin, and license.
- Unknown versions, origins, and licenses stay visible. The record invents none of them.
- The record invents no party and records no secret value.
