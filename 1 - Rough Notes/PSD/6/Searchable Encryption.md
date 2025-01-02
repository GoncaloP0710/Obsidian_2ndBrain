2025-01-02 18:00

Status: 

Tags: 

# Searchable Encryption

Searchable Encryption (SE) deals w/ the problem of how to encrypt a remote database in such a way that it can be privately and efficiently queried.

SE can be categorized in:
- Public-key Searchable Encryption
- Searchable Symmetric Encryption

A very easy way to solve the problem is to use Deterministic Encryption.
- Encrypt each keyword w/ a deterministic scheme

However, this leaks a lot of information.
- The server immediately learns how many times a keyword is repeated

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554344/mod_resource/content/5/dps-06-searchable%20encryption.pdf