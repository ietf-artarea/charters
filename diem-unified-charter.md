# Introduction

Digital Emblems provide a mechanism for conveying a set of attributes
bound to an asset that is presented to a validator and
asserted by an issuer.

The DIEM WG seeks to define a standard architecture, set of emblem types, and presentation
methods that will provide a cohesive approach to creating, displaying, and
interpreting emblems across applications and platforms.

There are three dimensions to digital emblems: Asset Type, Emblem Type, and 
Validator Relationship. Assets bound to digital emblems can be analog (e.g., a vehicle) or
digital (e.g., a web server). They
differ in the initial interaction between the asset and the validator. Digital
Emblems can fall into multiple types (e.g., self-signed, attested, etc.) that will
affect how a validator interprets and trusts the assertions made within the emblem.
The relationship between the asset and the validator will influence requirements on how
validators retrieve digital emblems for the asset. These three dimensions will be key
drivers in the development of a digital emblem architecture.

# Initial Scope

The working group will focus its initial work on assets that are discovered by use
of digital communication such as use of DNS or at a well-know location on a host identified
by a hostname or IP address. These discovery mechansisms have the
unique challenge of the validator remaining unknown to the operator of the asset.
Specifically the design of other discovery mechanisms using proximity-based protocols such as  QRCodes, NFC, or Bluetooth
is out-of-scope.

Other use cases for future consideration may also cover assets that lack this requirement
or even require separate digital discovery. The WG will ensure maximum reuse of work
for emblem representation and binding. A discovery
mechanism for the initial work will only be specified by this group after the initial emblem
binding protocol is completed (see the Deliverables section below).

The working group will coordinate with relevant working groups within the IETF and other SDOs to facilitate re-use of existing protocols and capabilities and ensure that existing standards are leveraged appropriately.
The working group will not produce any standard track generic serialization formats. The working group will not produce any standard track extensions to the DNS. The working group will not develop novel security mechanisms, cryptographic primitives, or digital signature schemes. 


# Deliverables

The DIEM WG will work on the following deliverables for the defined scope strictly in this order:

1. Use cases and requirements for the initial target scenarios (Informational)
   Initially, the working group will develop and maintain an informational use cases and requirements document, but is not required to request publication of this document. This document must describe at least one digital emblem suitable for indicating protection under international humanitarian law and at least one digital emblem suitable for indicating the presence of a hazard or a certification of the absence of a hazard. This work must assume any specific serialization format or discovery mechanisms.
   As part of this document, the working group will research, analyze and evaluate application layer serialization formats focusing on data structures that match discovery protocols used in the initial scope, such as DNS records or structured fields in DNS, as well as the respective securing mechanisms for digital emblems. The group is not required to describe object level securing mechanisms, in the case that existing protocol level securing mechanisms are sufficient, for example DNSSEC for DNS records, or TLS for well known HTTPS URLs. 

2. Architecture document containing a taxonomy, data model, and overall information flows (Informational)
   The working group will develop a high level architecture and data model but start this work only after the use case and requirements document has reached group consensus. The architecture must not assume any specific serialization formats or securing and discovery mechanisms.

3. A protocol specification describing the binding of emblems to assets (Proposed Standard or Experimental)
   After the architecture and data model are finished, the working group will specify a single concrete serialization for digital emblems and emblems types for one or two of the initial use cases . This document may describe a mandatory to implement securing mechanism. If a securing mechanism is described, this document must describe at least one mandatory to implement cryptographic algorithm which is already supported by the securing mechanism. This protocol is intended for proposed standard, and must not assume any specific discovery mechanisms.

4. A protocol specification describing an DNS-based emblem discovery mechanism (Proposed Standard
or Experimental)
  A proposed standard describing the use of the DNS as the initial presentation/discovery mechanism for digital emblems. This document may describe a mandatory to implement securing mechanism.
