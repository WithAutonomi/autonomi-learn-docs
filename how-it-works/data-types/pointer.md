---
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/T1VY0u5KuOsTpycHpSka/how-it-works/data-types/pointer
---

# Pointer

A Pointer is a mutable addressing mechanism that provides versioned references to other data on the Autonomi Network. Unlike most network data which is immutable, Pointers can be updated by their owner over time, making them essential for applications requiring dynamic content references.

Each Pointer consists of an owner (BLS public key), a version counter, a target address, and a cryptographic signature. The target can point to Chunks, GraphEntries, Scratchpads, or even other Pointers, creating flexible addressing chains. The counter-based versioning system ensures that only the latest version (highest counter) is kept, implementing a simple CRDT-like conflict resolution.

Pointers are stored at the network address derived from their owner's public key, with each key supporting exactly one active Pointer. Creation requires a one-time payment, but subsequent updates are free. This design makes them ideal for user profiles, mutable content references, decentralized naming systems, and implementing URL-like redirections in a decentralized environment.
