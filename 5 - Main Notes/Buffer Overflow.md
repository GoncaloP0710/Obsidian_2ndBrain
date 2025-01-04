2025-01-04 15:43

Status: #done 

Tags: [[Software Security]] [[Security]] [[Memory]] [[Over Flows]] 

# Buffer Overflow

Buffer overflow occurs when a program writes (or reads) outside the allocated space for the buffer, normally after the end.

What happens when there is an accidental BO?
- program becomes unstable
- program crashes
- program proceeds apparently normally

### Why are Buffer Overflows a security problem?
In the worst case, it can be exploited intentionally and let the attacker execute its own code on the target machine.

But there are other ways where BO can cause damage
- Code might be modified
- Data may be altered
- Data might be read, creating an information leak

## Main Solutions for Protection
### Address space layout randomization (ASLR)
the starting address of the address space segments changes in each execution, preventing the pre-computation of
- specific address to be overwritten
- location of a specific code

### Data Execution Prevention (DEP)
Marks certain memory regions as non-executable to prevent injected code execution.
- the stack pages cannot be executed, but only written/read
- the code segment can be executed, but not written

### Canaries
Put special (nondeterministic) values – canaries -- before (or after) the places we want to protect in memory.
Check that canaries have not been changed before accessing the protected memory

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554464/mod_resource/content/8/BO_T.pdf