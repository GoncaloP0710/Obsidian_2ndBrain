2025-01-02 19:00

Status: #done 

Tags: [[Data Privacy and Security]] [[Data Base]] [[Security]] [[ORAM]]

# Oblivious Shuffling based ORAM

The server stores N+C data blocks and the client stores a local cache of C blocks.

![[Oblivious Shuffling based ORAM 1.png]]

To read/write a data block:
- If data is not in cache, read it from DB and add to cache
- If it is in cache, read the next dummy slot from DB
- New data is written into cache

After C ops, we need to reshuffle the DB and flush the cache.

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554345/mod_resource/content/3/dps-07-oblivious%20ram.pdf