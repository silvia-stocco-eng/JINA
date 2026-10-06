---
unique-name: eessi-rina-6218-security-guide
display-name: EESSI   RINA 6.2.18   Security Guide
category: GENERAL
tags: ec
---

<!-- image -->

<!-- image -->

## EESSI -RINA 6.2.18 Security Guide

Operations Manuals &amp; Guides

Employment, Social Affairs and Inclusion

## Table of Contents

| Table of Contents ..............................................................................................   | Table of Contents ..............................................................................................   | 2                                                                                                 |
|--------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------|
| 1 Introduction ................................................................................................    | 1 Introduction ................................................................................................    | 6                                                                                                 |
| 1.1                                                                                                                | Document overview...............................................................................                   | 6                                                                                                 |
| 1.2                                                                                                                | Context................................................................................................            | 6                                                                                                 |
| 1.3                                                                                                                | Intended Audience                                                                                                  | ................................................................................ 6                |
| 1.4                                                                                                                | EESSI Topology.....................................................................................                | 7                                                                                                 |
| 2 RINA Overview ............................................................................................       | 2 RINA Overview ............................................................................................       | 8                                                                                                 |
| 2.1                                                                                                                | RINA Architecture..................................................................................                | 8                                                                                                 |
| 2.2                                                                                                                | RINA functions......................................................................................               | 9                                                                                                 |
| 2.3                                                                                                                | Overall Security baseline (Policies/Standards)...........................................                          | 9                                                                                                 |
| 2.4 RINA component layers.........................................................................11               | 2.4 RINA component layers.........................................................................11               |                                                                                                   |
| 2.4.1                                                                                                              | RINA Business Messaging Services (BMS)                                                                             | .........................................11                                                       |
| 2.4.2                                                                                                              | RINA Technical Messaging Services (TMS).........................................11                                 |                                                                                                   |
| 2.4.3                                                                                                              | RINA Case Processing Services (CPS)                                                                                | ...............................................12                                                 |
| 2.5 RINA Components                                                                                                | 2.5 RINA Components                                                                                                | ................................................................................13                |
| 2.5.1                                                                                                              | Component segregation                                                                                              | ..................................................................15                              |
| 2.6                                                                                                                | RINA in the Cloud.................................................................................16               |                                                                                                   |
| 2.7                                                                                                                | CIS Benchmarks                                                                                                     | ..................................................................................16              |
| 3                                                                                                                  | Security in Depth principle                                                                                        | ...........................................................................17                     |
| 4 Physical Security.........................................................................................18     | 4 Physical Security.........................................................................................18     |                                                                                                   |
| 5 Network.....................................................................................................19   | 5 Network.....................................................................................................19   |                                                                                                   |
| 5.1                                                                                                                | Firewall                                                                                                           | ...............................................................................................19 |
| 5.2                                                                                                                | Reverse Proxy......................................................................................20              |                                                                                                   |
| 5.3                                                                                                                | Web Application Firewall (WAF)..............................................................20                     |                                                                                                   |
| 5.4                                                                                                                | Traffic flow                                                                                                       | ..........................................................................................21      |
| 6 Operating System .......................................................................................22       | 6 Operating System .......................................................................................22       |                                                                                                   |
| 6.1                                                                                                                | Patch management...............................................................................22                  |                                                                                                   |
| 6.2                                                                                                                | Hardening                                                                                                          | ...........................................................................................23     |
| 6.3                                                                                                                | Parallel usage                                                                                                     | ......................................................................................23          |
| 6.4                                                                                                                | Virtualisation                                                                                                     | .......................................................................................23         |
| 6.5                                                                                                                | User management................................................................................24                  |                                                                                                   |
| 7 Software & application.................................................................................25        | 7 Software & application.................................................................................25        |                                                                                                   |
| 7.1                                                                                                                | RINA Software Catalogue                                                                                            | ......................................................................25                          |
| 7.2                                                                                                                | Hardening                                                                                                          | ...........................................................................................25     |
| 7.3                                                                                                                | SSL/TLS..............................................................................................25            |                                                                                                   |
| 7.4                                                                                                                | Patch management...............................................................................27                  |                                                                                                   |
| 7.5                                                                                                                | User management................................................................................27                  |                                                                                                   |
| 7.5.1                                                                                                              | Roles                                                                                                              | ............................................................................................27    |
| 7.5.2                                                                                                              | Administrator.................................................................................27                   |                                                                                                   |
| 7.6                                                                                                                | Identity and Access Management ...........................................................28                       |                                                                                                   |
| 7.6.1                                                                                                              | Central Authentication Server (CAS).................................................28                             |                                                                                                   |
| 7.7                                                                                                                | Certificate management........................................................................29                   |                                                                                                   |
| 8 Data (Message level)...................................................................................32        | 8 Data (Message level)...................................................................................32        |                                                                                                   |
| 8.1                                                                                                                | Message Overview................................................................................32                 |                                                                                                   |
| 8.2 EESSI message exchange                                                                                         | 8.2 EESSI message exchange                                                                                         | security..........................................................33                              |
| 8.2.1                                                                                                              | Transport level security (SSL/TLS)                                                                                 | ...................................................34                                             |
| 8.2.2                                                                                                              | Technical message-exchange security (signed                                                                        | ebMS)..........................34                                                                 |
| 8.2.3                                                                                                              | Business message security (XAdES) .................................................34                              |                                                                                                   |
| 8.3 RINA Global Messaging Settings.............................................................35                  | 8.3 RINA Global Messaging Settings.............................................................35                  |                                                                                                   |
| 8.3.1                                                                                                              | BMP Validation Mode                                                                                                | ......................................................................35                          |
| 8.3.2                                                                                                              | Authentication (TLS=Transport Layer                                                                                | Security)..................................35                                                     |
| 8.3.3                                                                                                              | Authorisation (Signatures)...............................................................36                        |                                                                                                   |
| 8.3.4                                                                                                              | Business Signatures                                                                                                | .......................................................................36                         |

<!-- image -->

9

<!-- image -->

General recommendations  ............................................................................37

9.1

User access .........................................................................................37

9.2

9.3

Acceptable use policy  ............................................................................38

Security awareness ..............................................................................38

Annexes ..........................................................................................................39

Annex I

-

RINA User roles matrix ...................................................................39

Annex II

-

Annex III

Password management  ...................................................................40

-

Annex III

List of applicable EESSI security statement ......................................41

-

Annex IV

-

RINA Technologies covered by CIS benchmarks  ................................43

Case Study : Web Application Firewall  ..............................................44

## Document Control Information

| Document Control                        | Value                                                                                                                                                                                                                                                                                                                                                                                                                        |
|-----------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Project Title                           | Electronic Exchange of Social Security Information (EESSI)                                                                                                                                                                                                                                                                                                                                                                   |
| Document Title EESSI                    | - RINA 6.2.18 - Security Guide                                                                                                                                                                                                                                                                                                                                                                                               |
| Document Category                       | Operations Manuals                                                                                                                                                                                                                                                                                                                                                                                                           |
| Revision                                | -                                                                                                                                                                                                                                                                                                                                                                                                                            |
| Component Version RINA                  | 6.2.18                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Last Publication Date Project Milestone | 22/12/2021 EESSI-2020 (RINA Fix8)                                                                                                                                                                                                                                                                                                                                                                                            |
| Document Status                         | Final                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Sensitivity (TLP) Distribution terms    | The distribution of this document is done strictly in line with the Traffic Light Protocol (TLP) established by the European Commission ' s note AC 790/15 REV for the EESSI project documentation. In line with the note AC 790/15 REV, this document is labelled as TLP = 'Green'. Therefore, it can be circulated widely within the EESSI community. However, the document or the information herein may not be published |
| Connected/Embedded Files                | None                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Authors                                 | European Commission, DG EMPL A4, EESSI ARCH                                                                                                                                                                                                                                                                                                                                                                                  |
| Revised by                              | European Commission, DG EMPL A4, EESSI QA                                                                                                                                                                                                                                                                                                                                                                                    |
| Approved by                             | European Commission, DG EMPL A4, EESSI PM                                                                                                                                                                                                                                                                                                                                                                                    |

<!-- image -->

## Document history

| Project Milestone Component version   | Date       | Changes/Corrections Description                                                              |
|---------------------------------------|------------|----------------------------------------------------------------------------------------------|
| EESSI-2018                            | -          | Addressing feedback and adding recommendations based on the latest security testing campaign |
| EESSI - 2019 RINA 5.6.4               | 30/11/2019 | Replace the screenshots of chapter 8 in order to be compatible with the current RINA version |
| EESSI - 2020 RINA 6.2.1               | 18/12/2020 | Update to new RINA Architecture and improvements                                             |
| EESSI-2020 (RINA Fix8) RINA 6.2.18    | 22/12/2021 | Provision of clarifications under sections 2.4 and Annex I                                   |

<!-- image -->

## 1. Introduction

## 1.1 Document overview

This  document  provides  security  measures  to  be  taken  into  consideration  when deploying RINA components in a production environment. Different level of security are addressed  in  this  document,  which  is  in  line  with  SEC2.2a  EESSI  Security  Policy document.

The current document is structured as follows:

- Chapter 1 ( this chapter ) provides an overall introduction with key concepts to know regarding RINA
- Chapter  2 provide  general  security  aspects  linked  to  RINA,  it  presents  the Security in depth principle and lists the existing specifications/standards that cover security requirements in the context of EESSI
- Chapter 3-7 describe the security measures that should/must be implemented in line with EESSI security policy in order to mitigate the risks respectively associated to  Physical  Security,  Infrastructure,  Network,  Operating  system,  Software  and Application, in the context of RINA
- Chapter 8 covers the general security aspects that should be considered at enduser level in order to enhance the security posture of RINA environment

