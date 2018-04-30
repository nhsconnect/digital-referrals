---
title: "A014: Reject Referral"
keywords: endpoint, catalogue
sidebar: overview_sidebar
toc: false
permalink: explore_endpoint_a014.html
summary: false
---

## API

| Request Type | URL |
| -------------| --- |
| POST | [/v1/ReferralRequest/{UBRN}/$ers.reject](https://api.{env}.ers.ncrs.nhs.uk/ers-api/v1/ReferralRequest/{UBRN}/$ers.reject)

## Description
This API lets the professional user reject the Referral with reject reason and comment.

## Input

### Header
Provide ASID for the end-point system, Session Key and VersionId.

#### Example
```http
XAPI_ASID:200000000220
HTTP_X_SESSION_KEY:{{sessionKey}}
Accept:application/json+fhir
If-Match: W/"n"
```

Note: `n` is the VersionId of the Referral and this can be retrieved by fetching the Referral details.

### Body
Provide reject details such as reject reason and reject comment.

#### Example
```javascript
{
 "resourceType": "Parameters",
 "meta": {
        "versionId": "1",
        "profile": ["http://fhir.nhs.net/OperationDefinition/ers-rejectreferral-operation-1"]
    },
 "parameter": [
   {
     "name": "reason",
     "valueString": "OTHER"
   },
    {
     "name": "comment",
     "valueString": "Test"
    }
 ]
}
```

Note: If it’s an IBS service, use below extra field:

```javascript
{
"name": "cancelledInPas",
"valueString": "true/false"
}
```

## Output
If successful the referral is rejected. The response code `200 (OK)` is returned. This response has no body.

<!--## Code Sample
Refer to the `API Client Demonstrator tool` source code.-->
