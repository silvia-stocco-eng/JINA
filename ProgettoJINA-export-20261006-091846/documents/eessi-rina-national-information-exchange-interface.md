---
unique-name: eessi-rina-national-information-exchange-interface
display-name: EESSI   RINA   National Information Exchange Interface (NIE)   rev02
category: GENERAL
tags: ec
---

<!-- image -->

<!-- image -->

## EESSI - RINA National Information Exchange Interface (NIE)

Solution / Application Architecture EESSI 2020 -rev02

Employment, Social Affairs andInclusion

## Table of Contents

<!-- image -->

| 1 EESSI national information exchange overview................................................ 6                 | 1 EESSI national information exchange overview................................................ 6                 | 1 EESSI national information exchange overview................................................ 6                 | 1 EESSI national information exchange overview................................................ 6             |
|------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|
| 2 Common API concepts and features ...............................................................               | 2 Common API concepts and features ...............................................................               | 2 Common API concepts and features ...............................................................               |                                                                                                              |
|                                                                                                                  |                                                                                                                  |                                                                                                                  | 8                                                                                                            |
| 2.1                                                                                                              | 2.1                                                                                                              | User authentication ...............................................................................              | 8                                                                                                            |
| 2.2                                                                                                              | 2.2                                                                                                              | User authorization                                                                                               | ................................................................................. 8                          |
| 2.3                                                                                                              | 2.3                                                                                                              | Audit trail .............................................................................................        | 8                                                                                                            |
| 2.4                                                                                                              | 2.4                                                                                                              | Exception management..........................................................................                   | 8                                                                                                            |
| 3 Functions and Use Cases...............................................................................         | 3 Functions and Use Cases...............................................................................         | 3 Functions and Use Cases...............................................................................         | 9                                                                                                            |
| 3.1                                                                                                              | National information exchange function....................................................                       | National information exchange function....................................................                       | 9                                                                                                            |
| 3.1.1                                                                                                            | 3.1.1                                                                                                            | Configure service                                                                                                | ...........................................................................10                                |
| 3.1.2                                                                                                            | 3.1.2                                                                                                            | Load from national application                                                                                   | .........................................................11                                                  |
| 3.1.3                                                                                                            | 3.1.3                                                                                                            | Store to national application                                                                                    | ............................................................11                                               |
| 4 Behaviour ..................................................................................................14 | 4 Behaviour ..................................................................................................14 | 4 Behaviour ..................................................................................................14 |                                                                                                              |
| 4.1                                                                                                              | Sequence diagrams                                                                                                | Sequence diagrams                                                                                                | ..............................................................................14                             |
|                                                                                                                  | 4.1.1 Exchange case information with national application...........................15                           | 4.1.1 Exchange case information with national application...........................15                           |                                                                                                              |
|                                                                                                                  | 4.1.2 Exchange document information with national application ...................16                              | 4.1.2 Exchange document information with national application ...................16                              |                                                                                                              |
| application                                                                                                      | 4.1.3 Exchange notification & business' exception information with                                               | 4.1.3 Exchange notification & business' exception information with                                               | national .................................................................................................17 |
| 4.2                                                                                                              | State machine diagrams........................................................................17                 | State machine diagrams........................................................................17                 |                                                                                                              |
| 4.2.1                                                                                                            | 4.2.1                                                                                                            | Case state machine                                                                                               | ........................................................................17                                   |
| 4.2.2                                                                                                            | 4.2.2                                                                                                            | Document sender state machine ......................................................18                           |                                                                                                              |
| 4.2.3                                                                                                            | 4.2.3                                                                                                            | Document receiver state machine                                                                                  | ....................................................20                                                       |
| 4.2.4                                                                                                            | 4.2.4                                                                                                            | Subdocument sender state machine                                                                                 | .................................................20                                                          |
| 4.2.5                                                                                                            | 4.2.5                                                                                                            | Subdocument receiver state machine                                                                               | ...............................................21                                                            |
| 5 Service contract..........................................................................................22   | 5 Service contract..........................................................................................22   | 5 Service contract..........................................................................................22   |                                                                                                              |
| 5.1 5.1.1                                                                                                        | 5.1 5.1.1                                                                                                        | hasCaseListener.............................................................................22                   |                                                                                                              |
| 5.1.2                                                                                                            | 5.1.2                                                                                                            | hasDocumentListener                                                                                              | .....................................................................22                                      |
| 5.1.3                                                                                                            | 5.1.3                                                                                                            | hasNotificationListener....................................................................23                    |                                                                                                              |
| 5.1.4                                                                                                            | 5.1.4                                                                                                            | fireCaseEvent ................................................................................23                 |                                                                                                              |
| 5.1.5                                                                                                            |                                                                                                                  | fireNotificationEvent                                                                                            | .......................................................................24                                    |
| 5.1.6                                                                                                            |                                                                                                                  | fireDocumentEvent.........................................................................24                     |                                                                                                              |
| 5.2 Structure of the events metadata...........................................................25                | 5.2 Structure of the events metadata...........................................................25                | 5.2 Structure of the events metadata...........................................................25                |                                                                                                              |
| 5.2.1                                                                                                            | 5.2.1                                                                                                            | fireCaseEvent                                                                                                    | ................................................................................25                           |
| 5.2.2                                                                                                            | 5.2.2                                                                                                            | fireDocumentEvent.........................................................................25                     |                                                                                                              |
| 5.2.3                                                                                                            | 5.2.3                                                                                                            | fireNotificationEvent                                                                                            | .......................................................................27                                    |
| 5.2.4                                                                                                            | 5.2.4                                                                                                            | organisation                                                                                                     | ..................................................................................28                         |
| 5.2.5                                                                                                            | 5.2.5                                                                                                            | creator..........................................................................................28              |                                                                                                              |
| 5.2.6                                                                                                            |                                                                                                                  | subject                                                                                                          | .........................................................................................28                  |
| 5.2.7                                                                                                            | 5.2.7                                                                                                            | searchMetadata                                                                                                   | .............................................................................28                              |

6

7

8

9

5.2.8

5.2.9

5.2.10

5.2.11

5.2.12

5.2.13

5.2.14

5.2.15

5.2.16

5.2.17

5.2.18

5.2.19

5.2.20

5.2.21

5.2.22

5.2.23

5.3

<!-- image -->

case participant .............................................................................  29

case assignment ............................................................................  29

version .........................................................................................  29

validation  ......................................................................................  29

conversation  ..................................................................................  29

attachment  ....................................................................................  29

caseInfo  ........................................................................................  30

document  ......................................................................................  30

extendedProperties ........................................................................  31

assignmentRequest ........................................................................  31

failureReason  .................................................................................  31

contactMethod ...............................................................................  31

address  .........................................................................................  31

actor ............................................................................................  31

userMessage .................................................................................  32

conversation participant  ..................................................................  32

Main Changes in the events metadata between RINA EESSI 2019 and RINA EESSI

2020 releases  ................................................................................................  32

5.3.1

fireCaseEvent ................................................................................  32

5.3.2

5.3.3

fireDocumentEvent  .........................................................................  32

fireNotification event ......................................................................  33

Data contract .............................................................................................  34

6.1

Data model .........................................................................................  34

6.2

6.3

6.4

6.5

6.6

6.7

EventType  ...........................................................................................  34