## 1.2 Context

EESSI is an ICT system designed to connect Member States' administrations in charge of  social  security  for  electronic  data  exchanges.  EESSI  will  connect  over  thousands Social Security institutions across Europe and support data exchanges estimated to be over 900 million per year. Technically, EESSI network is built by means of a hybrid star/mesh topology where a distinction is made between:

- The National Domains consists of competent institutions and networks - they sit outside the EESSI International network.
- The  EESSI International Domain  including  TESTA  network  and  a central coordination hub named Central Service Node (CSN) .
- Access  Points  (AP) are  the  gateways  that  enforce  the  approved  EESSI messaging  protocol,  security,  definitions  and  which  route  the  messages  in  a reliable  manner  to  the  appropriate  destination.  APs  are  connected  to  both international TESTA network via a national TAP (TESTA Access Point) and to local networks/institutions.
- National  Applications  ( NA ) -applications  used  by  clerks  to  prepare,  send  and receive messages according to the agreed business use cases.
- Reference  Implementation  for  a  National  Application  ( RINA )  is  developed  by EESSI central project team, based on open source software and using a modular design ( reusable components for national systems ).
- National Gateways ( NG ) -optional system that could be used by MS as "gateways" between NAs and AP in order to perform functions such as transformation between national format of the messages to international format, bridging between national communication  protocols  and  the  international  communication  protocols  or intelligent routing etc.
- National Access Services ( NAS ) - supporting systems to perform functions such as archiving, antimalware, monitoring, audit trail and reporting.

## 1.3 Intended Audience

This document is intended for System Administrators responsible for installation and/or maintenance of RINA (s) within the allocated EESSI environment of their country. The document describes a RINA reference architecture, with a focus on security and supports

<!-- image -->

<!-- image -->

## Note:

A single RINA instance may be used by multiple National Institutions exploiting the implemented multi-tenancy feature.

<!-- image -->

the implementation of the requirements defined in EESSI security policies for the RINA. This document is however not meant to be used as a step-by-step hardening guideline to configure the security of RINA components.

## 1.4 EESSI Topology

For the EESSI Post-PRR deployment, the following components must be deployed in each participating Member State:

- One Access Point
- One or more RINA deployment instances in National Institutions

Hereafter, a figure depicts the overall expected EESSI topology:

Figure 1: EESSI Topology

<!-- image -->

## 2. RINA Overview

This  section  provides  an  overview  on  the  different  RINA  components  and  highlights security principles designed in order to ensure a secure functioning of RINA services.

## 2.1 RINA Architecture

Part of the National Institutions Domain, RINA (Reference Implementation for a National Application)  consists  of  a  collection  of  infrastructure  and  communication  services, foundation, repository and publishing services, business, integration and user interface services.

RINA makes available to clerks and their organizations, the tools to implement the EESSI specific  International  Protocol  of  Data  Exchange  based  on  Structured  Electronic Documents in Social Security belonging to European Community Member States and Associated States.

Figure 2: RINA Architecture

<!-- image -->

RINA is based on 4 layers (Figure 2) which are built one on top of the other, plus the CAS module:

- Technical Message Services (TMS) -provide the mechanism for sending/receiving technical messages to the Access Point. It works based on the protocol ebMS3.0 - AS4 profile. It is an internal layer and cannot be used by third parties, being its unique client the RINA BMS.
- Business  Messaging  Services  (BMS) -  provide  a  reusable  component  for sending business messages to the Access Point via the TMS layer. These services provide the translation (business message to technical message and vice versa),

<!-- image -->

<!-- image -->

transformation (converting IDs to GUIDs), validation and signing of the business messages  for  correct  exchange  with  the  EESSI  environment,  and  the  correct reception  of  messages  from  other  institutions.  It  offers  the  BMI  WS  interface making  available  the  integration  of  third  party  applications  to  the  EESSI ecosystem.

- Case Processing Services (CPS) -provide a state full component  built on top of the Business Messaging Services that manage cases in a structured manner taking care of all the issues regarding case flow, documents, notifications, user management and provides two interfaces for external access (NIE and CPI)
- Portal -provides an UI build on top of the Case Processing Services (CPS) having administration consoles and case Processing modules
- CAS Authentication Server -the  SSO (Single Sign On) server providing the authentication to users/clients requesting to use a service

## 2.2 RINA functions

RINA, plays a key role within EESSI's national domain, being in charge perform the following main functions, which are further described in the next section.

- Message Exchange;
- Repository Synchronisation;
- Authentication and Authorisation;
- Logging and Audit Trail;
- Case Management;
- Localisation;
- Message Archiving.

These functions will provide for clerks and their organizations the possibility to perform the agreed BUCs in Social Security across Europe.

## 2.3 Overall Security baseline (Policies/Standards)

A  list  of  SEF-approved  EESSI  security  related  documents  have  been  created  and published on Confluence 1 ; these security artefacts define the baseline requirements and security aspects to be considered for various IT areas within EESSI context.

Hereafter,  the  available  EESSI  security  artefacts  that  might  be  relevant  for  RINA administrators to look at:

- Impact of new Data Protection Regulation &amp; Directory (SEC 1.1a):

https://webgate.ec.europa.eu/CITnet/confluence/pages/viewpage.action?pageId =315032044

- EESSI Personal Data Protection Toolkit (SEC 1.1d) https://webgate.ec.europa.eu/CITnet/confluence/pages/viewpage.action?pageId =611288180
- EESSI Security Policy (SEC2.2a): https://webgate.ec.europa.eu/CITnet/confluence/pages/viewpage.action?pageId

=315032117

- EESSI Access Control Policy (SEC 2.2c): https://webgate.ec.europa.eu/CITnet/confluence/pages/viewpage.action?pageId =315032104
- EESSI Communications &amp; Operations Policy (SEC 2.2d)

1  https://webgate.ec.europa.eu/CITnet/confluence/pages/viewpage.action?pageId=315032117

<!-- image -->

https://webgate.ec.europa.eu/CITnet/confluence/pages/viewpage.action?pageId =315032106

- EESSI Security Incident Management Policy (SEC 2.2g) https://webgate.ec.europa.eu/CITnet/confluence/pages/viewpage.action?pageId =315032117
- EESSI Business Continuity Management Policy (SEC 2.2h):

https://webgate.ec.europa.eu/CITnet/confluence/pages/viewpage.action?pageId =398854320

- Physical and Environmental Security Policy (SEC 2.2j):
- https://webgate.ec.europa.eu/CITnet/confluence/pages/viewpage.action?pageId =445513861
- Certificate &amp; Cryptographic Key Management Standard (SEC 3.2c): https://webgate.ec.europa.eu/CITnet/confluence/pages/viewpage.action?pageId =357632515
- Communications Security Standard (SEC 3.2d):
- https://webgate.ec.europa.eu/CITnet/confluence/pages/viewpage.action?pageId =315032112
- Authentication, Identification and Authorisation Standard (SEC 3.2b): https://webgate.ec.europa.eu/CITnet/confluence/pages/viewpage.action?pageId =315032110
- https://webgate.ec.europa.eu/CITnet/confluence/pages/viewpage.action?pageId
- Auditing Trail Standard (SEC 3.2e): =357632522
- EESSI antimalware standard (SEC 3.2f):
- https://webgate.ec.europa.eu/CITnet/confluence/pages/viewpage.action?pageId =485394059
- EESSI Security Incident Management Standard (SEC 3.2g):
- https://webgate.ec.europa.eu/CITnet/confluence/pages/viewpage.action?pageId =398854314
- Archiving Standard (SEC 3.2h):

https://webgate.ec.europa.eu/CITnet/confluence/pages/viewpage.action?pageId

=547949426

- Monitoring Standard (SEC 3.2i): https://webgate.ec.europa.eu/CITnet/confluence/pages/viewpage.action?pageId
- =547949430
- Infrastructure Security Standard (SEC 3.2j):

https://webgate.ec.europa.eu/CITnet/confluence/pages/viewpage.action?pageId

=315032110

- Compliance Guidelines (SEC 3.3a) :
- https://webgate.ec.europa.eu/CITnet/confluence/pages/viewpage.action?pageId =357632534
- Compliance Checklist (SEC 3.3b):
- https://webgate.ec.europa.eu/CITnet/confluence/pages/viewpage.action?pageId =3576325374
- Certificate Management Guide (SEC 4.1b):
- https://webgate.ec.europa.eu/CITnet/confluence/pages/viewpage.action?pageId =644678912
- https://webgate.ec.europa.eu/CITnet/confluence/pages/viewpage.action?pageId
- Change Management Guide (SEC 4.1c): =644678931
- Incident Management Guide (SEC 4.2a):
- https://webgate.ec.europa.eu/CITnet/confluence/pages/viewpage.action?pageId =650252986
- https://webgate.ec.europa.eu/CITnet/confluence/pages/viewpage.action?pageI=
- Traffic Light Protocol (TLP): 520654103
- EESSI Incident Management Standard (SEC 3.2g)

<!-- image -->

https://webgate.ec.europa.eu/CITnet/confluence/pages/viewpage.action?pageId =398854314

## 2.4 RINA component layers

RINAs are deployed by National Institutions and must be connected to/accessible from two separated networks:

- National  network(s) -secure  national  networks  connecting  the  National Institutions to the data centre where the Access Point is deployed.
- Internal  National  Institution  network(s) -internal  network  used  by  the National Institution, RINA should not be accessible over the public internet.

