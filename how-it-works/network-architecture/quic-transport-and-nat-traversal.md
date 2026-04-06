# QUIC Transport & NAT Traversal

Autonomi 2.0 uses saorsa-transport — a shared transport abstraction built specifically for the network. It replaces the previous networking stack with a purpose-built solution that integrates post-quantum cryptography at the transport level and provides native NAT traversal without relying on external infrastructure.

The transport layer handles all peer-to-peer connectivity: how nodes discover and connect to each other, how those connections are managed, and how data is routed across the network. The same transport is shared by both the Autonomi storage layer and the x0x communication layer.

#### Transport

All connections use QUIC, a modern transport protocol built on UDP. QUIC provides multiplexed streams, low-latency connection establishment, and built-in encryption via TLS 1.3. Unlike older TCP-based approaches, QUIC handles connection migration gracefully — nodes can maintain connections even as network conditions change.

#### NAT Traversal

Getting nodes behind home routers and business firewalls to talk to each other has long been one of the hardest problems for decentralised networks. Autonomi solves this with native QUIC extension frames — custom protocol extensions that enable NAT traversal without external STUN, ICE, or TURN infrastructure.

There's a three-tier strategy that aims to ensure high connectivity regardless of network topology:

1. **Direct connection** — nodes connect directly where possible
2. **Hole punching** — coordinated NAT traversal for nodes behind firewalls
3. **MASQUE relay** — for the most restrictive environments, traffic is relayed as a last resort

This means nodes can run from any home internet connection without port forwarding, relay servers, or manual configuration. It's what makes it possible for billions of everyday devices to participate — as more join, network capacity grows and costs fall.

#### Post-Quantum Security

Every connection is secured with post-quantum cryptography from the very first byte. The TLS 1.3 handshake uses NIST-standardised algorithms — ML-KEM-768 for key exchange, ML-DSA-65 for signing. There is no classical fallback. The connection is quantum-resistant before any application data is exchanged.

#### Peer Identity

Each node's identity is a post-quantum key pair (ML-DSA-65). Its network address (PeerId) is the BLAKE3 hash of its public key — deterministic, verifiable, and quantum-resistant. On joining or rejoining the Network a node cannot simply pick its own XOR address; it is determined by its cryptographic identity.

#### Future Transports

The transport architecture is designed to support additional connectivity methods beyond internet QUIC. Bluetooth Low Energy (BLE) is already implemented behind a feature gate, and the architecture is ready for LoRa (long-range radio) and other transports in future. These can be rolled out gradually, with nodes communicating across transport types, without requiring a network restart.
