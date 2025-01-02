2025-01-02 18:53

Status: 

Tags: 

# Oblivious RAM

The goal of ORAM is to **hide all access patterns** of a program accessing external memory.

The basic idea of ORAM is to conceal access patterns by continuously **shuffling** and **re-encrypting** data as it is accessed.

## Naïve Solutions

- A trivial solution is for the client to read all data blocks from the server with each logical request.
- Another is for the client to store all data, hence requesting no blocks from the server.
- A more interesting (yet still naïve) solution is to randomly permute all memory blocks before data accesses begin - This is known as a one-time ORAM.

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554345/mod_resource/content/3/dps-07-oblivious%20ram.pdf