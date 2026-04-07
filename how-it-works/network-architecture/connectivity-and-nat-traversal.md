# Connectivity and NAT Traversal

Autonomi is designed so ordinary devices can join the network from home or office internet connections, even when they sit behind routers and firewalls. To make that work, the network needs a reliable way to discover peers, establish secure connections, and stay reachable without asking most people to configure ports manually.

## Why this matters

Many decentralized networks work best on publicly reachable servers or require manual setup. Autonomi is designed so most nodes can connect from ordinary internet connections instead.

For you, that means:

1. Most nodes can run without manual port forwarding.
2. The network first tries to connect peers directly.
3. If that does not work, it tries hole punching, then falls back to a relay.

## How peers connect

Autonomi uses [QUIC](../../learn-more/glossary.md#quic), a modern transport protocol built on UDP, as the basis for peer connections. QUIC allows fast connection setup, multiple data streams over one connection, and built-in TLS 1.3 encryption.

To get peers talking across routers and firewalls, the network uses [NAT traversal](../../learn-more/glossary.md#nat-traversal). In practice, that means a three-step strategy:

1. **Direct connection** — peers connect directly where possible.
2. **Hole punching** — the network coordinates a connection between peers behind NAT.
3. **[MASQUE relay](../../learn-more/glossary.md#masque-relay)** — if direct connection and hole punching both fail, traffic is relayed as a last resort.

This keeps the network reachable in restrictive environments while keeping direct peer-to-peer connections as the default.

## Connection security

Every connection uses post-quantum cryptography from the first byte, so peers can establish secure connections without falling back to classical public-key cryptography.

## Peer identity

Each node has a [PeerId](../../learn-more/glossary.md#peerid), the network identifier other nodes use to recognize it. That identifier is derived from the node's cryptographic identity, so a node cannot choose its own position in the network arbitrarily.

This helps the network identify peers consistently, coordinate connections, and measure which nodes are closest to each other and to a given piece of data.

## Under the hood

The shared transport layer is [`saorsa-transport`](../../learn-more/glossary.md#saorsa-transport). It handles connection setup, address discovery, NAT traversal, and relay fallback. The same transport is also used by [x0x](../../learn-more/glossary.md#x0x), though Autonomi and x0x use it for different higher-level purposes.

Autonomi's transport layer uses `ML-KEM-768` for key exchange and `ML-DSA-65` for signatures, with no classical fallback. Each `PeerId` is the `BLAKE3` hash of the node's `ML-DSA-65` public key.

## Related pages

- [Nodes](../fully-autonomous-data-network/nodes.md)
- [Post-Quantum Identity & Credentials](../encryption-and-authentication/multisig-credentials.md)
- [Glossary](../../learn-more/glossary.md)