CaseEventType ....................................................................................  34

DocumentEventType  .............................................................................  35

EventSource ........................................................................................  35

PropertyType  .......................................................................................  36

BatchMetadata  .....................................................................................  36

Fault contract  .............................................................................................  37

Illustrative sample of a basic implementation .................................................  38

NIE configuration  ........................................................................................  39

3

<!-- image -->

## Document Control Information

| Document Control                     | Value                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|--------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Project Title                        | Electronic Exchange of Social Security Information (EESSI)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Document Title                       | EESSI - RINA - National Information Exchange Interface (NIE)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| Document Category                    | Solution / Application Architecture                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Revision                             | rev02                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Component Version                    | -                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Last Publication Date                | 13/12/2021                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Document Status                      | Final                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Sensitivity (TLP) Distribution terms | Traffic Light Protocol (TLP) = ' GREEN ' The distribution of this document is done strictly in line with the Traffic Light Protocol (TLP) established by the European Commission's note AC 790/15 REV for the EESSI project documentation. In line with the note AC 790/15 REV, this document is labelled as TLP = 'Green'. Therefore, it can be circulated widely within the EESSI community. However, the document or the information herein may not be published or posted on the Internet, nor released outside of the EESSI community. |
| Connected/Embedded Files             | None                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|                                      | European Commission, DG EMPL A4, EESSI ARCH/RINA                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| Authors                              |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Revised by                           | European Commission, DG EMPL A4, EESSI QA                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |

## Document history

| Project Milestone / Component version   | Date       | Changes/Corrections Description                                                                                                                                                                                                                                                                                                                              |
|-----------------------------------------|------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| EESSI 2019 RINA 5.6.2                   | -          | Update RINIE document template                                                                                                                                                                                                                                                                                                                               |
| EESSI 2019 RINA 5.6.2                   | -          | Updated port reference of RINIE service (page 35)                                                                                                                                                                                                                                                                                                            |
| EESSI 2020 RINA 6.2.1                   | 18/12/2020 | Update the content to new RINA developments and architecture                                                                                                                                                                                                                                                                                                 |
| EESSI 2020 RINA 6.2.1                   | 18/12/2020 | Replace the general introductory description to be aligned with 'EESSI - RINA - Architecture Overview' (Chapter 1)                                                                                                                                                                                                                                           |
| EESSI 2020 RINA 6.2.1                   | 18/12/2020 | Replace the NIE configuration/implementation screenshots with new ones from the New RINA Portal                                                                                                                                                                                                                                                              |
| EESSI 2020 RINA 6.2.5 (rev01)           | 9/4/2021   | Cosmetic changes on section enumerations. Minor clarifications in section 4.2.1.                                                                                                                                                                                                                                                                             |
| EESSI 2020 RINA 6.2.5 (rev01)           | 9/4/2021   | Add the chapter '5.2 - Structure of the events metadata' where the detailed description of the metadata fields for all NIE events is provided.                                                                                                                                                                                                               |
| EESSI 2020 RINA 6.2.5 (rev01)           | 9/4/2021   | Add the chapter '5.3 - Main Changes in the events metadata between RINA EESSI 2019 and RINA EESSI 2020 releases'.                                                                                                                                                                                                                                            |
| EESSI 2020 (rev02)                      | 13/12/2021 | The notification events list was updated by adding 3 cases (chapters 3.1.3 & 4.1.1). Minor clarifications regarding sections 5.1.1 & 5.1.2. Minor clarifications regarding the 'creator' NIE JSON element in document events (chapter 5.2.5). Minor clarifications regarding the ' business exception ' NIE JSON element in document events (chapter 5.1.3). |

<!-- image -->

<!-- image -->

## 1 EESSI national information exchange overview

Part  of  the  National  Institutions  Domain,  RINA  (Reference  Implementation  for  National Applications)  consists  in  a  collection  of  infrastructure  and  communication  services, foundation, repository and publishing services, business, integration and user interface services which will provide for clerks and their organisations the tools to implement the International  Protocol  of  Data  Exchange  based  on  Structured  Electronic  Documents  in Social Security belonging to European Community Member States and Associated States.

Figure 1 - Overview of RINA interfaces and layers

<!-- image -->

RINA is based on 4 layers which are built one on top of the other, plus the CAS module:

- Technical Message Services (TMS) provide the mechanism for sending/receiving technical messages to the Access Point. It works based on the protocol ebMS3.0 AS4 profile.  It  is  an  internal  layer  and  cannot  be  used  by  third  parties,  being  its unique client the RINA BMS.
- Business  Messaging  Services  (BMS) -  provide  a  reusable  component  for  sending business messages to the Access Point via the TMS layer. These services provide the translation (business message to technical message and vice versa), transformation (converting  IDs  to  GUIDs),  validation  and  signing  of  the  business  messages  for correct exchange with the EESSI environment, and the correct reception of messages from  other  institutions.  It  offers  the  BMI  WS  interface  making  available  the integration of third-party applications to the EESSI ecosystem.
- Case Processing Services (CPS) -provide a stateful component built on top of the Business Messaging Services that manage cases in a structured manner taking care of all the issues regarding case flow, documents, notifications, user management and provides two interfaces for external access (NIE and CPI).

<!-- image -->

- Portal -provides an UI build on top of the Case Processing Services (CPS) having administration consoles and case Processing modules;
- CAS  Authentication  Server -the  SSO  (Single  Sign  On)  server  providing  the authentication to users/clients requesting to use a service.

The  scope  of  this  document  is  to  provide  a  specification  document  for  the  National Information Exchange Interface, part of the Case Processing Services (CMS) layer.

## Here is a short description of how this document is structured:

- Interface overview -this chapter, an introduction to what this interface is about, its place and why it is needed;
- Functions and use cases -a presentation of high level functions and use cases that drive this service component;
- Sequence  diagrams -behavioural  diagrams  that  describes  the  flow  between components;
- Service interfaces -a description of the interfaces provided;
- Service contract -a description for all the methods exposed through the interfaces;
- Data contract -the data model used for this service;
- Fault contract -the exception model used for this service;
- Samples -some samples that shows how to use this library;
- NIE configuration -illustrative example of the configure events options.

This software component provides a JAVA interface that allows national applications  to subscribe for specific events during the life cycle of a case or a document together with the notifications and business exceptions associated to them. When that event happens, the national application is notified together with all the information details regarding the state of the case, or document, or with the notifications or business exceptions associated with the former.

7

## 2 Common API concepts and features

## 2.1 User authentication

N/A

## 2.2 User authorization

N/A

## 2.3 Audit trail

As  the  National  Information  Exchange  works  in  close  collaboration  with  the  Case Management Interface. Thus, all information related to its audit trail can be found in the EESSI - RINA - Case Processing Interface (CPI) document. Full information on RINA audit trail architecture is available in the EESSI -RINA -Architecture Overview document . Both documents are published and available at the RINA Architecture Documentation Confluence space:

https://citnet.tech.ec.europa.eu/CITnet/confluence/display/EESSI/RINA++Architecture+ Documentation

## 2.4 Exception management

This section explains how the library manages unexpected behaviour.

When an error occurs during an API call the library will throw a Java exception that is defined in the Fault contract.

There are two generic types of exception that might occur

