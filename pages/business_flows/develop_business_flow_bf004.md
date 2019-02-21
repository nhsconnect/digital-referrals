---
title: "Create Referral"
keywords: business, flow
sidebar: overview_sidebar
toc: false
permalink: /develop_business_flow_bf004.html
summary: "Business flows and their related endpoints"
---

###### Status: ![Alpha](images/icons/api_alpha.png)

#### Definition

This business flow describes the process of an authenticated user searching for services relevant for the selected patient. The search limits results to services which the user is able to refer the current patient into, based on the commissioning rules that apply to the user or the patient.

#### Prerequisites
A professional session must be created and [Reference Data Retrieved](explore_endpoint_a004.html)

#### This business flow involves the following APIs

* [A010 - Patient Specific Service Search](explore_endpoint_a010.html) ![Alpha](images/icons/api_alpha.png)
* [A011 - Create Referral](explore_endpoint_a011.html) ![Alpha](images/icons/api_alpha.png)
* [A020 - Upload File To Document Store](explore_endpoint_a020.html) ![Alpha](images/icons/api_alpha.png)
* [A012 - Maintain Referral Letter](explore_endpoint_a012.html) ![Alpha](images/icons/api_alpha.png)
* [A019 - Retrieve Patient Letter](explore_endpoint_a019.html) ![Beta](images/icons/api_beta.png)


<!-- #### Review the diagram below to learn more -->

<!-- ![BF004: Service Search](images/develop/BF004-ServiceSearch.jpg) -->
