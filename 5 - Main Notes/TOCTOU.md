2025-01-08 18:10

Status: #done 

Tags: [[Software Security]] [[2nd Brain/2 - Tags/Vulnerability|Vulnerability]] 

# TIME OF CHECK – TIME OF USE

Typical case:
- A program running setuid root is asked to write to a file owned by the user running the program
- Root can write to any file, so the program must check if the actual user has the required rights to change the file

![[TOCTOU 1.png]]

int access(const char pathname, int mode);
- checks whether the calling process can access the file **pathname** according with **mode**
- However, it is usually vulnerable to race conditions / TOCTOU
- Should never be used!

### Vulnerability with lstat()
- int stat(const char pathname, struct stat buf)
	- pathname – file to be checked
	- buf – structure to be filled with data about the file
- lstat() – the same but data is returned about the link itself (not the file that it refers to), if pathname is a link

![[TOCTOU 2.png]]

## Preventing file race conditions

- Most file races have to do with pathnames
- So the protection is to avoid the two sequential resolutions and use filenames only when strictly necessary inside the program

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554484/mod_resource/content/7/T_races.pdf