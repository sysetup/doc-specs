# Needs and intended-use validation matrix specification

## Identity and selection

- **Specification ID:** `VALIDATION-MATRIX@core`.
- **Purpose:** Account for how in-scope stakeholder, business or mission, or intended-use needs map to validation scenarios, criteria, methods, evidence, and current outcomes.
- **Intended readers:** Validation leads, stakeholder or user representatives, need owners, and reviewers judging whether fitness-for-use claims are supported.
- **Decision or action supported:** See which needs have a credible validation path, what has actually been assessed under which conditions, and which needs remain uncovered, failed, or inconclusive.
- **Use when:** A bounded need or intended-use set requires a control view of planned validation and current results.
- **Scope boundaries:** Entries assess stakeholder-visible outcomes and fitness under representative use conditions. Need wording must express the desired outcome or intended-use question; a prescribed technical or organizational obligation alone does not establish that need.

## Authoring inputs and unresolved facts

Inspect the solution and configuration boundary; the stakeholder, business or mission, or intended-use needs and their source editions; relevant users or proxies; scenarios and operating conditions; agreed or proposed effectiveness criteria; methods or procedures; planned events; and responsible roles. Establish the stakeholder-visible outcome or intended-use question for each need, rather than substituting a prescribed technical or organizational obligation. Inspect evidence, results, and acceptance decisions only when reporting that they exist. Identify each need's actual origin and cite its source record when one exists; otherwise state the need and its inspected origin in the matrix.

If a need source, scenario, criterion, configuration, method, or responsible role is missing, keep the need visible as a gap with the consequence, resolving action, and actual owner if assigned. Do not invent a user population, threshold, pass, or acceptance. If the stated scope has no established needs, say so and name the source gap instead of adding a sample row. A scheduled event, procedure identifier, or approved matrix is not a validation result.

## Finished-document contract

- **Title:** Identify the solution or intended-use scope and name the document as its validation matrix.
- **Frontmatter:** None. Begin with the GFM title. Need basis, mappings, and results belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State scope and status rules before the mappings; place coverage and unresolved findings after them. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Scope, need basis, and status rules | Required | Identify the solution and configuration boundary, need sources and editions, included and excluded use questions, status meanings, and who maintains the matrix. State the intended-use fitness question assessed by the entries. |
| Need-to-validation mappings | Required | Include every in-scope need or an explicit assessed-empty or source-gap statement. For each mapping, show the need, scenario and user or proxy population, representative conditions and fidelity limits, evaluation criteria, method, target configuration, and responsible role. Show evidence and an assessment result only for work that occurred. A selected scenario that was not attempted may be recorded as `not-run` with its bounded event and reason, but has no actual evidence. |
| Coverage, limits, and unresolved work | Required | Judge each need across its scenarios and real results. Identify missing scenarios, non-representative conditions, failed or inconclusive outcomes, stale results after a need or solution change, and the route for reassessment. Keep a favorable result separate from stakeholder or receiving-party acceptance. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Need identity | One entry for each in-scope need or intended-use question; zero only with an explicit assessed-empty or unresolved-source statement. | Give a stable project identifier when one exists, plus source, edition, and locator. A locally stated need must name its real origin. State the stakeholder-visible outcome, business or mission need, or intended-use question. A prescribed technical or organizational obligation alone is insufficient; establish the outcome or use question to be assessed. |
| Validation mapping | One or more mappings when a validation path exists; zero for a visible uncovered need. | Several scenarios may support one need. Do not count each row as a separate need. Identify scenario, actors or proxies, conditions, criterion, method, configuration, and responsible role. |
| Scenario and representativeness | Required on every mapping that claims a validation path. | State the user or operator population, task, environment, and known simulation or sampling limits. A scenario name without those conditions does not show that intended use was represented. |
| Evaluation criterion | At least one observable rule for each planned mapping. | State the effectiveness comparison, units or qualitative rubric, and whether stakeholders have agreed it. Proposed criteria stay labeled proposed. The criterion is not an acceptance authorization. |
| Method | One identified method per planned mapping. | Cite the actual procedure used for this use question by edition; otherwise describe the method sufficiently here to assess the stated criterion under the representative conditions. |
| Evidence and result | Zero or more actual assessment entries per mapping, plus selected unattempted scenario entries when relevant; a current summary is optional. | Use `pass`, `fail`, or `inconclusive` only for an attempted assessment, with actual configuration, method edition, assessed context, observation locator or missing-observation reason, and review state. `pass` needs an established fitness criterion and supporting observation in the stated context; `fail` needs an observed miss; an attempted comparison without a usable basis is `inconclusive`. Here `not-run` means a scenario selected for a bounded validation event received no validation action or result assertion; identify the event and reason, without claiming actual evidence or assessed context. When citing a test run, identify the selected scenario's case and attempt, if an attempt occurred. Mere planning has no result. Preserve unfavorable outcomes and separate reassessments; any current summary must explain which applicable entries it represents. |
| Acceptance reference | Conditional on an actual stakeholder or receiving-party decision. | Cite the decision, authority, and scope. Absence of a reference is neither denial nor acceptance. A passing validation result does not create acceptance. |
| Need coverage | One assessed state per in-scope need: `gap`, `planned`, `partial`, `met`, `not-met`, or `inconclusive`, with configuration and as-of point. | `gap` means a required scenario, criterion, or method is missing and no assessment was attempted. `planned` means the required representative conditions have a suitable scenario, criterion, and method but none was assessed, including when a selected scenario was `not-run`. `partial` means at least one required condition has an observed pass but the need-level claim still lacks an assessment or required review for one or more conditions, with no unresolved failed or inconclusive required condition. `not-met` means an observed failure against an established required fitness criterion; state any other unassessed conditions too. `inconclusive` means an attempted required comparison lacks a usable basis and no required condition is currently known to have failed. `met` requires checked passing evidence under established criteria for all declared representative conditions, with no unresolved contradictory result; it does not cover every imaginable use. Acceptance is never a coverage state. |

Use a need-centered table or linked tables with columns for need, scenario and population, conditions and fidelity limits, criterion, method, configuration, evidence, result, and coverage. Put long rationale in notes keyed to the row. Each row must assess the stated need or intended-use question under representative conditions. Do not copy a blank matrix or hide uncovered needs.

## Quality criteria

- Every in-scope need is accounted for at the correct source edition, including needs with no scenario or criterion yet.
- Scenario, population, conditions, and criterion can actually inform the stated use question; an identifier link alone is not validation.
- Planned work, observed fitness, and an authorized acceptance decision remain separate.
- Failed, inconclusive, invalid, and superseded results stay visible. A planned reassessment changes no coverage state; a later checked pass can support `met` only after any earlier contradictory finding is resolved for the stated scope.
- Coverage counts needs and declared use conditions, not duplicate scenario rows. 
