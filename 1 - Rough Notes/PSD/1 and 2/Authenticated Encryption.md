2025-01-02 15:35

Status: 

Tags: 

# Authenticated Encryption

How can we protect Privacy+Integrity?
Authenticated encryption aims at preventing these attacks.

In authenticated encryption, a message is protected regarding both **secrecy and integrity**.

Authenticated encryption implies two notions:
- CCA-security
- Unforgeability

If a CPA-secure encryption scheme provides secrecy, and MACs provide integrity, then any combination of these should provide secure authenticated encryption.

Encrypt then Authenticate:
- m is first encrypted and then t is built over the result

## Non-Malleability
Any encryption scheme that allows ciphertexts to be manipulated in some way cannot be CCA-secure. This is due to CCA-security implying the property of **non-malleability**.

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554340/mod_resource/content/7/dps-01-02-concepts.pdf