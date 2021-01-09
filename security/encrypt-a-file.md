# Encrypt A File

__Category: Security__

Encrypt a file using OpenSSL on Linux or Mac. When prompted for a password, enter a strong passphrase.

```shell
openssl enc -a -aes-256-gcm -in some-document.md -out some-document-encrypted.enc
```

Decrypt the file entering the passphrase when prompted:

```shell
openssl enc -d -a -aes-256-gcm -in some-document-encrypted.enc -out some-document.md
``` 

Options supplied to the above commands:

* `-aes-256-gcm` specifies the AES256 Galois/Counter Mode (GCM) algorithm
* `-a` base64 encodes the encrypted file or specifies that it is base64 encoded when decrypting
* `-d` decrypts a file
* `-pass` specifies a password source. This argument can have various formats: 
  * env:var to read it from the environment variable $var
  * file:pathname to read it from the file at pathname 
  * fd:number to read it from a given file descriptor
  * stdin to read it from standard input 
  * pass:password to specify the password directly in the command line (see below) 

If you do not use the `-pass` option you will be prompted for a password during the encryption/decryption process.

__Avoid using__ the `pass:password` for specifying the password directly in the command line as this could be read from the bash history.