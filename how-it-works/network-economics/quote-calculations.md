---
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/T1VY0u5KuOsTpycHpSka/how-it-works/network-economics/quote-calculations
---

# Quote Calculations

Autonomi does not use a flat storage price. Instead, each node quotes a price based on how full it already is.

Autonomi Network Tokens (ANT) are used to pay for storage on Arbitrum One. The quote a node returns is based on how many records it is already storing, which gives the network a simple supply-and-demand signal without needing external oracles or manual price setting.

## Pricing Formula

Storage pricing follows a calibrated quadratic curve based on node fullness:

```text
price_per_chunk_ANT(n) = 0.00390625 + 0.03515625 × (n / 6000)^2
```

Here, `n` is the number of records currently stored by that node. The non-zero baseline provides a spam barrier even when nodes are empty, and the quadratic term increases pricing as nodes fill up, pushing new uploads toward less-loaded parts of the network.

## Example Points

- `n = 0`: `0.00390625 ANT` (baseline only)
- `n = 6000`: `0.0390625 ANT`
- `n = 12000`: `~0.1445 ANT`
- `n = 24000`: `~0.566 ANT`

These points show how the baseline keeps pricing non-zero when nodes are empty, while the quadratic term makes prices rise much faster as nodes become more full.

## Payment Optimization

For larger uploads, Merkle tree batch payments reduce on-chain cost from `O(n)` per chunk to `O(1)` per batch. A single Merkle root submission on Arbitrum can cover an entire batch of chunks, which keeps large uploads more practical by reducing transaction overhead.

## Early-Stage Incentives

The network also includes early-stage incentives for node operators, funded through an emission allocation. The goal is to support participation while the network is still growing and the storage market is still finding its footing.

The Autonomi Foundation can mint new Autonomi Network Tokens (ANT) from that allocation and distribute them to participating node operators.
