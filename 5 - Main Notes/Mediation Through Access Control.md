2025-01-04 15:34

Status: #done 

Tags: [[Software Security]] [[Memory]] [[Security]] 

# Mediation Through Access Control

Access control is concerned with the validation of the access rights of subjects when performing operations in the resources of the system.

### Reference monitor
Generically, access control should be implemented by a **reference monitor**.

Ensure three principles
- **Completeness**: it must be impossible to bypass
- **Isolation**: it must be tamperproof
- **Verifiability**: it must be shown to be properly implemented

### Basic Models
**Access control lists** (ACLs)
- each object is associated with a list
- the list contains pairs (subject, rights)
**Capabilities**
- each subject has a list of objects that it may access
- the list contains capabilities, i.e., pairs (object, rights)
**Access control matrix**
-  a matrix with lines per subject, columns per object, rights in the cells

#### Who defines the rights?
Who defines the access control policy for each object?
- Usually, each subject sets policy for its own objects
What about administrative operations?
- The usual solution is to have a special user

### Access Control Models: DAC/MAC
- Discretionary A.C. – configured by the user (traditional Linux solution)
- Mandatory A.C. - configured by the administrator for all system

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554457/mod_resource/content/7/SS_OSprot.pdf