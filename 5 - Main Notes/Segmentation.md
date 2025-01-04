2025-01-04 15:06

Status: #done 

Tags: [[Software Security]] [[Memory]]

# Segmentation

A program’s memory is split in several parts called **segments**.
Memory is (logically) addressed by (name, offset).
This addressing allows for segments to be placed in any point of physical memory and to be relocated to other areas.

There is a **translation table** with the location of the beginning of each segment, which allows the translation of a logical address to a physical address.

### Translation table
- allows a process to access a segment only if the segment appears in its translation table
- keeps info about **access rights** (ex: READ, WRITE, EXECUTE)
- every memory access must go through the OS/MMU so access rights can be checked.

![[Segmentation 1.png]]

### Difficulties of segmentation
- checking efficiently if memory accesses are beyond the end of the segment
- can cause fragmentation of the memory

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554457/mod_resource/content/7/SS_OSprot.pdf