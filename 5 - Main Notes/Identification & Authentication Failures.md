2025-01-07 16:34

Status: #done 

Tags: [[Software Security]] [[2nd Brain/2 - Tags/Vulnerability|Vulnerability]] 

# Identification & Authentication Failures

Main idea: weaknesses in the implementation of **authentication** and **session management** allow the compromise of passwords, keys, or session tokens, or to exploit other implementation flaws to assume the identities of other users.

Example weaknesses of broken authentication:
- allow brute force or other automated attacks
- permit or have default weak or well know passwords
- uses insecure credential recovery / forgot password recovery

### Credential Stuffing
**Credential stuffing**: breached username/password pairs are automatically injected to get access to user accounts (a special case of brute force attacks)

**Credential spraying**: it is a variant, where a single weak password is automatically tested against a large number of different accounts

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/572748/mod_resource/content/8/T_webVuln.pdf