The RINA component layers as well as their (security) architecture specifications are described  hereafter.  Moreover,  a  reference  is  made  to  the  relevant  specification documents in order to find more in depth information on the interfaces connected to RINA instances.

## 2.4.1 RINA Business Messaging Services (BMS)

RINA Business Messaging Services (BMS) provide capabilities to convert an ebMS User Message (technical message) to a business message and vice versa and to convert an ebMS error or acknowledgement into a message status update. BMS works on top of Technical Messaging Service (TMS) that is based on protocol ebMS3.0 - AS4 profile. Processing  of  the  messages  sent  and  received  is  always  stateless  and  they  are  all handled in the same way, without any specific BUC-related operations, which are left for the integrating systems (e.g. the BUC-Engine in the CPS).

Based on the configuration, each received message and its status changes are passed further to a handler, which decides how to deal with them. For messages being sent, this layer provides a component for consuming them, applying necessary transformation, business signature and validation and passing them to the layer bellow, i.e. TMS.

The stateless message  processing includes the following  main (among  other) operations:

- Transformation
- Stateless Transaction Validation
- Business Signature

Currently there are two interfaces accessible for integration:

- BMI MicroService (BMI-MS) -is used for the internal integration purposes with upper layers of RINA present (CPS).
- BMI WebService (BMI-WS) -is used for integration through SOAP web-services (with National Applications) and does not require the upper RINA layers present.

Both the interfaces are using the same core underlying business message processing modules.  For  more  detailed  information  please  refer  to 'EESSI -RINA  -  Business Messaging Interface (BMI) ' document.

## 2.4.2 RINA Technical Messaging Services (TMS)

TMS in RINA provides a service for sending/receiving technical messages. It works based on the protocol ebMS3.0 - AS4 profile. National Applications have also the option to reuse  Technical  Messaging  Service  (without  getting  the  benefits  and  functionalities provided  by  BMS)  as  described  in  the  specification  document  of  this  interface: AS4 Messaging  Profile .  The  technical  messaging  interface  follows  the  file  drop  concept where:

<!-- image -->

- Files that need to be sent are written in a specific output folder. There are two types of files that are serialized:
- o Configuration (Pmode files and Pulling configuration)
- o Output messages
- Files that are received are read from a specific input folder. There are two types of files that can be de-serialized:
- o Input messages
- o Input status updates

In RINA context, this layer communicates via an internal interface (TMI) with a thirdparty  application  -  HolodeckB2B  engine.  It  implements  the  protocol  ebMS3.0  -  AS4 profile and handles the communication between an AP and RINA.

The  only  processing  of  the  message  on  this  layer  includes  the  protocol  related operations. Any further business operations based on the content of the received/sent message are performed in the upper layers.

For more detailed information please refer to the ' RINA - Business Messaging Interface (BMI) ' document.

## 2.4.3 RINA Case Processing Services (CPS)

RINA Case Processing Services provide the backend layer of the RINA Environment. It includes  business  logic,  which  encapsulates  the  complete  stateful  case  processing functionalities as well as configuration of the RINA instances. It integrates the bellow layers to utilize the connection to the AP through the ebMS3.0 - AS4 protocol.

RINA CPS includes a collection of public interfaces, which are used by either RINA Portal or are integrated within the National Systems. The stateful case processing functionality is  leveraged  by  the  integration  of  the  BUC-Engine.  RINA  CPS  layer  provides  the transactional context for operations. Depending  on  the  particular operation, it encapsulates them within a transaction and handles any possible concurrent modification issues. For more detailed information please refer to 'EESSI -RINA - Case Processing Interface (CPI) ' document .

The public interfaces provided by this layer include:

- Case Processing Interface (CPI) -exposes the case processing operations through a set of RESTFul services and provides following main (among other) modules:
- o Search Management
- o Case Management
- o Configuration Management
- o Notification Management

Please refer to the to 'EESSI - RINA - Case Processing Interface (CPI) ' document for more detailed information.

- National  Information  Exchange  Interface  (NIE) -The  National  Information Exchange Interface allows RINA to interact with national applications in order to exchange or receive information in the context of case management (e.g. for creating cases, for completing or exchanging SEDs with national systems). The RINA NIE is in charge to call the National Application for all the important events from the case or document lifecycle and notification generation while providing the relevant information (for example the actual SED part of a document), but it is  the  participating  country  responsibility  to  implement  the  processing  (for example store the SED along with other national useful information or give back an  updated  SED  filled  in  with  information  that  would  be  otherwise  hard  or cumbersome for a clerk to  fill  in  manually).  Please  refer to ' EESSI  -  RINA  -

<!-- image -->

National  Information  Exchange  Interface  (NIE) ' document  for  more  detailed information about NIE.

There are also other non-public interfaces or modules included in the RINA CPS, which interact with other lower layers from the RINA context (e.g BMS, TMS).

<!-- image -->

<!-- image -->

## Note

The documents listed in 2.4.1-2.4.5 are truly important as they provide explanations on various key concepts that are precious from security perspective. They provide a view on the different use cases that involve the  use  of  interfaces.  In  addition  to  that,  services  (e.g.  Antimalware Scanning Service) that are operating behind the interfaces are deeply described  as  well  as  the  events,  exceptions,  auditing  or  validations applicable  in  RINA  components  (including  the  security  related  ones) linked to the described interfaces.

## Recommendation

Security practitioners are encouraged to consider the attributes of active interfaces  and  implement  controls  that  can  be  used  to  restrict  the interfaces usage granularly in order to stay in line with EESSI security policies

## 2.5 RINA Components

The following diagram depicts RINA logical architecture, framed into logical packages and components, which are all described in the next subsections.

<!-- image -->

Figure 3: RINA High Level Component Diagram

<!-- image -->

<!-- image -->

<!-- image -->

| Note According to the required functionalities and the integration level, there are two (2) possible deployment scenarios (refer to EESSI - Rina Installation and Configuration Guides for detailed description of the deployment scenarios): • Scenario 1 : RINA Full Stack Deployment where the RINA portal is the main way of contacting EESSI system and the Case Processing Services (CPS) of RINA are exclusively used for the management of EESSI cases. • Scenario 2: RINA BMIWS Deployment where only the BMS components are installed and configured and the integration with the National Applications is performed at the Business Messaging level through the provided BMI WS (Web Services). At the BMIWS deployment scenario, the inherent RINA Case Management functionality cannot be used.   |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|

## 2.5.1 Component segregation

As mentioned, the RINA system consists of several interacting components where each single  component realises  a  specific  task.  This  ecosystem  of  components  allows  the exchange of business cases, which follow a predefined data scheme, between national institutions.

These components can be set up in one of the two following approaches:

- On a single server, all the components are installed on the same server;
- On a distributed way by using clusters deployed on different servers.

<!-- image -->

<!-- image -->

Depending on the need and the available resources, RINA administrators may choose one of the two approaches. Both have benefits and drawbacks, decision on this regard, should be taken on a case by case basis.

## 2.6 RINA in the Cloud

From governance point of view, there are no restrictions on the usage of a cloud solution for  the  RINA  deployment.  Therefore  Member  States  are  totally  free  to  implement  a cloud-based  RINA  solution  granted  that  the  proper  governance  of  the  security measures/compliance requirements (e.g. GDPR, eIDas, national regulations etc.) are guaranteed by the service provider and sufficient assurance is obtained accordingly.

In  practice,  this  can  be  achieved  by  having  in  place  the  appropriate  SLAs  and  the relevant  third  party  assurance  reports  (e.g.  ISAE  3402,  SOC).  In  case  of  revealing security  gaps  during  the  monitoring  controls  under  the  scope  of  the  provider,  the responsible national institutions should enforce compensating controls aiming of keeping the risks at a pre-defined acceptable level.

From cloud infrastructure  security  point  of  view,  the  traffic  from/to  RINA  should  be properly restricted.

The following security controls should be considered where relevant:

- Private/secure connection to the RINA instance should be setup by means of a secure  solution  (i.e.  VPN  secure  connection),  other  private  tunnels  or  Bastion network architecture in order to guarantee the confidentiality and integrity of the exchanged data;
- Use of Software Defined Network (SDN) and Cloud firewall (security groups) to ensure better isolation and restriction of the traffic;
- Consider the best practices to secure your management planes via the following:
- o Ensure that there is a strong security perimeter for API gateways and web consoles;
- o Use strong authentication and Multi Factor Authentication (MFA) methods;
- o Use separate super administrator and day-to-day administrator account(s) instead of root/primary account holder credentials.

## 2.7 CIS Benchmarks

CIS  Benchmarks  provide  extensive  guidance  on  hardening  ranging  from  operating systems to desktop software packages using various technologies. These configuration guides are provided free of charge by the Centre for Internet Security (CIS) 2 .

These guides, in the form of checklists for compliance checking purpose are based on industrial  best  practices.  They  allow  enhancing  RINA  security  posture  by  providing benchmarks to test against, more particularly at configuration level. Refer to Annex IV , for a list of technologies covered by CIS and that may be relevant for RINA deployment.

2  https://www.cisecurity.org/cis-benchmarks/

## 3. Security in Depth principle

The EESSI security baseline has been defined in a manner to enforce the principle of security-in-depth, which is a multi-layer security concept that increases security posture of the system as a whole. Should attack causes a security mechanism to fail, other mechanisms may still fulfil the necessary security requirements protecting the system. Hereafter, a description of the security in depth principle presented as a multi-layer approach tailored to RINA deployments as well as the corresponding relevant materials for further details, if needed:

