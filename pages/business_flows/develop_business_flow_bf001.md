---
title: "Authentication and Authorisation (Archived)"
keywords: business, flow
sidebar: overview_sidebar
toc: false
permalink: /develop_business_flow_bf001.html

---

## Status:

![Deprecated](images/icons/api_deprecated.png)

This site has now been archived.

Please visit [https://digital.nhs.uk/developer/api-catalogue/e-referral-service-fhir](https://digital.nhs.uk/developer/api-catalogue/e-referral-service-fhir) to learn more about how to integrate with the e-Referral Service (e-RS) FHIR API.

## Definition

This business flow describes the process of creating an authorised professional API session based upon an authenticated Care identify Service (CIS) smartcard. It makes use of the following NHS e-RS API Endpoints in order, with persisted rights to undertake further business workflows until the session is terminated.

## Using the identity agent
Guidance on using the identity agent and authenticating with NHS Smartcards can be found at [developer.nhs.uk/apis/spine-core/smartcards.html](https://developer.nhs.uk/apis/spine-core/smartcards.html)

## This business flow involves the following APIs

* [A001: Create Professional Session](explore_endpoint_a001.html) ![Live](images/icons/api_live.png)
* [A002: Professional Session Select Role](explore_endpoint_a002.html) ![Live](images/icons/api_live.png)
* [A003: Delete Professional Session](explore_endpoint_a003.html) ![Live](images/icons/api_live.png)

## Review the diagram below to learn more

![BF001: Authentication and Authorisation](images/develop/BF001-Auth.jpg)
