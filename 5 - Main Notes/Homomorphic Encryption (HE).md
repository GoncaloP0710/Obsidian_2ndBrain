2025-01-02 16:51

Status: #done 

Tags: [[Data Privacy and Security]] [[Security]] [[Encryption]] 

# Homomorphic Encryption (HE)

The goal is to support arbitrary computations over encrypted data.
- Computations expressed as additions and multiplications

Additions and multiplications are relevant because they can be used to express any computation.

Homomorphic Encryption can be categorized in four groups:
- Partially-Homomorphic Encryption: Schemes that allow only additions or multiplications of ciphertexts, but not both.
- Somewhat Homomorphic Encryption
- Levelled Homomorphic Encryption
- Fully Homomorphic Encryption: Schemes that allow arbitrary circuits with any depth and gate type.

## Partially Homomorphic Encryption (PHE)
Multiplicatively-Homomorphic Encryption Schemes:
- Unpadded RSA, ElGamal

Unpadded RSA is deterministic and hence provides only COA-Security.
ElGammal provides CPA-Security since encryptions depend on secret values 𝒚, making them probabilistic.

## Fully Homomorphic Encryption
A Somewhat Homomorphic Encryption (SWHE) scheme is one that supports both additions and multiplications, however these operations are “**noisy**”.
In SWHE the noise grows exponentially with each homomorphic
operation.
This means that only a few operations will be possible until the noise
grows too large.

Additionally, if a SWHE can evaluate its own decryption function, we say it is also **bootstrappable**.
The goal of bootstrapping is to “refresh” the encryption and **reduce the**
**noise** back to acceptable levels.
If a **boostrapple SWHE** can bootstrap its encryptions an unlimited number of times, then it can be turned into a **FHE**.
# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554342/mod_resource/content/5/dps-04-homomorphic%20encryption.pdf