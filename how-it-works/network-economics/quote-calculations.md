---
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/T1VY0u5KuOsTpycHpSka/how-it-works/network-economics/quote-calculations
---

# Quote Calculations

Autonomi does not use a flat storage price. Instead, each node quotes a price based on how full it already is. The quote a node returns is based on how many records it is already storing, which gives the network a simple supply-and-demand signal without needing external oracles or manual price setting.

## Pricing Formula

Storage pricing follows a calibrated quadratic curve based on node fullness:

```
price_per_chunk_ANT(n) = 0.00390625 + 0.03515625 × (n / 6000)^2
```

Here, `n` is the number of records currently stored by that node. The non-zero baseline provides a spam barrier even when nodes are empty, and the quadratic term increases pricing as nodes fill up, pushing new uploads toward less-loaded parts of the network.

## Example Points

* `n = 0`: `0.00390625 ANT` (baseline only)
* `n = 6000`: `0.0390625 ANT`
* `n = 12000`: `~0.1445 ANT`
* `n = 24000`: `~0.566 ANT`

These points show how the baseline keeps pricing non-zero when nodes are empty, while the quadratic term makes prices rise much faster as nodes become more full.
