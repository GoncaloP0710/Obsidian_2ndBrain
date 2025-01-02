2025-01-02 18:28

Status: 

Tags: 

# Forward and Backward Privacy

## Forward Privacy
If we search for keyword 𝒘 and later on add 𝒘 to a new document ID, the server should not immediately learn that ID contains a keyword that has been searched for in the past.

## Backward Privacy
Searching for 𝒘 should not reveal documents where 𝒘 has been added to and later removed from.

# Achieving Forward Privacy

To achieve forward privacy, updates should reveal no information, particularly when combined w/ old search tokens.

One way to achieve this is by having **Search Tokens** ST and **Update Tokens** UT **in separate**.

And by using asymmetric encryption, giving the **public key** PK to the **salver** and the **private key** SK to the **client**.

SK allows issuing new Search and Update Tokens, while PK allows
finding old Search and Update Tokens (but not new ones).

# Achieving Backward Privacy

Backward privacy can be achieved by having the **client filter deletions**.

Additionally, additions and deletions can be stored indistinguishably in the same index.

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554344/mod_resource/content/5/dps-06-searchable%20encryption.pdf