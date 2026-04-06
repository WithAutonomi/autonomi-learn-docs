---
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/T1VY0u5KuOsTpycHpSka/how-it-works/encryption-and-authentication/self-authentication
---

# Self-Authentication

With data self-encrypted, and its many parts stored by their content address throughout the Network, any one single point of file access is removed, as by default the map to this data is not publicly accessible on the Network. [Self-Authentication](https://docs.maidsafe.net/Whitepapers/pdf/SelfAuthentication.pdf) means access to this data, and the means to reassemble it into information, always resides with the user, never leaving their device (i.e. not accessible to a ‘cloud’).&#x20;

Another key innovation of the Network—at no point does the Network ever store a user’s credentials, there is no chance of passwords being attacked, nor can any user’s data (individual, collective or organisation) be targeted on or via the Network.&#x20;

The authentication system utilises Boneh-Lynn-Shacham Distributed Key Generation (BLS), so that users can securely and anonymously access data, with no central server required to mediate the login process, nor are trusted third parties to store and manage the users’ credentials. It means users can reliably and securely access data from any machine, without ever sending or sharing their details.&#x20;

Furthermore, it also allows for multi-signature credentials for permission-less recovery, without a single point of failure.



{% hint style="info" %}
#### Deeper Dive…

[Self-Authentication White Paper — MaidSafe (2010)](https://docs.maidsafe.net/Whitepapers/pdf/SelfAuthentication.pdf) \[PDF]
{% endhint %}
