Authenticated Transfer Protocol (ATP) Working Group
===================================================

The Authenticated Transfer Protocol (ATP) working group will develop a set of Standards Track specifications that enable creation of decentralized global networks for publication of self-certifying data.

See RFC 9518 for additional context on why decentralization matters.
Data is published by accounts in data repositories. An account represents the identity of a user, can migrate between hosting locations over time, and is identified by a persistent globally-resolvable account identifier.
The network comprises independent hosts and other participants that synchronize public data across organizational boundaries, while preserving authenticity of content and attribution to the accounts that published the content.
The network will give small independent participants global visibility and distribution without prior coordination, and will not depend on the existence of any single privileged entity.

The work will be based on draft-holmgren-at-repository and the pre-standardization implementation and deployment experience of multiple parties in the ATP ecosystem. 
Proposed changes to the existing approach must be weighed against their impact on deployed implementations.

The working group will focus on a general purpose data repository structure for public user data records, and mechanisms for synchronizing repositories across the network. 
Repositories are cryptographically verifiable and publicly published.

Cryptographic verification ensures existential unforgeability (EUF-CMA) of repository data, preventing injection of falsified content, signature transplantation, and unauthorized modifications by requiring resolution of account identifiers to current signing keys. 
Account identifiers are also used to resolve the current hosting location and must support bidirectional authorization: identifiers must resolve uniquely to specifications of allowed signing keys, and those keys must provide cryptographic commitment to the account identifier to prevent adversarial impersonation. 
Account identifiers should be globally resolvable and persist across hosting migrations. 
The working group will specify interface requirements and selection criteria for account identifier systems. 
To ensure broad interoperability, the working group will create a list indicating which identifier systems are recommended as a baseline, and a process for updating that list over time. 
Backwards compatibility will be maintained for the two account identifier systems supported in the currently deployed network (PLC and did:web).

Deliverables for the working group:

- Standards track document(s) describing a repository data structure, an encoding format for structured data records (CBOR and JSON representations), and an export format for transfer of data repositories
- Standards track document(s) describing a low-latency synchronization protocol
- Standards track document(s) describing a URI scheme ('at:') for persistent references between data records
- Document(s) describing interface requirements and selection criteria for account identifier resolution systems, and defining a public registry and update process for recommending specific account identifier resolution systems
- Document(s) describing operational considerations for deployment and interoperability testing.

Key goals for ATP are:

- The synchronization protocol should include notification of data deletion
- The synchronization protocol should allow for alternative transport layers, and not be overly fit to the current WebSocket transport layer.
- The synchronization protocol should require that the server is authenticated and that the traffic is confidential
- Scale to global network applications
- Support for redistribution of authenticated data via multiple layers of intermediary parties
- Account migration between network locations (eg, hosting providers) does not break references or graph relationships

The following are out of scope for the working group:

- Transfer of non-public or limited-visibility data
- Any application-specific data schemas
- Any social application semantics

The ATP working group will consult the Crypto Forum Research Group (CFRG) and Security Area groups concerning the use and selection of any cryptographic systems. Likewise, the WG will leverage (and liaise as appropriate) with HAPPY WG for transport selection matters.
Privacy and Centralization per RFC 6973 and RFC 9518 will inform design decisions.