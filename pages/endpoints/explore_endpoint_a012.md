---
title: "A012: Maintain Referral Letter (Deprecated)"
keywords: endpoint, catalogue, file, referral letter, referrer clinical information
sidebar: overview_sidebar
toc: false
permalink: explore_endpoint_a012.html
summary: false
---

#### Status: ![Deprecated](images/icons/api_deprecated.png)

This endpoint has been deprecated, meaning you should not use it for new integrations.

Instead, please use our newer e-RS FHIR API solution which is documented here:
[https://digital.nhs.uk/developer/api-catalogue/e-referral-service-fhir](https://digital.nhs.uk/developer/api-catalogue/e-referral-service-fhir)

## Description
As a Referring Clinician, Referring Clinician Administrator, Service Provider Clinician or Service Provider Clinician Admin

I want to maintain and associate referral clinical information files (this endpoint could be used to delete files only)

So that I can create the referral letter  

## Resource URL

| Method | URL | Authentication |
| -------------| --- | ---------------- |
| POST | {Base URL}/STU3/v1/ReferralRequest/{ubrn}/$ers.maintainReferralLetter | Session Token [(Details)](develop_business_flow_bf001.html) |

- {Base URL} (Dev1) = https://api.dev1.ers.ncrs.nhs.uk/ers-api
- The {ubrn} represents the unique booking reference number of the Advice and Guidance Request for which the caller is obtaining the “Advice and Guidance summary”


## Operation Definition
The Operation Definition for this endpoint is available on the FHIR server: [eRS-MaintainReferralLetter-Operation-1](https://fhir.nhs.uk/STU3/OperationDefinition/eRS-MaintainReferralLetter-Operation-1/_history/1.0)

## Prerequisite Operations
Each file to be attached to a referral needs to have been individually uploaded using [A020: Upload file to document store](explore_endpoint_a020.html). A020 will return the e-RS file location of each uploaded file; these are the URLs that need to be passed to the Maintain Referral Letter API so that they can be associated to the referral.

This linking action can be performed on newly created referrals that contain no existing attachments or an existing referral with associated attachments. Attachments can be subsequently added or deleted for existing referrals if at least one attachment remains associated with the referral after file maintenance. All new files to be associated with a referral should be uploaded first using [A020: Upload file to document store](explore_endpoint_a020.html) and then linked to the referral using this endpoint.

### Important Information:
The Maintain Referral Letter API can be used either to (1) associate attachments to a referral that has no existing referral letter attachments, OR (2) modify the set of referral letter attachments already associated with a referral.  

For scenario 1 the conceptual process is very simple, i.e. upload attachment(s) via A020, and then associate these via A012.

For scenario 2, the API consumer is required to post all the referral letter attachments they wish to be associated to the referral, including any that were already associated.  

   a)	Where a referral already has two referral letter attachments associated, and the API user wishes to **add some more files**:
      -	the API consumer must upload the additional attachment(s) using A020, and then associate these AND the already associated referral letter attachments via A012
   b)	Where a referral already has three referral letter attachments associated, and the API user wishes to **remove one of these**,
      -	the API consumer must re-associate, via A012, the two attachments that the user wishes to keep AND omit the file the user wishes to remove**. By omitting the file, e-RS will dis-associate the referral attachment.
   c)	Where a referral already has four referral letter attachments associated, and the API user wishes to add some more files and remove some files,
      -	the API consumer must upload the additional attachment(s) using A020, and then associate these AND only those referral letter attachments the user wishes to keep via A012.

In effect A012 completely replaces the set of referral letter attachments previously associated. As such, **it is imperative that the new message must contains all the attachments the user wishes to keep associated.**  

- API consumer must ensure the user is fully aware when referral letter attachments are already associated with a referral and the implications of what will happen as a result of their action. E.g when a referring user wants to update a referral they should be presented with the attachments that are currently associated so they can add and/or remove attachments as required.

**Note:**   
- It is possible to determine which files are already associated to a referral via A005: Retrieve Referral Request, and retrieve these clinical attachments via A006: Retrieve Attachment
- It is not permissible to remove all referral letter attachments leaving zero attachments associated. There must be at least one referral letter attachment associated.


# INPUT

## Request Operation: Header

