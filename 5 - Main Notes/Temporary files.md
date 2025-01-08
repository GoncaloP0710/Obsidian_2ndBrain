2025-01-08 18:25

Status: #done 

Tags: [[Software Security]] [[2nd Brain/2 - Tags/Vulnerability|Vulnerability]] 

# Temporary files

Caused by the creation of files in a shared dir, which if not created properly may allow the attacker to control the file.

Typical attack
1. Privileged program checks that there is no file X in /tmp
2. Attacker races to create a link called X to some file, say /etc/passwd
3. Privileged program attempts to create X but ends up opening theattacker’s file, and does something undesirable that its privileges allow …

![[Temporary files 1.png]]

- After mktemp() and before open() an attacker can link filename to some other file --- this is possible because he managed to predict the filename returned by mktemp()
- open() would then not create but open an existing file

### Possible solutions
Non-solutions
- Random file names
- Locks

Acceptable solutions
- Use a **long random number** (e.g., 128 bits), set umask appropriately (e.g., 0066), and open the file
- Use the **safe calls**

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554484/mod_resource/content/7/T_races.pdf