- Case processing exception -this kind of exception is thrown by the member states during the national application case handling when case processing cannot be done
- Document processing exception -this kind of exception is thrown by the member states during the national application document handling when document processing cannot be done

More information related on how RINA deals with Error and Exception management as well as  its  logging  architecture  can  be  found  in  the  previously  mentioned EESSI -RINA -Architecture Overview document

<!-- image -->

## 3 Functions and Use Cases

The national information exchange function is part of a broader set of national functions.

The national part of RINA supporting functions provide the system functionalities that will need to be provided at Member State level in order to complete the functioning of the RINA.

Figure 2. RINA Supporting Functions

<!-- image -->

This document specification is focused on the national information exchange function.

Figure 3. National Information Exchange Function

<!-- image -->

## 3.1 National information exchange function

The  national  information  exchange  function  allows  RINA  to  interact  with  national applications to exchange or receive information in the context of case management (e.g., for completing SEDs or exchanging SEDs with national systems).

The EESSI side is in charge to call the National Application for all the important events from the case or document (individual or in batch) lifecycle together with the notifications, business exception generated and provide the relevant information (for example the actual SED part of a document).

It will be up to the MS to choose the way to implement the processing (for example store the SED along with other national useful information or give back an updated SED filled in with information that would be otherwise hard or cumbersome for a clerk to fill in manually)

<!-- image -->

<!-- image -->

The following figure shows the use case diagram for this function:

Figure 4. National information exchange use case

<!-- image -->

## 3.1.1 Configure service

## Description

The  user  must  be  able  to  configure  the  national  information  exchange  EESSI  side component so that it can talk to any member state implementation.

- At configuration time, the RINA administrator uploads the member state implementation into RINA;
- The RINA system scans the library uploaded for the needed pieces to operate on and loads them all.

Figure 5 - Administrative Portal - NIE implementation configuration

<!-- image -->

<!-- image -->

Related to Figure 5, the Administrator has to upload the JAR file with the implementation. After this the class name which shall be instantiated shall be completed with the use of Update the NIE settings as described in the ' EESSI -RINA - Case Processing Interface (CPI) ' and 'EESSI RINA - Case Processing (CPI) -Reference ' documents .

## 3.1.2 Load from national application

## Description

The clerk may have a lot of information to fill in the SED before sending it, so there should be an automatically way to achieve this shortcoming of data re-entry. In order to avoid redundancy of the information introduced by the clerk, which were already in the NA, at specified times (e.g., when a document has been initialised, before saving a document,  etc.)  the  Guidance  Service,  triggers  specific  events  by  which  the  NIE  is retrieving relevant information from NA and provide it to the Guidance Service for further use. This use case is also useful for the batch documents. Through the import function a clerk can import a file, containing a batch of items (e.g. claims), and the individual items can be enriched automatically with needed / relevant information through NIE. As an illustrative example the below use case covers this issue and describes how the EESSI system interacts with the National Application so that it can read the necessary

information from the member state backend.

- The clerk prepares to send a new SED to another institution (for example he wants to send a pension P2000 SED);
- The clerk presses the "Create P2000" button;
- The system builds the parameter context by putting the relevant information (user identification, case identification, correlation information, all the document metadata needed to track down the document);
- The system calls  the  national  application  implementation  handing  over  the  event source  information  (event  just  happened,  business  use  case,  SED  type)  and  the context built at the previous step;
- The national application receives the event source and the information associated with the document and does whatever processing it needs to update the SED with all the fields it can automatically find in its backend system(s);
- The context is returned back to the RINA system and the SED updated with as many fields as the national application could find;
- The clerk may fill in more fields in the SED then sends the SED.

## Support API

5.1 National information exchange client (NIE client)

## 3.1.3 Store to national application

## Description

<!-- image -->

The member states have their own systems that need to be informed when specific events happen in the case management engine and a generic way of letting know about it should be supported. The national applications should be aware about all important events from the case and document lifecycle including the notifications sent between the parties and the Business exceptions occurring during different transactions. For  the  case  scenario,  the  following  events  could  be  notified  along  with  all  the  case information:

- When a case was opened locally;
- When a new case was received from the counter party;
- When a case was closed locally;
- When a case was reopened;
- When a case was deleted;
- When the case was forwarded to a counter party and removed from the local process owner;
- When a case was removed as a consequence of receiving a X006 document;
- When a case was unarchived;
- When a participant is removed from a case.

For  the  document  scenario,  the  following  events  should  be  notified  along  with  all  the document information:

- When the SED has been initialized;
- When the SED is newly created;
- When the SED is updated;
- When the SED is sent;
- When the SED is deleted;
- When the SED is invalidated;
- When the SED is received.

Notifications and Business exceptions can be configured in the Notifications Centre and consists of the following type:

- Case SEDs Automatically Sent to Participant
- Approval for Sending Required for SED
- SED not matching Case
- A new SED Arrived
- Your Alarm Expired
- Request to Assign Case
- Request to Assign Case Rejected
- Request to Assign Accepted
- Case Unassigned

12

- Case Assigned
- An Updated SED Arrived
- SED Delivered
- A New Case Arrived
- SED Failed to be Delivered
- Case Automatically Closed
- Archiving Case Exception
- Archiving Case Problem
- Case Assignment Exception
- Business Exception - Case Forwarded
- Business Exception - Attachment failed antimalware checking
- Business Exception - Case Closed
- Business Exception - Unknown Cause
- Business Exception - Invalid Business Signature
- Business Exception - SED in Wrong Sequence
- Business Exception - SED update without Create
- Business Exception - Case Removed
- Business Exception - Case Missing

Additionally, for the batch document scenario, the following events should be notified along with all the document information:

- When a part of a batch SED has been initialized;
- When a part of a batch SED is newly created;
- When a part of a batch SED is updated;
- When a part of a batch SED is deleted;
- When a batch of parts of a batch SED is created;
- When a batch of parts of a batch SED is received.

Finally for different type of RINA's notifications and business exceptions, the admin can choose if they want that these events should be notified al ong with the full notification's details.

## Support API

- 5.1 National information exchange client (NIE client)

<!-- image -->

## 4 Behaviour

## 4.1 Sequence diagrams

The sequence diagrams show the interaction between the EESSI case management system and the national applications when exchanging information about a case or a document.

All the diagrams have the following internal components:

- Guidance Service -this component implements the national information exchange processing part and it does this by having direct contact with the case management system and with the national information exchange client;
- National  Information  Exchange  Client -this  component  is  used  for  registering national application clients interested in receiving notifications about various events that get fired in the case management engine during the life cycle of a case or a document;
- National  Information  Exchange  API  (ICD5)  at  the  National  Application -this component is actually the member state's national application that registers itself for case management event  and handles (loads, store, all kind of processing) the events triggered in the case engine;

Next are presented the steps that need to be performed so that the national application receives a notification:

- The  Guidance  Service  triggers  the  hasCaseListener  /  hasDocumentListener  / hasNotificationListener methods which checks if there is any applicable situation for which needs to trigger the fireCaseEvent / fireDocumentEvent / fireNotificationEvent;
- For a case event, the list of business use cases is also provided so that notifications are sent for each case event - business use case combination;
- For a document event, the list of business use cases and the SED types are provided so that document notifications are sent for each document -business use case -SED type combination;
- For the notification event, the full notification's detail s are provided.
- When an event happens, the Guidance Service checks whether there is any listener registered. No case information context will be loaded if no listener is registered.

