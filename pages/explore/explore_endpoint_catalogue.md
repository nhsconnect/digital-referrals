---
title: Endpoint Catalogue
keywords: endpoint, catalogue
sidebar: overview_sidebar
toc: false
permalink: /explore_endpoint_catalogue.html
summary: "Catalogue of all currently available external e-Referral API endpoints"
---

|Id&nbsp;&nbsp;&nbsp;&nbsp;|Name|Family|Verb&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|URI|Status|FHIR|
|---|---|---|---|---|---|
|A001|[Create Professional Session](explore_endpoint_a001.html)|Session|POST|/v1/ProfessionalSession|<span class="api_status_indicator Live">Live</span>|&nbsp;|
|A002|[Professional Session Select Role](explore_endpoint_a002.html)|Session|PUT|/v1/ProfessionalSession/{sessionKey}|Live|&nbsp;|
|A003|[Delete Professional Session](explore_endpoint_a003.html)|Session|DELETE|/v1/ProfessionalSession/{sessionKey}|Live|&nbsp;|
|A004|[Retrieve Reference Data](explore_endpoint_a004.html)|Reference Data|GET|/v1/ValueSet/{valueSetId}|Live|&nbsp;|
|A005|[Retrieve Referral Request](explore_endpoint_a005.html)|Clinical Referral Information|GET|/v1/ReferralRequest/{id}|Live|[Model](https://data.developer.nhs.uk/specifications/eRS-draftd/Profile.ReferralsForReviewWorklistResponse/ers-referralrequest-1.html)|
|A006|[Retrieve Attachment](explore_endpoint_a006.html)|Clinical Referral Information|GET|/v1/Binary/att-{referralRequestAttachmentId|Live|&nbsp;|
|A007|[Retrieve Clinical Information](explore_endpoint_a007.html)|Clinical Referral Information|GET|/v1/Binary/$ers.generateCRI|Live|[Model](https://data.developer.nhs.uk/specifications/eRS-draftd/Profile.ClinicalReferralInformationQuery/ers-clinicalreferralinformation-operation-1.html)|
|A008|[Retrieve Worklist](explore_endpoint_a008.html)|Clinical Referral Information|GET|/v1/ReferralRequest/$ers.fetchworklist|Live|[Model](https://data.developer.nhs.uk/specifications/eRS-draftd/Profile.ReferralsForReviewWorklistQuery/ers-fetchworklist-operation-1.html)|
|A009|[Directory Service Search](explore_endpoint_a009.html)|Service Search|POST|/v1/HealthcareService/$dos.serviceSearch|<span class="api_status_indicator Alpha">Alpha</span>|&nbsp;|
|A010|[Patient Service Search](explore_endpoint_a010.html)|Service Search|POST|/v1/HealthcareService/$patient.serviceSearch|Alpha|&nbsp;|
|A011|[Create Referral Request Through Shortlist](explore_endpoint_a011.html)|Referral Request|POST|/v1/CreateReferral|Alpha| |
|A012|[Upload Attachments](explore_endpoint_a012.html)|Referral Request|POST|/v1/ReferralRequest/{{UBRN}}/$ers.uploadReferralLetter|Alpha|&nbsp;|
|A013|[Accept Referral](explore_endpoint_a013.html)|Referral Request|POST|/v1/ReferralRequest/{{UBRN}}/$ers.accept|Alpha|&nbsp;|
|A014|[Reject Referral](explore_endpoint_a014.html)|Referral Request|POST|/v1/ReferralRequest/{{UBRN}}/$ers.reject|Alpha|&nbsp;|
|A015|[Retrieve Appointment Slots](explore_endpoint_a015.html)|Referral Request|POST|/v1/Slot/$ers.searchAppointmentSlots|Alpha|&nbsp;|
|A016|[Book Appointment](explore_endpoint_a016.html)|Referral Request|POST|/v1/ReferralRequest/{UBRN}/$ers.bookdirect|Alpha|&nbsp;|
|A017|[Defer Booking to Provider](explore_endpoint_a017.html)|Referral Request|POST|/v1/ReferralRequest/{UBRN}/$ers.deferBooking|Alpha|&nbsp;|
|A018|[Re-book Appointment](explore_endpoint_a018.html)|Referral Request|POST|/v1/ReferralRequest/{UBRN}/$ers.deferBooking|Alpha|&nbsp;|
