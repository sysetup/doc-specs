# Cybersecurity incident response plan specification

## Identity and selection

- **Specification ID:** `INCIDENT-RESPONSE-PLAN@core`.
- **Purpose:** Define, before a cybersecurity incident, the response governance, roles, severity and escalation, communications, evidence handling, recovery interfaces, and exercise of that capability.
- **Intended readers:** Incident-response owners, security and operations leads, service owners, legal and communications roles when they apply, and teams that receive recovery or continuity handoffs.
- **Decision or action supported:** Establish who may declare and direct response, how events are classified and escalated, which capabilities must be ready, and how response coordinates with detailed methods, system recovery, and business continuity.
- **Use when:** An organization or defined scope needs cybersecurity incident preparedness.
- **Scope boundaries:** Cover preparedness and coordination for suspected or confirmed cybersecurity incidents within the identified services, assets, and suppliers. Ordinary vulnerability handling before suspected exploitation is outside this response scope.

## Authoring inputs and unresolved facts

Obtain the services, assets, suppliers, and supplied service or response commitments in scope; incident-command, declaration, escalation, communication, and response decision roles; severity criteria; staffing, training expectations, tools, contact reachability, and recovery-resource access; detection and analysis responsibilities; evidence-preservation and retention needs; containment and communication coordination; restoration criteria and any interfaces to system recovery and business continuity; and the exercise and review method. For each reporting commitment, obtain its recipient, trigger, deadline, project decision or supplied agreement, and responsible role. Identify any existing response procedures or incident-information records used in coordination by their location and version.

If a decision role, severity threshold, capability, reporting commitment, or restoration criterion is unknown or not established, state the gap, its response consequence, the resolving action, and the actual owner if assigned. Do not invent incident facts, recipients, deadlines, completed training, or approvals. Identify required operational permissions and the route for obtaining them before a response action is performed.

## Finished-document contract

- **Title:** Identify the organization or scope and name its cybersecurity incident response plan.
- **Frontmatter:** None. Begin with the GFM title; authority, scope, and severity rules belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** Establish scope and authority before detection and coordination; put recovery interfaces before exercise and improvement. Heading wording may vary. Section roles are planning duties.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Scope, authority, and readiness | Required | Define covered services, assets, suppliers, exclusions, and plan objectives. State supplied service and response commitments and their boundaries. Identify incident command and the distinct rights to declare an incident, escalate, communicate, and authorize response, including required operational permissions and their approving roles. State the staffing, coverage, training expectation, tools, contact reachability, and recovery-resource access the plan relies on, including gaps. |
| Detection and escalation | Required | Assign identification, classification, prioritization, and analysis responsibilities. Define the project's severity or priority levels, keep a suspected incident distinct from a confirmed one, and state escalation thresholds and the route when classification is uncertain. |
| Response coordination | Required | Plan coordination of investigation, evidence preservation, and containment, including who decides a disruptive action and how service or safety tradeoffs are raised. Define internal communication routes and the authority for external communication. State established reporting recipients, triggers, deadlines, and responsible roles. Identify the coordination points with existing response procedures, the information they need, and the escalation route when a required method is unavailable. |
| Recovery interfaces | Required | State restoration criteria at planning depth and how cybersecurity recovery coordinates with business continuity and information-system recovery arrangements within the response scope. Define restoration checks, the evidence needed for a later restored-service acceptance decision, the deciding role, and coordination with controlled operational procedures. |
| Evidence handling rules | Required | Define retention periods or selection criteria, authorized access, observation origin and collection context, integrity preservation, and handling of incident records and artifacts. State the reason for each sensitivity restriction and identify any unresolved handling need. |
| Exercise, learning, and plan maintenance | Required | Plan how the response capability will be exercised, which effectiveness measures will be used, and how lessons and improvements will be captured after a real event. State review triggers or frequency and the route for changing the plan. Include the internal approval route when the project requires it, with the deciding role and required information. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Response scope | One bounded organizational or system set. | Name inclusions, exclusions, suppliers, and supplied service or response commitments. |
| Decision right | One or more distinct authorities for command, declaration, escalation, communication, and disruptive or recovery action. | Name the role and its limit. Do not collapse different rights into one unnamed responder. |
| Severity level | One or more project-defined levels used to prioritize response. | State the observable conditions, expected escalation, and deciding role. |
| Readiness item | The staffing, training, tools, contacts, and recovery access the plan relies on. | Mark each as available, limited, or not established, with the limitation or gap affecting response. |
| Coordination handoff | Each material handoff to a response-method owner, business-continuity role, or system-recovery role. | Identify the trigger, receiving role, and information transferred. Where no such arrangement is in scope, say so instead of implying one. |
| Restoration criterion | One or more checks before restored service is offered for an acceptance decision. | Cover integrity and essential function at the plan's level of detail and specify the evidence required by the deciding role. |
| Evidence rule | One handling rule, with stricter controls where sensitivity or investigative use requires them. | State what is retained, who may access it, and the observation origin and collection context to preserve. Do not place secrets or raw incident data in the plan. |
| Exercise and review rule | One method for practicing and updating the plan. | Cover objectives, participants, records a later exercise would keep, measures, and the improvement route after a real incident. |

Use prose for authority, a severity table when levels differ, and a short handoff table for response-method, continuity, and system-recovery interfaces. Do not include incident timelines, indicator lists from past events, blank forms, or generic document-control metadata.

## Quality criteria

- Declaration, escalation, external communication, and disruptive action each have a responsible role or an explicit unresolved gap.
- Suspected and confirmed incidents stay distinct, and uncertain classification has a route.
- Response roles, readiness needs, escalation, procedure interfaces, and recovery coordination are explicit at planning depth.
- Reporting recipients, triggers, deadlines, and approval routes have an identified project commitment or internal decision and responsible role.
- Readiness states identify actual availability and gaps; exercises, notifications, restoration checks, and acceptance decisions identify the future actions, evidence, and decision roles needed.
