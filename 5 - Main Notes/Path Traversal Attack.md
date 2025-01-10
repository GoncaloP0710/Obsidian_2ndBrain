2025-01-10 14:59

Status: #done 

Tags: [[Software Security]] [[2nd Brain/2 - Tags/Attacks|Attacks]] 

# Path Traversal Attack

A **path traversal attack**, also known as a **directory traversal attack**, is a security vulnerability that occurs when an attacker manipulates input to access files or directories outside the intended scope of a web application or system. This can allow unauthorized access to sensitive files, such as configuration files, system files, or user data, which could compromise the system.

Path traversal attacks exploit the use of relative paths (e.g., `../../`) to navigate the file system. If an application concatenates user input directly into file paths without proper validation or sanitization, an attacker can inject path traversal sequences to access restricted areas.

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554465/mod_resource/content/7/T_formatStrings.pdf