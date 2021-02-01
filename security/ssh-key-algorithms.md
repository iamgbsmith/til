# SSH Key Algorithms

__Category: Security__

Generating SSH keys with `ssh-keygen` allows for use of different algorithms such as RSA (Rivest–Shamir–Adleman) or Ed25519 (Edwards-curve Digital Signature). 

## Which key type should I use?

[Practical Cryptography With Go](https://leanpub.com/gocrypto/read#leanpub-auto-chapter-5-digital-signatures) suggests that Ed25519 keys are more secure and performant than RSA keys. Ed25519 is [designed to be faster](https://en.wikipedia.org/wiki/EdDSA) than existing digital signature schemes without sacrificing security.

Use the following command to generate an Ed25519 key:

```shell
ssh-keygen -t ed25519 -C "your.email@example.com"
```

## What if I need to use an RSA based key?

By default, the ssh-keygen command creates an 1024-bit RSA key.

If you use RSA keys for SSH the US National Institute of Standards and Technology recommends that you use a [size of at least 2048 bits](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-57Pt3r1.pdf). 

Additionally, whilst it is possible to specify 4096 bits, this key size takes [30% longer](https://expeditedsecurity.com/blog/measuring-ssl-rsa-keys) to negotiate the SSL browser handshake than a 2048 bit key. 

Use the following command to generate a 2048 bit RSA key:

```shell
ssh-keygen -t rsa -b 2048 -C "your.email@example.com"
```



