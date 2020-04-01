---
title: "A016: Book Appointment"
keywords: endpoint, catalogue
sidebar: overview_sidebar
toc: false
permalink: explore_endpoint_a016.html
summary: false
---

##### Status: ![Alpha](images/icons/api_alpha.png)

## API

Base URL (Dev1): https://api.dev1.ers.ncrs.nhs.uk/ers-api/  

| Method | URL |
| -------------| --- |
| POST | v1/ReferralRequest/{UBRN}/$ers.bookdirect

## Description
This API lets the professional user book appointment for the slots returned in previous step A015.

## Input

### Header
Provide ASID for the end-point system, Session Key and VersionId.

#### Example
```http
XAPI_ASID:200000000203
HTTP_X_SESSION_KEY:pro-xapi-session_5a399946-23c5-4543-8c4f-7eca38732a58
Content-Type: application/json+fhir
If-Match: W/"n"
```

### Body
Provide USRN (the Unique Slot Reference Number of the new Appointment Slot that is being booked) retrieved in previous step A015.

#### Example
```javascript
{
"resourceType":"Parameters",
"meta":{
   "profile":"http://fhir.nhs.uk/OperationDefinition/ers-bookappointment-operation-1"
},
"parameter":[
   {
    "name":"usrn",
    "valueString":"00000000-0002-C1E7-0000-00F012598E8C"
   }
]
}
```

## Output
If successful the appointment slot is booked for the UBRN. The response code 200 (OK) is returned with blank response body.
