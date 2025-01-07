2025-01-07 14:13

Status: #done 

Tags: [[Software Security]] [[2nd Brain/2 - Tags/Vulnerability|Vulnerability]] 

# Broken Access Control

Due to bugs on authorization enforcement, (authenticated or anonymous) users can access functionality and/or data they were not supposed to.

Most common problems
- **violation** of the **principle of least privilege** allowing access to everyone
- replaying or **tampering** with unique **identifiers** to access other accounts
- **bypassing** **access control** checks by modifying the URL or the HTML page

### Cross-origin resource sharing (CORS)
CORS is a browser mechanism that enables controlled access to resources located outside a given domain; it extends and adds flexibility to the same-origin policy (SOP).
CORS protocol uses a suite of HTTP headers that define **trusted web origins** and associated properties such as whether authenticated access is permitted.
Due to the misconfiguration of the application, then the malicious-website can contact a vulnerable-website and request a sensitive-victim-data using its credentials.

#### Protection
Proper configuration of cross-origin requests; only allow access to public APIs.
- Except for public resources, deny by default
- Implement access control mechanisms once and re-use them
throughout the application

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554468/mod_resource/content/8/WebSec.pdf