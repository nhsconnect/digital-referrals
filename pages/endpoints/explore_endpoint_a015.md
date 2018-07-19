---
title: "A015: Retrieve Appointment Slots"
keywords: endpoint, catalogue
sidebar: overview_sidebar
toc: false
permalink: explore_endpoint_a015.html
summary: false
---

## API

| Request Type | URL |
| -------------| --- |
| POST | [/v1/Slot/$ers.searchAppointmentSlots](https://api.{env}.ers.ncrs.nhs.uk/ers-api/v1/Slot/$ers.searchAppointmentSlots)

## Description
This API lets the professional user retrieve appointment slots to book a slot for the UBRN created in A011.

## Input

### Header
Provide ASID for the end-point system, Session Key and Content-Type.

#### Example
```http
XAPI_ASID:200000000203
HTTP_X_SESSION_KEY:pro-xapi-session_5a399946-23c5-4543-8c4f-7eca38732a58
Content-Type: application/json+fhir
```

### Body
Provide Service details to fetch the available appointment slots e.g. Service ID, Exclusion Days, Start and End Dates etc.

#### Example
```javascript
{
  "parameter": [{
      "name": "patientNhsNumber",
      "value": "9476659793"
    },
    {
      "name": "serviceID",
      "value": "6473294"
    },
    {
      "name": "priority",
      "valueCoding": {
        "system": "fhir.nhs.priority",
        "code": "ROUTINE"
      }
    },

    {
      "name": "excludeDay",
      "valueCoding": {
        "system": "http://hl7.org/fhir/ValueSet/days-of-week",
        "code": "mon"
      }
    },
        {
      "name": "excludeDay",
      "valueCoding": {
        "system": "http://hl7.org/fhir/ValueSet/days-of-week",
        "code": "tue"
      }
    },
    {
      "name": "excludeDate",
      "valueDate": "2018-07-20"
    },
    {
      "name": "excludeDate",
      "valueDate": "2018-07-21"
    },
    {
      "name": "startDate",
      "valueDate": "2018-07-03"
    },
    {
      "name": "endDate",
      "valueDate": "2018-09-30"
    },
    {
      "name": "paginated",
      "valueBoolean": true
    },

    {
      "name": "pageNumber",
      "valueInteger": 1
    },
    {
      "name": "resultsPerPage",
      "valueInteger": 20
    }
  ]
}
```

## Output
If successful the available appointment slots are retrieved. The response code 200 (OK) is returned.

### Example
```javascript
{
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
