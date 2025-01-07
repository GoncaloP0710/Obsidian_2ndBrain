2025-01-07 15:33

Status: #done 

Tags: [[Software Security]] [[2nd Brain/2 - Tags/Attacks|Attacks]] [[2nd Brain/2 - Tags/Vulnerability|Vulnerability]]

# Security misconfiguration

A configuration flaw allows the attacker to access several things to gain unauthorized access to or knowledge of the system.

Examples:
- remote admin console is installed and not removed from production
- default account passwords are not changed/removed - attacker discovers, logs in with default passwords
- directory listing is not disabled - attacker finds all files on the server by simply listing the directories

### XML External Entity (XXE)
XML processors may incorrectly evaluate entity references within XML documents, allowing the disclosure of data or execute remote request …

Occurs when XML input contains a reference to an external entity that is processed by a badly configured XML parser.

#### Protection
- Applying hardening guidelines to the system
- Scanners are useful to automate the process of detecting missing patches, misconfigurations, etc...

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/572748/mod_resource/content/8/T_webVuln.pdf