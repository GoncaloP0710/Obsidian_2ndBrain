2025-01-04 14:52

Status: #done 

Tags: [[Software Security]] [[Operating System]] [[Security]] 

# Separation in the OS

Nowadays, there is a cooperation between the operating system and the hardware to enforce separation!

Common operating systems (Unix, Windows) run software in two modes:
- Kernel mode – software can play with any system resource
- User mode – access to resources is controlled by the OS

User mode: how can software execute operations in objects outside their control?
- software must call the OS kernel using **system calls**

System calls solve the separation issues for most resources of the machine, but what about memory?
- accesses to memory cannot be performed through system calls because of performance issues
- To enforce this protection there needs to be cooperation (again) between the hardware + OS

### Strategies for separation
- Physical separation: different processes use distinct devices
- Temporal separation: processes with different security requirements are executed at different times
- *Logical separation*: processes operate under the illusion that no other processes exist

### Separation for memory protection
- **Segmentation**
- **Paging**
- Segmentation + Paging

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554457/mod_resource/content/7/SS_OSprot.pdf