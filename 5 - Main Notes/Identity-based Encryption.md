2025-01-02 17:26

Status: #done 

Tags: [[Data Privacy and Security]] [[Security]] [[Encryption]] 

# Identity-based Encryption

IBE is a public-key cryptosystem where any string is a valid public key.
- This means that anyone can send encrypted messages to recipients without the need to setup public keys in advance nor establish a Public-Key Infrastructure (PKI).
- Example public keys: an email address, a date, a username, etc...

Formally, IBE is a functional predicate encryption w/ public index.

## Pairing-based Cryptography (PBC)
They let us “cheat” and solve the basic assumption behind the
security of public-key crypto (computational Diffie-Hellman problem)

Pairing-based cryptography is a field of cryptography that leverages **bilinear pairings** on elliptic curves to create efficient and powerful cryptographic protocols. It enables novel functionalities like **identity-based encryption**, **attribute-based encryption**, and advanced multi-party computations.

## Other variants of IBE:

- Hierarchical IBE (HIBE) 

Extends IBE to support multiple PKGs, organized in hierarchies.
Users from a domain request their secret keys from the PKG for that domain, and PKGs request their master keys from a root PKG.

- Anonymous IBE (AIBE)

Ciphertexts should not reveal the identity of the receiver.

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554343/mod_resource/content/4/dps-05-functional%20encryption.pdf