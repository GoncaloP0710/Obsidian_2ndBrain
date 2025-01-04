2025-01-03 15:20

Status: #done 

Tags: [[Data Privacy and Security]] [[Data Base]] [[Security]] 

# DepSky

A dependable and secure (NoSQL) storage system based on storage-only clouds.

- Stores data in the cloud
- Replicates data through multiple clouds instead of a single one
- Uses Byzantine Fault-Tolerant replication (integrity)
- Encrypts data and stores keys also in the cloud through secret sharing (privacy)

### Erasure Codes
Simply replicating data through 𝑛 clouds can lead to high financial costs.
Erasure codes is a technique that allows reducing replication costs.

### Secret Sharing
For confidentiality, data must be encrypted before being sent to the cloud.

### DepSky Limitations
- No replica recovery features
- Data is encrypted but access patterns are still revealed
- Computation on stored data is impossible without retrieving it

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/575695/mod_resource/content/4/dps-10-advanced%20crypto%20systems.pdf