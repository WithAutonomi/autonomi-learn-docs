---
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/T1VY0u5KuOsTpycHpSka/how-it-works/encryption-and-authentication/multisig-credentials
---

# Multisig Credentials

Boneh-Lynn-Shacham Distributed Key Generation (BLS-DKG) is used to help users handle their authentication credentials so they don't automatically lose their data if they lose their key.

Credentials are thus extremely important, but credential loss can be a serious problem on decentralized networks where there is no central authority to help recover or reset forgotten passwords. The temptation may be to choose simple credentials that are easy to remember, but these will likely be insecure (easily guessed or cracked) and prone to collisions—other people may choose the same ones and inadvertently stumble upon the user's private information.

Autonomi requires _at least_ two separate credentials, generally referred to as 'access keys', with the option to add more. In combination, these access keys have sufficient entropy (randomness) to make collisions vanishingly unlikely.

Onboarding for the first time requires the user to choose a password (the first access key) from which a second access key is generated in the form of a passphrase (12 random words with a checksum), which the user writes down, perhaps keeping copies in a few safe places. \
\
With these two access keys, we have _something you know_ (the password), and _something you have_ (the passphrase), and in combination, we can generate a suitable amount of entropy to avoid collisions. This is the minimum requirement for creating your data store on the Network.

The user may also choose to create a third access key, a device key, on a trusted smartphone or computer, which is where BLS-DKG comes in, enabling a 2-of-3 key scheme, or even further to any k-of-n!

<figure><img src="https://lh7-us.googleusercontent.com/C9l5S6tZQSTlA7Bwox40KCYQG1XRRJok8TcjWbIv8cQ6HzTYoc2p4ApLCC3yKjoODOPJzaS1-Gd-xedQIyIns_H4TKkw5qiYdLfWYXV7uyvm8UkwzTHLAH1gqWY1U9bwTNtMKl262EtH" alt=""><figcaption></figcaption></figure>

Now instead of requiring the passphrase, on this trusted device the user can just use the password and the device key—_something you have_—maybe utilising some inbuilt biometrics too, for an element of _something you are_.

Additional access keys can be created to provide more flexibility and resilience. A backup passphrase is one example, and additional devices can be set up too. Then if the user forgets the password or loses a device, a combination of another device and or passphrase will allow the password to be reset.

In this way, Autonomi caters for people with security needs ranging from the everyday to the extreme.

<br>
