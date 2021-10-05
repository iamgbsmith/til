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
            06:9b:0e:d3:10:cc:a5:16:90:04:5a:57:cd:fc:a6:fc
    Signature Algorithm: sha256WithRSAEncryption
        Issuer: C=US, O=DigiCert Inc, OU=www.digicert.com, CN=DigiCert SHA2 High Assurance Server CA
        Validity
            Not Before: Sep  9 00:00:00 2021 GMT
            Not After : Dec  8 23:59:59 2021 GMT
        Subject: C=US, ST=California, L=Menlo Park, O=Facebook, Inc., CN=*.facebook.com
        Subject Public Key Info:
            Public Key Algorithm: id-ecPublicKey
                Public-Key: (256 bit)
                pub: 
                    04:c4:14:16:6f:2c:45:20:d3:bf:a6:0a:97:44:ab:
                    40:96:49:08:43:65:1b:d9:a2:44:22:d7:7c:0f:0b:
                    90:2c:6a:33:c1:e0:bc:8a:95:58:ec:5e:8b:8b:10:
                    26:79:be:82:80:df:21:84:01:fa:68:80:75:7f:c5:
                    36:1d:fe:ee:cd
                ASN1 OID: prime256v1
                NIST CURVE: P-256
        X509v3 extensions:
            X509v3 Authority Key Identifier: 
                keyid:51:68:FF:90:AF:02:07:75:3C:CC:D9:65:64:62:A2:12:B8:59:72:3B

            X509v3 Subject Key Identifier: 
                71:3C:25:1D:87:8A:91:E7:2C:F1:1F:CC:96:AC:6B:44:A6:26:C4:9D
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
                ...j.h.v..\./.w0".T..0.V..M..3.../ ..N.d....{..|......G0E.!......'.G.8.m.}.Do.j8AT..q.(.K.... ~~.=V.H.1..
.M6..
...a..,4.g...4.v.\.C....ED.^..V..7...G..s..^........{..|2.....G0E.!....D..8...T.r..H.iX.P....&..d.&.. $...m. g.%.ye....?.K.l...#jiUu...v......rd.........ij.{Kj..8.G........{..|d.....G0E.!......%.u&.......$7Q...#BH..P..... L(........"./S.?....[..+,O.h s.v
    Signature Algorithm: sha256WithRSAEncryption
         4b:34:06:a5:17:92:fb:c6:be:ef:23:2c:d5:ee:f7:76:16:04:
         cf:2b:65:db:46:b9:6f:e0:8f:58:e7:8d:07:6a:8e:f2:76:a7:
         28:26:f7:bb:79:ca:e9:c1:2c:f6:45:85:cb:b6:11:ba:cf:0e:
         77:75:fb:e3:86:92:1b:1f:01:9c:bd:e2:eb:bf:d4:0b:18:b1:
         f1:78:c7:b1:bb:77:60:85:29:5d:de:00:39:49:35:47:01:0f:
         b9:7d:0d:fb:ec:05:d6:3d:78:0c:14:8f:58:b9:20:38:36:65:
         91:2c:53:a0:2c:9b:3c:1d:c5:64:d0:80:cf:81:9f:9a:a6:0a:
         30:e8:05:7f:20:3d:57:e9:ab:bb:50:0f:7c:3f:f3:78:3c:1c:
         25:6c:27:ff:cd:9f:18:c2:3b:27:05:7b:2f:9c:e5:ec:a9:29:
         b4:ef:ad:52:0f:42:9f:da:91:2a:b6:f6:bb:61:45:9e:e0:54:
         c0:67:b2:e4:d2:9f:91:2c:93:d5:f4:c2:15:5d:cd:06:72:0c:
         9e:a5:44:6f:84:60:f8:fb:32:b1:5f:d3:92:de:99:8b:fd:99:
         77:e3:e7:a4:cf:2b:74:c6:4a:24:af:f0:8b:9a:3d:20:eb:fc:
         60:29:4d:ba:e8:a4:db:b2:21:96:bf:f9:67:4d:e0:e1:e6:fd:
         16:35:08:99
```
