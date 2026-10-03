# Selected control implementation record specification

## Identity and selection

- **Specification ID:** `CONTROL-IMPLEMENTATION-RECORD@core`.
- **Purpose:** Record each explicitly selected control's scoped implementation claim, parameters, evidence, assessment state, exceptions, and residual or open items.
- **Intended readers:** Control owners, security or privacy engineers, assessors, and reviewers who need to see what was selected and what the current implementation claim can support.
- **Decision or action supported:** Determine, for a defined boundary, which controls were selected, how each is implemented or not, which evidence supports that claim, and what remains unresolved.
- **Use when:** A project must maintain implementation and assessment state for specifically selected controls, including controls that are still planned, partial, or not applicable.
- **Scope boundaries:** Record implementation claims and their assessment for explicitly selected controls within the stated boundary. Bound each claim to its statement parts, parameters, implementation, and evidence; a claim for one control does not establish the implementation or effectiveness of the whole set.

## Authoring inputs and unresolved facts

Obtain the system or organizational boundary, the project's explicitly selected control set and revision, the complete control statements and separately selected enhancements supplied for that boundary, each identifier and statement part in scope, organization-defined parameters and the internal role assigning those values, and whether this boundary implements the control or relies on an identified provider. Inspect mechanisms, configurations, versions, related project obligations, evidence, and assessment results only from records that exist. Record an exception, tailoring decision, or residual acceptance only when the project's authorized decision maker made it.

If the selected control-set revision, statement text, parameter, responsible role, or implementation fact is unknown, keep the control visible with status `not-assessed` or `gap` as appropriate, the consequence, the resolving action, and the actual owner if assigned. Do not invent a control from a group name or an example identifier. An intended mechanism is not an observed implementation or a completed assessment. If no control has been selected for the stated boundary, say so instead of adding a sample control.

## Finished-document contract

- **Title:** Identify the boundary and name the document as its selected control implementation record.
- **Frontmatter:** None. Begin with the GFM title. The control-set edition, implementation claims, and status belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State the boundary, control set, and status rules before individual controls; place open items after the claims. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Boundary, control set, and status rules | Required | Identify the system, service, or organizational boundary and as-of point; the project's selected control set and its revision; included and excluded control groups and additional selections; status meanings; and the role accountable for this record. State that selection of a control is not evidence that it is implemented or effective. |
| Selected controls and implementation claims | Required | Include every explicitly selected control, or an explicit statement that none were selected in the assessed scope. For each control, give its identifier, complete statement and parts in scope, project-record locator when available, separately selected enhancements, applicability, parameters, where in the boundary the claim applies, the mechanism or process and version, and one truthful status. Cite evidence and assessment records only when they exist. |
| Exceptions, limits, and open items | Required | For each control, state unimplemented parts, stale evidence, unset parameters, and residual exposure, or state that the stated scope was assessed and none of those limits were identified. Record tailoring, exception, or residual acceptance only with the actual decision. State how a control-set change or a boundary change reopens affected claims. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Selected control | One entry for each explicitly selected control or enhancement; zero only when the scope was assessed and no control was selected. | Give the exact identifier, selected project control-set revision, complete statement and subparts in scope, and project-record locator when available. A group name or example identifier does not select a control. Select each enhancement separately from its base control and include its statement. |
| Control-set edition | One identified revision for the project's selected control set used by this record. | State the actual project set identity and revision or edition, with its selection decision when recorded. The record includes the complete selected statements and parameter definitions needed to assess each claim. |
| Parameters | Required to address for each selected control. | For each parameter in the supplied statement, state its meaning, allowed values or range, assigned organization-defined value and assigning internal role, or state that the statement defines none. Unset parameters that change the required behavior block `implemented` and `verified`. |
| Implementation claim | At least one claim for each selected control. | State the component or process boundary, the mechanism or procedure and its version, and whether that description is intended, observed in place, or not established. Several claims may cover parts of one control. An in-place claim identifies the observed mechanism and evidence; an intended description alone cannot establish it. |
| Responsibility and origination | One accountable role for the record; per control, the role responsible for the claim when assigned. | If another provider implements any part, name that provider and describe only what this boundary does. Do not report the provider's work as local implementation. Leave an unassigned role unresolved rather than inventing a person. |
| Project obligations | Zero or more derived requirement references per claim. | State real derived project obligations and their editions when the project supplied them, with identifiers or locators when available. Otherwise the selected control statement included in the record is the obligation. Do not invent requirement identifiers to fill the chain. |
| Status | Exactly one current status per claim: `not-assessed`, `planned`, `implemented`, `gap`, `not-applicable`, or `verified`. | `not-assessed` means the claim has not been assessed. `planned` describes an intended implementation that is not in place. `implemented` means the stated mechanism or process is in place for that scope; effectiveness remains unverified. `gap` is an assessed shortfall. `not-applicable` cites the project's authorized applicability decision. `verified` requires an assessment that the in-place implementation satisfies the complete selected statement and assigned parameters for the stated scope. A document or identifier alone cannot establish implementation or verification. Record any residual-acceptance decision separately in the disposition field. |
| Evidence and assessment | Zero or more evidence references; assessment references as applicable. | Cite observations, configuration records, or executions that exist, with edition and date or as-of point. `verified` requires at least one such assessment reference. Expected evidence is not actual evidence. |
| Disposition | Conditional on an actual tailoring, exception, or residual-acceptance decision. | Cite the actual project decision, authorized decision maker, affected statement parts, and consequence, with the decision evidence. A proposed disposition stays pending until that decision exists. |
| Limitations | Required to address for each claim. | Name unimplemented subparts, stale or missing evidence, parameter gaps, and known residual exposure. "None identified" is allowed only after assessment of the stated scope. Unknown residual exposure stays unresolved. |

Use one control-centered table, or a short block per control, with columns or labeled fields for identifier, edition, complete statement and locator, parameters, applicability, mechanism and version, status, evidence, assessment, disposition, and limitations. Split inherited or component-specific claims onto their own rows. Do not add blank controls or replace individual claims with an undifferentiated control group or a machine-format export.

## Quality criteria

- Every selected control includes its complete supplied statement and parameter definitions, and every enhancement in scope is selected on its own.
- Status matches the implementation and assessment facts; `implemented` requires an observed in-place mechanism, and `verified` requires an assessment against the stated criteria.
- Unset parameters that define required behavior, and inherited work described as if this boundary performed it, remain visible limits.
- Tailoring, exceptions, residual acceptance, and assessment results each identify their actual decision or observation and its scope. Planned implementation remains distinguishable from observed implementation and completed assessment.
