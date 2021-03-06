---
title: "xxx"
keywords:  
sidebar: overview_sidebar
toc: false
permalink: xxx.html
summary: false
---

#### Status: ![Live](images/icons/api_live.png)

## Description


## Resource URL

Base URL (Dev1): https://api.dev1.ers.ncrs.nhs.uk/ers-api  

| Method       | URL | Authentication |
| -------------| --- | ---------------- |
| POST | /STU3/v1/ReferralRequest/{ubrn}/$ers.rejectReferral | Session Token [(Details)](develop_business_flow_bf001.html) |


## Operation Definition
- [eRS-RejectReferral-Operation-1](https://fhir.nhs.uk/STU3/OperationDefinition/eRS-RejectReferral-Operation-1)  

## Prerequisite Conditions
-
-
-

# INPUT

## Request Operation: Header

| Field Name | Value |
| ---------- | ----- |
| XAPI_ASID | The "Accredited System ID" issued to the third party |
| HTTP_X_SESSION_KEY | The session key generated by the [Authentication and Authorisation APIs](/develop_business_flow_bf001.html)  |
| Content-Type | `*/*`, `application/fhir+json` |
| If-Match | W/"`n`" |

Note: `n` is the VersionId of the Referral and this can be retrieved by fetching the Referral details.  
It must be the ID of the latest version of the referral in e-RS.

## Request Operation: Parameters

| Name | Cardinality | Type | Description |
| ---- | ----------- | ---- | ----------- |

### Example URI
```http
```

### Example Request Header
```http
```

### Example Request Body
##### Note: These examples may contain environment specific URLs and test data, these should be replaced with appropriate values for your implementation.  

- [Filename](downloads/json/[filename])  

# OUTPUT
## Response: Success
If successful, ...

### Example Response Header
```http
```

### Example Response Body
##### Note: These examples may contain environment specific URLs and test data, these should be replaced with appropriate values for your implementation.  

- [Filename](downloads/json/[filename])  

## Response: Failure
If an error occurs, the relating HTTP status code will be returned in the header.  

Where status code 422 (Unprocessable Entity) is returned then an eRS-OperationOutcome-1 will be included in the body, as detailed below:

| OutcomeKey | Description | Suggested Diagnostic |
| ---------- | ----------- | -------------------- |
