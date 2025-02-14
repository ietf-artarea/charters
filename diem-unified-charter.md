# Introduction

An emblem is a device, symbol, or figure adopted and used as an identifying mark.
As such, emblems provide a mechanism for conveying a set of attributes
bound to an asset. An emblem may be presented to a validator and attributes are asserted by an issuer.

In culture, emblems such as a flag, badge or coat of arms communicate group identity.
In speech, emblems are specific nonverbal gestures or signals that have a direct verbal translation and are widely understood within a particular culture or community.
The emblems of the International Committee of the Red Cross (ICRC)  are symbols of protection under the Geneva Conventions.
ISO 7010 defines a set of emblems that can be used to identify hazards, these include the skull and crossbones for toxic material, the ionizing radiation symbol and the biological hazard symbol.
Today often these emblems/symbols require a sense of sight, or touch to become known to the receiver.

There is a need to sense emblems/symbols through digital communication channels.
The work of this group therefore focuses on digital emblems that extend the range of identifying marks from the physical (visual and tactile) to the digital realm.
The presence of a digital emblem represents a new signal available to cyber operators. 

The DIEM WG will define an architecture, set of emblem types, and presentation
methods for creating, displaying, validating and
interpreting emblems across applications and platforms in a cohesive way.
The initial scope of the working group will assume that an emblem is also discovered thought digital communication,
however, ideally the methods defined for emblem creation and validation should not depend on this assumption.


# Archtectural Consideration

"To bear an emblem" means to use or adopt a symbol, figure, or device as an identifying mark. 
The entity that bears the emblem is respectively the bearer or emblem holder. This can be a separate entity
from the emblem issuer.

To "verify an emblem" means to confirm the authenticity or legitimacy of a particular symbol or design, often by checking its details against a known standard or reference point. 
Emblems may be observed by verifiers without the knowledge of the bearer displaying the emblem, or may be presented to a specific verifier upon request.
However, cryptographic verification can be optional as long is the emblem can be correctly interpreted.
Therefore, to be effective, the semantics of an emblem must be well known, easily recognizable, and distinguishable from other emblems.

Assets bound to digital emblems can be analog (e.g., a vehicle) or
digital (e.g., a web page), however, there need to be a digital representation that is used
for validation using digital communication.

Digital emblems can fall into multiple types (e.g., self-signed, attested, etc.) that will
affect how a validator interprets and trusts the assertions made within the emblem.
The communication between the asset and the validator will influence requirements on how
validators retrieve digital emblems for the asset. These three dimensions will be key
drivers in the development of a digital emblem architecture.

The architecture, specified by this group, must be flexible enough to support multiple serialization formats, securing mechanisms, discovery mechanisms, and use cases. 

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

The working group will facilitate re-use of existing protocols and capabilities and ensure that existing standards are leveraged appropriately.
The working group will not produce any standard track generic serialization formats. The working group will not produce any standard track extensions to the DNS. The working group will not develop novel security mechanisms, cryptographic primitives, or digital signature schemes. 


# Deliverables

The DIEM WG will work on the following deliverables for the defined scope strictly in this order:

1. Use cases and requirements for the initial target scenarios (Informational)
   Initially, the working group will develop and maintain an informational use cases and requirements document, but is not required to request publication of this document. This document must describe at least one digital emblem suitable for indicating protection under international humanitarian law and at least one digital emblem suitable for indicating the presence of a hazard or a certification of the absence of a hazard. This work must assume any specific serialization format or discovery mechanisms.
   As part of this document, the working group will research, analyze and evaluate application layer serialization formats focusing on data structures that match discovery protocols used in the initial scope, such as DNS records or structured fields in DNS, as well as the respective securing mechanisms for digital emblems. The group is not required to describe object level securing mechanisms, in the case that existing protocol level securing mechanisms are sufficient, for example DNSSEC for DNS records, or TLS for well known HTTPS URLs. 

2. An architecture containing a taxonomy, data model, and overall information flows (Informational)
   The working group will develop a high level architecture and data model but start this work only after the use case and requirements document has reached group consensus. The architecture must not assume any specific serialization formats or securing and discovery mechanisms.

3. A protocol specification describing the binding of emblems to assets (Proposed Standard or Experimental)
   After the architecture and data model are finished, the working group will specify a single concrete serialization for digital emblems and emblems types for one or two of the initial use cases. This specification may describe a mandatory to implement securing mechanism. If a securing mechanism is described, at least one mandatory to implement cryptographic algorithm which is already supported by the securing mechanism must be described as well. This protocol specification is intended for proposed standard or experimental, and must not assume any specific discovery mechanisms.

4. A specification describing an DNS-based emblem discovery mechanism (Proposed Standard
or Experimental)
  A proposed standard or experimental specification describing the use of the DNS as the initial presentation/discovery mechanism for digital emblems. This specification may describe a mandatory to implement securing mechanism.
