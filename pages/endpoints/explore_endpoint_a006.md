---
title: "A006: Retrieve Attachment"
keywords: endpoint, catalogue
sidebar: overview_sidebar
toc: false
permalink: explore_endpoint_a006.html
summary: false
---

## API

| Request Type | URL |
| -------------| --- |
| GET | [/v1/Binary/{AttachmentLogicalID}](https://api.{env}.ers.ncrs.nhs.uk/ers-api/v1/Binary/{AttachmentLogicalID})

## Description
This API lets users retrieve and download linked files for a referral, also known as attachments.

Note: The AttachmentLogicalID is not specifically required as the exact path required to retrieve the attachment is returned explicitly by [A005 Retrieve Referral Request](explore_endpoint_a005.html). The path to the attachment can be found in the “url” field of the DocumentReference.content.attachment in the contained section of the ReferralRequest resource.

## Input

### Header
Provide ASID of the end-point system and equivalent Session Key generated for the SSO Token-ID.

#### Example
```http
XAPI_ASID:200000000220
HTTP_X_SESSION_KEY:pro-xapi-session_5a399946-23c5-4543-8c4f-7eca38732a58
Accept:*/*
```

## Output
If successful file content linked to the referral is returned. The response code `200 (OK)` is returned.

<!--## Code Sample
Code snippets taken from the consumer example. See [Code Samples](develop_code_samples.html) for further details.-->

<!--## Notes
The path to the attachment can be found in the “url” field of the DocumentReference.content.attachment in the contained section of the ReferralRequest resource.-->

### Parameters

| Parameter | Value | Description | Parameter Type | Data Type |
| --------- | ----- | ----------- | -------------- | --------- |
| AttachmentLogicalID |   | The logical ID for the Binary resource (i.e. for the attachment) in the format att-x-y where x and y are Integers | Path | String |

### Response Messages

| HTTP Status Code | Reason |
| ---------------- | ------ |
| 200 | OK |
| 403 | Forbidden |
| 404 | Not Found |
