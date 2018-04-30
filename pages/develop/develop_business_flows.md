---
title: Business Flows
keywords: business, flows
sidebar: overview_sidebar
toc: false
permalink: develop_business_flows.html
summary: "Business flows and their related endpoints"
---

## BF001: Authentication and Authorisation ##

This business flow describes the process of creating an authorised professional API session based upon an authenticated Care identify Service (CIS) smartcard. It makes use of the following NHS e-RS API Endpoints in order, with persisted rights to undertake further business workflows until the session is terminated.

* A001 – Create Professional Session
* A002 – Professional Session Select Role
* A003 – Delete Professional Session

Review the diagram below to learn more:

![BF001: Authentication and Authorisation](images/develop/BF001-Auth.jpg)

## BF002: Clinical Referral Information ##

This business flow describes the process of accessing Clinical Referral Information (CRI) from the NHS e-RS Solution. This will require a pre-authenticated professional API session to have been established. This suite of API has four core API elements and can be supplemented by an additional Reference Data or ValueSet API, to aid with search selection criteria.

* A008 – Retrieve Worklist
* A005 – Retrieve Referral Request
* A006 – Retrieve Attachment
* A007 – Retrieve Clinical Information

Review the diagram below to learn more:

![BF001: Authentication and Authorisation](images/develop/BF002-CRI.jpg)
