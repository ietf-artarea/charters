# Introduction & Background

Emblems such as the Red Cross, Red Crescent, Red Crystal, and Blue Shield can be symbols of protection governed by International Humanitarian Law (IHL).  
Emblems can also be identified by other laws, agreements, or standards.
There is a need to present emblems through digital communication channels.
Emblems presented in such ways are called digital emblems.
Digital emblems extend the range of identifying marks from the physical (visual and tactile) to the digital realm.

"To bear an emblem" means to present and be identified by a digital emblem.
The entity that bears the emblem is the bearer or emblem holder.
This is often a separate entity from the creator or original designer of the emblem.
"To validate an emblem" means to confirm the authenticity or legitimacy of a particular symbol or design, often by checking its details against a known standard or reference point. 
Validation may include ensuring that the bearer has not forged, stolen, or tampered with an emblem.
Emblems may be observed by validators without the knowledge of the bearer presenting the emblem, or may be presented to a specific validator upon request.
Cryptographic verification may or may not be used based on the in-place security mechanisms of the communication channel bearing the emblem.
Which attributes an emblem contains, and how a digital emblem is secured and presented impacts how a validator interprets and trusts the assertions made within the emblem.

The DIEM WG will define an architecture and discovery mechanism enabling digital emblems to be presented and validated across applications and platforms in a cohesive way.

# Initial Scope

The DIEM WG will develop an initial DNS-based discovery mechanism and associated validation procedure for digital emblems that explicitly identify their bearer.
The design of discovery mechanisms using proximity-based protocols such as QRCodes, NFC, or Bluetooth is out-of-scope.
The discovery mechanism and validation procedures must allow for validators to be undetectable as validators.
The DIEM WG is not required to describe object level securing mechanisms, in the case that existing protocol level securing mechanisms are sufficient, for example DNSSEC.

The DIEM WG will seek advice from DNS experts in DNSOP and DNSSD WGs on proposed solutions.

The DIEM WG will not produce any standards track generic serialization formats, standards track extensions to the DNS, cryptographic primitives, or digital signature schemes.

The DIEM WG will investigate, analyze, and evaluate application-layer serialization formats focusing on data structures that match the initial scope's discovery mechanism (e.g., DNS records or structured fields in DNS) as well as the respective securing mechanisms for digital emblems.

# Deliverables

The DIEM WG will work on the following deliverables for the defined scope strictly in this order:

1. Use cases and requirements that can be addressed by the initial scope (Informational)
2. An extensible architecture containing a taxonomy, information model, and overall information flows (Informational)
3. A protocol specification describing the validation and discovery of digital emblems using DNS (Proposed Standard or Experimental)
   
