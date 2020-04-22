---
title: Audit Logs
keywords: Audit, Logs, Logging
sidebar: overview_sidebar
toc: false
permalink: /audit_logs.html
summary: "Summary of audit logging requirements"
---

# Audit logging

Ensure local audit logs are maintained for Subject Access Requests as pert the table below, it is recommended that audit logs are held for a minimum of 3 months to assist with incident triage.  

All mandatory fields must be adhered.

| Field Name | Field Type | Mandatory/Optional | Example | Comments |
| ---------- | ---------- | ------------------ | ------- | -------- |
| Unique Identifier | bigint | M | 1686289 |  |
| Event Type | character  | M | GET/POST/PUT/DELETE |  |
| Audit Type | character  | M | API Establish Session, Professional login attempt, API Retrieve Reference Data, API Retrieve Request List, API Retrieve Request Summary, API Retrieve Clinical Information, API Retrieve Clinical Attachment, API Close Session |  |
| Resource Type | character  | O | Worklist, Referral Request, Appointment Request, Clinical Attachment |  |
| Event Date & Time | timestamp without time zone | M | 2018-04-25 15:57:05.745 | yyyy-MM-dd HH:mm:ss.SSS format. All dates must be stored in UTC |
| UUID  | character  | M | 123456789012 | 12 digit Unique User Identifier of the smartcard |
| OBO UUID | character  | M | 123456789014 | On Behalf Of UUID |
| UBRN | character  | M | 000049614844 | Unique Booking Reference Number |
| NHS Number | character  | M | 9462640300 |  |
| Session ID | character  | M | pro-xapi-session_38dbf5e1-c145-475f-bdbc-f71bbb167e38 |  |
| Org Name | character  | M | Leeds Teaching Hospital | Organisation Name  |
| User Business Function | character  | M | SERVICE_PROVIDER_CLINICIAN | B0247, B0001 |
| ASID | character  | M | 200000000200 | Acrredited System Identifier |
| FQDN | character  | M | api.test.ncrs.nhs.uk | Fully Qualified Domain Name |
| Attachment ID | character  | O | 26928 |  |
| Attchment Type | character  | O | .JPEG, .DOC |  |
| File Name | character  | O | TEXT.TXT, JPEG.JPG |  |
