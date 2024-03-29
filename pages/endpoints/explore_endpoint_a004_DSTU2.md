---
title: "A004: Retrieve Reference Data (FHIR2)"
keywords: endpoint, catalogue
sidebar: overview_sidebar
toc: false
permalink: explore_endpoint_a004_DSTU2.html
summary: false
---

<div style="border: 2px solid #888888; padding: 10px; background: #c3e3c3;">For the new FHIR v3 endpoint, please click <a href="explore_endpoint_a004.html">here</a>.</div>

## Status: ![Deprecated](images/icons/api_deprecated.png)  

<div style="border: 2px solid #888888; padding: 10px; background: #ffcfcf;">
<strong>Defect fix:</strong><br>
Following e-RS <a href='https://digital.nhs.uk/services/e-referral-service/live-service-information-and-alerts/releases#release-9-6-friday-21-august-2020-subject-to-final-testing-'>release 9.6</a> this endpoint will return <em>all specialities</em>, prior to this fix only active specialities were returned, inactive specialties were not returned. Please note that this is a non-breaking change and only affects this endpoint. Find out more about this endpoint and related FHIR models.
</div>
<br>
<div style="border: 2px solid #888888; padding: 10px; background: #fcf2d4;">
This endpoint must be used with all FHIR2 (DSTU2) endpoints: <br>
<br>
- A005 Retrieve Referral Request (Live)<br>
- A007 Retrieve Clinical Information (Live)<br>
- A008 Retrieve Worklist (Live)<br>
</div>

## API

| Method | URL |
| -------------| --- |
| GET | v1/ValueSet/{{valueSetId}} |

- {Base URL} (Dev1) = https://api.dev1.ers.ncrs.nhs.uk/ers-api  
- {{valueSetId}} = Desired Value Set from [eRS-Specialty-ValueSet-1](https://data.developer.nhs.uk/specifications/eRS-draftd/Profile.Valueset/ers-specialty-valueset-1.html)

## Description
This read-only API lets a user access a pre-populated list of reference data. The NHS e-Referral Service uses these lists throughout. For example, a list of specialities. They support data accuracy and effective re-use. It retrieves a specific Value Set (Reference Dataset) by ID.

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
Currently applicable values for the {valueSetId}:

|Value Set ID|Description|
|---|---|
|SPECIALTY|Specialties defined in e-RS|

### Header
Provide ASID of the end-point system and equivalent Session Key generated for the SSO Token-ID.

#### Example
```http
XAPI_ASID:200000000220
Content-Type:application/json+fhir
HTTP_X_SESSION_KEY:pro-xapi-session_5a399946-23c5-4543-8c4f-7eca38732a58
```

## Output
A [Value Set Resource](explore_models.html) profiled specifically for the given valueSetId. This will include the requested coding system with its available codes. The response code `200 (OK)` is returned.

#### Example
```javascript
{
    "id": "SPECIALTY",
    "meta": {
        "profile": [
            "http://fhir.nhs.uk/StructureDefinition/ers-valueset-1"
        ]
    },
    "resourceType": "ValueSet",
    "status": "active",
    "publisher": "HSCIC",
    "date": "2017-07-28",
    "description": "Specialties defined in e-RS",
    "codeSystem": {
        "system": "http://fhir.nhs.uk/ValueSet/ers-specialty-1",
        "concept": [
            {
                "extension": [
                    {
                        "url": "http://fhir.nhs.uk/StructureDefinition/extension-ers-effectivefromdate-1",
                        "valueDateTime": "2004-06-01T00:00:00.000Z"
                    }
                ],
                "code": "2WW",
                "display": "2WW",
                "designation": {
                    "value": "9901"
                }
            },

            {
                "extension": [
                    {
                        "url": "http://fhir.nhs.uk/StructureDefinition/extension-ers-effectivefromdate-1",
                        "valueDateTime": "2004-06-01T00:00:00.000Z"
                    }
                ],
                "code": "UROLOGY",
                "display": "Urology",
                "designation": {
                    "value": "101"
                }
            }
        ]
    }
}
```

<!--## Code Sample
Code snippets taken from the consumer example. See [Code Samples](develop_code_samples.html) for further details.

```javascript
angular.module('ers-consumer-exampleApp')
  .service('referenceDataService', function ($q, $resource, config, session) {

    function getRefData(valueSetId) {
        var deferred = $q.defer();
        var sessionId = session.getId();

        var headersJson = {};
        headersJson[config.asidHeader] = config.asid;
        headersJson[config.sessionIdHeader] = sessionId;

        var refData = $resource(config.baseUrl + '/v1/ValueSet/' + valueSetId,
            null,
            {get: {method: 'GET', headers: headersJson}}
        );
        refData.get(function(data) {
            deferred.resolve(data);
        }, function() {
            deferred.reject();
        });

        return deferred.promise;
    }

    return {
        getRefData: getRefData
    };
  });
```-->

## Notes
Consuming application must have a valid session in order to access this endpoint.
