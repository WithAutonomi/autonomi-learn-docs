---
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/T1VY0u5KuOsTpycHpSka/how-it-works/network-architecture/libp2p
---

# libp2p

libp2p is a Kademlia-based open-source peer-to-peer networking framework developed by IPFS.  It consists of a collection of protocols, specifications and libraries that facilitate P2P communication between network peers (nodes).

It is used in the Autonomi Network to allow nodes to discover and connect to other nodes, to manage those connections thereafter, and to facilitate data routing.&#x20;

libp2p is modular, meaning Autonomi developers can use the parts they want without having to worry about the parts they don't need. The Rust implementation of libp2p is the one adopted. &#x20;

Among libp2p features useful to Autonomi are:

#### Transport:

libp2p supports TCP, UDP, μUDP and QUIC and can be configured to allow connections with nodes behind home routers or business firewalls (NATS), which has long been a problematic area for decentralized networks.

#### Verification:&#x20;

libp2p includes several security features, such as peer identity verification using public key cryptography and encrypted communication between nodes.

#### Fault tolerance:&#x20;

libp2p is designed to recover quickly from disruptions or failures. It also offers protection against network attacks through the use of mitigation techniques.

#### Support for PubSub (publish & subscribe):

This allows for the transmission and receipt of messages via the gossip protocol, meaning that nodes can listen out for and react to messages that affect them while ignoring the rest.

libp2p is interoperable, opening the door to future collaborations with other projects that use it.

Peers using libp2p are assigned a ’multiaddress’, a type of URL that encodes multiple layers of addressing information into a single “future-proof” path structure. It defines human-readable and machine-optimised encodings of common transport and overlay protocols and allows many layers of addressing to be combined and used together.  A multi-addresss looks like this:

`/ip4/139.59.181.245/tcp/37569/p2p/12D3KooWPHE8qcKL4CB2n8QvPpE25TRsP9nmkfeM6Qa61aAsokib`

> Importantly, on joining or rejoining the Network a node cannot simply pick its own XOR address
