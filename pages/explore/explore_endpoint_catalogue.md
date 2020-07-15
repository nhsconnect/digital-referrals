---
title: Endpoint Catalogue
keywords: endpoint, catalogue
sidebar: overview_sidebar
toc: false
permalink: /explore_endpoint_catalogue.html
summary: "Catalogue of all currently available external e-Referral API endpoints"
---

## Live FHIR v3 APIs  

| ID | Name | Endpoint URL | Status |
|----|------|--------------|--------|
|A001|[Create Professional Session](explore_endpoint_a001.html) | POST: /v1/ProfessionalSession | ![Live](images/icons/api_live.png) |
|A002|[Professional Session Select Role](explore_endpoint_a002.html) | PUT: /v1/ProfessionalSession/{sessionKey} | ![Live](images/icons/api_live.png) |
|A003|[Delete Professional Session](explore_endpoint_a003.html) | DELETE: /v1/ProfessionalSession/{sessionKey} | ![Live](images/icons/api_live.png) |
|A004|[Retrieve Reference Data](explore_endpoint_a004.html) | GET: /STU3/v1/CodeSystem/{CodeSystemID} | ![Live](images/icons/api_live.png) |
|A005|[Retrieve Referral](explore_endpoint_a005.html) | GET: /STU3/v1/ReferralRequest/{id} | ![Live](images/icons/api_live.png) |
|A006|[Retrieve Attachment](explore_endpoint_a006.html) | GET: /STU3v1/Binary/{AttachmentLogicalID} | ![Live](images/icons/api_live.png) |
|A007|[Retrieve Clinical Information](explore_endpoint_a007.html) | GET: /STU3/v1/ReferralRequest/{ubrn}/$ers.generateCRI | ![Live](images/icons/api_live.png) |
|A008|[Retrieve Worklist](explore_endpoint_a008.html) | POST: /STU3/v1/ReferralRequest/$ers.fetchworklist | ![Live](images/icons/api_live.png) |
|A010|[Patient Service Search](explore_endpoint_a010.html) | POST: STU3/v1/HealthcareService/$ers.searchHealthcareServicesForPatient | ![Live](images/icons/api_live.png) |
|A011|[Create Referral](explore_endpoint_a011.html) | POST: STU3/v1/ReferralRequest/$ers.createReferral | ![Live](images/icons/api_live.png) |
|A012|[Maintain Referral Letter](explore_endpoint_a012.html) | POST: STU3/v1/ReferralRequest/{UBRN}/$ers.maintainReferralLetter | ![Live](images/icons/api_live.png) |
|A013|[Accept Referral](explore_endpoint_a013.html) | POST: /STU3/v1/ReferralRequest/{ubrn}/$ers.acceptReferral | ![Live](images/icons/api_live.png) |
|A014|[Reject Referral](explore_endpoint_a014.html) | POST: /STU3/v1/ReferralRequest/{ubrn}/$ers.rejectReferral | ![Live](images/icons/api_live.png) |
|A019|[Generate Patient Letter](explore_endpoint_a019.html) | POST: /STU3/v1/ReferralRequest/[UBRN]/$ers.generatePatientLetter | ![Live](images/icons/api_live.png) |
|A020|[Upload File To Document Store](explore_endpoint_a020.html) | POST: /STU3/v1/Binary | ![Live](images/icons/api_live.png) |
|A021|[Create Referral And Send For Triage](explore_endpoint_a021.html) | POST: /STU3/v1/ReferralRequest/$ers.createReferralAndSendForTriage | ![Live](images/icons/api_live.png) |
|A022|[Cancel Appointment, Action Later](explore_endpoint_a022.html) | POST: v1/ReferralRequest/{UBRN}/$ers.CancelAppointmentActionLater | Available Q3 2020 |

## FHIR v2 APIs (Deprecated)   

| ID | Name | Status | Retirement Date |
|----|------|--------| :-------------: |
|A004|[Retrieve Reference Data (DSTU2)](explore_endpoint_a004_DSTU2.html) | ![Deprecated](images/icons/api_deprecated.png) | TBC |
|A005|[Retrieve Referral (DSTU2)](explore_endpoint_a005_DSTU2.html) | ![Deprecated](images/icons/api_deprecated.png) | TBC |
|A006|[Retrieve Attachment (DSTU2)](explore_endpoint_a006_DSTU2.html) | ![Deprecated](images/icons/api_deprecated.png) | TBC |
|A007|[Retrieve Clinical Information (DSTU2)](explore_endpoint_a007_DSTU2.html) | ![Deprecated](images/icons/api_deprecated.png) | TBC |
|A008|[Retrieve Worklist (DSTU2)](explore_endpoint_a008_DSTU2.html) | ![Deprecated](images/icons/api_deprecated.png) | TBC |

## APIs In Development

| ID | Name                                                   | Expected release | FHIR Version |
|----|--------------------------------------------------------|:----------------:|:------------:|
|A015|[Retrieve Appointment Slots](explore_endpoint_a015.html)|      Q3 2020     |     STU3     |
|A016|[Book Appointment](explore_endpoint_a016.html)          |      Q3 2020     |     STU3     |
|A017|[Defer Booking to Provider](explore_endpoint_a017.html) |      Q3 2020     |     STU3     |
|A018|[Re-book Appointment](explore_endpoint_a018.html)       |      Q4 2020     |     STU3     |

## Retired APIs

| ID | Name | Status | Retirement Date |
|----|------|--------| :-------------: |
|A009|[Generic Service Search (Alpha)](explore_endpoint_a009.html)| ![Retired](images/icons/api_retired.png) | OCT 2019 |
