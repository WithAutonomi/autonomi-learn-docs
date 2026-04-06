---
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/T1VY0u5KuOsTpycHpSka/how-it-works/network-architecture/building-on-kademlia
---

# Building on Kademlia

The first step in understanding the architecture of Autonomi is to take a look at distributed hash tables. These are structures that map a unique ID to something on the distributed network, be that data, a device or a service.

Kademlia is a distributed hash table (DHT) protocol which provides a way for millions of computers to self-organize into a network, communicate with other computers on the network, and share resources between devices, all without a central controlling entity.

Petar Maymounkov and David Mazières released the Kademlia distributed hash table in 2002. The idea is that nodes form a network overlay, and are identified with a different node identification system. So a node with an IP address of 96.251.182.97 might have a 256-bit XOR address that looks like this: `17846cb8a4b53c9e44c616d2415a15984283eee975a1dac8f488dd91d0aed1cd`.

Bitwise Exclusive OR (XOR) has the feature that each address is a unique distance from any other address in the address range. XOR distance bears no relation to physical distance. Indeed, two pieces of data on the network may be very close XOR-wise but be sitting on machines located on opposite sides of the world.

With potentially millions of devices on a network, there's no way a single node could keep track of them all without running out of resources. Instead it keeps a record (a routing table) containing information about a small number of other nodes and lets the magical uniqueness of XOR distances do the rest.

Each node is a unique distance from every XOR address in the space, which means its routing table is also unique. The address space is enormous: 2^256 is more than the number of atoms in the universe. To make this space manageable it is broken into k-buckets. The furthest away bucket (in terms of XOR distance) contains half the network, the next furthest away represents a quarter of the network, the next furthest an eighth, and so on.&#x20;

Autonomi is based on Kademlia. Each node's routing table contains information on up to 20 nodes in each k-bucket. This means it knows everything about the nodes in the address space close to it, but very little about space furthest away—but crucially it does know some nodes in that space, and those nodes, of course, know everything about other nodes close to them and can pass messages on. The bigger the Network becomes, the more secure it will get because an individual node will have influence over a decreasing range of addresses.

Every piece of data has a unique address; in the jargon it is ‘[content-addressable](content-addressable-storage.md)’—its content defines where it is stored. When a node wants to retrieve a piece of data, it checks its address, then asks the node closest to that address whether it's holding the data. That node in turn checks the address and sees whether it knows a node that's closer. If it does, it passes the message on to that node, and so on, until it reaches the node that's actually holding the data. The same messaging process happens when saving data too. It is very fast and efficient, with the enormous address space being traversable in just a few hops.&#x20;

In the Autonomi Network, a node's closest neighbours (again, in XOR terms) are called its ‘close group’. Data stored at a node is automatically replicated to the nodes in its close group for redundancy. As nodes leave and others join (a process known as churn) the node's close group will change. The size of the close group is defined by a tuneable parameter, currently it is set at 5.

So, nodes must constantly update their routing tables. They do this by observing which nodes are alive, dead and newly arrived during the course of their day-to-day operations.
