---
title: Endpoint Catalogue
keywords: endpoint, catalogue
sidebar: overview_sidebar
toc: false
permalink: /explore_endpoint_catalogue.html
summary: "Catalogue of all currently available external e-Referral API endpoints"
---

| ID | Name | Method | URL | Status | FHIR |
|----|------|--------|-----|--------|:----:|
|A002|[Professional Session Select Role](explore_endpoint_a002.html)|PUT|/ProfessionalSession/{sessionKey}|![Live](images/icons/api_live.png)| N/A |
|A001|[Create Professional Session](explore_endpoint_a001.html)|POST|/ProfessionalSession|![Live](images/icons/api_live.png)| N/A |
|A003|[Delete Professional Session](explore_endpoint_a003.html)|DELETE|/ProfessionalSession/{sessionKey}|![Live](images/icons/api_live.png)| N/A |
|A004|[Retrieve Reference Data](explore_endpoint_a004.html)|GET|/ValueSet/{valueSetId}|![Live](images/icons/api_live.png)|[Model](https://nhsconnect.github.io/NHS-FHIR-eRS/referencedata_resources_dstu2.html)|
|A005|[Retrieve Referral](explore_endpoint_a005.html)|GET|/ReferralRequest/{id}|![Live](images/icons/api_live.png)|[Model](https://nhsconnect.github.io/NHS-FHIR-eRS/referralrequest_resources_dstu2.html)|
|A006|[Retrieve Attachment](explore_endpoint_a006.html)|GET|/Binary/{AttachmentLogicalID}|![Live](images/icons/api_live.png)| N/A |
|A007|[Retrieve Clinical Information](explore_endpoint_a007.html)|GET|/Binary/$ers.generateCRI|![Live](images/icons/api_live.png)|[Model](https://nhsconnect.github.io/NHS-FHIR-eRS/retrieveci_resources_dstu2.html)|
|A008|[Retrieve Worklist](explore_endpoint_a008.html)|GET|/ReferralRequest/$ers.fetchworklist|![Live](images/icons/api_live.png)|[Model](https://nhsconnect.github.io/NHS-FHIR-eRS/fetch_worklist_resources_dstu2.html)|
|A009|[Directory of Services Search](explore_endpoint_a009.html)|POST|/HealthcareService/$dos.serviceSearch|![Alpha](images/icons/api_alpha.png)| TBC |
|A010|[Patient Specific Service Search](explore_endpoint_a010.html)|POST|/HealthcareService/$patient.serviceSearch|![Alpha](images/icons/api_alpha.png)|[Model](https://nhsconnect.github.io/NHS-FHIR-eRS/servicesearch_resources_stu3.html)|
|A011|[Create Referral](explore_endpoint_a011.html)|POST|/CreateReferral|![Alpha](images/icons/api_alpha.png)|[Model](https://nhsconnect.github.io/NHS-FHIR-eRS/createreferral_resources_stu3.html)|
|A012|[Maintain Referral Letter](explore_endpoint_a012.html)|POST|/ReferralRequest/{UBRN}/$ers.uploadReferralLetter|![Alpha](images/icons/api_alpha.png)|[Model](https://nhsconnect.github.io/NHS-FHIR-eRS/maintainreferral_resources_stu3.html)|
|A013|[Accept Referral](explore_endpoint_a013.html)|POST|/ReferralRequest/{UBRN}/$ers.accept|![Alpha](images/icons/api_alpha.png)| TBC |
|A014|[Reject Referral](explore_endpoint_a014.html)|POST|/ReferralRequest/{UBRN}/$ers.reject|![Alpha](images/icons/api_alpha.png)| TBC |
|A015|[Retrieve Appointment Slots](explore_endpoint_a015.html)|POST|/Slot/$ers.searchAppointmentSlots|![Alpha](images/icons/api_alpha.png)| TBC |
|A016|[Book Appointment](explore_endpoint_a016.html)|POST|/ReferralRequest/{UBRN}/$ers.bookdirect|![Alpha](images/icons/api_alpha.png)| TBC |
|A017|[Defer Booking to Provider](explore_endpoint_a017.html)|POST|/ReferralRequest/{UBRN}/$ers.deferBooking|![Alpha](images/icons/api_alpha.png)| TBC |
|A018|[Re-book Appointment](explore_endpoint_a018.html)|POST|/ReferralRequest/{UBRN}/$ers.deferBooking|![Alpha](images/icons/api_alpha.png)| TBC |
|A019|[Generate Patient Letter](explore_endpoint_a019.html)|POST|/ReferralRequest/{UBRN}/$ers.generatePatientLetter|![Beta](images/icons/api_beta.png)|[Model](https://nhsconnect.github.io/NHS-FHIR-eRS/genpatientletter_resources_stu3.html)|
|A020|[Upload File To Document Store](explore_endpoint_a020.html)|POST|/Binary|![Alpha](images/icons/api_alpha.png)| N/A |

If you feel functionality you require is missing from this list please log a request using the [User Need Request Form](downloads/NHS_e-Referral_Service_User_Need_Request_Form.docx).
