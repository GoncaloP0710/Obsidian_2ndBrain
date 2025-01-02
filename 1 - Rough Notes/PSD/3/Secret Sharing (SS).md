2025-01-02 15:42

Status: 

Tags: 

# Secret Sharing (SS)

Secret sharing consists in encrypting a message m in such a way that n ciphertexts are produced, instead of only one.

More formally, a SS scheme is composed of 2 algorithms:
- Share: Takes a message 𝐦, the threshold 𝒕 and the number 𝒏 of shares to generate, outputting the generated shares.
- Reconstruct: Recovers message 𝑚 from shares.

## Shamir’s Secret Sharing
The scheme is based on the **Lagrange interpolation** theorem, which states that any **t points** suffice to uniquely determine a **polynomial of degree t-1**.

Performance
- The cost of generating polynomials will mostly depend on their **degree** and the **size of the secret**.

Security
- Shamir’s SS provides **perfect secrecy**.

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554341/mod_resource/content/5/dps-03-secret%20sharing.pdf