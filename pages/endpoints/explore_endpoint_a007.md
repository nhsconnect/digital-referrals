---
title: "A007: Retrieve Clinical Information"
keywords: endpoint, catalogue
sidebar: overview_sidebar
toc: false
permalink: explore_endpoint_a007.html
summary: false
---

###### Status: ![Live](images/icons/api_live.png)

## API

| Method | URL |
| -------------| --- |
| GET | /ers-api/v1/Binary/$ers.generateCRI?UBRN={UBRN}

## Related FHIR model

* [eRS-ClinicalReferralInformation-Operation-1](https://data.developer.nhs.uk/specifications/eRS-draftd/Profile.ClinicalReferralInformationQuery/ers-clinicalreferralinformation-operation-1.html)

## Description
This API lets users create a real-time Portable Document Format (PDF) of the referral. This is suitable for integration into a 3rd party system. You can find the Clinical Information for a referral request using a UBRN.

## Input

### Header
Provide ASID of the end-point system and equivalent Session Key generated for the SSO Token-ID.

#### Example
```http
XAPI_ASID:200000000220
HTTP_X_SESSION_KEY:pro-xapi-session_5a399946-23c5-4543-8c4f-7eca38732a58
Accept:*/*
```

## Output
If successful a PDF of clinical referral information for referral is returned. The response code `200 (OK)` is returned.

<!--## Code Sample
Code snippets taken from the consumer example. See [Code Samples](develop_code_samples.html) for further details.-->

## Notes
Get the Clinical Referral Information for a Referral Request identified by the given UBRN.

### Parameters

| Parameter | Value | Description | Parameter Type | Data Type |
| --------- | ----- | ----------- | -------------- | --------- |
| UBRN |    | UBRN | Query | String |

### Response Messages

| HTTP Status Code | Reason |
| ---------------- | ------ |
| 200 | OK |
| 403 | Forbidden |
| 404 | Not Found |
