# Project or product quality plan specification

## Identity and selection

- **Specification ID:** `QUALITY-PLAN@core`.
- **Purpose:** Plan project- or product-specific quality objectives, assurance work, resources, measures, and nonconformity decisions against an established quality basis.
- **Intended readers:** Project and product leads, quality and assurance roles, engineers, suppliers, operations or service owners, and release or acceptance decision makers.
- **Decision or action supported:** Decide what quality work must be performed, what evidence will be reviewed, and how a deficient output is contained and dispositioned before delivery or continued use.
- **Use when:** A defined project, product, service, or contract needs a coordinated quality approach across its applicable lifecycle work.
- **Scope boundaries:** Cover quality objectives, assurance work, resources, output and process controls, and planned nonconformity decisions for the defined lifecycle scope.

## Authoring inputs and unresolved facts

Obtain the specific project, product, service, and lifecycle boundary; supplied customer and technical requirements and agreed project or delivery obligations at identified editions or agreement states; product and process quality objectives and designated target-setting roles; planned design, procurement, development, production, delivery, or service work; roles and required assessor independence; people, tools, measurement resources, and supplier capabilities; inspection, test, review, and audit objects and criteria; nonconforming-output and concession rights; records and retention needs; and release or customer-acceptance interfaces.

State an unknown requirement, target, criterion, resource, or authority with its effect, resolving action, and actual owner if assigned. Mark proposed objectives and schedules as proposed. Explain when a lifecycle activity or customer-property control is inapplicable because the project has no such work, custody, or assigned property-handling responsibility. If a material objective, acceptance basis, assessment role, or disposition authority is unresolved, expose the resulting quality-decision limit. Do not invent inspection results, process capability, corrective-action effectiveness, concession, or acceptance. Describe planned checks and decisions through criteria, expected evidence, and authorization still needed.

## Finished-document contract

- **Title:** Identify the project, product, or service and name its quality plan.
- **Frontmatter:** None. Begin with the GFM title; quality scope and authority belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Establish quality basis and objectives before responsibilities and controls; place assessment before nonconformity and improvement routes. Exact headings may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Specific case and quality basis | Required | Define covered outputs, project, supplied delivery scope or service and lifecycle stages, material exclusions, customer and technical requirements and agreed project or delivery obligations with editions or agreement states, and who may set or change the quality basis. State concrete criteria and distinguish established requirements from proposed targets. |
| Quality objectives and measures | Required | State established, assessable objectives for the scope, their responsible roles, measurement or evaluation method, source of targets, timing, and escalation when an objective or target is missing or missed. Avoid unsupported universal thresholds or claims of achieved performance. |
| Organization and resources | Required | Assign process, assurance, review, nonconformity, release, and acceptance roles as applicable; state the actual impartiality or independence requirement and conflict route. Plan the people, competence, infrastructure, equipment, measurement resources, and supplier capacity needed. |
| Realization and information controls | Required | Define quality controls appropriate to actual design, procurement, development or production, delivery, and service activities. Explain how project output specifications, controlled configurations, traceability, records, and objective evidence are identified, protected, reviewed, and retained. Include customer or supplier property handling only when the project has custody or an assigned property-handling responsibility. |
| Monitoring and assurance | Required | Plan inspections, tests, reviews, and audits as applicable, with object, criterion, timing or trigger, performer, degree of independence, expected record, and the planned response when a check does not meet its criterion or cannot be concluded. Identify assessment recommendation recipients and the roles authorized to decide release or acceptance. |
| Nonconformity and corrective action | Required | Define identification, containment against unintended use or delivery, assessment of impact and affected recipients, correction or rework, the role authorized to disposition or concede a deficient output when that authority exists, the planned check that a correction meets its criterion, escalation, and a planned effectiveness review where warranted. Distinguish proposed disposition rules from established decision rights. Identify any existing concession by its actual decision record. |
| Plan review and improvement | Required | State who maintains and distributes the plan, when objectives or controls are reviewed, how changes and supplier or field feedback lead to revision, and how actual trends inform improvement. Include an approval reference only for a real decision. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Quality basis | One bounded set of project requirements and acceptance criteria, with a rule for changed inputs. | Identify the supplied requirement or decision record, edition or agreement state, output or process affected, concrete criterion, and decision authority. |
| Quality objective | One or more objectives for the covered work. | Give measurable outcome or assessable criterion, target source and status, owner, method, review point, and action if not met. Do not invent a numeric target. |
| Planned quality check | One or more checks proportionate to the actual lifecycle and risk. | Give object, criterion, timing or trigger, responsible and reviewing roles, expected evidence, and the planned response when a check does not meet its criterion or cannot be concluded. Name a formal audit only when required by a stated project decision or selected for the scope. |
| Nonconforming-output route | One route for outputs that may miss a requirement. | Identify containment, assessment, authorized options, affected-party notice when relevant, verification after correction, and retained decision evidence. Identify the actual internal assignment or supplied agreement establishing concession decision rights. |
| Property or supplier control | Conditional when property is held or supplied work is in scope. | State custody, preservation, identification, loss or damage notice, or supplier evidence and oversight rights according to actual responsibility and agreement. |
| Quality measure | One or more measures chosen to assess objectives or control effectiveness. | Define data source, unit or decision rule, collection interval, reviewer, and interpretation limits; planned measurement is not observed performance. |

Use prose for quality rationale and role boundaries, an objective-to-measure or check matrix when several outputs or stages are covered, and a decision flow when nonconformity routes are complex. Reference actual reports or records only when they exist, with their editions and locators.

## Quality criteria

- Objectives, measures, checks, and acceptance criteria relate to the stated project outputs and supplied requirement, agreement, or decision records.
- Assessment responsibility and any required independence are explicit; recommendation, concession, release, and customer acceptance have distinct authorities.
- Nonconforming outputs are controlled before disposition, and corrective action has a planned effectiveness check when the cause and risk warrant it.
- Property and supplier controls apply only where custody or agreements support them, while gaps are visible.
- Planned checks and targets state criteria and expected evidence without asserted execution results or achieved quality.
- Proposed schedules, established decision rights, and any recorded prior concessions or acceptance decisions have explicit states and actual record locators where available.
