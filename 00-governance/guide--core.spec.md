# Engineering guide specification

## Identity and selection

- **Specification ID:** `GUIDE@core`.
- **Purpose:** Give practitioners reusable, nonbinding recommendations or conventions, with reasons and limits that help them choose how to work.
- **Intended readers:** Practitioners deciding whether and how to apply the advice, and the role that maintains it.
- **Decision or action supported:** A reader can choose a suitable practice, adapt it to the stated context, or identify when it should not be used.
- **Use when:** A practice needs explanation, options, examples, or contextual judgment without creating a new mandatory rule.

## Authoring inputs and unresolved facts

Obtain the problem or practice, intended audience, use contexts and exclusions, recommended approaches, their rationale and material limitations, and established project constraints that affect the recommended choice. Obtain the actual maintainer and review triggers for a maintained guide. If the guide uses examples, establish whether each is illustrative, proposed, or drawn from an actual case; obtain the observation and its locator for an actual case. Identify the guide's edition or current-state marker when the project controls revisions.

If a recommendation lacks an established basis, qualify it as reasoned advice and expose the uncertainty, or defer it; do not claim observed success without evidence. If an owner, context, project constraint, or other required fact is not established, state the gap, consequence, resolving action, and actual owner if assigned. Omit an inapplicable optional example or technique rather than inventing one. Label a draft as proposed; claim approval only when established by an actual decision.

## Finished-document contract

- **Title:** Name the subject or practice and identify the document as a guide; “Engineering Guide” alone is insufficient.
- **Frontmatter:** None. Begin with the GFM title. Context and nonbinding status are substantive body content.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Establish audience, purpose, and applicability before the advice; place maintenance information after the advice. Define a relevant term or project constraint before the advice it qualifies, or identify it at that point. Headings may use project wording if their semantic roles remain clear.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Purpose, audience, and boundaries | Required | State the practice or problem, intended readers, contexts in which the advice helps, material exclusions, and that the guide itself is nonbinding. Identify the current edition or draft state when the project controls it. |
| Recommendations and reasons | Required | Give one or more separately identifiable recommendations or conventions. Explain why each helps, when it applies, and its material limitations, tradeoffs, or alternatives. Express recommended actions as nonbinding choices even when imperative wording is used. |
| Application cues | Conditional when context changes the recommended choice | Give decision cues, adaptation guidance, or a short flow showing which advice fits which situation. Do not turn advice into a mandatory execution procedure. |
| Illustrations | Conditional when an example, diagram, or worked case is needed to prevent material ambiguity | Explain what the illustration demonstrates and its limits. Mark synthetic or proposed examples as such; identify the observation, locator, and scope of an actual case. Limit claims about observed outcomes to what the case evidence establishes. |
| Recommendation basis and project constraints | Conditional when a recommendation relies on project observations or its suitability depends on a project constraint | Identify the supporting observations and locators, state the constraint explicitly, and explain its effect on the recommended choice. Distinguish observed support from reasoned advice. |
| Maintenance | Required | Identify the role that maintains the guide, triggers or cadence for review, and how material changes are made visible to readers. State an unassigned maintainer as an unresolved gap rather than inventing one. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Guide scope | One statement of the practice, intended readers, useful contexts, and material exclusions. | A subject classification, such as security or testing, is optional when it helps readers locate the practice. |
| Binding status | One clear statement that the guide's own advice is nonbinding. | Keep this status consistent across recommendations, examples, and application cues. |
| Guidance item | One or more distinct recommendations or conventions. | Give each a stable heading or local label, the advised action or choice, its rationale, applicability, and material tradeoffs or limits. Do not assert that no tradeoff exists merely because none is known. |
| Illustration | Zero or more examples, diagrams, or worked cases. | Label illustrative, proposed, or actual/sourced status where confusion would affect use. An actual case needs an identifiable source and remains an illustration of the advice. A proposed case is not an approved practice or observed result. |
| Supporting observation or project constraint | Zero or more observations supporting a claim or constraints bounding a recommendation's suitability. | For an observation, identify the actual case or record, relevant version or configuration, and locator. State each project constraint and the contexts in which it affects the advice. |
| Maintainer and review rule | One maintenance role and one cadence or set of review triggers. | The maintainer need not be an issuing authority. Record how readers learn of material changes when the guide is revised. |

Use prose for rationale and caveats. Lists or compact tables may compare alternatives; a decision flow is suitable when context changes the recommendation. Include examples only when they clarify use. A command or sequence may illustrate a practice, but MUST NOT imply authority to execute it. State the actual prerequisites and required authorization if the example could be used operationally.

## Quality criteria

- Each recommendation is understandable, linked to a reason, and bounded by the situations where it is useful; alternatives or costs are stated when material.
- Recommendations remain nonbinding and fit the explicit project constraints and use contexts.
- Observations support the claims for which they are cited; opinion, proposed practice, and observed result remain distinguishable.
- Readers can tell which edition or draft they are using where version control exists, who maintains the guide, and when it should be reconsidered.
