---
title: "Technical request for comments specification"
description: >-
  Defines the authoring contract for technical requests for comments circulating a proposed architectural, protocol, interface, or engineering design change for structured peer review and alignment prior to formal decision or implementation. Covers proposal identity, lifecycle state, and review rules, concrete motivation, measurable goals, and non-goals, proposed technical design, evaluated alternatives and tradeoffs, cross-cutting security, reliability, compatibility, and operational impacts, phased migration and rollback boundaries, tracked open questions and reviewer objections, and explicit disposition separate from implementation authorization.
topics:
  - "control-records"
  - "architecture-and-design"
  - "software-engineering"
  - "technical-rfc"
  - "design-proposal"
  - "peer-review"
  - "migration-planning"
  - "design-alignment"
use_when:
  - "An engineer or architect is proposing a significant technical, architectural, protocol, or cross-team design change for peer comment before implementation."
  - "Reviewers need one structured proposal detailing motivation, non-goals, design, alternatives, cross-cutting impacts, migration limits, and open questions."
  - "A decision body is tracking reviewer objections and recording an explicit proposal disposition before authorizing an ADR, change request, or implementation."
not_for:
  - "Preserving a concise durable record of one already selected architecture choice and its follow-through, which belongs in an architecture decision record."
  - "Performing quantitative multi-criteria scoring and sensitivity analysis across competing options alone, which belongs in a trade study report."
  - "Controlling formal impact approval, execution, and baseline closure for a governed configuration item change, which belongs in a change request."
  - "Submitting one concrete repository code diff for peer review and merge, which belongs in a pull or merge request description."
---

# Technical request for comments specification

## Identity and selection

- **Specification ID:** `TECHNICAL-RFC@core`.
- **Purpose:** Circulate one bounded technical, architectural, protocol, or engineering design proposal for structured peer review, objection resolution, tradeoff evaluation, and explicit disposition prior to formal decision or implementation.
- **Intended readers:** Proposal authors, peer engineers, domain architects, affected service or subsystem owners, security and operations reviewers, and the decision sponsor or review body.
- **Decision or action supported:** Surface design flaws, cross-team dependencies, and migration risks early; resolve material objections; and decide whether to accept the proposal for formal decision recording and implementation, revise it, defer it, or reject it.
- **Use when:** A consequential technical change spans multiple components, interfaces, or teams—or carries high reversal cost—and requires written peer review and design alignment before committing engineering effort or locking an architecture decision record.
- **Scope boundaries:** Govern one pre-decision technical design proposal from draft through peer review and explicit disposition; exclude durable post-decision architecture records, quantitative standalone trade studies, formal baseline change-control execution, code-diff reviews, and commercial client quotations.

## Authoring inputs and unresolved facts

Obtain the proposal identity, author(s), assigned sponsor or shepherd if any, affected systems, interfaces, and teams, current lifecycle state, review venue and comment window, and explicit decision body or acceptance rule; concrete motivation, problem evidence, or user and operational drivers, measurable goals, and explicit non-goals; the proposed technical design covering major components, interfaces, data flows, state transitions, and key invariants; credible alternatives considered (including status quo when credible) and any supporting trade study or analysis report by edition and locator; cross-cutting impact assessments across security, privacy, reliability, performance, compatibility, observability, operational burden, and cost; proposed rollout, migration, compatibility coexistence, and rollback or reversal limits; tracked open questions and material reviewer objections with resolution status; and any actual disposition decision with deciding authority, date, conditions, and downstream handoff records (such as an architecture decision record, change request, or implementation backlog) once created.

If a cross-team dependency, performance impact, security assessment, migration path, rollback feasibility, or deciding authority is unknown or not yet assessed, record that status explicitly with its risk to adoption, resolving action, and actual owner only when assigned. Do not treat peer silence, comment-window expiry, or resolved discussion threads as proposal acceptance. Mark every unassessed cross-cutting impact dimension as `not-assessed` rather than claiming zero impact. Unresolved blocking objections or unestablished decision authority prevent transitioning the proposal to `accepted`. Keep accepted proposal design intent strictly distinct from completed implementation, baseline change approval, or production deployment.

