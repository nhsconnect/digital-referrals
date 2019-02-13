---
title: "A012: Upload Attachments"
keywords: endpoint, catalogue
sidebar: overview_sidebar
toc: false
permalink: explore_endpoint_a012.html
summary: false
---

## API

| Request Type | URL |
| -------------| --- |
| POST |  [/v1/ReferralRequest/{UBRN}/$ers.uploadReferralLetter](https://api.{env}.ers.ncrs.nhs.uk/ers-api/v1/ReferralRequest/{{UBRN}}/$ers.uploadReferralLetter)

## Description
This API lets the professional user upload attachments for the referral request that has already been created.

## Input

### Header
Provide ASID for the end-point system, Session Key and VersionId.

#### Example
```http
XAPI_ASID:200000000220
HTTP_X_SESSION_KEY:pro-xapi-session_5a399946-23c5-4543-8c4f-7eca38732a58
Accept:application/json+fhir
If-Match: W/"n"
```

Note: `n` is the VersionId of an already created Referral Request. Each time a referral request is updated (e.g. Referral letter attached), the VersionId is incremented.

### Body
Use option 1 and/or 2 to retain, remove or insert attachments.

#### Example 1
Insert attachment Example: Below content can be used as body to upload attachments:
```javascript
{
  "parameter": [
    {
      "name": "attachmentsToRetain",
      "resource": {
        "entry": []
      }
    },
    {
      "name": "attachmentsToRemove",
      "resource": {
        "entry": []
      }
    },
    {
      "name": "attachmentsToInsert",
      "resource": {
        "entry": [
          {
            "extension": [],
            "data": "aGVsbG8\u003d",
            "contentType": "text/plain",
            "title": "test.txt"
          }
        ]
      }
    }
  ]
}
```

Where attachmentsToRetain is the attachment ID(s) you wish to retain (so, in this example we wouldn’t retain anything),
attachmentsToRemove is the attachment ID(s) you wish to remove (so, in this example we wouldn’t remove anything),
and attachmentsToInsert is the attachment you wish to insert (so, in this example we would insert test.txt)

#### Example 2
Retain, Remove and Insert attachments Example: Below content can be used as body to upload attachments:

```javascript
{
  "parameter": [
    {
      "name": "attachmentsToRetain",
      "resource": {
        "entry": [
          {
            "value": "70009",
            "extension": []
          },
          {
            "value": "70011",
            "extension": []
          }
        ]
      }
    },
    {
      "name": "attachmentsToRemove",
      "resource": {
        "entry": [
          {
            "value": "70010",
            "extension": []
          }
        ]
      }
    },
    {
      "name": "attachmentsToInsert",
      "resource": {
        "entry": [
          {
            "extension": [
              {
                "valueString": "example txt"
              }
            ],
            "data": "aGVsbG8\u003d",
            "contentType": "text/plain",
            "title": "test1.txt"
          }
        ]
      }
    }
  ]
}
```

Where attachmentsToRetain is the attachment ID(s) you wish to retain (so, in this example we would retain 70009 and 70011),
attachmentsToRemove is the attachment ID(s) you wish to remove (so, in this example we would remove 70010),
and attachmentsToInsert is the attachment you wish to insert (so in this example we would insert test1.txt)

## Output
If successful the attachments are uploaded to the referral request. The response code `200 (OK)` is returned. This response has no body.

<!--## Code Sample
Refer to the `API Client Demonstrator tool` source code.-->
