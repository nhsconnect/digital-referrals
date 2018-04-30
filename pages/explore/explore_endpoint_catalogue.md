---
title: Endpoint Catalogue
keywords: endpoint, catalogue
sidebar: overview_sidebar
toc: false
permalink: /explore_endpoint_catalogue.html
summary: "Catalogue of all external e-RS API endpoints"
---

|Id&nbsp;&nbsp;&nbsp;&nbsp;|Name|Family|Verb&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|URI|
|---|---|---|---|
|A001|[Create Professional Session](explore_endpoint_a001.html)|Session|POST|/v1/ProfessionalSession|
|A002|[Professional Session Select Role](explore_endpoint_a002.html)|Session|PUT|/v1/ProfessionalSession/{sessionKey}|
|A003|[Delete Professional Session](explore_endpoint_a003.html)|Session|DELETE|/v1/ProfessionalSession/{sessionKey}|
|A004|[Retrieve Reference Data](explore_endpoint_a004.html)|Reference Data|GET|/v1/ValueSet/{valueSetId}|
|A005|[Retrieve Referral Request](explore_endpoint_a005.html)|Clinical Referral Information|GET|/v1/ReferralRequest/{id}|
|A006|[Retrieve Attachment](explore_endpoint_a006.html)|Clinical Referral Information|GET|/v1/Binary/att-{referralRequestAttachmentId|
|A007|[Retrieve Clinical Information](explore_endpoint_a007.html)|Clinical Referral Information|GET|/v1/Binary/$ers.generateCRI|
|A008|[Retrieve Worklist](explore_endpoint_a008.html)|Clinical Referral Information|GET|/v1/ReferralRequest/$ers.fetchworklist|
|A009|[Directory Service Search](explore_endpoint_a009.html)|Service Search|POST|/v1/HealthcareService/$dos.serviceSearch|
|A010|[Patient Service Search](explore_endpoint_a010.html)|Service Search|POST|/v1/HealthcareService/$patient.serviceSearch|
|A011|[Create Referral Request Through Shortlist](explore_endpoint_a011.html)|Referral Request|POST|/v1/CreateReferral|
|A012|[Upload Attachments](explore_endpoint_a012.html)|Referral Request|POST|/v1/ReferralRequest/{{UBRN}}/$ers.uploadReferralLetter|
|A013|[Accept Referral](explore_endpoint_a013.html)|Referral Request|POST|/v1/ReferralRequest/{{UBRN}}/$ers.accept|
|A014|[Reject Referral](explore_endpoint_a014.html)|Referral Request|POST|/v1/ReferralRequest/{{UBRN}}/$ers.reject|
