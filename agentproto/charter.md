# Agent Communication Protocols (agentproto) Proposed Charter

An AI agent is an autonomous, adaptive software system that uses AI models to complete a specific task on behalf of a human user, another AI agent, or an invoking system. AI agents interact with users and other agents through multiple modalities, including voice, video, and text, and are capable of independent decision-making, tool invocation, and task completion.

User-to-agent, agent-to-agent, and agent-to-tool interactions create dialogs between the users, agents, and tools. For all the interactions, there are common protocol requirements to ensure the correlation and maintenance of the created dialogs and the propagation of dialog context between the participants. The dialog context refers to the protocol-level metadata that enables the continuity and correlation of an agentic dialog, which is not the application-level data such as memory or other information that is fed into AI models.

The scope of Agent Communication Protocols (agentproto) Working Group is to define a common baseline agentic dialog management protocol and build a reference architecture to integrate related protocol building blocks, enabling interoperability across platforms and vendors.

The agentic dialog management protocol neither replaces application-layer agent communication protocols nor defines a new transport protocol. It defines dialog identifiers, lifecycle semantics, and the propagation of dialog context, together with bindings specifying how that context is carried over existing IETF protocols. A dialog context is defined independently of an application design: an application participant that understands it can correlate and maintain a dialog without the protocol constraining how the application is structured or what content it exchanges.

# Key Considerations

There are several considerations that are unique to AI agent applications that need to be addressed while working on developing the building blocks:

- AI agents act as autonomous software entities that may need to be authenticated independently of the users they represent. Establishing verifiable agent identity that is distinct from user identity enables independent revocation of agent access, scoping of agent permissions to a subset of user permissions, and auditability of agent-initiated actions distinct from user-initiated actions.

- Dialog between AI Agents and users, other AI Agents, and tools can be long-lived; and they depend on critical dialog context across various modalities (text, audio, video).  Some agentic dialogs, such as those involving interactive voice, require very low latency, including support for fast barge-in (a voice technology feature that allows a user to immediately interrupt an AI voice agent or automated system while it is talking, causing the system to stop playback instantly) and smooth interruption handling. Dialog context may need to be propagated and remain coherent across multiple intermediaries, and trust boundaries over time. This introduces new considerations around dialog correlation, reliability, transport session management, and data transport.

- To protect data exchanged between AI agents and users, other AI agents, and tools over potentially untrusted networks, particularly when handling sensitive information (such as personal data within dialog context), mechanisms are required to establish and verify identity of agents and of the users on whose behalf they act, ensure confidentiality, integrity, authenticity of the exchanged data, and delegated authorization across AI agent chains. This introduces new considerations around protocol-level security and privacy mechanisms.

# Deliverables

The working group will produce the following standards-track and informational documents. The work on these deliverables is expected to proceed in parallel.

## Agentic Dialog Management Protocol (Standards Track)

A Standards Track protocol for the propagation of dialog context across *multiple* intermediaries, trust boundaries, and transformation of modalities, enabling interoperable *agentic dialogs*. This protocol serves as a foundation for dialog continuity and correlation in user-to-agent, agent-to-agent, and agent-to-tool interactions, enabling dialog continuity when a participant changes device or network attachment, or when a dialog resumes after an interruption.

The specification will define:

* Dialog management primitives to:

    - Correlate dialogs, enabling agents to associate related interactions across multiple hops, trust boundaries, and over time.
    - Manage full dialog lifecycle, including establishment, modification, termination, and revocation of propagation relationships.
    - Provide scalable and resilient operation with recovery from failures of network paths and intermediaries, and handle unreachability.

* Transport bindings: specifying how the dialog context with its associated metadata are carried over one or more existing IETF protocols, such as HTTP, QUIC, WebTransport, WebRTC or MOQ, based on the anticipated use cases.

The agentic dialog management protocol may be bound to more than one underlying IETF protocol. The WG will describe a set of evaluation criteria used to select which bindings to specify.

The working group will analyze the privacy implications of dialog correlation and specify mitigations.

Because dialog identifiers may persist across intermediaries and trust boundaries, the working group will analyze the privacy implications of dialog correlation and specify mitigations.

The protocol is designed to be usable by existing application-layer agent communication protocols (e.g., MCP and A2A maintained by the Linux Foundation) through well-defined extension points, rather than replacing them.

## Reference Architecture (Informational)

To ensure interoperability in agent communications, this informational document describes related protocol building blocks that the agentic dialog management protocol can reuse, including identity, authentication, authorization, and encryption, rather than defining new ones. This reference architecture will:

* Define the terms used by the protocol deliverable.
* Describe the functional blocks the protocol deliverable assumes, and their relationships.

## Use Cases and Requirements (Informational)
* Describe basic use cases and requirements that drive the protocol deliverable. The deliverable will also describe the deployment model(s).

# Coordination

This working group is expected to closely coordinate with other related IETF working groups on dependencies of the reference architecture and the agentic dialog management protocol, including security, transport, and discovery aspects:

* **Security:** Web Authorization Protocol (OAuth), webbotauth, WIMSE - on identity, authorization, and security considerations.
* **Transport:** WebTransport, MoQ, QUIC, TSVWG, httpbis - on data transport.
* **Discovery and Operations:** INT area, OPS area - on agent discovery and operational considerations.
* **Evidence and transparency:** SCITT, RATS, on software and hardware security.
* **Conversational data:** vCon - on conversation representation and its relationship to dialog context.

If the agentproto WG identifies any gaps in protocols specified by other active WGs, those gaps will be raised with the relevant WGs for decisions on how best to handle them, which may include the work being carried out in that WG or, with its agreement, in agentproto WG.

The working group will also coordinate with relevant standards and open source efforts outside the IETF to understand deployed practice and avoid unnecessary divergence.

# Out of Scope

The following topics are explicitly out of scope for this working group:

- Implementation details of AI agents, including definition of AI models, backend AI infrastructure network and protocols, agent reasoning algorithms, or tool-specific business logic.

- Standardization of agent behavior, decision-making, or planning semantics.

- AI agent behavioral security (e.g., preventing the AI model itself from hallucinating, though mitigating the impact of hallucinations via protocol-level user confirmation is in scope).

- The design of human to agent user interfaces, client application UX, or the rendering of agent outputs on end-user devices
