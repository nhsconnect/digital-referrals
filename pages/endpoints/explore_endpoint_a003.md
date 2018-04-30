---
title: "A003: Delete Professional Session"
keywords: endpoint, catalogue
sidebar: overview_sidebar
toc: false
permalink: explore_endpoint_a003.html
summary: false
---

## API

| Request Type | URL |
| -------------| --- |
| DELETE | [/v1/ProfessionalSession/{sessionKey}](https://api.{env}.ers.ncrs.nhs.uk/ers-api/v1/ProfessionalSession/{sessionKey})

## Description
Logs out of the Professional Session and closes the dialogue.

## Input
The Session ID / Key of the session to be deleted should be provided as the sessionKey path parameter. The Session ID is that returned in `ProfessionalSession.id`.

### Header
Provide ASID of the end-point system and equivalent Session Key generated for the SSO Token-ID.

#### Example
```http
XAPI_ASID:200000000220
HTTP_X_SESSION_KEY:{sessionKey}
```

## Output
If successful the response code 204 (No Content) is returned. This response has no body.

<!--## Code Sample
Code snippets taken from the consumer example. See [Code Samples](develop_code_samples.html) for further details.

```javascript
function deleteSession() {
    var deferred = $q.defer();

    var headersJson = {};
    headersJson[config.asidHeader] = config.asid;
    headersJson[config.sessionIdHeader] = scope.sessionData.id;

    var rest = $resource(
            config.baseUrl + '/v1/ProfessionalSession/' + scope.currentSessionId,
            null,
            {'delete': {method: 'DELETE', headers: headersJson}}
    );
    rest.delete(function() {
        deferred.resolve(true);
        scope.currentSessionId = null;
    }, function() {
        deferred.reject();        
    });

    return deferred.promise;
}
```-->

## Notes
Consuming application must have a valid session in order to access this endpoint.

Used to delete a Professional Session after it has been created.

Once deleted the associate Session ID will become invalid.

Session is initially created using the Create Session / Select Role endpoints.
