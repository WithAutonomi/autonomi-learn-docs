---
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/T1VY0u5KuOsTpycHpSka/how-it-works/data-types/graphentry
---

# GraphEntry

A GraphEntry is a cryptographically signed, immutable data structure that serves as a building block for creating graph-like data structures on the Autonomi Network. Each GraphEntry is owned by a specific public key and stored at the network address derived from that key, meaning only one GraphEntry can exist per owner.

The structure contains an owner (public key), references to parent GraphEntries, 32 bytes of content, references to descendant GraphEntries with associated data, and a cryptographic signature that validates all fields. This design enables applications to build complex data relationships while maintaining cryptographic integrity and immutability.

GraphEntries are fundamental to higher-level data types like Registers (which use them as version history in doubly-linked chains) and Vaults (which store encrypted data references). Applications are free to define the semantic meaning of parent-child relationships, while the network protocol only enforces signature validity and immutability constraints.

Each GraphEntry has a maximum size of 100KB and requires payment for upload. Once stored, they are automatically replicated across multiple nodes for availability and include built-in fork detection to ensure data consistency.

<br>
