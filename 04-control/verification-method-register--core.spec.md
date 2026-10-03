# Verification method register specification

## Identity and selection

- **Specification ID:** `VERIFICATION-METHOD-REGISTER@core`.
- **Purpose:** Control the project methods available or proposed for checking technical requirements, including their applicability, capability limits, decision state, and links to actual planned activities.
- **Intended readers:** Verification planners, method owners, requirement owners, performers, and reviewers choosing or maintaining an assessment approach.
- **Decision or action supported:** Select an adequate method for an obligation and level, identify the authority and conditions for its use, and find the procedures or events that apply it.
- **Use when:** Several verification method definitions or variants need a shared, maintained index across a project or item scope.
- **Scope boundaries:** Record method definitions and variants with their use conditions and decision states; exclude ordered execution steps and per-requirement result rows.

## Authoring inputs and unresolved facts

Inspect the project's technical requirement classes, item levels and configurations, verification approach, available inspection, analysis, test, demonstration, or other methods, and the technical basis or rationale for each method's adequacy. Obtain relevant tool, model, facility, sample, calibration, competence, safety, and environment limits only where they affect use. Inspect actual selection or approval decisions, their decision makers and conditions, and existing event or procedure references.

If method capability, applicability, level, owner, or approval is unknown, record the uncertainty, its effect on method selection, the resolving action, and an actual owner if assigned. Label a candidate as proposed until a real selection or authorization occurs. If no method is established, describe the assessed scope and planning gap rather than inventing a generic method entry.

## Finished-document contract

- **Title:** Identify the project or item scope and name the document as its verification method register.
- **Frontmatter:** None. Begin with the GFM title. Method authority and applicability belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Define the project scope and method-state rules before the entries; place unresolved choices and maintenance information after them. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Scope and method-control rules | Required | Identify the item or project boundary, technical requirement classes and levels served, method decision authority, applicable edition or as-of point, state vocabulary, and how methods are selected, revised, superseded, and linked to assessments. Define project-specific meanings for method categories where ambiguity would affect selection. |
| Method entries | Required | Give one entry per real candidate or controlled method variant, or an explicit assessed-empty gap. State its stable ID, category, purpose and observable or calculable property, suitable item level and conditions, adequacy rationale, capability or qualification conditions, limits, accountable method owner, and proposal/selection/approval state with actual decision reference where needed. Link to real planned event or controlled procedure references when established. |
| Open methods and maintenance | Required | Identify methods with unresolved capability, authority, level, resource, or procedure questions; state the consequence and resolution route. Explain how changes to the technical basis, item, tool, or criteria trigger method review and how superseded entries remain distinguishable from current choices. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Method entry | Zero or more distinct method definitions or variants; at least one for a populated register. | Give each a stable ID within the declared namespace. Describe the controlled method at definition level. The entry MUST NOT contain ordered execution steps. |
| Method category | One per entry: inspection, analysis, test, demonstration, or a justified project-defined alternative. | Explain the property observed or calculated and why this method can expose it. Identify the requirement facets it can assess; additional categories may be needed for other facets of the same requirement. |
| Applicability and level | One declared scope per entry, with one or more applicable item levels or a visible unresolved choice. | State suitable products, configurations, life-cycle stages, conditions, and requirement classes; identify exclusions and limits. Identify life-cycle stages by their project-defined names and assess suitability for the relevant requirement facets. |
| Capability conditions | Conditional on resources or assumptions that determine adequacy. | State model validity, inputs, sampling, tool accuracy or calibration, facility, personnel competence, independence, or safety conditions where relevant. Do not require equipment qualification for a method that needs none. |
| Decision state and authority | One truthful state per entry and a named decision route. | Distinguish `proposed` from `selected` for planned use, `approved` by an actual authority, and `superseded` with its replacement or reason. Define any local alternative. A selected method is not automatically approved or ready to execute. |
| Activity and procedure references | Zero or more real links per entry. | Identify event or procedure ID, edition, and relevant level when an activity is planned or controlled. The link records planned or controlled method use; identify an unassigned event as an explicit planning gap where needed. |

Use a method table with ID, category, applicability/level, capability limits, rationale, state and decision basis, and actual procedure or event links. Add compact prose for nuanced assumptions or unresolved choices. Do not include per-requirement result rows, blank method examples, or copied procedure steps.

## Quality criteria

- Each method has a coherent technical purpose, suitable level and conditions, and a rationale that supports its proposed use without overclaiming capability.
- Proposed, selected, approved, and superseded definitions remain distinguishable and tied to real decisions where claimed.
- Tool, model, sampling, environment, and competence limits are explicit when they could change a conformance conclusion.
- Procedure or event links identify real planned work, its edition, and relevant level.
- Revisions and unresolved choices have a usable route to update method selection.
