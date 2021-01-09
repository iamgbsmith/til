# Install A Root Certificate

__Category: Linux__

You may need to install a root certificate on your system in the following scenarios:

* You are installing a self-signed certificate
* The certificate has been issued by a root Certificate Authority (CA) that is not known to your system

### Install the certificate - Ubuntu

The following steps will install a root certificate called `company-ca.crt`.

Copy the .crt file:

```
sudo cp /tmp/company-ca.cert /usr/local/share/ca-certificates/
```

Update the certificate store:

```
sudo update-ca-certificates
```

__Note: Only install certificates if you can vouch for their provenance.__