---
title: "A013: Accept Referral"
keywords: endpoint, catalogue
sidebar: overview_sidebar
toc: false
permalink: explore_endpoint_a013.html
summary: false
---

## API

| Method | URL |
| -------------| --- |
| POST | /ers-api/v1/ReferralRequest/{UBRN}/$ers.accept

## Description
This API lets the professional user accept the Referral that has already been created and not reviewed.

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

Note: `n` is the VersionId of the Referral and this can be retrieved by fetching the Referral details.

## Output
If successful the referral is accepted. The response code `200 (OK)` is returned. This response has no body.

<!--## Code Sample
Refer to the `API Client Demonstrator tool` source code.-->
