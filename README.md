# TrustFabric Identity Specification

## Summary

TrustFabric is a comprehensive Cloud Native Identity Specification designed for Applications. This specification covers aspects such as Identity Representation, Authentication, Authorization, Identity Revocation, and Interoperability. It aims to address the evolving security landscape and the unique challenges posed by the adoption of micro-services and cloud-native technology.

## Understanding Applications and Services

**Note**: *This specification adopts the definitions proposed by Jacob Jenkov [here](http://tutorials.jenkov.com/soa/services-applications.html)*

* Applications are user-accessible and can also be accessed by other programs over a network.
* Services are primarily accessed by programs, but can also be accessed by users over a network.
* In the cloud-native context, both applications and services perform specialized operations.

**Note**: While the terms 'application' and 'service' are used interchangeably in this document, TrustFabric consistently uses 'Application' as a standard term. The specification applies to both.

## About TrustFabric

TrustFabric is a flexible Cloud Native Identity Specification for Applications. The specification includes:

* Representation and Injection of Application (also known as Service) Identity.
* Verification of Application Identity (Authentication) and Authorization.
* Revocation and Invalidation of Identity.
* Interoperability and Extensibility.

## The Need for a New Specification

The security landscape is rapidly evolving. The rise of micro-services and cloud-native technology has altered the threat landscape. Here are a few challenges:

1. Applications (also known as Services) need an identity for interactions.
1. Application impersonation has emerged as a new attack vector.
1. Application security often relies on static credentials.
1. The 'Confused deputy' problem has become a new dimension of attack with micro-services.
1. A comprehensive approach to IDM/IAM for applications is lacking.
1. The diversity of applications complicates standardization.

## Navigating the Documentation

The following sections provide detailed information about the specification:

* [Terminology](./Terminology.md)
* [Goals](./Goals.md)
* [Overview](./Overview.md)
* [Fabric of Trusted Applications](./TrustFabric.md)
* [Interactions and Protocol](./InterOp.md)
* [Architecture](./Architecture.md)
* [Identity Representation](./Identity.md)
* [Tokens and Validations](./Tokens.md)
* [Integration](./Integrations.md) - gRPC, Envoy, Service Mesh, Generics and more
* [Identity Protection](./StrongIdentity.md) - MitM, Confused deputy, replay attacks
* [FAQ](./FAQ.md)
