2025-01-07 16:54

Status: #done 

Tags: [[Software Security]] [[2nd Brain/2 - Tags/Vulnerability|Vulnerability]]

# Software and Data Integrity Failures

Main idea: **code** and **infrastructure** that does not **protect against integrity violations**, such as when:
- an application relies upon plugins, libraries, or modules from untrusted sources
- updates are downloaded without sufficient integrity verification and applied to the previously trusted application
- objects or data are encoded or serialized into a structure that an attacker can see and modify to cause malicious deserialization

### Insecure Deserialization

![[Software and Data Integrity Failures 1.png]]

### Protection
- Use digital signatures or similar mechanisms to verify the software or data
- Ensure updates are coming from trusted repositories
- Implement integrity checks or encryption of the serialized objects

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/572748/mod_resource/content/8/T_webVuln.pdf