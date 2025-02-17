# Introduction

An emblem is a device, symbol, or figure adopted and used as an identifying mark.
In culture, emblems such as a flag, badge or coat of arms communicate group identity.
In speech, emblems are specific nonverbal gestures or signals that have a direct verbal translation and are widely understood within a particular culture or community.
Under International Humanitarian Law (IHL), the red cross, red crescent, and red crystal emblems are symbols of protection.
Similarly, the "blue shield" is another IHL emblem that marks cultural property under special protection.
ISO 7010 defines a set of emblems that can be used to identify hazards, these include the skull and crossbones for toxic material, the ionizing radiation symbol and the biological hazard symbol.
Today often these emblems/symbols require a sense of sight, or touch to become known to the receiver.

There is a need to sense emblems/symbols through digital communication channels.

Digital emblems extend the range of identifying marks from the physical (visual and tactile) to the digital realm.
The presence of a digital emblem represents a new signal available to cyber operators. 

The DIEM WG will define an architecture and discovery mechanism enabling digital emblems to be presented and validated across applications and platforms in a cohesive way.

# Architectural Consideration

"To bear an emblem" means to present or display an identifying mark. 
The entity that bears the emblem is respectively the bearer or emblem holder. 
This can be a separate entity from the creator or original designer of the emblem.

"To validate an emblem" means to confirm the authenticity or legitimacy of a particular symbol or design, often by checking its details against a known standard or reference point. 
Emblems may be observed by validators without the knowledge of the bearer displaying the emblem, or may be presented to a specific validator upon request.
Cryptographic verification can be optional as long as the emblem can be correctly interpreted.
Therefore, to be effective, the semantics of an emblem must be well known, easily recognizable, and distinguishable from other emblems.

Digital emblems can be borne or presented by entities that are analog (e.g., a vehicle) or digital (e.g., a web page), however, there needs to be a digital representation that is used for validation using digital communication.

Digital emblems can be unsigned, self-signed, or signed by a trust anchor.
How a digital emblem is secured and presented impacts how a validator interprets and trusts the assertions made within the emblem.

# Initial Scope

The DIEM WG will ensure maximum reuse of work for emblem representation and binding. 
A discovery mechanism for the initial work will only be specified by this group after the initial emblem binding protocol is completed (see the Deliverables section below).

The working group is limited to specifying discovery mechanisms that rely on digital communication such as the use of DNS or well-known locations on a host identified by a hostname or IP address.
The working group working group must not propose discovery mechanisms or binding solutions that enable validation to be distinguishable from currently existing interactions with the emblem bearer. 
The design of discovery mechanisms using proximity-based protocols such as QRCodes, NFC, or Bluetooth is out-of-scope.
The working group will facilitate re-use of existing protocols and capabilities and ensure that existing standards are leveraged appropriately.
The working group will not produce any standards track generic serialization formats. 
The working group will not produce any standards track extensions to the DNS. 
The working group will not develop novel security mechanisms, cryptographic primitives, or digital signature schemes. 

# Deliverables

The DIEM WG will work on the following deliverables for the defined scope strictly in this order:

1. Use cases and requirements for the initial target scenarios (Informational):
   Initially, the working group will develop and maintain an informational use cases and requirements document, but is not required to request publication of this document. 
   This document must describe at least one digital emblem suitable for indicating protection under international humanitarian law and at least one digital emblem suitable for indicating the presence of a hazard or a certification of the absence of a hazard. 
   This work must assume any specific serialization format or discovery mechanisms.
   As part of this document, the working group will research, analyze and evaluate application layer serialization formats focusing on data structures that match discovery protocols used in the initial scope, such as DNS records or structured fields in DNS, as well as the respective securing mechanisms for digital emblems. 
   The group is not required to describe object level securing mechanisms, in the case that existing protocol level securing mechanisms are sufficient, for example DNSSEC for DNS records, or TLS for well known HTTPS URLs. 

2. An architecture containing a taxonomy, data model, and overall information flows (Informational):
   The working group will develop a high level architecture and data model but start this work only after the use case and requirements document has reached group consensus. 
   The architecture must not assume any specific serialization formats or securing and discovery mechanisms.

3. A protocol specification describing the discovery of digital emblems (Proposed Standard or Experimental):
   After the architecture and data model are finished, the working group will specify a binding and discovery mechanism addressing one or two of the initial use cases. 
   This specification may describe a mandatory to implement securing mechanism. 
   If a securing mechanism is described, at least one mandatory to implement cryptographic algorithm which is already supported by the securing mechanism must be described as well. 
