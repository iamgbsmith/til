# Verify A Checksum

__Category: Security__

It is best practice from a security perspective to validate the integrity of a file before installation by comparing the checksum of it against one computed by a reliable source. 

A checksum is a small-sized datum from a block of digital data for the purpose of detecting errors which may have been introduced during its transmission. Differences in values can also indicate malicious tampering or that the wrong file has been supplied.

Verify a checksum from the command line using MD5, SHA-1, SHA-256 or SHA-512 algorithms.

## On Linux

### MD5 checksum

```shell
md5sum /path/to/file
```

For example:

```shell
md5sum ubuntu-mate-16.10-desktop-amd64.iso
d41d8cd98f00b204e9800998ecf8427e ubuntu-mate-16.10-desktop-amd64.iso
```

### SHA-256 checksum

```shell
sha256sum /path/to/file
```

For example:

```shell
sha256sum ubuntu-mate-16.10-desktop-amd64.iso
e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855 ubuntu-mate-16.10-desktop-amd64.iso
```

## On macOS

### MD5 checksum

```shell
md5 /path/to/file
```

For example:

```shell
$ md5 KeePassXC-2.6.1.dmg
MD5 (KeePassXC-2.6.1.dmg) = b296a2c46572c4d6302fcbcc8c393b2d
```

### SHA-512 checksum

```shell
$ shasum -a 512 /path/to/file
```

For example:

```shell
$ shasum -a 512 KeePassXC-2.6.1.dmg
076f0c0ab202ee58849152695d8f23c6843fb16fe83aecac6f470a2cc3faeec0fc4f8909c4ac65894f1a22673cfa7a90ba06dfc789502168960d04ab97c369dc  KeePassXC-2.6.1.dmg
```