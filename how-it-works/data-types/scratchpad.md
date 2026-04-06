---
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/T1VY0u5KuOsTpycHpSka/how-it-works/data-types/scratchpad
---

# Scratchpad

A Scratchpad is a mutable, encrypted storage container that allows users to store and update up to 4MB of private data on the Autonomi Network. It serves as a versioned, encrypted key-value store where data is automatically encrypted with the owner's public key and can only be decrypted using the corresponding private key.

Each Scratchpad includes an address derived from the owner's public key, a content type identifier, encrypted payload data, a version counter, and a cryptographic signature. The automatic encryption ensures privacy, while the counter-based versioning system handles concurrent updates using a highest-counter-wins conflict resolution strategy.

Scratchpads require a one-time payment for creation but allow free updates afterward. They are commonly used for storing application state, user preferences, configuration data, and as the underlying storage mechanism for the vault system. The content type field allows multiple applications to safely use the same Scratchpad address without conflicts by using unique identifiers.

The combination of mutability, privacy, and versioning makes Scratchpads ideal for applications needing to maintain private, evolving state on the otherwise immutable Autonomi Network.
