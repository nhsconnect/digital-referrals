---
title: Error Messages
keywords: api, errors
sidebar: overview_sidebar
toc: false
permalink: /explore_error_messages.html
summary: "A summary of error message handling for the e-Referral APIs"
---

| Error&nbsp;code&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; | Description | Guidance |
| ---------- | ----------- | -------- |
| 400 (Bad&nbsp;Request) | The data received was malformed (e.g. missing/incorrect fields)	| Report the error to local service desk |
| 403 (Forbidden)| The logged in user is not authorised to perform the requested action (e.g. due to their business function not being authorised, organisation not having the appropriate organisation role, legitimate relationship, referrer rights etc) | Report the error to local service desk |
| 404 (Resource&nbsp;not&nbsp;found) | The requested resource (e.g. A UBRN, NHSNumber, Attachment, Lock etc does not exist and cannot be returned) | Check the search term entered was correct |
| 405 (Method&nbsp;not&nbsp;allowed) | An attempt was made to call an e-RS internal API using an HTTP method that the API does not support (e.g. sending a POST request to create data to a read-only endpoint that only supports GET) | Report the error to local service desk |
| 409 (Conflict) | An attempt was made to update an out-of-date version of some data (i.e. optimistic locking error). Often caused by another user simultaneously editing the same record | Reload the data, re-enter your changes, and try again |
| 410 (Resource&nbsp;gone) | An attempt was made to retrieve/update data that no longer exists (e.g. it did exist but has since been deleted) | Check the search term entered was correct |
| 412 (Precondition&nbsp;failed) | A business rule assertion was violated (e.g. a search that is only expected to return a single entry such as find patient by NHS Number, returned multiple results) | Report the error to local service desk |
| 416 (Page&nbsp;not&nbsp;in&nbsp;range) | A request was made to retrieve a specific page of results that was out of the range of valid pages (e.g. when paging through appointment slots) | Reload the data and try again, if the issue persists report to local service desk |
| 422 (Unprocessable&nbsp;entity) | The data received failed validation and could not be processed (e.g. data to update/create or a search query) | Report the error to local service desk |
| 500 (Internal&nbsp;server&nbsp;error) | An unexpected internal server error occurred | Reload (relogin if necessary) and try again, if issue persists report to local service desk |
| 502 (Bad&nbsp;gateway) | An error occurred communicating with a gateway service (e.g. PDS, SDS, PAS etc) | Reload (relogin if necessary) and try again, if issue persists report to local service desk |
| 504 (Gateway&nbsp;timeout) | The gateway did not receive a timely response from the upstream server (e.g. PDS, SDS, PAS etc) | Reload (relogin if necessary) and try again, if issue persists report to local service desk |
