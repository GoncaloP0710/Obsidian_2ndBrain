2025-01-02 19:05

Status: #done 

Tags: [[ORAM]] [[Data Privacy and Security]] [[Data Base]] [[Security]] 

# Recursive Oblivious Shuffling ORAM

The cache can also be stored in the server, alongside the other N+C blocks.

Storage costs:
- Server: N+2C blocks
- Client: O(1)

![[Recursive Oblivious Shuffling ORAM 2.png]]

To read/write a slot:
- Scan cache from server
- If data is not in cache, read it from main memory
- If it is in cache, read next dummy slot
- Write data into cache

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554345/mod_resource/content/3/dps-07-oblivious%20ram.pdf