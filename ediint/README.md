# EDIINT Working Group Charter

The EDIINT Working Group is chartered to update and modernize the mechanisms defined in RFC 4130 (AS2 – Applicability Statement 2) to reflect advances in Internet transport security, messaging reliability, and interoperability practices, while maintaining backward compatibility with existing implementations where practical.

## Background

The original EDIINT Working Group developed protocols enabling secure and reliable business data interchange over the Internet, including AS1, AS2, and AS3. These technologies have been widely adopted in global commerce. Despite the availability of alternative technologies such as RESTful interfaces over HTTPS, AS2 remains foundational in numerous production environments and industry frameworks. Many sectors continue to depend on AS2 due to its proven reliability, strong authentication and non-repudiation capabilities, and established certification and compliance ecosystems. This update focuses on modernizing AS2 to maintain its operational relevance and interoperability in today's Internet environment.

## Goals and Scope

The Working Group will:

1. **Modernize RFC 4130 (AS2):**

- Align with current Internet and security practices (e.g., TLS 1.3, modern cipher suites, certificate validation, MIME updates).
- Replace outdated dependencies with references to current standards and best practices.
- Improve clarity in message structure, signatures, receipts, and error handling.

2. **Clarify Backward Compatibility Expectations:**

- Define guidance to ensure existing AS2 deployments continue operating without disruption, while recognizing that some legacy mechanisms—whether cryptographic, transport, configuration, or feature-related—may not interoperate with updated implementations.
- Clarify that backward compatibility focuses on preserving operational continuity and migration pathways, not guaranteeing interoperability across all legacy features or security levels.
- Where older algorithms or mechanisms are retained solely for compatibility, they will be designated as "MAY implement", while secure and modern alternatives will be specified as "MUST implement".

3. **Clarify and Extend Functionality:**

- Incorporate operational experience and lessons from two decades of AS2 deployment.
- Address implementation ambiguities, interoperability challenges, and deployment best practices.
- Consider optional, informational extensions that improve operational usability or integration without redefining AS2 as a new protocol.

4. **Deliverables**

- A standards-track document updating RFC 4130 ("RFC 4130bis").
- Optional informational drafts describing interoperability and transition strategies, covering best practices and implementation profiles.

## Out of Scope

- Development of new EDI or transport protocols (e.g., REST/HTTPS-based EDI messaging).
- Changes that break compatibility with existing AS2 deployments beyond what is required for security or standards alignment.

## Milestones

- **WG Adoption of RFC 4130bis draft as Proposed Standard**: Initial working group draft (Q2 2026)
- **WG Last Call**: Consensus on updates and backward compatibility sections (Q4 2026)
- **IETF Last Call / Publication Request**: Submission to IESG for publication (Q2 2027)
