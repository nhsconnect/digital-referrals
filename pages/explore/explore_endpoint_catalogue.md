---
title: Endpoint Catalogue
keywords: endpoint, catalogue
sidebar: overview_sidebar
toc: false
permalink: /explore_endpoint_catalogue.html
summary: "Catalogue of all currently available external e-Referral API endpoints"
---

| ID | Name | Method | URL | Status | FHIR |
|----|------|:-------|-----|:------:|:----:|
|A001|[Create Professional Session](explore_endpoint_a001.html)|POST|/ProfessionalSession|<span style="color: green">Live</span>| N/A |
|A002|[Professional Session Select Role](explore_endpoint_a002.html)|PUT|/ProfessionalSession/{sessionKey}|<span style="color: green">Live</span>| N/A |
|A003|[Delete Professional Session](explore_endpoint_a003.html)|DELETE|/ProfessionalSession/{sessionKey}|<span style="color: green">Live</span>| N/A |
|A004|[Retrieve Reference Data](explore_endpoint_a004.html)|GET|/ValueSet/{valueSetId}|<span style="color: green">Live</span>|[Model](https://nhsconnect.github.io/NHS-FHIR-eRS/referencedata_resources_dstu2.html)|
|A005|[Retrieve Referral Request](explore_endpoint_a005.html)|GET|/ReferralRequest/{id}|<span style="color: green">Live</span>|[Model](https://nhsconnect.github.io/NHS-FHIR-eRS/referralrequest_resources_dstu2.html)|
|A006|[Retrieve Attachment](explore_endpoint_a006.html)|GET|/Binary/att-{referralRequestAttachmentId|<span style="color: green">Live</span>| N/A |
|A007|[Retrieve Clinical Information](explore_endpoint_a007.html)|GET|/Binary/$ers.generateCRI|<span style="color: green">Live</span>|[Model](https://nhsconnect.github.io/NHS-FHIR-eRS/retrieveci_resources_dstu2.html)|
|A008|[Retrieve Worklist](explore_endpoint_a008.html)|GET|/ReferralRequest/$ers.fetchworklist|<span style="color: green">Live</span>|[Model](https://nhsconnect.github.io/NHS-FHIR-eRS/fetch_worklist_resources_dstu2.html)|
|A009|[Directory Service Search](explore_endpoint_a009.html)|POST|/HealthcareService/$dos.serviceSearch|<span class="api_status_indicator Alpha"><span style="color: orange">Alpha</span></span>| TBC |
|A010|[Patient Service Search](explore_endpoint_a010.html)|POST|/HealthcareService/$patient.serviceSearch|<span style="color: orange">Alpha</span>|[Model](https://nhsconnect.github.io/NHS-FHIR-eRS/servicesearch_resources_stu3.html)|
|A011|[Create Referral Request Through Shortlist](explore_endpoint_a011.html)|POST|/CreateReferral|<span style="color: orange">Alpha</span>|[Model](https://nhsconnect.github.io/NHS-FHIR-eRS/createreferral_resources_stu3.html)|
|A012|[Upload Attachments](explore_endpoint_a012.html)|POST|/ReferralRequest/{{UBRN}}/$ers.uploadReferralLetter|<span style="color: orange">Alpha</span>|[Model](https://nhsconnect.github.io/NHS-FHIR-eRS/maintainreferral_resources_stu3.html)|
|A013|[Accept Referral](explore_endpoint_a013.html)|POST|/ReferralRequest/{{UBRN}}/$ers.accept|<span style="color: orange">Alpha</span>| TBC |
|A014|[Reject Referral](explore_endpoint_a014.html)|POST|/ReferralRequest/{{UBRN}}/$ers.reject|<span style="color: orange">Alpha</span>| TBC |
|A015|[Retrieve Appointment Slots](explore_endpoint_a015.html)|POST|/Slot/$ers.searchAppointmentSlots|<span style="color: orange">Alpha</span>| TBC |
|A016|[Book Appointment](explore_endpoint_a016.html)|POST|/ReferralRequest/{UBRN}/$ers.bookdirect|<span style="color: orange">Alpha</span>| TBC |
|A017|[Defer Booking to Provider](explore_endpoint_a017.html)|POST|/ReferralRequest/{UBRN}/$ers.deferBooking|<span style="color: orange">Alpha</span>| TBC |
|A018|[Re-book Appointment](explore_endpoint_a018.html)|POST|/ReferralRequest/{UBRN}/$ers.deferBooking|<span style="color: orange">Alpha</span>| TBC |
|A019|[Generate Patient Letter](explore_endpoint_a019.html)|POST|/ReferralRequest/{UBRN}/$ers.generatePatientLetter|<span style="color: cyan">Beta</span>|[Model](https://nhsconnect.github.io/NHS-FHIR-eRS/genpatientletter_resources_stu3.html)|
