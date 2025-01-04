2025-01-04 17:29

Status: #done 

Tags: [[Software Security]] [[Memory]] [[Security]] 

# Use after free

Occurs when a program continues to use a pointer after it has been freed, with causes problems related to
- error conditions and other exceptional circumstances
- confusion over which part of the program is responsible for freeing the memory

Impact
- **integrity**: use of previously freed memory may **corrupt valid data**
- **availability**: if (malloc) chunk consolidation occurs after the use of previously freed data, the process may crash when invalid data is used as chunk information

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554464/mod_resource/content/8/BO_T.pdf