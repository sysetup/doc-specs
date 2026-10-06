# Support and request-routing guide specification

## Identity and selection

- **Specification ID:** `SUPPORT-GUIDE@core`.
- **Purpose:** Direct recipients to established help, defect, improvement, and security-reporting routes.
- **Intended readers:** Supported users, integrators, contributors, and support recipients.
- **Decision or action supported:** Choose the correct request channel and provide useful information within privacy and support boundaries.
- **Use when:** A product or service needs a recipient-facing support entrypoint.
- **Scope boundaries:** Describe request entry routes and supported scope; exclude internal support staffing plans, fulfillment procedures, invented response commitments, and public disclosure of sensitive reports.

## Authoring inputs and unresolved facts

Inspect the supported subject, versions or populations, actual help, defect, improvement, and private security channels, required intake information, supported hours or languages when established, response expectations and their authority, privacy restrictions, self-help resources, and maintenance responsibility.

Expose unknown supported versions, channel, response expectation, privacy condition, or owner with consequence and resolving action. An absent route cannot be presented as available, and no response guarantee may be inferred. Missing private security routing prevents instructions to submit sensitive content to a public channel. Do not collect secrets or invent contacts, support promises, or resolutions.

## Finished-document contract

- **Title:** Identify the supported subject and name its support and request-routing guide.
- **Frontmatter:** None. Begin with the GFM title. Identity, scope, and state belong in the body.
- **Client or receiving party:** Conditional body element in the identity or scope section. Include it only when a named external party commissions or receives the work; then state that party's established name and relationship, such as client or receiving organization. When no external party exists, state that the document has no external client. Do not invent a party. Do not put the party in the specification ID, filename, or type name.
- **Order:** State supported scope before request choices; put channel and intake information before expectations, privacy limits, and upkeep. Heading wording may vary.

| Section role | Status and inclusion condition | Content obligation |
|---|---|---|
| Supported scope and audience | Required | Identify product or service, supported versions and recipients or explicit gaps, support boundary, actual hours or language coverage when established, exclusions, and client or receiving-party element. |
| Request classification and routes | Required | Explain how to distinguish ordinary help, suspected defects, improvement or feedback, and security matters. Give established channels or visible gaps, actual self-help resources, and escalation route when supplied; sensitive security reports require an established private route. |
| Useful intake information | Required | State the context, version, observed versus expected behavior, reproducible details, and requested outcome useful for each applicable route. Instruct readers to redact credentials, personal data, and private infrastructure details and to use permitted attachments or secure sharing only when established. |
| Response expectations and limits | Required | State actual response or support commitments with source and scope, or that no guarantee is established. Distinguish acknowledgment, triage, treatment, and resolution; provide status or follow-up routes only when real. |
| Privacy and upkeep | Required | Explain relevant disclosure and retention limits for recipient submissions, avoid unsupported confidentiality claims, and identify update ownership or gap and triggers from version, support, or channel changes. |

## Content definitions and forms

| Element | Meaning and cardinality | Constraint |
|---|---|---|
| Support boundary | Exactly one bounded subject and audience account in Supported scope and audience. | Supported and unsupported versions are sourced; unknown support is not a supported promise. |
| Request route | One route or explicit unavailable-route statement for each relevant request class in Request classification and routes. | Use actual reachable destinations; public issue trackers cannot be substituted for unknown private security routes. |
| Intake field | Zero or more minimized fields per route in Useful intake information. | Require only useful context and placeholders; no secret value is requested. |
| Response expectation | Exactly one commitment or no-established-guarantee account in Response expectations and limits. | Bind hours and response expectations to actual authority; acknowledgment is not resolution. |
| Disclosure and maintenance basis | Exactly one account in Privacy and upkeep. | Describe only established protections, sharing limits, and update responsibility; do not claim anonymity or continuous monitoring without evidence. |

Use a short channel-selection table and route-specific intake lists. Link actual product guidance, contributor instructions, and security policies rather than reproducing internal response plans. This guide controls recipient entry; downstream support, feedback, defect, and incident records control their dispositions.

## Quality criteria

- Supported subject, versions, recipients, and hours reflect actual scope or explicit gaps.
- Request classes point to real routes, and sensitive security submissions have a private route or a clear unavailability statement.
- Intake asks for useful minimized context and prohibits submitting secret values.
- Response expectations distinguish acknowledgment and resolution and never create unsupported commitments.
- Privacy limits, source links, ownership, and update triggers preserve the actual support arrangements.
