# Product guide specification

## Identity and selection

- **Specification ID:** `PRODUCT-GUIDE@core`.
- **Purpose:** Explain how to install, configure, and use the delivered product.
- **Intended readers:** The people who install, configure, or use that product, and the role that keeps the guide aligned with the delivered behavior.
- **Decision or action supported:** A reader can install, configure, and use the product within the conditions the guide actually states.
- **Use when:** A delivered product needs recipient-facing instructions for installation, configuration, and use.
- **Scope boundaries:** Cover recipient-facing installation, configuration, and use for the stated product and version.

## Authoring inputs and unresolved facts

Obtain the product identity and delivered version or version range, the audience, the supported environment, the installation path, the configuration the user must set, the ordinary use the product provides, and the limits or recovery a user needs. Inspect the product's actual behavior or an established description of it.

If a step, setting, supported environment, or limit is unknown, say so and do not invent it. If the product has no installation, or no user configuration, state that with a scope reason and omit the empty procedure. Label an unreleased or proposed behavior as proposed. Describe steps and expected outcomes without claiming that a reader has performed them.

## Finished-document contract

- **Title:** Identify the product and name the document as its product guide.
- **Frontmatter:** None. Begin with the GFM title. Product identity and the guide's covered version belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Identify the product and audience before installation, configuration, and use. State limits and unresolved items after the procedures. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Identity and scope | Required | Identify the product, the version or version range this guide covers, the audience, the supported environment, and what the guide does not cover. Include the client or receiving-party element from this contract. |
| Installation | Conditional: the product is installed by the reader | Give the prerequisites, the installation sequence, and the check that shows installation completed. If the product is not installed by the reader, omit the procedure and state that reason in identity and scope. |
| Configuration | Conditional: the reader must set product configuration | State each setting the reader must choose, the effect of the choice, and the value or rule when one is established. An unknown setting stays unresolved. Do not invent a default and present it as required. |
| Use | Required | Explain the ordinary use the product provides, the inputs the reader supplies, the result the reader should see, and the conditions under which that use applies. |
| Limits, recovery, and unresolved facts | Required | State material limits, the user-visible recovery or failure behavior that is established, and any unknown step, setting, or environment. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Product and version | One product and the version or range this guide covers. | Do not present the guide as current for an unstated version. A proposed version is labeled proposed. |
| Reader task | One or more use paths; installation and configuration only when they apply. | Keep each path something the product's reader does. |
| Setting | Zero or more settings the reader must set. | State the name, the effect, and the established value or choice. An unknown value remains unknown. |
| Expected user result | One result for each stated use path. | Describe the expected observable outcome of the path. |
| Limit or failure | Each material limit or user-visible failure the guide relies on. | State what the reader can do. Do not invent a recovery the product does not provide. |

Use ordered steps for installation and for a use path whose sequence matters. Use a table for settings when several must be compared. Prose should explain what the product does and when a path does not apply.

## Quality criteria

- The guide tells a reader how to install, configure, and use the stated product version, or it states which of those paths does not apply.
- Steps and explanations address the product's recipients and stated use paths.
- Unknown steps, settings, and environments stay visible. The guide invents no behavior, party, or completed installation.
