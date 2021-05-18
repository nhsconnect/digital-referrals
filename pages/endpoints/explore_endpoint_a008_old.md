---
title: "A008: Retrieve Worklist"
keywords: endpoint, catalogue
sidebar: overview_sidebar
toc: false
permalink: explore_endpoint_a008_old.html
summary: false
---

<div style="border: 2px solid #888888; padding: 10px; background: #c7c7c7;">If you are using the deprecated FHIR v2 endpoint, please click <a href="explore_endpoint_a008_DSTU2.html">here</a>.</div>

#### Status: ![Live](images/icons/api_live.png)

## Description
This API lets authorised users retrieve the ‘Referrals for Review’ work list. This work list gives details of new or outstanding referrals sent to the service by GPs and others. It includes their key attributes.


## Resource URL

| Method       | URL | Authentication |
| -------------| --- | ---------------- |
| POST | {Base URL}/STU3/v1/ReferralRequest/$ers.fetchworklist | Session Token [(Details)](develop_business_flow_bf001.html) |

- {Base URL} (Dev1) = https://api.dev1.ers.ncrs.nhs.uk/ers-api  


## Operation Definition
[eRS-FetchWorklist-Operation-1](https://fhir.nhs.uk/STU3/OperationDefinition/eRS-FetchWorklist-Operation-1)

## Prerequisite Conditions


# INPUT

## Request Operation: Header

| Field Name | Description |
| ---------- | ------------- |
| XAPI_ASID | The "Accredited System ID" issued to the third party |
| HTTP_X_SESSION_KEY | The session key generated by the Create Session endpoint (A001) |
| Content-Type | Example: "application/fhir+json" |

## Request Operation: Parameters

| Name | Cardinality | Type | Description |
| ---- | ----------- | ---- | ----------- |
| listType | 1..1 | CodeableConcept | Indicates the type of list requested, this is currently fixed to either 'REFERRALS_FOR_REVIEW' or 'APPOINTMENT_SLOT_ISSUES'. |
| service | 0..1 | Identifier | The service identifier |
| specialtyAssignedIndicator | 0..1 | CodeableConcept | Indicates whether a Specialty is assigned to the Referral Request. If 'Assigned' the 'Specialty' parameter must be present. If 'Not Assigned' the 'specialtyAssignedIndicator' and 'Specialty' parameter must be absent. |
| specialty | 0..1 | CodeableConcept | The Specialty for the service. If present, the 'specialtyAssignedIndicator' parameter must be set to 'Assigned'. The specialty list must be retrieved dynamically from the e-RS valueset. |
| location | 0..1 | Identifier | The service location identifier. |
| clinicianAssignedIndicator | 0..1 | CodeableConcept | Indicates whether a clinician is assigned to the Referral Request. If 'Assigned' the 'Clinician' parameter must be present. If 'Not Assigned' the 'Clinician' parameter must be absent. |
| clinician | 0..1 | Identifier | The clinician assigned to the Referral Request. If present, the 'ClinicianAssignedIndicator' parameter must be set to 'Assigned' |

### Example URI
```http
https://api.dev1.ers.ncrs.nhs.uk/ers-api/STU3/v1/ReferralRequest/$ers.fetchworklist
```

### Example Request Header
```http
"XAPI_ASID" : "999000000045",
"HTTP_X_SESSION_KEY" : "pro-api-session:06bdd8aa-da2c-45dc-bc73-bee80b70fe2d",
"Content-Type" : "application/fhir+json"
```

### Example Request Body
##### Note: These examples may contain environment specific URLs and test data, these should be replaced with appropriate values for your implementation.  

- [A008_Request.json](downloads/json/A008_Request.json)  

# OUTPUT
## Response: Success
If successful, all referrals from the ‘Referrals for Review’ worklist matching the input criteria are returned. The response code `200 (OK)` is returned.

### Example Response Header
```http
"X_ERS_TRANSACTION_ID" : "bfa90094-981a-4d2a-ad56-a17429865241-1",
"Content-Type" : "application/fhir+json"
```

### Example Response Body
##### Note: These examples may contain environment specific URLs and test data, these should be replaced with appropriate values for your implementation.  

- [A008_Response.json](downloads/json/A008_Response.json)

## Response: Failure
If an error occurs, the relating HTTP status code will be returned in the header.  

Where status code 422 (Unprocessable Entity) is returned then an eRS-OperationOutcome-1 will be included in the body, as detailed below:

| OutcomeKey | Description | Suggested Diagnostic |
| ---------- | ----------- | -------------------- |
| NO_RELATIONSHIP | The SPC user (or if SPCA, SPC user they are “on behalf of”) is not a workgroup member for the worklist. | The professional user must be associated to the following by current workgroup membership at the same e-RS organisation that the ""owner"" professional user is logged-in under:<br>Service<br>Location (if provided)<br>Specialty (if provided) |
| MISSING_VALUE | Either one or both of the following fields have not been provided:<br>Specialty<br>Clinician<br>The field is reported as the location of the error. | When attempting to filter the worklist by specialty and/or clinician, the value for specialty assigned or clinician assigned is 'assigned'.  A specialty or clinician must be provided in this scenario. |"
| UNEXPECTED_FIELD | A value for specialty and/or clinician has been provided when not required.  The field is reported as the location of the error. | When attempting to filter the worklist by specialty and/or clinician, the value for specialty assigned or clinician assigned is not 'assigned', a specialty or clinician is not required. |
| NO_SUCH_SERVICE | The service provided does not exist in e-RS. | When attempting to filter the worklist by service, the service ID must match an existing service in the eRS application.  Check the service is still active and published in the DOS (directory of services). |
| NO_SUCH_LOCATION | The location does not match a service location in e-RS. | When attempting to filter the worklist by location, the location ID must match an existing location in the eRS application.  Check the organisation is still active and not closed. |
| NO_SUCH_SPECIALTY | The specialty provided is not part of e-RS reference data. | When attempting to filter the worklist by specialty, the provided specialty is not recognised.  Check against existing reference data. |
| NO_SUCH_CLINICIAN | The clinician provided is not a recognised professional user in e-RS. | When attempting to filter the worklist by clinician, the provided clinician is not recognised.  Check against existing reference data. |
| INVALID_VALUE | The specialty assigned value is 'Not Assigned'. | This value may be allowed in future worklists. |