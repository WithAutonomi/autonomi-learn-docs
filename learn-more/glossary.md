---
metaLinks:
  alternates:
    - https://app.gitbook.com/s/T1VY0u5KuOsTpycHpSka/learn-more/glossary
---

# Glossary

### ANT

ANT or $ANT was the former exchange ticker for [Autonomi Tokens](glossary.md#autonomi-tokens-usdautonomi), now $AUTONOMI

### ant

The command-line interface (CLI) for direct interaction with the network. It is part of [`ant-client`](https://github.com/WithAutonomi/ant-client).

### antd

The local daemon used by the SDKs and language bindings. It is part of [`ant-sdk`](https://github.com/WithAutonomi/ant-sdk).

### Autonomi

An autonomous data network built on the Autonomi Protocol that supports a rich application ecosystem to be created by developers and enjoyed by participants.

### Autonomi Tokens ($AUTONOMI)

Short for is an ERC20 standard token that will be distributed (see ‘[Token Allocation](../how-it-works/network-economics/token-supply.md)’), as well as spent and earned by using and/or supporting the Autonomi Network. A ‘$’ sign maybe used in front of it to indicate that it is a cryptocurrency.

### Autonomi Foundation

Often referred to just as _the Foundation._ A Swiss non-profit that facilitates, supports, funds and promotes the research and development of the Protocol, as well as enables the ongoing delivery, maintenance and adoption of the Network and its technologies. Formerly known as the Safe Network Foundation.&#x20;

### Autonomi Protocol&#x20;

Often referred to just as _the_ _Protocol_. A collection of open source algorithms, libraries and components that allows computers to form an autonomous data network

### Arbitrum One

A layer-2 scaling solution for Ethereum, enhancing speed and reducing costs for transactions while maintaining Ethereum's security.

### Asynchronous

Not time-dependent. A system that supports asynchronicity should come to consensus no matter what order the various messages arrive in.

### Boneh-Lynn-Shacham Distributed Key Generation (BLS-DKG)&#x20;

A cryptographic system that authenticates the sender of a message, allows for multiple parties to quickly come to a consensus, and can enable multi-signature transactions and n-of-k credentials

### Byzantine Fault Tolerance&#x20;

The ability of a decentralized network to function properly even if up to a third of the nodes (plus 1) is corrupt or faulty

### CashNote

Encrypted digital ‘cheque’ for a given value containing all the necessary information for the owner of the associated secret key to spend that value.

### Churn&#x20;

Nodes joining and leaving the Network

### Chunk

An immutable data type

### Client

Software that allows users to connect to the Network and make use of its services

### Close Group

A Close Group is a small number of nodes that look after a specific piece of data, and that only exist as a group for that specific data. \
\
This system of close groups allows nodes to act independently, but together to form a strong autonomous global network, capable of storing and retaining data in perpetuity.

### Conflict-free Data Types (CRDTs)

Data structures that obey certain mathematical rules which ensure that when multiple versions of data exist across a distributed network, eventually these will always converge onto one ‘true’ version

### Data map

A record of content chunks and their corresponding locations on the Network. Only users in possession of the data map can recreate the file

### Data payment

A one-time payment made upfront for data storage, distributed to Nodes as [Resource Supply Rewards](glossary.md#resource-supply-rewards).

### Distributed hash table

A map of where data is stored on a distributed network

### FIAT

FIAT currency is money declared by a government to be legal tender, not backed by a physical commodity. "Fiat" comes from Latin, meaning "let it be done," indicating it’s value by decree.

### Fault detection

Detecting nodes that are acting suspiciously and removing them from the routing table.

### [Kademlia](../how-it-works/network-architecture/building-on-kademlia.md)

A distributed hash table (DHT) protocol which provides a way for millions of computers to self-organize into a network.

### L2 / Layer 2

A scaling solutions built on top of a blockchain (Layer 1) to increase transaction speed and reduce costs.

### MaidSafeCoin

A cryptocurrency token created during a crowd-sale in April 2014 that supported the development of Autonomi.\
There are both Omni (MAID) and ERC-20 (EMAID) variants of MaidSafeCoin.

### Maximum Supply

Total number of whole Autonomi Network Tokens created over the Network’s lifetime: 1,200,000,000 (1.2 Billion) tokens.

### MASQUE relay

A relay path used as a last resort when direct connection and hole punching cannot connect two peers.

### Multiaddress

A unique locator for a peer that encodes multiple networking protocols into a single address

### Native Token

A non-blockchain token running on Autonomi to be introduced after the early phase/launch of The Network.

### NAT traversal

The set of techniques that help devices behind routers and firewalls connect to each other without manual port forwarding.

### [Node](../how-it-works/fully-autonomous-data-network/nodes.md)

A machine that connects with others using Autonomi's Protocol to form the Network.&#x20;

### Node Network Reserve

18% of data payments (up to 10% of maximum supply) are sent to this allocation for node operators. This allocation will be used to support payments to nodes should the network upload values experience volatility. If the Node Network Reserve holds 10% of the network’s Maximum Supply of tokens, 18% payment reduces to 2%, with the 2% payment burned (removed from Maximum Supply).

### PeerId

The node's network identifier. Other nodes use it to recognize a node and measure how close it is to other peers and data in the network.

### Proof-of-Resource

A system that rewards nodes based on the quality of the service they provide, making it economically disadvantageous for them to misbehave

### Proof of Work

The consensus algorithm used by the Bitcoin blockchain and others to confirm that transactions are valid and to deter attacks.

### Proof of Stake

The consensus algorithm used by the Etherum blockchain and others in which voting power is proportional to wealth.

### RPC (Remote Procedure Call) endpoint

Allows a program to execute code or perform operations on a remote system as if it were a local function call. RPC is designed to hide the details of the network communication from the programmer. You call a function as if it's local, but it's executed remotely.

### QUIC

A modern transport protocol built on UDP. Autonomi uses it for secure peer connections and NAT traversal coordination.

### Resource Supply Rewards&#x20;

Payment to the operators of resource-providing nodes in return for storing data. Also referred to as Data Payments.

### saorsa-transport

The shared transport layer used by Autonomi and [x0x](https://github.com/saorsa-labs/x0x) for peer connections, NAT traversal, and relay fallback. The source repo is [`saorsa-transport`](https://github.com/saorsa-labs/saorsa-transport).

### Safe Network

The former name for Autonomi

### [Self-Encryption](../how-it-works/encryption-and-authentication/self-encryption.md)&#x20;

The client-side process that breaks uploaded content into encrypted chunks and creates the Data Map needed to reconstruct it later. It uses BLAKE3 for chunk hashing and ChaCha20-Poly1305 for authenticated encryption.

### Spend

Transaction information stored on the Network.

### Stigmergy

An indirect mechanism of coordination between actors, in which the trace of an action stimulates the performance of a subsequent action.

### Storage Reward Rate

An adjustable factor that determines the rate of pay of participating nodes; it is increased when more storage is needed, decreased when there is an excess of storage space

### Tokens

The Autonomi Network Token (’ANT’) are earned by storing data and spent by uploading data. For purposes of these docs they may simply be referred to as ‘tokens’.

### Token Generation Event (TGE)

The Token Generation Event represents both the Genesis of the Autonomi Network Token _and_ the point at which its distribution begins.

### Tokens Emissions

240,000,000 tokens, representing 20% of the Maximum Supply, will be emitted at a diminishing rate over a period of 12 years.

### Transfer

A monetary transaction on the Network.

### XOR address

A unique 256-bit number; every entity on the Network has an XOR address

### x0x

A complementary layer for realtime, mutable, or collaborative behavior. Autonomi stores permanent, immutable data; [`x0x`](https://github.com/saorsa-labs/x0x) handles live interaction and shared state.

<br>
