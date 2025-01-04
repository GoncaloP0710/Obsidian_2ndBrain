2025-01-04 15:58

Status: #done 

Tags: [[Software Security]] [[Memory]] [[Security]] [[Over Flows]] 

# Heap Overflows

- Modify value of data in the heap

A **Heap Overflow** occurs when a program writes more data to a dynamically allocated memory area (heap) than it is supposed to, causing corruption of adjacent memory locations. The heap is a region of a process's memory used for dynamic memory allocation, managed at runtime by functions like `malloc()`, `calloc()`, `new`, etc.

Heap overflows can lead to **program crashes**, **data corruption**, or **security vulnerabilities**, especially when an attacker uses them to execute **arbitrary code** or manipulate program behavior.

### Heap Spray
A **Heap Spray** is a type of **memory corruption attack** where an attacker **fills the heap with malicious data** in order to control the program's execution flow.

Modern operating systems have **defensive mechanisms** like:
- **ASLR (Address Space Layout Randomization)**
- **DEP (Data Execution Prevention)**
A **heap spray** helps attackers bypass these defenses by **flooding the heap with their payload** to increase the chance that the program jumps to an address containing the malicious code.

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554464/mod_resource/content/8/BO_T.pdf