- Physical  Security -  describes  security  measures  that  should  be  physically implemented in order to deny unauthorized access to facilities, equipment and resources, as well as to protect personnel and property from damage or harm.
- o Refer to EESSI\_Physical and Environmental Security Policy (SEC 2.2j);
- Networking Security -describes security measures that are applied to networks and communications, firewall and proxy configurations.
- o Refer to EESSI\_Communications Security Standard (SEC 3.2d);
- Windows  Operating  System  Security -describes  the  security  hardening measures  configured  for  the  operating  system  that  hosts  the  SQL  Server  and BizTalk Server, including Windows updates and antimalware;
- o Refer to EESSI\_Infrastructure Security Standard (SEC 3.2j);
- o Refer to EESSI\_Anti-malware Standard (SEC 3.2f);
- EESSI Application/Software Security -describes the security features included in the EESSI application/software, including authentication and authorization.
- o Refer to EESSI Access Control Policy (SEC 2.2c);
- Message Security -describes the ebMS message signature and encryption.
- o Refer to EESSI\_Certificate &amp; Cryptographic Key Management Standard (SEC 3.2c);

<!-- image -->

## Note

The referred security documents define a baseline for RINA security, as they support the principle of 'S ecurity-in-Depth '

The splitting into multiple layers reduces significantly the complexity while managing security challenges. Security in depth principle consists of having multiple layers built one  on  top  of  the  other  with  their  own  specific  risks  that  need  to  be  addressed separately.

Therefore, the efforts should be oriented on mitigating the identified risks associated to each layer  at  a  time.  Note  that  these  layers  can  be  easily  mapped  to  the  different sections of this document.

<!-- image -->

## 4. Physical Security

Physical security describes security measures that are designed to deny unauthorized access to facilities, equipment and resources, and to protect personnel and property from damage or harm.

Physical  security  involves  the  use  of  multiple  layers  of  interdependent  systems  that include  CCTV  surveillance,  security  guards,  protective  barriers,  locks,  access  control protocols, and many other techniques.

The  following  table  lists  measures  that  should  be  implemented  to  satisfy  the  key requirements in the policy.

## Key Requirements :

- Limit the access to the RINA data centre to authorized personnel only
- Protect  the  RINA  data  centre  with  physical  barriers,  such  as  walls,  windows, ceilings, floors, card controlled access points and/ or operated reception desks
- Install  video  surveillance  or  another  monitoring  solution  that  covers  all  entry points of the data centre

Note: These requirements could be not applicable for national institutions in certain environments  (i.e.  third  party  service  provider).  In  these  cases,  the  national institutions must ensure that the minimal security requirements are contractually covered, and thus guarantee by the service provider party.

Refer to the EESSI Physical and Environmental Security policy (SEC 2.2j) for a list of security measures that must/should be implemented to ensure physical security of data centres where RINA is deployed.

The deployed physical security mechanisms, either logical or physical, should consider different tiers/perimeters, according to ISO 27001.

There  exists  up  to  four  defence  lines  to  take  into  account  while  managing  physical security:

- The site or building (e.g. fence, wall, windows, etc.)
- ( eventually ) The floor
- The room
- The asset's container (e.g. cabinet, cupboard, safe, etc.)

<!-- image -->

## 5. Network

This  chapter  describes  the  security  measures  that  are  applicable  to  networks  and communications, firewall and proxy configurations in the context of RINA deployment.

## 5.1 Firewall

For  Windows  environments,  Windows  Firewall  with  Advanced  Security  offers  an additional layer to the security-in-depth model. This will increase manageability while decreasing the likelihood of a successful attack.

Windows Firewall should be enabled on each deployed RINA server with deny-all policy with exceptions for the protocols and ports listed in the Table 1.

Windows Firewall settings can be configured:

- Manually, using the Windows Firewall with Advanced Security configuration;
- Automatically using Group Policy or Local Policy.

It  is  advisable  to  consult the following articles for designing and deploying Windows Firewall for RINA systems:

- Windows Firewall with Advanced Security Overview (https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windowsserver-2012-R2-and-2012/hh831365(v%3dws.11))
- Windows Firewall with Advanced Security Design Guide (https://technet.microsoft.com/en-us/library/jj721516(v=ws.11).aspx)
- Understanding  the  Windows  Firewall  with  Advanced  Security  Design  Process (https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windowsserver-2012-R2-and-2012/jj721539(v%3dws.11) )

For UNIX deployments, 'iptables' tool is sufficient to set up, maintain, and inspect the IP packet filter rules in the Linux kernel.

Table 1: Default ports used by RINA

| Default Port   | Component                                | Description                                                                       |
|----------------|------------------------------------------|-----------------------------------------------------------------------------------|
| 9200           | ElasticSearch                            | Port to bind to for incoming HTTP requests.                                       |
| 9300 5433      | ElasticSearch PostgreSQL                 | Port to bind for communication between nodes. Port to bind for PostgreSQL server. |
| 7071           | HolodeckB2B                              | Port to bind to for HolodeckB2B server.                                           |
| [4000 - 4009]  | Ehcache                                  | Listening port of EHCACHE engine for cache synchronization                        |
| 7070           | Loadbalancer HolodeckB2B RINA Web (HTTP) | Port to bind to for HolodeckB2B cluster. Port to bind to for RINA Web cluster     |
| 80 443         | RINA Web (HTTPS)                         | Port to bind to for RINA Web cluster                                              |
| 8081           | Tomcat                                   | Port to Tomcat                                                                    |
| 4000           | Hazelcast                                | Port to bind to for HAzelcast                                                     |
| 111 and 2049   | NFS                                      | Port to bind to for NFS                                                           |
| 8080           | RINA REST                                | Port to bind to for RINA REST cluster                                             |

Table 1 gives an overview of all default ports used by RINA. This table can be used as reference to configure firewalls on both machines and network devices in the context of RINA.

<!-- image -->

<!-- image -->

## Recommendations :

1. Enable Windows firewall for all network types (domain, private, public) on all RINA components. Refer to Table 1 to identify the ports that must be opened for RINA to function properly.
2. It  is  important,  from  security  perspective,  to  isolate  RINA environment as much as possible. Only RINA instance (and its dependencies) should be installed and active in RINA environment. Dedicated firewall rules should be set up taking in consideration the above list of required ports (Refer to Table 1)
3. All the other ports (not referred to Table 1) should be disabled, unless used for other purposes i.e. to monitor/control (e.g. SSH) remotely RINA components. In this case, make sure to mitigate the associated security risks; and that no vulnerabilities reside in the protocols/applications bound by the opened ports.

## 5.2 Reverse Proxy

A reverse proxy is a key component in RINA deployment, it is an enabler for achieving EESSI security requirements, therefore, it is more than advisable to install and properly configure it in each RINA environment. The reverse proxy allows to filter/restrict the incoming accesses across all RINA components. The reverse proxy should be placed at the entry point ( just behind the firewall ) of a RINA/NA/NG network.

From security perspective, depending on the chosen deployment scheme, it is highly recommended to have a reverse proxy set up in addition to the other required security mechanisms.  The  reverse  proxy  offers  other  features  that  address  EESSI  security requirements/recommendations (CIA), such as load balancing, SSL, etc.

## 5.3 Web Application Firewall (WAF)

A web application firewall is another possible component in RINA deployment. A web application  firewall  is  an  application  firewall  for  HTTP  applications.  It  analyse  HTTP requests a filter them according to a set of rules. These rules cover common attacks such as cross-site scripting (XSS) and SQL injections.

By using a Web Application Firewall, some attack vectors are not possible anymore; however, the WAF needs to be customized to be usable. The effort to perform this customization  can  be  significant  and  needs  to  be  maintained  as  the  application  is modified.

<!-- image -->

Note

Refer to Annex IV for a case study about a WAF on the RINA Application

<!-- image -->

## 5.4 Traffic flow

Figure 4 depicts the communication flows between the different components in RINA.

Figure 4: RINA components communication

<!-- image -->

In summary, the RINA web interface must be accessible to the end users, this is a single page application that make call to the RINA REST interface. The RINA REST must also be accessible to the end user, as calls to this interface are made from the end users browser.

The RINA REST interface writes logs to the ElasticSearch and communicates to BUC Engine to create messages towards the Access Points. BUC Engine communicates the created messages towards HolodeckB2B. Both HolodeckB2B and  BUC Engine uses a PostgreSQL database. Note that BUC Engine also logs to the ElasticSearch.

Depending on the chosen deployment scenario, it is important to configure the (reverse) proxies and firewalls to allow this exchange scheme in order to allow RINA to function properly. In addition, load balancers and clusters should be adapted to the traffic load.

Although,  redundancy  increase  the  availability  but  requires  more  resources,  and therefore  the  misconfiguration  related  risks  are  higher,  that's  why  it  is  highly recommended  to  design  and  implement  a  configuration  management  process  that controls all the assets managed within RINA scope.

<!-- image -->

## Notes:

1. Clusters can be defined as multiple machines as well as multiple ports.
2. If  there  are  other  non-production  deployed  environments  (i.e. Testing and/or Acceptance), these should be totally segregated from the production instance; every communication between the production  and  non-production  environments  must  be  banned (network segregation).

<!-- image -->

## 6. Operating System

This  chapter  describes  the  configuration  and  usage  managed  at  the  RINA  operating systems level

## 6.1 Patch management

RINA  is  delivered  only  for  Windows  and  Linux  Ubuntu  operating  systems  Security patches are key element amongst security aspects, therefore, the security elements should be managed in a consistent way by following procedures and controls that are designed to mitigate the associated risks.

Security Updates policies are described in the ' SEC 3.2j EESSI Infrastructure Security Standard - Chapter: 3.3.2 Patching and Updating ' and in ' EESSI- Upgrade and Update Management Guide' . Some general rules are given below:

- Operating  systems  security  patches MUST  NOT be  applied  on  any  National environment  unless  the  EESSI  Central  Service  Desk  ensures  that  the  specific patches  do  no  not  affect  negatively  the  systems'  performance  and  stability  in anyway;
- EESSI  Central  Service  Desk  quarterly  releases  the  white  catalogue  with  the predefined tested combinations of the Operational systems and software/application  security  patches  with  the  relevant  outcomes  that  declare whether a specific patch or a combination of patches is suitable for the Countries and can be installed with problems;
- The  list  of  the  patches  combinations  is  generated  by  summarising  the  critical requests from the countries and the proposals of the relevant development teams;
- It  is  strongly  recommended  that  all  'centrally  tested'  security  patches  on operational systems should be also tested locally before installing them in National Production Systems to avoid possible incompatibilities;
- The  patch  and  update  procedures  must  be  conducted  in  accordance  with established Updating and Upgrading policies and standards as well as local policies and constraints;
- All  patches  and  updates  must  be  obtained  from  a  legitimate  source  (software vendors);
- Patches must be installed ONLY by experienced/legitimate IT staff.

## Recommendations :

1. Latest security updates for infrastructure software and operating systems should be applied in a timely manner, in a reasonable time window after their official release, on all RINA environments to  avoid  working  with  unpatched  versions  of  software  and/or operating systems. Always stay as up-to-date as possible
2. The security updates and patches must be tested in a controlled environment by EESSI Central Service Desk, before applying them in National environments;
3. The  centrally  tested  security  updates  and  patches  should  be tested  by  the  national  teams  before  applying  them  in  National Production environments in order to identify the potential conflicts between the National applications and the EESSI functionality;

<!-- image -->

<!-- image -->

## 6.2 Hardening

Security hardening at the OS level, is highly important in order to protect the underlying systems of RINA components. The hardening should be looked at from different security areas such as (but not limited to):

- User management (including user configuration, features and roles configuration);
- Network management (including remote access);
- Patch management;
- Components configurations;
- Container;
- Logging and monitoring.

## Recommendations :

1. All automatic  updates  (Windows,  JAVA,  etc)  should  be disabled in  order  to  prevent  potential  unavailability  of  the systems  due  to  application  of  updates  that  may  result  to incompatibility  issues  or  use  carefully  automatic  updates  tools (such  as  Windows  Server  Update  Services  (WSUS),  System Centre Configuration Manager etc.) whenever possible but always test new releases before applying them to production environment
2. Backup of RINA servers is highly recommended, before applying any update on the Server (i.e. service pack,  hotfix  or security patch). A backup management control should be designed and implemented by Member States to ensure that data is backed up in an appropriate and controlled way
3. Make sure that all the service paths used in the context of RINA are quoted if they contain spaces. This is to avoid an unquoted service  path  attack,  which  can  be  exploited  by  an  attacker  to perform privilege escalation on the vulnerable system.

For more information about server hardening, refer to these pages: Windows and Linux

## 6.3 Parallel usage

Using the system for non-EESSI related functionality is not recommended, for instance, services that are not needed by the RINA component(s) installed, and are not required for the functionality of the Windows operating system, must be disabled (i.e. Themes) in order to reduce the attack surface at the RINA operating systems level.

## 6.4 Virtualisation

Virtualisation offers a considerable amount of benefits and can be used in the context of  RINA.  The  properties  of  virtualisation such  as  isolation (at different level), encapsulation allow flexibility, however, it adds extra security considerations that needs to be looking at when configuring the virtualised environment.

<!-- image -->

<!-- image -->

<!-- image -->

## Note

If a hypervisor is used to manage the virtual instances, it is a critical key component, thus make sure to handle its security (in-depth) in a proper way. In addition, security patches should be applied on timely basis to ensure  protection  from  known  vulnerabilities.  If  the  hypervisor  is compromised, its virtual machines are also compromised regardless all the security measures/controls implemented to protect the machines

## 6.5 User management

At  Operating  system  (OS)  level,  during  the  accounts  management  procedure  the following considerations should seriously be taken into account:

- Unnecessary accounts (such as Guest ) must be disabled;
- The use of shared accounts should be avoided, for traceability and accountability reasons.
- Service accounts (e.g. Postgres for DBMS), must be well defined and documented to ensure that their usage is totally under control. Ideally, they should be protected by passwords that change periodically.

## Recommendations :

1. Apply the least-privilege principle when granting access, meaning that  the  accounts  should  not  be  granted  with  more  permissions than  the  necessary  ones  in  order  the  corresponding  roles  to perform the related duties
2. It is also recommended to put in place user access controls that consider the accounts used in the context of RINA. Controls should be designed to address the security risks associated with inappropriate access management, more specifically, to  manage joiners, leavers and movers as well as the periodic review of the user access procedure

<!-- image -->

At OS level, either at domain level or locally, the use of administrative accounts (i.e. administrator) must be protected and restricted to limited number of persons in charge of administrating RINA systems as well as the underlying infrastructure. A strongest password  profile  must  be  enforced  for  these  accounts  given  the  criticality  of  their permissions.

<!-- image -->

## 7. Software &amp; application

This chapter describes the security recommendations related to the different software components used in RINA environments.

## 7.1 RINA Software Catalogue

Hereafter, the main technologies ( software components ) used in  RINA scope are listed:

- Load balancer -Apache web server
- BUC Engine
- Holodeck B2B -Apache Axis2
- REST API -Apache Tomcat
- JAVA
- ElasticSearch
- Logstash
- PostgreSQL

## 7.2 Hardening

Security hardening of RINA components is highly important in order to protect RINA components.  The  hardening  at  application  layer  should  be  looked  at  from  different security areas such as (but not limited to) :

- User management (including user configuration, features and roles configuration);
- Patch management;
- Components configurations;
- Logging and monitoring.

<!-- image -->

## Caution

It  is  important  to  be  noted  that  RINA  backend  components  (e.g. Postgres , Elasticsearch )  must  be  securely  deployed  in  a  secure environment,  as  they  are  provided  without  any  security  hardening mechanisms  to  protect  them.  Access  to  those  backend  components must be restricted and limited to few administrators.

The Security hardening of these critical components must be handled by member states as the security configuration required to protect them is highly dependent on the environments in which RINA will operate. It is therefore  important  for  administrator  to  have  this  in  mind  while deploying RINA software.  Other security hardening solutions need to be considered.  For  instance,  implementing  SSL/TLS  for  communication between  the  web  interface  and  the  backend  components  is  key  to guarantee secure operations in RINA.

Other important components that need to be deployed and configured securely are the Apache web servers used in RINA. Administrators should configure them considering the associated risks.

- Apache shall not run using system privileges.

For more information about Apache security, refer to this link.

## 7.3 SSL/TLS

The  EESSI  system  must  enable  all  parties  to  exchange  sensitive  data  over  it  in confidence and rely on it to provide protection against i.e. cybersecurity risks therefore, secure and resilient networks between the APs and RINAs in the national domains must be setup.

<!-- image -->

<!-- image -->

Transport  Layer  Security  (TLS)  must  be  implemented  to  make  sure  that  the  links between RINAs and APs within national domains and links between end-user hosts and RINA portals are both using secure encryption protocol. For instance, use "https" instead of "http" protocol for the links connected to RINA instances.

TLS can be configured in the following modes:

- TLS  Pass  Through -this  is  the  recommended  configuration.  TLS  Channel  is established directly between EESSI nodes (by example between RINA and AP). The nodes are performing mutual authentication using certificates. Also in Pilot Build 3 and later releases, TLS Authorisation lists can be configured, to accept connections only from valid EESSI nodes.
- TLS Bridging (it is strongly NOT recommended) -in  environments where traffic inspection at proxy/firewall level is required,  TLS  Bridging  can  be configured. TLS Channel from one EESSI node is terminated at the proxy/firewall, and then another TLS channel is established from the proxy/firewall to the second EESSI node. This configuration adds more complexity since certificates needs to be  installed  on  the  proxy/firewall  and  also  mutual  authentication  needs  to  be configured. The public key certificates have to be added to the IR repository, so they are recognized as valid EESSI nodes and used for authentication.

<!-- image -->

<!-- image -->

## Caution

TLS  bridging is  highly  NOT  recommended since  it  can  cause malfunctions and it may contradict security requirements because the authentication is not handled directly by the involved endpoints.

TLS 1.0 and 1.1 should be disabled. Industry standards specify that TLS 1.0  may  no  longer  be  used  early  2019,  and  also  strongly  suggests disabling TLS 1.1; since these protocols may be affected by vulnerabilities such as FREAK, POODLE, BEAST and CRIME

Recommendations

:

## Recommendations: 1. TLS version 1.2 must be used to ensure proper functioning of the

2.

2. TLS version 1.1, TLS Version 1.0 and all versions of SSL shall not be used of SSL 3. It is recommended to use TLS in TLS pass-through mode with
1. TLS version 1.2 and TLS Version 1.3 must be used to ensure proper functioning of the key agreement phase. (Since version 1.2, TLS\_RSA\_WITH\_AES\_128\_CBC\_SHA is mandatory to implement cipher suite) key agreement phase. (Since version 1.2, TLS\_RSA\_WITH\_AES\_128\_CBC\_SHA is mandatory to implement cipher suite) TLS version 1.0 and 1.1 should not be used as well as all version

mutual authentication using certificates

It is recommended to use TLS in TLS pass-through mode with mutual authentication using certificates.

Moreover , it  is  not  recommended  to  use  TLS  Termination configuration -this configuration is not supported. In this scenario TLS Channel from one EESSI node is terminated at the proxy/firewall, to allow traffic inspection at proxy/firewall level, and then  the  communication  to  the  second  EESSI  node  is  not  secured  (using  clear  text HTTP). Currently, RINA are not accepting connections which are not encrypted and not authenticated with TLS, so this scenario cannot be used.

## 7.4 Patch management

Security Updates policies are described in the ' SEC 3.2j EESSI Infrastructure Security Standard Chapter: 3.3.2 Patching and updating ' .

Refer to Section 6.1 , for recommendations on patch management process.

## 7.5 User management

A user management process at application/software layer should be implemented with either preventive or detective controls aiming to mitigate the risk associated to access granting (i.e. joiners, leavers and movers ). A better management of accounts would increase the resilience and therefore decrease the likelihood of an attack.

The accounts used to manage or access to RINA applications/software can be divided into 3 types, each of them has its own security considerations:

- Service accounts (e.g. ' postgres ' for Postgres DBMS)
- Regular user accounts (e.g. end-user accounts)
- Elevated user accounts (e.g. RINA Administrators)

## 7.5.1 Roles

Defining different roles within a system may impose an extra level of control. However, it allows a more granularity managing access, staying in line with duties segregation principle.

Each institution has different local rules for the assignation of tasks and responsibilities, the local RINA administrators can set up customised case policies that define which types of cases can be processed by a given profile. Therefore, only a part of the sectors or case types may be available as standard option to the end-users.

It is therefore important to assign roles and responsibilities in a controlled way to avoid inappropriate/unauthorised access to RINA environments. Moreover, it is also important to limit the access rights for user to the bare minimum permissions they need to perform their work (Refer to Annex I for user roles matrix). This user roles matrix should be translated to IAM settings on RINA servers.

<!-- image -->

## Note

The  assignment  policies/automatic  rules  must  be  defined  by  RINA administrator from the beginning in order to reflect the adequate roles and responsibilities needed for each single RINA deployment. This step needs to be performed before users start to use RINA platform.

## 7.5.2 Administrator

RINA Administrator access should be limited to a single component or machine. This is to  prevent  full  compromise  of  all  machines/components  upon  loss  or  breach  of credentials of one machine/component. Administrator account should only be able to perform administrative tasks, such as adding/removing a user. Administrator should not have access to any of the business functionalities (e.g. sending/receiving/modify cases) of a component or application.

<!-- image -->

## Recommendation

High privileged accounts must be protected and managed in a controlled way with an appropriate level of traceability (i.e. logs) and a stricter password policy profile for administrators as opposed to normal users

<!-- image -->

## 7.6 Identity and Access Management

The Identity and Access Management top-level function is a collection of services that enables the system to securely control access to RINA resources for internal or external users. It includes four basic functions:

- Configure IAM: The RINA IAM component can be configured to use the internal identity provider that is the system default source or an external data source;
- Authenticate User: When the end-user logs into the RINA system, he/she must be authenticated against the configured identity provider;
- Synchronise  RINA  default  repository  with  external  repository:  When  external identity provider is selected for managing the organization, a tool synchronizes all the users and groups from the external repository with the internal repository;
- Configure rules for process assignment: Rules that say who can manage what process;

RINA  system  administrators  must  be  able  to  configure  the  Identity  and  Access Management module. Currently, RINA offers four different authentication mechanisms:

- Internal ( default ): The users are authenticated against their username/password stored in RINA datastore.
- LDAP provider : the users are authenticated against an external LDAP server. The user/group profiles are still to be stored (synchronized) in the internal datastore, however the passwords are not needed.
- SAML 2.0 provider : enables to authenticate the users against an external SAML 2.0 identity provider. The user/group profiles are still to be stored (synchronized) in the internal datastore, however the passwords are not needed.
- JWT  Token :  enables  the  authentication  through  a  self-containing  Java  Web Token.

<!-- image -->

<!-- image -->

## Notes:

1. It is important to note that all external identity providers are used for the user authentication only. The user and group profiles must still be stored/manipulated within RINA datastore. RINA provides a synchronization  functionality  to  be  able  to  create/update  these profiles from external repositories
2. Please refer to EESSI -RINA Identity and Access Management (IAM) document for further details on how to manage Identity and Access Management within RINA. (E.g. LDAP user parameters mapping)

## Recommendation

There are no restrictions on the supported external identity providers, however, they must be accessible from the RINA infrastructure (i.e. firewall settings, etc.)

## 7.6.1 Central Authentication Server (CAS)

RINA  is  shipped  with  a  Central  Authentication  Server  (CAS)  which  handles  the authentication  of  a  user.  Internal  and  external  authentication  is  always  managed through the CAS server. Below, you will find the authentication schema used by RINA CPI (and possibly other system components).

<!-- image -->

<!-- image -->

<!-- image -->

The  CAS  server  acts  as  a  single-sign-on  server,  similar  to  the  former  OAuth  2 authentication server, however it provides many out-of-the-box integrations with third party systems and authentication protocols.

<!-- image -->

## Note

Refer  to  EESSI -RINA  Identity  and  Access  Management  (IAM) documents  for  further  details  on  how  IAM  authentication  process  is handled through the use of CAS

## 7.7 Certificate management

All certificates used for RINA in EESSI National Domain must be issued by a trust service provider issuing certificates in line with the eIDAS-Regulation. RINA uses the following stores for certificates.

- The Key Sores contain private keys used by RINA;
- The Trust Stores contain public keys for the corresponding parties.

To  enable  RINA  to  connect  to  the  appropriate  Access  Point,  at  least  the  following certificates need to be imported in the corresponding stores. In total, there are six Java Keystores (JKS) that contain the certificates to be used by RINA, these JKS are located under C:\EESSI\Share\repository\certs\ :

<!-- image -->

## Notes:

1. JKS default password is 'supervisor' for tlskeystore.jks, tlstruststore.jks, privatekeys.jks, publickeys.jks and businessSignatureKeystore.jks;
2. JKS default password is 'trusted' for trustedcerts.jks ;
3. Refer  to  EESSI  Certificate  &amp;  Cryptographic  Key  Management Standard to obtain more information about the certificate lifecycle management guidelines;
4. Refer  to  EESSI  Certificate  Management  Guide  to  obtain  more information about the procedures to import RINA certificates;
5. Refer to EESSI Certificate Profile - National Domain to obtain more information about the X.509 Certificates Profiles that should be used in the context of RINA at national domain level;
6. Refer to ' EESSI -AP MS Certificate Request Procedure ' document to obtain more information about the procedure to be followed in order to request certificates in the international domain;
7. The certificates  must  be  added  manually  in  the  ' trustedcerts.jks ' since they cannot be updated using the RINA Admin Portal.

<!-- image -->

Table 2: Keystores and TrustStores Details

|                                                                                                                                                    | Private Key Store                                                                                                                                                                                                                                                                                               | Public Key Trust Store           |
|----------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|
| • Content: National Private Key for TLS (key password must be supervisor) • Name: tlskeystore.jks • JKS default password:                          | • Content: Access Point Public Key for TLS (National Domain) • Name: tlstruststore.jks • JKS default password: ' supervisor '                                                                                                                                                                                   | Authentication (TLS) Application |
| • Content: National Application Private Key for ebMS signature • Name: privatekeys.jks • JKS default password: ' supervisor '                      | • Content: Access Point Public Key for ebMS signature (International/Testa Domain) • Name: publickeys.jks • JKS default password: ' supervisor '                                                                                                                                                                | Authorisation (Signatures)       |
| • Content: National Application Private Key for Business Signature • Name: businessSignatureKeystore.jks • JKS default password: ' supervisor123 ' |                                                                                                                                                                                                                                                                                                                 | Business Signature               |
|                                                                                                                                                    | • Content: Certification Authorities Public Keys (Root CA, Intermediate and Issuer) for all National (all participant countries) and International Domain because NA must be able to validate the certificate chain of every certificate imported. • Name: trustedcerts.jks • JKS default password: ' trusted ' | Certificate authority (CA)       |

<!-- image -->

## Recommendation

Default  passwords  should follow the best practices  and  comply  with password policy described in SEC 2.2c EESSI Access Control Policy .

<!-- image -->

## 8. Data (Message level)

This section describes the message security enablers; it highlights considerations to be taken into account from security perspective related to the data exchanged within EESSI ecosystem

## 8.1 Message Overview

The messaging protocol used in EESSI to exchange information between organisations is the AS4 profile of ebMS 3.0. To implement ebMS 3.0 in a message exchange, the specification must be described in a so called usage profile.

Figure 5: EESSI message parts

<!-- image -->

The ebMS message format used in EESSI includes the following components:

- SOAP Header -contains source and destination institution IDs. This information is used by Access Point to perform Synchronous Transport validation.
- Business Document
- o Standard  Business  Document  Header  (SBDH)  -  contains  source  and destination  institution  IDs.  This  information  is  used  by  Access  Point  to perform Asynchronous Business validation.
- o The Structured Electronic  Documents  (SEDs) -Structured Electronic Documents (SEDs), which represent the body of the Business Information exchange  between  institutions  in  the  EESSI  system,  defined  by  member states  and  approved  by  the  Administrative  Commission  based  on  the  EC Regulations. In EESSI, SEDs are physically implemented as XML messages that are authored by a National Application. Each XML SED must conform to a set of specific syntactic rules described in an XSD file.
- Attachments -each exchange  message  can  contain zero, one or  more attachments.

Communication  using  ebMS  is  performed  over  HTTP  secured  with  Transport  Layer Security (TLS). The protocol ebMS 3.0 AS4 profile also supports message signature with optional encryption. AS4 Encryption applies to SBDH, SED and attachments.

<!-- image -->

The following message types are used in EESSI:

- User Message (also called Business Message) -the messages initiated by users (clerks)  from  National  Applications.  These  messages  contain  the  Business Documents  (SBDH,  SED)  and  zero,  one  or  more  attachments  (documents  or images).
- System Messages -are used to transmit system information.
- o Receipt Message -this is sent by a Receiving National Application (R-NA) upon  a  Business  message  receipt  as  an  acknowledgment  of  a  successful message delivery. The Receipt message contains a reference to the original User Message id.
- o Error  Messages -these  are  messages  generated  by  Access  Points  or receiving application if asynchronous validation fails. These messages are typically placed in the Inbox queue for the Sending National Application (SNA) that sent the User Message which failed during validation.
- o Pull  Request -a  special  case  of  system  message  which  is  sent  by  a Receiving  National  Application  (R-NA)  after  connecting  to  the  Inbox  web service on the corresponding Receiving Access Point (R-AP).

## 8.2 EESSI message exchange security

EESSI  system  must  implement  three  layers  of  protection  to  ensure  the  security  of exchange of EESSI messages including confidentiality, integrity and authenticity of the messages. The three layers of protection are described below:

Figure 6: Three layers of protection of EESSI message exchange

<!-- image -->

The validation of the receiving messages (via Outbound or Inbound web services) can be performed at two different layers:

- Transport Layer Validation -is performed synchronously, when a message is received via Outbound or Inbound web services. Any validation errors are reported immediately to the Sending National Application (S-NA) or Sending Access Point (S-AP) on the same TLS connection. Transport layer validation is performed on the ebMS level against the data within the ebMS Messaging Header and within the MIME parts.
- Business Layer Validation -is performed asynchronously, after the message has been received and stored on the Receiving Access Point (R-AP). Any validation

<!-- image -->

<!-- image -->

errors are reported to the Sending National Application (S-NA) or Sending Access Point (S-AP) by sending and Error Message. Business layer validation is performed on the level of the business documents against the data within the SBDH, SED and attachments.

<!-- image -->

|   Notes: | Notes:                                                                                                                                                                                                   |
|----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|       1. | Refer to SEC 3.2c EESSI - Certificate & Cryptographic Key Management Standard for more information on Certificate and key management, key cryptographic control as well as the message security enablers |
|       2. | For System Messages, business validation is performed synchronously, when the message is received by the Receiving Access Point.                                                                         |
|       3. | ebMS Message Level Encryption is mandatory ONLY in International Domain between APs.                                                                                                                     |

## 8.2.1 Transport level security (SSL/TLS)

- The EESSI system must enable all parties to exchange sensitive data over it in confidence  and  rely  on  it  to  provide  protection  against  i.e.  cybersecurity  risks therefore, a secure and resilient network between the APs in the member states must be setup.
- The links between APs within the EESSI-core-systems domain network must be secured with appropriate secure encryption protocols. Therefore, the Transport Layer Security (TLS) must be implemented within EESSI system to secure links between AP and RINA/NA. This protocol combines asymmetric key encryption to assure non repudiation between APs and symmetric key derived from asymmetric public key is used to encrypt the links between AP and RINA/NA where the EESSI messages (SED) are exchanged.

## 8.2.2 Technical message-exchange security (signed ebMS)

- EESSI must ensure  the  security  of  technical  messages  used  as  wrapper  to exchange the business EESSI Business messages (SED).
- The security of technical messages exchange must be ensured via the security of web services message-exchanged via implementing signed ebMS 3.0 (profile AS4) messages  which  extends  Web  service  technologies  to  fulfil  the  security requirements below related to B2B documented exchange:
- o Authentication of message originator;
- o Data Integrity of exchanged messages;
- o Non-repudiation of exchanged messages.
- In order to ensure the three security aspects above, ebMS messages must be digitally signed by the following connected parties: Sending Institution (or National Gateway),  Sending  Access  Point  and  Receiving  Access  Point.  In  addition,  the protocol stipulates that connected parties which receive ebMS messages shall send a technical acknowledgement.

## 8.2.3 Business message security (XAdES)

- Business messages are EESSI messages which consist of metadata and a SED which are contained in the payload of ebMS messages.
- Business messages must implement the XAdES protocol (XML Advanced Electronic Signatures) which is a set of extensions to XML-DSig (XML signature), to ensure the following security services:
- o Data Integrity of business messages
- o Non-repudiation of business messages

<!-- image -->

- In order to ensure the two security aspects above, the business messages must be  signed  (using  XAdES)  by  the  sending  AP.  The  signature  of  the  sending Institution  /  RINA  /  National  Gateway  is  not  required  but  it  is  strongly recommended (for security and accountability reasons).
- Several  XAdES  profiles  exist,  but  the  basic  XAdES  profile  must  at  least  be implemented  within  EESSI  to  fulfil  the  legal  requirements  of  European  Union Directive 1999/93/EC for advanced signature. When the XAdES-A profile is used, XAdES  signature can remain valid for long periods, even if underlying cryptographic algorithms are broken which allows archiving SED with signature for long periods.

## 8.3 RINA Global Messaging Settings

This  section  provides  concrete  steps  on  how  to  configure  global  messaging  settings within RINA portal.

## 8.3.1 BMP Validation Mode

BMP validation mode allows the administrator to configure the validation against the local XSD files, at the business message level:

- ' Continue  When  No  Validation ' :  Validation  is  turned  on  but  the  process continues
- ' Exception When No Validation ' : Do not continue when an exception occurs
- ' No Validation ' : no validation performed.

Figure 7: BMP Validation Mode

<!-- image -->

## 8.3.2 Authentication (TLS=Transport Layer Security)

In  this  section  the  administrator  can  add/remove  the  certificates  for  Authentication against the AP and other RINAs. The Password field (for both TLS Keystore and TLS Truststore)  allows  the  administrator  to  set  the  password  for  the  TLS  keystore.  The default password is 'supervisor' (small caps, without quotes).

Figure 8: Authentication

<!-- image -->

In the section ' TLS Keystore ' the administrator has the TLS (private) certificate(s). It is recommended to have a single private key in this section.

In the section TLS Truststore the administrator stores the AP's (public) certificate(s). Normally, there is one certificate per AP.

<!-- image -->

<!-- image -->

## 8.3.3 Authorisation (Signatures).

In this section the administrator can add/remove certificates for signing Messages. The Password field (for both MSG Keystore and MSG Truststore) allows the administrator to set the password for the MSG keystore. The default password is " supervisor' (small caps, without quotes). Normally, the local TLS private certificates are handled in this section.  Additional  information  about  the  Authorisation  is  available  in  the  document ' EESSI -AS4 Messaging Profile ', in 'Chapter 7: Security' and 'Annex A: PMode[1].Security'.

Figure 9: Authorisation (Signatures)

<!-- image -->

The  section MSG  Keystore contains  the  (private)  signing  certificate(s).  Here  the administrator will have the (public) certificate(s) of the AP and other RINA institutions. If the administrator doesn't validate the signatures from the other NAs, their certificate is not needed.

## 8.3.4 Business Signatures

Business Signatures are used for signing the SEDs. Multiple certificates are allowed.

Figure 10:  Business Signatures

<!-- image -->

The pairing between certificate and user is performed in the section user management.

Figure 11: Transport Protocol Settings

<!-- image -->

<!-- image -->

The transport protocol  settings, along with the default values, are described below (Figure 11):

- Transport Mode : This option needs to be defined either as Pull or Push . For Access  Point operation  mode,  the  recommended  setting  for  transport  mode should be PULL.
- Use  compression :  If  selected,  it  allows  the  messages  compression  before sending. Even if compression can save bandwidth, under certain circumstances, it can add overhead and consume the server's resources. This should be set to ON.
- Max Message  Size  (KB) :  This  attribute  is  where  the  maximum  size  of  a message is set. The default value is 51200.
- Retry interval (sec) : This attribute is where the retry interval for re-sending a message is set. The default value is 237600.
- Maximum retries : This attribute is where the maximum number of attempts to send a message is set. The default setting is 1.
- Default pull request interval (sec) : This attribute is where the frequency of checking for new data is set when the Transport Mode is set to PULL. The default setting is 30.
- Antimalware  Mode :  This  attribute  controls  the  mode  of  the  Antimalware function. There are 3 different selectable Antimalware modes:
- o None: No antimalware control is applied (see Figure 11, first selection). Important : 'None' is the default value of Antima lware Mode;
- o Periodic Check: antimalware is applied periodically with the number of time frames to be configured by administrator (see Figure 11, selection 2);
- o Triggered: the Antimalware starts when the administrator 'calls' it. The administrator has to define the 'Scan Command' and the 'Antimalware Inf code' (see Figure 11, selection 3).

<!-- image -->

## 9. General recommendations

## 9.1 User access

It  is  strongly  recommended  to  manage  RINA  accounts  via  the  domain  (i.e.  domain accounts), that helps RINA administrators to keep deep control over RINA accounts in a centralised way. Using the local accounts provides less control over account properties (e.g. passwords policies).

<!-- image -->

<!-- image -->

<!-- image -->

Password policies are described in SEC 2.2c EESSI Access Control Policy .

- Password Length -EESSI system passwords must be sufficiently long so that they are difficult to guess or determine from the encrypted form. Passwords must have  a  minimal  length  of  8  characters.  A  minimal  length  of  10  characters  is recommended.
- Password Composition -  EESSI  system  passwords  should  consist  of  at  least three groups of characters out of: mixed numbers, small and capital letters and symbols.
- Frequency of Password Change - There must be a system provision for EESSI passwords to be changed frequently.

## Recommendations :

1. For Service Accounts, password expiration should be disabled, so it  would not cause system unavailability due to passwords expiring.  Instead,  Service  Accounts  should  manually  change their passwords on a regular basis
2. Password History should be enabled to prevent the reuse of the same password
3. Different passwords must be used for different Service Accounts
4. Password complexity should be enforced using Group Policy at the domain level and not on an individual basis for each account (e.g. local accounts)

## Note

Refer to Annex  III for further recommendations on password management

## 9.2 Acceptable use policy

Acceptable use policies should be provided to the clerks, supervisors and any users interacting with the RINA components.

## 9.3 Security awareness

Clerks and supervisors should be provided with adequate security awareness training on the general security considerations to prevent the targeting of the human factor (e.g. phishing attacks, social engineering …) .

## Annexes

## Annex I -RINA User roles matrix

Table 3: RINA User Roles and permitted actions matrix

<!-- image -->

| RINA USER ROLES            | RINA USER ROLES                                                                          | Manager/ Supervisor   | Authorised Clerk   | Un- Authorised Clerk   | Auditor   | Viewer   | Medical User   | VIP User   | Everyone   |
|----------------------------|------------------------------------------------------------------------------------------|-----------------------|--------------------|------------------------|-----------|----------|----------------|------------|------------|
| Management Case Assignment | Assign Case                                                                              | ✓                     |                    |                        |           |          |                |            |            |
| Management Case Assignment | Request Assignment                                                                       | ✓                     | ✓                  | ✓                      | ✓         | ✓        | ✓              | ✓          | ✓          |
| Management Case Assignment | Authorise Assignment                                                                     | ✓                     |                    |                        |           |          |                |            |            |
| Management Case Assignment | Create Case                                                                              |                       | ✓                  | ✓                      |           |          |                |            |            |
| Management Case Assignment | Create SED                                                                               |                       | ✓                  | ✓                      |           |          |                |            |            |
| Management Case Assignment | View SED                                                                                 | ✓                     | ✓                  | ✓                      | ✓         | ✓        |                |            |            |
| Management Case Assignment | Send SED                                                                                 | ✓                     | ✓                  |                        |           |          |                |            |            |
| Management Case Assignment | Request Approval for sending                                                             |                       |                    | ✓                      |           |          |                |            |            |
| Management Case Assignment | Approve and Send SED                                                                     | ✓                     | ✓                  |                        |           |          |                |            |            |
| Management Case Assignment | Upload/Delete/ Send/ Download Medical attachments                                        |                       |                    |                        |           |          | ✓              |            |            |
| Management Case Assignment | View VIPS                                                                                |                       |                    |                        |           |          |                | ✓          |            |
| Management Case Assignment | Change Case Metadata                                                                     | ✓                     | ✓                  | ✓                      |           |          |                |            |            |
| Management Case Assignment | Manual case archiving                                                                    | ✓                     | ✓                  |                        |           |          |                |            |            |
| Management Case Assignment | Manual case unarchiving                                                                  | ✓                     | ✓                  |                        |           |          |                |            |            |
| Management Case Assignment | Set/clear alarms                                                                         | ✓                     | ✓                  | ✓                      |           |          |                |            |            |
| Management Case Assignment | View case metadata (subject, participants, assignments, document list, alarms, comments) | ✓                     | ✓                  | ✓                      | ✓         | ✓        | ✓              | ✓          | ✓          |
| Management Case Assignment | Download/send regular attachments                                                        | ✓                     | ✓                  | ✓                      | ✓         | ✓        |                |            |            |
| Management Case Assignment | Upload/delete regular attachments                                                        |                       | ✓                  | ✓                      |           |          |                |            |            |
| Management Case Assignment | Add/delete comments                                                                      | ✓                     | ✓                  | ✓                      | ✓         | ✓        |                |            |            |
| Audit                      | View Audit                                                                               | ✓                     |                    |                        | ✓         |          |                |            |            |

<!-- image -->

## Annex II -Password management

## Password management

PS AC 109 - Password Length - Passwords must be sufficiently long so that they are difficult to guess or determine from the encrypted form. Passwords must have a minimal length of 8 characters. A minimal length of 10 characters is recommended.

PS AC 11 - Password Composition - Passwords should consist of at least three groups of characters out of mixed numbers, small and capital letters and symbols.

PS AC 12 - Password Storage - Passwords must be stored in such a way that no one, not even the System Administrator, may know them. Passwords must be stored in an encrypted form on databases, files, etc.

PS AC 13 -Password Generation/Choice - The system should automatically ensure that users follow good security practice in the selection of passwords.

PS AC 14 - Password Use - Users and system administrators must follow good security practice in the selection and use of passwords.

PS AC 15 - Frequency of Password Change - There must be a system provision for passwords to be changed frequently.

PS AC 16 - Password Distribution - Passwords must be distributed securely.

PS AC 17 - Users must be authenticated before being provided with access to the EESSI system. A single password is considered sufficient, although stronger System.

<!-- image -->

<!-- image -->

## Annex III -List of applicable EESSI security statement

For illustration of the consistency between the EESSI Communications Security Standard and the EESSI Security Policy, we list below the complete set of applicable security Policy statements that were already defined by the EESSI Security Policy.

The listed Security Policy statements [PS] are enclosed in a box and have the following format:

## PS &lt;id&gt; &lt;n&gt;.&lt;m&gt;

## Where:

- &lt;id&gt; is the abbreviation of the Security Policy to which it refers;
- &lt;n&gt; is the sequential number of the security statement inside that sections;
- &lt;m&gt; refers to related requirements itemised at lower level.

PS  22 -  The  EESSI  servers  and  network  must  be  physically  protected  from unauthorized access, damage, and interference.

## Remote support

PS 24 - If the system is supported remotely:

- The communication channel shall be encrypted.
- Two-factor authentication (something you know &amp; something you have) should be used for logging into the EESSI server/device.

## Data sender/receiver authentication and non-repudiation

PS 25 -  The  origin  of  messages  (SEDs) must be  authenticated.  Further  to  basic message  origin  identification (organization identifier), a secure  authentication mechanism shall be present to authenticate the sender.

PS  26 -  The  repudiation  of  messages  (SEDs)  passed  over  the  network shall be prevented. Non-repudiation techniques shall be implemented

## Data Confidentiality over Networks

PS 28 - The confidentiality of non-public information in transit over networks shall be protected.

## Data Integrity over Network

PS 29 - The integrity checking, error correction and reporting mechanisms inherent in the communication protocol must be used, if adequate.

<!-- image -->

PS 30 - Possible connection with the Internet must be secured.

## Network access control

PS 32 - The access to networks must be strictly controlled.

## Network operation management

PS 33 - The network must be managed and monitored for all faults on the network such as intrusions and abnormalities at all times.

PS 36 -Segregation  of  Duties -  The  segregation  of  duties  and  responsibilities should be implemented to reduce the risk of accidental or deliberate system misuse

PS  44 -Protection  from  Malicious  Code -  Controls must be  implemented  to prevent the introduction of malicious software into the IT system and to remove it when detected.

PS 45 -A standard describing processes and measures to counter malicious code should exist

PS 46 - An Access Control policy must exist and be implemented.

<!-- image -->

## Annex III -RINA Technologies covered by CIS benchmarks

Hereafter,  the  list  of  existing  CIS  benchmarks  that  may  be  relevant  for  RINA components depending on the deployment environment:

- Operating Systems:
- o Microsoft:
- Windows Server
- Windows Desktop
- o Linux:
- Debian
- Ubuntu
- Red Hat
- SUSE
- CentOS
- Distribution Independent Linux
- Network devices:
- o Cisco
- o Palo Alto Networks
- Server Software:
- o Microsoft IIS
- o VMware
- o Apache Tomcat
- o Apache HTTP Server
- o Docker
- Cloud Providers:
- o Amazon Web Services
- o Microsoft Azure

## Annex IV -Case Study : Web Application Firewall

A case study has been made for the RINA component using the ModSecurity module of Apache. Note that this module is initially loaded with Apache in the RINA package, one can import the OWASP ModSecurity Core Rule Set (CRS) in order to protect against several common attacks such as SQL injections, Cross Site Scripting etc.

The enabling of the ModSecurity WAF in our testing environment showed that several identified RINA risks were mitigated, therefore, not feasible anymore. E.g. DOS attacks, XSS injections, etc.

However, the rules applied to the WAF are sometimes too restrictive for the applications and can break some legitimate functionalities.  Therefore,  rules  have  to  be  carefully adapted/modified for the applications to work which can require additional efforts ( see below ).  Various  tutorials  exist  online  helping  to  configure  ModSecurity,  we  do recommend the following official wiki in order to install/configure/enable ModSecurity:

- https://github.com/SpiderLabs/ModSecurity/wiki

## Example of rules to be fine-tuned:

The list below provides some examples of URLs/functionalities, where the applied rules were too restrictive:

- ' /eessiCas/login?service=../portal/cas/cpi ' and
- ' /eessiRest/login/cas?ticket=abcdef1234 &amp;serviceId=../portal/cas/cp i' where a path traversal attack is detected.
- PUT and DELETE methods are not allowed by default policy. This may block some requests.
- …

<!-- image -->