---
title: Get Connected
keywords: development, connection
sidebar: overview_sidebar
toc: false
permalink: getstarted_get_connected.html
summary: "How to get connected to the e-Referral APIs in a few simple steps"
---

## Three important things to know ##

Getting Connected is simple, but there are 3 important things to know:

1. Your organisation needs to be using a secure Health and Social Care Network (HSCN) Connection (previously N3)
2. APIs can only be accessed using a smartcard
3. You will need to apply for a unique End Point and some test data

If you do not have a HSCN Connection, please go to the following site to request one:

* [Connecting to HSCN](https://digital.nhs.uk/health-social-care-network/new-to-hscn/connecting-to-HSCN)

If you require a smartcard, please go to the following site to find out more:

* [Registration Authorities and Smartcards](https://digital.nhs.uk/Registration-Authorities-and-Smartcards)

## Access to the Development Environment ##
Once you have a smartcard and a HSCN connection, you are now ready to request access to our Development Environment in order to integrate with the e-Referral Service APIs. The first thing to do is request a new End Point, unique to your organisation. You can do so by filling in the following form:

* [End Point Registration Form](https://developer.nhs.uk/wp-content/uploads/2018/01/e-RS-API-EPR-Form-v1-4.docx)

Once you have downloaded the form, please enter the following information and return to (platforms.supportdesk@nhs.net)

1. Enter your name and contact details.
2. In section 1, enter the FQDN (must not be the same as an existing FQDN on the organisation code) and IP.
3. In section 2, enter the ODS code and name of your allocated testing organisation (i.e. the pack allocated by the test data team).
4. Enter the Source IP

## Generating a Certificate Signing Request ##

You will also need to generate and submit a Certificate Signing Request (CSR) and a Private Key to obtain an endpoint certificate for the requested FQDN. The CSR must have a key length of 2048 and have the common name set to the FQDN value. We recommend using [OpenSSL](http://slproweb.com/products/Win32OpenSSL.html) for this.

Please do specify alongside the request to the Platforms Support Desk the need to be allocated a ‘NHS e-RS-API Testing Pack’.

## Using existing smartcards ##

Suppliers with existing smartcards in Spine Development can have these remotely updated with the relevant Registration Authority (RA), enabling the allocated UUIDs to be issued locally, please include your Spine Development UUID in your initial request to the Platforms Support Desk (platforms.supportdesk@nhs.net) if this is required.

Those suppliers without existing smartcards in Spine Development can be posted an RA Card for the required organisation(s) so that they can issue their allocated UUIDs locally . Please specify the requirement in your initial request to the Platforms Support Desk (platforms.supportdesk@nhs.net) and include your Name and Postal Address.

If you have any queries about connecting to Spine Development (smartcards, endpoints, certificates, connectivity, CSRs), please contact (platforms.supportdesk@nhs.net)

## Final steps ##

Once you have received a certificate from our Solutions Assurance Desk you will need to follow a few simple steps that will allow you to begin your e-Referral Service Integration journey.

You need to install ROOT and SUBCA certificates. Here’s a handy guide to get you started:

* [Certificate Installation Guide.pdf](https://developer.nhs.uk/wp-content/uploads/2018/01/Install-ROOTCA-and-SUBCA-certificates-v1.0.pdf)

## Tools for exploration ##

After this is all set up, you can use either the API Client Demonstrator Tool (also known as Quick Connect) or [Postman](https://www.getpostman.com). In the latter case we recommend you install the full version of Postman tool and not just the Chrome add-in for Postman.

If you go down the API Client Demonstrator Tool route you will need to install [Keystore Explorer](http://keystore-explorer.org) in order to convert the CSR and private key into a JKS file. Please contact the NHS e-Referrals Integration team and they will be happy to provide more information about how to access this tool.
