---
metaLinks:
  alternates:
    - https://app.gitbook.com/s/T1VY0u5KuOsTpycHpSka/how-it-works/data-types
---

# Data types

A data type is a classification which describes how data can be created, transformed and used. All programming languages use them, and common examples include integer, string and boolean.

Autonomi provides two native data types for storing and retrieving data: chunk and register. Registers are mutable data types, whereas Chunks are immutable.&#x20;

Data itself comes in different forms too. Content or binary data is always encrypted and is spread out over the Network as immutable chunks. It can be read by anyone with a data map, which shows how to decrypt and reconstruct the content from its constituent chunks. The data also holds other metadata such as filename and type (video, image, etc). \
\
So a 'file' on the Network is really a set of instructions for finding the content's immutable constituent parts and assembling them to recreate the original content, together with information about what will be returned when you do.

<br>