| Field Name | Value |
| ---- | ---- |
| XAPI_ASID | The "Accredited System ID" issued to the third party |
| HTTP_X_SESSION_KEY | The session key generated by the Create Session endpoint (A001)  |
| Accept | `application/fhir+json` |
| Content-Type |	`application/fhir+json` |

## Request Operation: Parameters

| Parameter Name             | Cardinality | Type            | Notes |
|  ------------------------- | ----------- | --------------- | ----- |
| referralLetterFile         | 1..*        | Resource        |The structure definition of this resource is:  [eRS-DocumentReference-1](https://fhir.nhs.uk/STU3/StructureDefinition/eRS-DocumentReference-1)  |

### Example URI
```http
/STU3/v1/ReferralRequest/000000097366/$ers.maintainReferralLetter
```

### Example Request Header
```http
"XAPI_ASID" : "999000000045",
"HTTP_X_SESSION_KEY" : "pro-api-session:e96357b1-298d-4159-ac58-a8953c3262c6",
"Content-Type" : "application/fhir+json",
"If-Match" : "W/\"3\""
```

### Example Request Body
##### Note: These examples may contain environment specific URLs and test data, these should be replaced with appropriate values for your implementation.  

- [A012 Request.json](downloads/json/A012_Request.json)  

# OUTPUT
## Response: Success
If successful, the status code `200 (OK)` is returned. The response body contains the just updated [eRS-ReferralRequest-1](https://fhir.nhs.uk/STU3/StructureDefinition/eRS-ReferralRequest-1)

### Example Response Header
```http
"X_ERS_TRANSACTION_ID" : "237129a8-af7c-451b-982e-052bf06c223e-1",
"ETag" : "W/\"6\"",
"Content-Disposition" : "inline;filename=f.txt",
"Content-Type" : "application/fhir+json"
```

### Example Response Body
##### Note: These examples may contain environment specific URLs and test data, these should be replaced with appropriate values for your implementation.  

- [A012 Response.json](downloads/json/A012_Response.json)  

## Response: Failure
If an error occurs, the relating [HTTP status code](explore_error_messages.html) will be returned in the header. Where status code 422 (Unprocessable Entity) is returned then an [eRS-OperationOutcome-1](https://fhir.nhs.uk/STU3/StructureDefinition/eRS-OperationOutcome-1) will be included in the body, as detailed below.  

| issue.details.code | Description |
| ------------------ | ------ |
|DUPLICATE_FILENAME | The File Name of one of the files to be associated with the Appointment Request exactly matches (including extension) that of a Provider Clinical Attachment, Advice Request, Guidance Response or Triage Attachment OR The File Name of one of the files to be associated with the Appointment Request exactly matches another filename (including extension) in the list of attachments provided in the request |
| INVALID_REQUEST_STATE | The UBRN relates to an onward referral; or: the referral state is either incomplete or cancelled or the referral has been superseded by an onward referral; or: the referral has an appointment booking with a date prior to today; or: the referral has an appointment booking that has been 'DNAd' ('Did Not Attend'); or: the referral already has referral letter files associated<br>Additional scenario:<br> There is at least one file linked with the Request AND the Appointment is within the Freeze Time period |
| INVALID_REQUEST_TYPE | The UBRN provided exists in e-RS but does not correspond to a referral |
| INVALID_STATE | One of the attachment IDs provided relates to a file that is already linked to a referral AND is not a Referrer attachment type; OR The file/s currently linked to the Request were added via a Referrer Clinical System |
| INVALID_VALUE | The input provided does not conform with the expected data types and format specifically documented on the FHIR OperationDefinition [eRS-maintainReferralLetter-Operation-1](https://fhir.nhs.uk/STU3/OperationDefinition/eRS-maintainReferralLetter-Operation-1/_history/1.0) or on the related FHIR profile [eRS-DocumentReference-1](https://fhir.nhs.uk/STU3/StructureDefinition/eRS-DocumentReference-1)|
| NO_RELATIONSHIP | The user does not have a suitable legitimate relationship with the referral |
| PATIENT_ERROR | There was an error retrieving the patient's record from SDS - this patient cannot be referred via e-RS |
| REFERENCE_NOT_FOUND | The file identified by the attachment ID does not exist in the e-RS document store |
| MISSING_VALUE | There is at least one file linked to the request. The API consumer is trying to unlink all the currently linked attachments from the request, without adding at least one |
| NO_CHANGES_DETECTED | There are no changes to the currently linked files or their file descriptions |
