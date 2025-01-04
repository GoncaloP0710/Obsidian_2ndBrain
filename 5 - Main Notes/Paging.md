2025-01-04 15:15

Status: #done 

Tags: [[Software Security]] [[Memory]] 

# Paging

The memory of a process is divided in pages of the same size.
- physical memory is divided into page frames of the same size as a page … so, there is no fragmentation, and knowing the end is trivial
- memory is addressed by (page, offset)

From a protection point of view, pages are like segments
- a process sees a physical page only if the page appears in its **page translation table**
- information about access rights (ex: WRITE, EXECUTE) is stored in the table, and access rights are enforced per access

![[Paging 1.png]]

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554457/mod_resource/content/7/SS_OSprot.pdf