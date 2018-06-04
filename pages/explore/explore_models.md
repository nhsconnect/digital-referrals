---
title: Standard Models
keywords: fhir, models
sidebar: overview_sidebar
toc: false
permalink: /explore_models.html
summary: "In-depth information about relevant e-Referral data models"
---

## ProfessionalSession ##

_NOTE: Session level data models are not covered by FHIR and therefore there is no associated e-RS Profile._

### ProfessionalSession Resource ###

|Field|Type|Description|
|---|---|---|
|id|String|Session ID.|
|token|String|Authentication Token.|
|user|ProfessionalSessionUser|Professional User associated with the Session.|
|permission|ProfessionalPermission|Selected Permission.|

### ProfessionalSessionUser ###

|Field|Type|Description|
|---|---|---|
|identifier|String|Unique identifier for the user.|
|firstName|String|User first name.|
|lastName|String|User last name.|
|middleName|String|User middle name.|
|permissions|List<ProfessionalPermission>|Permission applicable to the user.|

### ProfessionalPermission ###

|Field|Type|Description|
|---|---|---|
|businessFunction|BusinessFunction (String)|The enumerated Business Function for the permission.|
|orgIdentifier|String|The unique identifier of the organisation this permission is applicable to.|
|orgName|String|The name of the organisation this permission is applicable to.|

### BusinessFunction (String) ###

Values:

* REFERRING_CLINICIAN
* REFERRING_CLINICIAN_ADMIN
* REFERRING_ADMIN
* BMS_HCP_PROXY
* BMS_ADMIN
* SERVICE_PROVIDER_CLINICIAN
* SERVICE_PROVIDER_CLINICIAN_ADMIN
* SERVICE_PROVIDER_ADMIN
* SERVICE_DEFINER
* BOOKING_MANAGER
* COMMISSIONER
* INFORMATION_ANALYST
* ERS_ADMIN
* ADDITIONAL_REQUIREMENTS_MANAGER
* REFERRER_RIGHTS_MANAGER

## ValueSet ##

|Value Set ID|FHIR Profile|
|---|---|
|SPECIALTY (Beta)|e-RS Specialty|
|REQUEST_PRIORITY|_Not live at this time_|
|CLINIC_TYPE|_Not live at this time_|
|REQUEST_TYPE|_Not live at this time_|
|COMMISSIONING_TYPE|_Not live at this time_|
