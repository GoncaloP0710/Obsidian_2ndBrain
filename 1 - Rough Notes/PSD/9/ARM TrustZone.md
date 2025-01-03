2025-01-03 14:06

Status: 

Tags: 

# ARM TrustZone

Hardware security extensions introduced into ARM application processors and microcontrollers.

- Allows separating execution between a **secure world and normal world**.
- Both worlds are completely **hardware isolated**

### TrustZone Vulnerabilities
- TrustZone provides protection below the hypervisor level, this means more code has to be developed to use Trust Zone.
- Trust Zone does not specify where device **master keys** should be stored, and some devices have used unsecure places.
- Both the normal and secure world **compete** for the use of **cache lines**, which has been shown to be exploitable.

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554347/mod_resource/content/3/dps-09-hardware.pdf