---
title: "A010: Retrieve Patient Specific Search"
keywords: endpoint, catalogue
sidebar: overview_sidebar
toc: false
permalink: explore_endpoint_a010.html
summary: false
---

## API

| Request Type | URL |
| -------------| --- |
| POST | [/v1/HealthcareService/$patient.serviceSearch](https://api.{env}.ers.ncrs.nhs.uk/ers-api/v1/HealthcareService/$patient.serviceSearch)

## Description
This API lets the professional user retrieve patient-specific services that are available in e-RS.

## Input

### Header
Provide ASID for the end-point system and Session Key.

#### Example
```http
XAPI_ASID:200000000220
HTTP_X_SESSION_KEY:{sessionKey}
Accept:application/json+fhir
Content-Type:application/json
```

### Body
Provide search criteria to retrieve the services available e.g. Patient NHS Number, Postcode, Specialty, Clinic Type, Priority, Distance Limit etc.

#### Example
```javascript
{
  "meta":{
     "profile":"http://fhir.nhs.uk/OperationDefinition/ers-PatientServiceSearch-operation-1"
  },
  "parameter":[
     {
        "name":"patientPostcode",
        "valueString":"LS1 4HR"
     },
     {
    "name":"patientNhsNumber",
    "valueString":"9476659793"
     },
     {
      "name":"namedClinicianId",
      "valueString":""
     },
     {
    "name":"requestType",
    "valueString":"APPOINTMENT_REQUEST"
     },
     {
        "name":"commissioningProvisioning",
        "valueString":"ALL_AVAILABLE_FOR_BOOKING"
     },
     {
        "name":"priority",
        "valueString":"ROUTINE"
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
        "name":"clinicalTerm",
        "valueString":""
     },
     {
        "name":"indicativeWaitTime",
        "valueString":""
     },
     {
        "name":"organisationCode",
        "valueString":"R01"
     },
     {
        "name":"distanceLimit",
        "valueString":"5"
     },
     {
        "name":"sortBy",
        "valueString":"DISTANCE"
        },
     {
        "name":"referringClinicianId",
        "valueString":""
     }
  ]
}
```

## Output
If successful the list of patient-specific services are returned. The response code `200 (OK)` is returned.

#### Example
```javascript
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
                                "valueBoolean": true
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