<!-- image -->

<!-- image -->

## 4.1.1 Exchange case information with national application

## Diagram

Figure 6. Sequence diagram - Exchange Case Information with National Application

<!-- image -->

## Description

The sequence diagrams show the interaction between the EESSI case management system and the national applications when exchanging information about a case.

The following events can be triggered for this sequence diagram:

- When the case is opened;
- When the case is received from the counter party;
- When the case is closed;
- When the case is reopened;
- When the case is deleted;
- When the case is forwarded to a counter party and removed from the local process owner;
- When the case is removed as a consequence of receiving a X006 document;
- When the case is unarchived;
- When a participant is removed from the case.

Once the event is triggered the Guidance Service uses the National Information Exchange Client to inform about the event source and the case context that is passed as an input payload map. For the case scenario, the payload map has only one entry, namely the RESTCase object that contains all the details needed for a case.

The  National  Information  Exchange  Client  calls  the  NA,  and  provides  the  relevant information related to the current event and the NA needed data.

In the 'Call' method, the national application does all the processing it needs to fulfil its requirements  (store  the  case,  users  related  to  it,  etc.).  After  all  the  member  state processing is done it may return the updatedPayloadMap.

<!-- image -->

## 4.1.2 Exchange document information with national application

## Diagram

Figure 7. Sequence diagram - Exchange Document Information with National Application

<!-- image -->

## Description

This sequence diagram shows the interaction between the EESSI case management system and the national applications when exchanging information about a document.

## The following events can be triggered for this sequence diagram:

- When the document has been initialized;
- When the document is newly created;
- When the document is updated;
- When the document is sent;
- When the document is deleted;
- When the document is cancelled;
- When the document is received;
- When a part of a batch document has been initialized;
- When a part of a batch document is newly created;
- When a batch of parts of a batch document is created;
- When a part of a batch document is updated;
- When a part of a batch document is deleted;
- When a batch of parts of a batch document is received;

Once the event is triggered the Guidance Service uses the National Information Exchange Client to inform about the event source and the case context that is passed as an input payload map. For the document scenario, the payload map has two entries: the first entry is the Document Metadata that contains all the metadata for the document (what case is related to, the document type, who created, etc.) and the second entry is the actual SED payload.

<!-- image -->

The  National  Information  Exchange  Client  calls  the  National  Information  Exchange  API (ICD5) and provides the relevant information  related to the current  event and the NA needed data. In the method, the national application does all the processing it needs to fulfil its requirements (store the case, some users about it, etc.).

After all the member state processing is done it returns the updatedPayloadMap that in some cases (for example on initialized) should have lot of fields updated for the SED.

<!-- image -->

## 4.1.3 Exchange  notification  &amp;  business'  exception  information  with  national application

Depending on the option (generateNIE or not) chosen by the admin for different type of notifications &amp; Business exceptions in the Notification Centre, the system will share these details with the National Application.

## 4.2 State machine diagrams

The  state  machine  diagrams  presented  below  are  also  described  in  the  EESSI  Case Processing  Interface  (CPI)  specification  document  (same  chapter  4  Behaviour -state machines)  as  these  views  are  important  in  understanding  under  what  conditions information is exchanged with the national application.

## 4.2.1 Case state machine

The case state machine is used to keep track of the case state.

<!-- image -->

## Figure 8. Case state machine

As illustrate in the Figure 8 above, during the transition a specific event is triggered so that case information at that moment is sent to the national application:

