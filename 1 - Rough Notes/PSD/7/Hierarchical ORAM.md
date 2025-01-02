2025-01-02 19:07

Status: 

Tags: 

# Hierarchical ORAM

Server stores data blocks organized in log (N) levels.

**Data starts on lowest levels** and when accessed gets moved to level 1, eventually getting shuffled to lower levels.

![[Hierarchical ORAM 3.png]]

To perform a Read/Write(addr) operation:
- Scan both top buckets for the data
- At each lower level, scan exactly one bucket
- Move data to bucket on level 1
- Perform a “shuffling procedure” to maintain invariant

After every 𝟐𝒊 ops, level 𝒊 gets merged w/ level 𝒊 + 𝟏

Security
- All reads look like random bucket scans
# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554345/mod_resource/content/3/dps-07-oblivious%20ram.pdf