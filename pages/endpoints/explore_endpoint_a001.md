---
title: "A001: Create Professional Session"
keywords: endpoint, catalogue
sidebar: overview_sidebar
toc: false
permalink: explore_endpoint_a001.html
summary: false
---

##### Status: ![Live](images/icons/api_live.png)

## Description
As an e-RS user working in an integrated system  
I want to create a Professional Session in the Spine using my smartcard roles
So that I can securely access e-RS functions through my integrated system

## Resource URL

Base URL (Dev1): https://api.dev1.ers.ncrs.nhs.uk/ers-api/  

| Method | URL |
| -------------| --- |
| POST | v1/ProfessionalSession


### Prerequisite Conditions
- HSCN / N3 Connection
- NHS Smartcard with e-RS role(s)

### Using the identity agent
Guidance on using the identity agent and authenticating with NHS Smartcards can be found at [developer.nhs.uk/apis/spine-core/smartcards.html](https://developer.nhs.uk/apis/spine-core/smartcards.html)

# INPUT

## Request Operation: Header

| Field Name | Value |
| ---------- | ----- |
| XAPI_ASID  | The "Accredited System ID" issued to the third party |


## Request Operation: Parameters

| Name | Description |
| ---- | ----------- |
| token | Token from the Smartcard |

### Example Request Header
```http
XAPI_ASID:200000000220
Accept:application/json
Accept-Encoding:gzip,deflate
Content-Type:application/json
```

### Example Request Body

[Request Body](https://nhsconnect.github.io/digital-referrals/downloads/json/A001_Request.json)  

# OUTPUT
## Response: Success

The response code `201 (Created)` is returned. The created [Professional Session Resource](explore_models.html) is returned with available user permissions populated.

Once the session has been created a list of applicable permissions for the user will be returned. The session will not be usable until a permission/role has been selected using the [A002 Select Role](explore_endpoint_a002.html) endpoint.

The `ProfessionalSession.id` returned should be included as a header `(HTTP_X_SESSION_KEY)` for all subsequent requests.

### Example Response Body
[Response](https://nhsconnect.github.io/digital-referrals/downloads/json/A001_Response.json)


## Response: Failure
If an error occurs, the relating [HTTP status code](explore_error_messages.html) will be returned in the header.

Where status code 422 (Unprocessable Entity) is returned then an [eRS-OperationOutcome-1](https://fhir.nhs.uk/STU3/StructureDefinition/eRS-OperationOutcome-1) will be included in the body, as detailed below.  

| OutcomeKey | Description | Suggested Diagnostic |
| ---------- | ----------- | -------------------- |
