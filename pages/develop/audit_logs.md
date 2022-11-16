---
title: Audit Logs (Archived)
keywords: Audit, Logs, Logging
sidebar: overview_sidebar
toc: false
permalink: /audit_logs.html
summary: "Summary of audit logging requirements (Archived)"
---

# Audit logging

Ensure local audit logs are maintained for Subject Access Requests as per the table below, it is recommended that audit logs are held for a minimum of 3 months to assist with incident triage.  

All mandatory fields must be adhered.

| Field Name | Field Type | Mandatory | Example                                    | Comments |
| ---------- | ---------- | :-----------------: | ------- | -------- |
| Unique Identifier | bigint | Y | 1686289 |  |
| Event Type | character  | Y | GET/POST/PUT/DELETE |  |
| Audit Type | character  | Y | API Establish Session, <br>API Professional login attempt, <br>API Retrieve Reference Data, <br>API Retrieve Request List, <br>API Retrieve Request Summary, <br>API Retrieve Clinical Information, <br>API Retrieve Clinical Attachment, <br>API Close Session |  |
| Resource Type | character  | N | Worklist, <br>Referral Request, <br>Appointment Request, <br>Clinical Attachment |  |
| Event Date & Time | timestamp without time zone | Y | 2018-04-25 15:57:05.745 | Format: <br>yyyy-MM-dd HH:mm:ss.SSS <br>All dates must be stored in UTC |
| UUID  | character  | Y | 123456789012 | 12 digit Unique User Identifier of the smartcard |
| OBO UUID | character  | Y | 123456789014 | On Behalf Of UUID |
| UBRN | character  | Y | 000049614844 | Unique Booking Reference Number |
| NHS Number | character  | Y | 9462640300 |  |
| Session ID | character  | Y | pro-xapi-session_38dbf5e1-c145-475f-bdbc-f71bbb167e38 |  |
| Org Name | character  | Y | Leeds Teaching Hospital | Organisation Name  |
| User Business Function | character  | Y | SERVICE_PROVIDER_CLINICIAN | B0247, B0001 |
| ASID | character  | Y | 200000000200 | Acrredited System Identifier |
| FQDN | character  | Y | api.test.ncrs.nhs.uk | Fully Qualified Domain Name |
| Attachment ID | character  | N | 26928 |  |
| Attachment Type | character  | N | .JPEG, .DOC |  |
| File Name | character  | N | TEXT.TXT, JPEG.JPG |  |
