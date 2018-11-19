---
title: "A001: Create Professional Session"
keywords: endpoint, catalogue
sidebar: overview_sidebar
toc: false
permalink: explore_endpoint_a001.html
summary: false
---

## API

| Request Type | URL |
| -------------| --- |
| POST | [/v1/ProfessionalSession](https://api.{env}.ers.ncrs.nhs.uk/ers-api/v1/ProfessionalSession)

## Description
Creates a Professional Session in the Spine using smartcard roles. This gives a secure login.

## Input

### Header
Provide ASID for the end-point system.

#### Example
```http
XAPI_ASID:200000000220
Accept:application/json
Accept-Encoding:gzip,deflate
Content-Type:application/json
```

### Body
Provide only a token when first creating a session.

#### Example
```javascript
{
 "typeInfo": "uk.nhs.ers.xapi.dto.v1.session.ProfessionalSession",
 "token": " AQIC5wM2LY4Sfcyw62EbAOsRpdfbGYUOyvkfZ4M6U7W52lM=@AAJTSQACMDE=#"
}
```

## Output
The created [Professional Session Resource](explore_models.html) is returned with available user permissions populated.

The response code `201 (Created)` is returned.

#### Example
```javascript
{
    "typeInfo": "uk.nhs.ers.xapi.dto.v1.session.ProfessionalSession",
    "id": "pro-xapi-session_222c42c7-820f-4f9b-92fb-3add4b1db9f7",
    "token": "AQIC5wM2LY4Sfcyw62EbAOsRpdfbGYUOyvkfZ4M6U7W52lM=@AAJTSQACMDE=#",
    "user": {
        "identifier": "555020964101",
        "firstName": "SA Assurance",
        "lastName": "GP-Card",
        "middleName": null,
        "permissions": [
            {
                "businessFunction": "REFERRING_CLINICIAN",
                "orgIdentifier": "R01",
                "orgName": "NHST_X3"
            },
            {
                "businessFunction": "REFERRING_CLINICIAN_ADMIN",
                "orgIdentifier": "R01",
                "orgName": "NHST_X3"
            },
            {
                "businessFunction": "SERVICE_DEFINER",
                "orgIdentifier": "R01",
                "orgName": "NHST_X3"
            },
            {
                "businessFunction": "SERVICE_PROVIDER_CLINICIAN",
                "orgIdentifier": "R01",
                "orgName": "NHST_X3"
            },
            {
                "businessFunction": "SERVICE_PROVIDER_CLINICIAN_ADMIN",
                "orgIdentifier": "R01",
                "orgName": "NHST_X3"
            }
        ]
    },
    "permission": null
}
```

<!-- ## Code Sample
Code snippets taken from the consumer example. See [Code Samples](develop_code_samples.html) for further details.

```javascript
function createSession(tokenCode, entryUrl) {
     scope.entryUrl = entryUrl;
     var json = {
         token: tokenCode
     };
     var deferred = $q.defer();
 
     var headersJson = {};
     headersJson[config.asidHeader] = config.asid;
 
     var rest = $resource(
             config.baseUrl + '/v1/ProfessionalSession',
             null,
             {'save': {method: 'POST', headers: headersJson}}
     );
     rest.save(json, function (data) {
         scope.sessionData = data;
         scope.currentSessionId = data.id;
         deferred.resolve(data);
     });
     return deferred.promise;
 }
```-->

## Notes
Once the session has been created a list of applicable permissions for the user will be returned. The session will not be usable until a permission/role has been selected using the Select Role endpoint.

The `ProfessionalSession.id` returned should be included as a header `(HTTP_X_SESSION_KEY)` for all subsequent requests.

### Response Messages

| HTTP Status Code | Reason | Response Model | Headers |
| ---------------- | ------ | -------------- | ------- |
| 201 | Created |
| 403 | Forbidden |
| 422 | Unprocessable Entity – Provided data could not be processed due to a validation error |
