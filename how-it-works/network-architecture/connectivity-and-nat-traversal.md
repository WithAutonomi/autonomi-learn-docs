# Connectivity and NAT Traversal

Autonomi 2.0 uses a QUIC-based connectivity layer to let nodes discover each other, establish encrypted peer-to-peer connections, and stay reachable across home routers and business firewalls. This layer is shared by both the Autonomi storage network and x0x.

It handles connection setup, address discovery, and NAT traversal. Routing, DHT lookups, and close-group behaviour sit above it in saorsa-core.

#### Why this matters

Getting peers behind home routers and business firewalls to talk to each other has always been one of the hardest parts of decentralised networking. Autonomi is designed so ordinary devices can participate without port forwarding or manual network setup.

#### How connections are made

All connections use QUIC, a modern transport protocol built on UDP. QUIC gives the network low-latency connection setup, multiplexed streams, and built-in TLS 1.3 encryption. On top of that, Autonomi uses native QUIC extension frames for address discovery and NAT traversal.

There's a three-step connectivity strategy:

1. **Direct connection** — nodes connect directly where possible
2. **Hole punching** — coordinated NAT traversal for nodes behind firewalls
3. **MASQUE relay** — for the most restrictive environments, traffic is relayed as a last resort

This means most nodes can run from everyday internet connections without port forwarding. When direct connectivity is not possible, relay fallback keeps the network reachable.

#### Post-Quantum Security

Every connection is secured with post-quantum cryptography from the very first byte. The TLS 1.3 handshake uses NIST-standardised algorithms — ML-KEM-768 for key exchange, ML-DSA-65 for signing. There is no classical fallback. The connection is quantum-resistant before any application data is exchanged.

#### Peer Identity

Each node's identity is a post-quantum key pair (ML-DSA-65). Its network address (PeerId) is the BLAKE3 hash of its public key — deterministic, verifiable, and quantum-resistant. On joining or rejoining the Network a node cannot simply pick its own XOR address; it is determined by its cryptographic identity.
