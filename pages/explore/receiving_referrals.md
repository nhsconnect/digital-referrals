---
title: "Receiving e-Referrals for Service Providers"
keywords: Retrieving Referrals, Retrieve, CRI, attachments, worklist
sidebar: overview_sidebar
toc: false
permalink: /receiving_referrals.html
summary: "How to receive e-referrals into other systems using the e-RS integration APIs"
---

#### Definition

This page describes the functionality available for receiving e-referrals into external software systems including how to retrieve the "Referrals for Review" worklist, the Clinical Referral Information (CRI) and any referral attachments (Sometimes known as "The referral letter") from the NHS e-Referral Service (e-RS). This will require a pre-authenticated professional API session to have been established. These APIs have been developed in accordance with the [FHIR STU3](http://hl7.org/fhir/STU3/) specification, guidance for developers is available online [here](http://hl7.org/fhir/STU3/overview-dev.html).

#### The following APIs are used to receive e-referrals from e-RS

##### Authentication and Authorisation
* [A001 – Create Professional Session](explore_endpoint_a001.html) ![Live](images/icons/api_live.png)
* [A002 – Professional Session Select Role](explore_endpoint_a002.html) ![Live](images/icons/api_live.png)
* [A003 – Delete Professional Session](explore_endpoint_a003.html) ![Live](images/icons/api_live.png)

##### Reference Data
* [A004 - Retrieve Reference Data](explore_endpoint_a004_DSTU2.html) ![Live](images/icons/api_live.png)

##### Clinical Referral Information
* [A005 – Retrieve Referral Request](explore_endpoint_a005.html) ![Live](images/icons/api_live.png)
* [A006 – Retrieve Attachment](explore_endpoint_a006.html) ![Live](images/icons/api_live.png)
* [A007 – Retrieve Clinical Information](explore_endpoint_a007.html) ![Live](images/icons/api_live.png)
* [A008 – Retrieve Worklist](explore_endpoint_a008.html) ![Live](images/icons/api_live.png)

#### Logical Process Diagram

![Receiving Referrals](images/explore/receiving_referrals.png)   