## Finished-document contract

- **Title:** Name the proposed technical change concisely and identify the document as a technical request for comments (RFC).
- **Frontmatter:** Required. Begin with a YAML 1.2 Semantic-Discovery frontmatter block delimited by `---` lines containing `title`, `description` (60 to 140 neutral retrieval words), `topics` (3 to 12 concrete lowercase kebab-case terms), `use_when` (2 to 6 neutral task conditions), and conditional `not_for` (1 to 5 grounded exclusions, omitted when empty), followed by the GFM H1 title. Exclude internal IDs, version strings, hashes, filesystem paths, build metadata, and unresolved template delimiters from frontmatter values. Proposal identity, lifecycle state, review window, and disposition belong in the body. Governing source: Collection Semantic-Discovery Frontmatter contract.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. Omit it for internal documents unless a specific project policy requires explicit negative attestation. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Establish proposal identity, state, and review rules first; state motivation, goals, and non-goals before the proposed design; place alternatives, cross-cutting impacts, and migration before open questions, reviewer feedback, and disposition. Heading wording may vary.
- **Presentation:** Scale diagrams, interface sketches, and impact summaries to the proposal's blast radius without expanding into build-to code specifications or empty administrative chapters. Required roles may share sections while keeping lifecycle state, non-goals, unassessed impacts, open objections, and disposition authority immediately retrievable.

| Projection | Title and metadata ownership | Syntax and source authority |
| --- | --- | --- |
| Technical request for comments (standalone) | Begin with the mandatory 5-key Semantic-Discovery YAML frontmatter followed by one proposal-specific H1. Proposal identifier, authors, lifecycle state, review rules, and disposition authority remain body content, inheriting corpus-level changelog/VCS versioning, declared default maintainer, and external specification provenance when governed in a unified operational corpus. | Use GFM prose, diagrams, and comparison tables bound to inspected architecture baselines, interfaces, and review venues. External review threads remain historical discussion records; the RFC controls the settled proposal revision, while any resulting architecture decision record or change request assumes durable post-decision authority. |

