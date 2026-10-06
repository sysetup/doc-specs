# Learning tutorial specification

## Identity and selection

- **Specification ID:** `TUTORIAL@core`.
- **Purpose:** Guide a learner through a bounded practice exercise with a learning objective and observable checkpoints.
- **Intended readers:** Learners and instructors responsible for the stated prerequisites and practice environment.
- **Decision or action supported:** Complete a supported learning progression and recognize its practice outcome.
- **Use when:** A product or engineering concept needs a hands-on learning path.
- **Scope boundaries:** Define a safe, bounded learning exercise; exclude operational work authorization, comprehensive technical lookup, and claims that the reader already succeeded.

## Authoring inputs and unresolved facts

Inspect the learning need, learner prerequisites, product or concept and tutorial editions, controlling technical sources, reproducible isolated environment and permitted target, supplied or generated practice inputs, exact actions, expected checkpoints, failure recovery, reflection and cleanup. Obtain the actual walkthrough configuration, procedure, observations, failures and check status, or its not-run basis, and inspect change and maintenance arrangements.

Expose unknown version, environment, target, prerequisite, action, expected observation, permission, safety or cleanup fact with its consequence, resolving action and assigned owner only when established. Keep the affected path a draft and stop dependent practice or favorable readiness until resolved. Distinguish a harmless untested draft from a supported learner-ready path; untested steps are not proof of a usable progression. Do not invent commands, accounts, privileges, results, support ranges or learner achievement.

## Finished-document contract

- **Title:** Name the learning outcome and identify the product or concept when needed.
- **Frontmatter:** None. Begin with the standalone GFM title. Put editions, scope, readiness and actual check state in the body. Governing source: Type-owned TUTORIAL@core policy; no external publication metadata schema is selected.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State learning goal and prerequisites before environment preparation; present practice steps and checkpoints in dependency order; put outcome reflection and cleanup last. Heading wording may vary.
- **Presentation:** Required roles may share concise paragraphs, lists or sections when prerequisites, actions, checkpoints, gaps and readiness remain retrievable in dependency order. Use local step locators for recovery; a compact tutorial needs no separate administrative chapter per role.

| Projection | Title and metadata ownership | Syntax and source authority |
|---|---|---|
| Guided learning document (standalone) | The document owns an H1 identifying the bounded learning outcome and subject. Editions, environment and readiness are body content; no YAML frontmatter is used. | GFM presents the guided practice; commands and inputs preserve the stated version's actual syntax. Bind controlling technical sources and walkthrough evidence to inspected editions and usable locators, with revisions or digests where needed. A changed source, exercise or environment requires reassessment before retaining learner-ready applicability; historical evidence remains bound to its original configuration. |

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Learning goal and audience | Required | Identify the bounded objective, learner prerequisites, product or concept and tutorial editions, scope, exclusions and client or receiving-party element. State draft or learner-ready applicability for the declared environment; a readiness label does not establish personal achievement or professional competence. |
| Practice environment and preparation | Required | Specify the reproducible isolated environment, exact permitted target, inputs and source editions, applicable resources and costs, permissions, prerequisite checks and safe stop conditions before dependent actions. Use placeholders for sensitive values and expose unavailable prerequisites. Commands express an exercise method and confer no operational authority. |
| Incremental exercise and checkpoints | Required | Give ordered locally identifiable steps with purpose, exact version-applicable actions, expected observations, checkpoint criteria and recovery or safe stop. Verify command syntax and target boundaries before presenting a supported path; every failure route ends in an identified retry, recovery or stop. Keep choices bounded and link reference or explanation as support without replacing practice. Label held or untested steps and do not turn expected output into an observed result. |
| Practice outcome and reflection | Required | Describe the expected observable practice outcome and connect it to the objective and checkpoints. Include reflection that relates actions to the exercised concept. Distinguish expected outcome, actual author observations, a learner's own completion and assessed competence; require the learner's observations before claiming their success. |
| Cleanup, applicability, and upkeep | Required | Define removal or restoration only for identified exercise-created resources, its permissions and final checkpoint, and preserve unrelated work; give a reason when no removal is needed. State draft or learner-ready applicability by edition and environment, known failures and actual complete walkthrough or explicit partial, failed, inconclusive or not-run status. Bind performed actions, observations and outcomes to actual procedure, configuration, actor, times and evidence, retaining failures and retests. Learner-ready requires a supported safe path from prerequisite checks through practice, checkpoints, recovery arrangements, reflection and bounded cleanup; unresolved required checks keep that path a draft. Record untested combinations, maintenance owner or gap, and update triggers. Reassess after changed sources, inputs, actions, targets, runtime or cleanup rather than expanding historical support. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Learning objective | Exactly one bounded objective in Learning goal and audience. | Name a practice capability and its observable outcome; do not claim professional competence from one exercise. |
| Practice environment | Exactly one reproducible setup in Practice environment and preparation. | Bind editions, inputs, permitted target, runtime and permissions before practice. Unsupported combinations stay untested or blocked; an unspecified production target is prohibited. |
| Exercise step and checkpoint | One or more ordered steps, each with a checkpoint, in Incremental exercise and checkpoints. | Each names action, purpose, expected observation, comparison and locally identifiable recovery or safe stop. A supported command has checked syntax and target bounds; expected results remain distinct from actual runs. |
| Practice outcome | Exactly one expected outcome in Practice outcome and reflection. | Relate it to the learning objective and checkpoints; reader completion requires their own actual observations. |
| Cleanup and applicability basis | Exactly one account in Cleanup, applicability, and upkeep. | Limit cleanup to exercise-created resources and stated authority, with an observable final condition or an assessed no-removal reason. Checked, untested, unsupported and unknown combinations remain distinct; reassess changed inputs before extending support. |
| Path readiness | Exactly one applicability account by edition and environment in Learning goal and audience and Cleanup, applicability, and upkeep; repeat dispositions when combinations differ. | Use draft for an untested path, missing prerequisite or unresolved required check. Use learner-ready only with supported safe complete walkthrough evidence at the declared configuration. A changed path returns to draft pending reassessment; no result establishes approval or learner success. |
| Walkthrough evidence | Exactly one check-status account in Cleanup, applicability, and upkeep, with one entry per actual attempt when performed. | Identify the actual procedure and configuration, actor, captured times or timing gaps, actions, observations, outcome and evidence locators. Preserve each failure and retest; mark partial, inconclusive and not-run work explicitly. Static wording checks do not substitute for executing the claimed path or establish human learning. |

Use a guided sequence with short explanations and visible checkpoints. Examples and diagrams may clarify the practice path when applicable to the stated version. Reference and conceptual explanation remain linked support, while the tutorial controls learner progression. Commands convey an exercise method and do not grant permissions.

## Quality criteria

- Objective, audience, prerequisites and subject editions let the learner identify the bounded capability without a competence or personal-achievement claim.
- Preparation identifies the isolated target, runtime, inputs, resources and permissions before dependent actions; missing facts have a resolving action and safe stop rather than a guessed setup.
- Every supported step has checked applicable actions, an expected observable checkpoint and a locatable recovery or stop route; sequence and reflection connect actions to the bounded learning outcome.
- Cleanup and its final check affect only exercise-created resources under stated authority, or explain why removal is unnecessary; unrelated work remains preserved.
- Learner-ready claims have supported safe complete walkthrough evidence at the stated editions and environment; missing, partial, failed, inconclusive or not-run required checks keep the affected path a draft. Actual configurations, observations, failures, retests, limitations and update triggers prevent historical results from becoming broader support or human-learning claims.
