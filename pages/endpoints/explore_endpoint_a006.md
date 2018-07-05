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
| GET | [/v1/Binary/att-{referralRequestAttachmentId}](https://api.{env}.ers.ncrs.nhs.uk/ers-api/v1/Binary/att-{referralRequestAttachmentId})

## Description
This API lets users retrieve and download linked files for a referral. Identify the file using both the request and attachment identifier.

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

## Notes
Get the Attachment identified by the given Referral Request Id and Attachment Id.

### Parameters

| Parameter | Value | Description | Parameter Type | Data Type |
| --------- | ----- | ----------- | -------------- | --------- |
| referralRequestAttachmentId |   | Referral Request Attachment Id | Path | String |

### Response Messages

| HTTP Status Code | Reason |
| ---------------- | ------ |
| 200 | OK |
| 403 | Forbidden |
| 404 | Not Found |
