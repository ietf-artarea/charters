# Agent Communication Protocols (agentproto) Proposed Charter

An AI agent is an autonomous, adaptive intelligent software system that uses AI models to complete a specific task on behalf of a human user or another AI agent. AI Agents often interact with users and other agents through multiple modalities, including voice, video, and text, and are capable of independent decision-making, tool invocation, and task completion.

User-to-agent, agent-to-agent, and agent-to-tool interactions create dialogs between the participants. For all the interactions, there are common protocol requirements to ensure the correlation and maintenance of the created dialogs and the propagation of dialog context between the participants. The dialog context refers to the protocol-level metadata that enables the continuity and correlation of an agentic dialog, which is not the application-level data such as memory or other information that is fed into AI models.

The scope of Agent Communication Protocols (agentproto) Working Group is to define a common baseline agentic dialog management protocol and build a framework to integrate related protocol building blocks, enabling interoperability across platforms and vendors.

# Key Considerations

There are several considerations that are unique to AI Agent applications that need to be addressed while working on developing the building blocks:

- AI Agents act as autonomous software entities that may need to be authenticated independently of the users they represent. Establishing verifiable agent identity that is distinct from user identity enables independent revocation of agent access, scoping of agent permissions to a subset of user permissions, and auditability of agent-initiated actions distinct from user-initiated actions.

- Dialogs of AI Agents with users, other AI Agents, and tools can be long-lived, depend on critical dialog context across various modalities (text, audio, video), and require very low latency, including support for fast barge-in and smooth interruption handling. Dialog context must often be propagated and remain coherent across multiple hops, intermediaries, and trust boundaries over time. This introduces new considerations around dialogs correlation, reliability, transport session management, and data transport.

- To protect data exchanged between AI Agents (and between AI Agents and tools) over potentially untrusted networks, particularly when handling sensitive information (such as personal data within dialog context), mechanisms are required to establish and verify identity, ensure confidentiality, integrity, authenticity of the exchanged data, and delegated authorization across AI Agent chains. This introduces new considerations around protocol-level security and privacy mechanisms.

# Deliverables

The working group will produce the following standards-track and informational documents. The work on these deliverables is expected to proceed in parallel.

## Agentic Dialog Management Protocol (Standards Track)

A standards-track protocol for the propagation of dialog context across *multiple* hops, trust boundaries and transformation of modalities, enabling interoperable *agentic dialogs*. This protocol serves as a foundation for dialog continuity and correlation in user-to-agent, agent-to-agent, and agent-to-tool interactions, allowing dialog context to follow participants as they move between devices/hosts or over time.

The specification will define:

* Dialog management primitives to:

    - Correlate dialogs, enabling agents to associate related interactions across multiple hops, trust boundaries, and over time.
    - Manage full dialog lifecycle, including establishment, modification, termination, and revocation of propagation relationships.
    - Provide scalable and resilient operation with recovery from network and server failures, and handle unreachability.

* Transport bindings: specifying how the dialog context with its associated metadata are carried over one or more modern IETF protocols, such as HTTP, QUIC, WebTransport, WebRTC or MOQ, based on the anticipated use cases.

* The working group shall describe a set of evaluation criteria for selecting one or more IETF protocols to support concrete bindings.

The protocol is designed to be usable by existing application-layer agent communication protocols (e.g., MCP and A2A maintained by the Linux Foundation) through well-defined extension points, rather than replacing them.

## Reference Architecture (Informational)

To ensure interoperability in agent communications, this informational document describes related protocol building blocks that the agentic dialog management protocol can reuse, including identity, authentication, authorization, and encryption, rather than defining new ones. This reference architecture will:

* Define the terms used by the protocol deliverable.
* Describe the functional blocks the protocol deliverable assume, and their relationships.

## Use Cases and Requirements (Informational)
* Describe basic use cases and requirements that derive the protocol deliverable.

# Coordination

This working group is expected to closely coordinate with other related IETF working groups on dependencies of the framework and the agentic dialog management protocol, including security, transport, and discovery aspects:

* **Security:** Web Authorization Protocol (OAuth), webbotauth, WIMSE - on identity, authorization, and security considerations.
* **Transport:** WebTransport, MoQ, QUIC, TSVWG, httpbis - on data transport.
* **Discovery and Operations:** INT area, OPS area - on agent discovery and operational considerations.

If the working group needs any changes to or extensions of protocols specified by other working groups, those issues will be raised with the relevant working groups for decisions on how best to handle them.


# Out of Scope

The following topics are explicitly out of scope for this working group:

- Implementation details of AI Agents, including definition of AI models, backend AI infrastructure network and protocols, agent reasoning algorithms, or tool-specific business logic.

- Standardization of agent behavior, decision-making, or planning semantics.

- AI agent behavioral security (e.g., preventing the AI model itself from hallucinating, though mitigating the impact of hallucinations via protocol-level user confirmation is in scope).

- The design of human to agent user interfaces, client application UX, or the rendering of agent outputs on end-user devices
