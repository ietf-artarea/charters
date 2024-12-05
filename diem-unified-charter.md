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

The DIEM WG will initially consider use cases for assets with bindings to emblem types where
validation of the emblem is indistinguishable from observation of the emblem.
This encompasses the unique challenge of assets and validators remaining unknown to one another.

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