- Open -In this state the sender party (case owner) creates the case and the receiver party (counterparty) opens the case for the first time. After all the work is done on this  case  the  involved  participants  may  close  it.  If  other  participant  should  be responsible for this case from now on, an existing participant forwards the case. If the case owner is not interested anymore in the case he deletes the case. The case can be deleted if no SEDs have been exchanged. When deleted, a case is removed from the system and it has no specific status. This action cannot be reversed and the Case cannot be undeleted.
- Closed -  The participant closed the case, from this state the case can be opened again; also un-archiving a case which was closed will bring the case from archived back to the closed status;
- Removed - The case has been forwarded to another participant or own participant has been removed and is no longer part of the case; in the latter case the case will be read-only;
- Archived -The case is archived either automatically by the system following normal archiving  process  (following  case  closing,  case  forwarding,  or  case  removed participant according to the defined timers for respective case's BUC Type) , or either manually by the user.

## 4.2.2 Document sender state machine

The document state machine is used to keep track of the document state on the sender side.

Figure 9. Document State Machine

<!-- image -->

Note: Being physically deleted in the state machine is not reflected in the state machine. This can be represented in UML with a terminated event; for the diagram clarity this was not represented.

<!-- image -->

<!-- image -->

As illustrate in the Figure 9 above, during the transition a specific event is triggered so that document  information  from  that  particular  moment  is  exchanged  with  the  national application:

- Empty
- o This is the Empty state where the document metadata has just been initialized, Create action for the document is available and it has no content. Users with create rights can see the corresponding action Create .
- o When Create  action in  the UI is  triggered, Initialise  Document  Event described  in  the  document  event  types  DocumentEventType .  Triggering Create Action in UI does not change the status of the document, because it only retrieves the initial document . The real Create Action in RINA is only executed in UI if save button is pressed.
- o By executing directly RINA Create Action by using RINA API, not portal, the event Initialise Document Event will not be triggered. The document content will be saved directly and event NewDocument will be triggered.
- New
- o When save button in the UI is pressed or the create action is executed directly using RINA API, the document will go to state New . In RINA Portal this status is displayed as Draft . Then the NewDocument event is triggered.
- o NewDocument event described in the document event types -DocumentEventType ;
- o Document  in New state  can  be  updated  several  times.  In  RINA  portal  the document status is displayed as Draft until the document is sent or deleted. In each of these updates an event UpdateDocument will be triggered. The document will not change status.
- Deleted
- o Before a document is sent, while in status New, it may be deleted. A deleted document  is  removed  from  the  system  and  a  new  Create  Action  for  same document is available. When a document is deleted a DeleteDocument event is triggered.
- o The DeleteDocument event described in the document  event types -DocumentEventType ;
- Sent
- o When  the Send action  is  executed,  document  is  sent,  from  this  state  the document can be updated, cancelled or forwarded depending on the BUC. The document goes to status Sent. A SendDocument event is triggered.
- o The SendDocument event described in the document event types -DocumentEventType ;
- Updated
- o Once a document is in status Sent, depending on the BUC, may be updated. If it is updated the document will do to status Active in this status the document can be updated until document is cancelled. In RINA Portal the status will be displayed as Updated . An UpdateDocument event will be triggered every time the action Update is executed.
- o The UpdateDocument event described in the  document  event  types -DocumentEventType ;
- Cancelled

<!-- image -->

- o A Sent document may be cancelled if AD\_BUC\_06\_Subprocess-Invalidate\_SED is required for that document. If the document is cancelled it goes to status Cancelled and event CancelDocument is triggered. This is the final state.
- o The CancelDocument event described in the  document  event types -DocumentEventType.

## 4.2.3 Document receiver state machine

The document state machine is used to keep track of the document state on the receiver side.

Figure 10. Document receiver state machine

<!-- image -->

As illustrated in the Figure 10 above, during the transition a specific event is triggered so that document information from that particular moment is exchanged with the national application:

## · Received

- o When a document is  received  from  another  participant  a ReceiveDocument event is triggered.
- o The ReceiveDocument event  is  described  in  the  document  event  types  DocumentEventType;

## · Updated

- o Once a document is in status Received, depending on the BUC, new versions of the  same  document  may  be  received.  An UpdateDocument event  will  be triggered every time a newer version of a received document is received.
- o The UpdateDocument event described in the  document  event  types -DocumentEventType ;

## · Cancelled

- o A received document may be cancelled if AD\_BUC\_06\_Subprocess-Invalidate\_SED is required for that document. If the document is cancelled it goes to status Cancelled and event CancelDocument is triggered. This is the final state.
- o The CancelDocument event described in the document  event  types -DocumentEventType.

## 4.2.4 Subdocument sender state machine

This applies only to bulk documents that may have attached subdocuments. Those for documents  don't  have  a  status  and  the  associated  NIE  events  depend  on  the  action performed on them. Based on this actions:

## · Add Subdocument

- o A new subdocument is added to a bulk document. An event NewSubdocument is  triggered.  Adding  subdocuments  is  only  allowed  for  documents  in  status New .

<!-- image -->

- o The NewSubdocument event  described  in  the  document  event  types -DocumentEventType;

## · Update Subdocument

- o Any update on an already added subdocument triggers a event UpdateSubdocument event.
- o The NewSubdocument event  described  in  the  document  event  types -DocumentEventType;

## · Delete Subdocument

- o When a subdodocument is deleted an DeleteSubdocument event is triggered . Removing subdocuments is only allowed for documents in status New .
- o The DeleteSubdocument event  described  in  the  document  event  types  DocumentEventType;

Warning : The action Import Subdocuments triggers a corresponding event, NewSubdocument if  new or UpdateSubdocument if existing per each imported subdocument.

## 4.2.5 Subdocument receiver state machine

This applies only to bulk documents that may have attached subdocuments. Those for documents  don 't  have  a  status  and  the  associated  NIE  events  depend  on  the  action performed on them. Based on this actions:

## · Receiving a new Subdocument

- o A new subdocument is added to a bulk document. An event ReceiveDocumentBatch is triggered.
- o The ReceiveDocumentBatch event  described  in  the  document  event  types  DocumentEventType;

## 5 Service contract

## 5.1 National information exchange client (NIE client)

The NIE Client is used for receiving notifications about various events that get fired in the case management engine during the life cycle of a case or a document.

Before  any  call  to  the  fireCaseEvent,  fireDocumentEvent  or  fireNotificationevent,  the hasCaseListener, the hasDocumentListener and the hasNotificationListener methods are triggered  in  order  to  monitor  if  there  are  any  cases,  documents  or  notifications  to  be updated.

At a new NIE client implementation it will be up to the MS to choose the way on how the NIE Client configurations will be managed.

Figure 11. National Information Exchange interface

<!-- image -->

## 5.1.1 hasCaseListener

| Name              | hasCaseListener                                                                                                                                                                                                                             |
|-------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Description       | Checks whether there is a listener registered for a business use case and business use case version combination                                                                                                                             |
| Preconditions     | N/A                                                                                                                                                                                                                                         |
| Input Parameters  | 6.3 CaseEventType - The case event type for which the listener is registered for String - The business use case for which the listener is registered for String - The version of business use case for which the listener is registered for |
| Output Parameters | N/A                                                                                                                                                                                                                                         |
| Exceptions        | N/A                                                                                                                                                                                                                                         |

## 5.1.2 hasDocumentListener

| Name        | hasDocumentListener                                                                                                          |
|-------------|------------------------------------------------------------------------------------------------------------------------------|
| Description | Checks whether there is a listener registered for a document event, business used case, SED type combination. In the default |

<!-- image -->

<!-- image -->

|                   | implementation the business use case and the business use case version are ignored.                                                                                                                                                                                                                            |
|-------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Preconditions     | N/A                                                                                                                                                                                                                                                                                                            |
| Input Parameters  | DocumentEventType - The document event type for which the listener is registered for String - The business use case for which the listener is registered for String - The version of business use case for which the listener is registered for String - The SED type for which the listener is registered for |
| Output Parameters | N/A                                                                                                                                                                                                                                                                                                            |
| Exceptions        | N/A                                                                                                                                                                                                                                                                                                            |

## 5.1.3 hasNotificationListener

| Name              | hasNotificationListener                                                                                                                              |
|-------------------|------------------------------------------------------------------------------------------------------------------------------------------------------|
| Description       | Checks whether there is a listener registered for notifications. It is associated to the notifications and business exceptions RINA functionalities. |
| Preconditions     | N/A                                                                                                                                                  |
| Input Parameters  | none                                                                                                                                                 |
| Output Parameters | N/A                                                                                                                                                  |
| Exceptions        | N/A                                                                                                                                                  |

## 5.1.4 fireCaseEvent

| Name             | fireCaseEvent                                                                                                                                                                                                                                                                                 |
|------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Description      | Triggers a case event                                                                                                                                                                                                                                                                         |
| Preconditions    | N/A                                                                                                                                                                                                                                                                                           |
| Input Parameters | CaseEventType - The case event type for which the listener is registered for String - The business use case for which the listener is registered for String - The version of business use case for which the listener is registered for String (optional) - The user that triggered the event |

<!-- image -->

|                   | Map<PropertyType,Object) - Payload map has only one entry, namely the REST_CASE object that contains all the details needed for a case   |
|-------------------|------------------------------------------------------------------------------------------------------------------------------------------|
| Output Parameters | Map<PropertyType,Object) - The updated payload map or the original input payload map if no updates were made                             |
| Exceptions        | CaseProcessingException - Exception thrown during the case national application processing                                               |

## 5.1.5 fireNotificationEvent

| Name             | fireNotificationEvent                                                                                                                                                                     |
|------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Description      | Triggers a notification event.                                                                                                                                                            |
| Preconditions    | N/A                                                                                                                                                                                       |
| Input Parameters | Map<PropertyType, Map<String, Object>) - Payload map has only one entry (REST_NOTIFICATION), namely the notification object that contains all the full details needed for a notification. |
| Exceptions       | CaseProcessingException - Exception thrown during the case national application processing                                                                                                |

## 5.1.6 fireDocumentEvent

| Name             | fireDocumentEvent                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Description      | Triggers a document event                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Preconditions    | N/A                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| Input Parameters | DocumentEventType - The document event type for which the listener is registered for String (optional) - The user that triggered the event String - The business use case for which the listener is registered for String - The version of business use case for which the listener is registered for String - The SED type for which the listener is registered for Map<PropertyType,Object) - Payload map has two entries: the first entry is the DOCUMENT_METADATA that contains all the metadata for the document (what case is related to, the document type, local creator of the NIE event, etc.) and the second entry (SED_DATA) is the actual SED payload. For the events where the SED payload is a batch of document parts, there is a 3 rd map entry: the metadata of the batch, containing the batch size and the first part no (ordinal number). |

<!-- image -->

