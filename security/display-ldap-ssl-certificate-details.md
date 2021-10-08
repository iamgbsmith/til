
# Display LDAP SSL Certificate Details

__Category: Security__

Communication between applications and an LDAP server should be secured using SSL certificates to provide transport-level encryption.

You can display the SSL certificte for an LDAP server with the following command:

```shell
openssl s_client -connect ldap.orbiks.com:636
```

Subsitute the host and port number for the actual values used by the LDAP server you are connecting to. If connecting to Active Directory, the port for LDAPS is typically set to 636.

Output:

```shell
CONNECTED(00000005)
depth=0 
...
Server certificate
-----BEGIN CERTIFICATE-----
MJIHuTCCBKGgAwIBAgITHQAAAp4a92eQtuPIvwABAAACnjANBgkqhkiG9w0BAQsF
ADBJMRUwEwYKCZImiZPyLGQBGRYFbG9jYWwxFjAUBgoJkiaJk/IsZAEZFgZjb21y
YWQxGDAWBgNVBAMTD0NvbXJhZCBMb2NhbCBDQTAeFw0yMDA2MDkwNDM4MzhaFw0y
MTA2MDkwNDM4MzhaMAAwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQCX
GDpOrUbLSmts7AvDLU2Nv+LOmKbr/FNraj4q97zPl1gHv/2EBBibqF/sEsIwjvdv
JsWqC2CUGst0McnXgYy1CA4nfwUMJNFsVaxirwnNGA6oJ6PJ5Ij2a7UvwSaBOcKL
P6JIBMoT+h/mHg7a7L8t9HOBB9nAV2bo7+oM48k3BMH/Cb8UlmjOrkM//r22mfcC
sMxLQugZe3Yv83cxY6WzP2NfDFCF8tjtpZPjJUUCHEPwtKkssVwZn/V1osROVmzv
Em9R6NlK9uWTkzDdjjT/Xvt7adLYYHnyMXeMaNa0zz0ncp1RxmDgbhRVcZ1Se+ZJ
rYbbxF1Zzg4qH33LGj4VAgMBAAGjggLhMIIC3TA4BgkrBgEEAYI3FQcEKzApBiEr
BgEEAYI3FQiGirpshKeMGILxhwuCu882g5KpZYFqASECAW4CAQAwMgYDVR0lBCsw
...
PWNvbXJhZCxEQz1sb2NhbD9jZXJ0aWZpY2F0ZVJldm9jYXRpb25MaXN0P2Jhc2U/
b2JqZWN0Q2xhc3M9Y1JMRGlzdHJpYnV0aW9uUG9pbnQwgcYGCCsGAQUFBwEBBIG5
MIG2MIGzBggrBgEFBQcwAoaBpmxkYXA6Ly8vQ049Q29tcmFkJTIwTG9jYWwlMjBD
QSxDTj1BSUEsQ049UHVibGljJTIwS2V5JTIwU2VydmljZXMsQ049U2VydmljZXMs
Q049Q29uZmlndXJhdGlvbixEQz1jb21yYWQsREM9bG9jYWw/Y0FDZXJ0aWZpY2F0
ZT9iYXNlP29iamVjdENsYXNzPWNlcnRpZmljYXRpb25BdXRob3JpdHkwDQYJKoZI
hvcNAQELBQADggEBAC9Bxk0KRBWqwxFL1qxNqfWIMIiC9iXvfZqK3j+MHvQiVqQu
yKef/Ck0V4OHTYRBINTuHiCdfMRr2VwPJtGzG/UoDpPYPuxbOYLNk1PqVKABm4MF
Gb9ovKSDE96Hch3vUzi6H+acXQmKvyTa1LVwJK2dOAZzwymbZg53r7hfzJSR8+zZ
xc97Y+BqB/au+qsCp2PWQzZSkK1wKTtjS6X8UBB9AlpwOruccHR9130bHyK3bulr
PP22SNJeT4zwPnwwJPFt+nA8WykJkROfXLq0aMG0GeR7LMvGcoZJeGl95RI9GA/l
HtoVOy5KeVCNT0tvVmpfVr5J+1Foefe/JtnMIAY=
-----END CERTIFICATE-----
...
```

If you need to use the certificate, take the lines between BEGIN CERTIFICATE and END CERTIFICATE (including the BEGIN and END lines) and save them to a file with a `.pem` extension.

You can then import the Base64 encoded DER certificate that you saved to a `.pem` file into a trust store used by your application.
