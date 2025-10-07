# Introduction & Background

Open Cloud Mesh (OCM) is a server-to-server protocol designed to enable
federation between Enterprise File Sync and Share (EFSS) platforms.
Initially conceived of in 2015 and deployed since 2016, OCM has been
implemented by several platforms, including CERNBox, Nextcloud,
OpenCloud, ownCloud, and Seafile. This working group seeks to formally
specify OCM.

A core use case of OCM is when a user with file-sharing functionality
within one administrative domain wishes to provide file access to a 
user in another administrative domain without transferring the resource itself.
When many administrative domains are involved (e.g., many universities
and research centers with cross-collaboration) it becomes hard to allow
users to log into each others' administrative domains. Instead, a 
federated system has been built to allow servers in one domain to
connect to trusted servers in other domains and make shared data 
available to their own logged-in users.

OCM defines the exchange up to the point where other established
protocols such as WebDAV or JMAP can take over. This layered design
makes OCM agnostic to the underlying data exchange
mechanisms, enabling seamless integration between diverse systems.

The OCM specification has now grown
to a level of maturity where it will be useful to converge on a set of
features in a stable specification for vendors to build to or update to.

The architectural context for OCM is therefore federated servers already
providing an interoperable interface within their individual contexts, 
but requiring share mechanisms that cross administative boundaries, using
pre-existing trust mechanisms.

# Scope

The OCM WG will produce Standards Track specification(s)
for OCM's share/invite functionality. With these 
specifications the WG will:

* Cover general flows and structure of the protocol,
* Define extensible data models for objects conveyed in the protocol,
* Explain trust decisions and how trust can be established before
resources can be securely shared,
* Describe server-to-server invitations,
* Describe requirements around sending and receiving shares
* Describe requirements for managing active shares
* Consider whether operations, management or scaling of OCM servers
requires any requirements or recommenations,
* Consider extensibility in the protocol, data model and discovery
mechanisms
* Develop security considerations

The working group will **not** define new data transfer protocols or
mechanisms unrelated to server-to-server federation and metadata
exchange. Instead, established protocols such as WebDAV will be used
for actual data transfer.

OCM does not aim to address identity federation (e.g., OIDC or SAML);
rather, it leverages existing protocols for identity and authentication
where appropriate.  OCM also does not propose to create interoperable 
protocol flows to establish trust relationships where there are none 
before; instead the WG will explain how trust relationships set up 
out-of-band (e.g., configuration of server settings or allow lists) 
are required for secure sharing.


Importantly, OCM is **not** a competitor to user-oriented messaging or
social protocols like ActivityPub or Matrix federation, but addresses
different use cases focused on content federation and metadata
exchange.

# Deliverables

* One specification or family of specifications, that describe
OCM Invite/Share functionality and associated considerations such as
security considerations.