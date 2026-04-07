---
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/T1VY0u5KuOsTpycHpSka/how-it-works/network-economics/quote-calculations
---

# Quote Calculations

The pricing within The Network is determined by a supply-and-demand mechanism. Each node assesses its internal resource availability to calculate the price it needs to charge. Specifically, a node compares the number of records it is responsible for storing against the maximum capacity of records a node is allowed to hold.

Because The Network uniformly distributes the addresses of both nodes and records, the number of records assigned to each node accurately reflects the ratio between the total number of nodes (indicating storage space supply) and the total number of records (indicating storage space demand).

Autonomi Network Tokens (ANT) — an ERC-20 token on the Arbitrum One network — serve as the network’s currency. Payments are made on-chain via Arbitrum. As a result, the effective payment amount in ‘FIAT’ terms depends on the ANT token’s market value, which will be inherently volatile. To address this, prices are normalized by the token price, ensuring that The Network's size and functionality are governed by the true supply and demand for storage space, rather than fluctuations in market conditions.

Note: The number of nodes in The Network is constrained by the availability of raw resources such as disk space, bandwidth, and CPU power. Consequently, the node count alone should not be used to infer the total network capacity, as this would incorrectly assume that disk space is the sole limiting factor.

**The v2 pricing formula is a quadratic function of node fullness:**

**Price = (record\_count / 6000)² ANT per chunk**

Where `record_count` is the number of records currently stored by that node. Prices rise slowly when nodes are empty and accelerate sharply as they fill up. No external oracles, no governance votes — the price emerges from network state. Prices are verified through neighbourhood record count maintenance: nodes in a close group track what their neighbours hold and can detect inconsistent pricing claims.

**NOTE: The charts below may need updating to reflect the v2 quadratic pricing curve.**

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

<div align="left"><figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure></div>

<figure><img src="../../.gitbook/assets/image (1).webp" alt=""><figcaption></figcaption></figure>

As it can be seen from the charts above, the fair storage price will initially rise. The system must overcome this initial price resistance to benefit from the subsequent decline in price, driven by increasing data upload rates and decreasing raw resource costs. To address this **initial friction**, The Network will provide additional incentives to node operators during The Network's early stages - derived from an emission allocation.

To do this The Autonomi Foundation will mint new Autonomi Network Tokens (ANT) and distribute them to the participating node operators.

**Payment Optimisation:** For large uploads, Merkle Tree batch payments reduce on-chain cost from O(n) per chunk to O(1) per batch — a single Merkle root submission on Arbitrum covers an entire batch of chunks. This makes large-scale archiving economically practical. Every storage payment burns 1% of the ANT spent, creating deflationary pressure proportional to network usage.