|                   | *Note: The payload needs to be populated according to the expected Schema described under the CDM artefacts document 'EESSI_JSON_TEMPLATE_AND_SCHEMA (chapter 2: SCHEMA files) '   |
|-------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Output Parameters | Map<PropertyType,Object) - The updated SED map or the original input SED map if no updates were made                                                                               |
| Exceptions        | DocumentProcessingException - Exception thrown during the document national application processing                                                                                 |

## 5.2 Structure of the events metadata

## 5.2.1 fireCaseEvent

The metadata (REST\_CASE) of the case event contains the following fields:

- id (string): case local identifier (e.g. « 31 »)
- businessId (string): case business identifiler (e.g. « 31 »)
- processDefinitionName (string): the process definition name (e.g. « P\_BUC\_01 »)
- processDefinitionVersion (string): the process definition version (e.g. « 4.1 »)
- applicationRoleId (string): the role of the local tenant assigned to this case (e.g. « PO », « CP »)
- internationalId (string): the unique universal identifier of the case (e.g. « ff2628d388ab40eb8e6e6e073a594c67 »)
- sensitive (boolean): whether case has sensitive information or not
- status  (string):  case  status ;  possible  values:  « open »,  « closed »,  « active », « removed », « archived », « forward »
- counter (integer): technical field not related to business metadata
- sensitiveCommitted (boolean): technical field not related to business metadata
- startDate (string): the case start date in ISO 8601 format
- lastUpdate (string): the case last update in ISO 8601 format
- whoami (object):  the  organisation  the  local  case  belongs  to  (see chapter  5.2.4 organisation )
- creator (object): the local user which created this case (see chapter 5.2.5 creator )
- subject (object): the case subject prefills (see chapter 5.2.6 subject )
- searchMetadata  (object):  the  case  search  metadata  prefills  (see chapter  5.2.7 searchMetadata )
- participants  (list  of  objects):  the  case  participants  (see chapter  5.2.8  case participant )
- caseAssignment  (object):  the  case  assignment  data  (see chapter  5.2.9  case assignment )

## 5.2.2 fireDocumentEvent

The metadata (DOCUMENT\_METADATA) of the document event contains the following fields:

<!-- image -->

- id (string): the document local identifier (e.g. « c94eeac5ce814db0b497d34694bf7081 »)
- internalId (string): this field is deprecated and the value is always null
- type (string): the document type identifier (e.g. « P2000 »)
- typeVersion (string): the process definition version (e.g. « 4.1 »)
- displayName  (string):  the  document  type  description  (e.g.  « Old  age  pension claim »)
- caseId (string): the case local identifier (e.g. « 29 »)
- starter (boolean): true if this is a starter document
- isFirstDocument (boolean): true if this is the first document
- ParentType (string): the document type identifier of the parent document if the later exists (e.g. « P2000 »)
- status (string): the document status; the possible values are « new », « empty », « active », « sent », « cancelled », « received »
- direction (string): the document direction; the possible values are IN and OUT
- mimeType (string): this field is deprecated, and the value is null
- creator (object): the local user which created this document (see chapter 5.2.5 creator )
- versions (list of objects): a list of versions of this document (see chapter 5.2.10 version )
- isDummyDocument (boolean): true if this is a technical document (not official)
- isSendExecuted (boolean): true if send action was executed successfully
- hasMultipleVersions (boolean): true if the document has multiple versions
- hasBusinessValidation (boolean): true if business validation was performed
- hasCancel (boolean): true if the document can be invalidated
- order (integer): document order (e.g. 1)
- hasLetter (boolean): true if document can have letters attached (deprecated)
- hasReject (boolean): true if the document can be rejected
- hasReplyClarify (boolean): true if a reply can be sent to a request for clarification on this document
- isMLC (boolean): false if the document can be sent to only one participant
- selectParticipants (boolean): true if a subset of participants can be chosen when sending the document
- subProcessId (integer): technical field not related to business metadata (deprecated)
- isAdmin (boolean): true if the document is an administrative document (X\_\_\_)
- hasClarify (boolean): true if a request for clarification can be sent

<!-- image -->

- createTemplate (string): technical field not related to business metadata (deprecated)
- toSenderOnly (boolean): true if the document was a reply that can be send only to the sender of the request
- allowsAttachments (boolean): true if files can be attached to the document
- bulk (boolean): true if the document is bulk
- DMProcessId (string): technical field not related to business metadata (deprecated)
- creationDate (string): the document creation date in ISO 8601 format
- lastUpdate (string): the document last update time in ISO 8601 format
- validation  (object):  the  document  validation  information  (see chapter  5.2.11 validation )
- conversations (list  of  objects):  the  document  conversations  (see chapter 5.2.12 conversation )
- attachments  (list  of  objects):  the  document  attachments  (see chapter  5.2.13 attachment )

## 5.2.3 fireNotificationEvent

The metadata (REST\_NOTIFICATION) of the notification event contains the following fields:

- id (string): the identifier of the case or document that the notification refers to
- reason (string): technical field not related to business metadata (deprecated)
- caseId (string): the case local identifier (e.g. « 31 »)
- category (string): technical field not related to business metadata (deprecated)
- creationDate (string): the case/document creation date in ISO 8601 format
- dueDate (string): the due date of the notification in ISO 8601 format
- lastUpdate (string): the case/document laste update time in ISO 8601 format
- caseInfo (object): case information (see chapter 5.2.14 caseInfo )
- document  (object):  the  document  information  if  the  notification  refers  to  a document (see chapter 5.2.15 document )
- sourceType (string): the source of the notification (e.g. « business », « messaging »)
- creator  (object):  the  local  user  that  created  the  notification  (see chapter  5.2.5 creator )
- responsibleParties  (list  of  objects):  list  of  local  users  that  will  receive  the notification ; the object has the same structure as the creator (see chapter 5.2.5 creator )
- severity (string): the event severity level ; the possible values are « information », « warning », « error »
- type (string): the type of the notification (e.g. « case\_arrived », « case\_assigned »)
- status (string): the notification status (e.g. « active »)

<!-- image -->

- assignmentRequestStatus (string): technical field not related to business metadata (deprecated)
- isRead (boolean): true if the notification was read
- extendedProperties (object): see chapter 5.2.16 extendedProperties
- assignmentRequest (object): see chapter 5.2.17 assignmentRequest
- failureReason (object): information about the failure reason (see chapter 5.2.18 failureReason )

## 5.2.4 organisation

This object contains organisation data and has the following fields:

- id (string): the organisation universal identifier (e.g. « BE:ORG »)
- name (string): the organisation name
- acronym (string): the organisation acronym (e.g. « BE:ORG »)
- registryNumber (string): business registration number
- countryCode (string): the organisation country code (e.g. « BE »)
- location (string): the organisation geolocation (e.g. « 50.842443,4.367391 »)
- activeSince (string): the date since the organisation was active in ISO 8601 format
- contactMethods (list of objects): the list of contact methods for this organisation (see chapter 5.2.19 contactMethod )
- address (object): the organisation address (see chapter 5.2.20 address )

## 5.2.5 creator

This object contains data about a local RINA user and the organisation it belongs to. In case of received messages, the creator is the local RINA user responsible for managing the (received) document. It has the following fields:

- id (string): the user identifier (e.g. « 123 »)
- name (string): the user name (e.g. « supervisor »)
- type (string): « User »
- organisation  (object):  the  organisation  the  user  belongs  to  (see chapter  5.2.4 organisation )

## 5.2.6 subject

