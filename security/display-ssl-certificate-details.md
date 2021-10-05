# Display SSL Certificate Details
 
__Category: Security__
 
You can display the details of a remote SSL certficate from the command line. For example, the following will inspect the SSL certificate for facebook.com
 
```shell
echo | openssl s_client -showcerts -connect facebook.com:443 2>/dev/null | openssl x509 -inform pem -noout -text
```
 
Output:
 
```shell
Certificate:
    Data:
        Version: 3 (0x2)
        Serial Number:
            03:77:ed:dc:fa:f8:be:34:ba:23:3c:7c:2b:9a:31:7f
    Signature Algorithm: sha256WithRSAEncryption
        Issuer: C=US, O=DigiCert Inc, OU=www.digicert.com, CN=DigiCert SHA2 High Assurance Server CA
        Validity
            Not Before: Feb 10 00:00:00 2021 GMT
            Not After : May 10 23:59:59 2021 GMT
        Subject: C=US, ST=California, L=Menlo Park, O=Facebook, Inc., CN=*.facebook.com
        Subject Public Key Info:
            Public Key Algorithm: id-ecPublicKey
                Public-Key: (256 bit)
                pub:
                    04:43:82:04:65:9a:86:61:6f:53:bf:48:a1:8a:8a:
                    7f:76:be:d1:e8:89:32:ac:a0:68:61:3c:71:5b:18:
                    73:9d:d7:4e:41:e5:bf:3b:51:44:5c:6d:36:d8:25:
                    39:01:68:cd:f1:64:34:66:00:0d:c0:ed:ab:5e:59:
                    b0:8d:7c:5b:73
                ASN1 OID: prime256v1
                NIST CURVE: P-256
        X509v3 extensions:
            X509v3 Authority Key Identifier:
                keyid:51:68:FF:90:AF:02:07:75:3C:CC:D9:65:64:62:A2:12:B8:59:72:3B
 
            X509v3 Subject Key Identifier:
                A1:DE:5B:01:7E:24:95:35:8A:6B:D8:F1:A2:D8:DE:6C:F2:7F:D0:72
            X509v3 Subject Alternative Name:
                DNS:*.facebook.com, DNS:*.facebook.net, DNS:*.fbcdn.net, DNS:*.fbsbx.com, DNS:*.m.facebook.com, DNS:*.messenger.com, DNS:*.xx.fbcdn.net, DNS:*.xy.fbcdn.net, DNS:*.xz.fbcdn.net, DNS:facebook.com, DNS:messenger.com
            X509v3 Key Usage: critical
                Digital Signature
            X509v3 Extended Key Usage:
                TLS Web Server Authentication, TLS Web Client Authentication
            X509v3 CRL Distribution Points:
 
                Full Name:
                  URI:http://crl3.digicert.com/sha2-ha-server-g6.crl
 
                Full Name:
                  URI:http://crl4.digicert.com/sha2-ha-server-g6.crl
 
            X509v3 Certificate Policies:
                Policy: 2.23.140.1.2.2
                  CPS: http://www.digicert.com/CPS
 
            Authority Information Access:
                OCSP - URI:http://ocsp.digicert.com
                CA Issuers - URI:http://cacerts.digicert.com/DigiCertSHA2HighAssuranceServerCA.crt
 
            X509v3 Basic Constraints: critical
                CA:FALSE
            1.3.6.1.4.1.11129.2.4.2:
.g.a.3..@.......U....!..t.(.'.I^r9 5jk.mY..e...-........w.\.C....ED.^..V..7...G..s..^........w.........H0F.!..X...d..17...6..Y......<....i.$..!...w......g.j}Y./..?...f4Mb..+..c
    Signature Algorithm: sha256WithRSAEncryption
         6a:f3:8f:ad:44:76:ae:a3:7f:80:56:51:3e:03:3b:0d:7b:2e:
         40:63:e0:36:4f:ba:d1:10:6e:94:d3:82:02:ae:11:f5:cf:b1:
         c5:79:8d:83:e5:08:11:e1:e6:b7:6d:4e:b7:30:7b:4a:c6:0a:
         31:ff:70:9d:a3:f0:94:38:79:d1:48:89:6e:d3:18:e3:96:8d:
         84:ed:0d:8a:ae:2d:52:70:bb:43:cc:43:af:f8:ba:76:43:a1:
         25:34:ac:24:d9:6b:66:56:e4:ed:fc:77:ea:9a:8e:3f:95:b6:
         75:4b:7a:9c:17:a6:b8:d7:5c:0d:70:0e:a9:9d:5f:77:03:f6:
         e5:5a:19:31:3c:fc:0f:92:e5:79:3f:f3:05:5e:49:78:d6:cb:
         2b:14:24:17:10:d3:17:bb:40:2a:ae:df:22:91:ea:71:83:b8:
         de:89:24:f8:2c:00:49:58:c3:57:63:4f:f7:88:22:13:de:03:
         8c:28:df:2c:c9:80:7e:12:74:05:d6:27:4e:18:63:34:41:2a:
         ec:ad:0c:d7:78:5e:c4:70:31:81:f1:77:20:2e:9f:40:38:78:
         f3:a3:7d:2f:a9:bc:8c:0a:9f:24:48:12:29:24:83:07:18:9e:
         5d:f5:89:23:0b:27:eb:ab:0d:f1:58:20:43:51:f5:42:e0:5e:
         7e:73:0c:f1
```
