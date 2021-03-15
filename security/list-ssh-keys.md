# List SSH Keys

__Category: Security__

_The steps outlined here are for macOS. Listing keys using `ssh-add` on Linux should work in a similar manner._

Start the SSH agent:

```shell
eval "$(ssh-agent -s)"
```

List private keys in your SSH agent:

```shell
ssh-add -L
```

Output:

```shell
ssh-ed25519 CAFEC3NzaC1lZD......PCZpOja5PW3xpPnZL4uAAHb bob.jackson@orbiks.com
```
