---
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/T1VY0u5KuOsTpycHpSka/how-it-works/encryption-and-authentication/self-encryption
---

# Self-Encryption

**All content (documents, images, videos, etc.) on Autonomi are encrypted.**&#x20;

When a client uploads a piece of content to the Network (for example a video) it is first broken into chunks. Those chunks are then ‘self-encrypted’, a process patented by MaidSafe by which each chunk is encrypted using its own hash and the hashes of the two previous chunks in the same file. These encrypted chunks are then hashed again to arrive at the XOR Network address where the chunk will be stored.&#x20;

At the same time, a ‘data map’ is created on the client device, which maps the chunk number to the XOR network address of the chunk and the hash to decrypt it and its two successors, allowing the content to be recreated. A number of copies of each chunk are stored by nodes in the Section to ensure redundancy.

Data maps and other metadata are not encrypted, but on the network they are kept inside encrypted folders if the data is private.

The client retains the data map for the content it has uploaded and keys to decrypt it locally. That way no keys or passwords need ever leave a person's device. Users can choose to share content with others by sharing their keys / data map with them. They can also choose to make the content fully public, in which case the folders containing the relevant files are unencrypted.

{% hint style="info" %}
#### Deeper Dive…

[Self-encrypting Data — MaidSafe White-paper (2010)](http://docs.maidsafe.net/Whitepapers/pdf/SelfEncryptingData.pdf) \[PDF]
{% endhint %}

<br>
