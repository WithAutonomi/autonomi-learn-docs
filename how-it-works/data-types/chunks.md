---
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/T1VY0u5KuOsTpycHpSka/how-it-works/data-types/chunks
---

# Chunks

A chunk is an immutable data type. Its Network address is derived from the hash of its content. This means the file cannot be edited in any way after it has been uploaded—any change would alter the hash and therefore its address meaning it could not be found. The data chunks are created by [self-encryption](../encryption-and-authentication/self-encryption.md).

Data deduplication is a unique feature of Autonomi and a side benefit of the process of self-encryption. Two identical chunks will have the same hash value, and therefore only one (plus a few copies for redundancy) need be stored on the Network.

Chunks can be cached by clients, and fetching the same chunk next time can be quicker. Autonomi also has a planned feature called ‘opportunistic caching’ in which more copies of popular data are created closer to where it is being requested.

<br>