This  object  contains  the  case  subject  prefill  data.  It  may  have  fields  like:  « pid », « surname », « name », « birthday », « sex ».

## 5.2.7 searchMetadata

This object contains the case search metadata prefills. It has the following fields:

- caseId (string): the case local identifier (e.g. « 31 »)
- flowType (string): the process definition identifier (e.g. « P\_BUC\_01 »)
- status (string): the case status ; possible values: « open », « closed », « active », « removed », « archived », « forward »

<!-- image -->

This object may also contain fields like « localPin », « surname », « name », « birthday ».

## 5.2.8 case participant

This object contains case participant data and has the following fields:

- role (string): the role of the local tenant assigned to this case (e.g. «CaseOwner», «CounterParty»)
- organisation (object): an organisation that is participant in this case (see chapter 5.2.4 organisation )

## 5.2.9 case assignment

This object contains case assignment data and has the following fields:

- id (string): local case identifier
- properties (object): case properties have the following fields:
- o importance (string): e.g. « 0 », « 1 »
- o criticality (string): e.g. « 0 », « 1 »
- actors (list of objects): users/groups assigned to the case (see chapter 5.2.21 actor )

## 5.2.10 version

This object contains data about a version of a document, and it has the following fields:

- id (string): the document version identifier (e.g. « 1 », « 2 »)
- date (string): the update time in ISO 8601 format
- user (object): the user that created this version of the document (see chapter 5.2.5 creator )

## 5.2.11 validation

This object contains document validation data and has the following fields:

- status (string): possible values are « valid » and « invalid »
- errors (string): description of validation errors

## 5.2.12 conversation

This object contains data from the messages exchanged for this document and has the following fields:

- id (string): conversation identifier (e.g. « 6d55850a398c45c986df2446677fce98 »)
- versionId (integer): document version identifer (e.g. 1)
- userMessages  (list  of  objects):  details  about  the  message  (see chapter  5.2.22 userMessage )
- participants (list  of  objects):  list  of  participants  to  the  case  (see chapter 5.2.23 conversation participant )

## 5.2.13 attachment

This object contains metadata for the file attached to the document and has the following fields:

- id (string): the attachment identifier (e.g., « 1 »)

- name (string): the file name

·

fileName (string): the file name

- caseId (string): the case identifier (e.g., « 31 »)
- documentId (string): the document identifier (e.g. « c94eeac5ce814db0b497d34694bf7081 »)
- mimeType (string): the file mime type (e.g., « APP\_PDF »)
- creator (object): the user who attached the file (see chapter 5.2.5 creator )
- lastUpdate (string): the last update time in ISO 8601 format
- creationDate (string): the attachment creation date in ISO 8601 format
- versions (list of objects): list of versions of this attachment ; the version object has the following fields:
- o id (string): the attachment identifier
- o date (string): the version creation date in ISO 8601 format
- o user (object): the version creator (see chapter 5.2.5 creator )

## 5.2.14 caseInfo

This object contains case metadata and has the following fields:

- id (string): the case identifier (e.g., « 31 »)
- type (object): the case type meta ; has the following fields:
- o id (string): BUC identifier (e.g. « P\_BUC\_01 »)
- o version (string): BUC version (e.g. « 4.2 »)
- o name (string): BUC description (e.g. « Old Age Pension Claim »)
- o sector (string): BUC sector (e.g. « PENSION »)
- o versions (list of objects): BUC versions of this case ; the version has the following fields:
- version (string): BUC version (e.g. « 4.2 »)
- activeFrom (string): the activation date in ISO 8601 format
- subject (object): subject prefills for this case
- properties (object): has the following fields:
- o importance (string): e.g. « 1 »
- o criticality (string): e.g. « 1 »

## 5.2.15 document

This object contains document metadata and has the following fields:

- id (string): the document identifier (e.g. «c94eeac5ce814db0b497d34694bf7081»)
- typeVersion (string): BUC version (e.g. « 4.2 »)
- type (string): the document type (e.g. « P2000 »)

<!-- image -->

<!-- image -->

- name (string): the document type description (e.g. « Old Age Pension Claim »)
- receiver (object): the receiving organisation (see chapter 5.2.4 organisation )

## 5.2.16 extendedProperties

This object has the following fields:

