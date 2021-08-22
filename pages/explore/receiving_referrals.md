---
title: "Receiving and Reviewing e-Referrals for Service Providers"
keywords: Retrieving Referrals, Retrieve, CRI, attachments, worklist
sidebar: overview_sidebar
toc: false
permalink: /receiving_referrals.html
summary: "How to receive e-referrals into other systems using the e-RS integration APIs"
---

## Definition

This page describes the functionality available for receiving e-referrals into other software systems including how to retrieve the "Referrals for Review" worklist, the Clinical Referral Information (CRI) and any referral attachments (Sometimes known as "The referral letter") from the NHS e-Referral Service (e-RS). Further APIs also allow sending the result of a clinical review back to e-RS (i.e. Accept or Reject). These APIs have been developed in accordance with the [FHIR STU3](http://hl7.org/fhir/STU3/) specification, guidance for developers is available online [here](http://hl7.org/fhir/STU3/overview-dev.html).

## Process Diagram

[![Receiving Referrals](images/explore/Receiving Referrals2021.png)](images/explore/Receiving Referrals2021.png)  

## The following APIs are used to receive e-referrals from e-RS

### Authentication and Authorisation
* [A001 – Create Professional Session](explore_endpoint_a001.html) ![Live](images/icons/api_live.png)
* [A002 – Professional Session Select Role](explore_endpoint_a002.html) ![Live](images/icons/api_live.png)
* [A003 – Delete Professional Session](explore_endpoint_a003.html) ![Live](images/icons/api_live.png)

### Reference Data
* [A004 - Retrieve Reference Data](explore_endpoint_a004.html) ![Live](images/icons/api_live.png)

### Clinical Referral Information
* [A005 – Retrieve Referral Request](explore_endpoint_a005.html) ![Live](images/icons/api_live.png)
* [A006 – Retrieve Attachment](explore_endpoint_a006.html) ![Live](images/icons/api_live.png)
* [A007 – Retrieve Clinical Information](explore_endpoint_a007.html) ![Live](images/icons/api_live.png)
* [A008 – Retrieve Worklist](explore_endpoint_a008.html) ![Live](images/icons/api_live.png) ![Updated](images/icons/updated.png) ASI worklist now available


### Clinical Review
* [A013 – Accept Referral](explore_endpoint_a013.html) ![Live](images/icons/api_live.png)
* [A014 – Reject Referral](explore_endpoint_a014.html) ![Live](images/icons/api_live.png)
* [A022: Cancel Appointment, Action Later](explore_endpoint_a022.html) ![Live](images/icons/api_live.png)
* [A028: Record Review Outcome](explore_endpoint_a028.html) ![Live](images/icons/api_live.png)

### Advice & Guidance ![NEW](images/icons/new.png)
* [A023 - Retrieve Advice and Guidance Requests Worklist](explore_endpoint_a023.html) ![Live](images/icons/api_live.png)
* [A024 - Retrieve Advice and Guidance Request Summary](explore_endpoint_a024.html) ![Live](images/icons/api_live.png)
* [A025 - Retrieve Advice and Guidance Conversation](explore_endpoint_a025.html) ![Live](images/icons/api_live.png)
* [A026 - Send Advice and Guidance Response](explore_endpoint_a026.html) ![Live](images/icons/api_live.png)
* [A027 - Convert Advice and Guidance Request to Referral](explore_endpoint_a027.html) ![Live](images/icons/api_live.png)
