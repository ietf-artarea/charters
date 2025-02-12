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
The presence of a digital emblem represents a new signal available to cyber operators, one which can be combined with existing operational procedures to reduce uncertainty and improve decision making. 

The DIEM WG will define an architecture, set of emblem types, and presentation
methods for creating, displaying, validating and
interpreting emblems across applications and platforms in a cohesive way.
The initial scope of the working group will assume that an emblem is also discovered thought digital communication,
however, ideally the methods defined for emblem creation and validation should not depend on this assumption.


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
of digital communication as the primary interaction method that have the
unique challenge of the validator remaining unknown to the operator of the asset.
Other use cases for future consideration may also cover assets that lack this requirement
or even require separate digital discovery. The WG will ensure maximum reuse of work
for emblem representation and binding. A discovery
mechanism for the initial work will only be specified by this group after the initial emblem
binding protocol is completed (see the Deliverables section below).”

The working group is tasked with developing: 1) use cases and requirements related to the
initial scope, 2) an architecture that captures the relationships between entities utilizing
digital emblems, 3) a specification on binding digital emblems to assets, and 4) a specification
for discovery mechanisms supported by the initial scope.

The working group will liaise with appropriate organizations and relevant IETF WGs when
defining emblem formats, validation, and discovery mechanisms to facilitate re-use of existing
protocols and capabilities.

## Deliverables

The DIEM WG will work on the following milestones for the defined scope:

1. Use cases and requirements for the initial target scenarios (Informational)
2. Architecture document containing a taxonomy and overall information flows (Informational)
3. A protocol specification describing the binding of emblems to assets (Proposed Standard or Experimental)
4. A protocol specification describing the emblem discovery mechanism for the initial use cases (Proposed Standard
or Experimental)
