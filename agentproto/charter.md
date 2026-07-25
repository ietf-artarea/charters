# Agent Communication Protocols (agentproto) Proposed Charter

The Agent Communication Protocols (agentproto) Working Group will work on defining protocol building blocks for enabling interoperability for agent applications across the Internet. For the purposes of this charter, an agent is a networked software component that selects at run time which other components it will communicate with in order to carry out a task on behalf of a principal. The definition does not depend on AI models; this work is motivated by agents built on them, but must not require one.

AI agents are driving a change in how software is deployed. A task begun by one agent is decomposed and handed onward across others, operated by different parties, reached over different protocols, and chosen after the task is underway: a microservice deployment whose composition is decided at run time. Those participants have no interoperable way to establish that they are working on the same thing. Within one operator this is solved by convention, and the convention does not survive crossing trust boundaries.

# Key Considerations

There are several considerations that are unique to AI Agent applications that need to be addressed while working on developing the building blocks:

- AI Agents act as autonomous software entities that may need to be authenticated independently of the users they represent. Establishing verifiable agent identity that is distinct from user identity enables independent revocation of agent access, scoping of agent permissions to a subset of user permissions, and auditability of agent-initiated actions distinct from user-initiated actions.

- AI Agents possess unique and specialized functional capabilities which can be enhanced by collaboratively working with other agents or tools. This brings new considerations for how these specialized capabilities can be leveraged to select AI agents or tools for collaboration, initiate communication and maintain interactions, including across network boundaries.

- Interactions of AI Agents with users, other AI Agents, and tools can be long-lived, utilize significant amounts of context across various modes (text, audio, video), and require very low latency (including fast barge/interruption times). Whether existing transport and application protocols (such as MCP or A2A) already meet these requirements is a question for the gap analysis.

- To protect data exchanged between AI Agents (and between AI Agents and tools) over potentially untrusted networks, particularly when handling sensitive information (such as personal data or conversational context), mechanisms are required to establish and verify identity, ensure confidentiality, integrity, authenticity of the exchanged data, and delegated authorization across AI Agent chains. This introduces new considerations around protocol-level security and privacy mechanisms.

The scope of the working group includes agent-to-agent and agent-to-tools communication protocols. The working group will document common use-cases to derive requirements for these protocols. Human-agent communication protocols — specifically the protocol-level mechanisms for negotiating modalities and exchanging multimodal data between a human user and an AI Agent — are also in scope.

# Deliverables

The working group will produce the following standards track and informational documents. The work on these deliverables is expected to proceed in parallel.

## Interaction Reference and Binding (Standards Track)

An identifier for a unit of related activity spanning multiple agents and trust domains, with the means of proving it was legitimately bound to that activity. “Interaction” and “interaction reference” are provisional terms, expected to be replaced by the terminology deliverable below.

The specification will define:

* The reference format, and relationships between references, so an agent decomposing a task can mint one provably related to its parent for those entitled to see the relationship, and opaque to others.
* A binding envelope demonstrating that a reference was bound by a party entitled to bind it. Possession might not by itself confer authority: a reference says an operation belongs to an interaction, not that it is authorized.
* Propagation rules: what an agent does with a reference on receipt, on an onward call, on failure, and on completion.
* Linkability control, letting endpoints determine whether their activity is correlatable end to end; and revocation, including what it applies to and how it propagates where not every participant is reachable.
* How a reference anchors cryptographic context, so two non-adjacent agents can protect a subpath from the agent that brokered it. This specifies the anchor, not the key agreement.

## Carrier Bindings (Standards Track)

Specifications carrying the reference and its envelope over the protocols agent deployments already use: HTTP first, following RFC 9205, then QUIC, WebTransport, and MOQ for the streaming and multimodal cases. A protocol that already carries a correlation identifier, such as the A2A contextId, should be able to adopt these semantics in the field it already has.

## Terminology and Architecture (Informational)

A short informational document establishing the terminology used by the protocol deliverables and the minimal architectural model they assume.

This document will:

* Define the terms used by the protocol deliverables, superseding those used provisionally in this charter, including the name for the interaction concept.
* Describe the functional blocks the protocol deliverables assume, and their relationships.
* Describe how existing identity, authentication, and authorization mechanisms apply in agent deployments. Extensions to them are developed where they are owned: OAuth for authorization, WIMSE for workload identity credentials.

## Use Cases, Gap Analysis, and Requirements (Informational)

Foundational work will be documented through a set of informational Internet-Drafts covering:

* **Use cases** focused on Agent-to-agent and Agent-to-tool communications, used to verify the suitability of existing protocols and the protocols being developed.
* **Gap analysis and requirements** based on examination of existing de facto standard protocols implemented in open-source projects, from which necessary protocol requirements are derived. The absence of a demonstrated gap is itself a finding.

# Coordination

This working group is expected to closely coordinate with other related IETF working groups:

* **Security:** Web Authorization Protocol (OAuth), webbotauth, WIMSE — on identity, authorization, and security considerations.
* **Transport:** WebTransport, MoQ, QUIC, TSVWG — on data transport and the carrier bindings.
* **Discovery and Operations:** INT area, OPS area — on agent discovery and operational considerations.

If the working group needs any changes to or extensions of protocols specified by other working groups, those issues will be raised with the relevant working groups for decisions on how best to handle them. The group is also expected to maintain close communication with open-source projects running under the Linux Foundation.


# Out of Scope

The following topics are explicitly out of scope for this working group:

- Implementation details of AI Agents, including definition of AI models, backend AI infrastructure network and protocols, agent reasoning algorithms, or tool-specific business logic.

- Standardization of agent behavior, decision-making, or planning semantics, and definition of the terms “AI”, “intelligence”, or “autonomy”.

- Session lifecycle management: establishment, termination, pause and resume, turn taking, interruption, and reconnection. Existing protocols already address these; the working group will not develop a session protocol unless the gap analysis shows a requirement they cannot meet, which requires a recharter.

- Authorization semantics, delegation, and attenuation of delegated authority, which belong to OAuth and WIMSE.

- Determination of what other working groups should or should not work on.

- AI agent behavioral security (e.g., preventing the AI model itself from hallucinating, though mitigating the impact of hallucinations via protocol-level user confirmation is in scope).

- The design of human to agent user interfaces, client application UX, or the rendering of agent outputs on end-user devices
