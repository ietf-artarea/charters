# Introduction

Digital Emblems provide a mechanism for conveying a set of attributes
bound to an asset that is presented to a validator and
attested to by an issuer.

The DIEM WG seeks to define a standard architecture, set of emblem types, and presentation
methods that will provide a cohesive approach to creating, displaying, and
interpreting emblems across applications and platforms.

There are three dimensions to digital emblems: Asset Type, Emblem Type, and 
Validator Relationship. Assets bearing digital emblems can be analog or digital. They
differ in the initial interaction between the asset and the validator. Digital
Emblems can fall into multiple types (e.g., self-signed, attested, etc.) that will
affect how a validator interprets and trusts the assertions made within the emblem.
The relationship between the asset and the validator will influence requirements on how
validators retrieve digital emblems for the asset. These three dimensions will be key
drivers in the development of a digital emblem architecture.

# Initial Scope

To simplify the beginning work for DIEM, the initial scope is limited
to attested (e.g., an emblem issuer is independent of the asset, but is attesting to
the asset's right to claim protection) and self-signed (e.g., an emblem issuer is the
entity controlling the protected asset) emblem types and digital assets that must not be able to determine if
a validator has inspected its digital emblem. This combination encompasses the unique
challenge of assets and validators being unknown to one another.

The working group is tasked with developing: 1) use cases and requirements related to the
initial scope, 2) an architecture that captures the relationships between entities utilizing
digital emblems, 3) a specification on binding digital emblems to assets, and 4) a specification
for discovery mechanisms supported by the initial scope.

The working group will liaise with appropriate organizations and relevant IETF WGs when
defining emblem formats, validation, and discovery mechanisms to facilitate re-use of existing
protocols and capabilities.

Other use cases and scenarios can be added by re-chartering of the working group.

## Deliverables

The DIEM WG will work on the following milestones for the defined scope:

1. Use cases and requirements for the initial target scenarios (Informational)
2. Architecture document containing a taxonomy and overall information flows (Informational)
3. A protocol specification describing the binding of emblems to assets (Proposed Standard or Experimental)
4. A protocol specification describing the emblem discovery mechanism for the initial use cases (Proposed Standard
or Experimental)
