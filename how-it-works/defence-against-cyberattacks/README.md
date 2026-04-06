---
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/T1VY0u5KuOsTpycHpSka/how-it-works/defence-against-cyberattacks
---

# Defence Against Cyberattacks

Autonomi has an interlocking set of features, each covering the others’ vulnerabilities. This means that data security on the Network is maximized. While 100 percent security is impossible, this strength-in-depth means that the sort of attacks common on the current web will be much harder to carry out on Autonomi.

## Defensive Features&#x20;

**Random address allocation:** A new node joining the Network cannot set its own address and thus cannot decide which data it will be required to manage.

**Nodes are added only as needed:** Nodes that do not pull their weight or act as they should will be ignored, and will cease to earn.

**Churn:** Nodes are constantly joining or leaving. Membership is fluid.

**Encryption:** All data on the Network is protected by [several layers of encryption](../encryption-and-authentication/).&#x20;

[**Self-encryption**](../encryption-and-authentication/self-encryption.md)**:** Content stored on the Network is broken into chunks with each chunk encrypted using ChaCha20-Poly1305 with keys derived from its own hash and the hashes of the two previous chunks. These chunks are stored at geographically random locations (the XOR location being the hash of the encrypted chunk) with a number of copies retained for redundancy. Without a Data Map, the chunks cannot be retrieved and decrypted.

[**XOR Networking**](../network-architecture/content-addressable-storage.md)**:** Randomizes the geographical distribution of the chunks. Only someone in possession of the data map (i.e. the data owner) can find the chunks and piece them together again to recreate the content. An attacker trying to fake a chunk could not do so as its hash—and therefore its address on the Network—would be different. It could not be used to create a corrupted version of the file.

**Self-Authentication:** A user can create a store of data securely and anonymously without requiring any central server to mediate the login process or any trusted third party to store and manage users’ credentials.

**Post-Quantum Cryptography:** All node identity, key exchange, and authentication uses NIST-standardised post-quantum algorithms (ML-DSA-65 for signatures, ML-KEM-768 for key exchange). This makes the network resistant to attacks from quantum computers — both current and future. There is no classical cryptographic fallback.

**Close Group Validation:** At upload time, payment verification includes cryptographic proof that storing nodes are genuinely members of the data's close group. This prevents nodes from fraudulently claiming to store data they don't hold.
