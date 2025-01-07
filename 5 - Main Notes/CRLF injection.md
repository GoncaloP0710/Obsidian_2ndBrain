2025-01-07 15:05

Status: #done 

Tags: [[Software Security]] [[2nd Brain/2 - Tags/Attacks|Attacks]] [[2nd Brain/2 - Tags/Injection|Injection]] [[2nd Brain/2 - Tags/Vulnerability|Vulnerability]] 

# CRLF injection

Called CRLF (Carriage Return and Line Feed) injection or HTTP response splitting.

Idea is similar to **reflected XSS** but with **injection in the header** of the HTTP response.

Can be performed like a reflected XSS
- attacker sends the victim a URL of a vulnerable website

CRLF injection (Carriage Return Line Feed injection) is a type of vulnerability that occurs when an attacker manipulates the input to a web application or system to inject unexpected `CR` (Carriage Return, represented as `\r`) and `LF` (Line Feed, represented as `\n`) characters. These characters are used to signify the end of a line in many text-based protocols, such as HTTP, SMTP, or log files.

![[CRLF injection 1.png]]

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554468/mod_resource/content/8/WebSec.pdf