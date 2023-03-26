# Update GitHub RSA SSH Host Key

__Category: Git__

On 23 March 2023, [GitHub updated their RSA SSH host key](https://github.blog/2023-03-23-we-updated-our-rsa-ssh-host-key/) after the private key was briefly exposed in a public GitHub repository. 

An SSH key which has not been updated will display a message similar to the following when trying to push to GitHub:

```shell
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@    WARNING: REMOTE HOST IDENTIFICATION HAS CHANGED!     @
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
IT IS POSSIBLE THAT SOMEONE IS DOING SOMETHING NASTY!
Someone could be eavesdropping on you right now (man-in-the-middle attack)!
It is also possible that a host key has just been changed.
The fingerprint for the RSA key sent by the remote host is
SHA256:uNiVztksCsDhcc0u9e8BujQXVUpKZIDTMczCvj3tD2s.
```

Remove the GitHub SSH key from your known hosts:

```shell
ssh-keygen -R github.com
```

To update the key, either push to your remote repository on GitHub where you will be asked to add the new key to known hosts, or run the following command:

```shell
curl -L https://api.github.com/meta | jq -r '.ssh_keys | .[]' | sed -e 's/^/github.com /' >> ~/.ssh/known_hosts
```
