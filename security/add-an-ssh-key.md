# Add An SSH Key

__Category: Security__

_The steps outlined here are for macOS. Listing keys using `ssh-add` on Linux should work in a similar manner._

Start the SSH agent:

```shell
eval "$(ssh-agent -s)"
```

Add your SSH private key to the SSH agent and store your passphrase in the keychain using the `-K` flag (do not use the `-K` flag on Linux). 

You will be prompted to enter the passphrase for the key during the process:

```shell
ssh-add -K ~/.ssh/id_ed25519
```
