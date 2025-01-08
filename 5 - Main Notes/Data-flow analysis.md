2025-01-08 15:31

Status: #done 

Tags: [[Software Security]] [[Code Analysis]] 

# Data-flow analysis

Tries to understand how data moves through the program, namely from the input (attack surface) until dangerous instructions.

Typically, involves traversing a function's control flow graph.

Probably the most common form of data-flow analysis in the security context is **taint analysis**.

**Taint analysis**: follow the input data and verify if it reaches functions that can be exploited with malicious inputs.
# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554479/mod_resource/content/7/T_StaticA.pdf