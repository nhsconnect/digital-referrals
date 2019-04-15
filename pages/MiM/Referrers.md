---
title: Referrers
keywords: MiM, XML
sidebar: MiM_sidebar
toc: false
permalink: mim_referrers.html
summary: "XML Integration for Referring Organisations"
---

## Messaging ##

NHS e-Referral Service exchanges messages with Referrer systems via the messaging standards documented in the Message Implementation Manual (MiM) and External Interface Specification (EIS) as specified in the document references section.  It is assumed that the reader fully understands the content of the EIS and MiM.

Although NHS e-Referral Service currently supports two message interaction patterns, new suppliers/upgrading suppliers MUST implement MiM3.01.09.  Each MiM version contains specific versions of the NHS e-Referral Service message interactions and the NHS e-Referral Service application only supports those interaction versions with the correct version of the MiM/EIS. NHS e-Referral Service DOES NOT support any other versions of the MiM.


## Home Page Seamless Transition ##

Compliant systems Must support a mechanism for a logged on user to invoke the NHS e-Referral Service home page in the context of their (single) Role Profile in use in the compliant system.  NHS e-Referral Service is invoked by a URL address and passed the user’s current role profile code in the query string; NHS e-Referral Service will respond by displaying the user’s home page.  

The Compliant system Must provide this facility in appropriate places and contexts within their system.  It Must be easy to use and when the user invokes a home page seamless transition the effect is for the user to enter NHS e-Referral Service with no further user interaction (unless the role profile has more than one NHS e-Referral Service business function in which case NHS e-Referral Service will prompt the user to select the relevant one).
Home Page seamless transition is separate from the UBRN seamless transition (detailed later in the requirements) which used to direct a user in the patients context to the service search screens.  

The seamless transition support within NHS e-Referral Service (both home page seamless transition and UBRN seamless transition) allows an integrated Referrer to launch NHS e-Referral Service in context within a browser window.  The browser window can be a new window or can be an embedded browser control.
Currently, there is no recommended configuration for using a Web Browser Control to access NHS e-Referral Service, and in view of the large number of possible configurations it is unlikely that NHS Digital will produce a definitive statement of a standard configuration.  
