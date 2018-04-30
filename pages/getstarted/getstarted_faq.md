---
title: Frequently Asked Questions
keywords: development, faq
sidebar: overview_sidebar
toc: false
permalink: getstarted_faq.html
summary: "A set of common questions and answers regarding the e-RS APIs"
---

| Category&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; | Question | Answer |
| -------- | -------- | ------ |
| Comms | How can I view the Digital Health Webinar from the 23/02/2018? | The webinar can be found on the [Digital Health website](https://www.digitalhealth.net/events/webinar-nhs-e-referral-service-interoperability-api-integration-update/). |
| Comms | Can I see the NHS roadmap for the APIs? | The NHS roadmap for the APIs can be found [here](https://digital.nhs.uk/e-Referral-Service/Future-Service). |
| Comms | Which APIs are currently live? | Please see the [API Endpoint Catalogue](explore_endpoint_catalogue.html). |
| Comms | How can I register for further interest and receive future integration updates as they become available? | Please contact the Integration Team directly. |
| Comms | I have a specific scenario I want to talk through, who should I contact? | Please contact the e-RS API Integration Team directly. |
| Comms | I have a question that isn't listed here, who can I ask? | Please contact the e-RS API Integration Team directly. |
| e-RS | Whar does e-RS do? | Please find more information about what functionality e-RS provides [here](https://digital.nhs.uk/e-Referral-Service). |
| e-RS | How do I contact the Solutions Assurance (SA) Service Desk? | Please visit the [Assurance Support website](http://www.assurancesupport.digital.nhs.uk/). |
| Assurance | What is the API assurance approach? What do I need to fill in to get assurance of my solution? | You will need to complete the following documents: TOM, Connection Agreement, End User Policy, and Data Sharing. When you are ready to start this process, please contact the Integration Team and an Implementation Manager will be assigned to you to support you through this process. |
| Authentication | In order to use the APIs do I need to be logged on with the smartcard at all times or does it just require the smartcard UUID to authenticate the user? | The user will need to be logged on with the smartcard at all times to use the APIs. However we are having discussions to look into unattended or system-to-system calls and will be able to provide more information later. |
| Connecting | Can I access the APIs from outside the UK? | Current infrastructure access does not allow overseas companies as it is currently predicated on N3/HSCN network connectivity, IGSoC, the use of smartcards and having clinical sponsorship in place. This may change through the next year when we look to transition our infrastructure over to the cloud, but this is in its initial planning stage and no timescales have been communicated yet. |
| Connecting | How can I get started/access the APIs? - I don't have any e-RS/DEV smart cards | You will need to request smartcards from the SA service desk. Please find details [here](getstarted_get_connected.html). |
| Connecting | How can I access the APIs? - I have e-RS/DEV smartcards but no spine endpoint nor test pack | You will need to create a CSR using your FQDN and fill in an EPR form. Please find details [here](getstarted_get_connected.html). |
| Connecting | How can I access the APIs? - I have e-RS/DEV smart cards, a spine endpoint and a test pack | Once you have an endpoint registration certificate, you can will need to create a key pair by following the instructions in the "NHS e-RS API Connectivity Guide" document and then you can use the information about the API resource models in the "NHS e-RS API Structure" document to call the APIs. Please find details [here](getstarted_get_connected.html). |
| Connecting | I already have a DEV smartcard, do I need another one to access the APIs? | If you have already got a smartcard for the DEV environment, please provide SA Service Desk (sa.servicedesk@nhs.net) the UUID of the smartcard so that they can assign specific roles to it and also provide a test pack for you to access the e-RS APIs. |
| Connecting | Can I use my e-RS/LIVE smartcards with the e-RS/DEV1 environment? | No, you will need new smartcards as a smartcard can only be linked to a single environment (DEV, INT, DEP, TRAIN and LIVE). |
| Connecting | What is Postman? Can I connect using my own solution instead? | We ask Partners to use Postman to establish initial connectivity with the APIs after which you can use your own solution to talk to the APIs. Please learn more about Postman on their [official website](https://www.getpostman.com). |
| Costs | Is there any cost associated with utilising the APIs? | No, the use of the APIs is free. |
| Service | I can access the APIs, what's next? | For more information about e-RS please visit the [NHS e-Referral Service website](https://digital.nhs.uk/services/nhs-e-referral-service/). |
| Service | I have a Service, how can I link it to the NHS Test PAS? | Once you have created the service please send the Service ID to the SA Service Desk who will be able to link it to a Test PAS System for you to book appointments against. |
