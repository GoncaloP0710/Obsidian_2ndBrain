2025-01-02 17:11

Status: 

Tags: 

# Deterministic Encryption

- The property to preserve is equality of the plain texts.

Deterministic Encryption can be easily constructed in the symmetric key domain.
- Any mode of encryption, instantiated with fixed IVs/salts will be deterministic

Formally, this achieves a security notion called IND-DCPA.

In the public-key domain, no meaningful notion of security
can be achieved with Deterministic Encryption.
# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554342/mod_resource/content/5/dps-04-homomorphic%20encryption.pdf