### Introduction
[[Motivation to Software Security]]

### Security and Software Development
[[2nd Brain/5 - Main Notes/Vulnerability]]
[[2nd Brain/5 - Main Notes/Attacks]]
[[Software Development Life Cycle]]
[[Design Principles to Avoid Vulnerabilities]]

### Operating Systems Protection Mechanisms
[[Protection of Resources]]
[[Separation in the OS]]
[[Segmentation]]
[[Paging]]
[[Mediation Through Access Control]]

### Buffer Overflows
[[Buffer Overflow]]
[[Heap Overflows]]
[[Stack Overflows]]
[[Control Flow Integrity]]
[[Exception-handler Hijacking]]
[[Use after free]]
[[Integer Overflows]]

### Input Validation
printf(format_string, parameters…)
the stack contains:
- %08x ⇾ the number to print ⇾ read
- %s ⇾ the address of the string to print ⇾ read
- %n ⇾ the address where the value is stored ⇾ write
[[Different Forms of Input]]
[[Path Traversal Attack]]
[[Command Injection Attack]]
[[Metadata and metacharacters]]

### Web Application Vulnerabilities
[[Broken Access Control]]
[[Cryptographic Failures]]
[[2nd Brain/5 - Main Notes/Injection]]
[[Reflected XSS]]
[[Stored XSS]]
[[CRLF injection]]
[[Insecure Design]]
[[Security misconfiguration]]
[[Vulnerable and Outdated Components]]
[[Identification & Authentication Failures]]
[[Managing User Sessions]]
[[Software and Data Integrity Failures]]
[[Security Logging and Monitoring]]

### Database Vulnerabilities
[[SQL injection]]

### Static Code Analysis
[[Static source code analysis]]
[[Semantic Analysis]]
[[Type checking analysis]]
[[Control-flow analysis]]
[[Data-flow analysis]]
[[Web Application Protection (WAP)]]
[[Symbolic Execution]]

### Software Testing
[[Software testing and security]]
[[Fuzzers]]
[[AFL]]
[[Vulnerability scanners]]
[[Proxies]]

### Race Conditions
[[Race conditions]]
[[TOCTOU]]
[[Temporary files]]
[[Concurrency and Reentrant Functions]]

### Software Testing and Auditing
[[OWASP]]
[[Threat and Attack modeling]]
[[Code Review]]