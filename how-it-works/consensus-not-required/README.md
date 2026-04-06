---
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/T1VY0u5KuOsTpycHpSka/how-it-works/consensus-not-required
---

# Consensus Not Required

### A Hard Problem

Truly decentralized networks can have no master node or oracle to judge what is true or valid and what is not. Instead, the nodes that make up the Network must come to an agreement among themselves about which of many possible versions of “the truth” they will accept and the order in which events occur. This is challenging because each node has a different view of events. They must find a way to converge.

### Decentralized conflict resolution

The bitcoin blockchain uses Proof of Work (PoW) to solve these problems of achieving decentralized consensus over the ordering of events to prevent the problem of double-spend – being able to spend the same coin twice – and Byzantine behaviour. Miners battle to verify a block of transactions. If there are two simultaneous winners the chain will split and for a time there are two versions of the truth, i.e. two chains emanating from the disputed block. Ultimately, though, after a few blocks have been added one chain will be longer than the other, and it is this chain that will be accepted as the true state.

PoW has proved largely effective against the Sybil attack, also known as the 51-percent attack, where one entity owns more than half of the mining power, but it is slow, massively energy-intensive and it doesn’t scale. Also, the consensus is probabilistic rather than deterministic: after some time, you might be 99.9 percent sure that all nodes agree on network state, but never 100 percent.

Other blockchains such as ethereum use Proof of Stake (PoS). While much more environmentally friendly, there is a tradeoff in terms of equability in that larger holders of the currency have more power.

Autonomi is _naturally secure_, meaning that it doesn't need any artificial slowing down or behavioural assumptions to keep data safe. It does not use PoW or PoS for consensus.&#x20;

Instead it uses a system similar to that utilized by ants, [Stigmergy](stigmergy.md), plus a combination of lightweight mechanisms including [Conflict-free Data Types (CRDTs)](conflict-free-replicated-data-types.md) and constant tests that nodes are reliable.\
<br>
