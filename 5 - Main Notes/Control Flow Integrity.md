2025-01-04 16:16

Status: #done 

Tags: [[Security]] [[Software Security]] 

# Control Flow Integrity

CFI restricts the control-flow of an application to valid execution traces.
CFI enforces this property by monitoring the program at runtime and comparing its state to a set of precomputed valid states.

A **control-flow hijack** attack redirects the control-flow of the application to locations that would not be reached in a benign execution, e.g., to injected code or to code that is reused in an alternate context.

- CFI detects the attacks by limiting the targets of control-flow transfers.

Depending on the implementation, some techniques can bypass CFI.

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554464/mod_resource/content/8/BO_T.pdf