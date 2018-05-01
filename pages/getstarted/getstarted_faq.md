---
title: Frequently Asked Questions
keywords: development, faq
sidebar: overview_sidebar
toc: false
permalink: getstarted_faq.html
summary: "A set of common questions and answers regarding the e-RS APIs"
---

| Category&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; | Question | Answer |
| -------- | -------- | ------ |
| Overview | How can I view the Digital Health Webinar from 23/02/2018? | The webinar can be found on the [Digital Health website](https://www.digitalhealth.net/events/webinar-nhs-e-referral-service-interoperability-api-integration-update/). |
| Overview | Can I see the NHS roadmap for the APIs? | The NHS roadmap for the APIs can be found [here](https://digital.nhs.uk/e-Referral-Service/Future-Service). |
| Overview | Which APIs are currently live? | Please see the [API Endpoint Catalogue](explore_endpoint_catalogue.html). |
| Overview | How can I register for further interest and receive future integration updates as they become available? | Please contact the NHS e-Referral Service API Integration Team directly. |
| Overview | I have a specific scenario I want to talk through, who should I contact? | Please contact the NHS e-Referral Service API Integration Team directly. |
| Overview | I have a question that is not listed here, who can I ask? | Please contact the NHS e-Referral Service API Integration Team directly. |
| e-Referral | Whar does the NHS e-Referral Service do? | Please find more information about what functionality NHS e-Referral Service provides [here](https://digital.nhs.uk/e-Referral-Service). |
| e-Referral | How do I contact the Solutions Assurance (SA) Service Desk? | Please visit the [Assurance Support website](http://www.assurancesupport.digital.nhs.uk/). |
| Assurance | What is the API assurance approach? What do I need to fill in to get assurance of my solution? | You will need to complete the following documents: TOM, Connection Agreement, End User Policy, and Data Sharing. When you are ready to start this process, please contact the Integration Team and an Implementation Manager will be assigned to you to support you through this process. |
| Authentication | In order to use the APIs do I need to be logged on with the smartcard at all times or does it just require the smartcard UUID to authenticate the user? | The user will need to be logged on with the smartcard at all times to use the APIs. However we are having discussions to look into unattended or system-to-system calls and will be able to provide more information later. |
| Connecting | Can I access the APIs from outside the UK? | Current infrastructure access does not allow overseas companies as it is currently predicated on N3/HSCN network connectivity, Information Governance Statement of Compliance (IGSoC), the use of smartcards and having clinical sponsorship in place. This may change through the next year when we look to transition our infrastructure over to the cloud, but this is in its initial planning stage and no timescales have been communicated yet. |
| Connecting | How can I get started/access the APIs? - I don't have any e-RS/DEV smart cards | You will need to request smartcards from the SA service desk. Please find details [here](getstarted_get_connected.html). |
| Connecting | How can I access the APIs? - I have e-RS/DEV smartcards but no spine endpoint nor test pack | You will need to create a CSR using your FQDN and fill in an EPR form. Please find details [here](getstarted_get_connected.html). |
| Connecting | How can I access the APIs? - I have e-RS/DEV smart cards, a spine endpoint and a test pack | Once you have an endpoint registration certificate, you can will need to create a key pair by following the instructions in the "NHS e-RS API Connectivity Guide" document and then you can use the information about the API resource models in the "NHS e-RS API Structure" document to call the APIs. Please find details [here](getstarted_get_connected.html). |
| Connecting | I already have a DEV smartcard, do I need another one to access the APIs? | If you have already got a smartcard for the DEV environment, please provide SA Service Desk (sa.servicedesk@nhs.net) the UUID of the smartcard so that they can assign specific roles to it and also provide a test pack for you to access the the NHS e-Referral Service APIs. |
| Connecting | Can I use my e-RS/LIVE smartcards with the e-RS/DEV1 environment? | No, you will need new smartcards as a smartcard can only be linked to a single environment (DEV, INT, DEP, TRAIN and LIVE). |
| Connecting | What is Postman? Can I connect using my own solution instead? | We ask Partners to use Postman to establish initial connectivity with the APIs after which you can use your own solution to talk to the APIs. Please learn more about Postman on their [official website](https://www.getpostman.com). |
| Costs | Is there any cost associated with utilising the APIs? | No, the use of the APIs is free. |
| Service | I can access the APIs, what's next? | For more information about the the NHS e-Referral Service please visit the [NHS e-Referral Service website](https://digital.nhs.uk/services/nhs-e-referral-service/). |
| Service | I have a Service, how can I link it to the NHS Test Patient Administration System (PAS)? | Once you have created the service please send the Service ID to the SA Service Desk who will be able to link it to a Test PAS System for you to book appointments against. |
| Technology | What is an API? | API stands for Application Programming Interface. The API is a web service that receives requests and sends responses. From your users perspective, APIs allow them to complete an action without leaving your system. The system uses messages in the JSON format to talk to the API. |
| Technology | What is JSON? | JSON stands for JavaScript Object Notation. It is a syntax for storing and exchanging data as text, written with a notation that resembles how the language JavaScript stores objects. The benefits are wide support across all modern web services and a light-weight data transfer. |