- reason (string): technical field not related to business metadata (deprecated)
- failureReason (object): the error (if it's the case) that caused this event; has the following fields:
- o code (string): error code
- o description (string): the error description

## 5.2.17 assignmentRequest

This object has the following fields:

- actors (list of strings): list of users this notification refers to.

## 5.2.18 failureReason

This object has the following fields:

- code (string): the error code
- description (string): the error description

## 5.2.19 contactMethod

This object describes a contact method for an organisation and has the following fields:

- type (string): the contact method type (e.g. « email »)
- value (string): the contact method.

## 5.2.20 address

This object contains the organisation address and has the following fields:

- country (string): country code (e.g. « BE »)
- town (string)
- street (string)
- postalCode (string)
- region (string)

## 5.2.21 actor

This object contains metadata for a case assignment actor and has the following fields:

- id (string): the assignment identifier (e.g. « f42fc5c202e8484a82daddcda896ed34 »)
- name  (string): the assignment role ; possible values are: « Supervisor », « Authorized »,  « Nonauthorized »,  « Auditor »,  « Viewer », « Medical »,  « Vip », « Everyone »
- userGroups (list of objects): contains the list of users and groups that are part of the assignment ; this object (user/group) has the following fields:

<!-- image -->

- o id (string): user/group identifier (e.g. « 7 »)
- o name (string): user/group name (e.g. « supervisor »)
- o type (string): possible values are « User » and « Group »

## 5.2.22 userMessage

This object has the following fields:

- receiver (object): the receiving organisation (see chapter 5.2.4 organisation )
- sender (object): the sending organisation (see chapter 5.2.4 organisation )
- sbdh (object): the message content metadata
- isSent (boolean): true if the message was sent
- id (string): the message identifier (e.g. « a73d536677894b01b638c1ae7a5318fe »)

## 5.2.23 conversation participant

This object contains the conversation participant metadata and has the following fields:

- role  (string):  the  participant  role  in  the  conversation;  the  possible  values  are: « Sender », « Receiver », « Participant »
- organisation (object): the participant organisation (see chapter 5.2.4 organisation )

## 5.3 Main Changes in the events metadata between RINA EESSI 2019 and RINA EESSI 2020 releases

## 5.3.1 fireCaseEvent

Changes to the payload REST\_CASE object:

- the field processDefinitionName changed from a composite value (e.g. PO\_P\_BUC\_01\_v4.1) to the BUC identifier (e.g. P\_BUC\_01)
- new field processDefinitionVersion ; it contains the BUC version (e.g. 4.1)
- new field applicationRoleId ; it contains the application role (e.g. PO)

## 5.3.2 fireDocumentEvent

Changes to the payload DOCUMENT\_METADATA object:

- the field mimeType has value null
- the field internalId has value null
- the field receivedDate was removed; the data can be found in lastUpdate field
- the  field userId was  removed;  the  user  metadata  is  contained  in  the  structure creator

The following changes are related to subdocument events (e.g. UPDATE\_SUBDOCUMENT):

- no : subdocument order
- typeVersion : document type version (e.g. 4.1)

## 5.3.3 fireNotification event

Changes to the payload REST\_NOTIFICATION object:

- the field subject was removed
- the field lastUpdate was removed
- the field caseInfo was added. It has the following structure:
- o id : the case identifier
- o type : structure with fields:
- id : type identifier (e.g. P\_BUC\_01)
- name : type name (e.g. Old Age Pension Claim)
- sector : e.g. PENSION
- versions : list of objects containing the fields version (e.g. 4.1) and activeFrom (date-time)
- o subject : the same structure as the subject field removed from the root object (REST\_NOTIFICATION)
- o properties :  object  containing  the  fields importance (e.g.  1)  and criticality (e.g. 1)
- the  field receiver inside  the document object  now  contains  the  organisation metadata (e.g. id , name , acronym etc.)
- the organisation object  found  in  the document.receiver and responsibleParties paths does not contain the following metadata:
- o address
- o contactMethods
- o assignedBUCs
- o accessPoint

<!-- image -->

## 6 Data contract

Additional details related to Data Contract used in NIE can be found in the Case Processing Interface specifications (i.e., RESTCase, RESTDocument, etc.)

## 6.1 Data model

## Diagram

Figure 12. Data model

<!-- image -->

## 6.2 EventType

This is a marker interface for case and document event types

## 6.3 CaseEventType

CaseEventType tracks down the state where the case is in that moment. The case can be opened, received, closed or deleted.

| Attribute   | Description                              | Data Type     |
|-------------|------------------------------------------|---------------|
| OpenCase    | The case is opened as PO, unidirectional | CaseEventType |
| ReceiveCase | The case is received unidirectional      | CaseEventType |
| RemoveCase  | The case is removed, unidirectional      | CaseEventType |
| CloseCase   | The case is closed, unidirectional       | CaseEventType |
| DeleteCase  | The case is deleted, unidirectional      | CaseEventType |

<!-- image -->

<!-- image -->

| ForwardCase   | The case is forwarded to the counter party and the local process does not have ownership anymore, unidirectional   | CaseEventType   |
|---------------|--------------------------------------------------------------------------------------------------------------------|-----------------|
| ReopenCase    | The case is reopen, unidirectional                                                                                 | CaseEventType   |

## 6.4 DocumentEventType

| Attribute             | Description                                        | Data Type         |
|-----------------------|----------------------------------------------------|-------------------|
| InitialiseDocument    | The document is initialized, bidirectional         | DocumentEventType |
| NewDocument           | The document is new, bidirectional                 | DocumentEventType |
| UpdateDocument        | The document is updated, bidirectional             | DocumentEventType |
| SendDocument          | The document is sent, unidirectional               | DocumentEventType |
| DeleteDocument        | The document is deleted, unidirectional            | DocumentEventType |
| CancelDocument        | The document is cancelled, unidirectional          | DocumentEventType |
| ReceiveDocument       | The document is received, bidirectional            | DocumentEventType |
| InitialiseSubdocument | The subdocument is initialized, bidirectional      | DocumentEventType |
| NewSubdocument        | The subdocument is created, bidirectional          | DocumentEventType |
| UpdateSubdocument     | The subdocument is updated, bidirectional          | DocumentEventType |
| DeleteSubdocument     | The subdocument is deleted, unidirectional         | DocumentEventType |
| NewDocumentBatch      | A batch of subdocuments is created, unidirectional | DocumentEventType |
| ReceiveDocumentBatch  | A batch of subdocuments is received, bidirectional | DocumentEventType |

## 6.5 EventSource

EventSource contains all the information needed for the client being notified to understand the source of the event fired: type of the event (case or document), the business use case and the SED type (only needed for the document event type):

| Attribute   | Description Data Type                                   |
|-------------|---------------------------------------------------------|
| eventType   | The type of the event either case or document EventType |

<!-- image -->

| processDefinitionId   | The business use case   | String   |
|-----------------------|-------------------------|----------|
| sedType               | The SED type            | String   |

## 6.6 PropertyType

This enumeration shows what kind of object can be passed as input parameters:

| Attribute        | Description                                                                           | Data Type    |
|------------------|---------------------------------------------------------------------------------------|--------------|
| RestCase         | The object type is RESTCase is contains the case details                              | PropertyType |
| DocumentMetadata | The object type is RESTDocument and contains document metadata details                | PropertyType |
| SedData          | The object type is String and contains the SED data payload in JSON format            | PropertyType |
| BatchMetadata    | The object type is BatchMetadata and contains metadata of the batch of document parts | PropertyType |

## 6.7 BatchMetadata

BatchMetadata contains information about the batch of document parts: the number of the first subdocument in the batch and the batch size:

| Attribute   | Description                                              | Data Type   |
|-------------|----------------------------------------------------------|-------------|
| firstNo     | The ordinal number of the first subdocument in the batch | Integer     |
| size        | The number of subdocuments in this batch                 | Integer     |

## 7 Fault contract

We define the fault contract as the possible exceptions that might occur in the business messaging component.

## Diagram

Figure 13. Fault Contract

<!-- image -->

## CaseProcessingException

Exception that occurs during the execution of the case listener callback, this exception must be thrown by the client implementation in case of any error might happen during the case event processing.

## DocumentProcessingException

Exception that occurs during the execution of the document listener callback, this exception must be thrown by the client implementation in case of any error might happen during the document event processing.

## Note:

In cases when updatedPayloadMap are uncompliant, no faults are expected, this will be ignored and logged

<!-- image -->

<!-- image -->

## 8 Illustrative sample of a basic implementation

Depending on their needs, the national application implements the methods introduced in this document as they need. It is not necessary to address all possible events. The national application  can  choose  to  "listen"  only  for  some  combinations  of  events  and  input parameters and to ignore others.

A very basic implementation could use this pattern:

```
@Override public boolean hasDocumentListener (DocumentEventType documentType, String buc, String version, String document) { if (documentType.equals(DocumentEventType.INITIALISE_DOCUMENT)) { if (buc.equals("P_BUC_01") && document.equals("P6000")) return true; if (buc.equals("P_BUC_01") && document.equals("P5000")) return true; return false; } // ... return false; } @Override public Map<String, Object> fireDocumentEvent(DocumentEventType documentEventType, String buc, String version, String document, Map<PropertyType, Map<String, Object>> payLoad) throws DocumentProcessingException { if (documentEventType.equals(DocumentEventType.INITIALISE_DOCUMENT) && buc.equals("P_BUC_01") && document.equals("P5000")) { Map<String, Object> data = payLoad.get(PropertyType.SED_DATA); .../* code to call the national application to store the SED data in it */ String personId = .... /* code to read the person identification field/fields from received sed data */ Object naInformation = .... /* code to call the national application and to retrieve useful data from it, related to the person with personId determined before */ Map<String, Object> updatedPayload = .... /* code to fill in the SED with the data retrieved from the national application */ return updatedPayload; } // .... return payLoad; }
```

## 9 NIE configuration

The admin module of the portal allows also to configure the NIE events.

From the NIE Settings it can be added a new subscription to case event, document event or it can be deleted a subscription. Single or multiple cases or documents can be part of the same subscription.

If there is no subscription defined, no event will be fired/sent to the RINIE.

An example of the configured events is illustrated in the Figure 14 below.

Figure 14. Illustrative sample of configured events

<!-- image -->

<!-- image -->