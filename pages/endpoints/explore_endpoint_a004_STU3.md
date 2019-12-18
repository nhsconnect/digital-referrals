---
title: "A004: Retrieve Reference Data"
keywords: endpoint, catalogue
sidebar: overview_sidebar
toc: false
permalink: explore_endpoint_a004_STU3.html
summary: false
---

##### Status: ![Beta](images/icons/api_beta.png)

## API

Base URL (Dev3): https://api.dev3.ers.ncrs.nhs.uk/ers-api/

| Method | URL |
| -------------| --- |
| GET | STU3/v1/CodeSystem/{CodeSystemID} |

## Related FHIR model

[eRS-Specialty-CodeSystem-1](https://fhir.nhs.uk/STU3/StructureDefinition/eRS-Specialty-CodeSystem-1)

## Description
This read-only API lets a user access a pre-populated list of reference data. The NHS e-Referral Service uses these lists throughout. For example, a list of specialities. They support data accuracy and effective re-use. It retrieves a specific Reference Dataset by ID.

## Reference Data
Reference data is classified into 2 types:

### Static lists
These are documented on the FHIR server and can be looked up “manually” and stored _once and for all_ in the database.

* Values and associated business logic, such as adding/removing options (e.g. Priority, Request Type, Commissioning Type) - this means creating new business flows in the application, which means an upgrade is probably needed
* Standard FHIR lists

### Dynamic lists
These are “gettable” from e-RS; third parties should handle them as _dynamic_ data, i.e. adding/removing values should not require a software upgrade.

* The only dynamic list we have so far is _Specialty_
* The next forthcoming dynamic list is _Clinic Type_
* In future we will be adding _Rebooking Reasons/Cancellation Reasons_ and other dynamics lists

## Input
Currently applicable values for the {CodeSystemID}:

| CodeSystemID | Description |
| ------------ | ----------- |
| SPECIALTY | Specialties defined in e-RS |

### Header
Provide ASID of the end-point system and equivalent Session Key generated for the SSO Token-ID.

#### Example
```XAPI_ASID:200000000220
Content-Type:application/json+fhir
HTTP_X_SESSION_KEY:pro-xapi-session_5a399946-23c5-4543-8c4f-7eca38732a58
```

## Output  
A [Resource](https://fhir.nhs.uk/STU3/StructureDefinition/eRS-Specialty-CodeSystem-1) profiled specifically for the given CodeSystemID. This will include the requested coding system with its available codes. The response code `200 (OK)` is returned.

#### Example
```javascript
{
  "resourceType": "CodeSystem",
  "id": "SPECIALTY",
  "meta": {
    "profile": [
      "https://fhir.nhs.uk/STU3/StructureDefinition/eRS-Specialty-CodeSystem-1"
    ]
  },
  "url": "[e-RS host]/CodeSystem/SPECIALTY",
  "name": "eRS Specialty",
  "status": "active",
  "description": "eRS Specialty",
  "content": "complete",
  "concept": [
    {
      "extension": [
        {
          "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-eRS-EffectivefromDate-1",
          "valueDate": "2004-06-01"
        }
      ],
      "code": "SURGERY_NOT_OTHERWISE_SPECIFIED",
      "display": "Surgery - Not Otherwise Specified",
      "designation": [
        {
          "value": "100"
        }
      ]
    },
    {
      "extension": [
        {
          "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-eRS-EffectivefromDate-1",
          "valueDate": "2004-06-01"
        }
      ],
      "code": "UROLOGY",
      "display": "Urology",
      "designation": [
        {
          "value": "101"
        }
      ]
    },
    {
      "extension": [
        {
          "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-eRS-EffectivefromDate-1",
          "valueDate": "2004-06-01"
        },
        {
          "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-eRS-EffectivetoDate-1",
          "valueDate": "2008-05-09"
        }
      ],
      "code": "TRANSPLANTATION_SURGERY",
      "display": "Transplantation Surgery",
      "designation": [
        {
          "value": "102"
        }
      ]
    }
  ]
}
```

## Notes
Consuming applications must have a valid session in order to access this endpoint.
