2025-01-08 17:49

Status: #done 

Tags: [[Software Security]] [[2nd Brain/2 - Tags/Attacks|Attacks]] 

# Proxies

- The discovery/definition of the application protocol can be difficult to accomplish
- Special proxies can be used in this context
	- no need to obtain a protocol specification …
	- simply modify the messages in the network

### A minimal proxy - ITR
ITR: Interactive TCP Relay – allows to test client/server applications that communicate with TCP.

Interception
- ITR can intercept outgoing / incoming traffic
- data is buffered until the user indicates that it should be sent
- while buffered, the user can manually modify data

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554474/mod_resource/content/7/fuzz.pdf