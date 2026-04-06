---
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/T1VY0u5KuOsTpycHpSka/how-it-works/encryption-and-authentication
---

# Encryption and Authentication

Content on Autonomi is stored as encrypted chunks. The original content can be recreated from these chunks, provided we have a map of where the chunks are plus the keys to decrypt them. \
\
A 'file' on the Network is really a collection of chunks, with a datamap that allows us to discover all the chunks and decrypt the file.&#x20;

Files are kept in folders which are created as part of the [Self-Encryption](self-encryption.md) process and are encrypted, meaning their contents are only accessible to their owner by default.

The API for upload by default self-encrypts all files.

{% hint style="info" %}
#### Keeping it Simple

All content on Autonomi is encrypted by default. When content is stored on the Network it is first broken into chunks, hashed and then encrypted and these chunks are themselves encrypted using the hash of another chunk from the same file. This is ‘self-encryption’—a method originally patented by MaidSafe but now open-sourced. The encryption uses ChaCha20-Poly1305 for symmetric encryption and BLAKE3 for hashing. When content is made public, its containing folder is decrypted, meaning anyone can reassemble the chunks.
{% endhint %}

At the network level, Autonomi uses the QUIC protocol (built on UDP) and all data moved by this protocol is encrypted from 'bit 1', using post-quantum cryptography. The TLS 1.3 handshake integrated into QUIC uses ML-KEM-768 for key exchange and ML-DSA-65 for digital signatures — both NIST-standardised post-quantum algorithms. This means connections are quantum-resistant from before any application data is exchanged.

So communications between the Network and the user are always encrypted, never in plain text. No classical cryptographic fallback is used — Autonomi 2.0 is 100% post-quantum at the transport layer.

Note that any node on the Network can be used as a bootstrap server so long as its IP address is added to the configuration file of the joining node. It does not have to be one provided by MaidSafe.
