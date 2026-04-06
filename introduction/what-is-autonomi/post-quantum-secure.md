---
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/T1VY0u5KuOsTpycHpSka/introduction/what-is-autonomi/post-quantum-secure
---

# Post-Quantum Secure

Autonomi is designed so the network's connections and identities are protected by post-quantum cryptography from the very first byte. The transport layer uses ML-KEM-768 for key exchange and ML-DSA-65 for signatures, with no classical fallback.

This is separate from how content itself is protected. Files are self-encrypted on your own device before upload using ChaCha20-Poly1305 with keys derived via BLAKE3. In other words, stored data is client-side encrypted, while the network that moves it is secured with post-quantum cryptography.

Together, these layers let nodes verify who they are talking to, establish secure connections, and move data around the network without exposing readable content. Your data is encrypted before it leaves your device, and the network connections that carry it are built for a quantum-era threat model.
