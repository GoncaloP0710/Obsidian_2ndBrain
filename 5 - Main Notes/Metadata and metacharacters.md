2025-01-10 15:04

Status: #done 

Tags: [[Software Security]] [[2nd Brain/2 - Tags/Attacks|Attacks]] 

# Metadata and metacharacters

Metadata can be represented
- **In-band**, e.g., strings in C (a special character is used to indicate the termination)
- **Out-of-band**, e.g., strings in Java (the number of characters is metadata stored separately from the characters)

Vulnerabilities occur because
- the program trusts input to contain only characters (no metacharacters)
- but, the attacker introduces input with metacharacters

Solution: **sanitize** input from metacharacters!

Typical attacks using metachars
- **Embedded delimiters**: the application receives more than one kind of information separated by a delimiter
- **NULL character injection**: the \0 character is interpreted in different ways by distinct components
- **Separator injection**: the information may contain separators to divide it in parts (e.g., directory ´/´)
	- Directory separators cause truncation allowing a path traversal attack

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554465/mod_resource/content/7/T_formatStrings.pdf
