---
title: "A018: Re-book Appointment"
keywords: endpoint, catalogue
sidebar: overview_sidebar
toc: false
permalink: explore_endpoint_a018.html
summary: false
---

## API

| Request Type | URL |
| -------------| --- |
| POST | [/v1/ReferralRequest/{UBRN}/$ers.deferBooking](https://api.{env}.ers.ncrs.nhs.uk/ers-api/v1/ReferralRequest/{UBRN}/$ers.deferBooking)

## Description
This API lets the professional user to re-book an already booked appointment.

## Input

### Header
Provide ASID for the end-point system, Session Key and VersionId.

#### Example
```XAPI_ASID:200000000220
HTTP_X_SESSION_KEY:{sessionKey}
Accept:application/json+fhir
If-Match: W/"n"
```

### Body
Provide USRN, Re-booking reason, Rebooking comments and Clinical Information Intent Indicator.

#### Example
```{
"resourceType":"Parameters",
"meta":{
    "profile":"fhir.nhs.uk/OperationDefinition/ers-RebookDbsAppointment-operation-1"
},
"parameter":[
    {
       "name":"usrn",
       "valueString":"{{USRN}}"
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
