---
title: "A025: Retrieve Advice and Guidance Conversation (Deprecated)"
keywords:  
sidebar: overview_sidebar
toc: false
permalink: explore_endpoint_a025.html
summary: false
---

#### Status: ![Deprecated](images/icons/api_deprecated.png)

This endpoint has been deprecated, meaning you should not use it for new integrations.

Instead, please use our newer e-RS FHIR API solution which is documented here:
[https://digital.nhs.uk/developer/api-catalogue/e-referral-service-fhir](https://digital.nhs.uk/developer/api-catalogue/e-referral-service-fhir)

## Description
This endpoint allows an authenticated user to obtain the Advice and Guidance conversation details amounting to the communication between a Referrer and the Service Provider concerning a given Advice and Guidance Request. This is referenced as a single or set of Communication Resources in FHIR, where each Communication Resource is a single part of a conversation between a requester (the Referrer) or responder (the Service).  

This information must be used in conjunction with a request to A024: Get Advice and Guidance Summary to retrieve summary information about the Advice and Guidance Request.  

These endpoints available for users with the role of Referring Clinician (RC), Referring Clinician Admin (RCA), Service Provider Clinician (SPC) or Service Provider Clinician Admin (SPCA).


## Request Operation: URL

| Method       | URL | Authentication |
| -------------| --- | ---------------- |
| GET | {Base URL}/STU3/v1/Communication?based-on=CommunicationRequest/{ubrn}/_history/{version}&_include=Communication:requester-practitionerrole:PractitionerRole&_include=Communication:sender-practitionerrole:PractionerRole&_include=Communication:content-reference:DocumentReference | Session Token [(Details)](develop_business_flow_bf001.html) |

- The {ubrn} represents the unique booking reference number of the Advice and Guidance Request for which the caller is obtaining the “Advice and Guidance Conversation”
- {version} is the version of the A&G Request to be retrieved (only the most current version will be retrievable)
- {Base URL} (Dev1) = https://api.dev1.ers.ncrs.nhs.uk/ers-api  


## Operation Definition
- [eRS-Communication-1](https://fhir.nhs.uk/STU3/StructureDefinition/eRS-Communication-1)  

## Prerequisite Conditions
- The given UBRN must exist in e-RS and be an Advice and Guidance Request
- A call may have been made A023: Retrieve Advice and Guidance Requests Worklist to obtain the UBRN of the Advice and Guidance Request to be requested.


## Compliance Requirements
### Deceased Checks
-	Deceased Checks
Viewing an Advice and Guidance is normally subject to a “deceased patient” check.  This cannot be provided by API and instead the supplier should be expected to check for a Date of Death via PDS before making the call to the API
#### Example scenario
1) Supplier checks with PDS for the presence of a Date of Death  
2) If there is a DoD present, the Supplier should pass this information to the user so they can decide whether to proceed with retrieving the Advice and Guidance Request anyway, or not  
3) If they choose to retrieve the A&G Request, the presence of a DoD will not prevent the API returning the response   

### Communication versions
To ensure the supplier is always referencing the latest version of the CommunicationRequest and the most up to date Communication, the supplier must use the basedOn functionality, if they don't the Supplier could miss a change in the CommunicationRequest, such as priority change, because they are referencing an out-of-date CommunicationRequest.

### Advice and Guidance Conversation

- The 'Communication' Resource described here is only for the A&G Request Conversation, i.e. the 'request' and 'response' messages
  - Via the API one can always "view" an Advice and Guidance Request without invoking a lock - even if it is "locked" by another user. As "viewing" via the API doesn't "lock" the Advice and Guidance (but "updates" via the API or eRS might do), the information retrieved is only valid at the point that it is viewed
- Communication results (the messages) will be returned in the default order, i.e. eRS will not sort them for the Supplier and if they are required in a specific order, the Supplier must sort them
  - The results of obtaining the Communication Resource are unsorted
  - The order in which the Communication Resource are returned are not guaranteed and may change
  - It is therefore imperative that a Supplier determines the order in which the Communications should be viewed by sorting themselves by communication.sent (the order in which they were sent)
  - Do NOT sort by ID
  - There is "Sent" field containing a Date/Time which could be used to “sort”
- The URL "_include" details are default behaviour. Meaning if a Supplier does not include them, the e-RS response will include them anyway, this will be evident via the 'self' link in the response body
  - To insure for future behaviour changes, we need to ensure Suppliers are aware they must request the "_includes" they require, otherwise that information may not be available/returned as the direct endpoints for "PractitionerRole" or "DocumentReference" do not exist
  - The following includes are supported:
    - &_include=Communication:requester-practitionerrole:PractitionerRole
    - &_include=Communication:sender-practitionerrole:PractionerRole
    - &_include=Communication:content-reference:DocumentReference
    - The Communication.Note field is a plain text field that additionally supports hyperlinks in the following format: ```<a href="%web_address%" target="_blank">%link_text%</a>```
- It is the Suppliers responsibility to sanitize responses received from eRS. eRS allows for ```<a>``` tag HTML elements so that hyperlinks can be rendered. Suppliers MUST sanitize as they deem necessary, noting that eRS suggests all other HTML stored within eRS should be considered a text-only string.


# INPUT

## Header

| Field Name | Value |
| ---------- | ----- |
| XAPI_ASID | The "Accredited System ID" issued to the third party |
| HTTP_X_SESSION_KEY | The session key generated by the [Authentication and Authorisation APIs](/develop_business_flow_bf001.html)  |

