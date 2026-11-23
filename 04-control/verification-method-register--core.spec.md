---
title: "Verification method register specification"
description: >-
  Defines the authoring contract for verification method registers maintaining a shared, controlled index of reusable or proposed technical conformance assessment methods and variants across a project or item scope. Covers method-control rules, method categories, applicability and verification levels, capability limits and prerequisites, decision state and approval authority, links to planned procedures or verification events, and open methods awaiting decision while excluding step-by-step execution scripts and per-requirement result rows.
topics:
  - "control-records"
  - "verification-and-validation"
  - "verification-methods"
  - "method-register"
  - "assessment-capabilities"
  - "method-applicability"
  - "conformance-planning"
  - "verification-control"
use_when:
  - "A project uses multiple reusable verification methods or variants and needs one shared catalog of applicability and capability limits."
  - "A verification planner is selecting authorized assessment methods and linking them to procedures and planned activities."
  - "A reviewer is checking which proposed verification methods remain pending approval and what limitations bound their use."
not_for:
  - "Writing ordered step-by-step conformance execution instructions, which belongs in a verification procedure."
  - "Tracking requirement-by-requirement verification status and evidence, which belongs in a requirements verification matrix."
  - "Recording actual observed verification outcomes, which belongs in a verification evidence record."
---

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
- **Frontmatter:** Required. Begin with a YAML 1.2 Semantic-Discovery frontmatter block delimited by `---` lines containing `title`, `description` (60 to 140 neutral retrieval words), `topics` (3 to 12 concrete lowercase kebab-case terms), `use_when` (2 to 6 neutral task conditions), and conditional `not_for` (1 to 5 grounded exclusions, omitted when empty), followed by the GFM H1 title. Exclude internal IDs, version strings, hashes, filesystem paths, build metadata, and unresolved template delimiters from frontmatter values. Method authority and applicability belong in the body. Governing source: Collection Semantic-Discovery Frontmatter contract.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. Omit it for internal documents unless a specific project policy requires explicit negative attestation. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Define the project scope and method-state rules before the entries; place unresolved choices and maintenance information after them. Heading wording may vary.
- **Presentation:** Use compact registers, structured item tables, or grouped lists sized to the controlled inventory without placeholder rows. Required roles may share sections while keeping stable identities, owners, states, source locators, and reconciliation gaps directly retrievable.

| Projection | Title and metadata ownership | Syntax and source authority |
| --- | --- | --- |
| Verification method register (standalone) | Begin with the mandatory 5-key Semantic-Discovery YAML frontmatter followed by one scope-specific H1. Control scope, as-of point, state, ownership, and authority references remain body content, inheriting corpus-level changelog/VCS versioning, declared default maintainer, and external specification provenance when governed in a unified operational corpus. | Use GFM prose, tables, or structured lists bound to controlling masters and inspected snapshots. Referenced systems, trackers, or baselines remain authoritative for their native records; changes to controlling sources require reconciliation rather than silent overwrite. |

| Section role | Status and inclusion condition | Content obligation |
| --- | --- | --- |
| Scope and method-control rules | Required | Identify the item or project boundary, technical requirement classes and levels served, method decision authority, applicable edition or as-of point, state vocabulary, and how methods are selected, revised, superseded, and linked to assessments. Define project-specific meanings for method categories where ambiguity would affect selection. |
| Method entries | Required | Give one entry per real candidate or controlled method variant, or an explicit assessed-empty gap. State its stable ID, category, purpose and observable or calculable property, suitable item level and conditions, adequacy rationale, capability or qualification conditions, limits, accountable method owner, and proposal/selection/approval state with actual decision reference where needed. Link to real planned event or controlled procedure references when established. |
| Open methods and maintenance | Required | Identify methods with unresolved capability, authority, level, resource, or procedure questions; state the consequence and resolution route. Explain how changes to the technical basis, item, tool, or criteria trigger method review and how superseded entries remain distinguishable from current choices. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
| --- | --- | --- |
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
