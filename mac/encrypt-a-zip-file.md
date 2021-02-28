# Encrypt A Zip File

__Category: Mac__

For security reasons, it is best practice to encrypt all commercially sensitive files before sending them over email. Compressed files also use less disk space and data bandwidth than uncompressed files.

You can encrypt a zip file from the command line as follows:

### Encrypt a single file

```shell
zip -er encrypted-file.zip unencrypted-file.pdf
```

### Encrypt all files matching an extension type 

```shell
zip -er encrypted-files.zip *.pdf
```

When encrypting, you will be prompted to enter your password twice.