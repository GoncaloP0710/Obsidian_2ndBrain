2025-01-10 14:54

Status: #done 

Tags: [[Software Security]] [[2nd Brain/2 - Tags/Vulnerability|Vulnerability]] 

# Different Forms of Input

### Input: command line arguments
An attacker can pass malformed program arguments to any program parameter, including the program name.

### Input: passed by parent process
Don’t trust things left by the parent process
- umask (since it is used to set default permissions of created files, it should be reset)
- signal handlers (reset them)

### Input: environment variables
system(command), popen(command, type) call the shell with the program’s environment - avoid both.

What environment variables are used by the libraries you use? If they do not do enough sanity checking
- do it yourself
- set yourself the variable

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554465/mod_resource/content/7/T_formatStrings.pdf