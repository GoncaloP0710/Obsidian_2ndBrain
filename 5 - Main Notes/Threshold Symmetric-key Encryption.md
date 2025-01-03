2025-01-02 16:12

Status: #done 

Tags: [[Data Privacy and Security]] [[Security]] [[Encryption]] 

# Threshold Symmetric-key Encryption

Threshold symmetric-key encryption is a cryptographic scheme where the decryption of a ciphertext requires collaboration from multiple parties, each holding a part of the decryption key.

- Client sends Commitment 𝒕 of message 𝒎 to the servers
- Servers run a DPRF between themselves on 𝒕 to get partial results 𝒌𝒊
- Client receives all 𝒌𝒊 and combines them to get 𝒌
- 𝒌 is then used to encrypt m

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554341/mod_resource/content/5/dps-03-secret%20sharing.pdf