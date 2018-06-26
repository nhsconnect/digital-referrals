---
title: "A008: Retrieve Worklist"
keywords: endpoint, catalogue
sidebar: overview_sidebar
toc: false
permalink: explore_endpoint_a008.html
summary: false
---

## API

| Request Type | URL |
| -------------| --- |
| POST [/v1/ReferralRequest/$ers.fetchworklist](https://api.{env}.ers.ncrs.nhs.uk/ers-api/v1/ReferralRequest/$ers.fetchworklist)

## Description
This API lets authorised users retrieve the ‘Referrals for Review’ work list. This is the same as the existing interface. This work list gives details of new referrals sent to the service by GPs and others. It includes their key attributes.

## Input

### Header
Provide ASID of the end-point system and equivalent Session Key generated for the SSO Token-ID.

#### Example
```http
XAPI_ASID:200000000220
HTTP_X_SESSION_KEY:{sessionKey}
Content-Type:application/json+fhir
```

### Body
Provide ‘Referrals for Review’ worklist parameter.

#### Example
```javascript
{
   "resourceType":"Parameters",
   "meta":{
      "versionId":"1",
      "profile":[
         "http://fhir.nhs.uk/OperationDefinition/ers-fetchworklist-operation-1"
      ]
   },
   "parameter":[
      {
         "name":"listType",
         "valueCodeableConcept":{
            "coding":[
               {
                  "system":"http://fhir.nhs.uk/ValueSet/ers-referrallistselector-1",
                  "code":"REFERRALS_FOR_REVIEW"
               }
            ]
         }
      }
   ]
}
```

## Output
If successful referrals under ‘Referrals for Review’ worklist are returned. The response code `200 (OK)` is returned.

#### Example
```javascript
{
    "meta": {
        "profile": [
            "http://fhir.nhs.uk/StructureDefinition/ers-fetchworklist-list-1"
        ]
    },
    "resourceType": "List",
    "contained": [
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
            "id": "Patient-9461838328",
            "meta": {
                "profile": [
                    "http://fhir.nhs.uk/StructureDefinition/ers-patient-1"
                ]
            },
            "resourceType": "Patient",
            "identifier": [
                {
                    "system": "http://fhir.nhs.uk/Id/nhs-number",
                    "value": "9461838328"
                }
            ]
        }
    ],
    "status": "current",
    "mode": "snapshot",
    "entry": [
        {
            "extension": [
                {
                    "extension": [
                        {
                            "url": "specialty",
                            "valueCodeableConcept": {
                                "coding": [
                                    {
                                        "system": "http://fhir.nhs.uk/ValueSet/ers-specialty-1",
                                        "code": "EAR_NOSE_THROAT"
                                    }
                                ]
                            }
                        },
                        {
                            "url": "requestContextStatus",
                            "valueCodeableConcept": {
                                "coding": [
                                    {
                                        "system": "http://fhir.nhs.uk/ValueSet/ers-requestcontextstatus-1",
                                        "code": "NEVER_REVIEWED",
                                        "display": "Never Reviewed"
                                    }
                                ]
                            }
                        },
                        {
                            "url": "allocatedClinician",
                            "valueReference": {
                                "reference": "#Practitioner-100000873988"
                            }
                        },
                        {
                            "url": "clinicalInfoPrinted",
                            "valueBoolean": false
                        },
                        {
                            "url": "clinicalInfoFirstSubmitted",
                            "valueDateTime": "2017-07-27T13:41:11.552Z"
                        },
                        {
                            "url": "dateWhenBookingMade",
                            "valueDateTime": "2017-07-27T13:42:10.967Z"
                        },
                        {
                            "url": "appointmentStart",
                            "valueDateTime": "2017-08-04T13:00:00.000Z"
                        },
                        {
                            "url": "priority",
                            "valueCodeableConcept": {
                                "coding": [
                                    {
                                        "system": "http://fhir.nhs.uk/ValueSet/ers-priority-1",
                                        "code": "ROUTINE"
                                    }
                                ]
                            }
                        },
                        {
                            "url": "patient",
                            "valueReference": {
                                "reference": "#Patient-9461838328"
                            }
                        }
                    ],
                    "url": "http://fhir.nhs.uk/StructureDefinition/extension-ers-referralsforreview-worklistitem-1"
                }
            ],
            "item": {
                "reference": "ReferralRequest/000048417799"
            }
        }
    ]
}
```

<!--## Code Sample
Code snippets taken from the consumer example. See [Code Samples](https://developer.nhs.uk/library/systems/e-rs/ecosystem/develop/code/) for further details.

## Notes
TODO-->

### Response Messages

HTTP Status Code | Reason | Response Model | Headers
---------------- | ------ | -------------- | -------
403	| Forbidden |
422	| Unprocessable Entity – Provided data could not be processed due to a validation error. |
