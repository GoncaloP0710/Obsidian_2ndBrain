2025-01-07 14:41

Status: #done 

Tags: [[Software Security]] [[Security]] [[2nd Brain/2 - Tags/Attacks|Attacks]] [[2nd Brain/2 - Tags/Injection]]  [[2nd Brain/2 - Tags/Vulnerability|Vulnerability]] 
# Injection

The web server accepts input that is poorly understood by an interpreter, allowing an:
- unintended command to be executed
- the access to some data for which there was no authorization

Often, it is possible to find these vulnerabilities with automated tools, such as static analysis and fuzzers.

### OS command injection
Example: Perl allows piping data to a process from an open statement by adding a '|' (Pipe) character onto the end of a filename.
- if the filename ends with a '|', the filename is interpreted as a command that pipes the output to us

### Cross Site Scripting (XSS)
Attacker is able to inject a script in the victim’s browser (typically JavaScript but others are possible).

Types:
- Reflected XSS (or non-persistent) 
	- a page reflects user supplied data directed to a user’s browser
- Stored XSS (or persistent)
	- hostile data (scripts) is stored in a file, database or other and is later sent to a user’s browser

## Protection for Injection

**Prevention** is related to ensure that user supplied data canot be incorrectly used in commands or queries.
- **Avoid** the interpreter or employ secure APIs that **parameterize** user data added to commands
- a “white list” can define which acceptable input can be used

**Detect**
- look for the places in the code where the interpreters
	- **use** the **potentially malicious data** supplied from the user
	- **validate, filter or sanitize** the user-controlled data to be utilized in a command or query

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554468/mod_resource/content/8/WebSec.pdf