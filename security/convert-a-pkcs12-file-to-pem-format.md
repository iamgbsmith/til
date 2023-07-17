# Convert A PCKS12 File To PEM Format

You can convert a PKCS12 file to PEM format using OpenSSL.

The following command will put the certificate and private key into `newfile.pem`:

```shell
openssl pkcs12 -in certificate.p12 -out somefile.pem -clcerts -nodes 
```

The following command will put the certificate only into `somefile.crt.pem`:

```shell
openssl pkcs12 -in certificate.p12 -out somefile.crt.pem -clcerts -nokeys
```

__Note:__ You may be asked to enter your passphrase when running the above commands.
