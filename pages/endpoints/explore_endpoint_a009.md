---
title: "A009: Retrieve Generic Service Search"
keywords: endpoint, catalogue
sidebar: overview_sidebar
toc: false
permalink: explore_endpoint_a009.html
summary: false
---

##### Status: ![Alpha](images/icons/api_alpha.png)

## API

Base URL (Dev3): https://api.dev3.ers.ncrs.nhs.uk/ers-api/

| Method | URL |
| -------------| --- |
| POST | v1/HealthcareService/$dos.serviceSearch

## Description
This API lets the professional user retrieve directory of services that are available in e-RS.

## Input

### Header
Provide ASID for the end-point system and Session Key.

#### Example
```http
XAPI_ASID:200000000220
HTTP_X_SESSION_KEY:pro-xapi-session_5a399946-23c5-4543-8c4f-7eca38732a58
Accept:application/json+fhir
Content-Type:application/json
```

### Body
Provide search criteria to retrieve the services available e.g. Organisation Code, Postcode, Specialty, Clinic Type, Priority etc.

#### Example
```javascript
{
  "meta":{
     "profile":"http://fhir.nhs.uk/OperationDefinition/ers-PatientServiceSearch-operation-1"
  },
  "parameter":[
     {
        "name":"professionalPostcode",
        "valueString":"LS1 4HR"
     },
     {
        "name":"commissioningProvisioning",
        "valueString":"ALL_AVAILABLE_FOR_BOOKING"
     },
     {
        "name":"specialty",
        "valueString":"EAR_NOSE_THROAT"
     },
     {
        "name":"clinicType",
        "valueString":"EAR"
     },
     {
        "name":"priority",
        "valueString":"ROUTINE"
     },
     {
        "name":"clinicalTerm",
        "valueString":""
     },
     {
        "name":"namedClinicianId",
        "valueString":""
     },
     {
        "name":"organisationCode",
        "valueString":"R01"
     },
     {
        "name":"indicativeWaitTime",
        "valueString":""
     },
     {
        "name":"distanceLimit",
        "valueString":""
     },
     {
        "name":"sortBy",
        "valueString":"DISTANCE"
     }
  ]
}
```

## Output
If successful the list of directory services are returned. The response code `200 (OK)` is returned.

```javascript
Example
{
    "contained": [
        {
            "id": "1",
            "address": {
                "line": [
                    "NHS",
                    "1 WHITEHALL QUAY"
                ],
                "city": "LEEDS",
                "district": "WEST YORKSHIRE",
                "postalCode": "LS1 4HR",
                "country": "England"
            },
            "identifier": [
                {
                    "value": "R0101"
                }
            ],
            "name": "R01 TRUST SITE 01",
            "resourceType": "Location"
        }
    ],
    "type": "searchset",
    "total": 1,
    "entry": [
        {
            "resource": {
                "extension": [
                    {
                        "url": "http://fhir.nhs.uk/StructureDefinition/extension-ers-healthcareService-1-0",
                        "extension": [
                            {
                                "url": "bookable",
                                "valueCode": "DIRECTLY_BOOKABLE"
                            },
                            {
                                "url": "commissioningType",
                                "valueCode": "NATIONALLY_AVAILABLE"
                            },
                            {
                                "url": "capacityStatus",
                                "valueCode": "GOOD"
                            },
                            {
                                "url": "indicativeAppointmentWait",
                                "valueString": "7 days"
                            },
                            {
                                "url": "nhsChoicesLink",
                                "valueString": "http://www.nhs.uk/service-search/chooseandbook?serviceId=6473294"
                            },
                            {
                                "url": "prioritiesSupported",
                                "valueString": "ROUTINE,TWO_WEEK_WAIT,URGENT"
                            },
                            {
                                "url": "namedClinicians",
                                "valueString": "USERONE, Userone (Mr)"
                            },
                            {
                                "url": "appointmentType",
                                "valueString": "FIRST_OUTPATIENT"
                            },
                            {
                                "url": "serviceType",
                                "valueString": "APPOINTMENT,ADVICE"
                            },
                            {
                                "url": "organisationType",
                                "valueString": "NHS_TRUST"
                            },
                            {
                                "url": "exclusions",
                                "valueString": "Exclusions - Tongue"
                            },
                            {
                                "url": "conditionsTreated",
                                "valueString": "Conditions - Ear / Nose / Throat"
                            },
                            {
                                "url": "suggestedInvestigation",
                                "valueString": "Suggested - Ear Tests"
                            },
                            {
                                "url": "restricted",
                                "valueBoolean": false
                            },
                            {
                                "url": "accredited",
                                "valueBoolean": false
                            },
                            {
                                "url": "distance",
                                "valueInteger": 0
                            },
                            {
                                "url": "referralLetterRequired",
                                "valueBoolean": true
                            }
                        ]
                    }
                ],
                "identifier": [
                    {
                        "value": "6473294"
                    }
                ],
                "name": "SA ENT Service 002 - DBS - RL and CAS",
                "specialty": [
                    {
                        "coding": [
                            {
                                "code": "EAR_NOSE_THROAT"
                            }
                        ]
                    }
                ],
                "location": [
                    {
                        "reference": "#1"
                    }
                ],
                "resourceType": "HealthcareService"
            }
        }
    ],
    "resourceType": "Bundle"
}
```

<!--## Code Sample
Refer to the `API Client Demonstrator tool` source code.-->
