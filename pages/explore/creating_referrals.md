---
title: "Creating e-Referrals for Referring Organisations (Archived)"
keywords: creating referrals, creating e-referrals, create, refer, referring
sidebar: overview_sidebar
toc: false
permalink: /creating_referrals.html
---

## Status:

![Deprecated](images/icons/api_deprecated.png)

This site has now been archived.

Please visit [https://digital.nhs.uk/developer/api-catalogue/e-referral-service-fhir](https://digital.nhs.uk/developer/api-catalogue/e-referral-service-fhir) to learn more about how to integrate with the e-Referral Service (e-RS) FHIR API.

## Definition

This page describes the APIs required to conduct a search for services relevant for the selected patient, create an e-referral with a shortlist of directly and/or in-directly bookable services or create an e-referral for a Referral Assessment Service (RAS). The APIs also allow for the initial upload of attachments (Sometimes known as "The referral letter") and generate a confirmation letter for the patient. The search limits results to services which are appropriate for patient and the referring organisation based on the commissioning rules that apply to the authenticated user and/or the patient.

Following creation of a referral to a directly bookable service in e-RS a search for available appointment slots can be performed and a slot booked for the patient against their referral. In the case where there are no available appointment slots for a directly bookable service then the responsibility for booking the patient's appointment can be deferred to the service provider. In both cases the relevant patient letter can be downloaded.

## Process Diagram

[![Creating Referrals](images/explore/creating_referrals.png)](images/explore/creating_referrals.png)  

## The following APIs can be used to create an e-referral

### Authentication and Authorisation
* [A001 – Create Professional Session](explore_endpoint_a001.html) ![Live](images/icons/api_live.png)
* [A002 – Professional Session Select Role](explore_endpoint_a002.html) ![Live](images/icons/api_live.png)
* [A003 – Delete Professional Session](explore_endpoint_a003.html) ![Live](images/icons/api_live.png)

### Reference Data
* [A004 - Retrieve Reference Data (STU3)](explore_endpoint_a004.html) ![Live](images/icons/api_live.png)

### Create Referral
* [A010 - Patient Service Search](explore_endpoint_a010.html) ![Live](images/icons/api_live.png)
* [A011 - Create Referral](explore_endpoint_a011.html) ![Live](images/icons/api_live.png)
* [A021 - Create Referral and Send for Triage](explore_endpoint_a021.html) ![Live](images/icons/api_live.png)
* [A020 - Upload File To Document Store](explore_endpoint_a020.html) ![Live](images/icons/api_live.png)
* [A012 - Maintain Referral Letter](explore_endpoint_a012.html) ![Live](images/icons/api_live.png)<br>
  (Additional attachments can now be added or removed after first upload) ![Updated](images/icons/updated.png)
* [A019 - Generate Patient Letter](explore_endpoint_a019.html) ![Live](images/icons/api_live.png) with shortlist and details of how to book an appointment

### Book Appointment
* [A015 - Retrieve Appointment Slots](explore_endpoint_a015.html) ![Live](images/icons/api_live.png)
* [A016 - Book or Defer Appointment](explore_endpoint_a016.html) ![Live](images/icons/api_live.png)
* [A019 - Generate Patient Letter](explore_endpoint_a019.html) ![Live](images/icons/api_live.png) with confirmation of appointment booking or deferral to Service Provider

<div style="border: 2px solid #888888; padding: 10px; background: #fff1b5;">
<b>Notes:</b><br>
The creation of an e-referral to a service set up as a RAS is different to other referrals. Therefore, a referral request for a RAS should be created using the endpoint <a href="/explore_endpoint_a021.html">A021: Create Referral And Send For Triage</a> with a shortlist containing ONLY the intended service. However, a referral containing a shortlist of non-RAS services (I.e. Directly bookable services (DBS) or in-directly bookable services (IBS)) should be created using <a href="/explore_endpoint_a011.html">A011: Create Referral</a>.
<br>
<br>
Clinical information should be collated into an attachment and added to the referral, it cannot currently be uploaded as separate structured data.   
</div>
