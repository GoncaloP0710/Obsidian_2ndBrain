2025-01-03 14:12

Status: 

Tags: 

# Intel SGX

Intel Software Guard Extensions (SGX) was Intel’s response to ARM TrustZone.

SGX operates at the user level
- SGX allows users to create protected regions of memory to run their apps.
- These regions are called **Enclaves**.
- The CPU does this by **encrypting the enclave memory** and **restricting access to it**.

SGX provides:
- Isolated execution
- Remote attestation of enclave code
- Data Sealing

To use SGX, an application must first be partitioned between its sensitive and non-sensitive components
- Non-sensitive (or untrusted) code can be executed as normal
- Sensitive (or trusted) code is executed inside the enclave

### Remote Attestation
Attestation consists in proving that the enclave is running the expected software, and it has not been tampered with.

### SGX Limitations
- The main limitation regarding SGX is **Enclave size**

### SGX Applications
- Secure processing
- Secure storage

### SGX Vulnerabilities
- Side Channel Attacks
- Replay Attacks
- Speculative Execution Attacks
- Enclave Attacks

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554347/mod_resource/content/3/dps-09-hardware.pdf