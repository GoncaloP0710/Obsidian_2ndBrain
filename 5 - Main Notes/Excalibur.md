2025-01-05 15:52

Status: #done 

Tags: [[Data Privacy and Security]] [[Security]] [[Data Base]] 

# Excalibur

- Goal: to provide trusted cloud services secure against malicious administrators.

**Data** is **sealed** according to a **policy** and only cloud vms that fulfill the policy can unseal and access it.

Data sealing is achieved through Ciphertext-Policy Attribute Based Encryption (CP-ABE).

### Enforcing Policies
- To enforce policies and distribute ABE keys, a VM monitor is used in the cloud.
- All cloud nodes and monitor are equipped with TPMs.
- Whenever a cloud node reboots, the monitor invokes its TPM to attests its configuration.
- The monitor itself can be replicated for scalability and attested by the clients for security.

Excalibur minimizes the use of TPMs, which are slow, but ABE encryption and decryption can also be slow.

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/575695/mod_resource/content/4/dps-10-advanced%20crypto%20systems.pdf