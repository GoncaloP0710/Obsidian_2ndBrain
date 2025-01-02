2025-01-02 19:54

Status: 

Tags: 

# GMW MPC

GMW protocol extends MPC to the general case, supporting more than 2 parties.

The protocol is based on full-threshold (𝒕 = 𝒏) Secret Sharing and can work on both Boolean and arithmetic circuits.

Performance
- O(1) communication cost for Addition gates
- O(N2) communication cost for Multiplication gates
- Nº of communication rounds is linear w/ circuit depth

Security
- The protocol provides perfect security against passive adversaries

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554346/mod_resource/content/8/dps-08-multi-party%20computation.pdf