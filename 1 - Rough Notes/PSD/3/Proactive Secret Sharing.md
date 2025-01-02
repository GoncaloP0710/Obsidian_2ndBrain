2025-01-02 15:55

Status: 

Tags: 

# Proactive Secret Sharing

In long-lived systems, a mobile adversary can progressively corrupt servers, eventually reaching k shares.

PSS deals w/ this by **periodically refreshing shares** w/o having to reconstruct the secret (which could put it in risk).

PSS leverages the homomorphic properties of Shamir’s SS.
Homomorphic properties of Shamir's scheme allow servers to update their shares independently of the secret. This ensures that during refreshing, the secret itself is never reconstructed or exposed.

**How the Refreshing Works**:
Shares are refreshed by having each server generate a random polynomial of degree k−1 (with a constant term of 0) and distributing the corresponding evaluations (sub-shares) to the other servers. Each server updates its share by summing up the received sub-shares.

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554341/mod_resource/content/5/dps-03-secret%20sharing.pdf