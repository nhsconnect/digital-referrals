---
title: "A002: Professional Session Select Role"
keywords: endpoint, catalogue
sidebar: overview_sidebar
toc: false
permalink: explore_endpoint_a002.html
summary: false
---

## API

| Method | URL |
| -------------| --- |
| PUT | /ers-api/v1/ProfessionalSession/{sessionKey}

## Description
Updates a Professional Session with the appropriate NHS organisation and role. This ensures the correct access rights for the user.

## Input
The base input for this endpoint should be the output from the Create Session endpoint. The consumer should then additionally populate the permission field with the permission they wish to select from those available to the user (`ProfessionalSession.user.permissions`).

### Header
Provide ASID of the end-point system and equivalent Session Key generated for the SSO Token-ID.

#### Example
```http
XAPI_ASID:200000000220
Content-Type:application/json
HTTP_X_SESSION_KEY: pro-xapi-session_222c42c7-820f-4f9b-92fb-3add4b1db9f7
```

### Body
Provide token and permission fields when selecting a role.

#### Example
```javascript
{
  "typeInfo": "uk.nhs.ers.xapi.dto.v1.session.ProfessionalSession",
  "token": "AQIC5wM2LY4Sfcyw62EbAOsRpdfbGYUOyvkfZ4M6U7W52lM=@AAJTSQACMDE=#"
"permission":{"businessFunction":"SERVICE_PROVIDER_CLINICIAN", "orgIdentifier":"R01"}
}
```

## Output
The created [Professional Session Resource](explore_models.html) is returned with the selected permission applied.

The response code `200 (OK)` is returned.

#### Example
```javascript
{
    "typeInfo": "uk.nhs.ers.xapi.dto.v1.session.ProfessionalSession",
    "id": "pro-xapi-session_94414701-70d0-4570-a674-f6f2125ab571",
    "token": "AQIC5wM2LY4Sfcy/V7hKhbk2t0fqyvCmHCBhnjZq0TjqBYw=@AAJTSQACMDE=#",
    "user": {
        "identifier": "555020964101",
        "firstName": "SA Assurance",
        "lastName": "GP-Card",
        "middleName": null,
        "permissions": [
            {
                "businessFunction": "REFERRING_CLINICIAN",
                "orgIdentifier": "R01",
                "orgName": " NHST_X3"
            },
            {
                "businessFunction": "REFERRING_CLINICIAN_ADMIN",
                "orgIdentifier": "R01",
                "orgName": " NHST_X3"
            },
            {
                "businessFunction": "SERVICE_DEFINER",
                "orgIdentifier": "R01",
                "orgName": " NHST_X3"
            },
            {
                "businessFunction": "SERVICE_PROVIDER_CLINICIAN",
                "orgIdentifier": "R01",
                "orgName": " NHST_X3"
            },
            {
                "businessFunction": "SERVICE_PROVIDER_CLINICIAN_ADMIN",
                "orgIdentifier": "R01",
                "orgName": " NHST_X3"
            }
        ]
    },
    "permission": {
        "businessFunction": "SERVICE_PROVIDER_CLINICIAN",
        "orgIdentifier": "R01",
        "orgName": " NHST_X3"
    }
}
```

<!--## Code Sample
Code snippets taken from the consumer example. See [Code Samples](develop_code_samples.html) for further details.

```javascript
function selectRole(permission) {
     var deferred = $q.defer();
     scope.selectedPermission = permission;

     var headersJson = {};
     headersJson[config.asidHeader] = config.asid;
     headersJson[config.sessionIdHeader] = scope.sessionData.id;

     var rest = $resource(config.baseUrl + '/v1/ProfessionalSession/' + scope.currentSessionId,
             null,
             {
                 'save': {method: 'PUT', headers: headersJson}
             });
     var json = {
         id: scope.sessionData.id,
         permission: permission
     };
     rest.save(json, function (data) {
         deferred.resolve(data);
     });

     return deferred.promise;
 }
```-->

## Notes
The Create Session endpoint must be called in order to create the session. This endpoint can then be used to select one of the applicable roles/permissions returned.

The ProfessionalSession.id returned from the Create Session endpoint should be included as a header (HTTP_X_SESSION_KEY) for this and all subsequent requests.
