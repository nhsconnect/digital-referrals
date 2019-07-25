---
title: "Create Referral"
keywords: business, flow
sidebar: overview_sidebar
toc: false
permalink: /develop_business_flow_bf004.html
summary: "Business flows and their related endpoints"
---

###### Status: ![Beta](images/icons/api_beta.png)

#### Definition

This business flow describes the process of an authenticated user searching for services relevant for the selected patient. The search limits results to services which the user is able to refer the current patient into, based on the commissioning rules that apply to the user or the patient.

#### This business flow involves the following APIs

##### Authentication and Authorisation
* [A001 – Create Professional Session](explore_endpoint_a001.html) ![Live](images/icons/api_live.png)
* [A002 – Professional Session Select Role](explore_endpoint_a002.html) ![Live](images/icons/api_live.png)
* [A003 – Delete Professional Session](explore_endpoint_a003.html) ![Live](images/icons/api_live.png)

##### Reference Data
* [A004 - Retrieve Reference Data](explore_endpoint_a004.html) ![Live](images/icons/api_live.png)

##### Create Referral
* [A010 - Patient Service Search](explore_endpoint_a010.html) ![Beta](images/icons/api_beta.png)
* [A011 - Create Referral](explore_endpoint_a011.html) ![Beta](images/icons/api_beta.png)
* [A021 - Create Referral and Send for Triage](explore_endpoint_a021.html) ![Beta](images/icons/api_beta.png)
* [A020 - Upload File To Document Store](explore_endpoint_a020.html) ![Beta](images/icons/api_beta.png)
* [A012 - Maintain Referral Letter](explore_endpoint_a012.html) ![Beta](images/icons/api_beta.png)
* [A019 - Generate Patient Letter](explore_endpoint_a019.html) ![Beta](images/icons/api_beta.png)


<!-- #### Review the diagram below to learn more -->

<!-- ![BF004: Service Search](images/develop/BF004-ServiceSearch.jpg) -->
