---
title: Endpoint Catalogue (Archived)
keywords: endpoint, catalogue
sidebar: overview_sidebar
toc: false

---

## APIs In Development

As of November 2022, our new e-RS FHIR API solution should be used for all new Partner integrations. Please navigate to [https://digital.nhs.uk/developer/api-catalogue/e-referral-service-fhir](https://digital.nhs.uk/developer/api-catalogue/e-referral-service-fhir) for more information including how to Onboard.


## Deprecated FHIR v3 API endpoints  

| ID | Name | Endpoint URL | Status | Retirement Date |
|----|------|--------------------|--------|--------|
|A001|[Create Professional Session](explore_endpoint_a001.html) | POST: /v1/ProfessionalSession | ![Deprecated](images/icons/api_deprecated.png) | TBC |
|A002|[Professional Session Select Role](explore_endpoint_a002.html) | PUT: /v1/ProfessionalSession/{sessionKey} | ![Deprecated](images/icons/api_deprecated.png) | TBC |
|A003|[Delete Professional Session](explore_endpoint_a003.html) | DELETE: /v1/ProfessionalSession/{sessionKey} | ![Deprecated](images/icons/api_deprecated.png) | TBC |
|A004|[Retrieve Reference Data](explore_endpoint_a004.html) | GET: /STU3/v1/CodeSystem/{CodeSystemID} | ![Deprecated](images/icons/api_deprecated.png) | TBC |
|A005|[Retrieve Referral](explore_endpoint_a005.html) | GET: /STU3/v1/ReferralRequest/{id} | ![Deprecated](images/icons/api_deprecated.png) | TBC |
|A006|[Retrieve Attachment](explore_endpoint_a006.html) | GET: /STU3/v1/Binary/{AttachmentLogicalID} | ![Deprecated](images/icons/api_deprecated.png) | TBC |
|A007|[Retrieve Clinical Information](explore_endpoint_a007.html) | GET: /STU3/v1/ReferralRequest/{ubrn}/$ers.generateCRI | ![Deprecated](images/icons/api_deprecated.png) | TBC |
|A008|[Retrieve Worklist](explore_endpoint_a008.html) | POST: /STU3/v1/ReferralRequest/$ers.fetchworklist | ![Deprecated](images/icons/api_deprecated.png) | TBC |
|A010|[Patient Service Search](explore_endpoint_a010.html) | POST: STU3/v1/HealthcareService/$ers.searchHealthcareServicesForPatient | ![Deprecated](images/icons/api_deprecated.png) | TBC |
|A011|[Create Referral](explore_endpoint_a011.html) | POST: STU3/v1/ReferralRequest/$ers.createReferral | ![Deprecated](images/icons/api_deprecated.png) | TBC |
|A012|[Maintain Referral Letter](explore_endpoint_a012.html) | POST: STU3/v1/ReferralRequest/{ubrn}/$ers.maintainReferralLetter | ![Deprecated](images/icons/api_deprecated.png) | TBC |
|A013|[Accept Referral](explore_endpoint_a013.html) | POST: /STU3/v1/ReferralRequest/{ubrn}/$ers.acceptReferral | ![Deprecated](images/icons/api_deprecated.png) | TBC |
|A014|[Reject Referral](explore_endpoint_a014.html) | POST: /STU3/v1/ReferralRequest/{ubrn}/$ers.rejectReferral | ![Deprecated](images/icons/api_deprecated.png) | TBC |
|A015|[Retrieve Appointment Slots](explore_endpoint_a015.html)| GET: /STU3/v1/Slot | ![Deprecated](images/icons/api_deprecated.png) | TBC |
|A016|[Book or Defer Appointment](explore_endpoint_a016.html) | POST:	/STU3/v1/Appointment | ![Deprecated](images/icons/api_deprecated.png) | TBC |
|A019|[Generate Patient Letter](explore_endpoint_a019.html) | POST: /STU3/v1/ReferralRequest/{ubrn}/$ers.generatePatientLetter | ![Deprecated](images/icons/api_deprecated.png) | TBC |
|A020|[Upload File To Document Store](explore_endpoint_a020.html) | POST: /STU3/v1/Binary | ![Deprecated](images/icons/api_deprecated.png) | TBC |
|A021|[Create Referral And Send For Triage](explore_endpoint_a021.html) | POST: /STU3/v1/ReferralRequest/$ers.createReferralAndSendForTriage | ![Deprecated](images/icons/api_deprecated.png) | TBC |
|A022|[Cancel Appointment, Action Later](explore_endpoint_a022.html) | POST: /STU3/v1/ReferralRequest/{ubrn}/$ers.CancelAppointmentActionLater | ![Deprecated](images/icons/api_deprecated.png) | TBC |
|A023|[Retrieve Advice and Guidance Requests Worklist](explore_endpoint_a023.html) | GET: /STU3/v1/CommunicationRequest/$ers.fetchworklist | ![Deprecated](images/icons/api_deprecated.png) | TBC |
|A024|[Retrieve Advice and Guidance Request Summary](explore_endpoint_a024.html)  | GET: /STU3/v1/CommunicationRequest/ | ![Deprecated](images/icons/api_deprecated.png) | TBC |
|A025|[Retrieve Advice and Guidance Conversation](explore_endpoint_a025.html) | GET: /STU3/v1/Communication?[parameters] | ![Deprecated](images/icons/api_deprecated.png) | TBC |
|A026|[Send Advice and Guidance Response](explore_endpoint_a026.html) |	POST: /STU3/v1/CommunicationRequest/{ubrn}/$ers.sendCommunicationToRequester | ![Deprecated](images/icons/api_deprecated.png) | TBC |
|A027|[Convert Advice and Guidance Request to Referral](explore_endpoint_a027.html) | POST: /STU3/v1/ReferralRequest/$ers.createFromCommunicationRequestActionLater | ![Deprecated](images/icons/api_deprecated.png) | TBC |
|A028|[Record Review Outcome](explore_endpoint_a028.html) | POST: /STU3/v1/ReferralRequest/ | ![Deprecated](images/icons/api_deprecated.png) | TBC |
|A029|[Available Actions For User List](explore_endpoint_a029.html) | GET: /STU3/v1/Task?focus=ReferralRequest/{ubrn}/_history/int&intent=proposal&status=ready | ![Deprecated](images/icons/api_deprecated.png) | TBC |

## Deprecated FHIR v2 API endpoints   

| ID | Name | Status | Retirement Date |
|----|------|--------| :-------------: |
|A004|[Retrieve Reference Data (DSTU2)](explore_endpoint_a004_DSTU2.html) | ![Deprecated](images/icons/api_deprecated.png) | TBC |
|A005|[Retrieve Referral (DSTU2)](explore_endpoint_a005_DSTU2.html) | ![Deprecated](images/icons/api_deprecated.png) | TBC |
|A006|[Retrieve Attachment (DSTU2)](explore_endpoint_a006_DSTU2.html) | ![Deprecated](images/icons/api_deprecated.png) | TBC |
|A007|[Retrieve Clinical Information (DSTU2)](explore_endpoint_a007_DSTU2.html) | ![Deprecated](images/icons/api_deprecated.png) | TBC |
|A008|[Retrieve Worklist (DSTU2)](explore_endpoint_a008_DSTU2.html) | ![Deprecated](images/icons/api_deprecated.png) | TBC |


## Retired APIs

| ID | Name | Status | Retirement Date | Notes |
|----|------|--------| :-------------: | ----- |
|A009|[Generic Service Search (Alpha)](explore_endpoint_a009.html)| ![Retired](images/icons/api_retired.png) | OCT 2019 | Experimental API, not progressed to production |
|A017|[Defer Appointment (Alpha)](explore_endpoint_a017.html)| ![Retired](images/icons/api_retired.png) | DEC 2020 | This functionality has been incorporated into [A016: Book or Defer Appointment](explore_endpoint_a016.html)|
|A018|[Re-book Appointment (Alpha)](explore_endpoint_a018.html) | ![Retired](images/icons/api_retired.png) | JUN 2020 | Prototype API shelved for future development as required |
