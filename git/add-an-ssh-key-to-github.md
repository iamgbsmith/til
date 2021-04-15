# Add An SSH Key To GitHub

__Category: Git__

Assuming you have generated a SSH key pair, you will need to upload your public key to GitHub in order to interact with the repository.

Print the public key to the console.

```shell
cat ~/.ssh/id_ed25519.pub 
```

Output:

```shell
ssh-ed25519 DFCEA1NzaC1lZDI1NTE5BBBBIAthmFj00y8yWLLkilZ3Be+dS6HzDS4vZrvObvmgHwTC billy.bragg@orbiks.com
```

Log into GitHub and navigate to Settings -> SSH and GPG keys.

Press the button "New SSH Key".

Specify a `Title` for the SSH key (for example, "My Home Laptop").

Copy the output from displaying the public key in the console into the `Key` field.  This should include the email address specified when generating the SSH key.

Press the button "Add SSH key" to save your configuration.
