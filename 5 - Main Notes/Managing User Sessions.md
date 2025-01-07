2025-01-07 16:43

Status: #done 

Tags: [[Software Security]] [[2nd Brain/2 - Tags/Attacks|Attacks]] 

# Managing User Sessions

Typical approach:
- user authenticates (ex, in a login page)
- a session starts
- server stores user info and manages the session state in a table

### State tracking mechanisms - ID
Server sends to the browser an ID to be included in every request.

IDs must be:
- Univocal
- Unpredictable
- With a (short) expiration time

### Session hijacking attack
Attacker discovers an open session ID and sends commands to that session.

### Session Fixation Attack
Occurs when the attacker is able
to hijack a valid user session.
- is a special case of a session hijacking attack
- when authenticating a user keeps an existing session ID (instead of creating its own new ID)

![[Managing User Sessions 1.png]]

### Protection
- **Multi-factor authentication** to prevent automated guessing attacks.
- Do not setup default credentials, namely for admin accounts.
- Follow best practices for managing passwords.

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/572748/mod_resource/content/8/T_webVuln.pdf