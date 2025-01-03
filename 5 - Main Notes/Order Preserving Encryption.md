2025-01-02 17:14

Status: #done 

Tags: [[Data Privacy and Security]] [[Security]] [[Encryption]]

# Order Preserving Encryption

First proposed in the database community in 2004, OPE is a form of deterministic encryption that additionally preserves order relations.

## Hypergeometric Distribution
However, there are 2 main issues w/ the previous scheme.
- the scheme **leaks** not only **order** but also the **relative distance** between ciphertexts.
- encrypted values take a numeric form.

# Order Revealing Encryption

ORE improves on the security of OPE by preventing ciphertexts from being numeric values and directly comparable.

Instead, ciphertexts can take any format (e.g., random bytes) and a function 𝒄𝒐𝒎𝒑(. , . ) is introduced and used to give the order relation between two ciphertexts.

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554342/mod_resource/content/5/dps-04-homomorphic%20encryption.pdf