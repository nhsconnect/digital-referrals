---
title: "A027: Convert Advice Request to Referral"
keywords:  
sidebar: overview_sidebar
toc: false
permalink: explore_endpoint_a027.html
summary: false
---

#### Status: ![Live](images/icons/api_live.png)

## Description
This functionality allows a Service Provider to reference an existing Advice and Guidance Request, and if validation passes, allows that Service Provider to create a Referral from that Advice and Guidance Request. As part of the Referral creation, notes, and optionally attachments, for other staff (e.g. Service Provider Clinician Admin staff) are recorded so that the person who picks up the Referral next has some context. The created referral is the responsibility of the Service which created the Referral, until they decide what to do with it (e.g. Book / Defer / Send to another service, cancel etc).  

The Advice and Guidance Request is “closed” and sent back to the Referrer as a result of this action.

## Request Operation: URL

| Method | URL | Authentication |
| ------ | --- | -------------- |
| POST | {Base URL}/STU3/v1/ReferralRequest/$ers.createFromCommunicationRequestActionLater | Session Token [(Details)](develop_business_flow_bf001.html) |

- {Base URL} (Dev1) = https://api.dev1.ers.ncrs.nhs.uk/ers-api

## Operation Definition
[eRS-SendCommunicationToRequester-Operation-1](https://fhir.nhs.uk/STU3/OperationDefinition/eRS-SendCommunicationToRequester-Operation-1)

#### Input
[eRS-SendCommunicationToRequester-Request-Parameters-1](https://fhir.nhs.uk/STU3/StructureDefinition/eRS-SendCommunicationToRequester-Request-Parameters-1)

#### Output
[eRS-SendCommunicationToRequester-Response-Parameters-1](https://fhir.nhs.uk/STU3/StructureDefinition/eRS-SendCommunicationToRequester-Response-Parameters-1)


## Prerequisite Conditions
- An Advice and Guidance request must exist and not be “closed”, I.e. a conversation between the Provider and Referrer must be on-going.
- The caller should have reviewed the most recent Advice and Guidance Request. This can be accessed via two endpoints
  - Advice and Guidance Request Summary
  - Advice and Guidance Conversation

## Compliance Requirements
-	This feature checks the version of the CommunicationRequest last viewed (via a parameter denoting the CommunicationRequest version: createFrom=CommunicationRequest/{ubrn}/_history/{{version}}). However, it does NOT check that the caller has seen the most recent Communication(s). Therefore it follows that:  
  - Supplier systems MUST get the most recent Communication(s) to ensure that they are converting with the most recent Clinical Information to hand.
  -	Supplier systems MUST get the most recent CommunicationRequest to ensure they are converting with the most recent version of the CommunicationRequest.
-	Currently ALL Advice and Guidance Request attachments are included under SupportingInfo under the ReferralRequest meaning, if you can view the ReferralRequest, you can view the Advice and Guidance Request Clinical Attachments (except any "structured information"). Since this feature adds reference to the Advice and Guidance Request in the Pathway, arguably, there is no need to include these attachments on the ReferralRequest anymore. There is no current business need to make a distinction, and it might be a breaking change to do so. Making this a future Business need might make LR easier to manage. Currently you can only “fetch” the attachments if you have LR with the attachment anyways, so we are somewhat protected.

# INPUT
[eRS-CreateFromCommunicationrRequestActionLater-Request-Parameters-1 ](https://fhir.nhs.uk/STU3/StructureDefinition/eRS-CreateFromCommunicationrRequestActionLater-Request-Parameters-1)  

## Request Operation: Parameters

| Name | Cardinality | Type | Description |
| ---- | ----------- | ---- | ----------- |
| createFrom | 1..1 | Reference | Identifies the Advice and Guidance Request a Professional wants to update and the version last seen by that Professional. Only the most recent version can be converted.<br><br>Must of value and format ```createFrom=CommunicationRequest/{ubrn}/_history/{{version}}``` |
| guidance | 1..1 | String | Response back to the Referrer on the Advice and Guidance Request (Max 2000 char) |
| guidanceAttachmentFile | 0..* | Resource | Document(s) sent back to the Referrer on the Advice and Guidance Request<br>Must be eRS-DocumentReference-1 |
| reviewComments | 1..1 | string | Comment the Professional (admin) staff will see on the created Referral (Max 2000 char) |
| reviewAttachmentFile | 0..* | Resource | Document(s) to associate with the created Referral<br>Must be eRS-DocumentReference-1 |
| newReferralPriority | 1..1 | Coding | Priority to attribute to the created Referral<br>Must be from ValueSet [eRS-Priority-1](https://fhir.nhs.uk/STU3/ValueSet/eRS-Priority-1) |

### Example Request Header
```http
XAPI_ASID:999000000045
HTTP_X_SESSION_KEY:pro-api-session:e96357b1-298d-4159-ac58-a8953c3262c6"
Content-Type:application/fhir+json
```

### Example Request Body
Note: These examples may contain environment specific URLs and test data, these should be replaced with appropriate values for your implementation.
- [A027_Request.json](downloads/json/A027_Request.json)

# OUTPUT
## Response: Success
If successful we return as per [A005: Retrieve Referral Request](https://developer.nhs.uk/apis/e-Referrals/explore_endpoint_a005.html) but it’s worth translating some of what is returned into business language.
1. Immediately after creating a Referral from an Advice and Guidance Request  
  -	The FHIR “status” element will be “proposed”
  -	The FHIR “reason.coding.system.value” will be PROVIDER_CONVERTED_ADVICE_AND_GUIDANCE_ADMIN_TO_REFER. This is so that the person picking up the Referral understands what happened to it i.e. the Provider has, from an Advice and Guidance Request, created a Referral, accepting the responsibility to refer it
  -	The FHIR “comment” element will be the value submitted on the reviewComments parameter so that the person picking up the Referral can see the comments added
  -	The FHIR “participant[0].actor.identifier.value” will be the Service which created the Referral
2. After a newly created Referral converted from an Advice and Guidance Request is processed (e.g. booked, sent for triage etc), the values detailed in (1) may no longer be present due to state changes, but you can still tell if there was an Advice and Guidance Request in the Pathway due to the following:
  -	The FHIR “supportingInfo[CommunicationRequest]” references the CommunicationRequest from which the Referral was created. This is only “fetchable” if you are allowed to view the Advice and Guidance Request and can be fetched from View Advice and Guidance Summary endpoint
  -	The FHIR “supportingInfo[DocumentReference]” references
    -	Any attachments on the Referral (as per existing)
    -	Now includes all Advice and Guidance attachments
    -	It will also contain any attachment(s) uploaded as part of the Referral creation (via reviewAttachmentFile )
    -	AND may (unless removed via the Pro App) contain a reference to an automatically generated PDF
    -	The automatically generated PDF is a copy of the Advice and Guidance Conversation that eRS creates when the Referral is created from the Advice and Guidance Request
    -	[eRS-AttachmentType-1](https://fhir.nhs.uk/STU3/CodeSystem/eRS-AttachmentType-1) value tells a Supplier what type of attachment is referenced. In other words, if it was uploaded and associated to the Request as part of Advice and Guidance, by a Referrer, Provider (etc)
    -	The Structured Clinical Information is still only accessible via [A007: Retrieve Clinical Information](https://developer.nhs.uk/apis/e-Referrals/explore_endpoint_a007.html)

### Example Response Body
Note: These examples may contain environment specific URLs and test data, these should be replaced with appropriate values for your implementation..

- [A027_Response.json](downloads/json/A027_Response.json)  

## Response: Failure
If an error occurs, the relating HTTP status code will be returned in the header.  

Where status code 422 (Unprocessable Entity) is returned then an eRS-OperationOutcome-1 will be included in the body, as detailed below:

| OutcomeKey | Description | Suggested Diagnostic |
| ---------- | ----------- | -------------------- |
| INAPPROPRIATE_VALUE | reviewAttachmentFile<br>type is not 'PROVIDER' | ```parameter[x]/resource/type/coding[0]``` must be 'PROVIDER' for ```Binary/70000-70001``` |
| INAPPROPRIATE_VALUE | Guidance Response Clinical Attachments type is not 'GUIDANCE_RESPONSE' | ```parameter[x]/resource/type/coding[0]``` must be 'GUIDANCE_RESPONSE' for ```Binary/70000-70001``` |
| NO_SUCH_REQUEST | Request of type Advice and Guidance Request with this UBRN does not exist | HTTP response only (404) |
| VERSION_CONFLICT | The UBRN version number is not current | HTTP response only (409) |
| DUPLICATE_FILENAME | The File Name of one of the files to be associated with the Request exactly matches (including extension) that of a Provider Clinical Attachment, Advice Request Clinical Attachment, Guidance Response Clinical Attachment or Referrer Clinical Attachment | 'Filename' matches the name of a file already associated with the request |
| NO_RELATIONSHIP | The person authenticated does not have a relationship with the Request so cannot view it | No legitimate relationship with referral UBRN |
| PATIENT_ERROR |  | An error occurred while retrieving the requested patient (NHS Number). Do not attempt again |
| INVALID_REQUEST_STATE | An Advice and Guidance Request must be in progress | An Advice and Guidance Request must be in progress |
| INVALID_REQUEST_STATE | A Referrer must give permission to create a Referral from an Advice and Guidance Request. This Referral is not permitted to be created into a Referral.  | This Advice and Guidance Request is not permitted to be converted to a Referral |
