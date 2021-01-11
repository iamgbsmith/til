# Generate An SSH Key

__Category: Security__

_The steps outlined here are for macOS. SSH keygen on Linux follows a similar process._

An SSH key is an access credential in the SSH protocol. SSH keys are primarily used for accessing systems which have been hardened by system administrators or power users.

### Generate a new SSH key pair

Generate a key pair using your email address:

```shell
ssh-keygen -t ed25519 -C "your.email@example.com"
```

This creates a new ssh key pair using the provided email as a label.

```
> Generating public/private ed25519 key pair
```

When prompted to "Enter a file in which to save the key," press Enter. This accepts the default file location.

```
> Enter a file in which to save the key (/Users/you/.ssh/id_ed25519): [Press enter]
```

At the prompt, type a secure passphrase.

```
> Enter passphrase (empty for no passphrase): [Type a passphrase]
> Enter same passphrase again: [Type passphrase again]
```

### Adding your SSH key to the ssh-agent

Start the ssh-agent in the background:

```
$ eval "$(ssh-agent -s)"
> Agent pid 34117
```

Check to see if your ~/.ssh/config file exists in the default location.

```
$ open ~/.ssh/config
> The file /Users/you/.ssh/config does not exist.
```

If the file doesn't exist, create it:

```shell
touch ~/.ssh/config
```

Add the key to the SSH agent:

```
Host *
  AddKeysToAgent yes
  IdentityFile ~/.ssh/id_ed25519
```

Add your SSH private key to the ssh-agent and store your passphrase in the keychain:

```shell
ssh-add -K ~/.ssh/id_ed25519
```

__Note:__ The -K option is Apple's standard version of ssh-add, which stores the passphrase in your keychain for you when you add an ssh key to the ssh-agent. If you chose not to add a passphrase to your key, run the command without the -K option.