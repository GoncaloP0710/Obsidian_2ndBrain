2025-01-02 17:38

Status: #done 

Tags: [[Data Privacy and Security]] [[Security]] [[Encryption]] 

# Attribute-based Encryption

ABE allows for a ciphertext to be decrypted only by users that match a predefined set of attributes, and no one else.

There are 2 sub types of ABE:
- Key-Policy ABE (KP-ABE)
- Ciphertext-Policy ABE (CP-ABE)

### Key-Policy ABE (KP-ABE)
- Ciphertexts are associated w/ a set of attributes.
- Secret key is associated w/ a policy

### Ciphertext-Policy ABE (CP-ABE)
- Secret keys are associated w/ a set of attributes
- Ciphertexts are associated w/ a policy

## Fuzzy IBE (A first attempt at constructing ABE)

In fuzzy IBE, a user has a set of attributes and it can decrypt a message if a subset of at least d of these match those of the ciphertext.

Generalized ABE (both KP and CP) can be constructed by extending the same idea and using an additional tree-based data-structure. In this tree, leaf nodes are attributes and interior nodes are logical gates.

![[Attribute-based Encryption 1.png]]


# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554343/mod_resource/content/4/dps-05-functional%20encryption.pdf