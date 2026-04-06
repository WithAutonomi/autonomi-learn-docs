---
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/T1VY0u5KuOsTpycHpSka/how-it-works/network-architecture/content-addressable-storage
---

# Content-Addressable Storage

Content stored on Autonomi is first broken into chunks, hashed and then encrypted, in a unique process known as [Self-Encryption](../encryption-and-authentication/self-encryption.md). Those chunks are run through a hashing algorithm to create a unique 256-bit hash for each chunk. Only chunks that are exactly identical will have the same hash value. This hash serves as the XOR address on the Network where that chunk will be stored, which in turn determines the nodes that will manage it.

Chunks with hashes that lie within a certain address range (say 000010... to 000011...) will be secured, stored and managed by the nodes whose IDs are closest (in XOR terms) to that address. These will change over time as new nodes join and others leave.

{% hint style="info" %}
The hash of a chunk of data serves as the XOR address on the Network where it will be stored, which in turn determines which nodes will manage it
{% endhint %}

Nodes are paid for data chunks they hold, but not for replicated data. They are expected to hold replicated data as a condition of participating in the network and having the chance to earn.

As nodes fill up, the [price of storing a chunk of data rises](/broken/pages/f28SMy5nhNUhU9OtLWKf). All nodes on the Network fill up at more or less the same rate although there will be some local variations and hence a range of prices.

Nodes cache data when a new close node appears and they share some of their primary data store with that node. This cache isn't included in the fullness calculations. It is just something they are required to do to ensure smooth data transfer. For security, nodes cannot delete or edit data, only store and move it.&#x20;

libp2p allows for the existence of specialised nodes for providing services such as caching. These will be introduced in later iterations of the Autonomi Protocol.

It's important to note that all the features above emerge from simple local interactions between nodes. Likewise, the codebase is simple, making it easier to maintain, update, audit and secure.

<br>
