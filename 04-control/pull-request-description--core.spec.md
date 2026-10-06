# Pull or merge request description specification

## Identity and selection

- **Specification ID:** `PULL-REQUEST-DESCRIPTION@core`.
- **Purpose:** Present an identified change for review and integration with its rationale, validation, risks, and pending decisions.
- **Intended readers:** Change authors, reviewers, integrators, maintainers, and relevant release or operations roles.
- **Decision or action supported:** Assess the requested diff and decide which review, integration, or readiness questions remain.
- **Use when:** An identified repository change is submitted or prepared for pull-request or merge-request review.
- **Scope boundaries:** Control the review request for one bounded diff; exclude performed code-review evidence, baseline-change authorization, actual merge, deployment, and acceptance.

## Authoring inputs and unresolved facts

Inspect the repository and bounded proposed diff; request or draft identity and current status; actual standalone or native surface and its title, metadata, syntax, and authoritative locators; current base and head and immutable checked snapshot or configuration; concrete trigger and before-and-after result; changed components, versions, sources and exclusions; checks actually performed with evidence, failures and coverage; material compatibility, migration, data, security and operational concerns; rollout and reversal dispositions; and reviewer questions or decision dependencies.

Expose unknown base, head, checked snapshot, host provenance, validation, impact, rollout, or reversal facts with consequence, resolving action, and assigned owner if known. Mutable branches and host status are context rather than immutable checked evidence. Missing diff identity or changed host metadata blocks applying earlier checks to the current diff until applicability is re-established. Unperformed checks remain not-run; a material assessment gap blocks the dependent readiness claim. Do not invent issues, commits, reviewers, successful checks, approval, merge, release, or deployment.

## Finished-document contract

- **Title:** Use a title stating the concrete change. A standalone GFM document begins with its own H1; a native request body uses the host-owned title and omits its H1 when the declared surface requires that.
- **Frontmatter:** None. Omit YAML frontmatter. Only standalone GFM begins with its own H1. A native body follows the host-owned title rule without an added H1; scope, client context, and checked-snapshot provenance remain retrievable in the body or referenced host fields under the declared projection. Governing source: This type's standalone and native-request body policy; host metadata stays in the selected host.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Explain the concrete problem and result before diff scope; place actual validation before material risks, rollout, reversal, and requested reviewer decisions. Heading wording may vary.
- **Presentation:** Scale the description to the diff. Small documentation or maintenance changes may combine all required roles into a few paragraphs or a short list without a heading per role. Describe the concrete document or configuration result when no runtime behavior changes; retain actual check status, reasoned risk and rollout dispositions, reversal limits, and pending decisions.

| Projection | Title and metadata ownership | Syntax and source authority |
|---|---|---|
| Standalone GFM (standalone) | Supply one concrete-change H1. The body identifies repository, request or draft status, current base/head or gaps, and checked snapshot with provenance. | Use GFM prose, lists, or tables. Identify the current diff and each immutable checked snapshot independently. Refer to actual source masters; later edits require applicability reassessment rather than rewriting old check identities. |
| Native request body (native) | The identified host owns the request title; omit a redundant H1 on a host body that excludes it. Host fields remain authoritative for current repository, request identity, base/head and integration status. Identify their inspected locator or snapshot and field ownership; do not maintain copied current metadata as a second master. | Use the selected host body syntax and inspected surface edition; do not inject YAML metadata or claim an unselected provider schema. Bind check records to their original immutable source or merge configuration and identify its relationship to inspected host base/head. If host metadata or diff content changes, preserve old observations, mark current applicability unresolved, and reassess before a current-readiness claim. |

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Request identity and change rationale | Required | Identify repository, actual request or draft identity and status, current base/head or explicit gaps, and their body or host provenance. Explain the concrete trigger, before-and-after result and intended benefit; use an observable document or configuration result when there is no runtime behavior change. Include the client or receiving-party element. |
| Diff scope and source relationships | Required | State changed components, interfaces and affected versions, material exclusions, and source requirements, defects, changes, or decisions that actually exist. Explain material compatibility effects and distinguish this bounded diff from a larger delivery plan. Use real locators or direct facts with explicit source gaps. |
| Validation actually performed | Required | Record each actual check's command or method, immutable checked snapshot or configuration and relationship to the current diff, observed result, and retained evidence or its absence. State checks not run with reasons, failed or inconclusive outcomes and remaining coverage limits. Preserve earlier check identities when host base/head changes; explicitly re-establish applicability or leave current validation unresolved. |
| Risks, rollout, and reversal | Required | State assessed material compatibility, migration, data, security and operational effects or visible assessment gaps. Give a reasoned no-rollout disposition when none is needed; otherwise identify proposed stages, safeguards, checkpoints, decision dependencies, and reversal route and limits, with real plan locators when available. Unavailable rollback and irreversible effects retain their consequences; intent is not executed deployment or recovery. |
| Review focus and pending decisions | Required | State reviewer questions or an assessed absence, current request readiness or gaps, and actual review or authorization dependencies. Separate review, approval, integration, release and deployment; supply decision evidence only when it exists. A passing check or ready description does not decide those states. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Diff identity and host provenance | Exactly one bounded diff account in Request identity and change rationale. | Identify actual repository and current base/head or gaps with controlling body or host field locators. A mutable request identifier is not an immutable check target. Changing base, head, or relevant content invalidates assumed applicability of earlier checks until reassessed. |
| Concrete change result | One or more observable changes in Request identity and change rationale and Diff scope and source relationships. | Connect the before-and-after result to the trigger and source without copying a requirement master. Documentation, generated artifacts, or configuration-only changes can state their concrete result and assessed runtime-effect disposition rather than inventing behavior changes. |
| Check record | Zero or more actual checks and exactly one coverage and not-run account in Validation actually performed. | Each actual check binds method, observed result, immutable snapshot or configuration, provenance and evidence or its absence. Not-run, unknown, fail, inconclusive and pass remain distinct. A later snapshot does not inherit a pass without explicit scope and applicability evidence. |
| Risk, rollout, and reversal disposition | Exactly one account in Risks, rollout, and reversal. | Tie assessment and applicable stages, safeguards, checkpoints, authority dependencies, and irreversible effects to this diff. Reasoned none-needed and not-assessed differ. A proposed reversal is not an executed rollback; a setting revert does not recover deleted data. |
| Review question and decision account | Zero or more review questions and exactly one pending-decision account in Review focus and pending decisions. | State assessed absence of special questions when appropriate. Only actual reviews and decisions support approval or integration claims; check success, author readiness and missing objections confer none. |

Use a concise rationale and result, bounded scope, actual check facts, risk and reversal notes, and requested decisions. Combine roles for small changes while keeping every obligation retrievable. A native body may rely on identified authoritative host fields for current metadata; checked records retain their original snapshot, provenance and status. Use a table only when multiple checks or material rollout stages make comparison clearer.

## Quality criteria

- A reviewer can identify one diff, concrete trigger and before-and-after result, scope, sources, and current base/head or gaps without inventing runtime effects.
- Standalone H1 and native host title rules agree with frontmatter policy; host field locators and ownership expose current metadata without a second master.
- A reviewer can retrieve actual methods, immutable checked snapshots, failures, not-run reasons and coverage limits; changed host metadata exposes unresolved applicability until reassessed.
- Material risks and assessment gaps lead to reasoned rollout and reversal dispositions, safeguards, checkpoints, decision dependencies and irreversible consequences rather than an unsupported readiness claim.
- The request preserves concise presentation and retrievable reviewer questions, readiness gaps and pending decisions; no check result implies approval, integration, release or deployment.
