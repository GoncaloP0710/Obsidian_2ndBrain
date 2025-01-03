2025-01-02 15:13

Status: #done 

Tags: [[Data Privacy and Security]] [[Cryptography]]

# Historical Ciphers

## Caesar’s Cipher
Consisted in shifting the letters of the alphabet by 3 places forward.

## Shift Cipher
Keyed variant of Caesar’s Cipher. Shifting amount is variable and used as key.

## Mono-Alphabetic Substitution Cipher
Each letter is substituted by any other letter from the alphabet. Brute-force attacks on the key space are infeasible. However, the scheme is still insecure against **statistical analysis**.

## Vigenère
The key is a string of letters.
Encryption shifts each plain text character by the amount indicated by the next character of the key, wrapped around the key when necessary.

![[Historical Ciphers 1.png]]

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554340/mod_resource/content/7/dps-01-02-concepts.pdf