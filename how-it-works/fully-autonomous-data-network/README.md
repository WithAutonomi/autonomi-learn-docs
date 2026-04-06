---
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/T1VY0u5KuOsTpycHpSka/how-it-works/fully-autonomous-data-network
---

# Fully Autonomous Data Network

**Autonomi can be seen as a secure, encrypted, intelligent layer that sits on top of the current Internet, complementing the top three layers in the OSI model and adding resources in the application layer.**

Going a little deeper, Autonomi introduces some changes to the networking and application layers as shown below.

<figure><img src="../../.gitbook/assets/Network Layers &#x26; Autonomi.png" alt=""><figcaption><p>Autonomi compliments three of the seven networking layers in the OSI model for improved security, privacy and autonomy</p></figcaption></figure>

Many features of Autonomi are genuine innovations, but there is no intention to reinvent the wheel. It builds on existing decentralized technologies such as Kademlia and is based on the physical and data infrastructure of the Internet. Early development of Autonomi (formerly the SAFE Network) happened in parallel with blockchain, but it has taken an alternative route to solve the decentralization puzzle.

Autonomi can be seen as a secure, encrypted, intelligent layer that sits on top of the current Internet, complementing the top three layers in the OSI model and adding resources in the application layer. This enables secure, anonymous, decentralized data storage and networking.

Its core libraries are written in the Rust programming language. The diagram below shows the basic hierarchy.

**NOTE: The stack diagram below is outdated and will be replaced. The v2 stack is: ant-client / ant-sdk (developer interfaces) → saorsa-transport (shared transport abstraction with QUIC NAT traversal) → saorsa-core (Kademlia DHT routing, trust) → saorsa-pqc (post-quantum cryptography).**

<figure><img src="../../.gitbook/assets/image (8).png" alt=""><figcaption><p>The Autonomi Network Stack (to be updated for v2)</p></figcaption></figure>

Autonomi 2.0 is a permanent, immutable data store. Data integrity is guaranteed by the content-addressing of self-encrypted chunks and cryptographic verification by close group nodes at upload time.

Client connections are managed via a custom QUIC transport layer (saorsa-transport) with native NAT traversal, and are mediated via the client API. There is a command line interface (CLI) for this purpose, and apps written in Rust can access network functions directly via the API. Apps written in other languages do the same via the ant-sdk daemon and its REST/gRPC endpoints, with bindings available for 15 languages.

Nodes and clients provide the main means for users to interact with the Network, either by providing resources in return for payment by running a node or by storing data and interacting with data as a client.
