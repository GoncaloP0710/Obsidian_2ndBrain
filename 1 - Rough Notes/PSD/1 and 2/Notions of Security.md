2025-01-02 15:27

Status: 

Tags: 

# Notions of Security

## Perfectly Secret Encryption
When a ciphertext reveals nothing regarding a plaintext.
Also, equivalent to Semantic Security.
- Nothing can be learned about a plaintext from the ciphertext that could not be learned without seeing the ciphertext.

### The One-Time Pad
Although unknown at the time, it was the first scheme to fulfill the notion of Perfect Secrecy.
The encryption algorithm simply makes a bitwise exclusive-or (XOR) of the message m and key k.
However, this requires key k to be as large as message m.
And each k should only be used once, as encrypting multiple messages with the same key leaks a lot of information.

## Computational Security
Perfect secrecy requires that absolutely no information be leaked to an eavesdropper with unlimited computational power.
However, an encryption scheme would still be considered secure if it leaked information with some tiny probability to eavesdroppers with **bounded computational power**.
We call this Computational Security, as it takes into account the computational limits of attackers.

### Computational Secure Encryption from PRNGs
Using a secure PRNG, we can build a computationally secure variant of the one-time pad.

![[Notions of Security 1.png]]

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554340/mod_resource/content/7/dps-01-02-concepts.pdf