---
title: "A017: Defer Booking to Provider"
keywords: endpoint, catalogue
sidebar: overview_sidebar
toc: false
permalink: explore_endpoint_a017.html
summary: false
---

## API

| Request Type | URL |
| -------------| --- |
| POST | [/v1/ReferralRequest/{UBRN}/$ers.deferBooking](https://api.{env}.ers.ncrs.nhs.uk/ers-api/v1/ReferralRequest/{UBRN}/$ers.deferBooking)

## Description
This API lets the professional user to defer a booking to a different Service Provider

## Input

### Header
Provide ASID for the end-point system, Session Key and VersionId.

#### Example
```http
XAPI_ASID:200000000220
HTTP_X_SESSION_KEY:{sessionKey}
Accept:application/json+fhir
If-Match: W/"n"
```

### Body
Provide Service ID and Deferral Reason where you want this referral to defer to.

#### Example
```{
  "meta": {
    "profile": "http://fhir.nhs.uk/OperationDefinition/ers-DeferAppointment-operation-1"
  },
  "parameter": [{
    "name": "serviceId",
    "valueString": "{{ServiceID1_DEV}}"
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
