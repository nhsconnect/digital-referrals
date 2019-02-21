---
title: "A017: Defer Booking to Provider"
keywords: endpoint, catalogue
sidebar: overview_sidebar
toc: false
permalink: explore_endpoint_a017.html
summary: false
---

##### Status: ![Alpha](images/icons/api_alpha.png)

## API

| Method | URL |
| -------------| --- |
| POST | /ers-api/v1/ReferralRequest/{UBRN}/$ers.deferBooking

## Description
This API lets the professional user to defer a booking to a different Service Provider

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
Provide Service ID and Deferral Reason where you want this referral to defer to.

#### Example
```javascript
{
  "meta": {
    "profile": "http://fhir.nhs.uk/OperationDefinition/ers-DeferAppointment-operation-1"
  },
  "parameter": [{
    "name": "serviceId",
    "valueString": "6473294"
  },
  {
    "name": "deferralReason",
    "valueString": "SYSTEM_UNAVAILABLE"
  },

  {
    "name": "deferralComment",
    "valueString": "Test"
  }
   ]
}
```

## Output
If successful the URBN created in A011 is deferred to a different Service Provider. The response code 200 (OK) is returned. This response has no body.
