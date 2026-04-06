---
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/T1VY0u5KuOsTpycHpSka/how-it-works/consensus-not-required/conflict-free-replicated-data-types
---

# Conflict-free Replicated Data Types

There's another way to drive consistency asynchronously across a decentralized network without consensus: Conflict-free Replicated Data Types, or CRDTs.&#x20;

With CRDTs consistency is inherent in the data structure itself. If different versions of the same data exist across a set of connected nodes (or replicas as they are known in CRDT-speak), they will all eventually converge on the same state. If some data is changed on an offline replica, as soon as connection is re-established this change will propagate to all other replicas, even if the same data was changed on another replica in its absence. At the end of the process, everyone will have the exact same version.

In asynchronous decentralised networks, each node can perceive a different order of events. With CRDTs it is not necessary to try to enforce an order or agree on it before changes can be applied.&#x20;

CRDTs can range from simple counters to more complex structures, such as documents on which many people collaborate. Because CRDTs follow a strict set of rules based on metadata contained within their structure, conflicts (i.e. the persistence of multiple states of the same data) are automatically avoided without any special code or user intervention required.

Not every data structure can be a CRDT, but where it's possible it makes the job of ensuring consistency significantly easier. Changes can be made locally to CRDTs in complete confidence that they will be valid whatever may be happening elsewhere.

On Autonomi all mutable data types are CRDTs

<br>
