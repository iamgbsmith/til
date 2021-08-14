# List GPG Keys

__Category: Security__

_The steps outlined here are for macOS. Listing keys on Linux should work in a similar manner._

List the long form of the GPG keys for which you have both a public and private key for using the following command:

```shell
gpg --list-secret-keys --keyid-format=long
```

Sample output:

```shell
gpg --list-secret-keys --keyid-format=long
/Users/hubot/.gnupg/secring.gpg
------------------------------------
sec   4096R/3AA5C34371567BD2 2016-03-10 [expires: 2017-03-10]
uid                          Hubot 
ssb   4096R/42B317FD4BA89E7A 2016-03-10
```

Print the public key using the GPG key ID you want to use. From the above output, the GPG key ID is 3AA5C34371567BD2:

```shell
gpg --armor --export 3AA5C34371567BD2
```
