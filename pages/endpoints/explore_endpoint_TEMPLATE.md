---
title: "A0xx: Template"
keywords: endpoint, catalogue
sidebar: overview_sidebar
toc: false
permalink: explore_endpoint_template.html
summary: false
---
### Image Map test

<img src="images/assure/roles_responsibilities.png" usemap="#image-map">

<map name="image-map">
    <area target="_blank" alt="System Supplier" title="System Supplier" href="https://digital.nhs.uk/data-and-information/information-standards/information-standards-and-data-collections-including-extractions/publications-and-notifications/standards-and-collections/dcb0129-clinical-risk-management-its-application-in-the-manufacture-of-health-it-systems" coords="203,353,60" shape="circle">
    <area target="_blank" alt="End User Org" title="End User Org" href="https://digital.nhs.uk/data-and-information/information-standards/information-standards-and-data-collections-including-extractions/publications-and-notifications/standards-and-collections/dcb0160-clinical-risk-management-its-application-in-the-deployment-and-use-of-health-it-systems" coords="948,350,58" shape="circle">
</map>


### API

| Method | URL | Authentication |
| -------------| --- | ---------------- |
| POST | URL String Example | Session Token [(Details)](develop_business_flow_bf001.html) |

### Description
Describe the purpose of this endpoint and what can be achieved by using it.

### Prerequisite Operations
List any endpoints that must be used prior to calling this endpoint.
(E.g. Reference data etc.)  

### Request Operation

#### Request Header

| Field Name | Value |
| --------- | ---- |
| XAPI_ASID | ASID |
| Accept | application/json |
| Accept-Encoding | gzip,deflate |
| Content-Type | application/json |

#### Request Body Parameters
A full list of available parameters is described in the FHIR documentation available [here.](++ ADD LINK +++)

#### Mandatory parameters

| Parameter | Data Type | Notes |
| --------- | --------- | ----- |
| Parameter | String | Usage notes |

##### Example code

<details><summary>Request Header</summary>
  <br>
  <pre>
  XAPI_ASID:200000000220
  Accept:application/json
  Accept-Encoding:gzip,deflate
  Content-Type:application/json
  </pre>
</details>

<details><summary>Request Body</summary>
<br>
  <p>
    <pre>
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

    </pre>
  </p>
</details>

### Response

#### Response Header
A response code is returned.

#### Response Body
(Resource type expected)

#### Response Messages

| HTTP Code | Reason | Notes |
| --------- | ------ |
| 201 | Created | Operation Successful, record created  |
| 403 | Forbidden | ... |
| 422 | Unprocessable Entity | Provided data could not be processed due to a validation error |
