# Introduction

Emblems such as the Red Cross, Red Crescent, Red Crystal, and Blue Shield can be symbols of
protection governed by International Humanitarian Law (IHL).  Emblems can also
be identified by other laws or ISO standards that parties need to be able to apply
to digital infrastructure.

There is a need to present emblems through digital communication channels.
Emblems presented in such ways are called digital emblems.
Digital emblems extend the range of identifying marks from the physical (visual and tactile) to the digital realm.

The DIEM WG will define an architecture and discovery mechanism enabling digital emblems to be presented and validated across applications and platforms in a cohesive way.

# Terminology

"To bear an emblem" means to present or display and be identified by a digital emblem.
The entity that bears the emblem is respectively the bearer or emblem holder. 
This is often a separate entity from the creator or original designer of the emblem.

"To validate an emblem" means to confirm the authenticity or legitimacy of a particular symbol or design, often by checking its details against a known standard or reference point. 
Validation may include ensuring that the bearer has not forged, stolen, or tampered with an emblem.
Emblems may be observed by validators without the knowledge of the bearer displaying the emblem, or may be presented to a specific validator upon request.
Cryptographic verification may or may not be used based on the in-place security mechanisms of the communication channel bearing the emblem.
Which attributes an emblem contains, and how a digital emblem is secured and presented impacts how a validator interprets and trusts the assertions made within the emblem.

# Initial Scope

The DIEM WG will develop digital emblems that explicitly identify their bearer. It will also develop an initial DNS-based discovery mechanism.
The design of discovery mechanisms using proximity-based protocols such as QRCodes, NFC, or Bluetooth is out-of-scope.
The discovery mechanism, presentation, and validation procedures must allow for validators to be undetectable as validators.

The working group will not produce any standards track generic serialization formats. 
The working group will not produce any standards track extensions to the DNS. 
The working group will not develop novel security mechanisms, cryptographic primitives, or digital signature schemes. 

# Deliverables

The DIEM WG will work on the following deliverables for the defined scope strictly in this order:

1. Use cases and requirements that can be addressed by the initial scope (Informational):
   Initially, the working group will develop and maintain an informational use cases and requirements document, but is not required to request publication of this document. 
   As part of this document, the working group will research, analyze and evaluate application layer serialization formats focusing on data structures that match initial scope's discovery mechanism, such as DNS records or structured fields in DNS, as well as the respective securing mechanisms for digital emblems.
   The group is not required to describe object level securing mechanisms, in the case that existing protocol level securing mechanisms are sufficient, for example DNSSEC.

2. An extensible architecture containing a taxonomy, data model, and overall information flows (Informational):
   The working group will develop a high level architecture and data model that includes a taxonomy defining the terminology to be used in future working group documents but start this work only after the use case and requirements document has reached group consensus. 
   The architecture must not assume any specific serialization formats or securing and discovery mechanisms.

3. A protocol specification describing the discovery of digital emblems (Proposed Standard or Experimental):
   After the architecture and data model are finished, the working group will specify a validation and discovery mechanism implementing the initial scope.
   This specification may describe a mandatory to implement securing mechanism. 
   If a securing mechanism is described, at least one mandatory to implement cryptographic algorithm which is already supported by the securing mechanism must be described as well. 
