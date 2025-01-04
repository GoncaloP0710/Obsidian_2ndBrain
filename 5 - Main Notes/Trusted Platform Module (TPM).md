2025-01-03 14:00

Status: #done 

Tags: [[Data Privacy and Security]] [[Security]] 

# Trusted Platform Module (TPM)

A TPM is a standard for secure crypto processors that can be added to commodity PC motherboards.

A TPM provides:
- True random number generation
- Remote attestation
- Secure boot
- Sealing

### TPM Applications
- Platform Integrity - Secure boot and remote attestation can be used to provide platform integrity.
- Disk Encryption - Sealing can be used to provide full disk encryption.

### Limitations
- performance
- storage size

### Vulnerabilities
- Probing the internal bus in some models
- Differential power analysis - attacker measures the energy consumption of the TPM.
- Cold Boot Attacks.

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554347/mod_resource/content/3/dps-09-hardware.pdf