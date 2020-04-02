---
title: "BF002: Clinical Referral Information"
keywords: business, flow
sidebar: overview_sidebar
toc: false
permalink: /develop_business_flow_bf002.html
summary: "Business flows and their related endpoints"
---

###### Status: ![Live](images/icons/api_live.png)

#### Definition

This business flow describes the process of accessing Clinical Referral Information (CRI) from the NHS e-RS Solution. This will require a pre-authenticated professional API session to have been established. This suite of API has four core API elements and can be supplemented by an additional Reference Data or ValueSet API, to aid with search selection criteria.

#### This business flow involves the following APIs

##### Authentication and Authorisation
* [A001 – Create Professional Session](explore_endpoint_a001.html) ![Live](images/icons/api_live.png)
* [A002 – Professional Session Select Role](explore_endpoint_a002.html) ![Live](images/icons/api_live.png)
* [A003 – Delete Professional Session](explore_endpoint_a003.html) ![Live](images/icons/api_live.png)

##### Reference Data
* [A004 - Retrieve Reference Data](explore_endpoint_a004.html) ![Live](images/icons/api_live.png)

##### Clinical Referral Information
* [A005 – Retrieve Referral Request](explore_endpoint_a005.html) ![Live](images/icons/api_live.png)
* [A006 – Retrieve Attachment](explore_endpoint_a006.html) ![Live](images/icons/api_live.png)
* [A007 – Retrieve Clinical Information](explore_endpoint_a007.html) ![Live](images/icons/api_live.png)
* [A008 – Retrieve Worklist](explore_endpoint_a008.html) ![Live](images/icons/api_live.png)

#### Review the diagram below to learn more

![BF002: Clinical Referral Information](images/develop/BF002-CRI.jpg)
