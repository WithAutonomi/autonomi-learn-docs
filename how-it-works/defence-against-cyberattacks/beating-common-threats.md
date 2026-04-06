---
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/T1VY0u5KuOsTpycHpSka/how-it-works/defence-against-cyberattacks/beating-common-threats
---

# Beating Common Threats

### Sybil attacks

Sybil attacks involve malicious actors generating multiple fake identities, known as Sybil nodes, in an attempt to control operations. With sufficient Sybil nodes controlling part of the address space, a malicious actor could block access to certain content, for example. \
\
Autonomi detects Sybil attacks by estimating the network size using a statistical method KL Divergence. This compares the real distribution of node IDs (i.e. their network addresses) with the theoretical one. A significant difference between the two could indicate a Sybil attack. At this point nodes looking for data at a certain address will broaden their search to include a wider range of peers than normal. Even if all nodes closest to a chunk of data are compromised, it may still be accessed via nodes that are further away.

### Man in the Middle attacks

_MitM_ attacks rely on data being unencrypted or the victim’s browser accepting the attacker's certificate instead of the website’s certificate. They will not work on Autonomi.

### DDoS

Exceptionally difficult as there is no single point to attack. The Network will simply re-route around any nodes that are taken down.

### Quantum computing&#x20;

Self-Encrypted data is considered 'quantum secure’, meaning that it cannot currently be defeated by a brute force attack, even with a quantum computer. \
\
On top of that, the volume of encrypted packets means that there could only be targeted attempts at decryption, and decentralization makes such targeting difficult.

### **Phishing & Key-logging etc**&#x20;

While there is some feasibility to these attacks, as the Network cannot protect endpoints such as a device itself, such an attack would only compromise the user’s own data. Using such a compromise as a springboard for a wider attack on a database, or swaths of Network data, is just not possible, and would be of dubious value to an attacker outside of a highly targeted hack.

### Ransomware

Files are stored in immutable data and cannot be changed, so ransomware cannot encrypt it, but it could potentially delete Data Maps or hide them, making data inaccessible.

<br>
