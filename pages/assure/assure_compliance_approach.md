---
title: Compliance Approach
keywords: assurance, compliance
sidebar: overview_sidebar
toc: false
permalink: /assure_compliance_approach.html
summary: "Compliance approach for the e-Referral APIs"
---

## Overview

The overall NHS Digital approach to compliance is based on the Supplier Conformance Assessment List (SCAL) and the End User Online Declaration (EUOD), together these documents allow suppliers and end user organisations to self-certify that their products and solutions are compliant with appropriate NHS standards, specific e-RS compliance requirements and are clinically safe and fit for purpose.

### Supplier Conformance Assessment List (SCAL)  

The Supplier Conformance Assessment List (SCAL) is a technical document which details the supplier approach to information governance, clinical safety, functional testing and e-Referrals requirements. This document will be provided to you by NHS Digital and guidance on how to complete the SCAL is detailed in the document itself.

You can download an example of the SCAL [here](downloads/agreements/SCAL_vsn2.0.xlsx) but the latest version should be obtained from [functional.assurance@nhs.net](mailto:functional.assurance@nhs.net) prior to completion.

If a supplier has not worked with NHS Digital before, there is also a requirement for them to register to use the NHS Digital national service desk to log incidents.

#### Submitting the SCAL
Once the document has been completed, it should be submitted by email to [functional.assurance@nhs.net](mailto:functional.assurance@nhs.net) who will review it and issue a Technical Conformance Certificate.

Once a technical conformance certificate has been issued, it should be embedded into the SCAL document and submitted by email to [interop.mgmt@nhs.net](mailto:interop.mgmt@nhs.net).  

### Connection Agreement
In order to connect to the live service APIs a connection agreement must be signed by the owner of the connecting system. This should be obtained from [interop.mgmt@nhs.net](mailto:interop.mgmt@nhs.net), signed and returned by email.  

### End User Online Declaration (EUOD)
The End User Online Declaration (EUOD) comprises questions about the organisation that is completing the Declaration and also statements around conformance to NHS Digital requirements.

Further guidance on completing the EUOD can be found [here](https://nhs-digital.citizenspace.com/onboarding/d72f6cc8/).

## Special Terms

<div style="border: 2px solid #888888; padding: 10px; background: #eeeeee;">
Version 1.0 of NHS e-Referral API Special Terms. Effective date 1 June 2018. Applicable to all supplier and provider partners and should be read in conjunction with the End User Policy and Connection Agreement above.
</div>

### Data Sharing Requirements and Policy

Data sharing requirements are dependent on the Usage and Setting as defined by the End User Organisation and the Solution Supplier Parties in the Target Operating Model.

The Usage and Settings approval process includes a decision flow to determine whether such agreement is required or not.

The Connecting Supplier Party will not be able to on-board its customers until those End Users have signed a Data Sharing Agreement with NHS Digital, where required.

### Deprecation Policy

NHS Digital will announce if it intends to discontinue or make backwards incompatible changes to its Current Version.

#### Depreciation Schedule

NHS Digital operates an agile development process with regular, dynamic and condensed release cycles.
Deprecation should be interpreted as a fair warning that the either the Current or a Previous Version will soon be turned off.  End User Organisation and the Connecting Party will actively be encouraged to upgrade their implementations at that point. Sunset means that the version is no longer available.

NHS Digital shall provide notification of upcoming sunsets on the NHS Digital Solution Assurance Functional Assurance and Environment Management Team Newsletters.  End User Organisations and the Connecting Party are required to register to the NHS Digital Solution Assurance Functional Assurance and Environment Management Team Newsletters by emailing the Platforms Support Desk (platforms.supportdesk@nhs.net).

NHS Digital will endeavour to provide a 6-month notice period of upcoming sunsets for the Connecting Party to update its system.  NHS Digital shall endeavour not to introduce Major Upgrades (as defined below) more than two times in any twelve-month period. This will mean NHS Digital will practically support a rolling release of two major versions of the Services at one time (beyond alpha and beta development released).

The deprecation schedule will be published on the [Forward Notices](pages/forward_notices.html) page.

### Upgrade Policy

This document describes the upgrade policy for the Services.

#### Overview

At times in is necessary to make changes to the Services. The upgrade policy is provided to increase transparency on how these changes take place.

#### What’s Covered by This Policy

This policy covers both the API request (payload and uri) and API response, defined as minor or major upgrades.

#### Minor Upgrade

Defined as a point release, i.e. from 1.1 to 1.2.
Affects one or multiple endpoints, may impact functioning applications, but often can be applied without having to make changes to applications, i.e. new non-mandatory field.

For Minor Upgrades NHS Digital shall endeavour to:

* Publish detail of changes on developer ecosystem in the upgrade schedule at least 4 weeks before code change is due to be deployed.
* Provide upgrade path advice on developer ecosystem.
* Outreach communications to suppliers with content of change and upgrade path advice.

#### Major Upgrade

Version change is defined as moving from one major release to another (i.e. upgrade from version 4 to 5). Upgrades often involve changes in data structures and program processes, and therefore are more likely to impact a functioning application than an update, i.e. removal of a mandatory field or change in FHIR version.

For Major Upgrades NHS Digital shall endeavour to:

* Publish detail of change on developer ecosystem at least 8 weeks before code change is due to be deployed in the upgrade schedule.
* Provide upgrade path advice on developer ecosystem.
* Outreach communications to suppliers with content of change and upgrade path advice.

#### Upgrade Schedule

The upgrade schedule shall be published on the [Forward notices for the e-Referral APIs](https://developer.nhs.uk/apis/e-Referrals/forward_notices.html) webpage.

### Transparency Policy

NHS Digital shall be entitled to publish from time to time into the public domain or to a defined list or selected recipients a high-level catalogue of registration and implementation status milestones for End User Organisations and the Connecting Parties. These will comprise five milestone achievement phases:

1. Registered: The End User Organisations and the Connecting Party have registered as NHS e-Referral Service API users.
2. Initiation: A defined implementation project has been defined with submitted TOM Usage and Settings.
3. Connected: The Connecting party has achieved a NHS e-Referral Service API call capability from its development environment to the initial NHS Digital Path-To-Live (PTL) environment e-RS/DEV1.
4. Compliance: The End User Organisation and the Connecting Party have developed their technical solution and submitted their completed compliance artefacts to commence the formal product assurance process.
5. Released: The implemented technical solution has successfully achieved product compliance approval and has been released into live NHS e-Referral Service environment.

### Notice Period for Termination

Notice period for termination of the service will be defined in the written notification of the termination when issued to the Connecting Party. Its duration will be dependent on the following factors:

* Number of connected End User sites.
* The care setting of the End User sites.
* The circumstances of the termination.

<div style="border: 2px solid #888888; padding: 10px; background: #eeeeee;">
<i>End of Special Terms.</i>
</div>
