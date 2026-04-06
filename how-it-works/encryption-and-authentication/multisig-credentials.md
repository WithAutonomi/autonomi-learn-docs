---
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/T1VY0u5KuOsTpycHpSka/how-it-works/encryption-and-authentication/multisig-credentials
---

# Post-Quantum Identity & Credentials

Autonomi 2.0 uses ML-DSA-65 (NIST FIPS 204) post-quantum digital signatures for all identity and authentication, with ML-KEM-768 (NIST FIPS 203) for key exchange — both at NIST Level 3 security. Each user's identity is based on a cryptographic key pair — there are no usernames, passwords, or central authentication servers.

Post-quantum keys are larger than classical keys — this is the cost of quantum resistance:

- ML-DSA-65 public key: 1,952 bytes (vs ~32 bytes for Ed25519)
- ML-DSA-65 signature: 3,309 bytes (vs ~64 bytes for Ed25519)
- ML-KEM-768 public key: 1,184 bytes

These sizes affect handshake overhead (~7.5KB vs ~228 bytes for classical TLS) but do not impact data throughput once a connection is established. There is no classical cryptographic fallback.

A user's secret key is the root of their identity on the network. From a single master secret key, unlimited child keys can be derived using HKDF (HMAC-based Key Derivation Function). This enables:

- **Separate keys for different apps or contexts** — logical separation without managing unrelated keys
- **Delegation** — derive a child key for a specific purpose, share it without exposing the master
- **Hierarchical access control** — organise data access through key hierarchies
- **Per-application data organisation** — each derived key has its own address space on the network

Credentials are extremely important, but credential loss can be a serious problem on decentralized networks where there is no central authority to help recover or reset forgotten passwords.

**Key Management Best Practices:**

Users should securely back up their master secret key. Without it, all data derived from that key — including all child keys and their associated data — becomes permanently inaccessible. There is no recovery mechanism on a decentralised network.

For enhanced security, users may choose to split their key across multiple devices or locations, so that no single point of failure results in complete loss of access.
