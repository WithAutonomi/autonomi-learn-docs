---
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/T1VY0u5KuOsTpycHpSka/introduction/what-is-autonomi/post-quantum-secure
---

# Post-Quantum Secure

Autonomi is designed for a post-quantum threat model, but it does not use the same cryptography for everything. Stored data is protected by self-encryption on your own device, while node identity and network connections use explicitly post-quantum cryptography.

## What this means

Post-quantum security means the network does not rely only on classical public-key cryptography for node identity and connection security. That matters because large quantum computers would weaken some cryptographic systems that are still used widely on today's Internet.

For a reader or user, the important distinction is simple:

- your files are protected by self-encryption before they leave your device
- the connections between clients and nodes are protected by post-quantum cryptography

These are separate layers, and Autonomi uses both as part of the same broader security model.

## Why Autonomi separates these layers

Stored data and live network connections face different risks, so they are protected differently. Self-encryption keeps uploaded content unreadable to the network itself using modern symmetric encryption and hashing. Post-quantum transport security protects node identity and the secure connections used to move data around.

That means the network can verify who is participating and establish secure connections without exposing readable content in transit or at rest.

## Under the hood

Autonomi's transport layer uses `ML-KEM-768` for key exchange and `ML-DSA-65` for signatures, with no classical fallback.

Content protection follows a different path. Files are self-encrypted on the client using `ChaCha20-Poly1305`, with keys and addresses derived using `BLAKE3`. These are not the same as the network's explicit post-quantum identity and transport algorithms, but they are also not vulnerable in the same way as classical public-key cryptography.

## Related pages

- [Everything's Encrypted](everythings-encrypted.md)
- [Self-Encryption](../../how-it-works/encryption-and-authentication/self-encryption.md)
- [Post-Quantum Identity & Credentials](../../how-it-works/encryption-and-authentication/multisig-credentials.md)
