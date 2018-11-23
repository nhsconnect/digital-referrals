---
title: "A019: Generate Patient Letter API"
keywords: endpoint, catalogue, Letter
sidebar: overview_sidebar
toc: false
permalink: explore_endpoint_a019.html
summary: false
---

## API

| Request Type | URL |
| -------------| --- |
| POST | [v1/ReferralRequest/{UBRN}/$ers.generatePatientLetter](https://api.{ENV}.ers.ncrs.nhs.uk/ers-api/v1/ReferralRequest/{UBRN}/$ers.generatePatientLetter)

## Description
This API retrieves the Patient Appointment Request Letter once the referral request has been created (with or without uploaded attachments).

## Input

### Header
Provide ASID for the end-point system, Session Key, Content Type and Accept parameters.

#### Example
```http
XAPI_ASID:200000000220
HTTP_X_SESSION_KEY: pro-xapi-session_5a399946-23c5-4543-8c4f-7eca38732a58
Content-Type: application/json+fhir
Accept: */*
```

## Output
If successful:
```javascript
Response Status: 200 OK
Response Body: A PDF file with Patient Letter will be generated.
```
