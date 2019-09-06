# Decentralized Identity Agent Architectures Overview

These notes to be refactored with attribution to Transmute into [this paper](https://github.com/WebOfTrustInfo/rwot9-prague/blob/91aaecf37ca77355ca85baa0602e58deecaad6b4/topics-and-advance-readings/Bare-minimum-agent-architecture.md) by Snorre.

Please use: [Orie Steele](https://www.linkedin.com/in/OR13b/) for the co-author field, and [Transmute](https://www.transmute.industries/) as the company supporting the contribution.

According to Merriam-Webster:

Definition of agent:

- one that acts or exerts power

- something that produces or is capable of producing an effect: an active or efficient cause chemically, physically, or biologically active principle
- a means or instrument by which a guiding intelligence achieves a result
- one who is authorized to act for or in the place of another: such as a representative, emissary, or official of a government
- one engaged in undercover activities (such as espionage): SPY
- a business representative (as of an athlete or entertainer)
- a computer application designed to automate certain tasks (such as gathering information online)

With this definition in mind, let’s further refine the definition of a DID Agent:

A software system which may control or coordinate identities or activities linked to identities.

With such a broad definition we can now describe some traits of agent’s which when combined can yield specific architectural differences.

## Identification

An agent may or may not have a distinct identifier from its controller. For example, a local system agent may manage keys and produce signatures, but not have publicly accessible interfaces. The keys it uses may or may not be discoverable via a DID Method. An agent may have more than one form of identification such as DID, PeerID, IP Address, Host Name, IPC Interface, Email Address, Phone Number, Username, etc… A single agent may represent multiple DIDs, across multiple methods, and a single DID may leverage multiple Agents.

## Cryptographic Operations

Symmetric, Asymmetric, Threshold, Zero Knowledge Proofs, other forms of cryptographic operations may be directly computed or indirectly computed via remote service or trusted hardware. Performing cryptographic operations on behalf of a user is one of the most significant activities an agent performs, however it is not a requirement. An agent could simply communicate cryptographic activity performed by other trusted systems.

## Communication

Communication with an agent can be accomplished via various network, hardware or software channels. HTTP and web sockets are popular choices. In addition to the wire protocol, there are various messaging, and transport level protocols, such as DIDComm, UMF, and Activity Pub, which might be used.

## Storage

Most agent’s seem to be stateful and require some minimum storage capabilities to operate, but others may also provide Personal Data Hub or Identity Wallet like storage capabilities. Other agent’s may prefer to rely on centralized databases or remote storage systems, instead of being storage providers themselves.

### Example Agent Architectures

## Progressive Web App Agent

- Managed Keys
- QR Code / HTTP interface
- Accessible on any browser
- Store credentials on server / hub (not local).

## SMS Chat Bot

- Managed Keys
- SMS command interface
- Single phone number per agent, or multi user phone number.
- QR Code / Text Credential interfaces

## Mobile Phone App Agent

- User controlled keys
- QR Code / Bluetooth / Wifi Interfaces
- Biometric Support
- Store credentials locally
- Cloud backup

## Apple Watch App

- Managed Keys
- Bluetooth / nfc

## Desktop Agent

- User managed keys
- Wifi / HTTP interface
- Credentials stored locally

## Raspberry Pi Agent

- User controlled keys
- Wifi / HTTP / Hardware interfaces
