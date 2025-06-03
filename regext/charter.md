Charter for Working Group

The Extensible Provisioning Protocol (EPP, Standard 69) is the
standard domain name provisioning protocol for top-level domain name
registries. To avoid many separate EPP extensions that provide the
same functions, it's important to coordinate and standardize EPP
extensions.

The EPP Extensions (EPPEXT) working group completed its first goal of
creating an IANA registry of EPP extensions. The registration process
of the registry is documented in RFC 7451. Extensions may be registered
for informational purposes as long as there is a published
specification that has been reviewed by a designated expert.  The
Registration Data Access Protocol (RDAP, RFCs 7480-7484) is the
proposed standard for retrieving registration metadata from both
domain name and Regional Internet Registries. To ensure interoperable
implementations it's important to coordinate and standardize
extensions and profiles to be used by registries.

Extensions in both cases that are targeted for the Standards Track are
subject to more thorough review and open discussion within the IETF.
In addition, commonality may be discovered in related extensions,
especially EPP extensions listed on the EPP extension registry, for
which it would makes sense to merge them into a single standard
extension everybody agrees on.

The REGEXT working group is the home of the coordination effort for
standards track extensions. The selection of extensions for standards
track shall incorporate the following guidelines.

1. Proprietary documented extensions and individual submissions of
informational or experimental EPP extensions will follow the expert
review process as described in RFC 7451 for inclusion in the EPP
extensions registry. These documents will not be part of the REGEXT
working group work or milestones. The working group may discuss or
advise on these documents.

2. Extensions that seek standards track status can be suggested for WG
adoption. If accepted by the working group then the development of the
standard may proceed.

3. When there are no more proposals for Standards-Track extensions,
the working group will either close or become dormant, with the
decision made in consultation with the responsible AD. In any case,
the mailing list will remain open and available for the use of the
expert review process as described in RFC 7451.

The working group may also take on work to develop specifications that
describe the following types of information exchanged between entities
involved in Internet identifier registration that are using the RDAP or
EPP protocols:

* Uniform representation formats for publishing local policy or
  configuration options regarding EPP and RDAP use.

* Data formats for files exchanged between registration entities that
  need insertion in or extraction from EPP or RDAP.

* Technical guidance for registration processes that are supported by
  EPP or RDAP.
