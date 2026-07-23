# Agent Communication Protocols (agentproto) Proposed Charter

AI agents are driving a change in how software is deployed and how protocols are used.
Components increasingly select at run time which other components they will communicate with
in order to carry out a task. A task begun by one component may be decomposed and handed
onward across several others, operated by different parties, reached over different
protocols, and chosen after the task is already underway. The resulting structure is a
dynamically reconfiguring collection of services communicating point to point across a
multiprotocol mesh, spanning trust boundaries that were not known when the task began.

This pattern is not new in kind. It is the pattern of a microservice deployment, with the
composition decided at run time rather than at deployment time. What is new is the
dynamicity: the set of participants, and the boundaries crossed, are determined during the
interaction rather than in advance. Agents have made this pattern common enough, and
automatic enough, to expose a gap that closed and statically composed systems could paper
over with local convention.

The gap is that these components have no interoperable way to establish that they are
working on the same thing. Within a single operator, this is solved by convention: a trace
identifier or a stack of them is carried in the RPC protocol, usually for observability, and
it works because every participant is under common control. Across operators, protocols, and
trust boundaries, that convention does not survive. An identifier that any party can mint,
copy, or forge conveys nothing, and an identifier that conveys authority is a bearer token
with all of the attendant hazards.

The agentproto working group will define a minimal set of protocol primitives that closes
this gap: an identifier for a unit of related activity, a means of proving that identifier
was legitimately bound to that activity, rules for propagating it across components and
trust boundaries, and bindings that carry it over the protocols already in use. It will not
attempt to specify the interactions themselves.

# Terminology

This charter uses "agent" for a networked software component that selects at run time which
other components it will communicate with in order to carry out a task on behalf of a
principal. This definition is deliberately independent of how that selection is made. It
does not require the use of machine learning, and the working group will not attempt to
define "intelligence", "autonomy", or "agentic". The protocols developed here are motivated
by systems built around language models but must not depend on the presence of one.

This charter uses "interaction" for the unit of related activity that the working group's
primitives identify, and "interaction reference" for the identifier itself. **Both terms are
provisional placeholders.** Selecting the terminology this work will use is an explicit
deliverable, described below, and the working group is expected to replace these terms —
including in a revision of this charter — before the protocol documents are finished.

# Scope

In scope:

- The format and relational semantics of the interaction reference.
- The cryptographic envelope that binds a reference to an interaction.
- Rules for propagating references between agents, including across trust boundaries.
- Bindings carrying references over protocols already used for agent communication.
- Use cases, gap analysis, and requirements supporting the above.

The working group will apply existing IETF identity, authentication, and authorization
mechanisms rather than developing new ones. Where those mechanisms are found insufficient,
the required extensions will be pursued in the working groups that own them — OAuth for
authorization, WIMSE for workload identity — and not here.

# Deliverables

## Interaction Reference and Binding (Standards Track)

The core deliverable. It will specify:

* **Reference format and relational semantics.** An identifier for a unit of related
  activity spanning multiple agents and trust domains, and the relationships between
  references, such that an agent decomposing a task can mint a reference provably related
  to its parent for those entitled to observe the relationship, and opaque to those not.

* **Binding envelope.** A means of demonstrating that a reference was bound to an
  interaction by a party entitled to bind it. Possession of a reference, with or without
  its envelope, must not by itself confer authority to act. The reference states that an
  operation belongs to an interaction; it does not authorize that operation. Conflating
  these two is a known failure mode and is out of scope by construction.

* **Propagation rules.** Normative behaviour for an agent receiving a reference, making an
  onward call, encountering a failure, and completing or abandoning work — the small set of
  operations that a participating implementation must get right.

* **Linkability control.** Mechanisms allowing endpoints to determine whether their
  activity is correlatable end to end by parties along the path, and to sever that
  correlation where required. The trade-off between reduced linkability and increased local
  state is inherent, and the specification is expected to expose it rather than resolve it
  on the implementer's behalf.

* **Revocation.** What revoking a reference means, what it applies to, and how revocation
  propagates through a mesh in which not every participant is reachable or still running.

* **Anchoring of cryptographic context.** How a reference serves as an anchor from which
  two non-adjacent agents can establish protection over a subpath of the interaction,
  including where the agent that brokered their communication is not entitled to read it.
  This deliverable specifies the anchor, not the key agreement; the latter is expected to
  use existing IETF mechanisms.

The working group may divide this material across multiple documents.

## Carrier Bindings (Standards Track)

Specifications carrying the interaction reference and its envelope over the protocols agent
deployments already use. The working group will begin with a binding to HTTP, following the
guidance in RFC 9205, because it is the substrate on which the widely deployed agent
communication protocols are built and is therefore the binding most likely to see use.
Bindings to QUIC, WebTransport, and MOQ will follow, addressing the streaming and multimodal
cases that HTTP request/response serves poorly.

These bindings are deliberately designed to be adoptable by existing protocols without
restructuring them. An existing protocol that already carries a correlation identifier
should be able to adopt these semantics in the field it already has.

## Terminology and Architecture (Informational)

A single Informational document establishing the terminology used by the working group's
protocol documents and the minimal architectural model those protocols assume. It will
supersede the provisional terminology in this charter, including the working group's chosen
name for the interaction concept.

**This is intended to be a short document.** It exists to serve the protocol deliverables. It
does not describe an ecosystem, does not enumerate components the working group is not
specifying, and neither authorizes nor precludes work in any other working group.

## Use Cases, Gap Analysis, and Requirements (Informational)

Documentation of the agent-to-agent and agent-to-tool interactions motivating this work,
and an analysis of which requirements are already met by deployed protocols and which are
not. The gap analysis will examine the widely deployed agent communication protocols
developed in open source, and will treat the absence of a demonstrated gap as a finding.

# Out of Scope

The following are explicitly out of scope:

- Session lifecycle management — establishment, termination, pause and resume, turn taking,
  interruption, and reconnection. Existing transport and application protocols already
  address these, and the working group will not develop a session protocol unless the gap
  analysis identifies a requirement that existing protocols demonstrably cannot meet. Should
  it do so, that work requires a recharter.

- Authorization semantics, delegation, and the attenuation of delegated authority. These
  belong to OAuth and WIMSE. The working group will consume their output.

- Definition of agent behaviour, reasoning, planning, or decision making, and definition of
  the terms "AI", "intelligence", or "autonomy".

- Agent implementation internals, model architectures, and backend infrastructure.

- Replacement of, or competition with, existing agent communication protocols. The working
  group's output is intended to be adopted by them.

- Determination of what other working groups should or should not work on.

- Human-to-agent user interface design and the rendering of agent output.

# Coordination

The working group will coordinate with OAuth and WIMSE on identity and authorization; with
QUIC, WebTransport, MOQ, and TSVWG on the carrier bindings; and with the open source
projects developing the deployed agent communication protocols, whose adoption of this work
is the measure of its success.

Where changes to protocols owned by other working groups are required, those changes will be
raised with, and decided by, those working groups.

# Milestones

- Use cases and gap analysis adopted as working group documents.
- Terminology and architecture document adopted, establishing the working group's chosen
  terminology and superseding the provisional terms in this charter.
- Interaction reference and binding specification adopted.
- HTTP carrier binding adopted.
- Gap analysis submitted to the IESG for publication. Any session lifecycle work identified
  as necessary by the gap analysis is proposed at this point by recharter.
- Interaction reference and binding specification submitted to the IESG for publication.
- QUIC, WebTransport, and MOQ carrier bindings submitted to the IESG for publication.
