# CloudSurvivalGuide
To list all SSH fingerprints for verification, paste this into the "Run command" section of your cloud provider.
```sh
#!/bin/bash

# Change to the /etc/ssh directory
cd /etc/ssh

# Enumerate and print the SHA256 fingerprints of all public keys
for pubkey in *_key.pub; do
    echo "Fingerprint for ${pubkey}:"
    ssh-keygen -lf "${pubkey}" -E sha256
    echo
done
```
