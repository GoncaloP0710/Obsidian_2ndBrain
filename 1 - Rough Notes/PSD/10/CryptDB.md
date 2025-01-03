2025-01-03 14:30

Status: 

Tags: 

# CryptDB

- An encrypted relational / SQL database
- The goal is to support (almost) all SQL queries w/ privacy and without requiring client modifications

CryptDB proposes using **encryption onions**
- Each onion is designed to support a different type of query
- Each onion layer preserves a different property
- Top layers are more secure but also more restrictive on computations
- Bottom layers allow more computations but are less secure

During queries, layers are peeled off as required.
Proxy converts DBMS query into encrypted query.

Security
- Security depends on the encryption schemes used
- As onion layers get peeled, security decreases

### Attacking CryptDB
- A system’s security is as strong as its weakest link.
- In CryptDB, if onions get peeled to DET and OPE, than an attacker can target those schemes with inference attacks.
- Inference attacks need an auxiliary source of information that is well correlated with the DB data.

### How to improve CryptDB’s Security
- CryptDB’s main problem is the DET and OPE encryptions, which have inherently limited security

There are 3 main ways to solve this problem:
- Use efficient cryptographic primitives that deal with snapshot attackers
- Use stronger cryptographic primitives
- Use **trusted hardware**
# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/575695/mod_resource/content/4/dps-10-advanced%20crypto%20systems.pdf