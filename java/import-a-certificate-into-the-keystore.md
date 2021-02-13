# Import A Certificate Into The KeyStore

__Category: Java__

KeyStore is a repository of certificates, public, and private keys used by the JVM.

It may be necessary to import a root or intermediate CA certificate into a KeyStore to establish a chain of trust for a JVM when connecting over HTTPS or LDAPS. A .cer file contains public X.509 keys and can be used only for identity verification.

With the CA certificate in Base64 encoded X.509 (.CER) format, you can install it into the Java KeyStore using the following command:

```shell
keytool -import -storepass changeit -trustcacerts -file /path/to/some-ca.cer -alias some-ca -keystore /path/to/cacerts
```

The new certificate will be loaded after restarting the JVM process.