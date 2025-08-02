# Introduction & Background

Open Cloud Mesh (OCM) is a server-to-server protocol designed to enable
federation between Enterprise File Sync and Share (EFSS) platforms.
Initially conceived of in 2015 and deployed since 2016, OCM has been
implemented by several major vendors, including Cernbox, Nextcloud,
OpenCloud, ownCloud, and Seafile.

A core use case of OCM is when a user (e.g., Alice on System A) wishes
to share a resource with another user (e.g., Bob on System B) without
transferring the file itself or requiring cross-authentication. While
this scenario is illustrative, OCM is designed to support a broader
range of interactions, including but not limited to file transfers.

OCM defines the exchange up to the point where other established
protocols such as WebDAV or JMAP can take over. This layered design
makes OCM flexible and agnostic to the underlying data exchange
mechanisms, enabling seamless integration between diverse systems.

## Motivations

Many Internet protocols require metadata exchange such as
authentication tokens, API endpoints, or identifiers before any useful
interaction can occur. OCM facilitates such metadata exchange between
servers, making it a valuable tool for federation. In addition, it
enables users on federated systems to connect via an invite mechanism
that can leverage trusted out-of-band networks to initiate
server-to-server contact.

## High-Level Outcome

The working group will deliver a specification that enables users on
federated servers to interact, and enables the servers to exchange the
necessary metadata required for resource federation.

# Scope

The basis for the working group's efforts is the current [Open Cloud
Mesh Internet-Draft](https://datatracker.ietf.org/doc/draft-lopresti-open-cloud-mesh/).

This draft outlines the general flows and structure of the protocol,
but further work is required particularly around security
considerations that will benefit from the IETF community’s broader
review and input.

The working group will **not** define new data transfer protocols or
mechanisms unrelated to server-to-server federation and metadata
exchange. Instead, established protocols such as WebDAV will be used
for actual data transfer.

OCM does not aim to address identity federation (e.g., OIDC or SAML);
rather, it leverages existing protocols for identity and authentication
where appropriate.

Importantly, OCM is **not** a competitor to user-oriented messaging or
social protocols like ActivityPub or Matrix federation, but addresses
different use cases focused on content federation and metadata
exchange.

# Deliverables

The working group will deliver one or more Internet-Drafts describing
the OCM protocol, suitable for publication as standards-track RFCs.

Depending on how the protocol evolves, it may be appropriate to
separate its functionality into multiple drafts e.g., invitations,
notifications, and sharing while other elements such as discovery,
capabilities, and restrictions could be documented in a core
specification. Alternatively, all functionality may be maintained in a
single document.

Given that the protocol is already deployed and a working draft exists,
we believe that the group can progress relatively quickly. However, we
welcome and seek thorough input from the IETF community to ensure that
the final specification is secure, robust, and maintainable. There is
no intention to rush publication of an incomplete or underdeveloped
standard.

