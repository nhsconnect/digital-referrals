---
title: "A005: Retrieve Referral Request"
keywords: endpoint, catalogue
sidebar: overview_sidebar
toc: false
permalink: explore_endpoint_a005_DSTU2.html
summary: false
---

<div style="border: 2px solid #888888; padding: 10px; background: #c3e3c3;">For the new FHIR v3 endpoint, please click <a href="explore_endpoint_a005.html">here</a>.</div>

##### Status: ![Deprecated](images/icons/api_deprecated.png)  

## API

Base URL (Dev1): https://api.dev1.ers.ncrs.nhs.uk/ers-api/  

| Method | URL |
| -------------| --- |
| GET | v1/ReferralRequest/{id}

## Related FHIR model

* [eRS-ReferralRequest-1](https://data.developer.nhs.uk/specifications/eRS-draftd/Profile.ReferralsForReviewWorklistResponse/ers-referralrequest-1.html)

## Description
This API gets the referral request identified by the given ID. For each new referral, the user will be able to get key data attributes. External systems can show these in their system. The user can then see status and content header info.

## Input

### Header
Provide ASID of the end-point system and equivalent Session Key generated for the SSO Token-ID.

#### Example
```http
XAPI_ASID:200000000220
HTTP_X_SESSION_KEY:pro-xapi-session_5a399946-23c5-4543-8c4f-7eca38732a58
```

## Output
If successful referral details are returned. The response code `200 (OK)` is returned.

#### Example
```javascript
Example:
{
    "id": "000048420911",
    "meta": {
        "versionId": "5",
        "profile": [
            "http://fhir.nhs.uk/StructureDefinition/ers-referralrequest-1"
        ]
    },
    "resourceType": "ReferralRequest",
    "extension": [
        {
            "url": "http://fhir.nhs.uk/StructureDefinition/extension-ers-appointment-1",
            "valueReference": {
                "reference": "#appointment"
            }
        },
        {
            "url": "http://fhir.nhs.uk/StructureDefinition/extension-ers-clinicalinfofirstsubmitted-1",
            "valueDateTime": "2018-01-15T14:07:40.564Z"
        }
    ],
    "contained": [
        {
            "id": "HealthcareService-6473294",
            "meta": {
                "profile": [
                    "http://fhir.nhs.uk/StructureDefinition/ers-healthcareservice-1"
                ]
            },
            "resourceType": "HealthcareService",
            "serviceName": "SA ENT Service 002 - DBS - RL and CAS",
            "identifier": {
                "system": "http://fhir.nhs.uk/Id/ers-service",
                "value": "6473294"
            },
            "location": {
                "reference": "#Location-R0101"
            }
        },
        {
            "id": "Location-R0101",
            "meta": {
                "profile": [
                    "http://fhir.nhs.uk/StructureDefinition/ers-location-1"
                ]
            },
            "resourceType": "Location",
            "identifier": {
                "system": "http://fhir.nhs.uk/Id/ods-site-code",
                "value": "R0101"
            }
        },
        {
            "id": "DocumentReference-26807",
            "meta": {
                "profile": [
                    "http://fhir.nhs.uk/StructureDefinition/ers-documentreference-1"
                ]
            },
            "resourceType": "DocumentReference",
            "type": {
                "coding": [
                    {
                        "system": "http://fhir.nhs.uk/ValueSet/ers-attachmenttype-1",
                        "code": "REFERRER"
                    }
                ]
            },
            "status": "current",
            "indexed": "2018-01-16T16:33:13.178Z",
            "description": "",
            "content": [
                {
                    "attachment": {
                        "id": "26807",
                        "extension": [
                            {
                                "url": "http://fhir.nhs.uk/StructureDefinition/extension-ers-attachedby-1",
                                "valueReference": {
                                    "reference": "#Practitioner-555022085101"
                                }
                            }
                        ],
                        "contentType": "text/html",
                        "url": "Binary/att-48420728-26807",
                        "size": 548,
                        "title": "HTML TEST.html",
                        "creation": "2018-01-15"
                    }
                }
            ]
        },
        {
            "id": "DocumentReference-26808",
            "meta": {
                "profile": [
                    "http://fhir.nhs.uk/StructureDefinition/ers-documentreference-1"
                ]
            },
            "resourceType": "DocumentReference",
            "type": {
                "coding": [
                    {
                        "system": "http://fhir.nhs.uk/ValueSet/ers-attachmenttype-1",
                        "code": "REFERRER"
                    }
                ]
            },
            "status": "current",
            "indexed": "2018-01-16T16:33:13.178Z",
            "description": "",
            "content": [
                {
                    "attachment": {
                        "id": "26808",
                        "extension": [
                            {
                                "url": "http://fhir.nhs.uk/StructureDefinition/extension-ers-attachedby-1",
                                "valueReference": {
                                    "reference": "#Practitioner-555022085101"
                                }
                            }
                        ],
                        "contentType": "image/jpeg",
                        "url": "Binary/att-48420728-26808",
                        "size": 8631,
                        "title": "JPE TEST.JPE",
                        "creation": "2018-01-15"
                    }
                }
            ]
        },
        {
            "id": "Practitioner-100000873988",
            "meta": {
                "profile": [
                    "http://fhir.nhs.uk/StructureDefinition/ers-practitioner-1"
                ]
            },
            "resourceType": "Practitioner",
            "identifier": [
                {
                    "system": "http://fhir.nhs.uk/Id/sds-user-id",
                    "value": "100000873988"
                }
            ]
        },
        {
            "id": "Practitioner-555022085101",
            "meta": {
                "profile": [
                    "http://fhir.nhs.uk/StructureDefinition/ers-practitioner-1"
                ]
            },
            "resourceType": "Practitioner",
            "identifier": [
                {
                    "system": "http://fhir.nhs.uk/Id/sds-user-id",
                    "value": "555022085101"
                }
            ]
        },
        {
            "id": "Patient-9476659793",
            "meta": {
                "profile": [
                    "http://fhir.nhs.uk/StructureDefinition/ers-patient-1"
                ]
            },
            "resourceType": "Patient",
            "identifier": [
                {
                    "system": "http://fhir.nhs.uk/Id/nhs-number",
                    "value": "9476659793"
                }
            ]
        },
        {
            "id": "appointment",
            "meta": {
                "profile": [
                    "http://fhir.nhs.uk/StructureDefinition/ers-appointment-1"
                ]
            },
            "resourceType": "Appointment",
            "status": "booked",
            "start": "2018-01-31T12:00:00.000Z",
            "end": "2018-01-31T12:29:00.000Z",
            "participant": [
                {
                    "actor": {
                        "reference": "#HealthcareService-6473294",
                        "display": "SA ENT Service 002 - DBS - RL and CAS"
                    },
                    "status": "accepted"
                },
                {
                    "type": {
                        "coding": [
                            {
                                "system": "http://hl7.org/fhir/ValueSet/encounter-participant-type",
                                "code": "CON"
                            }
                        ]
                    },
                    "actor": {
                        "reference": "#Practitioner-100000873988"
                    },
                    "status": "accepted"
                }
            ]
        }
    ],
    "status": "active",
    "specialty": {
        "coding": [
            {
                "system": "http://fhir.nhs.uk/ValueSet/ers-specialty-1",
                "code": "EAR_NOSE_THROAT"
            }
        ]
    },
    "priority": {
        "coding": [
            {
                "system": "http://fhir.nhs.uk/ValueSet/ers-priority-1",
                "code": "ROUTINE"
            }
        ]
    },
    "patient": {
        "reference": "#Patient-9476659793"
    },
    "supportingInformation": [
        {
            "reference": "#DocumentReference-26808"
        },
        {
            "reference": "#DocumentReference-26807"
        }
    ]
}
```

<!--## Code Sample
Code snippets taken from the consumer example. See [Code Samples](develop_code_samples.html) for further details.

## Notes
To follow.-->
