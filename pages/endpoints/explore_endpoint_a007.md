---
title: "A007: Retrieve Clinical Information"
keywords: endpoint, catalogue
sidebar: overview_sidebar
toc: false
permalink: explore_endpoint_a007.html
summary: false
---

## API

| Request Type | URL |
| -------------| --- |
| GET [/v1/Binary/$ers.generateCRI?UBRN={UBRN}](https://api.{env}.ers.ncrs.nhs.uk/ers-api/v1/Binary/$ers.generateCRI?UBRN={UBRN})

## Description
This API lets users create a real-time Portable Document Format (PDF) of the referral. This is suitable for integration into a 3rd party system. You can find the Clinical Information for a referral request using a UBRN.

## Input

### Header
Provide ASID of the end-point system and equivalent Session Key generated for the SSO Token-ID.

#### Example
```http
XAPI_ASID:200000000220
HTTP_X_SESSION_KEY:{sessionKey}
Accept:*/*
```

## Output
If successful a PDF of clinical referral information for referral is returned. The response code `200 (OK)` is returned.

<!--## Code Sample
Code snippets taken from the consumer example. See [Code Samples](develop_code_samples.html) for further details.-->

## Notes
Get the Clinical Referral Information for a Referral Request identified by the given UBRN.

### Parameters

| Parameter | Value | Description | Parameter Type | Data Type |
| --------- | ----- | ----------- | -------------- | --------- |
| UBRN |    | UBRN | Query | String |

### Response Messages

| HTTP Status Code | Reason |
| ---------------- | ------ |
| 200 | OK |
| 403 | Forbidden |
| 404 | Not Found |
