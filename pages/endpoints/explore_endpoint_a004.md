---
title: "A004: Retrieve Reference Data"
keywords: endpoint, catalogue
sidebar: overview_sidebar
toc: false
permalink: explore_endpoint_a004.html
summary: false
---

## API

| Request Type | URL |
| -------------| --- |
| GET | [/v1/ValueSet/{valueSetId}](https://api.{env}.ers.ncrs.nhs.uk/ers-api/v1/ValueSet/{valueSetId})

## Description
This read-only API lets a user access a pre-populated list of reference data. The NHS e-Referral Service uses these lists throughout. For example, a list of specialities. They support data accuracy and effective re-use. It retrieves a specific Value Set (Reference Dataset) by ID.

## Related FHIR model

* [eRS-Specialty-ValueSet-1](https://data.developer.nhs.uk/specifications/eRS-draftd/Profile.Valueset/ers-specialty-valueset-1.html)

## Input
Applicable values for the {valueSetId}:

|Value Set ID|Description|
|---|---|
|REQUEST_PRIORITY|Request Priorities defined in e-RS.|
|SPECIALTY|Specialties defined in e-RS. Also returns applicable Clinic Types as sub-concepts (categorized by Specialty).|
|CLINIC_TYPE|Clinic Types defined in e-RS.|
|REQUEST_TYPE|Request Types defined in e-RS.|
|COMMISSIONING_TYPE|Commissioning Types defined in e-RS.|

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
