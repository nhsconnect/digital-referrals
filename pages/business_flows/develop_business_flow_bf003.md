---
title: "Clinical Review"
keywords: business, flow
sidebar: overview_sidebar
toc: false
permalink: /develop_business_flow_bf003.html
summary: "Business flows for accepting, rejecting or adding instructions for further action"
---

###### Status: ![Live](images/icons/api_live.png)

#### Definition

This business flow describes the process of a provider-side clinician fetching referrals that are ready for review (together with the associated clinical information) and either accepting them into their service, rejecting them with a specific rejection reason and a comment (where appropriate) or moving the referral onto an admin worklist with notes for further action.


#### This business flow involves the following APIs

##### Authentication and Authorisation
* [A001 – Create Professional Session](explore_endpoint_a001.html) ![Live](images/icons/api_live.png)
* [A002 – Professional Session Select Role](explore_endpoint_a002.html) ![Live](images/icons/api_live.png)
* [A003 – Delete Professional Session](explore_endpoint_a003.html) ![Live](images/icons/api_live.png)

##### Reference Data
* [A004 - Retrieve Reference Data](explore_endpoint_a004_STU3.html) ![Live](images/icons/api_live.png)

##### Referral Review
* [A013 – Accept Referral](explore_endpoint_a013.html) ![Live](images/icons/api_live.png)
* [A014 – Reject Referral](explore_endpoint_a014.html) ![Live](images/icons/api_live.png)
* A0xx - Admin Action *(Available Q2 2020)*

#### Review the diagram below to learn more

![Clinical Review](images/develop/BF003-ClinicalTriage.png)
