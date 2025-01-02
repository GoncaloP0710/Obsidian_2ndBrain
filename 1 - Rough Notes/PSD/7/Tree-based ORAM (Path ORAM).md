2025-01-02 19:15

Status: 

Tags: 

# Tree-based ORAM (Path ORAM)

Path ORAM is a very simple ORAM algorithm which organizes blocks in the server according to a tree.
- The idea is that for every block there is a path that goes from the root to a leaf node and that contains it.

Server:
- Stores blocks organized in nodes of a tree, which must have **as many leaves as the size of the database**.
- Every block is assigned a “position”, based on its leaf sequence number
- Blocks must be placed on the path to their positions
- Block positions are chosen randomly from 1 to W (nº of leaves)

Client:
- Position Map: stores the positions of all blocks
- Stash: cache that keeps overflowed blocks

![[Tree-based ORAM (Path ORAM) 4.png]]

## Performance Analysis
- Without recursion: O(𝒍𝒐𝒈 𝒏) blocks
- With recursion: O(𝒍𝒐𝒈𝟐 𝒏) blocks

## Security Analysis
- Path ORAM hides access patterns w/ perfect security.

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554345/mod_resource/content/3/dps-07-oblivious%20ram.pdf