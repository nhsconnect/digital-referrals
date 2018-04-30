---
title: "A011: Create Referral Shortlist"
keywords: endpoint, catalogue
sidebar: overview_sidebar
toc: false
permalink: explore_endpoint_a011.html
summary: false
---

## API

| Request Type | URL |
| -------------| --- |
| POST | [/v1/CreateReferral](https://api.{env}.ers.ncrs.nhs.uk/ers-api/v1/CreateReferral)

## Description
This API lets the professional user create a referral request through shortlist.

## Input

### Header
Provide ASID for the end-point system and Session Key.

#### Example
```http
XAPI_ASID:200000000220
HTTP_X_SESSION_KEY:{sessionKey}
Accept:application/json+fhir
```

### Body
Provide referral details that will need to be created e.g. Patient NHS Number, Service details etc.

#### Example
```javascript
{
   "extension":[
      {
         "url":"http://fhir.nhs.net/StructureDefinition/extension-ers-referralRequest-1-0",
         "extension":[
            {
               "url":"alertedToLimitedCapacity",
               "valueBoolean":false
            },
            {
               "url":"clinicalInformationIntent",
               "valueBoolean":true
            },
            {
               "url":"contentSensitive",
               "valueBoolean":false
            },
            {
               "url":"firstReminderFollowUpDays",
               "valueInteger":14
            },
            {
               "url":"referrerRightOverrideComment",
               "valueString":""
            }
         ]
      }
   ],
   "resourceType":"ReferralRequest",
   "searchCriteria":{
      "parameter":[
         {
            "name":"patientNhsNumber",
            "valueString":"9476659793"
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
            "name":"namedClinicianId",
        	"valueString":""
         },
         {
            "name":"requestType",
            "valueString":"APPOINTMENT_REQUEST"
         },
         {
            "name":"patientPostcode",
            "valueString":"LS1 4HR"
         },
         {
            "name":"commissioningProvisioning",
            "valueString":"ALL_AVAILABLE_FOR_BOOKING"
         },
         {
            "name":"organisationCode",
        	"valueString":""
         },
         {
        	"name":"sortBy",
        	"valueString":"DISTANCE"
         },
         {
        	"name":"referringClinicianId",
        	"valueString":""
         },
         {
        	"name":"distanceLimit",
        	"valueString":""
         }
      ]
   },
   "shortlist":{
      "resourceType":"Bundle",
      "total":1,
      "entry":[
         {
            "resource":{
               "extension":[
                  {
                     "url":"http://fhir.nhs.net/StructureDefinition/extension-ers-healthcareService-1-0"
                  }
               ],
               "resourceType":"HealthcareService",
               "identifier":[
                  {
                     "value":"6473294"
                  }
               ]
            }
         }
      ]
   }
}
```

## Output
If successful the referral request is created with UBRN and Version Id. The response code `201 (Created)` is returned.

#### Example
```javascript
{
    "meta": {
        "versionId": "3"
    },
    "extension": [
        {
            "url": "http://fhir.nhs.net/StructureDefinition/extension-ers-referralRequest-1-0",
            "extension": []
        }
    ],
    "identifier": {
        "value": "000048421055"
    },
    "resourceType": "ReferralRequest"
}
```

<!--## Code Sample
Refer to the `API Client Demonstrator tool` source code.-->
