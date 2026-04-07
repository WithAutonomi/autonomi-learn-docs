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
