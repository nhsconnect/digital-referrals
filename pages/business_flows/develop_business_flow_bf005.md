---
title: "BF005: Referral Management"
keywords: business, flow
sidebar: overview_sidebar
toc: false
permalink: /develop_business_flow_bf005.html
summary: "Business flows and their related endpoints"
---

###### Status: ![Alpha](images/icons/api_alpha.png)

#### Definition

This business flow describes the process by which a referring clinician can create a referral with a selection of shortlisted services and all the necessary attributes for it to appear on the referrals for review shortlist (i.e. with a referral letter and a booked appointment).

A slot search across all shortlisted services returns the appointment slots that can be booked via e-RS; where appointment slots are not available at the chosen service, the referrer can defer the appointment booking to the provider.

The referral letter can be uploaded or amended at any time up a number of days before the appointment, as set by the service (so as to allow enough time for the referral to be reviewed).

Appointment bookings can be amended and moved to any of the services on the shortlist whose slots are available via e-RS.

While an appointment booking (or a booking deferral) is made at a specific service, referrers are supposed to shortlist more than one service where possible in order to offer patient choice, according to the [NHS Choice Framework](https://www.gov.uk/government/publications/the-nhs-choice-framework/the-nhs-choice-framework-what-choices-are-available-to-me-in-the-nhs) (item 3).

#### Prerequisites
A professional session must be created and [Reference Data Retrieved](explore_endpoint_a004.html)

#### This business flow involves the following APIs

* [A011 - Create Referral Shortlist](explore_endpoint_a011.html)
* [A012 - Upload Attachments](explore_endpoint_a012.html)
* [A015 - Retrieve Appointment Slots](explore_endpoint_a015.html)
* [A016 - Book Appointment](explore_endpoint_a016.html)
* [A017 - Defer to Provider](explore_endpoint_a017.html)
* [A018 - Re-book Appointment](explore_endpoint_a018.html)

#### Review the diagram below to learn more

![BF005: Referral Management](images/develop/BF005-ReferralManagement.png)
