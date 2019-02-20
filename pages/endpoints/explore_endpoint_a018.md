---
title: "A018: Re-book Appointment"
keywords: endpoint, catalogue
sidebar: overview_sidebar
toc: false
permalink: explore_endpoint_a018.html
summary: false
---

## API

| Method | URL |
| -------------| --- |
| POST | /ers-api/v1/ReferralRequest/{UBRN}/$ers.deferBooking |

## Description
This API lets the professional user to re-book an already booked appointment.

## Input

### Header
Provide ASID for the end-point system, Session Key and VersionId.

#### Example
```http
XAPI_ASID:200000000220
HTTP_X_SESSION_KEY:pro-xapi-session_5a399946-23c5-4543-8c4f-7eca38732a58
Accept:application/json+fhir
If-Match: W/"n"
```

### Body
Provide USRN, Re-booking reason, Rebooking comments and Clinical Information Intent Indicator.

#### Example
```javascript
{
"resourceType":"Parameters",
"meta":{
    "profile":"fhir.nhs.uk/OperationDefinition/ers-RebookDbsAppointment-operation-1"
},
"parameter":[
    {
       "name":"usrn",
       "valueString":"00000000-0002-C1E8-0000-00F012598E8C"
    },
    {
       "name": "rebookingReason",
       "valueString":"PATIENT_ILL"
    },
    {
       "name": "rebookingReasonComments",
       "valueString":"test"
    },
    {
       "name":"clinicalInformationIntent",
       "valueString":"NOT_INTENDING_TO_ADD"
    }
]
}
```

## Output
If successful the appointment is re-booked to a different date and time. The response code 200 (OK) is returned. This response has no body.
