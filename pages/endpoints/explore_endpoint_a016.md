---
title: "A016: Book Appointment"
keywords: endpoint, catalogue
sidebar: overview_sidebar
toc: false
permalink: explore_endpoint_a016.html
summary: false
---

## API

| Request Type | URL |
| -------------| --- |
| POST | [/v1/ReferralRequest/{UBRN}/$ers.bookdirect](https://api.{env}.ers.ncrs.nhs.uk/ers-api/v1/ReferralRequest/{UBRN}/$ers.bookdirect)

## Description
This API lets the professional user book appointment for the slots returned in previous step A015.

## Input

### Header
Provide ASID for the end-point system, Session Key and VersionId.

#### Example
```http
XAPI_ASID:{ASID}
HTTP_X_SESSION_KEY:{sessionKey}
Content-Type: application/json+fhir
If-Match: W/"n"
```

### Body
Provide USRN (the Unique Slot Reference Number of the new Appointment Slot that is being booked) retrieved in previous step A015.

#### Example
```javascript
{
"resourceType":"Parameters",
"meta":{
   "profile":"http://fhir.nhs.uk/OperationDefinition/ers-bookappointment-operation-1"
},
"parameter":[
   {
    "name":"usrn",
    "valueString":"00000000-0002-C1E7-0000-00F012598E8C"
   }
]
}
```

## Output
If successful the appointment slot is booked for the UBRN. The response code 200 (OK) is returned with blank response body.

### Example
```{
    "contained": [
        {
            "id": "1",
            "extension": [
                {
                    "url": "http://fhir.nhs.uk/StructureDefinition/extension-ers-healthcareServiceSlotSearchItem-1-0",
                    "extension": [
                        {
                            "url": "slotAvailabilityStatus",
                            "valueCode": "HAS_SLOT"
                        },
                        {
                            "url": "serviceId",
                            "valueInteger": 6473294
                        }
                    ]
                }
            ],
            "resourceType": "HealthcareServiceSlotSearchItem"
        },
        {
            "id": "2",
            "actor": [
                {
                    "id": "Practitioner/100000873988",
                    "reference": "SASHA BATTY"
                },
                {
                    "id": "HealthcareServiceSlotSearchItem/#1"
                }
            ],
            "resourceType": "Schedule"
        }
    ],
    "type": "searchset",
    "total": 6,
    "entry": [
        {
            "resource": {
                "identifier": "00000000-0002-C1E7-0000-00F00C63AD8C",
                "status": "free",
                "start": "2018-07-11T09:00:00.000Z",
                "end": "2018-07-11T09:29:00.000Z",
                "schedule": {
                    "reference": "#2"
                },
                "resourceType": "Slot"
            }
        },
        {
            "resource": {
                "identifier": "00000000-0002-C1E7-0000-00F012598E8C",
                "status": "free",
                "start": "2018-07-11T10:00:00.000Z",
                "end": "2018-07-11T10:29:00.000Z",
                "schedule": {
                    "reference": "#2"
                },
                "resourceType": "Slot"
            }
        },
        {
            "resource": {
                "identifier": "00000000-0002-C1E7-0000-00F0184F6F8C",
                "status": "free",
                "start": "2018-07-11T11:00:00.000Z",
                "end": "2018-07-11T11:29:00.000Z",
                "schedule": {
                    "reference": "#2"
                },
                "resourceType": "Slot"
            }
        },
        {
            "resource": {
                "identifier": "00000000-0002-C1E8-0000-00F00C63AD8C",
                "status": "free",
                "start": "2018-07-12T09:00:00.000Z",
                "end": "2018-07-12T09:29:00.000Z",
                "schedule": {
                    "reference": "#2"
                },
                "resourceType": "Slot"
            }
        },
        {
            "resource": {
                "identifier": "00000000-0002-C1E8-0000-00F012598E8C",
                "status": "free",
                "start": "2018-07-12T10:00:00.000Z",
                "end": "2018-07-12T10:29:00.000Z",
                "schedule": {
                    "reference": "#2"
                },
                "resourceType": "Slot"
            }
        },
        {
            "resource": {
                "identifier": "00000000-0002-C1E8-0000-00F0184F6F8C",
                "status": "free",
                "start": "2018-07-12T11:00:00.000Z",
                "end": "2018-07-12T11:29:00.000Z",
                "schedule": {
                    "reference": "#2"
                },
                "resourceType": "Slot"
            }
        }
    ],
    "resourceType": "Bundle"
}
```
