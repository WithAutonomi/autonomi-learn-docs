---
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/T1VY0u5KuOsTpycHpSka/how-it-works/fully-autonomous-data-network/nodes
---

# Nodes

The Autonomi Network is formed of interconnected machines running node software. This software connects the devices to each other using the QUIC protocol with native NAT traversal, manages data and routes it around the Network. It allows users to offer computer resources, like hard drive space, to the Network, and earn Autonomi Network Tokens (ANT) in return. This process of providing a service in return for a reward is analogous to Bitcoin mining, but is designed to work on everyday consumer hardware.

The node software is a small executable file that connects the user’s machine to the Network, turns it into a routing node and also allocates some disk space for storage. It manages the storage of data chunks on the user’s computer and in that way provides storage capacity to the Network. It also routes and caches data chunks (these are encrypted) over the Network via post-quantum encrypted QUIC connections to other nodes.

Each node maintains a list of its ‘close group’, other nodes with IDs (XOR addresses) close to its own. Data stored at a node will also be replicated to members of its close group for redundancy.

Nodes fulfil several functions. They route and store chunks of data; they cryptographically check messages; they cluster into temporary close groups, and thus manage a certain portion of the Network; and they store replicas of data chunks for redundancy.

Every node has an identity based on post-quantum cryptographic keys (ML-DSA-65). Its network address (PeerId) is the BLAKE3 hash of its public key — making it deterministic, verifiable, and resistant to attack by quantum computers. When nodes connect to each other, they authenticate through a quantum-resistant handshake built into the QUIC transport layer. No certificates or central authorities are needed.

Importantly, nodes can run from any home internet connection without port forwarding or manual configuration. NAT traversal is handled natively — the network tries a direct connection first, then coordinated hole punching, with a relay fallback for the most restrictive firewalls. This is what makes it possible for everyday home computers to participate.
