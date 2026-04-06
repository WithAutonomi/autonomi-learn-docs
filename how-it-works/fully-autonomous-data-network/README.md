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

Many features of Autonomi are genuine innovations, but there is no intention to reinvent the wheel. It builds on existing decentralized technologies such as Kademlia and libp2p and is based on the physical and data infrastructure of the Internet. Early development of Autonomi (formerly the SAFE Network) happened in parallel with blockchain, but it has taken an alternative route to solve the decentralization puzzle.

Autonomi can be seen as a secure, encrypted, intelligent layer that sits on top of the current Internet, complementing the top three layers in the OSI model and adding resources in the application layer. This enables secure, anonymous, decentralized data storage and networking.

Its core libraries are written in the Rust programming language. The diagram below shows the basic hierarchy.

<figure><img src="../../.gitbook/assets/image (8).png" alt=""><figcaption><p>The Autonomi Network Stack</p></figcaption></figure>

In order to guarantee strong consistency, the Network uses [conflict-free replicated data types](https://bartoszsypytkowski.com/the-state-of-a-state-based-crdts/) (CRDTs) for storing data.&#x20;

Client connections managed by libp2p are mediated via the client API. There is a command line interface (CLI) for this purpose, and apps written in Rust can access network functions directly via the API. Apps written in other languages do the same via the language bindings layer.&#x20;

Nodes and clients provide the main means for users to interact with the Network, either by providing resources in return for payment by running a node or by storing data and interacting with data as a client.
