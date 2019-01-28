---
title: "A0xx: Template"
keywords: endpoint, catalogue
sidebar: overview_sidebar
toc: false
permalink: /explore_endpoint_template.html
summary: false
---

## API

| Request Type | URL |
| -------------| --- |
| POST | [URL]() |

## Description
Describe the purpose of this endpoint and what can be achieved by using it.

## Prerequisites
List any endpoints that must be used prior to calling this endpoint.
(E.g. Authentication, Reference data etc.)  

## Request Operation

### Request Header

| Parameter | Mandatory | Value |
| --------- | --------- | ----- |
| Accept | application/json | - |
| Accept-Encoding | gzip,deflate | - |
| Content-Type:application/json | - | - |

### Request Body Parameters

| Parameter | Mandatory | Data Type | Length | Restrictions |
| --------- | --------- | --------- | ------ | ------------ |
| - | - | - | - | - |

#### Example Request Header
```http
XAPI_ASID:200000000220
Accept:application/json
Accept-Encoding:gzip,deflate
Content-Type:application/json
```

#### Example Request Body
```javascript
{
 "typeInfo": "uk.nhs.ers.xapi.dto.v1.session.ProfessionalSession",
 "token": " AQIC5wM2LY4Sfcyw62EbAOsRpdfbGYUOyvkfZ4M6U7W52lM=@AAJTSQACMDE=#"
}
```

#### Example

<details><summary>EXPAND</summary>
<p>
```javascript
{
    "typeInfo": "uk.nhs.ers.xapi.dto.v1.session.ProfessionalSession",
    "id": "pro-xapi-session_222c42c7-820f-4f9b-92fb-3add4b1db9f7",
    "token": "AQIC5wM2LY4Sfcyw62EbAOsRpdfbGYUOyvkfZ4M6U7W52lM=@AAJTSQACMDE=#",
    "user": {
        "identifier": "555020964101",
        "firstName": "SA Assurance",
        "lastName": "GP-Card",
        "middleName": null,
        "permissions": [
            {
                "businessFunction": "REFERRING_CLINICIAN",
                "orgIdentifier": "R01",
                "orgName": "NHST_X3"
            },
            {
                "businessFunction": "REFERRING_CLINICIAN_ADMIN",
                "orgIdentifier": "R01",
                "orgName": "NHST_X3"
            },
            {
                "businessFunction": "SERVICE_DEFINER",
                "orgIdentifier": "R01",
                "orgName": "NHST_X3"
            },
            {
                "businessFunction": "SERVICE_PROVIDER_CLINICIAN",
                "orgIdentifier": "R01",
                "orgName": "NHST_X3"
            },
            {
                "businessFunction": "SERVICE_PROVIDER_CLINICIAN_ADMIN",
                "orgIdentifier": "R01",
                "orgName": "NHST_X3"
            }
        ]
    },
    "permission": null
}
```
</p>
</details>

## Response

### Response Header
The response code `201 (Created)` is returned.

### Response Body
Empty.

### Response Messages

| HTTP Status Code | Reason | Response Model | Headers |
| ---------------- | ------ | -------------- | ------- |
| 201 | Created |

### Example Response Header

## Error codes

| HTTP Status Code | Reason | Response Model | Headers |
| ---------------- | ------ | -------------- | ------- |
| 403 | Forbidden |
| 422 | Unprocessable Entity – Provided data could not be processed due to a validation error |
