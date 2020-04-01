---
title: Get Connected
keywords: development, connection
sidebar: overview_sidebar
toc: false
permalink: getstarted_get_connected.html
summary: "How to get connected to the e-Referral APIs in a few simple steps"
---

## Prerequisites for connection

To use the e-RS Integration APIs you must:

1. Use a secure Health and Social Care Network (HSCN) Connection (or an N3 connection until migration to HSCN)
2. Have an NHS smartcard with valid e-RS role for the data you are requesting or submitting
3. Be issued with a unique Endpoint (and specific test data for use in development environments)

#### HSCN connections ##

If you do not have a HSCN or N3 Connection, please go to the following site to request one:

* [Connecting to HSCN](https://digital.nhs.uk/health-social-care-network/new-to-hscn/connecting-to-HSCN)

#### NHS Smartcards

If you require a smartcard, please go to the following site to find out more:

* [Registration Authorities and Smartcards](https://digital.nhs.uk/Registration-Authorities-and-Smartcards)  


## Access to development environments ##
To request access to a test environment to connect to for development and testing purposes, please contact [platforms.supportdesk@nhs.net](mailto:platforms.supportdesk@nhs.net) and request the following:

1. Access to the e-RS Integration APIs in the e-RS DEV1 development environment
2. Allocation of an e-RS Integration API Test Pack for e-RS DEV1
3. Issue of Smartcard(s) for e-RS development  
  (If you already have smartcard please include the UUIDs so they can be re-used if possible)

#### Using existing smartcards
Suppliers with existing smartcards in Spine Development can have these remotely updated with the relevant Registration Authority (RA), enabling the allocated UUIDs to be issued locally, please include your Spine Development UUID in your initial request to the Platforms Support Desk (platforms.supportdesk@nhs.net) if this is required.

<!-- ## Further details on connecting

#### Generating a Certificate Signing Request

You will also need to generate and submit a Certificate Signing Request (CSR) and a Private Key to obtain an endpoint certificate for the requested FQDN.

1. The CSR must have a key length of 2048.
2. The common name must be set to the FQDN value.

We recommend using [OpenSSL](http://slproweb.com/products/Win32OpenSSL.html) for this.

Once installed, Open Command Prompt and run the below command to configure the `openssl.cfg` file:

```shell
C:\OpenSSL-Win32\bin>set OPENSSL_CONF=C:\OpenSSL-Win32\bin\openssl.cfg
```

Change the directory to `C:\OpenSSL-Win32\bin` and run the below command to generate the CSR by replacing _"Test-FQDN"_ and the org code, e.g. _"O=ROB"_, with yours:

```shell
openssl req -new -newkey rsa:2048 -nodes -out Test-FQDN.cfh.nhs.uk.csr -keyout Test-FQDN.cfh.nhs.uk.key -subj "/C=GB/ST=/L=na/O=ROB/OU=na/CN=Test-FQDN.cfh.nhs.uk"
```

The CSR along with the private key will be generated and available in `C:\OpenSSL-Win32\bin` folder as per the above FQDN details.

Please specify alongside the request to the Platforms Support Desk the need to be allocated a ‘NHS e-RS-API Testing Pack’.

#### Registry Settings ##

Please install “IAConfig2.msi” by downloading the IAConfig.zip archive from [http://nww.hscic.gov.uk/dir/downloads/index.html#ia_config](http://nww.hscic.gov.uk/dir/downloads/index.html#ia_config) (Can only be accessed via N3)

Once installed you should be able to apply the DEV Registry settings to access the e-RS/DEV1 environment.

#### Identity Agent ##

Please install the Identity Agent and Middleware from [http://nww.hscic.gov.uk/dir/downloads/index.html](http://nww.hscic.gov.uk/dir/downloads/index.html) (Can only be accessed via HSCN/N3)

#### Unblocking IP addresses ##

If you want to unblock certain IP addresses as part of this process, please email the [Platforms Support Desk](platforms.supportdesk@nhs.net).

#### Installing ROOT and SUBCA Certificates

Once you have received a certificate from our Platforms Support Desk you will need to follow a few simple steps that will allow you to begin your e-Referral Service Integration journey.

You need to install ROOT and SUBCA certificates, download the [Certificate Installation Guide](https://developer.nhs.uk/wp-content/uploads/2018/01/Install-ROOTCA-and-SUBCA-certificates-v1.0.pdf) for more details. -->