### Example Request Header
```http
XAPI_ASID:999000000045
HTTP_X_SESSION_KEY:pro-api-session:e96357b1-298d-4159-ac58-a8953c3262c6"
```

# OUTPUT
## Response: Success

The output includes
-	200 HTTP response
-	A “Bundle” of Communcation’s are returned

A Bundle contains:
-	"resourceType" of 'Bundle'
-	"Bundle.Type" of 'searchset'
-	"Bundle.Total" indicating the number of Communication 'matches', i.e. the number of Communcation Resources (indicating the number of back, and forth).
-	"Bundle.Link.Self" this ensures the bundle associates and returns the Sender and Requester details and any contentReferences for file attachments.
-	"Bundle.Entry.FullUrl" FHIR requirement specifying the Base URL
-	"Bundle.Entry.Search.mode" Field for FHIR compliance

Multiple messages could have been sent, as indicated by the 'Bundle.Total', in which case the below structure will repeat for each message sent. **This includes multiple messages sent in the same direction without a reply**
-	"resourceType" representing the FHIR resource that the conversation is formatted in, i.e. "Communication"
-	"Communication.Id" integer representing a unique id for the specific request or response
-	"BasedOn.Reference/_history/{{version}}" field used to identify the Advice and Guidance Summary this 'Communication' belongs to
-	"Status" This is a mandatory FHIR field and for e-RS purposes this will always be "completed"
-	"Recipient" field representing the intended received of the message. This will either be:
  -	"Recipient.Identifier" when the message is being sent to the Referring Organisation OR
  -	"Recipient.Extension" to /HealthcareService-Reference-1, when the message is being sent to a Service Provider
-	"Sent" field containing a Date/Time the Communication was successfully stored by eRS. This can be used to order the communications
-	“Note" field which contains the free text message entered by the Professional User, i.e. the Request or Response message.
-	Sender.Extension (PractionerRole-Reference-1) that contains:
  -	PractitionerRole.Practitioner representing the user at the keyboard at the time of creation, e.g. 222222222222
  -	PractitionerRole.Organization representing the organisation of the user at the keyboard at the time of creation, e.g. P30X
  -	PractitionerRole.Coding representing the user role of the user role at the keyboard at the time of creation, e.g. SERVICE_PROVIDER_CLINICIAN_ADMIN
    These represent the details of the user at the keyboard and are of either:
    -	Service Provider Communication
      -	The Service Provider Admin that created the Communication “on behalf of” an Service Provider Clinician OR the Service Provider Clinician who created the Communication and is responsible. OR
    - Referrer Communication
      -	The Referrer Clinician Admin that created the Communication OR
      -	The RC that created the Communication and is responsible.
-	Communication.Extension (Communication-Requester-1) Reference(PractitionerRole) that contains:
  -	PractitionerRole.Practitioner representing the User 'responsible' at the time of creation, e.g. 111111111111
  -	PractitionerRole.Organization representing the organisation of the 'responsible' Professional User at the time of creation, e.g. RGD03
  -	PractitionerRole.Coding representing the user role of the 'responsible' Professional User at the time of creation, e.g. SERVICE_PROVIDER_CLINICIAN
-	"Payload" field that contains the reference for any eRS-DocumentReference-1. i.e. Attachments associated with the Communcatio (0..*)
  -	This document reference will only be present if a file was attached
-	"Category.CodeSystem" displays a value (via CommunicationSentBy-1) representing the Direction Type of the communication, i.e. whether it's "Requester" or "Responder" Communcation.
  -	Note this field can also indicate a “message” from a Referrer Clinical System pointing to when Clinical Information was added/updated. In which case, the value here will be REFERRER_CLINICAL_INFORMATION_UPDATED.
    -	In this case the Commucation.note will always read “NOTE: Clinical Information has been added / amended”.
    -	This is effectively a date stamp of when a Referrer Clinical System added OR amended an attachment on the Advice and Guidance Request and should prompt a user to retrieve that attachment.
    -	Within the CommunicationRequest resource there is an entity ("payload.eRS-DocumentReference-1" field nested under "payload") which contains details of the current attachment added via a Referrer Clinical System
    -	There is only ever one set of seamlessly added RCI on an A&G Request, any 'updated' set replaces the existing set , meaning there will only be one RCI attachment set)
    -	This attachment can be obtained from an existing endpoint (A006: Retrieve Attachment) using the file's unique id from CommuncationRequest.


### Example Response Body

- [A025_Response.json](downloads/json/A025_Response.json)  

## Response: Failure
If an error occurs, the relating HTTP status code will be returned in the header.  

Where status code 422 (Unprocessable Entity) is returned then an eRS-OperationOutcome-1 will be included in the body, as detailed below:

| OutcomeKey | Suggested Diagnostic |
| ---------- | -------------------- |
| NO_SUCH_REQUEST | The UBRN provided in the URL doesn't have a suitable match |
| NO_RELATIONSHIP | User associated with the API session does not have a Legitimate Relationship with the Advice and Guidance Request |
| PATIENT_ERROR | The Patient cannot be viewed via e-Referrals |
| INVALID_REQUEST_TYPE  | The UBRN supplied does not correspond to an Advice and Guidance Request |
| HISTORY_NOT_SUPPORTED | The  version number supplied is not the latest version |



**Note:** the above errors are in addition to “generic” errors.
