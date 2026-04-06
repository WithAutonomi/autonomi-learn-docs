---
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/T1VY0u5KuOsTpycHpSka/how-it-works/encryption-and-authentication/multilayered-encryption
---

# Multilayered encryption

Autonomi uses several layers of encryption to protect a user's anonymity and privacy. The Network is designed to be as 'zero-knowledge' as possible, to the extent that node operators cannot possibly figure out what chunks from which private file they are storing — even if it's their own.&#x20;

By utilizing multiple levels of encryption, Autonomi provides a platform for applications that is both highly secure and anonymized by design.

These layers work together:

**Self-encryption:** Content is chunked and encrypted on the user's device before it ever touches the network, using ChaCha20-Poly1305 encryption and BLAKE3 hashing. Each chunk is encrypted using keys derived from its neighbouring chunks, creating a web of interdependencies — tamper with any one chunk and the whole structure breaks.

**Post-quantum transport encryption:** All connections between nodes and clients are secured by NIST-standardised post-quantum algorithms (ML-KEM-768 for key exchange, ML-DSA-65 for authentication). The connection is quantum-resistant from the very first byte — before any of your data is exchanged.

**Content addressing:** The network address where a chunk is stored is derived from the hash of the encrypted chunk itself. This means the network's routing layer reveals nothing about the content of the data it moves — the address tells you nothing about what's inside.
