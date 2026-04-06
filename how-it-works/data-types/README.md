---
metaLinks:
  alternates:
    - https://app.gitbook.com/s/T1VY0u5KuOsTpycHpSka/how-it-works/data-types
---

# Data types

A data type is a classification which describes how data can be created, transformed and used. All programming languages use them, and common examples include integer, string and boolean.

Autonomi 2.0 employs a content-addressed, immutable storage model. All data stored on the network is permanent and unchangeable — this is fundamental to the architecture and what makes the pay-once economic model work.

At the network level, Autonomi stores one thing: **chunks**. Chunks are the storage primitive. When content is uploaded, it is split into chunks (each up to ~4MB), encrypted via self-encryption, and stored at content-addressed locations — the address of each chunk is derived from the BLAKE3 hash of its encrypted content. The 4MB limit applies to individual chunks, not to the content they represent — a file of any size is split into as many chunks as needed.

When content is self-encrypted, the process produces a **DataMap** — a small structure that records the network addresses of all the chunks and the hashes needed to decrypt them. The DataMap is the key to your content: without it, the chunks are meaningless encrypted fragments scattered across the network. What makes data public or private is simply where the DataMap lives — stored on-network for public data, kept locally (or encrypted on-network) for private data.

So a 'file' on the Network is really a set of instructions for finding the content's immutable constituent parts and assembling them to recreate the original content, together with information about what will be returned when you do.

All storage on Autonomi is immutable. If your application needs mutable state, real-time interaction, or live collaboration, those capabilities exist in the broader ecosystem through x0x — a complementary post-quantum gossip network that provides CRDTs, pub/sub, and direct messaging.
