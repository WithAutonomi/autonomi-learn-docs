---
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/T1VY0u5KuOsTpycHpSka/how-it-works/encryption-and-authentication
---

# Encryption and Authentication

Content on Autonomi is stored as encrypted chunks. The original content can be recreated from these chunks, provided we have a map of where the chunks are plus the keys to decrypt them. \
\
A 'file' on the Network is really a collection of chunks, with a datamap that allows us to discover all the chunks and decrypt the file.&#x20;

Files are kept in folders which are created as part of the [Self-Encryption](self-encryption.md) process and are encrypted, meaning their contents are only accessible to their owner by default.

The API for upload by default self-encrypts all files.

{% hint style="info" %}
#### Keeping it Simple

All content on Autonomi is encrypted by default. When content is stored on the Network it is first broken into chunks, hashed and then encrypted and these chunks are themselves encrypted using the hash of another chunk from the same file. This is ‘self-encryption’—a method patented by MaidSafe but now open-sourced. When content is made public, its containing folder is decrypted, meaning anyone can reassemble the chunks.
{% endhint %}

At the network level, the Autonomi uses the TCP, UTP and µTP protocols and all the data moved by these protocols is encrypted from 'bit 1'.&#x20;

So communications between the Network and the user are always encrypted, never in plain text. Note that any node on the Network can be used as a bootstrap server so long as its IP address is added to the configuration file of the joining node. It does not have to be one provided by MaidSafe.