| Section role | Status and inclusion condition | Content obligation |
| --- | --- | --- |
| Proposal identity, state, and review process | Required | Assign one stable proposal identifier; name authors, sponsor or shepherd when assigned, affected systems and teams, current lifecycle state (`draft`, `in-review`, `final-comment`, `accepted`, `rejected`, `deferred`, `withdrawn`, or `superseded`), comment venue, review period or final-comment rules, deciding authority, client or receiving-party element when applicable, and links to upstream problem records or downstream decision records once established. |
| Motivation, goals, and non-goals | Required | State the concrete problem, technical constraint, or opportunity backed by actual observations or cited records. Define measurable goals and acceptance signals that would show the design succeeds, alongside explicit non-goals and out-of-scope boundaries to bound review scope. |
| Proposed technical design | Required | Explain the proposed solution at reviewable engineering depth: major components, interface or protocol changes, data model and ownership effects, state transitions, error or failure semantics, and core invariants. Keep build-to implementation minutiae outside the RFC while providing enough concrete detail to evaluate feasibility and compatibility. |
| Alternatives considered and tradeoffs | Required | Document credible alternatives actually evaluated—including maintaining the status quo when credible—explaining key tradeoffs, complexity, and why the proposed design is preferred. Cite a trade study report or technical analysis report by edition and locator when quantitative scoring or experiments support the comparison. |
| Cross-cutting impacts, migration, and risks | Required | Assess material impacts across security, privacy, reliability, performance, backward compatibility, observability, operational effort, and cost, marking any unexamined area as `not-assessed` and an assessed absence of effect explicitly. Define phased rollout or migration steps, version coexistence or feature-flag safeguards, known risks, and rollback or reversal boundaries including irreversible state changes. |
| Open questions, review feedback, and disposition | Required | Track unresolved design questions and material reviewer objections with explicit states (`open`, `resolved`, `deferred`, or `accepted-risk`) and resolution rationale. Record the actual disposition (`accepted`, `rejected`, `deferred`, `withdrawn`, or `superseded`) only with the deciding authority, date, conditions, and required downstream handoff (such as authoring an architecture decision record, change request, or implementation plan), keeping proposal acceptance separate from completed implementation. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
| --- | --- | --- |
| Proposal identity and state | Exactly one stable proposal identifier and one current lifecycle state in Proposal identity, state, and review process. | Use `draft`, `in-review`, `final-comment`, `accepted`, `rejected`, `deferred`, `withdrawn`, or `superseded`. `accepted` and `rejected` require actual recorded disposition from the declared authority; `superseded` names the replacing proposal or decision record; `withdrawn` names the withdrawing author and date. |
| Goal and non-goal | One or more concrete goals and one or more explicit non-goals in Motivation, goals, and non-goals. | Distinguish desired outcomes from intentional scope boundaries so reviewers do not conflate excluded work with unaddressed defects. |
| Proposed design element | One or more affected components, interfaces, protocols, or invariants in Proposed technical design. | Label all described behavior as proposed until decided and implemented; cite existing baseline architecture or interface records by edition when modifying them. |
| Considered alternative | One or more credible alternatives (or an explicit statement that none was credible after assessment) in Alternatives considered and tradeoffs. | Include status quo when credible; state concrete tradeoffs rather than straw-man dismissals. |
| Cross-cutting impact assessment | One explicit assessment covering security, privacy, reliability, performance, compatibility, operations, and cost in Cross-cutting impacts, migration, and risks. | Distinguish assessed impact, assessed no-impact, and `not-assessed`. Cite controlling threat models, DPIAs, or SLO specifications when they exist or identify required follow-up assessments. |
| Migration and rollback plan | One rollout and reversal disposition in Cross-cutting impacts, migration, and risks. | Specify coexistence constraints, migration sequence, and reversal boundaries; if rollback is unavailable or lossy, state that limit and its mitigation explicitly. |
| Open question or objection | Zero or more tracked design questions or reviewer objections in Open questions, review feedback, and disposition. | Assign state (`open`, `resolved`, `deferred`, or `accepted-risk`), owner when known, and resolution basis. Blocking `open` items prevent `accepted` disposition unless explicitly waived by the decision authority. |
| Disposition and downstream handoff | Zero until decided; one actual disposition account in Open questions, review feedback, and disposition once decided. | Name deciding authority, date, scope, conditions, and downstream records to create or update (such as an ADR or change request). Preserve rejected or withdrawn proposals with rationale rather than deleting debate history. |

Use structured prose for motivation, design narrative, and tradeoffs, diagrams for architecture or sequence changes when topology matters, and compact tables for alternative comparisons, cross-cutting impact dimensions, and tracked open questions or objections. Link external review threads or prototype branches by locator without copying raw comment transcripts wholesale. Do not insert blank objection rows, invented approvals, or unverified benchmark numbers.

## Quality criteria

- Proposal identity, authors, affected teams, lifecycle state, review rules, and deciding authority are explicit, and silence or review expiry is never presented as acceptance.
- Motivation rests on concrete evidence, and goals and non-goals establish clear review boundaries.
- Proposed design detail is concrete enough to evaluate interfaces, invariants, failure behavior, and feasibility without degenerating into low-level code documentation.
- Credible alternatives—including doing nothing when credible—and material tradeoffs remain visible in the rationale.
- Cross-cutting impacts distinguish assessed effects, assessed no-impact, and `not-assessed` dimensions; migration steps and irreversible rollback limits are explicit.
- Open questions and material reviewer objections retain visible states and resolution bases; final disposition cites actual authority, conditions, and downstream handoff without conflating acceptance with implementation.
