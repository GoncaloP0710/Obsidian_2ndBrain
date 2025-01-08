2025-01-08 15:46

Status: #done 

Tags: [[Software Security]] [[Code Analysis]] 

# Symbolic Execution

Emulate the execution of the program
- using **symbolic input values**, instead of concrete data values
- represent the values of program variables as **symbolic expressions** over the symbolic input values
- **output values** computed by the program are expressed as a function of the symbolic input values

Main goals of symbolic execution for software testing
- explore as many different program paths as possible in a given amount of time 
- generate a set of concrete input values exercising that path
- check for the presence of various kinds of errors

**Execution path** is a sequence of true and false values, where
- a true at the if position in the sequence denotes that the if conditional statement encountered along the execution path took the “then” branch
- a false means that an “else” was taken

All execution paths of the program can be represented in an **execution tree**

![[Symbolic Execution 1.png]]

### Difficulties
Symbolic **path explosion**
- as more if conditions are encountered in the program, there are too many PC (Path Constraints) to be solved
Code containing loops and recursion
- may result in an infinite number of paths
Symbolic paths with unsolvable constraints
- there are several formulas that cannot (or are hard) be solved with existing SAT solvers

Solution: use a timeout for the processing or a limit on the number of paths.

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554479/mod_resource/content/7/T_StaticA.pdf