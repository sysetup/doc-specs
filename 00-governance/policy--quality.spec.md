# Quality policy specification

## Identity and selection

- **Specification ID:** `POLICY@quality`.
- **Purpose:** Establish mandatory direction for product or service quality, impartial assurance, and the control of nonconforming outputs.
- **Intended readers:** People who create, assess, release, deliver, or oversee the covered products or services, and the policy's issuing authority.
- **Decision or action supported:** Readers can determine the quality obligations that apply, who may make assurance and disposition decisions, and how a suspected nonconforming output is controlled and escalated.
- **Use when:** An issuing authority needs organization or project-wide quality obligations for a defined product or service scope.

## Authoring inputs and unresolved facts

Obtain the actual issuing mandate and the products or services, lifecycle stages, suppliers or other parties, and people within scope. For the subjects in scope, obtain supplied project requirements and quality objectives, their established project basis, and requirement or acceptance authorities; the assurance and release decision rights and any independence obligations; and how nonconforming outputs are identified, controlled, dispositioned, and escalated. Obtain the policy owner, exception authority, communication route, and review triggers, and the policy edition, issuance state, and effective-date decision when established.

If an authority, quality objective, assurance boundary, or disposition right is unknown or not established, state the gap, its effect on the proposed obligation, the resolving action, and an actual owner if assigned. A draft without established authority, scope, or substantive obligations MUST remain visibly proposed and MUST NOT claim to be effective. Do not invent quality results, approvals, or product acceptance.

Normally all three named quality subjects are covered. A subject may be excluded only where it is genuinely inapplicable to the stated product or service scope within the issuing mandate. For each exclusion, record the subject, exact excluded scope, reason, actual issuing authority, explicit disposition, and decision date or locator. A pending disposition does not remove a subject or reduce its obligations; the policy MUST remain proposed until that disposition is established. Only an approved exclusion of an entire named subject reduces the coverage and directive minimum; a partial exclusion leaves that subject in scope. At least one named subject and substantive mandatory direction MUST remain. If all subjects are excluded, keep the document proposed and resolve its mandate and scope before issuance.

## Finished-document contract

- **Title:** Identify the covered organization, project, product, or service as needed and name the document as a quality policy.
- **Frontmatter:** None. Begin with the GFM title. Authority, applicability, and policy state belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Establish authority and applicability before quality obligations, then decision rights and exception rules, then communication and review. Headings may use local wording if these roles remain clear.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Authority, purpose, and applicability | Required | Identify the real issuing authority or mark it proposed; policy owner, unambiguous edition, truthful issuance state, covered outputs and people, organizational and lifecycle boundaries, material exclusions, and effective date only when decided. State the desired quality outcome and the established project basis for the obligations. |
| Mandatory quality direction | Required; subject coverage follows the approved exclusions defined above | State separately identifiable obligations for **product or service quality**, **assurance independence**, and **nonconforming outputs** wherever each subject remains in scope. For those subjects, respectively govern how supplied project requirements and quality objectives are established or used before conformance or release decisions; what impartiality or independence is required for consequential assessment and approval; and how a suspected or confirmed nonconforming output is identified, controlled against unintended use or delivery, evaluated, dispositioned, and escalated. When nonconforming outputs are covered, require treatment after delivery when the scope can encounter it. |
| Quality authority and decisions | Required | For the subjects in scope, identify who applies quality obligations, who assesses or provides assurance, who may authorize release or disposition, and how conflicts of interest or disagreements are escalated. Where assessment, concession, or release decisions are covered, define how an assurance recommendation informs the decision, who may make it, and what evidence is required to determine whether the output meets its stated requirements and quality objectives. |
| Exceptions and noncompliance | Required | State whether policy exceptions are permitted. If permitted, define decision authority, request basis and quality consequence, scope and duration or review condition, how the decision is recorded, and treatment while pending. If prohibited, state the conflict route. Explain how suspected failure to follow the policy is reported and addressed; a product concession MUST NOT silently waive a policy obligation or established project requirement. |
| Communication, oversight, and policy review | Required | State how obligations and changes reach affected roles, what assurance or nonconformity information within scope the responsible authority receives, how material trends or failures are escalated, and when and by whom the policy is reviewed and changed. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Issuing authority and policy owner | One issuing body or delegated role and one accountable maintenance role. | A proposed issuer is labeled proposed; an assurance or release role does not automatically have policy-issuing authority. |
| Applicability and quality basis | One scoped statement of covered outputs, parties, lifecycle boundary, and material exclusions; supplied project requirements or acceptance basis identified where they govern decisions. | State how the project basis is selected or authorized. Do not invent product-specific criteria or bind an external party without real authority. |
| Issuance state and edition | One truthful state and unambiguous edition; effective date conditional on an actual decision. | Distinguish proposed, authorized but not yet effective, effective, and withdrawn or superseded in the project's terms. |
| Quality directive | Normally three or more distinct obligations, with at least one for each named subject. Subtract one from this minimum for each approved whole-subject exclusion; retain at least one distinct obligation per remaining subject. | Give each a stable local label, addressee, mandatory action or constraint, and applicable condition. Count a directive only once even if it covers several subjects; such coverage does not reduce the distinct-obligation minimum. Subject labels, exclusions, unresolved gaps, and aspirations do not count. |
| Assurance independence rule | When assurance independence remains in scope, at least one obligation defining the required impartiality and decision separation for the covered work. | State who sets the needed degree of independence and how a conflict or unavailable independent assessor is escalated. Allow the organizational structure to suit the actual scope. |
| Nonconforming-output rule | When nonconforming outputs remain in scope, at least one obligation for identification, control, evaluation, authorized disposition, and escalation. | Define who may decide release, rework, rejection, or permitted concession as applicable. An unapproved deviation or undocumented rework is not acceptance. Address affected recipients when a post-delivery discovery requires action. Define the scope of a concession explicitly; changes to established project requirements, policy exceptions, and acceptance of residual risk require their own authorized decisions. |
| Exception rule | One policy-exception allowance or prohibition. | For permitted policy exceptions, define authority and conditions, decision recording, and treatment while pending; for prohibited exceptions, define the conflict route. When product disposition is within the approved subject scope, define its authority and conditions separately. A policy exception MUST NOT authorize a product disposition outside that scope or the issuing mandate. |

Use concise prose and numbered directives. A compact responsibility or decision table MAY clarify distinct assurance, disposition, and release authorities. A short flow MAY clarify the policy-level escalation for nonconforming outputs.

## Quality criteria

- All three quality subjects are covered unless an explicit issuer-approved exclusion removes a subject for the stated scope. Every exclusion has its scoped reason and decision identity; pending decisions and empty governed scope prevent issuance. The distinct-directive minimum matches the remaining subjects without counting exclusions or gaps.
- Subjects in scope have obligations with clear actors; requirements, assurance, disposition, and release rights within that scope do not contradict one another.
- Where assurance independence is covered, it is defined for the actual scope, including conflict escalation, without assuming a universal staffing model.
- Where nonconforming outputs are covered, a reader can prevent unintended use or delivery and identify who may authorize each relevant disposition. A concession, release, or policy exception is never inferred from a request or assessment.
- Each directive states mandatory quality direction with a clear project basis and decision authority.
