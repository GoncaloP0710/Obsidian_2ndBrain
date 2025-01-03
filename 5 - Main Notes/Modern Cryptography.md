2025-01-02 15:18

Status: #done 

Tags: [[Data Privacy and Security]] [[Cryptography]]

# Modern Cryptography

Based on formal definitions, principles and rigorous proofs.

Three foundational principles:
- Formal Definitions
- Precise Assumptions
- Proofs of Security

Formal definitions give a clear description of the threats considered and the security guarantees desired. Provide a way to analyze and evaluate different schemes. And provide a way to meaningfully compare schemes.

A **threat model** specifies the “power” an attacker is assumed to have.

- Ciphertext-Only Attacks (COA)
- Known-Plaintext Attacks (KPA)
- Chosen-Plaintext Attacks (CPA)
- Chosen-Ciphertext Attacks (CCA) 

Most modern cryptographic constructions cannot be proven secure unconditionally. As such, any required **assumptions** should be clearly and precisely stated.
If we can prove that a scheme satisfies a given definition under some assumptions, then we have a guarantee for its security.

## Proofs of Security
Security proofs are usually built through **reduction**.
If we can reduce the problem of breaking a scheme to the problem of breaking its assumptions, then the scheme’s security will hold as long as the assumptions hold.

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554340/mod_resource/content/7/dps-01-02-concepts.pdf