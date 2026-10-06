---
unique-name: eessi-rina-functional-specs-administration-portal-
display-name: EESSI   RINA   Functional Specs   Administration Portal   rev03 (1)
category: GENERAL
tags: ec
---

EESSI - RINA

## Functional Specifications

Administration console Use Cases (rev03)

Solution / Application Architecture

Employment, Social Affairs and Inclusion

## Contents

1

Glossary of Terms

2

3

4

5

6

.............................................................................................. 5

Document Information and Audience

....................................................................... 5

Business Purpose

.............................................................................................. 5

Introduction

..................................................................................................... 5

4.1

Context .................................................................................................... 5

4.2

4.3

4.4

Scope

........................................................................................................ 6

Out of scope: ............................................................................................ 6

Requirements

.............................................................................................. 6

RINA Administration Console

5.1

Main Modules

- 

Functional Specifications .................................... 17

............................................................................................. 17

Interface Use Cases ....................................................................................... 21

6.1

Access Control Interfaces and Admin Settings .............................................. 21

6.2

6.3

6.4

6.5

6.6

6.7

6.8

6.9

6.10

6.11

6.12

6.13

Application Settings .................................................................................. 29

Messaging Settings ................................................................................... 51

NIE Settings ............................................................................................ 74

RINA Archiving ......................................................................................... 82

IAM ........................................................................................................ 91

Authorization ......................................................................................... 107

Notification Centre .................................................................................. 124

Logs ..................................................................................................... 134

Technical Logs........................................................................................ 141

Automatic Updates ................................................................................. 145

Test Center ............................................................................................ 155

Business Exceptions ................................................................................ 157

## Document Control Information

| Document Control | Value |
| --- | --- |
| Project Title | Electronic Exchange of Social Security Information (EESSI) |
| Document Title | EESSI - RINA - Functional Requirements - Administration Portal |
| Document Category | Solution / Application Architecture |
| Revision | rev03 |
| Component Version | \- |
| Last Publication Date | 14/12/2021 |
| Document Status | Final |
| Sensitivity (TLP) Distribution terms | The distribution of this document is done strictly in line with the Traffic Light Protocol (TLP) established by the European Commission's note AC 790/15 REV for the EESSI project documentation. In line with the note AC 790/15 REV, this document is labelled as TLP = 'Green'. Therefore, it can be circulated widely within the EESSI community. However, the document or the information herein may not be published or posted on the Internet, nor released outside of the |
| Connected/Embedded Files | None |
| Authors | European Commission, DG EMPL A4, EESSI BA |
| Revised by | European Commission, DG EMPL A4, EESSI QA/QC |
| Approved by | European Commission, DG EMPL A4, EESSI PMO |

## Document History

| Project Milestone | Date | Changes/Corrections Description |
| --- | --- | --- |
| EESSI 2020 | 18/12/2020 | Initial Document |
| EESSI-2020 (rev01) | 12/03/2021 | Section 6.2- removed Validate SED in Client check box; Case counter setting |
| EESSI-2020 (rev01) | 12/03/2021 | Section 6.3 - removed Clustering Nodes |
| EESSI-2020 (rev01) | 12/03/2021 | Removed Section Letter Templates |
| EESSI-2020 (rev01) | 12/03/2021 | Section 6.7 - removed Policy decision point Implementation Class |
| EESSI-2020 (rev01) | 12/03/2021 | Section 6.8 - added new types of notifications for duplication |
| EESSI-2020 (rev01) | 12/03/2021 | Section 6.6 - removed refresh case assignment |
| EESSI-2020 (rev02) | 01/07/2021 | Section 6.8 - added new use cases UC_NC_02_extension1, UC_NC_02_extension2 and deleted the ' SED not matching Case ' n otification references |
| EESSI-2020 (rev03) | 14/12/2021 | Section 5.1 - clarifications about RINA version Section 6.2 - UC_AS_10 - clarifications about relationship between local and business case IDs |
| EESSI-2020 (rev03) | 14/12/2021 | Section 6.2 - UC_AS_07 - adding clarifications on the new field Case Search Results Maximum Limit |

## 1 Glossary of Terms

| Term/Acronym | Definition |
| --- | --- |
| RINA | Reference Implementation of a National Applications |

## 2 Document Information and Audience

## Purpose :

This document provides a functional description of the Reference Implementation of a National Application ( RINA -Administration Console ) from a user point of view. For this purpose, the specification describes the RINA services behaviour with a set of identified use-cases.

## Audience :

- All project team members
- Project Sponsor, Business Owner, and IT/Technical Owner
- All other key stakeholders

## 3 Business Purpose

The free movement of people is a fundamental right in Europe. Citizens of the European Union can freely travel to other countries in the EU/EFTA space and take up residence and employment there. Modern social security systems need to reflect this mobility and make sure that citizens enjoy full access to social security in cross-border settings as well.

The Reference Implementation of a National Applications ( RINA ) is a web-based software application for the electronic management and exchange of social security cases across competent institutions of the participant countries. RINA is developed by the Directorate-General for Employment, Social Affairs and Inclusion (DG EMPL) and evolved out of the EESSI (Electronic Exchange of Social Security Information) project.

It fulfils the business needs -the so-called business layer requirements -for national institutions participating in the EESSI cross-border message exchange. The application supports the complete range of business use cases concerning the exchange of social security data.

## 4 Introduction

## 4.1 Context

Part of the National Institutions Domain, RINA (Reference Implementation for National Applications) consists in a collection of infrastructure and communication services, foundation, repository and publishing services, business, integration and user interface services which will provide for clerks and their organisations the tools to implement the International Protocol of Data Exchange based on Structured Electronic Documents in Social Security belonging to European Community Member States and Associated States. It is based on 4 layers which are built one on top of the other:

- Business Messaging Services (BMS) - provide a reusable component for sending business messages to the Access Point using the technical protocol (ebMS/AS4).

These services provide the translation (business message to technical message and vice versa), transformation (converting IDs to GUIDs), validation and signing of the business messages for correct exchange with the EESSI environment, and the correct reception of messages from other institutions.

- Case Processing Services (CPS ) -provide a state full component built on top of the Business Messaging Services that manage cases in a structured manner taking care of all the issues regarding case flow, documents, notifications, user management and provides several interfaces for external access
- Portal -provides an UI (user interface) built on top of the Case Processing Services having:
- o Case Management Console and
- o Administration Console
- CAS Authentication Server -the SSO (Single Sign On) server providing the authentication to users/clients requesting to use a service.

## 4.2 Scope

The scope of this document is to provide a specification document for Administration Console, part of the Case Processing Interface (UI Portal). It covers the perspective of an IT administrator and details how a RINA instance can be configured locally or adapted to the needs of a specific institution.

## 4.3 Out of scope:

Additional details related to the Case Processing Interface functions and use cases, service contract, data contract and relevant samples are out of scope for this specification and can be found in other RINA related specifications:

- RINA Identity and Access Management (IAM),
- RINA National Information Exchange Interface (NIE),
- RINA Archiving,
- RINA Localisation,
- RINA High Availability and High Performance

## 4.4 Requirements

| Req. ID | Summary | Req. Statement | Req. Type | Layer( s) | MoSCo W |
| --- | --- | --- | --- | --- | --- |
| EESSI.NA.0 01 | EEESI BL Conformanc e | The system must fully conform to the EESSI BL specifications (BUCs) | Non- Functional | General | Must have |
| EESSI.NA.0 02 | Search managemen t requirement s | The system must provide tools for users to be able to search and find cases in different ways: · free-text search · structured search · predefined structured search · combination of predefined with text search | Functional | Present ation(G UI) | Must have |

| Req. ID | Summary | Req. Statement | Req. Type | Layer( s) | MoSCo W |
| --- | --- | --- | --- | --- | --- |
|  |  | All Searches are performed against Case Metadata |  |  |  |
| EESSI.NA.0 03 | Search managemen t requirement s | All Searches are performed against Case Metadata | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 04 | Free-text search | A user must be able to perform free-text search in fuzzy or exact manner on case metadata in order to identify a case or a group of cases. | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 05 | Predefined - Structured search | The system must allow users to define structured searches using visual search expressions and allow users to persist their searches as pre-defined searches. | Functional | Present ation(G UI) | Should have |
| EESSI.NA.0 06 | Predefined - Structured search | A user must be able to add a new or modify an existing predefined search. | Functional | Present ation(G UI) | Should have |
| EESSI.NA.0 07 | Predefined - Structured search | A user must be able to delete an existing pre-defined search | Functional | Present ation(G UI) | Should have |
| EESSI.NA.0 08 | Applying a predefined search | A user must be able to quickly select and apply a predefined search in order to minimize searching effort. | Functional | Present ation(G UI) | Should have |
| EESSI.NA.0 09 | Refine predefined search results | After the system has filtered the cases based on a user's predefined search request, the user can read the list of filtered cases. The user must be able to optionally use the free text search to further refine the returned results. | Functional | Present ation(G UI) | Should have |
| EESSI.NA.0 10 | Configure Search Result | A user must have the possibility to configure for each case type: • the list of columns that will be returned by the search engine • the order of the columns and • the order of the results (ascending/descending sort). | Functional | Present ation(G UI) | Should have |

| Req. ID | Summary | Req. Statement | Req. Type | Layer( s) | MoSCo W |
| --- | --- | --- | --- | --- | --- |
| EESSI.NA.0 11 | Case managemen t requirement s | The case management requirements cover all aspects of case management, including creation of case, creation of document, creation of a counterparty list, sending documents, running case specific actions, listing cases, documents, or actions | Functional | General | Must have |
| EESSI.NA.0 12 | Create case | The system must allow a user to create a case through accessing a hierarchical structure of case types | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 13 | Create case | The system should retain (per session) the last case type instantiated to enable to quickly creation of another case. | Functional | Present ation(G UI) | Should have |
| EESSI.NA.0 14 | Determine Exchange Partners | The system must allow the user to specify the case participant(s) for each case | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 15 | Determine Exchange Partners | The system must persist the case participant (s) for each case instance | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 16 | Determine Exchange Partners | The system must allow the user to view the current case participant(s) and any historical changes. | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 17 | Case managemen t actions | The system must provide users with a list of available actions (tasks) related to a specific case instance depending on the state of the case. | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 18 | Case managemen t actions | Any case action executed by a user must update the case state. | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 19 | Case managemen t actions | The system must recalculate display the available action list upon the change of case state to ensure that users can only perform actions that are correct based the case state. | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 20 | Case managemen t actions | The user must have the possibility to select one action from the action list presented to him. | Functional | Present ation(G UI) | Must have |

| Req. ID | Summary | Req. Statement | Req. Type | Layer( s) | MoSCo W |
| --- | --- | --- | --- | --- | --- |
| EESSI.NA.0 21 | Group Case Actions | The system must provide logical grouping of case actions at case level or SED level. | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 22 | Group Case Actions | The system could provide further logical grouping of case actions as case level. | Functional | Present ation(G UI) | Should have |
| EESSI.NA.0 23 | Group Case Actions | The system should offer the possibility to filter case actions by grouping. | Functional | Present ation(G UI) | Could have |
| EESSI.NA.0 24 | Case Importance/ Criticality | A user must be able to specific the level of Importance of a case. | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 25 | Case Importance/ Criticality | A user must be able to specific the level of Criticality of a case. | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 26 | Case Importance/ Criticality | A user should be able to change the importance and criticality of a case at time during the case. | Functional | Present ation(G UI) | Should have |
| EESSI.NA.0 27 | Case Importance/ Criticality | The system should allow a user to set the importance/criticality of more than one case at a time. | Functional | Present ation(G UI) | Could have |
| EESSI.NA.0 28 | Case Alarm | A user must be able to set an alarm by which they expect an action to have occurred. | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 29 | Case Alarm | A user must be able to delete the alarm. | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 30 | Case Alarm | The system must notify the user when an alarm expires. | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 31 | Create Documents | The system must allow the persistence of documents in multiple draft states. | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 32 | Document Validation | The system must display document validation errors in a clear and logical fashion, allowing the user to navigate directly to the source of the error from the error description. | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 33 | Document Validation | Document validation must fire on the sending of a document. | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 34 | Document Validation | Document validation must not fire on the saving of a draft. | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 35 | Manage Document Views | The system must allow users to view all major document versions | Functional | Present ation(G UI) | Must have |

| Req. ID | Summary | Req. Statement | Req. Type | Layer( s) | MoSCo W |
| --- | --- | --- | --- | --- | --- |
| EESSI.NA.0 36 | Manage Document Views | The system could allow users to view minor document versions | Functional | Present ation(G UI) | Could have |
| EESSI.NA.0 37 | Manage Document Views | The system should offer multiple views for users to view sent and received documents | Functional | Present ation(G UI) | Should have |
| EESSI.NA.0 38 | Manage Document Views | The system must offer the possibility to filter documents by: • Time • Direction • Partner • Type | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 39 | Manage Document Views | A user must be able to clearly visualise draft documents from sent/received documents. | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 40 | Manage Document Views | A user should be able to clearly visualise documents that are in different document states. | Functional | Present ation(G UI) | Should have |
| EESSI.NA.0 41 | Manage Document Views | The system must offer access to view all document versions. | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 42 | Manage document attachments | The user must be able to manage the attachments through attaching and detaching files. | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 43 | Manage document attachments | The system must allow attachments to be added at case level or at SED level. | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 44 | Manage document attachments | The user must be able to manage the attachments through attaching and detaching files. | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 45 | Manage document attachments | The system must allow attachments to be added at case level or at SED level. | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 46 | Manage document attachments | The system should restrict the type of attachments allowed to the following types: · application/pdf · application/msword · application/xml · image/jpeg · image/png · image/tif · text/rtf | Functional | Present ation(G UI) | Should have |

| Req. ID | Summary | Req. Statement | Req. Type | Layer( s) | MoSCo W |
| --- | --- | --- | --- | --- | --- |
|  |  | · text/xml |  |  |  |
| EESSI.NA.0 47 | Manage document attachments | The system must restrict the access to attachments of a certain business type where necessary. | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 48 | Manage document attachments | The system must allow users the access to read/open attachments directly. | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 49 | Print Documents | The system must allow a user to choose an action that will render a document as a printable form (PSED). | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 50 | Print Documents | The system should generate Portable Documents. | Functional | Present ation(G UI) | Should have |
| EESSI.NA.0 51 | Manage comments | The user must be able to create, read or delete comments (case notes) at document level or case level. | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 52 | Manage comments | The system must persist and display the author and time of each comment. | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 53 | Manage comments | The system must ensure only the author of a comment (or a user with special permissions) can delete a comment. | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 54 | Case assignment | New Cases (both created locally & received) should be automatically assigned to users using configurable case assignment rules (via the administration console). The type rules that can be set should be based on for example: • The country concerned • The case metadata (PIN, Surname, DOB) • The outstanding workload of users | Functional | Present ation(G UI) | Should have |
| EESSI.NA.0 55 | Case assignment | A user (with permission) must be able to assign a case to users or groups of users that are part of the local organisation. | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 56 | Case assignment | A user (with permission) must be able to unassign/reassign a case to users or groups of users that are part of the local organisation. | Functional | Present ation(G UI) | Must have |

| Req. ID | Summary | Req. Statement | Req. Type | Layer( s) | MoSCo W |
| --- | --- | --- | --- | --- | --- |
| EESSI.NA.0 57 | Case assignment | A user (without permission) must be able to request to a user (with permission) to assign a specific case to them. | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 58 | Case assignment | A user must be able to assign/unassign/reassign more than one case at a time. | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 59 | Case assignment | The system must ensure that only assigned users can actively work on/progress a case. | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 60 | Case assignment | The system must restrict access to certain case types where necessary (e.g., sensitive cases) | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 61 | Document Translation | A user must be able to translate a received documents content (whole document of part of) into any of the EU official languages. | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 62 | Generate notifications | Every time an event condition is fulfilled, the system must notify the assigned Users of the case. Examples of events are presented below: • New message arrived; • New case arrived; • Message update; • Message delivered; • Message delivery error; • New case assigned; • New counterparty case was created; | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 63 | Generate notifications | Each notification must have associated a type that is either: • Error • Alert or • Information | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 64 | View notifications | Users must be able to view all their notifications though a dedicated Notifications panel. | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 65 | View notifications | User should be able to view case specific notifications in the case level view | Functional | Present ation(G UI) | Should have |
| EESSI.NA.0 66 | Notification actions | A user should be able to take logical actions direct from the notification | Functional | Present ation(G UI) | Should have |

Status: Final / TLP: GREEN

| Req. ID | Summary | Req. Statement | Req. Type | Layer( s) | MoSCo W |
| --- | --- | --- | --- | --- | --- |
| EESSI.NA.0 67 | Filter notifications | The system must offer the possibility to filter notifications based on type and status | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 68 | Filter notifications | The System should offer the possibility to navigate to the notifications' timeline. | Functional | Present ation(G UI) | Should have |
| EESSI.NA.0 69 | Notification Summary | The system must provide count of notification by types in the notification panel and the case level views | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 70 | Notification Summary | The counts be automatically re- calculated when User take actions on the notifications | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 71 | Notification Summary | A user must be able to receive anytime in every module of the application the delivery of a new notification. This must be obtrusive to the user. | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 72 | Suppress/U nsuppresse d notification | The user must be able to suppress a notification so that it is not taken into account anymore | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 73 | Suppress/U nsuppresse d notification | The user must be able to unsuppress a previously suppressed notification so that it is taken into account anymore. | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 74 | Mark notification as read/unread | The user can mark a notification as read or unread so that the next time the notifications are displayed the read/unread state is preserved. | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 75 | Report requirement s | TBD |  |  |  |
| EESSI.NA.0 76 | Administrati on Console | All administrator tasks must be provided through a dedicated administrator console | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 77 | User Managemen t and organization structure | An administrator must be able to define organization units, together with departments having any level of nesting. | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 78 | User Managemen t and organization structure | An administrator must be able to define users or to refer them from an external identity management repository. | Functional | Present ation(G UI) | Must have |

| Req. ID | Summary | Req. Statement | Req. Type | Layer( s) | MoSCo W |
| --- | --- | --- | --- | --- | --- |
| EESSI.NA.0 79 | User Managemen t and organization structure | An administrator must be able to configure the default user settings | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 80 | Authorisatio n policies | For each case type, the administrator must be able to configure what users or groups are allowed to create, to execute, to administer or to audit new cases. These are corresponding to the regular user roles: Clerk, Supervisor and Auditor. | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 81 | Audit | The administrator must be able to configure what events the system needs to audit. The audit must reflect to all main resources exposed by the functional modules, for all possible operations: create, read, update, delete and execute. | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 82 | Audit | The minimum dataset the system must audit are: • Id of event • Operation (create, read, update, delete and execute) • Username • Computer name and IP • Date and time • Component which generated the event • Outcome: Success or business error • Audited object ( e.g.: case) • Participants ( e.g.: person or organisation) | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 83 | Technical log | All the modules of system must populate a centralised log available for Administrators. | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 84 | Technical log | The administrator must be able to configure the level of logging: trace, debug, info, warn, error and fatal. | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 85 | Notification Managemen t | An administrator should be able to suspend notification types | Functional | Present ation(G UI) | Should have |

Status: Final / TLP: GREEN

| Req. ID | Summary | Req. Statement | Req. Type | Layer( s) | MoSCo W |
| --- | --- | --- | --- | --- | --- |
| EESSI.NA.0 86 | Notification Managemen t | An administrator should be able to configure notification behaviour (i.e. how a notification is presented to a user) | Functional | Present ation(G UI) | Should have |
| EESSI.NA.0 87 | System updates and versioning | The physical artefacts (forms, case behaviour, vocabularies, etc.) distributed by CSN through AP must be able to be updated by an administrator. These physical models must be accompanied with a minimum set of metadata: • Version • Date of release | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 88 | Messaging configuratio n | The messaging configurations must be fully available for administrators through the administration console | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 89 | Counter managemen t | The administrator must be able to define counters for national case ID. The policies for national case identification can be particular to a department and must have a period of availability | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 90 | Retention policy (case, audit, technical log) | The system must be able to archive the closed cases, audit and technical log. The retention policy for all of this must be configurable | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 91 | Dead letter Queue | The system must provide an administrator with access to received documents that it could not logically processed (i.e., unrelated documents, documents with errors) | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 92 | Dead letter Queue | The system must allow the administrator to return a business exception error automatically for these documents | Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 93 | Dead letter Queue | The sending of business exception error could be a bulk operation | Functional | Present ation(G UI) | Could have |
| EESSI.NA.0 94 | User login | Any user having the right credentials must be able to access the system. The credentials can be username and password or smartcards. | Non- Functional | Present ation(G UI) | Must have |

Status: Final / TLP: GREEN

| Req. ID | Summary | Req. Statement | Req. Type | Layer( s) | MoSCo W |
| --- | --- | --- | --- | --- | --- |
| EESSI.NA.0 95 | User login | The system must logout a user if the application is left idle for a pre-configurable period of time | Non- Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 96 | Multi- tenancy | The system must be able to host multiple institutions completely isolated between them and with independent capabilities of administration | Non- Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 97 | Localization | The user can decide any-time what the language of its user interface is. The user interface must act accordingly to this setting by translating all the screens together with the codified fields (vocabularies). | Non- Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 98 | Accessibility | The system must be WCAG 2.0 compliant to minimum AA standard. | Non- Functional | Present ation(G UI) | Must have |
| EESSI.NA.0 99 | Browser Compatibilit y | The system must fully work in the following browsers: • Chrome (v.40 +) • Firefox (v.32+) • Internet Explorer (v.11) • MS Edge | Non- Functional | Present ation(G UI) | Must have |
| EESSI.NA.1 00 | Error Handling | Application Errors must be delivered to users in an unobtrusive manner, while providing sufficient information to understand the problem | Non- Functional | Present ation(G UI) | Must have |
| EESSI.NA.1 01 | Help | The system should provide context aware help for users | Non- Functional | Present ation(G UI) | Should have |

## 5 RINA Administration Console -Functional Specifications

## 5.1 Main Modules

This console includes all components for administering RINA installation. The services contained are consoles used by the privileged users to administer RINA. All Tenants in the same RINA Application share the following common application configuration and administration:

| Component | Description |
| --- | --- |
| Access Control Interfaces | The core function of Access Control Interfaces is to validate the required credentials of users, administrators or several applications accessing information or protected resources in the subsystem environment. There are sub-categories that can be used: • Localization Settings: to customize the administrator portal • Change Password : to change the administrator(s)' password • Help: to receive online contextual help about the usage of the Admin Portal |

| Component | Description |
| --- | --- |
|  | About RINA: to visualize the version specific information concerning the specific RINA component Installation (portal/server). • Login • Logout |
| Application Settings | The ' Application Settings ' component contains three major categories: • Tenant Settings: configures the Institutions/Liaison Body/etc1, that are defined as Tenants of the specific RINA Installation (via Add, Delete, Set Default and Enable/Disable actions) • General Settings: defines the general application settings • Case Counter Settings: defines the method to automatically generate the local Case ID (Case Management Identification counter) |
| Messaging Settings | The ' Messaging Settings ' component contains two major categories: • Global Messaging Settings that contain the definition of: the BMP validation method; the Authentication/Authorisation and Business Signature parameters; the transport protocol settings; the Antimalware settings; Local Messaging Settings contains shared Local Messaging Settings that are shared between all Tenants and specific settings of each Tenant. |
| NIE Settings | National Information Exchange (NIE) is a RINA stateful interface that allows participating countries to exchange information with their National Legacy Applications/Systems. Additionally, NIE allows RINA to receive documents and/or be notified when configurable events occur during the lifecycle of a Case and including its documents, based on subscriptions to specific events during the case handling lifecycle at both Case and Document levels. |
| IAM | IAM allows configuring users and groups in RINA. The settings are distinguished and independent between each RINA Tenant. The section is split in three subsections: Users, Groups and LDAP Configuration. |
| Authorisation | Authorisation is the administrative screen where the Administrator configures who gets access to resources in RINA. It consists of two main sections, Assignment Policies |

| Component | Description |
| --- | --- |
|  | and Process Assignments. Together, the policies provide the administrator with the tools required to manage and restrict control to cases in RINA. |
| Notification Centre | The Notification Centre provides the following functions: • Configuration of the critical notifications' parameters (i.e., retention & notification periods, etc.) • List of the received Notifications with the necessary filtering and navigation tools. In general, the notifications can be filtered by severity, type, status and grouped by date. Also, the navigation functionality can be used to easily select the notification of a specific time period. |
| Logging Console | The logging consoles (Audit Logs & Technical Logs) package provides the detailed views on the logs created at RINA deployment level. It contains |
| Archiving | Data archiving is the process of moving data that is no longer actively used to a separate storage device for long-term retention. Archive data consists of: • data that is not currently used but it is still important to the organization and it has to be available for any future reference, as well as • data that must be retained for regulatory compliance. The data archives serve as a way of reducing primary storage consumption and related costs, rather than acting as a data recovery mechanism. A data archive that can be used for litigation situations or contains sensitive data, should be treated as 'read - only' in order to protect it from any modification. |
| Automatic Updates | The Automatic Updates component is used to synchronise/configure either IR (Institution repository) or CDM (Common Data Model) retrieved from CSN, through the AP component. |
| Test Center | This Test Center component allows performing basic testing of RINA's network connectivity to EESSI International Domain. |
| Business Exceptions | The Business Exceptions component provide access to the settings related to operations on Business Exceptions and Pending Messages, such as: • Retrieve the business exceptions details • Submit a business exception • Retrieve the business exceptions time slots |

Status: Final / TLP: GREEN

| Component | Description |
| --- | --- |
|  | • Retrieve the SED content of the business exception • Retrieve the rejection SED content of the business exception • Retrieve the pending messages details • Retrieve the pending messages time slots • Retrieve the SED content of the pending message |

## 6 Interface Use Cases

## 6.1 Access Control Interfaces and Admin Settings

Use case diagrams

Use Case View

UC_ADM_01 Login Administrator

| Use Case ID: | UC_ADM_01 | UC_ADM_01 | UC_ADM_01 |
| --- | --- | --- | --- |
| Use Case Name: | Login Administrator | Login Administrator | Login Administrator |
| Actors: | System, Administrator | System, Administrator | System, Administrator |
| Description: | This use case (UC) describes how the Administrator can Login and get access to the functions related to the relevant role. This UC is performed in two steps: authentication (verification of the user identity using the submitted password) and authorization (granting access to the functions/data of the system according to the role of the user). | This use case (UC) describes how the Administrator can Login and get access to the functions related to the relevant role. This UC is performed in two steps: authentication (verification of the user identity using the submitted password) and authorization (granting access to the functions/data of the system according to the role of the user). | This use case (UC) describes how the Administrator can Login and get access to the functions related to the relevant role. This UC is performed in two steps: authentication (verification of the user identity using the submitted password) and authorization (granting access to the functions/data of the system according to the role of the user). |
| Trigger: | The Administrator opens a Web browser and types in the RINA application URL of the institution. | The Administrator opens a Web browser and types in the RINA application URL of the institution. | The Administrator opens a Web browser and types in the RINA application URL of the institution. |
| Preconditions: | N/A | N/A | N/A |
| Post conditions: | The Administrator can perform any action he is authorized to in the system. | The Administrator can perform any action he is authorized to in the system. | The Administrator can perform any action he is authorized to in the system. |
| Main Scenario: | \# | Step actions | Expected Result |
| Main Scenario: | 1 | The Administrator opens a Web browser and types in the RINA | The System opens 'RINA Home Page'. This page contains a Login button |

|  |  | application URL of the institution. |  |
| --- | --- | --- | --- |
|  | 2 | The Administrator clicks 'Login' button | The System opens 'RINA Login Page'. The System displays a notification in case a non-secure URL connection is established, in order to inform the Administrator. This page contains: • A free text field labelled 'Username:' where the Administrator enters his/her username • A free text field labelled 'Password:' where the Administrator enters his/her password |
|  | 3 | The Administrator enters the username and relevant password and clicks 'Login' button | • A Login button The System validates the provided credentials. The System redirects the Administrator to 'RINA Admin Console'. The System navigates the user to the home screen, which follows a certain basic structure throughout the application. The 'RINA Admin Console' screen layout consists in the following menu options: 1. 'Application Settings' 2. 'Messaging Settings' 3. 'NIE Settings' 4. 'RINA archiving' 5. 'IAM' 6. 'Authorization' 7. 'Logs' 8. 'Notifications Centre' 9. 'Automatic updates' 10. 'Test C enter' 11. 'Business exceptions' |
| Exception Flow 1 |  | The Administrator enters wrong credentials (username or password) | The Administrator authentication fails. The System displays the login page with the following error message: 'Invalid credentials'. |

## UC_ADM_02 Set up User Localization Settings

| Use Case ID: | UC_ADM_02 |
| --- | --- |
| Use Case Name: | Set up User Localization Settings |

| Actors: | System, Administrator | System, Administrator | System, Administrator |
| --- | --- | --- | --- |
| Description: | This use case describes how an Administrator can set up the localization settings: language, number format, data format, time format, currency, or time zone | This use case describes how an Administrator can set up the localization settings: language, number format, data format, time format, currency, or time zone | This use case describes how an Administrator can set up the localization settings: language, number format, data format, time format, currency, or time zone |
| Trigger: | The Administrator clicks on the user icon from the main menu and then clicks on the 'Localization Settings' option. | The Administrator clicks on the user icon from the main menu and then clicks on the 'Localization Settings' option. | The Administrator clicks on the user icon from the main menu and then clicks on the 'Localization Settings' option. |
| Preconditions: | 1\. The Administrator is authenticated in RINA (UC_CPI_01) | 1\. The Administrator is authenticated in RINA (UC_CPI_01) | 1\. The Administrator is authenticated in RINA (UC_CPI_01) |
| Post conditions: | The new localization settings are saved at user level and will be used for: • Language: All RINA UI messages (labels, value lists, error messages, notifications, etc) of the Admin Portal are given in the selected language • Number/Date/Time format and Time Zone: displays the Numbers, Dates and Time in the selected format and the correct Time Zone is applied • Currency: currently not used | The new localization settings are saved at user level and will be used for: • Language: All RINA UI messages (labels, value lists, error messages, notifications, etc) of the Admin Portal are given in the selected language • Number/Date/Time format and Time Zone: displays the Numbers, Dates and Time in the selected format and the correct Time Zone is applied • Currency: currently not used | The new localization settings are saved at user level and will be used for: • Language: All RINA UI messages (labels, value lists, error messages, notifications, etc) of the Admin Portal are given in the selected language • Number/Date/Time format and Time Zone: displays the Numbers, Dates and Time in the selected format and the correct Time Zone is applied • Currency: currently not used |
| Main Scenario: | \# | Step actions | Expected Result |
|  | 1 | The Administrator clicks on the user icon from the main menu. | The System displays a contextual menu with the following menu options: • 'Localization Settings' • 'Change Password' • 'Help' • 'Logout' |
|  | 2 | The Administrator clicks on the 'Localization Settings' option | The System displays 'Localization Settings' form. This page contains: • a drop-down list field labelled 'Language \*' where the user can select the language of the UI. The languages used by the participating countries are available • a drop-down list field labelled 'Number Format \*' where the user can select the format of numbers. The possible options are: o 1.000,00 o 1,000.00 o 1 000.00 o 1000,00 o 1000.00 o 1 000,00 • a drop-down list field labelled 'Date Format \*' where the user must select the format of the date |

|  |  |  | from the provided list of available date formats • a drop-down list field labelled 'Time Format \*' where the user must select the default time format • a drop-down list field labelled 'Currency \*' where the user must select the default currency from the list of available currencies • a drop-down list field labelled 'Time Zone *' where the user must select the default time zone from the list of available time zones. The '*' character from all the labels of the fields mean that they are mandatory. All the fields are pre- populated with default values (as per set up of the administrator). The form also contains: • 'Reset' button • 'Save' button • 'Back' button |
| --- | --- | --- | --- |
|  | 3 | The user selects the desired values of the localization fields and clicks on the 'Save' button | The System closes 'Localization Settings' form. The System saves all values in the server. Remark: • 'Language'. The selected language is applied: - for all the labels and list of values displayed in RINA screens and for all the error messages text - for the Translate link inside the received SEDs • 'Number/Date/Time Format' and 'Time Zone': the specific values are displayed in the selected format The value(s) on the field(s) are |
| Alternate Scenario 1 |  | The Administrator make changes in one or more fields and clicks 'Reset' button | discarded and the fields values are reloaded from the server. |
| Alternate Scenario 2 |  | The Administrator clicks 'Back' button | The System closes 'Localization Settings' form and returns to previous form. |

| Exception Flow 1 | The Administrator selects the blank value for one or more fields and clicks on the 'Save' | The System displays the field(s) with blank value and displays them marked in red. |
| --- | --- | --- |

## UC_ADM_03 Change Administrator Password

| Use Case ID: | UC_ADM_03 | UC_ADM_03 | UC_ADM_03 |
| --- | --- | --- | --- |
| Use Case Name: | Change Administrator Password | Change Administrator Password | Change Administrator Password |
| Actors: | System, Administrator | System, Administrator | System, Administrator |
| Description: | This use case describes how an Administrator changes his own password | This use case describes how an Administrator changes his own password | This use case describes how an Administrator changes his own password |
| Trigger: | The Administrator clicks on user icon and then clicks 'Change Password' option. | The Administrator clicks on user icon and then clicks 'Change Password' option. | The Administrator clicks on user icon and then clicks 'Change Password' option. |
| Preconditions: | The Administrator is authenticated in RINA | The Administrator is authenticated in RINA | The Administrator is authenticated in RINA |
| Post conditions: | The Administrator password is changed and can be used for future logins | The Administrator password is changed and can be used for future logins | The Administrator password is changed and can be used for future logins |
| Main | \# | Step actions | Expected Result |
| Scenario: | 1 | The Administrator clicks on the user icon from the main menu. | The System displays a contextual menu with the following options: • 'Localization Settings' • 'Change Password' • 'Help' • 'Logout' |
|  | 2 | The Administrator clicks 'Change Password' option | The System displays 'Change Password ' form. This page contains: • a free- text field labelled 'Old password\*:' where the Administrator must enter his current password • a free- text field labelled 'New password\*:' where the Administrator must enter the new password • a free- text field labelled 'Confirm new password\*: ' where the Administrator must enter again the new password As the \* from all the fields suggests, all are mandatory. The form also contains: • 'Reset' button • 'Save' button • 'Back' button |

|  | 3 | The Administrator enters the old and the new password in the dedicated fields and clicks on the 'Save' button. | The System compares values entered in fields 'Old password' and 'New password' of the user. The System saves the new password in the server which can be used for future logins. The System closes 'Change pa ssword' form. |
| --- | --- | --- | --- |
| 1 | The Administrator make changes in one or more fields and clicks on the 'Reset' button | The value(s) on the field(s) are discarded and the fields values are reloaded from the server. | Alternate Scenario 1 |
| 1 | The Administrator clicks on the 'Back' button | The System closes 'Change Password' form and returns to previous form. | Alternate Scenario 2 |
| 1 | The Administrator enters different values in fields 'New password:\*' and 'Confirm new password: \*' and clicks on 'Save' button | The System displays the field 'Confirm new password: \*' marked in red and an error message is displayed under the field: 'Password must match'. The Administrator can re-enter the value for this field and resume the main scenario. | Exception Flow 1 |
| 1 | The Administrator enters a wrong value in the 'Old password: \*' field and values for the new and old password and clicks on the ' Sav e' button | The System displays the error message: 'Old password of user does not match'. The Administrator can re-enter the value for this field and resume the main scenario | Exception Flow 2 |
| 1 | The Administrator enters a value shorter than 8 characters in the 'New password: \*' field and leaves the field. | The System marks the field 'New password: \*' in red and an error message is displayed under the field: 'Password must be at least 8 characters' The Administrator can re-enter the value for this field and resume the main scenario | Exception Flow 3 |

## UC_ADM_04 Access contextual Help

| Use Case ID: | UC_ADM_04 |
| --- | --- |
| Use Case Name: | Access contextual Help |
| Actors: | System Administrator |
| Description: | This use case describes how an Administrator accesses the Contextual Help - ' RINA Help Manual '. |
| Trigger: | The Administrator clicks on User icon and then clicks 'Help' option. |

UC_ADM_05 Logout User

| Preconditions: | 1\. The user is authenticated in RINA. | 1\. The user is authenticated in RINA. | 1\. The user is authenticated in RINA. |
| --- | --- | --- | --- |
| Post conditions: | The user consulted the ' RINA Help Manual ' . | The user consulted the ' RINA Help Manual ' . | The user consulted the ' RINA Help Manual ' . |
| Main | \# | Step actions | Expected Result |
| Scenario: | 1 | The Administrator clicks on the user icon from the main menu | The System displays a contextual menu with the following options: • 'Localization Settings' • 'Change Password' • 'Help' 'Logout' |
|  | 2 | The Administrator clicks on the 'Help' option | • The System opens in a new browser window/tab - 'Rina Help Manual' . The content shown is specific for the step where the user is. This window displays the content of the Administrator Manual in an easy to navigate form. This content is available only in English. The System displays the following fields: • A free text 'Search' field where the user can enter the text and press enter to launch the search of the entered text in the content of the admin manual. The system provides/adapts the search results automatically as the Administrator types the input in the Search field • A table of content where each entry is a link that allows the Administrator to access the specific content directly |
|  | 3 | The Administrator navigates via the 'Search' functionality or by clicking on the topic of interest from the table on content. The Administrator has access to read the available information. Optionally the Administrator closes the browser window/tab. | The System closes ' Rina Help Manual' . The Administrator can also leave the 'Rina Help Manual ' window open and continue his/her work in RINA, and meanwhile consult needed information in the manual. |

| Use Case ID: | UC_ADM_05 | UC_ADM_05 | UC_ADM_05 |
| --- | --- | --- | --- |
| Use Case Name: | Logout User | Logout User | Logout User |
| Actors: | System administrator | System administrator | System administrator |
| Description: | This use case describes how an Administrator can logout from the application. | This use case describes how an Administrator can logout from the application. | This use case describes how an Administrator can logout from the application. |
| Trigger: | The Administrator clicks user icon and then clicks 'Logout' option. | The Administrator clicks user icon and then clicks 'Logout' option. | The Administrator clicks user icon and then clicks 'Logout' option. |
| Preconditions: | 1\. The Administrator is authenticated in RINA. | 1\. The Administrator is authenticated in RINA. | 1\. The Administrator is authenticated in RINA. |
| Post conditions: | The Administrator is logged out from application. | The Administrator is logged out from application. | The Administrator is logged out from application. |
| Main Scenario: | \# | Step actions | Expected Result |
|  | 1 | The Administrator clicks on the user icon from the main menu | The System displays a contextual menu with the following options: • 'Localization Settings' • 'Change Password' • 'Help' • 'Logout' |
|  | 2 | The Administrator clicks on the 'Logout' option | The user is logged out. The application displays the ' RINA Home Page' where the user has the possibility to log in again. |

## Fields Details

## Admin -Localisation Settings

| No. | Item name | Type | Validation/ business rules |
| --- | --- | --- | --- |
| 1 | Language | List | Mandatory, contains values chars |
| 2 | Number Format | List | Mandatory, contains numbers |
| 3 | Date Format | List | Mandatory, contains values type date |
| 4 | Time Format | List | Mandatory, contains values type time (hh:mm) |
| 5 | Currency | List | Mandatory, contains values chars |
| 6 | Time Zone | List | Mandatory, contains values type zone |
| 7 | Save | Button |  |
| 8 | Reset | Button |  |

## Admin -Change Password

| No. | Item name | Type | Validation/business rules |
| --- | --- | --- | --- |
| 1 | Old password | Free text box field | Mandatory, use visible/invisible functionality |

Status: Final / TLP: GREEN

| 2 | New password | Free text box field | Mandatory, use visible/invisible functionality |
| --- | --- | --- | --- |
| 3 | Confirm new password | Free text box field | Mandatory, use visible/invisible functionality |
| 4 | Save | Button |  |
| 5 | Reset | Button |  |

## 6.2 Application Settings

Use case diagrams

Use Case View

UC_AS_01 Add new tenant

| Use Case ID: | UC_AS_01 |
| --- | --- |
| Use Case Name: | Add new tenant |

| Description: | This use case describes how the Administrator adds a new tenant (The Administrator defines and configures the Institutions that are defined as Tenants in the RINA) | This use case describes how the Administrator adds a new tenant (The Administrator defines and configures the Institutions that are defined as Tenants in the RINA) | This use case describes how the Administrator adds a new tenant (The Administrator defines and configures the Institutions that are defined as Tenants in the RINA) |
| --- | --- | --- | --- |
| Trigger: | The Administrator clicks on 'Application Settings' menu option and then 'Tenant Settings' option. | The Administrator clicks on 'Application Settings' menu option and then 'Tenant Settings' option. | The Administrator clicks on 'Application Settings' menu option and then 'Tenant Settings' option. |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized as an administrator of the system. 3. The institution to be added as Tenant belongs to the same AP as the Default Tenant and they are part to the Institution Repository | 1\. The user is authenticated in RINA. 2. The user is authorized as an administrator of the system. 3. The institution to be added as Tenant belongs to the same AP as the Default Tenant and they are part to the Institution Repository | 1\. The user is authenticated in RINA. 2. The user is authorized as an administrator of the system. 3. The institution to be added as Tenant belongs to the same AP as the Default Tenant and they are part to the Institution Repository |
| Post conditions: | (IR). The new Tenant is added, and it is visible in the system. The list with existing tenants is updated accordingly. The simple addition of a new Tenant is not enough to have a fully functional Tenant. For a Tenant, new or existing, to be operational, all its tenant specific configurations should be successfully completed ('Valid Messaging Configurat ion', 'IAM' and 'Authorization Settings', 'Case Counter Settings'). | (IR). The new Tenant is added, and it is visible in the system. The list with existing tenants is updated accordingly. The simple addition of a new Tenant is not enough to have a fully functional Tenant. For a Tenant, new or existing, to be operational, all its tenant specific configurations should be successfully completed ('Valid Messaging Configurat ion', 'IAM' and 'Authorization Settings', 'Case Counter Settings'). | (IR). The new Tenant is added, and it is visible in the system. The list with existing tenants is updated accordingly. The simple addition of a new Tenant is not enough to have a fully functional Tenant. For a Tenant, new or existing, to be operational, all its tenant specific configurations should be successfully completed ('Valid Messaging Configurat ion', 'IAM' and 'Authorization Settings', 'Case Counter Settings'). |
| Main Scenario: | \# 1 | Step actions The Administrator clicks | Expected Result The System displays 'Tenant |
|  | 2 | The Administrator starts typing in the 'Add Tenant' field. | The System displays a list with institutions which meet the criteria. |
|  | 3 | The Administrator selects the desired | The System displays the selected institution in 'Add Tenant' field and the '+' and 'x' buttons are enabled . |
|  | 4 | institution from the list The Administrator clicks on the '+' button. | The System displays the 'Confirmation' form, which contains: |

|  |  | • The following text field 'You are about to add the tenant:' and the identification attributes of the selected institution • 'Yes' button • 'No' button |
| --- | --- | --- |
| 5 | The Administrator clicks on the 'Yes ' button | The System closes 'Confirmation' pop-up window. The System displays the messages: 'Tenant settings successfully added'. 'Please update the Local Messaging Settings of the newly added Tenant.' The list with tenants is updated accordingly and the new added tenant is displayed in the grid of tenants. In the 'Status' column, the new tenant has the value 'Disabled'. Remark: The simple addition of a new Tenant in the 'Tenant Settings' form is not enough to have a fully functional tenant. The Administrator also needs to specify: • The valid messaging configuration: 'Global Messaging Settings' and 'Local Messaging settings' should be modified and set accordingly. o Authorisation Private Key and Business Signature default certificate of the Tenant should be added in the ' Messaging Settings ' o Next, the above elements should be paired with their passwords in the ' Local Messaging Settings ' • The IAM and Authorisation Settings for the new Tenant should also be modified accordingly. In more details: o At least one Group and one regular User should be added for the new Tenant o The user should have at least membership 'Supervisor' and 'Authorized' to this Group to be assigned with enough access rights in each case instance o A 'Case Creator' Assignment Policy and a 'supervisor' |

Status: Final / TLP: GREEN

|  |  | Assignment Policy should be added and related to this User. Both policies could be grouped to a group policy o For each sector and BUC, for this user to be automatically assigned (either in case of Case Owner or Counter Party) to case instances, the previous 'creator' and 'supervisor' policy (or the group policy) should be assigned to the relevant processes. • The Case Counter Settings. The Case Counter Settings are Tenant dependent, and it is not necessary to be configured by the administrator since a default value is used. |
| --- | --- | --- |
| 1 | The Administrator clicks the 'No ' button | Alternative scenario 1 The System discards all changes. The System closes ' Confirmation ' |
| 1 | The Administrator clicks 'Refresh' button | Alternative Scenario 2 The System redisplays the form 'Tenant Settings'. |

## UC_AS_02 Deleting tenants

| Use Case ID: | UC_AS_02 | UC_AS_02 | UC_AS_02 |
| --- | --- | --- | --- |
| Use Case Name: | Deleting tenants | Deleting tenants | Deleting tenants |
| Actors: | System, Administrator | System, Administrator | System, Administrator |
| Description: | This use case describes how the Administrator deletes a Tenant | This use case describes how the Administrator deletes a Tenant | This use case describes how the Administrator deletes a Tenant |
| Trigger: | The Administrator clicks 'Application Settings' menu option, clicks on 'Tenant Settings' option and then clicks in the 'Delete' button. | The Administrator clicks 'Application Settings' menu option, clicks on 'Tenant Settings' option and then clicks in the 'Delete' button. | The Administrator clicks 'Application Settings' menu option, clicks on 'Tenant Settings' option and then clicks in the 'Delete' button. |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized as an administrator of the system. 3. The tenant has no active cases (cases which are not closed or archived) or business Users. 4. The tenant is not set as a Default tenant | 1\. The user is authenticated in RINA. 2. The user is authorized as an administrator of the system. 3. The tenant has no active cases (cases which are not closed or archived) or business Users. 4. The tenant is not set as a Default tenant | 1\. The user is authenticated in RINA. 2. The user is authorized as an administrator of the system. 3. The tenant has no active cases (cases which are not closed or archived) or business Users. 4. The tenant is not set as a Default tenant |
| Post conditions: | The system removed the tenant from the tenant's list, the tenant will no longer be visible on the list. | The system removed the tenant from the tenant's list, the tenant will no longer be visible on the list. | The system removed the tenant from the tenant's list, the tenant will no longer be visible on the list. |
| Main Scenario: | \# | Step actions | Expected Result |
| Main Scenario: | 1 | The Administrator clicks on the ' Application Settings ' main menu option, and from the displayed options, clicks on the 'Tenant Settings' option . | The System displays 'Tenant Settings' form, containing: • a field labelled 'Add Tenant' with Institution free text 'Search' functionality enabled. Only institutions belonging to the same AP as the Default tenant are available. |

|  |  |  | • a button '+' disabled • a button 'x' disabled • a grid displaying the existing tenants, with the following header o 'Tenant': column for displaying the institution identifier o 'Is Default': column for displaying if tenant is the default one o 'Status' o 'Actions', with associated buttons 'Set Default', 'Enable', 'Delete'. For the default tenant, the 'Actions' column is empty. o 'Refresh' button |
| --- | --- | --- | --- |
|  | 2 | The Administrator identifies the tenant to be deleted in the display grid and clicks on the 'Delete' button from the 'Actions' column | The System displays the 'Confirmation' form. In this form, the Administrator has available: • the message : ' You are about to delete the tenant' and the identification attributes of the institution to be deleted as tenant. • 'Yes' button • 'No' button - when clicked, it closes the 'Confirmation' form, without saving the deletion. |
|  | 3 | The Administrator clicks on the 'Yes' button | The System deletes the existing institution as a Tenant from the RINA instance. The System closes the ' Confirmation ' form. The list with tenants is updated accordingly, and the deleted tenant is no longer displayed in the tenants' grid. |
| Alternative Scenario 1 | 1 | The Administrator clicks 'Refresh' button | The System redisplays the form 'Tenant Settings'. |
| Exception flow 1 | 1 | The Administrator identifies for deletion a tenant that still has active cases and/or users and clicks on the 'Delete' button | The System displays the error message: 'Error deleting tenant: Cannot delete tenant because it contains active cases!' The System does not delete the tenant. |

## UC_AS_03 Set Tenant as default

| Use Case ID: | UC_AS_03 | UC_AS_03 | UC_AS_03 |
| --- | --- | --- | --- |
| Use Case Name: | Set tenant as default | Set tenant as default | Set tenant as default |
| Actors: | System, Administrator | System, Administrator | System, Administrator |
| Description: | This use case describes how the Administrator sets a Tenant as Default tenant | This use case describes how the Administrator sets a Tenant as Default tenant | This use case describes how the Administrator sets a Tenant as Default tenant |
| Trigger: | The Administrator clicks 'Application Settings' menu option, clicks on 'Tenant Settings' option and then clicks 'Set Default' button. | The Administrator clicks 'Application Settings' menu option, clicks on 'Tenant Settings' option and then clicks 'Set Default' button. | The Administrator clicks 'Application Settings' menu option, clicks on 'Tenant Settings' option and then clicks 'Set Default' button. |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application |
| Post conditions: | The System sets up the Default tenant (the Default Tenant cannot be deleted, 'Set default', 'Disable', 'Delete' buttons are not available) | The System sets up the Default tenant (the Default Tenant cannot be deleted, 'Set default', 'Disable', 'Delete' buttons are not available) | The System sets up the Default tenant (the Default Tenant cannot be deleted, 'Set default', 'Disable', 'Delete' buttons are not available) |
| Main Scenario: | \# | Step actions | Expected Result |
| Main Scenario: | 1 | The Administrator clicks on the ' Application Settings ' main menu option, and from the displayed options, clicks on the 'Tenant Settings' option. | The System displays 'Tenant Settings' form, containing: • a field labelled 'Add Tenant' with Institution free text 'Search' functionality enabled. Only institutions belonging to the same AP as the Default tenant are available. • a button '+' disabled • a button 'x' disabled • a grid displaying the existing tenants, with the following header o 'Tenant': column for displaying the institution identifier o 'Is Default': column f or displaying if tenant is the default one o 'Status' o 'Actions', with associated buttons 'Set Default', 'Enable', 'Delete'. For the default tenant, the 'Actions' column is empty. • 'Refresh' button |
|  | 2 | The Administrator identifies the tenant to be set as default in the display grid and clicks on the 'Set Default' button from the 'Actions' column | The System displays the 'Confirmation' form. In this form, the Administrator has available: • the information message: ' You are about to set as default the tenant:' and the identification attributes of the institution that was selected • 'Yes' button • 'No' button |
|  | 3 | The Administrator clicks 'Yes ' button | The System closes 'Confirmation' form. |

Status: Final / TLP: GREEN

|  |  | In the tenants' grid, the details of the selected tenant and the old default tenant are updated accordingly: • the selected tenant is set as Default tenant • for the old default tenant, in the 'Is Default' column, the value is changed to not default and in the 'Actions' column the associated buttons 'Set Default', 'Enable', 'Delete' are displayed |
| --- | --- | --- |
| 1 | The Administrator clicks 'No' button | Alternative Scenario 1 The System discards all changes. The System closes the 'Confirmation' form. |
| 1 | The Administrator clicks 'Refresh' button | Alternative Scenario 2 The System redisplays the form 'Tenant Settings'. |

UC_AS_04 Switching Enabled / Disabled status for tenant

| Use Case ID: | UC_AS_04 | UC_AS_04 | UC_AS_04 |
| --- | --- | --- | --- |
| Use Case Name: | Switching Enable / Disable status for tenant | Switching Enable / Disable status for tenant | Switching Enable / Disable status for tenant |
| Actors: | System, Administrator | System, Administrator | System, Administrator |
| Description: | This use case describes how the Administrator switches the 'Enabled/Disabled' status for tenants by clicking on the appropriate button (for enabled status the associated icon is green, for disabled status the associated icon is red; enabled status gives the possibility to insert, change parameters) | This use case describes how the Administrator switches the 'Enabled/Disabled' status for tenants by clicking on the appropriate button (for enabled status the associated icon is green, for disabled status the associated icon is red; enabled status gives the possibility to insert, change parameters) | This use case describes how the Administrator switches the 'Enabled/Disabled' status for tenants by clicking on the appropriate button (for enabled status the associated icon is green, for disabled status the associated icon is red; enabled status gives the possibility to insert, change parameters) |
| Trigger: | The Administrator clicks 'Application Settings' menu option, t hen 'Tenant Settings' option and clicks 'Enable/Disabled' button | The Administrator clicks 'Application Settings' menu option, t hen 'Tenant Settings' option and clicks 'Enable/Disabled' button | The Administrator clicks 'Application Settings' menu option, t hen 'Tenant Settings' option and clicks 'Enable/Disabled' button |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized to access RINA Application with the Administrator role 3. The tenant should not be set up as Default tenant | 1\. The user is authenticated in RINA. 2. The user is authorized to access RINA Application with the Administrator role 3. The tenant should not be set up as Default tenant | 1\. The user is authenticated in RINA. 2. The user is authorized to access RINA Application with the Administrator role 3. The tenant should not be set up as Default tenant |
| Post conditions: | The user switches between Enable/Disable tenant status | The user switches between Enable/Disable tenant status | The user switches between Enable/Disable tenant status |
| Main Scenario: | \# | Step actions | Expected Result |

Status: Final / TLP: GREEN

|  |  |  | o 'Is Default': column for displaying if tenant is the default one o 'Status' o 'Actions', with associated buttons 'Set Default', 'Enable', 'Delete'. For the default tenant, the 'Actions' column is empty. |
| --- | --- | --- | --- |
|  | 2 | The Administrator clicks on the 'Enabled/Disabled' button | 'Refresh' button The System displays the 'Confirmation' form. In this form, the Administrator has available: • An information message: ' You are about to disable the tenant:' and the identification attributes of the institution that was selected • 'Yes' button • 'No' button |
|  | 3 | The Administrator clicks on the 'Yes ' button | The System closes the 'Confirmation' form. Notes: In case the Administrator clicks on the 'Disable' button, the 'Status' column is updated with status 'Disabled' and the 'Set Default' button is disabled. (a disabled tenant cannot be set as Default). In case the Administrator clicks on the 'Enable' button, the 'Status' column is updated with status 'Enabled' and the 'Set Default' button is enabled. |
| Alternate Scenario 1 | 1 | The Administrator clicks 'No' | The System discards all changes. The System closes the 'Confirmation' form. |
| Exception flow 1 | 1 | The administrator clicks on the 'Disable' button corresponding to a tenant that has active cases | The System checks opened cases related to this institution. The System does not allow disabling tenants in opened cases. |
|  | 2 | The Administrator clicks 'Yes' for confirming the existence of opened cases related to this institution | The System display a warning message. The System disable the action. |
| Alternative Scenario 2 | 1 | The Administrator clicks 'No' for confirming the non-existence of opened | The System discards all changes. The System closes 'Confirmation' pop-up window. |

Status: Final / TLP: GREEN

| cases related to this institution |
| --- |

## UC_AS_05 Set Case Settings Default area

| Use Case ID: | UC_AS_05 | UC_AS_05 | UC_AS_05 |
| --- | --- | --- | --- |
| Use Case Name: | Set Case Settings Default area | Set Case Settings Default area | Set Case Settings Default area |
| Actors: | System, Administrator | System, Administrator | System, Administrator |
| Description: | This use case describes how the Administrator fills in and sets up the Case Settings default area. | This use case describes how the Administrator fills in and sets up the Case Settings default area. | This use case describes how the Administrator fills in and sets up the Case Settings default area. |
| Trigger: | The Administrator clicks on the 'Default Case Settings' option from 'Application Settings' menu option. | The Administrator clicks on the 'Default Case Settings' option from 'Application Settings' menu option. | The Administrator clicks on the 'Default Case Settings' option from 'Application Settings' menu option. |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application |
| Post conditions: | The Administrator set up Default Case Settings area. An audit event is raised into | The Administrator set up Default Case Settings area. An audit event is raised into | The Administrator set up Default Case Settings area. An audit event is raised into |
| Main Scenario: | \# | Step actions | Audit Log. Expected Result |
| Main Scenario: | 1 | The Administrator clicks on the ' Application Settings ' main menu option, and from the displayed options, clicks on the 'Default Case Settings ' option. | The System displays the 'Default case Settings' form, with the following fields: • an area labelled 'Documents', used to define the Documents preferable view and the way of sorting, with: o a selection field labelled 'View mode'- with possible values 'Classical View' and 'Timeline View' o a selection field labelled 'Sort by'- with possible values 'Creation ' and 'Last Update' o a check box field labelled 'Display Flags ' • a dynamic area, labelled and populated based on the selection in the 'View Mode' field • an area labelled 'Alarm Settings', with: o a checkbox field -when clicked it enables the counter field for setting up the number of days o a counter field that allows the user to set up a numerical value for the number of days for the alarm. • a 'Reset' button • a 'Save' button |
|  | 2 | The Administrator select the 'Classic View' value for the 'View Mode' field | The dynamic area is labelled 'Classic View', and contains: |

|  |  |  | o a checkbox field labelled 'Group by Month' |
| --- | --- | --- | --- |
|  | 3 | The Administrator chooses to check/uncheck the flag 'Display Flags' | The System displays the checked/unchecked 'Display Flags ' |
|  | 4 | The Administrator chooses to check the checkbox field ' Auto set Alarm on Send Action', related to 'Alarm Settings ' area | The System enables the counter field where the Administrator can input the number of days. |
|  | 5 | The Administrator chooses to uncheck the checkbox field ' Auto set Alarm on Send Action ' , related to 'Alarm Settings ' area | The System disables the counter field. |
|  | 6 | The Administrator clicks on the 'Save ' button. | The System displays the message 'Case Settings successfully saved'. |
| Alternative scenario 1 | 1 | The Administrator select the 'Timeline View' value for the 'View Mode' field | The dynamic area is labelled 'Timeline View', and contains: a selection field labelled 'Display Mode' with possible values '1 Column' and '2 Columns' |
| Alternative Scenario 2 | 1 | The Administrator clicks the 'Reset' button | The System redisplays the form 'Default Case Settings'. |

## UC_AS_06 Set User Profile Default Area

| Use Case ID: | UC_AS_06 | UC_AS_06 | UC_AS_06 |
| --- | --- | --- | --- |
| Use Case Name: | Set User Profile Default area | Set User Profile Default area | Set User Profile Default area |
| Actors: | System, Administrator | System, Administrator | System, Administrator |
| Description: | This use case describes how the Administrator fills in the 'Default User Profile' available options. This profile is applicable to (used as a setting by) any user that has not performed changes under their own corresponding User Profile settings. | This use case describes how the Administrator fills in the 'Default User Profile' available options. This profile is applicable to (used as a setting by) any user that has not performed changes under their own corresponding User Profile settings. | This use case describes how the Administrator fills in the 'Default User Profile' available options. This profile is applicable to (used as a setting by) any user that has not performed changes under their own corresponding User Profile settings. |
| Trigger: | The Administrator selects 'Default User Profile' option from the 'Application Settings' menu option | The Administrator selects 'Default User Profile' option from the 'Application Settings' menu option | The Administrator selects 'Default User Profile' option from the 'Application Settings' menu option |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized as RINA administrator | 1\. The user is authenticated in RINA. 2. The user is authorized as RINA administrator | 1\. The user is authenticated in RINA. 2. The user is authorized as RINA administrator |
| Post conditions: | The Administrator set up the 'Default User Profile' options. An audit event is raised into Audit Log. | The Administrator set up the 'Default User Profile' options. An audit event is raised into Audit Log. | The Administrator set up the 'Default User Profile' options. An audit event is raised into Audit Log. |
| Main Scenario: | \# | Step actions | Expected Result |
| Main Scenario: | 1 | The Administrator clicks on the 'Default User Profile' option, available from the 'Application Settings' menu option. | The System displays the 'Default User Profile' form with following mandatory drop-down list fields: • 'Language\*' - contains all European languages |

Status: Final / TLP: GREEN

|  |  |  | • 'Number Format\*' - 6 possible number formats are available as described in the relevant field of UC_ADM_02 • 'Date Format\*' - includes all types of data format • 'Time Format\*' - includes all types of time format • 'Currency\*' - includes all types of European currencies • 'Time zone\*' - all time zones (All the settings are applied to all RINA users as default settings. After any customisation at user level, the user does not use the default setting but the customised ones) |
| --- | --- | --- | --- |
|  | 2 | The Administrator chooses from mandatory drop-down list fields his preferences and clicks on the 'Save' button | The System displays the message 'Default User Profile successfully saved'. The System saves the settings related to 'Localization Settings ' section. |
| Alternative Scenario 1 | 1 | The Administrator clicks on the 'Reset' button | The System discards all value(s) from the field(s) and the fields values are reloaded from the server. |

## UC_AS_07 Set up main area parameters

| Use Case ID: | UC_AS_07 | UC_AS_07 | UC_AS_07 |
| --- | --- | --- | --- |
| Use Case Name: | Set Up Main Area Parameters | Set Up Main Area Parameters | Set Up Main Area Parameters |
| Actors: | System, Administrator | System, Administrator | System, Administrator |
| Description: | This use case describes how the Administrator sets up Main Area parameters | This use case describes how the Administrator sets up Main Area parameters | This use case describes how the Administrator sets up Main Area parameters |
| Trigger: | The Administrator clicks on the 'General Settings' option from 'Application Settings' menu option | The Administrator clicks on the 'General Settings' option from 'Application Settings' menu option | The Administrator clicks on the 'General Settings' option from 'Application Settings' menu option |
| Preconditions: | 1\. The user is authenticated in RINA 2. The user is authorized as RINA administrator 3. The user is performing updates only related to the fields in the main section | 1\. The user is authenticated in RINA 2. The user is authorized as RINA administrator 3. The user is performing updates only related to the fields in the main section | 1\. The user is authenticated in RINA 2. The user is authorized as RINA administrator 3. The user is performing updates only related to the fields in the main section |
| Post conditions: | The Administrator has setup main area parameters. An audit event is raised into Audit Log. | The Administrator has setup main area parameters. An audit event is raised into Audit Log. | The Administrator has setup main area parameters. An audit event is raised into Audit Log. |
| Main Scenario: | \# | Step actions | Expected Result |
| Main Scenario: | 1 | The Administrator clicks on the 'General Settings' option available from 'Application Settings' menu option | The System displays the 'General Settings' form with the following fields: • ' Use Application Id ' : |

| o with a checkbox field - when selected, the free text field is enabled. o a free text field for entering the identifier of the application id to be used. This setting is used to identify the sending and receiving application for 'Intelligent routing' on AP level. The 'Intelligent Routing' function can automatically route messages depending on certain attributes. One of the attributes is the 'Application Id'. For example, one institution could have different RINA deployment instances which use the same Institution Id, but different Application Ids based on different competences; one 'Application Id' can be used for Pensions and Sickness sectors (i.e., ' application1 ' ) and another one for AWOD (i.e., ' application2 ' ). • ' Languages\* ' : This option allows the administrator to select the list of the languages available to all users of this application. A default language proposed to new users (along with other settings) is defined in the 'Default User Profile' form. • ' Max Idle Time (in minute s) \*': The Administrator can configure and set the 'Maximum Idle Time' for the users/clients until disconnecting them from the system. The default value is set to 15 minutes and the timer is reset by any action of the GUI. The duration of the connection of the users/clients to RINA depends also to the thresholds that have been set for the Session time (these timers are refreshed only when a CPI call is performed). • ' Case Search Results Maximum Limit ' : The Administrator can configure the maximum number of cases to be displayed when performing a case search • 'Organization System Password': Sets the Organization system password (System User Password) that is the password of the BPM engine. |
| --- |

| • An area labelled SEDs where the Administrator has available: o a selection field labelled 'SED Validation Mode', where the Administrator can configure how the application should validate a SED in the backend components. For this, the following 3 options are available to choose from: ▪ 'Continue When No Validation' - when selected, the validation is activated but the process continues even if validation criteria are not met ▪ 'Exception When No Validation' - when selected the process does not continue when an exception occurs ▪ 'No Validation' - when selected, no validation is performed, and the SED can be saved/submitted anyway o a counter field labelled 'Maximum number of Child Documents in Bulk SED \*' - mandatory list box, allows to setup the limit for the number of child documents (individual claims) under the bulk SEDs (containing the global claims). • An area labelled ' Errors ' , containing the following fields: o a checkbox field labelled 'Show Full Error Information' - when checked, the application provides more information in the stack trace in case of an error. By default, this is not enabled. o a checkbox field labelled 'Show Process Version' - when checked, the application shows the version of a process (BUC) along with its name. By default, this is not enabled, but it can be used for testing or other purposes. • An area labelled 'Attachments' that contains: o a free text field labelled 'Attachment Directory Path \*' o a counter field labelled 'Attachment Maximum File Size (in MB)' - allows the |
| --- |

|  |  | maximum file size of case attachments (per attachment) that can be uploaded in RINA application. The default value is 10Mbytes and the maximum permitted value is 1.024 Mbytes. o a selection field labelled 'Attachment Allowed Mime Types' that: ▪ displays the allowed file types that may be attached to a case/SED ▪ allows the Administrator to delete a predefined file type from the list by clicking on \[x\] ▪ allows the Administrator to add other types that are not included by clicking on ADD button associated to a text field in bottom of the section. • A n area labelled 'Default Values (Importance - Criticality)' where the default importance and criticality levels for new cases that will be submitted can be configured. This area contains the following fields: o a selection field labelled 'Importance' where the Administrator can select from possible values 'Normal' and 'High' o a selection field labelled 'Criticality' where the Administrator can select from possible values 'Normal' and 'High' The importance/ criticality may be changed for each case afterwards; this just sets the implicit/default values. • a 'Reset' button • a 'Save' button |
| --- | --- | --- |
| 2 | The Administrator selects the desired values and clicks on the 'Save' button | The System saves the data on server. The System displays the message: 'General Settings successfully saved.' |

Status: Final / TLP: GREEN

| Alternative scenario 1 | 1 | The Administrator clicks on the 'Reset' button | The system discards all values changed by the Administrator and displays the values saved on server. |
| --- | --- | --- | --- |

## UC_AS_08 Set Up Case Counter Settings -Default Scenario

| Use Case ID: | UC_AS_08 | UC_AS_08 | UC_AS_08 |
| --- | --- | --- | --- |
| Use Case Name: | Set Up Case Counter Settings - Default Scenario | Set Up Case Counter Settings - Default Scenario | Set Up Case Counter Settings - Default Scenario |
| Actors: | System, Administrator | System, Administrator | System, Administrator |
| Description: | This use case describes how the Administrator sets the method to be used when generating the local Case IDs and Business IDs as a default sequence provided by the counter engine. The 'Case Counter Settings' are defined per Tenant . | This use case describes how the Administrator sets the method to be used when generating the local Case IDs and Business IDs as a default sequence provided by the counter engine. The 'Case Counter Settings' are defined per Tenant . | This use case describes how the Administrator sets the method to be used when generating the local Case IDs and Business IDs as a default sequence provided by the counter engine. The 'Case Counter Settings' are defined per Tenant . |
| Trigger: | The Administrator clicks on the 'Case Counter Settings' option from 'Application Settings' menu option | The Administrator clicks on the 'Case Counter Settings' option from 'Application Settings' menu option | The Administrator clicks on the 'Case Counter Settings' option from 'Application Settings' menu option |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized as an administrator of the system. 3. The user defined a Tenant | 1\. The user is authenticated in RINA. 2. The user is authorized as an administrator of the system. 3. The user defined a Tenant | 1\. The user is authenticated in RINA. 2. The user is authorized as an administrator of the system. 3. The user defined a Tenant |
| Post conditions: | The Case Counter Settings have been setup as a Default type for a Tenant and the counter to be used when generating the Local Case ID/Business ID is generated by the counter engine. | The Case Counter Settings have been setup as a Default type for a Tenant and the counter to be used when generating the Local Case ID/Business ID is generated by the counter engine. | The Case Counter Settings have been setup as a Default type for a Tenant and the counter to be used when generating the Local Case ID/Business ID is generated by the counter engine. |
| Main Scenario: | \# | Step actions | Expected Result |
| Main Scenario: | 1 | The Administrator accesses 'Case Counter Settings' option from 'Application Settings ' menu option | The system displays the form 'Case Counter Settings' with the following fields • A drop-down list field labelled 'Select Tenant ' which contains the available tenants. • A selection field labelled 'Type' with available values: 'Default ' , 'HTTP Call back ', ' Pattern ' |
|  | 2 | The Administrator selects the value 'Default ' in the 'Type' field. | The system displays, under the 'Type' field, the message: ' Internal sequence for all cases will be used' . |
|  | 3 | The Administrator clicks 'Save' button | The system displayed the message 'Case counter settings successfully saved', changes regarding this section are saved for the tenant (the Local and the Business Case IDs are set to the same integer value that automatically generated by the platform internal counter engine (the Local Case ID changes after Case archiving/unarchiving) |

## UC_AS_09 Creating and test a valid URL

| Use Case ID: | UC_AS_09 |
| --- | --- |
| Use Case Name: | Creating and test a valid URL |
| Actors: | System, Administrator |

| Description: | This use case describes how the Administrator sets the method to be used when generating the Business IDs as the 'HTTP callback' type and tests the given URL validity. This URL is called every time a new case is created, and it is in the implementation responsibility to ensure the uniqueness of the IDs. | This use case describes how the Administrator sets the method to be used when generating the Business IDs as the 'HTTP callback' type and tests the given URL validity. This URL is called every time a new case is created, and it is in the implementation responsibility to ensure the uniqueness of the IDs. | This use case describes how the Administrator sets the method to be used when generating the Business IDs as the 'HTTP callback' type and tests the given URL validity. This URL is called every time a new case is created, and it is in the implementation responsibility to ensure the uniqueness of the IDs. |
| --- | --- | --- | --- |
| Trigger: | The Administrator clicks 'Case Counter Settings' option from | The Administrator clicks 'Case Counter Settings' option from | The Administrator clicks 'Case Counter Settings' option from |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized as an administrator of the system. | 1\. The user is authenticated in RINA. 2. The user is authorized as an administrator of the system. | 1\. The user is authenticated in RINA. 2. The user is authorized as an administrator of the system. |
| Post conditions: | 3\. A valid URL has been configured and the counter to be used when generating the Business Id is received through an integration with an external provider that generates IDs | The user has defined a Tenant | 3\. A valid URL has been configured and the counter to be used when generating the Business Id is received through an integration with an external provider that generates IDs |
| Main Scenario: | \# | Step actions | Expected Result |
| Main Scenario: | 1 | The Administrator accesses 'Case Counter Settings' option from 'Application Settings ' menu option | The system displays the form 'Case Counter Settings' with the following fields • A drop-down list field labelled 'Select Tenant ' which contains the available tenants. • A selection field labelled 'Type' with available values: 'Default ' , 'HTTP Call back ', ' Pattern ' |
|  | 2 | The Administrator clicks on 'HTTP Call Back' type | The system displays on the new screen: • a free text field labelled 'URL' where the Administrator can provide the URL of the external provider. • a 'Test' button - enables the Administrator to test the provided URL to check its validity by pressing the 'Test' button, |
|  | 3 | The Administrator enters a value in the 'URL' and clicks on 'Test' button (In case the URL is correctly introduced (http:// or https://) the button 'Test' is enabled) | The URL is called, and the outcome is communicated to the Administrator. |
|  | 4 | The Administrator clicks 'Save' button | The System saves data on server. The System displays message 'Case Counter Settings Successfully Saved'. (The URL is called always when a case is created, and it is the implementation responsibility to ensure the uniqueness of the IDs. |

Status: Final / TLP: GREEN

|  |  |  | RINA issues a GET request to the specified URL and use whichever string that gets received in response as the business ID parameter .) |
| --- | --- | --- | --- |
| Exception flow 1 | 1 | The Administrator inserts a wrong URL | The system does not permit to update fields, 'Test' button remains disabled |

## UC_AS_10 Create custom pattern

| Use Case ID: | UC_AS_10 | UC_AS_10 | UC_AS_10 |
| --- | --- | --- | --- |
| Use Case Name: | Create custom pattern | Create custom pattern | Create custom pattern |
| Actors: | System, Administrator | System, Administrator | System, Administrator |
| Description: | This use case describes how the Administrator sets the method to be used when generating the Business IDs as a Pattern string. | This use case describes how the Administrator sets the method to be used when generating the Business IDs as a Pattern string. | This use case describes how the Administrator sets the method to be used when generating the Business IDs as a Pattern string. |
| Trigger: | The Administrator clicks 'Case Counter Settings' option from 'Application Settings' menu option | The Administrator clicks 'Case Counter Settings' option from 'Application Settings' menu option | The Administrator clicks 'Case Counter Settings' option from 'Application Settings' menu option |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized as an administrator of the system. 3. The user defined a Tenant | 1\. The user is authenticated in RINA. 2. The user is authorized as an administrator of the system. 3. The user defined a Tenant | 1\. The user is authenticated in RINA. 2. The user is authorized as an administrator of the system. 3. The user defined a Tenant |
| Post conditions: | The system has created a string Pattern for the automatically generated Business Case ID values. | The system has created a string Pattern for the automatically generated Business Case ID values. | The system has created a string Pattern for the automatically generated Business Case ID values. |
| Main Scenario: | \# | Step actions | Expected Result |
| Main Scenario: | 1 | The Administrator accesses 'Case Counter Settings' option from 'Application Settings ' menu option | The system displays the form 'Case Counter Settings' with the following fields • A drop-down list field labelled 'Select Tenant ' which contains the available tenants. • A selection field labelled 'Type' with available values: 'Default ' , 'HTTP Call back ', ' Pattern ' |
|  | 2 | The Administrator clicks 'Pattern ' type button | The system displays: • a free text field labelled ' Pattern\* ' where: o the Administrator can enter text. The field does not allow special characters : • / • \\ • % • ; o the System adds text during the creation of the pattern, based on the Administrator selection. • an area with parameters that contains the list of main parameters that can be used to construct the required pattern: |

|  |  | o '&lt;BUC_TYPE&gt;', o '', o '' o '&lt;SEQ (global,1000,10)&gt;' with 3 associated field: ▪ a drop-down list field with possible values 'global', 'buc', 'sector' ▪ 2 free-text fields that allow only numerical values (offset and minimum length) o '&lt;DATE (dd/MMM/yyyy)&gt;' with an associated drop-down list, which contains all data formats). Each parameter has available an 'Add' button. |
| --- | --- | --- |
| 3 | The Administrator clicks on the 'Add' button of the '&lt;BUC_TYPE&gt;' parameter. | The string '&lt;BUC_TYPE&gt;' is added in the 'Pattern' field. This keyword means that the construction algorithm shall put the relevant BUC type (i.e., P_BUC_01) at the specific place of the Case ID string. |
| 4 | The Administrator clicks on the 'Add' button of the '' parameter. | The string '' appears in the Pattern field. This character sequence shall be replaced by the Case sector name (e.g., ) |
| 5 | The Administrator clicks on the 'Add' button of the '' parameter. | The string '' appears in the Pattern field. This character sequence shall be replaced by the Case short name ID (e.g., the letter 'P' for Pensions) |
| 6 | The Administrator selects from List of Patterns '&lt;SEQ(NAME, OFFSET, MININUM_LENGTH)&gt;' and chooses from drop- down list box a value, inputs a value from the second text box field and inputs a value in the second text box field and clicks 'Add' button | The string '&lt;SEQ(NAME, OFFSET, MININUM_LENGTH)&gt;' appears in Pattern field. This character sequence shall be replaced by a sequence number in the defined format. The pattern must be defined with three parameters, which influence the look and context of the sequence number. The attributes are explained below: • 'N AME '- name of the sequence. There are three available sequence types: o 'G lobal ' - incremental number for all the cases of the tenant (institution) |

|  |  | o ' BUC ' - incremental number for all the cases of the given BUC type. This is evaluated when the case is created, i.e., the BUC type is known o ' Sector ' - incremental number for all the cases of the given sector type. This is evaluated when the case is created, i.e., the sector type is known. • OFFSET - defines the offset, which will be added to the generated number. Must be an integer value. Example: if the generated number was 10 and the offset set to 1000, the final sequence number will be 1010 • MINIMUM_LENGTH - defines the minimum length of the generated sequence number. If the character length of the generated number is shorter than the minimum length, it will be padded with zeros '0'. Example: if the generated sequence number was 1234 and the minimum length is set to 8, the final sequence string will be 00001234. |
| --- | --- | --- |
| 7 | The Administrator selects from List of Patterns '&lt;DATE(dd/MMM/yyyy) &gt;' and chooses a format date from the associated drop-down list and clicks on green icon associated | The string '&lt;DATE(dd/MMM/yyyy)&gt;' is added in the 'Pattern' field. This character sequence will be replaced by the date of the case creation in the given format. |
| 8 | The Administrator clicks 'Save' button | The system displayed the pop-up message ''Case Counter Settings successfully saved''. |

## Fields Details

## Application Settings -Tenant Settings

| No. | Item name | Type | Validation/business rules |
| --- | --- | --- | --- |
| 1 | Tenant | Free text field | Enabled Search - Look up to IR local repository. |
| 2 | (List of tenants) | Grid | 'Tenant': column for displaying the institution identifier((format: BE:PCTNA05, PCTNA05, PCTNA05, BE represent |

|  |  |  | Country: Institution, Institution, Country) o 'Is Default': column for displaying if tenant is the default one o 'Status' o 'Actions', with associated buttons 'Set Default', 'Enable', 'Delete'. For the default tenant, the 'Actions' column is empty. |
| --- | --- | --- | --- |
| 3 4 | Add Tenant Refresh | Button Button |  |

## Application Settings -General Settings

| No. | Item name | Type | Validation/business rules |
| --- | --- | --- | --- |
| 1 | Use Application Id | Check box | Checked/unchecked |
| 2 | Use Application Id name | Label |  |
| 3 | Languages | List | Check all Uncheck all |
| 4 | Max Idle Time (in minutes) | List | Contains numbers Possibility to select a number from the list |
| 5 | Case Search Results Maximum Limit\* | List | Contains numbers Possibility to select a number from the list |
| 6 | Organization System Password | Free text box field | Visible/invisible inserted characters with role to protect the visibility of the password |
| 7 | Continue when no validation | Tab |  |
| 8 | Exception when no validation | Tab |  |
| 9 | No validation | Tab |  |
| 10 | Show Full Error Information | Check box | Checked/unchecked |
| 11 | Show Process Version | Check box | Checked/unchecked |
| 12 | Attachment directory Path | Free text box field | Mandatory free text field (C:/EESSI/Share/portal/attachments/) |
| 13 | Attachment maximum File Size (in MB) | List | Numeric values, mandatory |
| 14 | Attachment Allowed Mime Type | Area contains attachments |  |
| 15 | Importance | Area |  |
| 16 | Normal | Button |  |
| 17 | High | Button |  |
| 18 | Criticality | Area |  |
| 19 | Normal | Button |  |
| 20 | High | Button |  |
| 21 | Reset | Button |  |
| 22 | Save | Button |  |

## Application Settings -Default Case Settings

| No. | Item name | Type | Validation/business rules |
| --- | --- | --- | --- |
| 1 | View mode | Area |  |
| 2 | Classic view | Button | When clicked change colour in blue |
| 3 | Timeline view | Button | When clicked change colour in blue |
| 4 | Sort by | Area |  |
| 5 | Creation |  | When clicked change colour in blue |
| 6 | Last Update |  | When clicked change colour in blue |
| 7 | Display Flags | Check box |  |
| 8 | Group By Month | Check box |  |
| 9 | Auto Set Alarm on Send Action | List | Contains numeric values (Number of days) |
| 10 | Reset | Button |  |
| 11 | Save | Button |  |

## Application Settings -Default User Profile

| No. | Item name | Type | Validation/business rules |
| --- | --- | --- | --- |
| 1 | Language | List | Mandatory, contains language's list |
| 2 | Number Format | List | Mandatory, contains format numbers |
| 3 | Date Format | List | Mandatory, contains date formats |
| 4 | Time Format | List | Mandatory, contains time formats |
| 5 | Currency | List | Mandatory, contains currencies format |
| 6 | Time Zone | List | Mandatory, contain time zone formats |
| 7 | Reset | Button |  |
| 8 | Save | Button |  |

## Application Settings -Case Counter Settings

| No. | Item name | Type | Validation/business rules |
| --- | --- | --- | --- |
| 1 | Select tenant: | List box | Contains all Tenant, attached explanatory notes |
| 2 | Editing the tenant | Label | Displays the selected tenant (in format Country: Institution) |
| 3 | Default | Tab | Displays label ' Internal sequence for all cases will be used' . Note: Any RINA case locally created or received with this counter setting, which got archived and unarchived up to RINA 2019 versions resulted to different Local and Business IDs. With same configuration and operations for cases created in RINA 2020, the 2 IDs remain the same. |
| 4 | HTTP Callback | Tab | Displays following fields: |

| 5 | URL | Free text box field | Proposed format http://test.com Enabled, mandatory |
| --- | --- | --- | --- |
| 6 | Test | Button |  |
| 7 | Pattern | Tab | Displays following fields: |
| 8 | Pattern | Free text box field | Enabled, mandatory |
| 9 | List of Patterns, contains explanatory notes for following parameters: &lt;BUC_TYPE&gt; &lt;SEQ(global,1000,10)&gt; With associated: Global list box; Free text box, enabled (proposed format number 1000); Free text box, enabled (proposed format number 10) &lt;DATE(dd/MMM/yyyy)&gt; list contains all dates format | Grid | Possibility to select a parameter and add it to Pattern free text field |
| 10 | Save | Button |  |

## 6.3 Messaging Settings

Use case diagrams

Use Case View

UC_MS_01 View TLS certificates

| Use Case ID: | UC_MS_01 | UC_MS_01 | UC_MS_01 |
| --- | --- | --- | --- |
| Use Case Name: | View and delete TLS certificates | View and delete TLS certificates | View and delete TLS certificates |
| Actors: | System, Administrator | System, Administrator | System, Administrator |
| Description: | This use case describes how the Administrator can read details about the certificates for Authentication (TLS) against the AP | This use case describes how the Administrator can read details about the certificates for Authentication (TLS) against the AP | This use case describes how the Administrator can read details about the certificates for Authentication (TLS) against the AP |
| Trigger: | The Administrator clicks on the 'Messaging Systems' menu option, selects option 'Certificates' and clicks on the 'Authentication (TLS)' button from 'Certificates' form. | The Administrator clicks on the 'Messaging Systems' menu option, selects option 'Certificates' and clicks on the 'Authentication (TLS)' button from 'Certificates' form. | The Administrator clicks on the 'Messaging Systems' menu option, selects option 'Certificates' and clicks on the 'Authentication (TLS)' button from 'Certificates' form. |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized as an administrator of the system. | 1\. The user is authenticated in RINA. 2. The user is authorized as an administrator of the system. | 1\. The user is authenticated in RINA. 2. The user is authorized as an administrator of the system. |
| Post conditions: | The Administrator viewed the TLS certificates for Authentication against the AP. | The Administrator viewed the TLS certificates for Authentication against the AP. | The Administrator viewed the TLS certificates for Authentication against the AP. |
| Main Scenario: | \# | Step actions | Expected Result |
| Main Scenario: | 1 | The Administrator clicks on the | The 'Certificates' form is displayed to the Administrator. |

Status: Final / TLP: GREEN

| 'Messaging Systems' menu option and clicks on the 'Certificates' button |
| --- |

EESSI - RINA - Functional Requirements - Administration Portal Status: Final / TLP: GREEN

|  |  |  | o a free text field labelled 'Password' o a 'Save' button o a grid with the columns: o 'Alias' o 'Actions' - for each displayed value in the grid, a 'Delete' button is available. |
| --- | --- | --- | --- |
| Alternate Scenario 1 | 1 | The Administrator clicks 'Refresh' button. | The System redisplay the form 'Certificates' . |

## UC_MS_02 Add New TLS Private Certificate

| Use Case ID: | UC_MS_03 | UC_MS_03 | UC_MS_03 |
| --- | --- | --- | --- |
| Use Case Name: | Add New TLS Private Certificates | Add New TLS Private Certificates | Add New TLS Private Certificates |
| Actors: | System, Administrator | System, Administrator | System, Administrator |
| Description: | This use case describes how the Administrator adds new TLS private certificates | This use case describes how the Administrator adds new TLS private certificates | This use case describes how the Administrator adds new TLS private certificates |
| Trigger: | The Administrator accesses 'Messaging Systems' menu option, selects option 'Certificates' and clicks on the '+New TLS Private Certificate' button from 'Certificates' form. | The Administrator accesses 'Messaging Systems' menu option, selects option 'Certificates' and clicks on the '+New TLS Private Certificate' button from 'Certificates' form. | The Administrator accesses 'Messaging Systems' menu option, selects option 'Certificates' and clicks on the '+New TLS Private Certificate' button from 'Certificates' form. |
| Precondition s: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application |
| Post conditions: | The Administrator added a new TLS private certificate. | The Administrator added a new TLS private certificate. | The Administrator added a new TLS private certificate. |
| Main Scenario: | \# | Step actions | Expected Result |
|  | 1 | The Administrator clicks on the 'Messaging Systems' menu option, clicks on the 'Certificates' button and then clicks on '+ New TLS Private Certificate' button. | The System displays the 'TLS Private Certificate Form' which contains: • 'Keystore Password' - free-text field • 'Certificate File \*' - field where the imported certificate file id displayed • '+Import certificate' button - when clicked it enables the Administrator to upload the certificate file • 'Certificate Alias \*' - mandatory free-text field • 'Certificate Password \*' - mandatory free-text field • 'Back' button • 'Reset' button • 'Save' button |
|  | 2 | The Administrator fills in the fields, imports the certificate and clicks on the 'Save' button | The System saves the data on server. The System closes the 'TLS Private Certificate Form' and navigates back to the 'Certificates' form, where the |

|  |  | new certificate is corresponding display | displayed in the grid. |
| --- | --- | --- | --- |
| 1 | The Administrator clicks on the 'Reset' button | The value(s) on the field(s) are discarded and the fields values are reloaded from the server. | Alternate Scenario 1 |
| 1 | The Administrator clicks on 'Back' button | The present form closes, and the system navigates the Administrator to the previous form 'Certificates' | Alternative Scenario 2 |

## UC_MS_03 Add New TLS Public Certificate

| Use Case ID: | UC_MS_03 | UC_MS_03 | UC_MS_03 |
| --- | --- | --- | --- |
| Use Case Name: | Add New TLS Public Certificates | Add New TLS Public Certificates | Add New TLS Public Certificates |
| Actors: | System, Administrator | System, Administrator | System, Administrator |
| Description: | This use case describes how the Administrator adds new TLS public certificates. | This use case describes how the Administrator adds new TLS public certificates. | This use case describes how the Administrator adds new TLS public certificates. |
| Trigger: | The Administrator accesses 'Messaging Systems' menu option, selects option 'Certificates' and clicks list box with option 'New TLS Public Certificate' from 'Certificates' form. | The Administrator accesses 'Messaging Systems' menu option, selects option 'Certificates' and clicks list box with option 'New TLS Public Certificate' from 'Certificates' form. | The Administrator accesses 'Messaging Systems' menu option, selects option 'Certificates' and clicks list box with option 'New TLS Public Certificate' from 'Certificates' form. |
| Precondition s: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application |
| Post conditions: | The Administrator added new TLS public certificates | The Administrator added new TLS public certificates | The Administrator added new TLS public certificates |
| Main | \# | Step actions | Expected Result |
| Scenario: | 1 | The Administrator clicks on the 'Messaging Systems' menu option, clicks on the 'Certificates' button, clicks on the 'v' expand button, and, from the available options, clicks on the then clicks on 'New TLS Public Certificate'. | The system displays the 'TLS Public Certificate Form' which contains: • 'Keystore Password' - free-text field • 'Certificate File \*' - field where the imported certificate file id displayed • '+Import certificate' button - when clicked it enables the Administrator to upload the certificate file • 'Certificate Alias \*' - mandatory free-text field • 'Back' button • 'Reset' button • 'Save' button |
|  | 2 | The Administrator fills in the fields, imports the certificate and clicks on the 'Save' button | The System saves the data on server. The System closes the 'TLS Public Certificate Form' and navigates back to the 'Certificates' form, where the new certificate is displayed in the corresponding display grid. |

| Alternate Scenario 1 | 1 | The Administrator clicks on the 'Reset' button | The value(s) on the field(s) are discarded and the fields values are reloaded from the server. |
| --- | --- | --- | --- |
| 1 | The Administrator clicks on 'Back' button | The present form closes, and the system navigates the Administrator to the previous form 'Certificates' | Alternative Scenario 2 |

## UC_MS_04 Delete TLS certificates

| Use Case ID: | UC_MS_04 | UC_MS_04 | UC_MS_04 |
| --- | --- | --- | --- |
| Use Case Name: | Delete TLS certificates | Delete TLS certificates | Delete TLS certificates |
| Actors: | System, Administrator | System, Administrator | System, Administrator |
| Description: | This use case describes how the Administrator delete certificates for Authentication (TLS) against the AP | This use case describes how the Administrator delete certificates for Authentication (TLS) against the AP | This use case describes how the Administrator delete certificates for Authentication (TLS) against the AP |
| Trigger: | The Administrator accesses 'Messaging Systems' menu option, selects option 'Certificates' . | The Administrator accesses 'Messaging Systems' menu option, selects option 'Certificates' . | The Administrator accesses 'Messaging Systems' menu option, selects option 'Certificates' . |
| Precondition s: | 1\. The user is authenticated in RINA. 2. The user is authorized as an administrator of the system. | 1\. The user is authenticated in RINA. 2. The user is authorized as an administrator of the system. | 1\. The user is authenticated in RINA. 2. The user is authorized as an administrator of the system. |
| Post conditions: | The Administrator deleted TLS certificates for Authentication against the AP. | The Administrator deleted TLS certificates for Authentication against the AP. | The Administrator deleted TLS certificates for Authentication against the AP. |
| Main Scenario: | \# 1 | Step actions The Administrator clicks | Expected Result The system displays the |
|  | 2 | 'Certificates' button The Administrator identifies in the display grids the certificate to be deleted and clicks on the corresponding 'Delete' button | The System displays confirmation pop- up with the message 'You are about to delete the certificate:' with buttons 'Yes' and 'No'. |
|  | 3 | The Administrator clicks on 'Yes' button | The System deletes the TLS certificate from the associated row from the view. |
| Alternate Scenario 1 | 1 | The Administrator clicks 'No' button | The System discards the action to delete the TLS certificate. The System closes the confirmation pop-up message. |

## UC_MS_05 View ebMS certificates

| Use Case ID: | UC_MS_05 |
| --- | --- |
| Use Case Name: | View ebMS certificates |

| Actors: | System, Administrator | System, Administrator | System, Administrator |
| --- | --- | --- | --- |
| Description: | This use case describes how the Administrator can read details about certificates for signing Messages (ebMS) | This use case describes how the Administrator can read details about certificates for signing Messages (ebMS) | This use case describes how the Administrator can read details about certificates for signing Messages (ebMS) |
| Trigger: | The Administrator accesses 'Messaging Systems' menu option, selects option 'Certificates' and clicks tab 'Authorization (Signatures)' from 'Certificates' form. | The Administrator accesses 'Messaging Systems' menu option, selects option 'Certificates' and clicks tab 'Authorization (Signatures)' from 'Certificates' form. | The Administrator accesses 'Messaging Systems' menu option, selects option 'Certificates' and clicks tab 'Authorization (Signatures)' from 'Certificates' form. |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application |
| Post conditions: | The Administrator viewed ebMS certificates | The Administrator viewed ebMS certificates | The Administrator viewed ebMS certificates |
| Main | \# | Step actions | Expected Result |
| Scenario: | 1 | The Administrator clicks on the 'Messaging Systems' menu option, clicks on the 'Certificates' button | The system displays the 'Certificates' form |
|  | 2 | The Administrator clicks on the 'Authorization (Signature)' button | In the display area the following information is displayed: • an area labelled 'MSG Keystore ()' where the (private) ebMS signing National Domain certificate(s) of every Tenant hosted by RINA is displayed. For this area, the Administrator has available: o a free text field labelled 'Password' o a 'Save' button o a grid with the columns: o 'Alias' o 'Actions' - for each displayed value in the grid, a 'Delete' button is available • an area labelled 'MSG Truststore ()' where the (public) ebMS International Domain (TESTA) certificate of the AP is displayed. For this area, the Administrator has available: o a free text field labelled 'Password' o a 'Save' button o a grid with the columns: o 'Alias' o 'Actions' - for each displayed value in the grid, a 'Delete' button is available |

## UC_MS_06 Add New MSG Private Certificate

| Use Case ID: | UC_MS_06 | UC_MS_06 | UC_MS_06 |
| --- | --- | --- | --- |
| Use Case Name: | Add New MSG Private Certificates | Add New MSG Private Certificates | Add New MSG Private Certificates |
| Actors: | System, Administrator | System, Administrator | System, Administrator |
| Description: | This use case describes how the Administrator adds new MSG private certificates | This use case describes how the Administrator adds new MSG private certificates | This use case describes how the Administrator adds new MSG private certificates |
| Trigger: | The Administrator clicks on the 'Messaging Systems' menu option, clicks on the 'Certificates' button, and in the 'Certificate' form clicks on the 'v' expand button, and, from the available options, clicks on the 'New MSG Private Certificate'. | The Administrator clicks on the 'Messaging Systems' menu option, clicks on the 'Certificates' button, and in the 'Certificate' form clicks on the 'v' expand button, and, from the available options, clicks on the 'New MSG Private Certificate'. | The Administrator clicks on the 'Messaging Systems' menu option, clicks on the 'Certificates' button, and in the 'Certificate' form clicks on the 'v' expand button, and, from the available options, clicks on the 'New MSG Private Certificate'. |
| Precondition s: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application |
| Post conditions: | The Administrator added new MSG private certificates | The Administrator added new MSG private certificates | The Administrator added new MSG private certificates |
| Main | \# | Step actions | Expected Result |
| Scenario: | 1 | The Administrator clicks on the 'Messaging Systems' menu option, clicks on the 'Certificates' button, and in the 'Certificate' form clicks on the 'v' expand button, and, from the available options, clicks on the 'New MSG Private Certificate'. The Administrator fills in | The system displays the 'MSG Private Certificate Form' which contains: • 'Keystore Password' - free-text field • 'Certificate File \*' - field where the imported certificate file id displayed • '+Import certificate' button - when clicked it enables the Administrator to upload the certificate file • 'Certificate Alias \*' - mandatory free-text field • 'Certificate Password \*' - mandatory free-text field • 'Back' button • 'Reset' button • 'Save' button |
|  | 2 | the fields, imports the certificate and clicks on the 'Save' button | The System saves the data on server. The System closes the 'TLS Public Certificate Form' and navigates back to the 'Certificates' form, where the new certificate is displayed in the corresponding display grid. |
| Alternate Scenario 1 | 1 | The Administrator clicks on 'Reset' button | The value(s) on the field(s) are discarded and the fields values are reloaded from the server. |
| Alternative Scenario 2 | 1 | The Administrator clicks on 'Back' button | The present form closes, and the system navigates the Administrator to the previous form 'Certificates' |

## UC_MS_07 Add New MSG Public Certificate

| Use Case ID: | UC_MS_07 | UC_MS_07 | UC_MS_07 |
| --- | --- | --- | --- |
| Use Case Name: | Add New MSG Public Certificates | Add New MSG Public Certificates | Add New MSG Public Certificates |
| Actors: | System, Administrator | System, Administrator | System, Administrator |
| Description: | This use case describes how the Administrator adds new MSG private certificates | This use case describes how the Administrator adds new MSG private certificates | This use case describes how the Administrator adds new MSG private certificates |
| Trigger: | The Administrator clicks on the 'Messaging Systems' menu option, clicks on the 'Certificates' button, and in the 'Certificate' form clicks on the 'v' expand button, and, from the available options, clicks on the 'New MSG Public Certificate'. | The Administrator clicks on the 'Messaging Systems' menu option, clicks on the 'Certificates' button, and in the 'Certificate' form clicks on the 'v' expand button, and, from the available options, clicks on the 'New MSG Public Certificate'. | The Administrator clicks on the 'Messaging Systems' menu option, clicks on the 'Certificates' button, and in the 'Certificate' form clicks on the 'v' expand button, and, from the available options, clicks on the 'New MSG Public Certificate'. |
| Precondition s: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application |
| Post conditions: | The Administrator added new MSG private certificates | The Administrator added new MSG private certificates | The Administrator added new MSG private certificates |
| Main | \# | Step actions | Expected Result |
| Scenario: | 1 | The Administrator clicks on the 'Messaging Systems' menu option, clicks on the 'Certificates' button, and in the 'Certificate' form clicks on the 'v' expand button, and, from the available options, clicks on the 'New MSG Public Certificate'. | The system d isplays the 'MSG Public Certificate Form' which contains: • 'Keystore Password' - free-text field • 'Certificate File \*' - field where the imported certificate file id displayed • '+Import certificate' button - when clicked it enables the Administrator to upload the certificate file • 'Certificate Alias \*' - mandatory free-text field • 'Back' button • 'Reset' button • 'Save' button |
|  | 2 | The Administrator fills in the fields, imports the certificate and clicks on the 'Save' button | The System saves the data on server. The System closes the 'MSG Public Certificate Form' and navigates back to the 'Certificates' form, where the new certificate is displayed in the corresponding display grid. |
| Alternate Scenario 1 | 1 | The Administrator clicks on 'Reset' button | The value(s) on the field(s) are discarded and the fields values are reloaded from the server. |
| Alternative Scenario 2 | 1 | The Administrator clicks on 'Back' button | The present form closes, and the system navigates the Administrator to the previous form 'Certificates' |

## UC_MS_08 Delete ebMS certificates

| Use Case ID: | UC_MS_08 |
| --- | --- |

| Use Case Name: | Delete ebMS certificates | Delete ebMS certificates | Delete ebMS certificates |
| --- | --- | --- | --- |
| Actors: | System, Administrator | System, Administrator | System, Administrator |
| Description: | This use case describes how the Administrator delete certificates for signing Messages (ebMS) | This use case describes how the Administrator delete certificates for signing Messages (ebMS) | This use case describes how the Administrator delete certificates for signing Messages (ebMS) |
| Trigger: | The Administrator accesses 'Messaging Systems' menu option, clicks on the 'Certificates' button, and, in the 'Certificates' form, clicks on the 'Authorization (Signature)' button | The Administrator accesses 'Messaging Systems' menu option, clicks on the 'Certificates' button, and, in the 'Certificates' form, clicks on the 'Authorization (Signature)' button | The Administrator accesses 'Messaging Systems' menu option, clicks on the 'Certificates' button, and, in the 'Certificates' form, clicks on the 'Authorization (Signature)' button |
| Precondition s: | 1\. The user is authenticated in RINA. 2. The user is authorized as an administrator of the system. | 1\. The user is authenticated in RINA. 2. The user is authorized as an administrator of the system. | 1\. The user is authenticated in RINA. 2. The user is authorized as an administrator of the system. |
| Post conditions: | The Administrator deleted the ebMS certificate. | The Administrator deleted the ebMS certificate. | The Administrator deleted the ebMS certificate. |
| Main | \# | Step actions | Expected Result |
| Scenario: | 1 | The Administrator accesses 'Messaging Systems' menu option, clicks on the 'Certificates' button, and, in the 'Certificates' form, clicks on the 'Authorization (Signature)' button | The system displays the 'Certificates' form. In the displ ay area, information about certificates for signing messages are shown. |
|  | 2 | The Administrator identifies in the display grids the certificate to be deleted and clicks on the corresponding 'Delete' button | The System displays confirmation pop-up with the message 'You are about to delete the certificate:' with buttons 'Yes' and 'No'. |
|  | 3 | The Administrator clicks on 'Yes' button | The System deletes the TLS certificate from the associated row from the view. |
| Alternate Scenario 1 | 1 | The Administrator clicks 'No' button | The System discards the action to delete the TLS certificate. The System closes the confirmation pop-up message. |

## UC_MS_09 View Business Signature certificates

| Use Case ID: | UC_MS_09 |
| --- | --- |
| Use Case Name: | View Business Signature certificates |
| Actors: | System, Administrator |
| Description: | This use case describes how the Administrator can read details about certificates used for signing the SEDs |
| Trigger: | The Administrator accesses 'Messaging Systems' menu option, selects option 'Certificates' and clicks on the 'Business Signatures' button from 'Certificates' form. |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application |

Status: Final / TLP: GREEN

| Post conditions: | The Administrator viewed ebMS certificates | The Administrator viewed ebMS certificates | The Administrator viewed ebMS certificates |
| --- | --- | --- | --- |
| Main Scenario: | \# | Step actions | Expected Result |
|  | 1 | The Administrator clicks on the 'Messaging Systems' menu option, clicks on the 'Certificates' button | The system displays the 'Certificates' form |
|  | 2 | The Administrator clicks on the 'Business Signature' button | In the display area the following information is displayed: • an area labelled 'Business Keystore ()' (i.e., 'MSG Keystore (C:/EESSI/Share/repository/certs /businessSignatureKeystore.jks)') ) where the certificates used to sign SEDs are displayed. For this area, the Administrator has available: o a free text field labelled 'Password' o a 'Save' button o a grid with the columns: o 'Alias' o 'Actions' - for each displayed value in the grid, a 'Delete' button is available |

UC_MS_10 Add New Business Private Certificate

| Use Case ID: | UC_MS_10 | UC_MS_10 | UC_MS_10 |
| --- | --- | --- | --- |
| Use Case Name: | Add New Business Private Certificates | Add New Business Private Certificates | Add New Business Private Certificates |
| Actors: | System, Administrator | System, Administrator | System, Administrator |
| Description: | This use case describes how the Administrator adds a new Business private certificate. Each Tenant can use its own Business signature certificate that can be added. | This use case describes how the Administrator adds a new Business private certificate. Each Tenant can use its own Business signature certificate that can be added. | This use case describes how the Administrator adds a new Business private certificate. Each Tenant can use its own Business signature certificate that can be added. |
| Trigger: | The Administrator clicks on the 'Messaging Systems' menu option, clicks on the 'Certificates' button, and in the 'Certificate' form clicks on the 'v' expand button, and, from the available options, clicks on the 'New Business Private Certificate'. | The Administrator clicks on the 'Messaging Systems' menu option, clicks on the 'Certificates' button, and in the 'Certificate' form clicks on the 'v' expand button, and, from the available options, clicks on the 'New Business Private Certificate'. | The Administrator clicks on the 'Messaging Systems' menu option, clicks on the 'Certificates' button, and in the 'Certificate' form clicks on the 'v' expand button, and, from the available options, clicks on the 'New Business Private Certificate'. |
| Precondition s: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application |
| Post conditions: | The Administrator added a new business private certificate | The Administrator added a new business private certificate | The Administrator added a new business private certificate |
| Main Scenario: | \# | Step actions | Expected Result |
| Main Scenario: | 1 | The Administrator clicks on the 'Messaging Systems' menu option, | The system displays the 'MSG Private Certificate Form' which contains: |

Status: Final / TLP: GREEN

|  | clicks on the 'Certificates' button, and in the 'Certificate' form clicks on the 'v' expand button, and, from the available options, clicks on the 'New Business Private Certificate'. | • 'Keystore Password' - free-text field • 'Certificate File \*' - field where the imported certificate file id displayed • '+Import certificate' button - when clicked it enables the Administrator to upload the certificate file • 'Certificate Alias \*' - mandatory free-text field • 'Certificate Password \*' - mandatory free-text field • 'Back' button • 'Reset' button • 'Save' button |
| --- | --- | --- |
| 2 | The Administrator fills in the fields, imports the certificate and clicks on the 'Save' button | The System saves the data on server. The System closes the 'TLS Public Certificate Form' and navigates back to the 'Certificates' form, where the new certificate is displayed in the corresponding display grid. |
| 1 | The Administrator clicks on 'Reset' button The value(s) of the field(s) are discarded, and the fields values are reloaded from the server. | Alternate Scenario 1 |
| 1 | The Administrator clicks on 'Back' button The present form closes, and the system navigates the Administrator the pr evious form 'Certificates' | Alternative Scenario 2 to |

UC_MS_11 Delete Business Signature certificates

| Use Case ID: | UC_MS_11 | UC_MS_11 | UC_MS_11 |
| --- | --- | --- | --- |
| Use Case Name: | Delete ebMS certificates | Delete ebMS certificates | Delete ebMS certificates |
| Actors: | System, Administrator | System, Administrator | System, Administrator |
| Description: | This use case describes how the Administrator deletes a certificate for signing SEDs | This use case describes how the Administrator deletes a certificate for signing SEDs | This use case describes how the Administrator deletes a certificate for signing SEDs |
| Trigger: | The Administrator accesses 'Messaging Systems' menu option, clicks on the 'Certificates' button, and, in the 'Certificates' form, clicks on the 'Business Signature' button | The Administrator accesses 'Messaging Systems' menu option, clicks on the 'Certificates' button, and, in the 'Certificates' form, clicks on the 'Business Signature' button | The Administrator accesses 'Messaging Systems' menu option, clicks on the 'Certificates' button, and, in the 'Certificates' form, clicks on the 'Business Signature' button |
| Precondition s: | 1\. The user is authenticated in RINA. 2. The user is authorized as an administrator of the system. | 1\. The user is authenticated in RINA. 2. The user is authorized as an administrator of the system. | 1\. The user is authenticated in RINA. 2. The user is authorized as an administrator of the system. |
| Post conditions: | The Administrator deleted the business certificate. | The Administrator deleted the business certificate. | The Administrator deleted the business certificate. |
| Main Scenario: | \# | Step actions | Expected Result |
| Main Scenario: | 1 | The Administrator accesses 'Messaging Systems' menu option, clicks on the 'Certificates' button, | The system displays the 'Certificates' form. In the display area, information about certificates for signing SEDs are shown. |

Status: Final / TLP: GREEN

|  |  | and, in the 'Certificates' form, clicks on the 'Business Signature' button |  |
| --- | --- | --- | --- |
| 2 |  | The Administrator identifies in the display grid the certificate to be deleted and clicks on the corresponding 'Delete' button | The System displays confirmation pop- up with the message 'You are about to delete the certificate:' with buttons 'Yes' and 'No'. |
| 3 |  | The Administrator clicks on 'Yes' button | The System deletes the TLS certificate from the associated row from the view. |
| 1 | 1 | The Administrator clicks 'No' button | Alternate Scenario The System discards the action to delete the TLS certificate. The System closes the confirmation |

UC_MS_12 Change password for certificate store

| Use Case ID: | UC_MS_12 | UC_MS_12 | UC_MS_12 |
| --- | --- | --- | --- |
| Use Case Name: | Change password for certificate store | Change password for certificate store | Change password for certificate store |
| Actors: | System Administrator | System Administrator | System Administrator |
| Description: | This use case describes how the Administrator can change the password for the certificates store. The default password is supervisor . The password can be also changed in the file: ' RINA_Root_Folder\\HolodeckB2B\\bin\\startServer.bat ' | This use case describes how the Administrator can change the password for the certificates store. The default password is supervisor . The password can be also changed in the file: ' RINA_Root_Folder\\HolodeckB2B\\bin\\startServer.bat ' | This use case describes how the Administrator can change the password for the certificates store. The default password is supervisor . The password can be also changed in the file: ' RINA_Root_Folder\\HolodeckB2B\\bin\\startServer.bat ' |
| Trigger: | The Administrator clicks on the 'Messaging Systems' menu option, selects option 'Certificates'. | The Administrator clicks on the 'Messaging Systems' menu option, selects option 'Certificates'. | The Administrator clicks on the 'Messaging Systems' menu option, selects option 'Certificates'. |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized as an administrator of the system. | 1\. The user is authenticated in RINA. 2. The user is authorized as an administrator of the system. | 1\. The user is authenticated in RINA. 2. The user is authorized as an administrator of the system. |
| Post conditions: | The Administrator changed the password for the certificates store | The Administrator changed the password for the certificates store | The Administrator changed the password for the certificates store |
| Main Scenario: | \# | Step actions | Expected Result |
| Main Scenario: | 1 | The Administrator clicks on the 'Messaging Systems' menu option and clicks on the 'Certificates' button | The 'Certificates' form is displayed to the Administrator. In the display area, the authentication private and public certificated are displayed |
|  | 2 | The Administrator fills in the desired value in the 'Password' corresponding to the 'TLS Keystore' store | The password for the TLS Private Certificates store is changed. |

|  |  | and clicks on the 'Save' button. |  |
| --- | --- | --- | --- |
| Alternative flow 2 | 1 | At step 2, the Administrator fills in the desired value in the 'Password' corresponding to the 'TLS Truststore' store and clicks on the 'Save' button. | The password for the TLS Public Certificates store is changed. |
| Alternative flow 2 | 1 | After step 1, the Administrator clicks on the 'Authorisation (Signatures)' button | In the display area, the authorisation private and public certificated are displayed |
|  | 2 | At step 2, the Administrator fills in the desired value in the 'Password' corresponding to the 'MSG Keystore' store and clicks on the 'Save' button. | The password for the MSG Private Certificates store is changed. |
| Alternative flow 3 | 1 | After step 1, the Administrator clicks on the 'Authorisation (Signatures)' button | In the display area, the authorisation private and public certificated are displayed |
|  | 2 | At step 2, the Administrator fills in the desired value in the 'Password' corresponding to the 'MSG Truststore' store and clicks on the 'Save' button. | The password for the MSG Public Certificates store is changed. |
| Alternative flow 4 | 1 | After step 1, the Administrator clicks on the 'Business Signatures' button | In the display area, the business certificated are displayed |
|  | 2 | At step 2, the Administrator fills in the desired value in the 'Password' corresponding to the 'Business Keystore' store and clicks on the 'Save' button. | The password for the Business Certificates store is changed. |

## UC_MS_13 Set Transport protocol parameters

| Use Case ID: | UC_MS_13 |
| --- | --- |
| Use Case Name: | Set Transport protocol parameters |
| Actors: | System, Administrator |
| Description: | This use case describes how the system allows the Administrator to configure the settings for receiving messages from the APs |

|  | (transportation method), maximum message size, retry interval and maximum number of retries, in parallel with the interval of pulling request (in case this communication pattern has been selected while receiving from the AP). | (transportation method), maximum message size, retry interval and maximum number of retries, in parallel with the interval of pulling request (in case this communication pattern has been selected while receiving from the AP). | (transportation method), maximum message size, retry interval and maximum number of retries, in parallel with the interval of pulling request (in case this communication pattern has been selected while receiving from the AP). |
| --- | --- | --- | --- |
| Trigger: | The Administrator accesses 'Messaging Systems' menu option and clicks on the 'Global Messaging Systems' button. | The Administrator accesses 'Messaging Systems' menu option and clicks on the 'Global Messaging Systems' button. | The Administrator accesses 'Messaging Systems' menu option and clicks on the 'Global Messaging Systems' button. |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application 3. The user has filled in one area related to certificates | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application 3. The user has filled in one area related to certificates | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application 3. The user has filled in one area related to certificates |
| Post conditions: | The Administrator configured settings for receiving messages depending on Transport mode. | The Administrator configured settings for receiving messages depending on Transport mode. | The Administrator configured settings for receiving messages depending on Transport mode. |
| Main Scenario: | \# | Step actions | Expected Result |
|  | 1 | The Administrator accesses 'Messaging Systems' menu option and clicks on the 'Global Messaging Systems' button. | The system displays the 'Global Messaging Settings' form with the following fields: • a selection field labelled 'BPM Validation Mode', that allows the Administrator to configure the validation against the local XSD files, at the business message services level - by ApClient microservice (at BMS layer), with possible values: o 'Exception When No Validation' o 'No Validation' o 'Continue When No Validation' • a selection field labelled 'Transport Mode', with possible values: o ' Pull ' o 'Push ' Remark: The terminology 'PULL' and 'PUSH' refers to the way the messages are retrieved, at the receiving side, by the MSH (Holodeck) 'PULL': the message is 'pulled' by RINA (ebMS/AS4 client) from the AP queue 'PUSH': the message is 'pushed' from AP to RINA • a counter field labelled ' Max Message Size (KB) \*' , mandatory integer value. This attribute sets the message maximum permitted size that can be sent from RINA application. This parameter configures the size limitation of the entire exchanged message including the SOAP ebMS envelope, the SED and the attachments. The |

|  |  |  | maximum limit is set to 2GB. The default value is 51200Kbytes. • a counter field labelled 'Retry interval (sec) \*' , mandatory integer field. This attribute sets the message re-sending retry interval (in secs). This defines the interval for which RINA waits for the acknowledgement receipt before starts a re-transmission. The default value is 237600 (secs) • a counter field labelled 'Maximum retries \*', mandatory integer field. This attribute sets the maximum number of retries to send a message. The default value is 1. • a counter field labelled 'Default pull request interval (sec) \*', mandatory integer field. This attribute configures the frequency of checking for new data from AP when the Transport Mode is set to PULL. |
| --- | --- | --- | --- |
|  | 2 | The Administrator fills in the fields and clicks on the 'Save ' button | The System saves all parameters concerning the Transport Protocol. |
| Alternative Scenario 1 | 1 | The Administrator clicks 'Reset' button | The System returns all field(s) value(s) to previous value(s) on server. |

## UC_MS_14 Disable Antimalware

| Use Case ID: | UC_MS_14 | UC_MS_14 | UC_MS_14 |
| --- | --- | --- | --- |
| Use Case Name: | Disable Antimalware | Disable Antimalware | Disable Antimalware |
| Actors: | System Administrator | System Administrator | System Administrator |
| Description: | This use case describes how the Administrator configures the settings to disable the Antimalware control. The default value for Antimalware Mode is 'None'. | This use case describes how the Administrator configures the settings to disable the Antimalware control. The default value for Antimalware Mode is 'None'. | This use case describes how the Administrator configures the settings to disable the Antimalware control. The default value for Antimalware Mode is 'None'. |
| Trigger: | The Administrator accesses 'Messaging Systems' menu option, and clicks on the 'Global Messaging Systems' button | The Administrator accesses 'Messaging Systems' menu option, and clicks on the 'Global Messaging Systems' button | The Administrator accesses 'Messaging Systems' menu option, and clicks on the 'Global Messaging Systems' button |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as Admin user 3. The Antimalware Mode is set to a value different than 'None' | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as Admin user 3. The Antimalware Mode is set to a value different than 'None' | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as Admin user 3. The Antimalware Mode is set to a value different than 'None' |
| Post conditions: | The Administrator configured Antimalware section related to 'None' section (no antimalware control) | The Administrator configured Antimalware section related to 'None' section (no antimalware control) | The Administrator configured Antimalware section related to 'None' section (no antimalware control) |
| Main Scenario: | \# | Step actions | Expected Result |
| Main Scenario: | 1 | The Administrator accesses 'Messaging | The 'Global Messaging Settings' is displayed. |

Status: Final / TLP: GREEN

|  |  | Systems' menu option and clicks on the 'Global Messaging Systems' button. | In this form, the Administrator has available the selection field labelled 'Antimalware Mode' with possible values: • 'None' • 'Periodic check' • 'Triggered' The value retrieved from the server is different than 'None'. |
| --- | --- | --- | --- |
|  | 2 | In the selection field 'Antimalware Mode', the Administrator selects the value 'None' | The System displays the 'None' value highlighted. |
|  | 3 | The Administrator clicks on the 'Save ' button | The System displays pop-up window with message 'Global Messaging Settings successfully saved '. Remark: No antimalware control is applied. |
| Alternative Scenario 1 | 1 | The Administrator clicks on the 'Reset' button | The System returns all field(s) value(s) to previous value(s) on server. |

## UC_MS_15 Set Antimalware on 'Periodic check' mode

| Use Case ID: | UC_MS_15 | UC_MS_15 | UC_MS_15 |
| --- | --- | --- | --- |
| Use Case Name: | Set Antimalware on 'Periodic check' mode | Set Antimalware on 'Periodic check' mode | Set Antimalware on 'Periodic check' mode |
| Actors: | System Administrator | System Administrator | System Administrator |
| Description: | This use case describes how the Administrator configures the settings regarding antimalware control in periodic check mode, which means that antimalware is applied periodically. | This use case describes how the Administrator configures the settings regarding antimalware control in periodic check mode, which means that antimalware is applied periodically. | This use case describes how the Administrator configures the settings regarding antimalware control in periodic check mode, which means that antimalware is applied periodically. |
| Trigger: | The Administrator accesses 'Messaging Systems' menu option, and clicks 'Global Messaging Systems' option | The Administrator accesses 'Messaging Systems' menu option, and clicks 'Global Messaging Systems' option | The Administrator accesses 'Messaging Systems' menu option, and clicks 'Global Messaging Systems' option |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as Admin user 3. The Antimalware Mode is set to a value different than 'Periodic check' | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as Admin user 3. The Antimalware Mode is set to a value different than 'Periodic check' | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as Admin user 3. The Antimalware Mode is set to a value different than 'Periodic check' |
| Post conditions: | The Administrator configured Antimalware mode applied periodically | The Administrator configured Antimalware mode applied periodically | The Administrator configured Antimalware mode applied periodically |
| Main Scenario: | \# | Step actions | Expected Result |
| Main Scenario: | 1 | The Administrator accesses 'Messaging Systems' menu option and clicks on the 'Global Messaging Systems' button. | The 'Global Messaging Settings' is displayed. In this form, the Administrator has available the selection field labelled 'Antimalware Mode' with possible values: • 'None' • 'Periodic check' |

Status: Final / TLP: GREEN

|  |  |  | • 'Triggered' The value retrieved from the server is different than 'Periodic check'. |
| --- | --- | --- | --- |
|  | 2 | In the selection field 'Antimalware Mode', the Administrator selects the value 'Periodic check' | The System displays the 'Periodic check' value highlighted. A counter field labelled 'Timeframe Settings \*' is enabled. In this field the Administrator must enter the number of seconds between checks. Remark: it is recommended to not set high value for antimalware period, preferred value for timeframe less than 45 secs. |
|  | 3 | The Administrator fills in the 'Timeframe Settings \*' field and clicks on the ' Save ' button | The System displays pop-up window with: 'Global Messaging Settings successfully saved ' . The System has been configured to be periodically checked. |
| Alternative Scenario 1 | 1 | The Administrator clicks 'Reset' button | The System returns all field(s) value(s) to previous value(s) on server. |

## UC_MS_16 Set Antimalware to 'Triggered' mode

| Use Case ID: | UC_MS_16 | UC_MS_16 | UC_MS_16 |
| --- | --- | --- | --- |
| Use Case Name: | Set Antimalware to 'Triggered' mode | Set Antimalware to 'Triggered' mode | Set Antimalware to 'Triggered' mode |
| Actors: | System, Administrator | System, Administrator | System, Administrator |
| Description: | This use case describes how the Administrator configures the settings regarding antimalware control, as triggered check, which means that antimalware starts when the Administrator 'calls' it. | This use case describes how the Administrator configures the settings regarding antimalware control, as triggered check, which means that antimalware starts when the Administrator 'calls' it. | This use case describes how the Administrator configures the settings regarding antimalware control, as triggered check, which means that antimalware starts when the Administrator 'calls' it. |
| Trigger: | N/A | N/A | N/A |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as Admin User 3. The Antimalware Mode is set to a value different than 'Triggered' | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as Admin User 3. The Antimalware Mode is set to a value different than 'Triggered' | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as Admin User 3. The Antimalware Mode is set to a value different than 'Triggered' |
| Post conditions: | The Administrator configured Antimalware as triggered check mode. | The Administrator configured Antimalware as triggered check mode. | The Administrator configured Antimalware as triggered check mode. |
| Main Scenario: | \# | Step actions | Expected Result |
| Main Scenario: | 1 | The Administrator accesses 'Messaging Systems' menu option and clicks on the 'Global Messaging Systems' button. | The 'Global Messaging Settings' is displayed. In this form, the Administrator has available the selection field labelled 'Antimalware Mode' with possible values: |

|  |  |  | • 'None' • 'Periodic check' • 'Triggered' The value retrieved from the server is different than 'Triggered'. |
| --- | --- | --- | --- |
|  | 2 | In the selection field 'Antimalware Mode', the Administrator selects the value 'Triggered' | The System displays the 'Triggered' value highlighted. Two additional fields are enabled: • free-text field, labelled 'Antimalware Scan Command \*', mandatory • free-text field, labelled 'Antimalware inf code \*' , mandatory |
|  | 2 | The Administrator fills in data related to Antimalware section, and clicks on the 'Save' button | The System displays pop-up window with: 'Global Messaging Settings successfully saved'. Remark: The Antimalware control is activated triggered by the Administrator. |
| Alternative Scenario 1 | 1 | The Administrator clicks 'Reset' button | The System returns all field(s) value(s) to previous value(s) on server. |

## UC_MS_17 Set Local Messaging settings

| Use Case ID: | UC_MS_17 | UC_MS_17 | UC_MS_17 |
| --- | --- | --- | --- |
| Use Case Name: | Set Local Messaging settings | Set Local Messaging settings | Set Local Messaging settings |
| Actors: | System, Administrator | System, Administrator | System, Administrator |
| Description: | This use case describes how the Administrator configures the Local Messaging Settings | This use case describes how the Administrator configures the Local Messaging Settings | This use case describes how the Administrator configures the Local Messaging Settings |
| Trigger: | N/A | N/A | N/A |
| Preconditio ns: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application |
| Post conditions: | The user configured local messaging settings. | The user configured local messaging settings. | The user configured local messaging settings. |
| Main Scenario: | \# | Step actions | Expected Result |
| Main Scenario: | 1 | The Administrator clicks on the 'Messaging Systems' menu option, and then clicks on the 'Local Messaging Systems' button. | The System displays the 'Local Messaging Settings' form: 'Access Point FQDN Address' section, as defined through the RINA Installation and Configuration process, which includes • ' Protocol \*' - mandatory drop- down list to select the http protocol (includes the possible |

| values 'http' and 'https'). Default value is 'https' • 'IP \*' - free text field for introducing the IP address (in terms of the Fully Qualified Domain Name - FQDN) • 'Port \*' - free text field for introducing the relevant connection port. The AP FQDN must be the same as the one defined in the CN (Common Name) of the public certificates provided by the AP 'Business Endpoint' section used for SED exchange - content depends on the selected 'Transport Mode' • For 'Pull' - 'Inbox' (Business) - text box field. The AP application context related service where messages are being retrieved from (only used when the Transport Mode is set to ' Pull ' mode); this is configured in CSN/AP and defined through installation scripts in RINA application ' /eessi/BusinessMessaging/v1.0/I nbox/Service.svc' • For 'Push ' - ' Outbox ' ( Business ) - text box field: the AP application context related service where the messages are being sent to; this is configured in CSN/AP and defined through installation scripts in RINA application ' /eessi/BusinessMessaging/v1.0/ Outbox/Service.svc' 'System Endpoint' section used for synchronization activities- content depends on the selected 'Transport Mode' • ' Inbox ' ( System ) - text box field. The AP application context related service where messages are being retrieved from (only used when the Transport Mode is set to ' Pull ' mode); this is configured in CSN/AP and defined through installation scripts in RINA application ' /eessi/SystemMessaging/v1.0/In box/Service.svc' • ' Outbox ' ( Systems ) - text box field : the AP application context related service where the |
| --- |

|  |  |  | messages are being sent to; this is configured in CSN/AP and defined through installation scripts in RINA application. ' /eessi/SystemMessaging/v1.0/O utbox/Service.svc' • Grid with columns: 'Institution' 'Default business signature alias' 'Endpoint' 'MPC' 'Pulling interval' 'Alias' 'Password' (editable field) • 'Reset' button • 'Save' button |
| --- | --- | --- | --- |
|  | 2 | The Administrator makes the desired changes and clicks on the 'Save' button | The System saves the changes and displays pop-up message 'Messaging Settings successfully saved' |
| Alternative scenario 1 | 1 | The Administrator clicks 'Reset ' button | The System discards all changes included on the fields from the form and restore previous values from server. |

Fields Details

## Messaging Settings -Global Messaging Settings

| No. | Item name | Type | Validation/business rules |
| --- | --- | --- | --- |
| 1 | BPM Validation Mode | Label |  |
| 2 | Exception When No Validation | Tab | When clicked changes the colour in blue |
| 3 | No Validation | Tab | When clicked changes the colour in blue |
| 4 | Continue When No Validation | Tab | When clicked changes the colour in blue |
| 5 | Authentication (TLS) | Tab | By selecting this tab is displayed next fields: |
| 6 | Transport mode | Label |  |
| 7 | Pull | Tab | When clicked changes the colour in blue |
| 8 | Push | Tab | When clicked changes the colour in blue |
| 8 | Max Message Size (KB) | List | Contains numerical values, mandatory |

Status: Final / TLP: GREEN

| 9 | Retry Interval (sec) | List | Mandatory, contains numerical values |
| --- | --- | --- | --- |
| 10 | Maximum retries | List | Mandatory, contains numerical values |
| 11 | Default Pull Request Interval(sec) | List | Mandatory, contains numerical values |
| 12 | Antimalware Mode | Label |  |
| 13 | None | Button | When clicked changes the colour in blue |
| 14 | Periodic check | Button | When clicked changes the colour in blue |
| 15 | Timeframe settings | List | Mandatory |
| 16 | Triggered | Button | When clicked changes the colour in blue |
| 17 | Antimalware Scan command | Free text field | Mandatory |
| 18 | Antimalware inf Code | Free text field | Mandatory |
| 19 | Reset | Button |  |
| 20 | Save | Button |  |

## Messaging Settings -Certificates

| No. | Item name | Type | Validation/busine ss rules |
| --- | --- | --- | --- |
| 1 | Refresh | Button |  |
| 2 | New TLS Public Certificate |  |  |
| 3 | Authentication TLS | Button | When clicked the system displays |
| 4 | TLS Keystore (C:/EESSI/Share/repository/certs/tlskeystore.j ks) | Label |  |
| 5 | Password | Free text box field |  |
| 6 | Save | Button |  |
| 7 | Alias | Grid | Contains columns: Alias Action Delete button, associated to every row |
| 8 | TLS Truststore (C:/EESSI/Share/repository/certs/tlstruststore. jks) | Label |  |
| 9 | Password | Free text box field |  |
| 10 | Save | Button |  |
| 11 | Alias | Grid | Contains columns: Alias Action Delete button, associated to every row |
| 12 | Authorization (Signatures) | Button | When clicked the system displays: |

- 13 MSG Keystore (C:/EESSI/Share/repository/certs/privatekeys.j

ks)

- Label

14

Password

- Free text box field

- 15 Save

Button

- 16 Alias

Grid

- Contains columns: Alias Action Delete button, associated to every row

- 17 MSG Truststore (C:/EESSI/Share/repository/certs/publickeys.jk s)

- Label

- 18 Password

- Free text box field

- 19 Save

Button

- 20 Alias

Grid

- Contains columns: Alias Action Delete button, associated to every row

- 21 Business Signatures

- Button

- When clicked displays:

22

Business Keystore

(C:/EESSI/Share/repository/certs/businessSign atureKeystore.jks)

- 23 Password

- Free text box field Button

24

Save

- 25 Alias

Grid

- Contains columns: Alias Action Delete button, associated to every row

- 26 New TLS Public Certificate

27

Keystore password

- Free text box field

28

Certificate File

- Free text box field

Mandatory with associated

- 29 Import Certificate

Button

Open window that offers possibility to choose a file

- 30 Certificate Alias

Free text box

field

Mandatory

31

Reset

Button

32

Save

Button

33

Back

Button

34

New MSG Private certificate

35

Keystore password

- Free text box field

| 36 | Certificate File | Free text box field | Mandatory with associated |
| --- | --- | --- | --- |
| 37 | Import Certificate | Button | Open window that offers possibility to choose a file |
| 38 | Certificate Alias | Free text box field | Mandatory |
| 39 | Certificate Password | Free text box field | Mandatory |
| 40 | Reset | Button |  |
| 41 | Save | Button |  |
| 42 | Back | Button |  |
| 43 | New MSG Public Certificate |  |  |
| 44 | Keystore password | Free text box field |  |
| 45 | Certificate File | Free text box field | Mandatory with associated |
| 46 | Import Certificate | Button | Open window that offers possibility to choose a file |
| 46 | Certificate Alias | Free text box field | Mandatory |
| 48 | Reset | Button |  |
| 49 | Save | Button |  |
| 50 | Back | Button |  |
| 51 | New Business Private Certificate |  |  |
| 52 | Keystore password | Free text box field |  |
| 53 | Certificate File | Free text box field | Mandatory with associated |
| 54 | Import Certificate | Button | Open window that offers possibility to choose a file |
| 55 | Certificate Alias | Free text box field | Mandatory |
| 56 | Certificate Password | Free text box field | Mandatory |
| 57 | Reset | Button |  |
| 58 | Save | Button |  |
| 59 | Back | Button |  |

## Messaging Settings - Local Messaging Settings

| No. | Item name | Type | Validation/busines s rules |
| --- | --- | --- | --- |
| 1 | Protocol | List | Mandatory, contains http, https values |
| 2 | IP | Free text box | Mandatory |
| 3 | Port | Free text box | Mandatory |
| 4 | Business Endpoint | Label |  |
| 5 | Outbox /eessi/BusinessMessaging/v1.0/Ou tbox/Service.svc | Label |  |

| 6 | System Endpoint | Label |  |
| --- | --- | --- | --- |
| 7 | Outbox /eessi/SystemMessaging/v1.0/Out box/Service.svc | Label |  |
| 8 | Local Message | Grid | Contains columns: Institution (ex: RO:RONA06, RO:RONA06, RO:RONA06, RO) Default Business Signature Alias, has attached list with values Endpoint Alias Password |
| 9 | Reset | Button |  |
| 10 | Save | Button |  |

## 6.4 NIE Settings

Use case diagrams

Use Case View

## UC_NIE_01 NIE - Add case event

| Use Case ID: | UC_NIE_01 |
| --- | --- |
| Use Case Name: | NIE - Add case event |
| Actors: | System, Administrator |

| Description: | This use case describes how the Administrator adds a new case event | This use case describes how the Administrator adds a new case event | This use case describes how the Administrator adds a new case event |
| --- | --- | --- | --- |
| Trigger: | in RINA. The Administrator clicks on the 'NIE Settings' menu option and | in RINA. The Administrator clicks on the 'NIE Settings' menu option and | in RINA. The Administrator clicks on the 'NIE Settings' menu option and |
| Preconditions: | clicks on the 'Add Case Event' button. 1. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA Admin 3. By default, no cases are defined following a new RINA deployment | clicks on the 'Add Case Event' button. 1. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA Admin 3. By default, no cases are defined following a new RINA deployment | clicks on the 'Add Case Event' button. 1. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA Admin 3. By default, no cases are defined following a new RINA deployment |
| Post conditions: | The Administrator added a new case event to NIE. | The Administrator added a new case event to NIE. | The Administrator added a new case event to NIE. |
| Main Scenario: | \# 1 | Step actions The | Expected Result The System displays the 'Add Case Event' |
|  | 2 | Optionally, the Administrator clicks 'Add ' | The System displays in the 'Subscribers' area a new row with 'BUC' and 'Version' fields and corresponding 'Delete' button. |
|  |  | button |  |
|  | 3 | The Administrator fills in the fields | The system saves the inserted data. |

|  |  | and clicks 'Save' button |  |
| --- | --- | --- | --- |
| 1 | At step 3, the Administrator clicks 'Reset ' button | The System discards all changes made on the field(s) of this form and restores value(s) from server. | Alternative scenario 1 |
| 1 | The Administrator does not fill in any of the URL dedicated fields in the 'Listeners' area and clicks the 'Save' button | The System displays the message 'At least one of the listeners should be filled' | Exception flow 1 |

## UC_NIE_02 NIE - Add document event

| Use Case ID: | UC_NIE_02 | UC_NIE_02 | UC_NIE_02 |
| --- | --- | --- | --- |
| Use Case Name: | NIE - Add document event | NIE - Add document event | NIE - Add document event |
| Actors: | System, Administrator | System, Administrator | System, Administrator |
| Description: | This use case describes how the Administrator adds a new document event in RINA. | This use case describes how the Administrator adds a new document event in RINA. | This use case describes how the Administrator adds a new document event in RINA. |
| Trigger: | The Administrator clicks on the 'NIE Settings' menu option and clicks on the 'Add Document Event' button. | The Administrator clicks on the 'NIE Settings' menu option and clicks on the 'Add Document Event' button. | The Administrator clicks on the 'NIE Settings' menu option and clicks on the 'Add Document Event' button. |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA admin | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA admin | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA admin |
| Post conditions: | The Administrator added a new document event. | The Administrator added a new document event. | The Administrator added a new document event. |
| Main | \# | Step actions | Expected Result |
| Scenario: | 1 | The Administrator clicks on the 'NIE Settings' menu option and clicks on the 'Add Document Event'. | The System displays the 'Add Document Event' form, which includes: • 'Subscription name \*', mandatory, free - text field • an area labelled 'Subscribers' where the Administrator has available: o a free- text field 'Document \*', o an 'Add' button for repeating the above field o a 'Delete' button corresponding to each 'Document \*' field • an area labelled 'Listeners' that contains field for introducing URLs for specific events: o 'Initialise Document ' - free-text field o 'New Document ' - free-text field o 'Update Document ' - free-text field o 'Send Document' - free-text field o 'Delete Document' - free-text field o 'Cancel Document' - free-text field o 'Receive Document ' - free-text field |

|  |  |  | o 'Initialise Subdocument ' - free-text field o 'New Subdocument ' - free-text field o 'Update Subdocument ' - free-text field o 'Delete Subdocument ' - free-text field o 'New Document Batch ' - free-text field o 'Receive Document Batch ' - free- text field o an information label: 'Reference implementation URI: http://ip:port/rinieRest/CasesEvents ' • 'Save' button • 'Reset' button |
| --- | --- | --- | --- |
|  | 2 | Optionally, the Administrator clicks on the 'Add' button | The System displays in Subscribers section a new row with 'Document' field and corresponding 'Delete' button. |
|  | 3 | The Administrator clicks on 'Save' button | The System displays the message 'At least one of the listeners should be filled' in case there is no listeners inserted in the list of listeners. The system saves inserted data and display the message 'NIE setting successfully saved' |
| Alternate Scenario 1 | 1 | At step 3, the Administrator clicks on 'Reset' button | The System discards all the changes made on the fields of the form and restores previous values from the server. |

## UC_NIE_03 NIE - Add notification event

| Use Case ID: | UC_NIE_03 |
| --- | --- |
| Use Case Name: | NIE - Add notification event |
| Actors: | System Administrator |
| Description: | This use case describes how the System allows the Administrator to add a new notification event in RINA and how NIE interface (owned by RINA) allows participant countries to exchange information with their National Applications/Systems. RINA uses the NIE client to connect to a listener at National level. This listener will be notified by RINA when a specific Notification event happens. |
| Trigger: | The Administrator accesses 'NIE Settings' menu option and clicks 'Add Notification Event'. |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA admin |

| Post conditions: | The Administrator added a new notification event. | The Administrator added a new notification event. | The Administrator added a new notification event. |
| --- | --- | --- | --- |
| Main | \# | Step actions | Expected Result |
| Scenario: | 1 | The Administrator accesses 'NIE Settings' menu option and select 'Add Notification Event' option | The System displays 'Add Notification Event' form, which contains: • 'Subscription Name \*', mandatory, free - text field • 'Reference implementation URI: http://ip:port/rinieRest/NotificationsEvents' (this is the URL of the listener, where the URL defines the location where the notification's templates should be saved) • 'Generate Notifications \*', free -text field, mandatory • 'Save' button • 'Reset' button |
|  | 2 | The Administrator fills in the fields and clicks 'Save' button | The system saves the inserted data. |
| Alternative scenario 1 | 1 | At step 2, the Administrator clicks 'Reset ' button | The System discards all changes made on the field(s) of this form and restores value(s) from server. |
| Exception flow 1 | 1 | The Administrator does not fill in any of the URL dedicated fields in the 'Listeners' area and clicks the 'Save' button | The System displays the message 'At least one of the listeners should be filled' |

UC_NIE_04 NIE - Consult NIE events

| Use Case ID: | UC_NIE_04 |
| --- | --- |
| Use Case Name: | Consult NIE Events |
| Actors: | System, Administrator |
| Description: | This use case describes how the Administrator consults details about all the NIE events. |
| Trigger: | The Administrator accesses 'NIE Settings' menu option and clicks 'NIE Events'. |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA Admin |
| Post conditions: | The Administrator consulted the list with NIE events |

Status: Final / TLP: GREEN

| Main Scenario: | \# | Step actions | Expected Result |
| --- | --- | --- | --- |
|  | 1 | The Administrator accesses ' NIE Settings ' menu option and clicks on ' NIE Events ' button. | The System displays the 'NIE Events' form with the following information: • A header area that enables the Administrator to sort and search the displayed NIE events using: o a drop-down list field 'Sort by' with possible values: 'Newest First', 'Oldest First', 'Event name' - when a value is selected, the events displayed are sorted accordingly o a free text field 'Search by event name' for entering text to be searched in the event name • A display area where the existing events are displayed. For each displayed event, the Administrator has available a 'Delete' button. |

## UC_NIE_05 NIE - Delete NIE events

| Use Case ID: | UC_NIE_05 | UC_NIE_05 | UC_NIE_05 |
| --- | --- | --- | --- |
| Use Case Name: | Manage NIE Events | Manage NIE Events | Manage NIE Events |
| Actors: | System, Administrator | System, Administrator | System, Administrator |
| Description: | This use case describes how the Administrator deletes a NIE event. | This use case describes how the Administrator deletes a NIE event. | This use case describes how the Administrator deletes a NIE event. |
| Trigger: | The Administrator accesses 'NIE Settings' menu option and clicks 'NIE Events'. | The Administrator accesses 'NIE Settings' menu option and clicks 'NIE Events'. | The Administrator accesses 'NIE Settings' menu option and clicks 'NIE Events'. |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA Admin | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA Admin | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA Admin |
| Post conditions: | The Administrator consulted the list with NIE events | The Administrator consulted the list with NIE events | The Administrator consulted the list with NIE events |
| Main Scenario: | \# | Step actions | Expected Result |
| Main Scenario: | 1 | The Administrator accesses ' NIE Settings ' menu option and clicks on ' NIE Events ' button. | The System displays the 'NIE Events' form |
| Main Scenario: | 2 | The Administrator identifies the NIE event to be deleted and clicks on the corresponding 'Delete' button. | The System displays confirmation pop- up with buttons 'Yes' and 'No'. |
| Main Scenario: | 3 | The Administrator clicks on 'Yes' button | The System deletes the event. |

## UC_NIE_06 NIE - Configures policy decision Nie Client Implementation

| Use Case ID: | UC_NIE_06 | UC_NIE_06 | UC_NIE_06 |
| --- | --- | --- | --- |
| Use Case Name: | Configure policy decision NIE - Client Implementation | Configure policy decision NIE - Client Implementation | Configure policy decision NIE - Client Implementation |
| Actors: | System, Administrator | System, Administrator | System, Administrator |
| Description: | This use case describes how the Administrator configures the policy decision point implementation class | This use case describes how the Administrator configures the policy decision point implementation class | This use case describes how the Administrator configures the policy decision point implementation class |
| Trigger: | The Administrator accesses 'NIE Settings' menu option and clicks 'NIE Client Implementation' button. | The Administrator accesses 'NIE Settings' menu option and clicks 'NIE Client Implementation' button. | The Administrator accesses 'NIE Settings' menu option and clicks 'NIE Client Implementation' button. |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA Admin | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA Admin | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA Admin |
| Post conditions: | The Administrator configures the policy decision point implementation class | The Administrator configures the policy decision point implementation class | The Administrator configures the policy decision point implementation class |
| Main Scenario: | \# | Step actions | Expected Result |
| Main Scenario: | 1 | The Administrator clicks on the 'NIE Settings' main menu option and then clicks on the 'NIE Client Implementation' button. | The System displays the 'Nie Client Implementation' form with the following information: • 'Policy Decision Point Implementation Class (Fully qualified name) \*'- mandatory free-text field • 'Save' button • 'Reset' button |
|  | 2 | The Administrator enters the needed value in the 'Policy Decision Point Implementation Class (Fully qualified name) \*' field and clicks on the 'Save ' button | The System saves data on server. The System displays message 'Nie Client Implementation successfully saved'. |
| Alternative scenario 1 | 1 | The Administrator clicks 'Reset ' button | The System discards all changes made on the field(s) of the form and restores the value(s) from the server. |

Fields Details

NIE -Events

| No. | Item name | Type | Validation/business rules |
| --- | --- | --- | --- |
| 1 | Sort By | List | Contains: Newest First, Oldest First, Event Name |
| 2 | Search by element name | Search element | Enabled |

## NIE -Client Implementation

| No. | Item name | Type | Validation/business rules |
| --- | --- | --- | --- |
| 1 | Policy Decision Point Implementation Class (Fully Qualified Name) | Free text box | Mandatory |

Status: Final / TLP: GREEN

| 2 | Reset | Button |
| --- | --- | --- |
| 3 | Save | Button |

## NIE -ADD Case Event

| No. | Item name | Type | Validation/business rules |
| --- | --- | --- | --- |
| 1 | Subscription name\* | Free text box | Mandatory |
| 2 | BUC | Free text box | Mandatory |
| 3 | Version | Free text box | Mandatory |
| 4 | Add | Button |  |
| 5 | Delete | Button |  |
| 6 | Listeners | Label |  |
| 7 | Open Case | Free text box |  |
| 8 | Receive Case | Free text box |  |
| 9 | Remove Case | Free text box |  |
| 10 | Close Case | Free text box |  |
| 11 | Delete Case | Free text box |  |
| 12 | Forward Case | Free text box |  |
| 13 | Reopen Case | Free text box |  |
| 14 | Reset | Button |  |
| 15 | Save | Button |  |

## NIE -ADD Document Event

| No. Item | name | Type | Validation/business rules |
| --- | --- | --- | --- |
| 1 | Subscription name\* | Free text box | Mandatory |
| 2 | Document | Free text box | Mandatory |
| 4 | Add | Button |  |
| 5 | Delete | Button |  |
| 6 | Listeners | Label |  |
| 7 | Initialise Document | Free text box |  |
| 8 | New Document | Free text box |  |
| 9 | Update Document | Free text box |  |
| 10 | Send Document | Free text box |  |
| 11 | Delete Document | Free text box |  |
| 12 | Cancel Document | Free text box |  |

Status: Final / TLP: GREEN

| 13 | Receive Document | Free text box |
| --- | --- | --- |
| 14 | Initialise Subdocume nt | Free text box |
| 15 | New Subdocument | Free text box |
| 16 | Update Subdocument | Free text box |
| 17 | Delete Subdocument | Free text box |
| 18 | New Document Batch | Free text box |
| 19 | Receive Document Batch | Free text box |
| 20 | Reset | Button |
| 21 | Save | Button |

NIE -ADD Notification Event

| No. | Item name | Type | Validation/business rules |
| --- | --- | --- | --- |
| 1 | Subscription name\* | Free text box | Mandatory |
| 2 | Generate Notifications | Free text box | Mandatory |
| 3 | Reset | Button |  |
| 4 | Save | Button |  |

## 6.5 RINA Archiving

Use case diagrams

Use Case View

## UC_RA_01 Set up archiving policies

| Use Case ID: | UC_RA_01 | UC_RA_01 | UC_RA_01 |
| --- | --- | --- | --- |
| Use Case Name: | Set up archiving policies | Set up archiving policies | Set up archiving policies |
| Actors: | System, Administrator | System, Administrator | System, Administrator |
| Description: | This use case describes how the Administrator can: • define the archiving policies for the cases • enable the messages archiving procedure The archiving policies are defined per Sector and BUC. | This use case describes how the Administrator can: • define the archiving policies for the cases • enable the messages archiving procedure The archiving policies are defined per Sector and BUC. | This use case describes how the Administrator can: • define the archiving policies for the cases • enable the messages archiving procedure The archiving policies are defined per Sector and BUC. |
| Trigger: | The Administrator clicks on the 'RINA Archiving' button from main menu, then clicks on the 'Archiving Policies' button. | The Administrator clicks on the 'RINA Archiving' button from main menu, then clicks on the 'Archiving Policies' button. | The Administrator clicks on the 'RINA Archiving' button from main menu, then clicks on the 'Archiving Policies' button. |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA admin | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA admin | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA admin |
| Post conditions: | The user created/set up policy for archived messages related to a business case. | The user created/set up policy for archived messages related to a business case. | The user created/set up policy for archived messages related to a business case. |
| Main Scenario: | \# | Step actions | Expected Result |
| Main Scenario: | 1 | The Administrator clicks on the 'RINA Archiving' menu option, then on the ' Archiving Policies ' button | The System displays the form 'Archiving Policies' , which includes: • '+Add Policies', button • 'Settings', button • Grid displaying the existing archiving policies, with following columns o 'Sector' o 'Process' - for displaying the BUC type of the archiving policy o 'Role' o 'Days' o 'Actions' where, for each displayed policy, the Administrator has available: o 'Edit' button o 'Delete' button • 'Refresh' button |
|  | 2 | The Administrator clicks on the '+Add Policies' button | The System displays the ' Archiving Policies Form ' , with following fields: • 'Process Owner ' - check box • 'Counter Party ' - check box The Administrator must check at least one of the above checkbox fields. • 'Archiving Period (days)' - counter field with the default value 90 days, where the Administrator must select the archive period. This is the period |

|  |  | of time during which a closed case is retained at such state, prior to automatically getting to archived state. The archived state can be reverted, only if the case is not deleted. For a case in archive state only case metadata are available to the user • the 'Sector' drop -down field that allows the Administrator to select the relevant business sector (AWOD, Pensions, Family benefits, Horizontal, Legislation applicable, Miscellaneous, Recovery, Sickness, Unemployment). • the 'BUC': based on the selected Sector, the System displays all the BUCs of that Sector. Each BUC has a corresponding checkbox field for the administrator to select one or more BUCs to be included in the archiving policy by clicking on the check box • 'Save' button • 'Reset' button |
| --- | --- | --- |
| 3 | The Administrator fills in the fields and clicks on 'Save' button | The System saves the archiving policy and displays message 'Archiving policies successfully saved'. The System closes the form 'Archiving Polic ies Form ' and displays the 'Archiving Policies' form. In the display grid, the new added policy is visible. |
| 4 | The Administrator clicks on the 'Edit' button corresponding to a displayed archiving policy | The System: • Enables for changes the 'Days' field of the archiving policy: • In the 'Action' column, the 'Edit' and 'Delete' buttons are replaced with : o 'Save' button o 'Cancel' button |

UC_RA_02 Configure location and messages repositories

|  | 5 | The Administrator fills in the 'Days' field and clicks on the 'Save ' button | The System saves the updated value and displays the message ' Archiving policies successfully saved ' . |
| --- | --- | --- | --- |
| Alternate Flow 1 | 1 At step 5, the Administrator 'Days' field on the 'Cancel' | fills in the and clicks The System discards the changes made on the field. | button |
| Alternate Flow 2 | 1 | After step 5, the administrator clicks on the ' Delete ' button The System displays pop-up message ' You are about to delete the archiving policy: ' with two buttons 'Yes' and 'No' |  |
|  | 2 | The Administrator clicks 'Yes' button | The System deletes the Case archiving policy, and the policy is removed from the archiving policies list. |
| Alternate | 1 | At step 2 of Alternative Flow 2, the Administrator clicks on the 'No' button The System discards delete action which means the case archiving policy is not deleted and continues to be visible on archiving policies | Flow 3 |
| Alternate Flow 4 | 1 | At step 3, the Administrator fills in the fields and clicks the 'Reset' button | case's list. The System discards all values from the fields on the form and displays the values saved on server. |
| Alternate 5 | 1 | Administrator clicks Refresh ' button the form, saved on | Flow The ' The System redisplays retrieving the information the server. |
| Alternate Flow 6 | 1 | The Administrator clicks on the 'Back' button | The System closes present form and returns to previous form. |
| Flow | 1 | At step 2, the Administrator clicks on 'Settings ' button The System displays the ' Archiving Policies Settings ' form, which contains: • 'Archive Messages' checkbox field - when clicked indicates that the messages are to be archived • 'Default Period (Days) \*' - counter field, indicating number of days • 'Reset' button • 'Save' button | Alternate 7 |
|  | 2 | The Administrator fills the fields and clicks 'Save' button | The System saves data, closes 'Archiving Policies Settings' form , and returns to the previous form. |
| Alternate Flow 8 | 1 | The Administrator clicks on the 'Reset' button | The System discard all changes made on the fields from this form and restore previous values from the server. |

| Use Case ID: | UC_RA_02 | UC_RA_02 | UC_RA_02 |
| --- | --- | --- | --- |
| Use Case Name: | Configure location and messages repositories | Configure location and messages repositories | Configure location and messages repositories |
| Actors: | System, Administrator | System, Administrator | System, Administrator |
| Description: | This use case describes how the Administrator configures the cases and messages repositories parameters (i.e., name, location, minimum size) | This use case describes how the Administrator configures the cases and messages repositories parameters (i.e., name, location, minimum size) | This use case describes how the Administrator configures the cases and messages repositories parameters (i.e., name, location, minimum size) |
| Trigger: | The Administrator clicks on the 'RINA Archiving' main menu entry and then clicks on the 'Archiving Repositories' button. | The Administrator clicks on the 'RINA Archiving' main menu entry and then clicks on the 'Archiving Repositories' button. | The Administrator clicks on the 'RINA Archiving' main menu entry and then clicks on the 'Archiving Repositories' button. |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA Admin | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA Admin | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA Admin |
| Post conditions: | The Administrator configured the location of the cases and messages repositories, set up volumes | The Administrator configured the location of the cases and messages repositories, set up volumes | The Administrator configured the location of the cases and messages repositories, set up volumes |
| Main Scenario: | \# | Step actions | Expected Result |
|  | 1 | The Administrator clicks on the 'RINA Archiving' menu option, then on the 'Archiving Repositories' button. | The System displays the 'Archiving Repositories' form which contains: • 'Refresh' button • ' + Add Repository' button • a grid for displaying the existing repositories, which contains columns: o 'Volume Name' o 'Min Threshold (MB)' - once the minimum threshold (MB) is reached and the disk space used by archives exceeds this value, the administrator receives a notification to check the disk space availability on the respective volume) o 'Path' o 'Actions', for each displayed repository, the Administrator has available : o 'Edit' button o 'Delete' button |
|  | 2 | The Administrator clicks on the ' +Add Repository' button | The System displays the ' Archiving Repository F orm' , with following fields: • ' Volume Name \*' - free-text field, mandatory • ' Min Threshold (MB) \*' - counter field, mandatory • An area labelled 'Locations' with following fields o ' Path \*' - mandatory, free-text field and corresponding o ' Delete ' button |

Status: Final / TLP: GREEN

UC_RA_03 Set up message archiving repository policy

|  |  |  | o 'Add' button - when clicked, it repeats the 'Path\*' field • ' Save ' button • ' Reset ' button • ' Back ' button |
| --- | --- | --- | --- |
|  | 3 | Optionally, the Administrator clicks the 'Add ' button | The System displays a new 'Path \*' - mandatory free-text field and a new corresponding 'Delete' button |
|  | 4 | Optionally, the Administrator clicks on the 'Delete' button | The system deletes the row with the field 'Path \*' and the 'Delete' button |
|  | 5 | The Administrator fills in the fields and clicks ' Save ' button | The System saves the data and displays a pop-up message 'Archiving Repository successfully saved'. The System closes the form and returns to the form 'Archiving Repositories' with the new repository item displayed in the grid. |
| Alternative Scenario 1 | 1 | The Administrator clicks on the 'Delete' button corresponding to a repository entry from the display grid. | The System displays the 'Confirmation' form with the message ' You are about to delete the archiving repository: ' and with 'Yes' and 'No' buttons. |
|  | 2 | The Administrator clicks on the 'Yes' button | The System deletes selected archiving repository and displays pop- up message 'Archiving repository successfully saved'. |
| Alternative Scenario 2 | 1 | At step 2 from Alternative Scenario 1, the Administrator clicks 'No' button | The System closes the 'Confirmation' form without deleting the repository. In the display grid, the repository is available to the Administrator. |
| Alternative Scenario 3 | 1 | After step 5, the Administrator clicks on the ' Edit ' button corresponding to a repository entry from the display grid. | The System enables for edit all the values displayed in the grid corresponding to the repository. |
|  | 2 | The Administrator fills in the fields on the grid and clicks on the 'Save' button | The System saves data and displays pop- up message ' Archiving repository successfully saved '. The System displays the row line with the data changed in view mode. |

| Use Case ID: | UC_RA_03 | UC_RA_03 | UC_RA_03 |
| --- | --- | --- | --- |
| Use Case Name: | Set up message archiving repository policy | Set up message archiving repository policy | Set up message archiving repository policy |
| Actors: | System, Administrator | System, Administrator | System, Administrator |
| Description: | This use case describes how the Administrator configures the volumes(repositories) where the messages are to be stored for archiving purposes. | This use case describes how the Administrator configures the volumes(repositories) where the messages are to be stored for archiving purposes. | This use case describes how the Administrator configures the volumes(repositories) where the messages are to be stored for archiving purposes. |
| Trigger: | The Administrator clicks on the 'RINA Archiving' main menu entry and then clicks on the ' Message Archiving Repository Policy' button. | The Administrator clicks on the 'RINA Archiving' main menu entry and then clicks on the ' Message Archiving Repository Policy' button. | The Administrator clicks on the 'RINA Archiving' main menu entry and then clicks on the ' Message Archiving Repository Policy' button. |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA admin 3. The user has defined archiving policies and volumes | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA admin 3. The user has defined archiving policies and volumes | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA admin 3. The user has defined archiving policies and volumes |
| Post conditions: | The Administrator has configured the volume where the messages are to be stored for archiving purposes | The Administrator has configured the volume where the messages are to be stored for archiving purposes | The Administrator has configured the volume where the messages are to be stored for archiving purposes |
| Main Scenario: | \# | Step actions | Expected Result |
| Main Scenario: | 1 | The Administrator clicks on the 'RINA Archiving' main menu entry and then clicks on the ' Message Archiving Repository Policy' button. | The S ystem displays the 'Message Archiving Repository Policy' form, with following fields: • ' Volume *' - mandatory, drop- down list field with possible values the list of volumes defined by the Administrator by performing UC_RA_02 • ('Min Threshold (MB)') associated to selected volume, free-text field, disabled for editing - the System populates the corresponding value after a selection is made in the 'Volume*' field. • 'Reset' button • 'Save' button |
| Main Scenario: | 2 | The Administrator fills in 'Volume\*' field and clicks ' Save ' button | The System saves data on server. The System displays pop-up window with message ' Message archiving repository policy successfully saved' |
| Alternative Scenario 1 | 3 | At step 2, the Administrator fills in 'Volume\*' field and clicks on the 'Reset' button. | The System discards all changes and displays the values retrieved from the server. |

UC_RA_04 Set up message retention policies

| Use Case ID: | UC_RA_04 |
| --- | --- |
| Use Case Name: | Set up message retention policies |

Status: Final / TLP: GREEN

| Actors: | System, Administrator | System, Administrator | System, Administrator |
| --- | --- | --- | --- |
| Description: | This use case describes how the Administrator can set up the default message retention period prior to messages getting deleted. | This use case describes how the Administrator can set up the default message retention period prior to messages getting deleted. | This use case describes how the Administrator can set up the default message retention period prior to messages getting deleted. |
| Trigger: | The Administrator clicks on the 'RINA Archiving' main menu entry, then clicks on the 'Message Retention Policies' bu tton. | The Administrator clicks on the 'RINA Archiving' main menu entry, then clicks on the 'Message Retention Policies' bu tton. | The Administrator clicks on the 'RINA Archiving' main menu entry, then clicks on the 'Message Retention Policies' bu tton. |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA admin | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA admin | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA admin |
| Post conditions: | The user set up the policy for retaining messages | The user set up the policy for retaining messages | The user set up the policy for retaining messages |
| Main Scenario: | \# | Step actions | Expected Result |
|  | 1 | The Administrator clicks on the 'RINA Archiving' menu option, then on the ' Message Retention Policies ' button | The System displays the form 'Message Retention Policies' , which includes: • 'Default Period (Days) \*' counter field with default value 90 days. This field controls the period of time during which an archived message is retained into the System, prior to automatically getting deleted. • 'Save' button • 'Reset' button - when clicked, the System discards all the unsaved changes done by the Administrator and displays the values retrieved from the server. |
|  | 2 | The Administrator changes the value of the ' Default Period (Days) \*' field and clicks on the 'Save' field. | The System saves the default message retention period and displays the message: 'Message retention policies successfully saved' |

## Fields Details

## RINA archiving -Archiving Policies

| No. | Item name | Type | Validation/business rules |
| --- | --- | --- | --- |
| 1 | Refresh | Button |  |
| 2 | Policies | Grid | Contains columns: Sector Process Role Days Actions |
| 3 | Add Policies | Button | When clicked the system displays: |

Status: Final / TLP: GREEN

| 4 | Process Owner | Check box |  |
| --- | --- | --- | --- |
| 5 | Counterparty | Check box |  |
| 6 | Archiving Period (days) | List | Contains numerical values |
| 7 | Sector | List | Possibility to choose, by clicking on associated check box |
| 8 | BUC | List | Possibility to choose, by clicking on associated check box |
| 9 | Back | Button |  |
| 10 | Reset | Button |  |
| 11 | Save | Button |  |

## RINA Archiving - Archiving repositories

| No. | Item name | Type | Validation/business rules |
| --- | --- | --- | --- |
| 1 | Add Repository | Button | At click is displayed form which contains: |
| 2 | Volume Name\* | Free text box field | Mandatory |
| 3 | Min. Threshold (MB)\* | List | Mandatory |
| 4 | Path | Free text box field | Mandatory |
| 5 | Back | Button |  |
| 6 | Reset | Button |  |
| 7 | Save | Button |  |
| 8 | Archiving Repositories | Grid | Contains columns: Volume name Min. Threshold (MB) Path Actions Has associated buttons: Edit button Pressing on Edit button, the system displays Save and Cancel buttons Delete button |

## RINA Archiving - Message Retention Policy

| No. | Item name | Type | Validation/business rules |
| --- | --- | --- | --- |
| 1 | Default period days | List | Contains volumes, mandatory |
| 2 | Reset | Button |  |
| 3 | Save | Button |  |

## RINA Archiving - Message archiving repository policy

| No. | Item name | Type | Validation/business rules |
| --- | --- | --- | --- |
| 1 | Default period days | List | Contains volumes, mandatory |
| 2 | Reset | Button |  |
| 3 | Save | Button |  |

## 6.6 IAM

Use case diagrams

Use Case View

UC_IAM_01 Configure users

| Use Case ID: | UC_IAM_01 |
| --- | --- |
| Use Case Name: | Configure users |
| Actors: | System, Administrator |
| Description: | This use case describes how the system allows the Administrator to configure users in RINA, create new users (every user belongs to a group and have defined multiples roles) and deletes users. All IAM Settings are independent between each RINA Tenant. |
| Trigger: | The Administrator clicks on the 'IAM' main menu option and then clicks on the 'Users' button. |

| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application (with Admin role) 3. The user selected the relevant tenant (top left-hand side of the screen - if there is only 1 tenant, the system displays only the default value) 4. The user's group is already created | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application (with Admin role) 3. The user selected the relevant tenant (top left-hand side of the screen - if there is only 1 tenant, the system displays only the default value) 4. The user's group is already created | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application (with Admin role) 3. The user selected the relevant tenant (top left-hand side of the screen - if there is only 1 tenant, the system displays only the default value) 4. The user's group is already created |
| --- | --- | --- | --- |
| Post conditions: | The Administrator has been configured the user. An audit event is raised into Audit Log. | The Administrator has been configured the user. An audit event is raised into Audit Log. | The Administrator has been configured the user. An audit event is raised into Audit Log. |
| Main | \# | Step actions | Expected Result |
| Scenario: | 1 | The Administrator clicks on the 'IAM' main menu option and then clicks on the 'Users' button. | The System displays the 'Users' form with following fields: • 'Search' - free text field, which offers the possibility to search users using key words. This element has associated an 'x' red icon button; when clicked it deletes the text written for the search. • 'Add Users' button • ' Refresh ' button • Grid which contains the following columns: o 'Username' o 'First name' o 'Last name' o 'Email' o 'Enabled' - check box that describe whether the account is Enabled or not (the user can be provisioned for a later phase but may not be currently active). o ' Actions ' , for each displayed user, the Administrator has available : ▪ 'Edit' button |
|  | 2 | The Administrator clicks on the 'Add User' button | The System displays 'User Form', with the following elements: • 'Username' - mandatory, free-text field, case sensitive (The length of Username should be equal to or less than 15 characters and the space char (' ') is not permitted). • 'Password' - free-text field (Standard, the minimum length of the Password, is 8 and the recommended length is 10 characters), case sensitive • 'Confirm Password' • 'First Name' - mandatory, free-text field • 'Last Name' - mandatory, free-text field • 'Email' - mandatory, free-text field • 'Mobile Number' - free-text field • 'Business Keystore Certificate Alias' - drop-down list |

| • ' Enabled ' - check box (whether the account is Enabled or not - the user can be provisioned for a later date but may not be currently active). o An area labelled 'Memberships' where the Administrator adds the relevant groups and roles. Membership is the link between the user, the group and the user's role in the group). In this area, the Administrator has available the following fields: o 'Group' - selection field, where all the defined groups are displayed o 'Clear' button - when clicked, it clears the selection from the 'Group' field o 'Role' - drop-down list field, where the types of roles are available for selection. A User/Clerk can have multiple roles. A user with multiple roles can perform any action permitted by all the assigned roles. As an example, an authorised clerk that is also a medical user can send SEDs (permitted by the authorised clerk role) and also access classified medical attachments (permitted by the medical user role). o 'Add' button - when clicked, the selected values from fi elds 'Group' and 'Role' are displayed in the 'Memberships' area with a corresponding 'Delete' button • 'Reset' button • 'Save' button The 'Medical' and 'VIP' roles have limited permissions and can be considered as supplementary roles that are assigned to specific users when access to critical data is required. 'VIP' users are able to select/unselect the 'Sensitive' flag in the 'Case Metadata' pop- up. 'VIP' user may set 'Sensitive Case' flag BUT in order to create/edit |
| --- |

|  |  | documents must be also 'authorised'/ 'non authorised' clerk. In order to send documents, the clerk must have the 'authorised' clerk role. In order to view case documents, the clerk must be 'authorised ' /'non authorised', 'supervisor ' and/or 'viewer '. ' Medical ' user can tag/un-tag an attachment as medical. In order to add must be also 'authorised'/'non authorised' clerk. In order to view it, the user must be 'authorised'/'non authorised', 'supervisor' and/or 'Viewer' ' Supervisors ' , 'Authorised ' clerks and 'non -authorised ' clerks are able to chan ge the 'Criticality' and 'Importance' properties (Case Assignments) Some groups can be labelled with the 'Organisational Unit' flag (the equivalent of the OU in LDAP). This is used in order to represent the branches. |
| --- | --- | --- |
| 3 | The Administrator fills in the user related fields, selects values for the membership 'Group' and 'Role' fields and clicks on the 'Add' button . | The System displays the selected group and role in the 'Membership' area |
| 4 | Optionally, the user makes additional selections for the membership 'Group' and 'Role' fields, after each selection clicking on the 'Add' button | The System displays the selected groups and roles in the 'Membership' area |
| 4 | The Administrator clicks on the 'Save' button | The System creates a new user, closes the 'User Form' and displays the 'Users' form. In the display grid, the new created user is displayed as a line item in the users list. The System displays the message pop-up window 'User successfully saved' |

| Exception Flow 1 | 1 | At step 3, the Administrator makes no selection and clicks on the 'Add' button | The System displays a message ' Please first select a group'. The main scenario can be resumed by performing step 3. |
| --- | --- | --- | --- |
|  | 1 After step 1, the Administrator identifies in the display grid a user to be modified and clicks on the 'Edit' button. | The System displays the 'User Form' filled with the data about the user retrieved from the server. | Alternative Scenario 1 |
|  | 2 | The Administrator changes the values of the displayed fields and clicks on the 'Save' button | The System saves the data and displays the pop- up message 'User successfully saved'. The System closes 'User Form' and returns to 'Users' Form. |
| Alternate Scenario 4 | 1 | After step 1, the Administrator identifies in the display grid a user to be deleted and clicks on 'Delete' button. System opens a pop-up box with the 'You are about to delete the '. button button - when clicked, the 'Delete' is aborted | The message user: - 'Yes' - 'No' action |
|  | 2 | The Administrator clicks on the 'Yes' button | The System verifies that the user can be deleted. A user/clerk cannot be deleted by the Administrator if: • an open case is assigned directly to the user • or a direct Case assignment is established through the application of a policy rule (i.e., when a rule applies an assignment to a Group and not to a User, any member of that Group can be deleted if the member is not directly assigned to an open case). When criteria for deletion are met, the System deletes the user. |
| Exception | 1 | At step 3, the Administrator fills in the name of an existing user System indicates the creation of a user failed and displays an error 'The Name of the User should unique for every RINA installation. ' rule is applied at the tenant level, i.e., existence of 2 or more users with the | 1 The new message: be The the |

## UC_IAM_02 Search user

| Use Case ID: | UC_IAM_02 | UC_IAM_02 | UC_IAM_02 |
| --- | --- | --- | --- |
| Use Case Name: | Search users | Search users | Search users |
| Actors: | System, Administrator | System, Administrator | System, Administrator |
| Description: | This use case describes how the system allows the Administrator to search data related to user. | This use case describes how the system allows the Administrator to search data related to user. | This use case describes how the system allows the Administrator to search data related to user. |
| Trigger: | The Administrator clicks on the 'IAM' main menu option and then clicks on the 'Users' button. | The Administrator clicks on the 'IAM' main menu option and then clicks on the 'Users' button. | The Administrator clicks on the 'IAM' main menu option and then clicks on the 'Users' button. |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA admin 3. The user selected the relevant tenant (top left-hand side of the screen - if there is only 1 tenant, the system displays only the default value) | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA admin 3. The user selected the relevant tenant (top left-hand side of the screen - if there is only 1 tenant, the system displays only the default value) | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA admin 3. The user selected the relevant tenant (top left-hand side of the screen - if there is only 1 tenant, the system displays only the default value) |
| Post conditions: | The Administrator has updated the user parameters. An audit event is raised into Audit Log. | The Administrator has updated the user parameters. An audit event is raised into Audit Log. | The Administrator has updated the user parameters. An audit event is raised into Audit Log. |
| Main Scenario: | \# | Step actions | Expected Result |
| Main Scenario: | 1 | The Administrator clicks on the 'IAM' main menu option and then clicks on the 'Users' button. | The System displays the 'Users' form |
| Main Scenario: | 1 | The Administrator enters the key word to search after in the ' Search ' free text field and clicks on the magnifying glass icon button. | The System executes a search in the list of users for the entered text and displays in the grid the list of users. The entered keyword in compared against the 'Username' field. Wildcard '\*' character is allowed. The search is not case-sensitive. |

UC_IAM_03 Create groups

| Use Case ID: | UC_IAM_03 |
| --- | --- |
| Use Case Name: | Create groups |
| Actors: | System, Administrator |
| Description: | This use case describes how the system allows the Administrator to create a new group (it is advisable to use groups in order to assign permissions, instead of assigning permissions/rights individually to users). The system allows the Administrator to assign users to groups and then assign authorization policies to groups and resources |
| Trigger: | The Administrator clicks on the 'IAM' main menu option and then clicks on the ' Groups ' button. |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application (with Admin role) 3. The user selected the relevant tenant (top left-hand side of the screen - if there is only 1 tenant, the system displays only the default value) The system allows the Administrator to assign users to groups and then assign authorization policies to groups and resources |

| Post conditions: | The Administrator created a new group. An audit event is raised into Audit Log. | The Administrator created a new group. An audit event is raised into Audit Log. | The Administrator created a new group. An audit event is raised into Audit Log. |
| --- | --- | --- | --- |
| Main Scenario: | \# | Step actions | Expected Result |
|  | 1 | The Administrator clicks on the 'IAM' main menu option and then clicks on the ' Groups ' button. | The System displays the 'Groups' form which contains: • 'Refresh' button • 'Search' free text field , with magnifying glass icon button to launch the search and x icon button to clear the search • 'Add Group' button • Display grid, with following columns: o 'Name' - displays the name of the group o 'Description' o 'Organization Unit' - (OU). An OU is intended to be a 'super - group'; for instance, it may be used to represent/cover a branch (in a multi-branch environment) o 'Created' - displays the creation date of the group o 'Actions' - for each displayed group, the column contains: ▪ 'Edit' button ▪ 'Delete' button |
|  | 2 | The Administrator clicks on the ' Add Group ' button | The System displays the 'Groups' form which contains: • 'Name \*' - mandatory, free-text field • 'Description' - free-text field • 'Organization Unit' - check box • 'Parent Group' - list that contains the list with groups and associated groups to the parent group. The Administrator needs to decide its position/location in the group hierarchy, which means it is needed to decide first which the parent group is. Each group needs to have a parent group, except for the root group. • 'Clear' button- used to unselect the group • 'Save' button • 'Reset' button |

EESSI - RINA - Functional Requirements - Administration Portal

(rev03)

Status: Final / TLP: GREEN

|  |  | • 'Back' button |  |
| --- | --- | --- | --- |
| the fields the ' Save ' | 3 | The Administrator fills in and clicks on button | The System saves the data, creates the new group (following the provided group structure by the administrator) The system displays a pop-up message ' Group successfully created' . |
| 1 | After step 2, the Administrator fills in the fields and clicks on the ' Reset ' button | The System discards all values from the form. | Alternative scenario 1 |
|  | After step 2, the Administrator click 'Back' button | The System closes 'Group Form' and returns to step 1 of the Main scenario | Alternative Scenario 2 on |
| 1 | The Administrator fills in the 'Name' field the name of an existing group | The System does not create a new group and displays the error message: ' The Name of the Groups should be unique for every RINA installation. ' The rule is applied at the tenant level, i.e. the existence of 2 or more groups with the same name under the same tenant is not permitted . | Exception 1 |

## UC_IAM_04 Search groups

| Use Case ID: | UC_IAM_04 | UC_IAM_04 | UC_IAM_04 |
| --- | --- | --- | --- |
| Use Case Name: | Search groups | Search groups | Search groups |
| Actors: | System, Administrator | System, Administrator | System, Administrator |
| Description: | This use case describes how the system allows the Administrator to search groups | This use case describes how the system allows the Administrator to search groups | This use case describes how the system allows the Administrator to search groups |
| Trigger: | The Administrator clicks on the 'IAM' main menu option and then clicks on the ' Groups ' button. | The Administrator clicks on the 'IAM' main menu option and then clicks on the ' Groups ' button. | The Administrator clicks on the 'IAM' main menu option and then clicks on the ' Groups ' button. |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application (with Admin role) 3. The user selects the relevant tenant (top left- hand side of the screen - if there is only 1 tenant, the system displays the default value) | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application (with Admin role) 3. The user selects the relevant tenant (top left- hand side of the screen - if there is only 1 tenant, the system displays the default value) | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application (with Admin role) 3. The user selects the relevant tenant (top left- hand side of the screen - if there is only 1 tenant, the system displays the default value) |
| Post conditions: | The Administrator searched group in a list of groups | The Administrator searched group in a list of groups | The Administrator searched group in a list of groups |
| Main Scenario: | \# | Step actions | Expected Result |
| Main Scenario: | 1 | The Administrator clicks on the 'IAM' main menu option and then clicks on the ' Groups ' button. | The System display the 'Groups' form. |
| Main Scenario: | 2 | The Administrator enters in the free-text | The System executes a search in the list of groups for the entered text |

|  |  | field 'Search' the keyword to search after. | and displays the resulting groups in the display grid. The entered keyword in compared against the 'Name' field The search is not case-sensitive. |
| --- | --- | --- | --- |
| Alternative Flow 1 | 1 | At step 2, the entered keyword does not match any of the existing groups The System executes a search in the list of groups for the entered text The System displays the grid without any result. |  |

## UC_IAM_05 Modify groups

| Use Case ID: | UC_IAM_05 | UC_IAM_05 | UC_IAM_05 |
| --- | --- | --- | --- |
| Use Case Name: | Modify groups | Modify groups | Modify groups |
| Actors: | System, Administrator | System, Administrator | System, Administrator |
| Description: | This use case describes how the system allows the Administrator to modify(edit) groups | This use case describes how the system allows the Administrator to modify(edit) groups | This use case describes how the system allows the Administrator to modify(edit) groups |
| Trigger: | The Administrator clicks on the 'IAM' main menu option and then | The Administrator clicks on the 'IAM' main menu option and then | The Administrator clicks on the 'IAM' main menu option and then |
| Preconditions: | clicks on the ' Groups ' button. 1. The user is authenticated in RINA. 2. The user is authorized to access Application (with Admin role) 3. The user selects the relevant tenant (top left- hand side of the screen - if there is only 1 tenant, the system displays the default value) 4. The group to be edited was created following UC_IAM_03 | clicks on the ' Groups ' button. 1. The user is authenticated in RINA. 2. The user is authorized to access Application (with Admin role) 3. The user selects the relevant tenant (top left- hand side of the screen - if there is only 1 tenant, the system displays the default value) 4. The group to be edited was created following UC_IAM_03 | clicks on the ' Groups ' button. 1. The user is authenticated in RINA. 2. The user is authorized to access Application (with Admin role) 3. The user selects the relevant tenant (top left- hand side of the screen - if there is only 1 tenant, the system displays the default value) 4. The group to be edited was created following UC_IAM_03 |
| Post conditions: | The Administrator modified group parameters. An audit event is raised into Audit Log. | The Administrator modified group parameters. An audit event is raised into Audit Log. | The Administrator modified group parameters. An audit event is raised into Audit Log. |
| Main Scenario: | \# | Step actions | Expected Result |
| Main Scenario: | 1 | The Administrator clicks on the 'IAM' main menu option and then clicks on the ' Groups ' button. | The System displays 'Groups' form . |
|  | 2 | The Administrator identifies in the display grid the group to be modified and clicks on the corresponding ' Edit ' button. | In the display grid, the System enables for edit all the displayed fields corresponding to the selected group: • 'Name' • 'Description' • 'Organization Unit' • In the 'Actions' column, the 'Edit' and 'Delete' buttons are replaced with: o 'Save' button o 'Cancel' button |

| 3 The the fields and clicks button |  | Administrator fills in on the grid on the 'Save' | The System saves the modified data and displays the message ' The group has been successfully updated ' . Remark: It is not possible to modify the name of a group to an existing group name - name of the group is unique. |
| --- | --- | --- | --- |
| 4 | At step 3, the Administrator clicks ' Cancel ' button | on The System discards all changes and return to previous data on server The System returns to step 1 from Main Scenario. | Alternative Scenario 1 |

## UC_IAM_06 Delete a group

| Use Case ID: | UC_IAM_06 | UC_IAM_06 | UC_IAM_06 |
| --- | --- | --- | --- |
| Use Case Name: | Delete a group | Delete a group | Delete a group |
| Actors: | System, Administrator | System, Administrator | System, Administrator |
| Description: | This use case describes how the system allows the Administrator to delete group(s) | This use case describes how the system allows the Administrator to delete group(s) | This use case describes how the system allows the Administrator to delete group(s) |
| Trigger: | The Administrator clicks on the 'IAM' main menu option and then clicks on the ' Groups ' button , then clicks 'Delete' button. | The Administrator clicks on the 'IAM' main menu option and then clicks on the ' Groups ' button , then clicks 'Delete' button. | The Administrator clicks on the 'IAM' main menu option and then clicks on the ' Groups ' button , then clicks 'Delete' button. |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application (with Admin role) 3. The user selected the relevant tenant (top left- hand side of the screen - if there is only 1 tenant, the system displays only the default value) 4. The group to be edited was created following UC_IAM_03 | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application (with Admin role) 3. The user selected the relevant tenant (top left- hand side of the screen - if there is only 1 tenant, the system displays only the default value) 4. The group to be edited was created following UC_IAM_03 | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application (with Admin role) 3. The user selected the relevant tenant (top left- hand side of the screen - if there is only 1 tenant, the system displays only the default value) 4. The group to be edited was created following UC_IAM_03 |
| Post conditions: | The Administrator deleted a group. An audit event is raised into Audit Log. | The Administrator deleted a group. An audit event is raised into Audit Log. | The Administrator deleted a group. An audit event is raised into Audit Log. |
| Main Scenario: | \# | Step actions | Expected Result |
| Main Scenario: | 1 | The Administrator clicks on the 'IAM' main menu option and then clicks on the ' Groups ' button | The System display the 'Groups' . form which contains: |
|  | 2 | The Administrator identifies in the display grid the group to be deleted and clicks on the corresponding ' Delete ' button. | The System displays the 'Confirmation' form where the Administrator has available: • 'Yes' button - to confirm the deletion • 'No' button - to cancel the deletion |
|  | 2 | The Administrator clicks on 'Yes' button | The System deletes the line item with the group data. The System displays message ' Group successfully deleted '. The System returns to step 1 of Main Scenario. |

| Alternate Scenario 1 | 1 | The Administrator clicks 'No' button | The System cancel the deletion. The System returns to step 1 of Main Scenario. |
| --- | --- | --- | --- |
| 1 | The Administrator select a particular group (which has active users assigned) and chooses to delete it | The system does not delete a group, once a case has been sent for that group OR if active users are still available | Exception Flow 1 |

UC_IAM_07 Setting up LDAP configuration

| Use Case ID: | UC_IAM_07 | UC_IAM_07 | UC_IAM_07 |
| --- | --- | --- | --- |
| Use Case Name: | Setting up LDAP configuration | Setting up LDAP configuration | Setting up LDAP configuration |
| Actors: | System, Administrator | System, Administrator | System, Administrator |
| Description: | This use case describes how the system allows the Administrator to add the configuration for synchronizing RINA users and groups (for a specific Tenant) with the structure residing at an LDAP server | This use case describes how the system allows the Administrator to add the configuration for synchronizing RINA users and groups (for a specific Tenant) with the structure residing at an LDAP server | This use case describes how the system allows the Administrator to add the configuration for synchronizing RINA users and groups (for a specific Tenant) with the structure residing at an LDAP server |
| Trigger: | The Administrator clicks on the 'IAM' main menu option and then clicks on the 'LDAP Configuration' button. | The Administrator clicks on the 'IAM' main menu option and then clicks on the 'LDAP Configuration' button. | The Administrator clicks on the 'IAM' main menu option and then clicks on the 'LDAP Configuration' button. |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application (with Admin role) 3. The user selects the relevant tenant (top left-hand side of the screen - if there is only 1 tenant, the system displays the default value) | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application (with Admin role) 3. The user selects the relevant tenant (top left-hand side of the screen - if there is only 1 tenant, the system displays the default value) | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application (with Admin role) 3. The user selects the relevant tenant (top left-hand side of the screen - if there is only 1 tenant, the system displays the default value) |
| Post conditions: | The Administrator configures the relevant parameters and proceeds with the necessary user/group information mapping before the synchronization of the Users/Groups between RINA and the LDAP server | The Administrator configures the relevant parameters and proceeds with the necessary user/group information mapping before the synchronization of the Users/Groups between RINA and the LDAP server | The Administrator configures the relevant parameters and proceeds with the necessary user/group information mapping before the synchronization of the Users/Groups between RINA and the LDAP server |
| Main | \# | Step actions | Expected Result |
| Scenario: | 1 | The Administrator clicks on the 'IAM' main menu option and then clicks on the 'LDAP Configuration' button. | The System displays the 'LDAP Configuration' form where the Administrator configures the LDAP sync process. The Group & User Mapping between RINA internal authentication DB and the external LDAP provider follows the LDAP communication parameters configuration. The form contains: • 'Configuration' area (RINA/LDAP communication parameters) with following field: o 'User \*' - mandatory, free-text field (the user account used to authenticate to the LDAP server (for example,"cn=install,ou=people,dc =test domain ,dc=com")) o 'Password \*' - free-text field case sensitive, mandatory (the |

| password for auth_user_dn auth_ssl - define whether SSL is used for authentication. Accepted values: true or false) o 'Url \*' - mandatory, free-text field (FQDN/ IP Address and port of the LDAP server to synchronise from) o 'Security Authentication \*' - mandatory, free-text field (simple (specifies the authentication mechanism to use. Possible values 'simple', 'none', 'sasl_mech', etc)) o 'LDAP User Search Base \*' - mandatory, free-text field (users_provider_dn for example, "OU=people, DC=testdomain, DC=com")) o 'LDAP Group Search Base \*' - free- text field (users_provider_dn, for example, "OU=people, DC=testdomain, DC=com") o 'User Search String' - free-text field (LDAP query to filter user. For example:"(&(objectClass=inetOrgP erson)(!(uid=install)))") o 'Group Search String' - free-text field (Group filtering. For example, "(objectclass=posixGroup)" groups_mapping - Mapping of the groups "group_name=cn description=description") • 'Group Mappings' subsection, with following fields: o 'LDAP Unique Identifier \*' - mandatory, free-text field (LDAP attribute, which is unique and used to identify the group, in most LDAP implementations is 'distinguishedName' or 'sAMAccountName') o 'Group name \*' - mandatory, free-text field (the full qualified name of the group) o 'Display Name \*' - mandatory, free-text field ( the short name of the group) o 'Description' - free-text field (the description of group from LDAP) o 'Is group Organisation Unit' - free-text field (Boolean to declare if the given entity is an organisation unit) o 'Is group reassigned' - free-text field (Boolean to check if the given entity needs reassignment) |
| --- |

| o 'Parent group Id' - free-text field (the id of the parent Group) o 'Group's path' - free-text field (the full path of the Group to root unit) o 'Creation Date' - free-text field (the Group creation date) o 'Last Update' - free-text field (the last update of the Group) o 'Groups members' - free-text field (Attribute of a group which maps members of this group (users). If it is set, members of this group will be synchronized, even if they are not looked up by user search string) • 'User Mappings' subsection , with following fields o 'LDAP Unique Identifier \*' - mandatory, free-text field ( LDAP attribute, which is unique and used to identify the group, in most LDAP implementations is 'distinguishedName' or 'sAMAccountName') o 'Username \*' - mandatory, free- text field (the full qualified Username) o 'First Name \*' - mandatory, free- text field (the User's first name) o 'Last Name \*' - mandatory, free- text field (the User's last name) o 'Email \*' - mandatory, free-text field (the User's email) o 'Phone Number' - free-text field ( the User's phone number) o 'Is enabled' - free-text field ( Boolean to declare if the User is enabled or not) o 'Is administrator' - free-text field ( Boolean to declare if the User is the administrator or not) o 'Creation Date' - free-text field (the User creation date in the system) o 'Last Update' - free-text field (the last update of the User info) o 'User's Groups' - free-text field (the property mapping to LDAP Groups to which the User belongs) o 'User's Role' - free-text field (the appropriate selection from a User's roles list) • 'Save' button |
| --- |

Status: Final / TLP: GREEN

|  |  | • 'Reset' button • ' Synchronize LDAP' button |
| --- | --- | --- |
| 2 | The Administrator fills in the fields and clicks 'Save' button | The system validates the inserted data and displays the messages: 'LDAP Configuration settings successfully saved' 'LDAP user mappings successfully saved' 'LDAP group mapping settings successfully saved' After successful synchronization with LDAP server, it is possible to log in to system with LDAP credentials. |
| 3 | The Administrator clicks on 'Synchronize LDAP' | The System synchronizes the RINA content with one LDAP server each time |

## Fields Details

IAM - Users

| No. | Item name | Type | Validation/business rules |
| --- | --- | --- | --- |
| 1 | Select tenant (with explanatory notes associated) | List | (a value is selected by default) |
| 2 | Search bar element |  | Delete |
| 3 | Refresh | Button | Refresh screen |
| 4 | Add user | Button | At click displays User form, which contains: |
| 4.1 | Username | Free text box field | Mandatory |
| 4.2 | Password | Free text box field | Mandatory |
| 4.3 | Confirm password | Free text box field | Mandatory |
| 4.4 | First Name | Free text box field | Mandatory |
| 4.5 | Last Name | Free text box field | Mandatory |
| 4.6 | Email | Free text box field | Mandatory, suggested format admin@example.com |
| 4.7 | Mobile number | Free text box field | Suggested format +00- 00000000 |
| 4.8 | Business Keystore Certificate Alias | List |  |
| 4.9 | Enabled | Check box |  |
| 4.10 | Memberships | Label |  |
| 4.11 | Group | List | With associated Clear button |
| 4.12 | Role | List |  |
| 4.13 | Add | Button |  |
| 5 | Users | Grid | Contains columns: Username First Name Last Name Email Enabled |

Status: Final / TLP: GREEN

|  |  |  | Actions Every row has associates for Actions column 2 buttons |
| --- | --- | --- | --- |
| 5.1 | Edit | Button | The system displays User form (step 4) |
| 5.1 | Delete | Button |  |

## IAM -Groups

| No. | Item name | Type | Validation/business rules |
| --- | --- | --- | --- |
| 1 | Select tenant (with explanatory notes associated) | List (a value is selected by default) |  |
| 2 | Search bar element |  | Search Delete |
| 3 | Refresh | Button | Refresh screen |
| 4 | Add Group | Button | At click displays Group Form, which contains fields: |
| 4.1 | Name | Free text field | Mandatory |
| 4.2 | Description | Free text field |  |
| 4.3 | Organization Unit | Check box |  |
| 4.4 | Parent Group | Free text box | Has associated Clear button |
| 4.5 | Back | Button |  |
| 4.6 | Reset | Button |  |
| 4.7 | Save | Button |  |
| 5 | Groups | Grid | Contains columns: Name Description Organization unit Created Actions Every row has 2 buttons: |
| 5.1 | Edit | Button | When click the system displays: Save and Cancel Buttons |
| 5.2 | Delete | Button |  |

## IAM -LDAP Configuration

| No. | Item name | Type | Validation/business rules |
| --- | --- | --- | --- |
| 1 | Select tenant (with explanatory notes associated) | List | (a value is selected by default) |
| 2 | LDAP configuration for Tenant Name | Label |  |
| 3 | Configuration section | Label |  |
| 4 | User: | Free text box field | Mandatory, suggested format user@user.lab |
| 5 | Password | Free text box field | Visible/invisible mandatory |

Status: Final / TLP: GREEN

| 6 | URL | Free text box field | mandatory, suggested format ldap://123.123.123.54:389 |
| --- | --- | --- | --- |
| 7 | Security Authentication | Free text box field | Mandatory |
| 8 | LDAP User Search Base | Free text box field | Mandatory, suggested format OU=example1, DC=example2, DC=example3 |
| 9 | LDAP Group Search Base | Free text box field | Mandatory, suggested format OU=example1, DC=example2, DC=example3 |
| 10 | User Search String | Free text box field |  |
| 11 | Group Search String | Free text box field |  |
| 12 | Group Mappings | Label |  |
| 13 | LDAP Unique Identifier | Free text box field | Mandatory |
| 14 | Group name | Free text box field | Mandatory |
| 15 | Display name | Free text box field | Mandatory |
| 16 | Description | Free text box field |  |
| 17 | Is group Organization unit | Free text box field |  |
| 18 | Is group reassigned | Free text box field |  |
| 19 | Parent group id | Free text box field |  |
| 20 | Group's path | Free text box field |  |
| 21 | Creation date | Free text box field |  |
| 22 | Last update | Free text box field |  |
| 23 | Group's members | Free text box field |  |
| 24 | User Mappings ( section ) | Label |  |
| 25 | LDAP Unique Identifier | Free text box field, | Mandatory |
| 26 | Username | Free text box field | Mandatory |
| 27 | First name | Free text box field | Mandatory |
| 28 | Last name | Free text box field | Mandatory |
| 29 | Email | Free text box field | Mandatory, suggested format admin@example.com |
| 30 | Phone number | Free text box field |  |
| 31 | Is enabled | Free text box field |  |
| 32 | Is administrator | Free text box field |  |

| 33 | Creation date | Free text box field |  |
| --- | --- | --- | --- |
| 34 | Last update: | Free text box field |  |
| 35 | User's groups | Free text box field |  |
| 36 | User's Role | List | Contains list with groups |
| 37 | Reset | Button |  |
| 38 | Save | Button |  |
| 39 | Synchronize LDAP | Button |  |

## 6.7 Authorization

Use case diagrams

Use Case View

UC_Auth_01 Create a new Case Policy

| Use Case ID: | UC_Auth_01 |
| --- | --- |
| Use Case Name: | Create a new Case Policy |

| Description: | This use case describes how the System allows the Administrator to configure who gets access to RINA resources by creating and configuring a new policy (the policies provide the Administrator with the tools required to manage and restrict access to cases in RINA). The case assignment policies control the permissions and the access to cases. All settings are independent and distinguished between RINA Tenants. | This use case describes how the System allows the Administrator to configure who gets access to RINA resources by creating and configuring a new policy (the policies provide the Administrator with the tools required to manage and restrict access to cases in RINA). The case assignment policies control the permissions and the access to cases. All settings are independent and distinguished between RINA Tenants. | This use case describes how the System allows the Administrator to configure who gets access to RINA resources by creating and configuring a new policy (the policies provide the Administrator with the tools required to manage and restrict access to cases in RINA). The case assignment policies control the permissions and the access to cases. All settings are independent and distinguished between RINA Tenants. |
| --- | --- | --- | --- |
| Trigger: | The Administrator clicks on the ' Authorization ' main menu option , then clicks 'Assignment Policies' button. | The Administrator clicks on the ' Authorization ' main menu option , then clicks 'Assignment Policies' button. | The Administrator clicks on the ' Authorization ' main menu option , then clicks 'Assignment Policies' button. |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA admin 3. The user selects the relevant tenant (top left-hand side of the screen - if there is only 1 tenant, the system displays the default | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA admin 3. The user selects the relevant tenant (top left-hand side of the screen - if there is only 1 tenant, the system displays the default | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA admin 3. The user selects the relevant tenant (top left-hand side of the screen - if there is only 1 tenant, the system displays the default |
| Post conditions: | The Administrator has created a new case policy. | The Administrator has created a new case policy. | The Administrator has created a new case policy. |
| Main | \# | Step actions | Expected Result |
| Scenario: | 1 | The Administrator clicks on the ' Authorization ' main menu option, then clicks 'Assignment Policies' button. | The System displays the 'Assignment Policies' form, with the following fields: • 'Refresh' button • ' Search' free text field - enables the Administrator to search within the list of existing policies based on entered text. This field has associated an 'x' red icon, used to delete the text to be searched and a magnifying glass icon to launch the search. • 'New Policy' button. This button has associated an expand 'v' icon button - when clicked, it provides two additional buttons: 'New Creator Policy' and 'New Policy Group'. • a grid for displaying all existing policies, with columns: o 'Name' o 'Description' o 'Type' o 'Actions', for each displayed policy, the Administrator has available in this column : ▪ 'Edit' button ▪ 'Delete' button |
|  | 2 | The Administrator clicks on the 'New Policy' button | The System displays the 'Policy Form', which contains: • 'Name \*' - mandatory, free-text field • 'Description' - free-text field • 'Color' - drop down list with colour icon values (to be associated to a policy, which may |

| provide visual indications in the section Process assign) • Subsection labelled ' Rule X ' ('X' from 1…n) with the following fields: • 'Add' button - when clicked, it adds a new subsection of type 'Rule X' and enables for each displayed 'Rule X' subsection: o 'Move down' button - not available for last added rule o 'Move up' button - not available for first rule o 'Delete' button • Information label - 'When these conditions are met:' • selection field 'Application Role in' - with possible values: o 'Process Owner' button o 'Counter Party' button o 'Any' button Based on the selection done by the Administrator in the 'Application Role in' field, the System enables different fields in the 'Rule x' subsection, as follows ➢ with 'Process Owner' button selected the System displays: • 'Sector In' - drop-down list, which contains all the EESSI sectors, i.e., 'FB', 'Pensions', and the generic 'Any' value • 'Process Type In' - drop-down list which contains all the available BUC types of selected Sector and the generic 'Any' value • 'Case Creator In' - selection field with possible values the list of groups of users. This field has associated two buttons: o 'Clear' button - when clicked, the selection from the 'Case Creator In' field is cleared o 'Add' button - when clicked, it adds the selected group from the 'Case Creator In' field as a display line with associated 'Delete' button • 'Assign To Actors' - drop-down list field with multi-select allowed and possible values the list of roles • 'These Users and Groups \*' checkbox selection field - with: o 'Creator User' - checkbox |
| --- |

EESSI - RINA - Functional Requirements - Administration Portal (rev03) Status: Final / TLP: GREEN

| o 'Creator Branch' - checkbox • 'Select Group' - selection field for indicating the group of the users to be assigned to the case, with associated fields o 'Clear' button o 'Add' button o 'Select User' - activated after a group is selected in the 'Select Group'. ➢ with 'Counter Party' button selected the System display: • 'Sector In' - drop-down list, which contains all the EESSI sectors, i.e., 'FB', 'Pensions', and the generic 'Any' value • 'Process Type In' - drop-down list which contains all the available BUC types of selected Sector and the generic 'Any' value • 'Subject Address like' - free text field • 'Owner Country In' - drop-down list contains participating countries and generic value 'Any' • 'Owner Organization In' - field with Institution free text search enabled for selecting the institution and associated '+' button for confirming the selection • 'Assign To Actors' - drop-down list, contains all roles • 'These Users and Groups \*' - mandatory subsection with: o 'Select Group' - selection field for indicating the group of the users to be assigned to the case, with associated fields ▪ 'Clear' button ▪ 'Add' button ▪ 'Select User' - activated after a group is selected in the 'Select Group'. ➢ with 'Any' button selected th e System displays: • 'Sector In' - drop-down list, which contains all the EESSI sectors, i.e., 'FB', 'Pensions', and the generic 'Any' value • 'Process Type In' - drop-down list which contains all the available BUC types of selected Sector and the generic 'Any' value |
| --- |

|  |  | • 'Assign To Actors' - drop-down list, contains all roles • 'These Users and Groups \*' - mandatory subsection with: o 'Select Group' - selection field for indicating the group of the users to be assigned to the case, with associated fields ▪ 'Clear' button ▪ 'Add' button ▪ 'Select User' - activated after a group is selected in the 'Select Group'. The form also contains: • 'Save' button • 'Reset' button |
| --- | --- | --- |
| 3 | The Administrator fills in the fields from the form and clicks on the 'Save' button | • 'Back' button The System creates a new policy, which is listed in policies' list. The system displays a pop-up message 'Assignment policy successfully saved' The System return to 'Assignment Policy' form with the new case policy added and visible on the grid. The System shall apply these rules sequentially until the first successful rule completely fulfils the defined criteria and conditions. Therefore, the order of the rules in the provided list defines the priority in which the system processes the rules. The Administrator can enforce a specific rule by changing its order on the list. The change of the priority order can be done by using the selections ( 'Move up' ) and ('Move down' ) buttons. The checked legend 'And stop processing more rules', has been located at the end of each rule to clearly indicate that the system stops processing the rules queue sequentially if the specific rule fulfils completely the conditions. |

## UC_Auth_02 Deleting a Policy

| Use Case ID: | UC_Auth_02 |
| --- | --- |
| Use Case Name: | Deleting a Policy |

| Actors: | System, Administrator | System, Administrator | System, Administrator |
| --- | --- | --- | --- |
| Description: | This use case describes how the System allows the Administrator to delete a policy (General - non-Creator, Creator or Policy Group). All Settings are distinguished and independent between each RINA Tenant. | This use case describes how the System allows the Administrator to delete a policy (General - non-Creator, Creator or Policy Group). All Settings are distinguished and independent between each RINA Tenant. | This use case describes how the System allows the Administrator to delete a policy (General - non-Creator, Creator or Policy Group). All Settings are distinguished and independent between each RINA Tenant. |
| Trigger: | The Administrator clicks on the ' Authorization ' main menu option , then clicks 'Assignment Policies' button. | The Administrator clicks on the ' Authorization ' main menu option , then clicks 'Assignment Policies' button. | The Administrator clicks on the ' Authorization ' main menu option , then clicks 'Assignment Policies' button. |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA Admin 3. The user selected the relevant tenant (top left-hand side of the screen - if there is only 1 tenant, the system displays the default value) 4. The Policy to be deleted exists in the system. | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA Admin 3. The user selected the relevant tenant (top left-hand side of the screen - if there is only 1 tenant, the system displays the default value) 4. The Policy to be deleted exists in the system. | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA Admin 3. The user selected the relevant tenant (top left-hand side of the screen - if there is only 1 tenant, the system displays the default value) 4. The Policy to be deleted exists in the system. |
| Post conditions: | The Administrator has deleted a policy. | The Administrator has deleted a policy. | The Administrator has deleted a policy. |
| Main Scenario: | \# | Step actions | Expected Result |
| Main Scenario: | 1 | The Administrator clicks on the ' Authorization ' main menu option, then clicks 'Assignment Policies' button. | The System displays the 'Assignment Policies' form . |
|  | 2 | The Administrator identifies the policy to be deleted in the display grid and clicks on the associated 'Delete' button from the column 'Actions' | The system displays a pop-up window Confirmation with the message ' You are about to delete the policy: ' - ' Y es' button - ' N o' button |
|  | 3 | The Administrator clicks on 'Yes' button | The System closes confirmation pop-up window The System deletes the assignment policy and displays the message ' Assignment policy successfully deleted' The deleted policy is no more visible in the grid. |

UC_Auth_03 Edit an existing Case Policy

| Use Case ID: | UC_Auth_03 |
| --- | --- |
| Use Case Name: | Edit an existing Case Policy |
| Actors: | System, Administrator |
| Description: | This use case describes how the system allows the Administrator to edit/modify a policy selected from list of policies. All Settings are distinguished and independent between each RINA Tenant. |
| Trigger: | The Administrator clicks on the ' Authorization ' main menu option , then clicks 'Assignment Policies' button. |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA Admin |

|  | 3\. The user selected the relevant tenant (top left-hand side of the screen - if there is only 1 tenant, the system displays the default value). 4. The Case Policy to be edited exists in the system. | 3\. The user selected the relevant tenant (top left-hand side of the screen - if there is only 1 tenant, the system displays the default value). 4. The Case Policy to be edited exists in the system. | 3\. The user selected the relevant tenant (top left-hand side of the screen - if there is only 1 tenant, the system displays the default value). 4. The Case Policy to be edited exists in the system. |
| --- | --- | --- | --- |
| Post conditions: | The Administrator has modified a general policy. | The Administrator has modified a general policy. | The Administrator has modified a general policy. |
| Main Scenario: | \# | Step actions | Expected Result |
|  | 1 | The Administrator clicks on the ' Authorization ' main menu option, then clicks 'Assignment Policies' button. | The System displays the 'Assignment Policies' form. |
|  | 2 | The Administrator identifies the policy to be edited in the display grid and clicks on the associated 'Edit' button from the column 'Actions' | The System opens the 'Policy Form' with all fields in edit mode and filled in with the values retrieved from the server |
|  | 3 | The Administrator changes one or more value(s) of the field(s) and/or 'Add'/'Delete'/'Move Up'/'Move Down' any of the rule(s) and clicks on the 'Save' button | The System updates the values on server. The System closes the 'Polic y Form' and returns to 'Assignment Policies' Form. The System displays the message 'Assignment policy successfully saved'. |

UC_Auth_04 Create a new Case Creator Policy

| Use Case ID: | UC_Auth_04 | UC_Auth_04 | UC_Auth_04 |
| --- | --- | --- | --- |
| Use Case Name: | Create a new case creator policy | Create a new case creator policy | Create a new case creator policy |
| Actors: | System, Administrator | System, Administrator | System, Administrator |
| Description: | This use case describes how the System allows the Administrator to define the policy that determines the users that are authorized to create new cases, users of a specific group, or a specific user which has assigned appropriate roles. All Settings are distinguished and independent between each RINA Tenant. | This use case describes how the System allows the Administrator to define the policy that determines the users that are authorized to create new cases, users of a specific group, or a specific user which has assigned appropriate roles. All Settings are distinguished and independent between each RINA Tenant. | This use case describes how the System allows the Administrator to define the policy that determines the users that are authorized to create new cases, users of a specific group, or a specific user which has assigned appropriate roles. All Settings are distinguished and independent between each RINA Tenant. |
| Trigger: | The Administrator clicks on the ' Authorization ' main menu option , then clicks 'Assignment Policies' button. | The Administrator clicks on the ' Authorization ' main menu option , then clicks 'Assignment Policies' button. | The Administrator clicks on the ' Authorization ' main menu option , then clicks 'Assignment Policies' button. |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA Admin 3. The user selected the relevant tenant (top left-hand side of the screen - if there is only 1 tenant, the system displays only the default value) | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA Admin 3. The user selected the relevant tenant (top left-hand side of the screen - if there is only 1 tenant, the system displays only the default value) | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA Admin 3. The user selected the relevant tenant (top left-hand side of the screen - if there is only 1 tenant, the system displays only the default value) |
| Post conditions: | The Administrator completes the configuration of the new creator policy that determines the authorized to create new cases. | The Administrator completes the configuration of the new creator policy that determines the authorized to create new cases. | The Administrator completes the configuration of the new creator policy that determines the authorized to create new cases. |
| Main Scenario: | \# | Step actions | Expected Result |
| Main Scenario: | 1 | The Administrator clicks on the ' Authorization ' main menu option, | The System displays the 'Assignment Policies' form. |

|  | then clicks 'Assignment Policies' button. |  |
| --- | --- | --- |
| 2 | The Administrator click on the 'v' button associated to the 'New Policy' button and selects the option 'Creator New Policy' of this button | The System displays the 'Creator Policy Form', which contains: • 'Name \*' - mandatory, free-text field • 'Description' - free-text field • 'Color' - drop down list with colour icon values (to be associated to a policy, which may provide visual indications in the section Process assign) • Subsection labelled ' Rule X ' ('X' from 1…n) with the following fields: • 'Add' button - when clicked, it adds a new subsection of type 'Rule X' and enables for each displayed 'Rule X' subsection: o 'Move down' button - not available for last added rule o 'Move up' button - not available for first rule o 'Delete' button • Information label - 'When these conditions are met:' • Read-only selection field 'Application Role in' - with possible values: o 'Process Owner' button - selected value o 'Counter Party' button o 'Any' button • 'Sector In' - drop-down list, which contains all the EESSI sectors, i.e., 'FB', 'Pensions', and the generic 'Any' value • 'Process Type In' - drop-down list which contains all the available BUC types of selected Sector and the generic 'Any' value • 'These Users and Groups \*' subsection - with: o 'Select Group' - selection field for indicating the group of the users to be assigned to the case, with associated fields ▪ 'Clear' button ▪ 'Add' button ▪ 'Select User' - activated after a group is selected in the 'Select Group'. |
| 3 | The Administrator fills in the fields, optionally adding and moving | The System creates a new policy, which is listed in policies' list. |

Status: Final / TLP: GREEN

| rules and clicks on the 'Save' button | The System displays a pop-up message 'Assignment policy successfully saved' The System returns to 'Assignment Policy' form with the new case policy added and visible on the grid. |
| --- | --- |

## UC_Auth_05 Edit an existing Case Creator Policy

| Use Case ID: | UC_Auth_05 | UC_Auth_05 | UC_Auth_05 |
| --- | --- | --- | --- |
| Use Case Name: | Edit an existing creator policy | Edit an existing creator policy | Edit an existing creator policy |
| Actors: | System, Administrator | System, Administrator | System, Administrator |
| Description: | This use case describes how the system allows the Administrator to edit/modify the creator policy, selected from list of policies. All Settings are distinguished and independent between each RINA Tenant. | This use case describes how the system allows the Administrator to edit/modify the creator policy, selected from list of policies. All Settings are distinguished and independent between each RINA Tenant. | This use case describes how the system allows the Administrator to edit/modify the creator policy, selected from list of policies. All Settings are distinguished and independent between each RINA Tenant. |
| Trigger: | The Administrator clicks on the ' Authorization ' main menu option , then clicks 'Assignment Policies' button and clicks 'Edit' button . | The Administrator clicks on the ' Authorization ' main menu option , then clicks 'Assignment Policies' button and clicks 'Edit' button . | The Administrator clicks on the ' Authorization ' main menu option , then clicks 'Assignment Policies' button and clicks 'Edit' button . |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA Admin 3. The user selected the relevant tenant (top left-hand side of the screen - if there is only 1 tenant, the system displays the default value). 4. The Case Creator Policy to be edited exists in the system. | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA Admin 3. The user selected the relevant tenant (top left-hand side of the screen - if there is only 1 tenant, the system displays the default value). 4. The Case Creator Policy to be edited exists in the system. | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA Admin 3. The user selected the relevant tenant (top left-hand side of the screen - if there is only 1 tenant, the system displays the default value). 4. The Case Creator Policy to be edited exists in the system. |
| Post conditions: | The Administrator edited the creator policy | The Administrator edited the creator policy | The Administrator edited the creator policy |
| Main Scenario: | \# | Step actions | Expected Result |
| Main Scenario: | 1 | The Administrator clicks on the ' Authorization ' main menu option, then clicks 'Assignment Policies' button. | The System displays the 'Assignment Policies' form. |
|  | 2 | The Administrator identifies the policy to be edited in the display grid and clicks on the associated 'Edit' button from the column 'Actions' | The System opens the 'Creator Policy Form' with all fields in edit mode and filled in with the values retrieved from the server The System show for every rule (including new added) the button 'Process Owner' locked and disabled as this is the one allowed for a 'Creator Policy' |
|  | 3 | The Administrator changes one or more value(s) of the field(s) and/or 'Add'/'Delete'/'Move Up'/'Move Down' any of the rule(s) and click 'Save' button | The System updates the values on server. The System closes the 'Creator Police Form' and return s to 'Assignment Policies' Form. The System displays the message 'Assignment policy successfully saved'. |

Status: Final / TLP: GREEN

## UC_Auth_06 Create a new Group Case Policy

| Use Case ID: | UC_Auth_06 | UC_Auth_06 | UC_Auth_06 |
| --- | --- | --- | --- |
| Use Case Name: | Create a new Group Case Policy | Create a new Group Case Policy | Create a new Group Case Policy |
| Actors: | System, Administrator | System, Administrator | System, Administrator |
| Description: | This use case describes how the System allows the Administrator to configure policies for groups. All settings are distinguished and independent between each RINA Tenant. | This use case describes how the System allows the Administrator to configure policies for groups. All settings are distinguished and independent between each RINA Tenant. | This use case describes how the System allows the Administrator to configure policies for groups. All settings are distinguished and independent between each RINA Tenant. |
| Trigger: | The Administrator clicks on the ' Authorization ' main menu option , then clicks 'Assignment Policies' button. | The Administrator clicks on the ' Authorization ' main menu option , then clicks 'Assignment Policies' button. | The Administrator clicks on the ' Authorization ' main menu option , then clicks 'Assignment Policies' button. |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA Admin 3. The user selected the relevant tenant (top left-hand side of the screen - if there is only 1 tenant, the system displays only the default value) | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA Admin 3. The user selected the relevant tenant (top left-hand side of the screen - if there is only 1 tenant, the system displays only the default value) | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA Admin 3. The user selected the relevant tenant (top left-hand side of the screen - if there is only 1 tenant, the system displays only the default value) |
| Post conditions: | The Administrator has configured the group policies | The Administrator has configured the group policies | The Administrator has configured the group policies |
| Main Scenario: | \# | Step actions | Expected Result |
| Main Scenario: | 1 | The Administrator clicks on the ' Authorization ' main menu option, then clicks 'Assignment Policies' button. | The System displays the 'Assignment Policies' form. |
|  | 2 | The Administrator click on the 'v' button associated to the 'New Policy' button and selects the option 'New Group Policy' of this button. | The System displays the 'Policy Group Form', which contains: • 'Name \*' - mandatory, free-text field • 'Description' - free-text field • 'Color' - list - (to be associated to a policy, which may provide visual indications in the section Process assign) • 'Existing Policy \*' - selection list with possible values all policies defined in the System • 'Save' button • 'Reset' button • 'Back' button |
|  | 3 | The Administrator fills in the fields, selects the policies to be grouped and clicks on the 'Save' button | The System creates a new group policy, which is listed in the list of policies. The System displays a pop-up message 'Assignment policy successfully saved' The System returns to 'Assignment Policy' form with the new case policy group added and visible on the grid. |

## UC_Auth_07 Edit an existing Group Case Policy

| Use Case ID: | UC_Auth_07 | UC_Auth_07 | UC_Auth_07 |
| --- | --- | --- | --- |
| Use Case Name: | Edit group policy | Edit group policy | Edit group policy |
| Actors: | System, Administrator | System, Administrator | System, Administrator |
| Description: | This use case describes how the System allows the Administrator to edit/modify a group policy selected from list of policies. All Settings are distinguished and independent between each RINA Tenant. | This use case describes how the System allows the Administrator to edit/modify a group policy selected from list of policies. All Settings are distinguished and independent between each RINA Tenant. | This use case describes how the System allows the Administrator to edit/modify a group policy selected from list of policies. All Settings are distinguished and independent between each RINA Tenant. |
| Trigger: | The Administrator clicks on the ' Authorization ' main menu option , then clicks 'Assignment Policies' button and clicks 'Edit' button. | The Administrator clicks on the ' Authorization ' main menu option , then clicks 'Assignment Policies' button and clicks 'Edit' button. | The Administrator clicks on the ' Authorization ' main menu option , then clicks 'Assignment Policies' button and clicks 'Edit' button. |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA admin 3. The user selects a relevant tenant (top left-hand side of the screen - if there is only 1 tenant, the system displays only the default value) 4. The Case Creator Policy to be edited exists in the system. | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA admin 3. The user selects a relevant tenant (top left-hand side of the screen - if there is only 1 tenant, the system displays only the default value) 4. The Case Creator Policy to be edited exists in the system. | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA admin 3. The user selects a relevant tenant (top left-hand side of the screen - if there is only 1 tenant, the system displays only the default value) 4. The Case Creator Policy to be edited exists in the system. |
| Post conditions: | The Administrator has modified a group policy | The Administrator has modified a group policy | The Administrator has modified a group policy |
| Main Scenario: | \# 1 | Step actions The Administrator clicks | Expected Result The System displays the |
|  | 2 | The Administrator identifies the group policy to be edited in the display grid and clicks on the associated 'Edit' button from the column 'Actions' . | The System opens the 'Policy Group Form' with all fields in edit mode and filled in with the values retrieved from the server. |
|  | 3 | The Administrator changes one or more value(s) of the field(s) click 'Save' button | The System updates values on server. The System closes 'Police Group Form' and return to 'Assignment Policies' Form. The System displays the message 'Assignment policy successfully saved'. |

## UC_Auth_08 Process assignment

| Use Case ID: | UC_Auth_08 |
| --- | --- |
| Use Case Name: | Process assignment |
| Actors: | System, Administrator |
| Description: | This use case describes how the System allows the Administrator to configure policies at the level of sector or process. The Administrator performs the process manually or automatically. All Settings are distinguished and independent between each RINA Tenant. |

EESSI - RINA - Functional Requirements - Administration Portal Status: Final / TLP: GREEN

|  | The Administrator may go as granular and complex as needed, but it is recommended to keep the structure of groups and policies as simple as possible as a best practice, in order to have a clear view of the installed environment and easy troubleshooting (whenever applicable). | The Administrator may go as granular and complex as needed, but it is recommended to keep the structure of groups and policies as simple as possible as a best practice, in order to have a clear view of the installed environment and easy troubleshooting (whenever applicable). | The Administrator may go as granular and complex as needed, but it is recommended to keep the structure of groups and policies as simple as possible as a best practice, in order to have a clear view of the installed environment and easy troubleshooting (whenever applicable). |
| --- | --- | --- | --- |
| Trigger: | The Administrator clicks on the ' Authorization ' main menu option , then clicks on the 'Process Assignments' button | The Administrator clicks on the ' Authorization ' main menu option , then clicks on the 'Process Assignments' button | The Administrator clicks on the ' Authorization ' main menu option , then clicks on the 'Process Assignments' button |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA admin 3. The user selects the relevant tenant (top left-hand side of the screen - if there is only 1 tenant, the system displays only the default value) | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA admin 3. The user selects the relevant tenant (top left-hand side of the screen - if there is only 1 tenant, the system displays only the default value) | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA admin 3. The user selects the relevant tenant (top left-hand side of the screen - if there is only 1 tenant, the system displays only the default value) |
| Post conditions: | 4\. At least one policy is defined in the System. The Administrator has configured the policies at the level of sectors or processes. | 4\. At least one policy is defined in the System. The Administrator has configured the policies at the level of sectors or processes. | 4\. At least one policy is defined in the System. The Administrator has configured the policies at the level of sectors or processes. |
| Main Scenario: | \# | Step actions | Expected Result |
|  | 1 | The Administrator clicks on the ' Authorization ' main menu option, then clicks on the 'Process Assignments' button | The System displays the 'Process Assignments' form which contains: • 'Refresh' button • 'Export Policies and Assignments' button • 'Import Policies and Assignments' button • An area labelled 'Sectors', containing the list of sectors. For each displayed sector, the Administrator has available a radio button for selecting the sector and a policy icon button for launchi ng the 'Assigned Policies' pop up form • An area labelled 'Processes', with dynamic content: the list of processes (BUCs) pertaining to the selected Sector from the 'Sectors' area. For each displayed process, the Administrator has available a radio button for selecting the process and a policy icon button for launching the 'Assigned Policies' pop up form • An area labelled 'Application Roles', containing the values 'Process Owner' and 'Counter Party'. For each displayed value, the Administrator has available a radio button for selecting the value and a policy icon button for launching the 'Assigned Policies' pop up form • An area labelled 'Actors', containing the values 'Auditor', 'Authorized', 'Medical', 'Nonauthorized', 'Supervisor', 'Viewer', 'VIP'. For each |

|  |  |  | displayed value, the Administrator has available a radio button for selecting the value and a 'cog' icon button that launches the 'Assigned Policies' pop up form. A Sector where there is at least one Process that has no policy assigned, has an icon next to it (top right side of the screen). |
| --- | --- | --- | --- |
|  | 2 | The Administrator clicks on the policy icon button corresponding to a value from the 'Sectors' area. | The System displays the pop-up form 'Assigned Policies', which contains: • Dynamic label with the name of the selected sector • Information label 'All policies from this list are evaluated and their results are cumulated.' • 'Existing Policy \*' selection list field with possible values all policies defined in the System and possibility to search with free text search • 'Save' button |
|  | 3 | The Administrator selects one or more policies and clicks on the ' Save ' button | The System saves data on server. The System closes the pop-up form 'Assigned Policies'. The System display message 'Assignment Policies successfully saved'. |
| Alternative Scenario 1 | 1 | At step 2, the Administrator clicks on the policy icon button corresponding to a value from the 'Processes' area. | The System displays the pop-up form 'Assigned Policies', which contains: • Dynamic label with the name of the selected sector and the name of the selected process • Information label 'All policies from this list are evaluated and their results are cumulated.' • 'Existing Policy \*' selection list field with possible values all policies defined in the System and possibility to search with free text search • 'Save' button Main scenario resumes at step 3. |

Status: Final / TLP: GREEN

| Alternative Scenario 2 | 1 | At step 2, the Administrator clicks on the policy icon button corresponding to a value from the 'Processes' area. | The System displays the pop-up form 'Assigned Policies', which contains: • Dynamic label with the name of the selected sector, the name of the selected process and the name of the selected application role • Information label 'All policies from this list are evaluated and their results are cumulated.' • 'Existing Policy \*' selection list field with possible values all policies defined in the System and possibility to search with free text search • 'Save' button Main scenario resumes at step 3. |
| --- | --- | --- | --- |
| 1 | At step 2, the Administrator clicks on the policy icon button corresponding to a value from the 'Actors' area. | The System displays the pop-up form 'Assigned Policies', which contains: • Dynamic label with the name of the selected sector, the name of the selected process, the name of the selected application role and the name of the selected actor • Information label 'All policies from | Alternative Scenario 3 |
| Alternative |  | At step 3 of main scenario, the Administrator unselects one of the selected policies and clicks on the 'Save' button The System removes the link of the policy from the server. The System closes the pop-up form 'Assigned Policies'. | Scenario 4 |

## UC_Auth_09 Export policies and assignments

| Use Case ID: | UC_Auth_09 |
| --- | --- |
| Use Case Name: | Export policies and assignments |
| Actors: | System, Administrator |

Status: Final / TLP: GREEN

| Description: | This use case describes how the system allows the Administrator to export policies and assignments. The Administrator does it automatically. All Settings are distinguished and independent between each RINA Tenant. | This use case describes how the system allows the Administrator to export policies and assignments. The Administrator does it automatically. All Settings are distinguished and independent between each RINA Tenant. | This use case describes how the system allows the Administrator to export policies and assignments. The Administrator does it automatically. All Settings are distinguished and independent between each RINA Tenant. |
| --- | --- | --- | --- |
| Trigger: | The Administrator clicks on the ' Authorization ' main menu option , then clicks on the 'Export Policies and Assignments' button | The Administrator clicks on the ' Authorization ' main menu option , then clicks on the 'Export Policies and Assignments' button | The Administrator clicks on the ' Authorization ' main menu option , then clicks on the 'Export Policies and Assignments' button |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA admin 3. The user selected the relevant tenant (top left-hand side of the screen - if there is only 1 tenant, the system displays only the default value) 4. Process Assignment and access policies are configured | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA admin 3. The user selected the relevant tenant (top left-hand side of the screen - if there is only 1 tenant, the system displays only the default value) 4. Process Assignment and access policies are configured | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA admin 3. The user selected the relevant tenant (top left-hand side of the screen - if there is only 1 tenant, the system displays only the default value) 4. Process Assignment and access policies are configured |
| Post conditions: | The Administrator exported policies and assignments, which holds the policies and process assignments | The Administrator exported policies and assignments, which holds the policies and process assignments | The Administrator exported policies and assignments, which holds the policies and process assignments |
| Main | \# | Step actions | Expected Result |
| Scenario: | 1 | The Administrator clicks on the ' Authorization ' main menu option, then clicks on the 'Process Assignments' button | The system displays 'Process Assignments' form. |
|  | 2 | The Administrator clicks on the 'Export Policies and Assignments' button | The System exports the configuration file for backup purposes or for new RINA deployments (on the same or different servers that use the same Process Assignment and policies structure). The exported filenames 'ProcessDefinitionAssignments.json', which holds the policies and process assignments. This file can be opened by the Administrator or/and is saved locally. |

UC_Auth_10 Import policies and assignments

| Use Case ID: | UC_Auth_10 |
| --- | --- |
| Use Case Name: | Import policies and assignments |
| Actors: | System, Administrator |
| Description: | This use case describes how the System allows the Administrator to import policies and assignments. All Settings are distinguished and independent between each RINA Tenant. |
| Trigger: | The Administrator clicks on the ' Authorization ' main menu option , then clicks on the 'Import Policies and Assignments' button |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA admin 3. The user selects the relevant tenant (top left-hand side of the screen - if there is only 1 tenant, the system displays only the default value) 4. Process Assignment and access policies are configured |

| Post conditions: | The Administrator imports policies and assignments successfully | The Administrator imports policies and assignments successfully | The Administrator imports policies and assignments successfully |
| --- | --- | --- | --- |
| Main Scenario: | \# | Step actions | Expected Result |
| Main Scenario: | 1 | The Administrator clicks on the ' Authorization ' main menu option, then clicks on the 'Process Assignments' button. | The system displays 'Process Assignments' form |
|  |  | The Administrator clicks on the 'Import Policies and Assignments' button. | The System opens the 'File Explorer' from Operating System. The Administrator selects the JSON file that was successfully exported during the export procedure. A small progress bar appears. It is important to notice that once the import process is complete, the existing (if any) process assignments are replaced by the configuration imported from the selected JSON file. (After importing the 'Exported' policies and Assignments are not automatically activated the Administrator has to EDIT and SAVE the Policies and Assignments in order to obtain a new valid ID in the new system and be applied) |

## Fields Details

## Authorization - Assignment Policies

| No. | Item name | Type | Validation/busines s rules |
| --- | --- | --- | --- |
| 1 | Select tenant (with explanatory notes associated) | List | (a value is selected by default) |
| 2 | Search element |  | Search Delete |
| 3 | Refresh | Button | Refresh screen |
| 4 | New Policy | Button |  |
| 4.1 | Assignment Policies | Grid | Contains columns: Name Description Type Actions Every row has associated 2 buttons: |
| 4.2 | Edit | Button | When click on this button, Creator Policy Form is |

|  |  |  | displayed, which contains: |
| --- | --- | --- | --- |
| 4.2.1 | Name | Free text field | Mandatory |
| 4.2.2 | Description | Free text field |  |
|  | Color | List | Contains colours: (red, yellow, green, blue, violet) |
| 4.2.3 | Rule 1 | Section |  |
| 4.2.4 | Add | Button |  |
| 4.2.5 | Process Owner | Tab | Enabled |
| 4.2.6 | Counterparty | Tab | Disabled |
| 4.2.7 | Any | Tab | Disabled |
| 4.2.8 | Sector in | List |  |
| 4.2.9 | Process Type in | List |  |
| 4.2.10 | Assign to actors | List | Disabled |
| 4.2.11 | These Users And Groups | Free text box field |  |
| 4.2.12 | Select Groups | Free text box field |  |
| 4.2.13 | Clear | Button |  |
| 4.2.14 | Add | Button |  |
| 4.2.15 | Select user | Free text box field |  |
| 4.2.16 | Add | Button |  |
| 4.2.17 | Back | Button |  |
| 4.2.18 | Reset | Button |  |
| 4.2.19 | Save | Button |  |
| 4.3 | Delete | Button |  |
| 5 | New Creator Policy | Area | The system displays Creator Policy Form, see 4.2.1 - 4.219 |
| 6 | New Policy Group | Area | The system displays Policy Group Form, which contains: |
| 6.1 | Name | Free text field | Mandatory |
| 6.2 | Description | Free text field |  |
| 6.3 | Color | List | Contains colours: (red, yellow, green, blue, violet) |
| 6.4 | Existing Policy | List |  |
| 6.5 | Back | Button |  |
| 6.6 | Reset | Button |  |
| 6.7 | Save | Button |  |

## Authorization -Process Assignment

| No. | Item name | Type | Validation/business rules |
| --- | --- | --- | --- |
| 1 | Select tenant (with explanatory notes associated) | List | (a value is selected by default) |
| 2 | Export Policies and Assignments | Button | The system downloads the file with policies |
| 3 | Import Policies and Assignments | Button | The system displays the directories, gives the possibility to choose the file |

Status: Final / TLP: GREEN

| 4 | Refresh | Button | Refresh screen |
| --- | --- | --- | --- |
| 5 | Sectors | Grid | Contains list with all sectors: AWOD Family Benefits Horizontal Legislation Applicable Miscellaneous Pension Recovery Sickness Unemployment Every sector has associated ration button and imagine. At click of imagine, the system displays Assigned Policy form, which contains: |
| 5.1 | 'Sector name' and 'All policies from this list are evaluated and their results are cumulated' | Label |  |
| 5.2 | Existing Policy | List |  |
| 5.3 | Save | Button |  |
| 6 | Processes | List | Contains list with Processes associated to a sector. The list has associated ration buttons and imagine. At click on imagine is displayed Assigned Policies Form |
| 7 | Application roles | List | Contains values Process Owner and Counter Party with associated ration button and imagine. At click on imagine is displayed Assigned Policies form |
| 8 | Actors | List | Contains the Actors list with associated ratio button and imagine. At click on imagine is displayed Assigned Policies form. |

## 6.8 Notification Centre

Use case diagrams

Use Case View

## UC_NC_01 Set Notifications

| Use Case ID: | UC_NC_01 | UC_NC_01 | UC_NC_01 |
| --- | --- | --- | --- |
| Use Case Name: | Set Notifications | Set Notifications | Set Notifications |
| Actors: | System, Administrator | System, Administrator | System, Administrator |
| Description: | This use case describes how the system allows the Administrator to configure: • the notifications to be shown to the users (Clerks) • the notifications to be shown to the administrators • the retention and notification periods for the Business exceptions • the generation of the NIE events per Notification type. For each type of notification, a specific use case can be consulted in the EESSI - RINA - Functional Specs - Case Management document. | This use case describes how the system allows the Administrator to configure: • the notifications to be shown to the users (Clerks) • the notifications to be shown to the administrators • the retention and notification periods for the Business exceptions • the generation of the NIE events per Notification type. For each type of notification, a specific use case can be consulted in the EESSI - RINA - Functional Specs - Case Management document. | This use case describes how the system allows the Administrator to configure: • the notifications to be shown to the users (Clerks) • the notifications to be shown to the administrators • the retention and notification periods for the Business exceptions • the generation of the NIE events per Notification type. For each type of notification, a specific use case can be consulted in the EESSI - RINA - Functional Specs - Case Management document. |
| Trigger: | The Administrator clicks on the 'Notifications Centre' menu option and clicks 'Notifications Settings' butto n | The Administrator clicks on the 'Notifications Centre' menu option and clicks 'Notifications Settings' butto n | The Administrator clicks on the 'Notifications Centre' menu option and clicks 'Notifications Settings' butto n |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA Admin | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA Admin | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA Admin |
| Post conditions: | The Administrator sets up the rules related to what types of notifications are visible for end users and Administrator, configures the retention period and notification periods for the Business Exceptions, and sets up the Business Exception to be automatically sent by RINA without any manual intervention. | The Administrator sets up the rules related to what types of notifications are visible for end users and Administrator, configures the retention period and notification periods for the Business Exceptions, and sets up the Business Exception to be automatically sent by RINA without any manual intervention. | The Administrator sets up the rules related to what types of notifications are visible for end users and Administrator, configures the retention period and notification periods for the Business Exceptions, and sets up the Business Exception to be automatically sent by RINA without any manual intervention. |
| Main Scenario: | \# | Step actions | Expected Result |
| Main Scenario: | 1 | The Administrator clicks on the 'Notifications Centre' menu option, and then clicks on the 'Notification Settings' button | The System displays the 'Notification Settings' form. This form contains a grid displaying all the possible types of notification with the following columns: • ' Notification Type ' : in this column all the types of notifications are displayed: • ' Notification Centre for Clerk' - for each displayed notification, the Administrator has available in this column a checkbox field for selecting if the type of notification is to be displayed to clerks or not. |

| Exception, for the types of notifications ' Business Exception - Unknown Cause ' and 'Business Exception - Case Missing', this option is not available • ' Notification Centre for Admin' - for each displayed notification, the Administrator has available in this column a checkbox field for selecting if the type of notification is to be displayed to the Administrator or not. This option is available only for the types of notifications: o ' Archiving Case Exception ' o ' Case Assignment Exception o ' Business Exception - Attachment failed antimalware checking ' o ' Business Exception - Case Forwarded ' o ' Business Exception - Case Closed ' o ' Business Exception - Unknown Cause ' o ' Business Exception - Invalid ' Business Signature ' o ' Business Exception - SED in Wrong Sequence ' o ' Business Exception - SED update without Create ' o 'A duplicate message arrived' o 'A duplicate SED (update) arrived' o 'A wrong SED (update) arrived' • ' Retention period (in days) \*' and 'Notification period (in days \*') columns, related only to 'Business Exceptions' notifications where the Administrator has available a counter field for setting up the number of days: o ' Business Exception - Attachment failed antimalware checking ' o ' Business Exception - Case Forwarded ' o ' Business Exception - Case Closed ' o ' Business Exception - Unknown Cause ' o ' Business Exception - Invalid Business Signature ' o ' Business Exception - SED in Wrong Sequence ' |
| --- |

| o ' Business Exception - SED update without Create ' 'Retention period (in days)' - is the period of time that needs to elapse since the appearance of the relevant messages under the 'Business Exceptions: Pending Message' form. Upon the expiration of the retention period, the System automatically generates Business Exceptions for the respective incoming Pending Messages and the exception is moved from Pending Messages to Business Exceptions. 'Notification period (in days)' is the period of time that needs to elapse since the appearance of the relevant messages under the 'Business Exceptions: Pending Message' form. Upon this expiration of notification period, the System automatically generates the respective notification) The 'Retention period' parameter should be greater or equal to the 'Notification Period'. According to approved business specifications the default values for 'Retention Period' and 'Notification Per iod' for the Business Exceptions are: o 'Attachment failed antimalware checking': Retention Period = 0; Notification Period = 0 (in days) o 'Case Forwarded: Retention Period =1; Notification Period = 0 (in days) o 'Case Closed': Retention Period = 1; Notification Period = 0 (in days) o 'Unknown Cause': Retention Period = 1; Notification Period = 0 (in days) o 'Invalid Business Signature': Retention Period = 0; Notification Period = 0 (in days) o 'SED in Wrong Sequence': Retention Period = 1; Notification Period = 0 (in days) o 'SED update without Create': Retention Period = 1; |
| --- |

|  |  |  | Notification Period = 0 (in days) o 'Case Removed': Retention Period = 1; Notification Period = 0 (in days) o 'Case Missing': Retention Period = 1; Notification Period = 0 (in days) • 'Generate a NIE event' - for each displayed notification, the Administrator has available in this column a checkbox field for selecting if the type of notification should generate a NIE event • 'Reset' - Button • 'Save' - Button • 'Refresh' - Button |
| --- | --- | --- | --- |
|  | 2 | The Administrator selects the relevant Notification types and configures the appropriate Retention & Notifications periods, the NIE event generation and clicks on 'Save ' button | The System saves data on server The System display the message 'Notifications settings successfully saved'. |
|  | 3 | The Administrator clicks 'Refresh ' button | The System redisplay the form with data from server. |
| Alternative scenario 1 | 1 | At step 2, the Administrator makes changes and then clicks on ' Reset ' button | The System discards all changes on the form. |

UC_NC_02 Filter and visualize notifications

| Use Case ID: | UC_NC_02 |
| --- | --- |
| Use Case Name: | Filter and visualize notifications |
| Actors: | System, Administrator |
| Description: | This use case describes how the System allows the Administrator to access the notifications. The System automatically generates notifications to inform about updates and changes within the existing and new cases. Each type of notification is described in details in the ' EESSI - RINA - Functional Specs - Case Management document ' , except for the ' Case missing ' notification that is described below, in UC_NC_02_extension, as this type of notification is visible only for the Administrator. |
| Trigger: | The Administrator selects 'Notifications Centre' menu option and clicks 'Notifications' option |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA admin |

| Post conditions: | The Administrator consulted the notifications about updates and changes within the existing and about new cases. | The Administrator consulted the notifications about updates and changes within the existing and about new cases. | The Administrator consulted the notifications about updates and changes within the existing and about new cases. |
| --- | --- | --- | --- |
| Main Scenario: | \# | Step actions | Expected Result |
|  | 1 | The Administrator accesses 'Notifications Center' menu option, 'Notifications' option | The System displays the 'Notifications' form. This form has 2 areas: 1. The Display area The notifications are displayed in a grid with the following header: • Checkbox field - when selected all displayed notifications are selected. For each displayed notification, the checkbox field is also available. Clicking on the checkbox field at notification level/ all notification level) activates 2 buttons in the header: • a button labelled 'Mark as Unread' • a button labelled 'Mark as Read' • (show details column)- for each displayed notification, in this column the Administrator has available the'&gt;' button for displaying the details of the notification • (more info column) - for each displayed notification, in this column the Administrator has available two icons: o An info '!' icon - to indicate the type of notification coloured in blue for information notification, yellow for warning notification and red for error notification o The criticality and severity matrix icon of the case • 'Date' - the date when notification was generated • 'Type' - type of notification • 'Description • Actions' - for each displayed notification, an 'Action' button- when clicked displays available actions for that type of notification Under the header, all the relevant notifications are displayed ordered descending by the notification date. The types of notifications generated by the system are: • Warning notifications: o 'A New Case Arrived'; |

Status: Final / TLP: GREEN

| o 'A New SED Arrived'; o 'An Updated SED Arrived'; o 'Approval for Sending Required for SED'; o 'Your Alarm Expired'; o 'Request to Assign Case'; o 'Request to Assign Case Rejected'; o 'Request to Assign Case Accepted'; • Information notifications: o 'Case Unassigned'; o 'Case Assigned'; o 'Case Automatically Closed'; o 'SED Delivered'; o 'Case SEDs Automatically Sent to New Participant'; • Error notifications: o 'Archiving Case Problem'; o 'Case Missing'; o 'Case Assignment Exception'; o 'Attachment failed antimalware checking'; o 'Archiving Case Exception'; o 'SED Update without Create'; o 'SED Failed to be Delivered'; o 'SED in a wrong Sequence'; o 'Case Forwarded'; o 'Invalid Business Signature'; o 'Case Removed'; o 'Unknown Cause'; o 'Case Closed'; o 'A duplicate message arrived' o 'A duplicate SED (update) arrived' o 'A wrong SED (update) arrived' 2. The Search area In the Search area the Administrator has available: • A search button - when clicked refreshes the list of displayed notifications. • A free text field 'Enter case id' for searching notifications related to a case id • A 'filter icon' button |
| --- |

|  | 3 | The Administrator enters a case id in the 'Enter case id' free text and clicks the magnifying glass icon | In the display area, only notifications linked to the search case id are displayed. |
| --- | --- | --- | --- |
|  | 4 | The Administrator clicks the filter icon button and selects needed filters. The filters are checkbox fields, grouped by type. Each grouping has a descriptive label and an x icon to remove the criterion from filter. The groups and criteria are: • 'Severity' group with: o 'Warning' o 'Information' o 'Error' • 'Recent' group with: o 'Unread' o 'Read' • 'Type group' with available values the types of notifications. | Only the notifications complying the selected criteria are displayed. |
|  | 5 | The Administrator clicks the Search button | The System redisplay the list of notifications, and all applied filters are removed. |
| Alternate Scenario 1 | 1 | The Administrator clicks on an individual notification from the list (related to the main section) | The system opens a detailed view and provides information about the case ID, the case type, and a list of assignees. For alerts that require a reaction within a specified time frame, the detail view also shows by which date an action is required. The actual detail views differ for each notification severity category type. |
| Alternative Scenario 2 | 1 | The Administrator selects a bulk of notifications (multiple notifications selected once) | The system automatically selects all notifications from that date (bulk operation) Once the Administrator selects a notification (or more as a bulk) the links ' Mark as Read ' or ' Mark as Unread ' will be visible |
|  | 2 | The Administrator clicks 'Mark as Read' or 'Mark as Unread' | The system sets a notification to read state (if link 'Mark as Read' was clicked). The state can be reset to unread (if 'Mark as Unread' link was clicked) |

## UC_NC_02_extension1 Notification of type 'Case missing'

| Use Case ID: | UC_NC_02_extention1 | UC_NC_02_extention1 | UC_NC_02_extention1 |
| --- | --- | --- | --- |
| Use Case Name: | Notification of type 'Case missing' | Notification of type 'Case missing' | Notification of type 'Case missing' |
| Actors: | System, Administrator | System, Administrator | System, Administrator |
| Description: | This use case describes how the Administrator is notified about the fact that a SED received in the system could not be assigned to any case. When receiving a non-starter SED, the system checks that the international case id referenced in the SED corresponds to an existing local case in the system. If it does not exist, the system automatically generates a notification of type 'Case missing' for the users of the system, based on default settings. Also, for SEDs that cannot be allocated to a case for an unknown reason (a reason that cannot be matched with the X050 SED list of reasons), the same type of notification informs the Administrator about the inability to process the SED. | This use case describes how the Administrator is notified about the fact that a SED received in the system could not be assigned to any case. When receiving a non-starter SED, the system checks that the international case id referenced in the SED corresponds to an existing local case in the system. If it does not exist, the system automatically generates a notification of type 'Case missing' for the users of the system, based on default settings. Also, for SEDs that cannot be allocated to a case for an unknown reason (a reason that cannot be matched with the X050 SED list of reasons), the same type of notification informs the Administrator about the inability to process the SED. | This use case describes how the Administrator is notified about the fact that a SED received in the system could not be assigned to any case. When receiving a non-starter SED, the system checks that the international case id referenced in the SED corresponds to an existing local case in the system. If it does not exist, the system automatically generates a notification of type 'Case missing' for the users of the system, based on default settings. Also, for SEDs that cannot be allocated to a case for an unknown reason (a reason that cannot be matched with the X050 SED list of reasons), the same type of notification informs the Administrator about the inability to process the SED. |
| Trigger: | A new SED is received in the system The Administrator identifies the received notification of type 'Case missing' and clicks on the expand notification button, represented with the '&gt;' icon, in the 'Notifications' workspace. | A new SED is received in the system The Administrator identifies the received notification of type 'Case missing' and clicks on the expand notification button, represented with the '&gt;' icon, in the 'Notifications' workspace. | A new SED is received in the system The Administrator identifies the received notification of type 'Case missing' and clicks on the expand notification button, represented with the '&gt;' icon, in the 'Notifications' workspace. |
| Preconditions: | 1\. The User is authenticated in RINA. 2.1 The SBDH case action of the received SED is different than ' Start ' and 'StartForward' and the International Id of the case referenced in the SED does not match any existing case in the system, or it matches an archived case Or 2.2 The received SED could not be successfully processed and no known cause (i.e., case forwarded, case removed) could be assigned to the failure of processing (for example: Institution not competent for the BUC) 3. The notification of type 'Case missing' is configured to be available for the Administrator and the waiting period configured for this type of notification has passed. | 1\. The User is authenticated in RINA. 2.1 The SBDH case action of the received SED is different than ' Start ' and 'StartForward' and the International Id of the case referenced in the SED does not match any existing case in the system, or it matches an archived case Or 2.2 The received SED could not be successfully processed and no known cause (i.e., case forwarded, case removed) could be assigned to the failure of processing (for example: Institution not competent for the BUC) 3. The notification of type 'Case missing' is configured to be available for the Administrator and the waiting period configured for this type of notification has passed. | 1\. The User is authenticated in RINA. 2.1 The SBDH case action of the received SED is different than ' Start ' and 'StartForward' and the International Id of the case referenced in the SED does not match any existing case in the system, or it matches an archived case Or 2.2 The received SED could not be successfully processed and no known cause (i.e., case forwarded, case removed) could be assigned to the failure of processing (for example: Institution not competent for the BUC) 3. The notification of type 'Case missing' is configured to be available for the Administrator and the waiting period configured for this type of notification has passed. |
| Post conditions: | The User is informed about the received SED that could not be assigned to any existing case. | The User is informed about the received SED that could not be assigned to any existing case. | The User is informed about the received SED that could not be assigned to any existing case. |
| Main Scenario: | \# | Step actions | Expected Result |
| Main Scenario: | 1 | The Administrator identifies the received notification of type 'Case missing' and clicks on the expand notification button, represented with the '&gt;' icon, i n the 'Notifications' workspace. | The System marks the notification as read (the System changes the font of the date, type and description of the notification from bold to un-bolded font). The System displays the details of the notification: 'Local Case Id', the Local Id of the case automatically created by the system |

Status: Final / TLP: GREEN

| 'Case Type', the Sector code and the case type of the case. 'Assignees', the list of users that are assigned to the case. |
| --- |

UC_NC_02_extension2 Notification of type ' Archiving Case Exception '

| Use Case ID: | UC_NC_02_extention2 | UC_NC_02_extention2 | UC_NC_02_extention2 |
| --- | --- | --- | --- |
| Use Case Name: | Notification of type ' Archiving Case Exception ' | Notification of type ' Archiving Case Exception ' | Notification of type ' Archiving Case Exception ' |
| Actors: | System, Administrator | System, Administrator | System, Administrator |
| Description: | This use case describes how the Administrator is notified about the fact that the archiving of a case failed. | This use case describes how the Administrator is notified about the fact that the archiving of a case failed. | This use case describes how the Administrator is notified about the fact that the archiving of a case failed. |
| Trigger: | An automatic archiving process fails for one case. The Administrator receives a notification of type 'Archiving Case Exception ' in the 'Notifications' workspace | An automatic archiving process fails for one case. The Administrator receives a notification of type 'Archiving Case Exception ' in the 'Notifications' workspace | An automatic archiving process fails for one case. The Administrator receives a notification of type 'Archiving Case Exception ' in the 'Notifications' workspace |
| Preconditions: | 1\. The Administrator is authenticated in RINA 2. The Administrator is assigned to the case. 3. An automatic archiving process is performed in the system and one case fails to be archived. 4. The notification of type 'Archiving Case Exceptions ' is configured to be available to the Administrator. | 1\. The Administrator is authenticated in RINA 2. The Administrator is assigned to the case. 3. An automatic archiving process is performed in the system and one case fails to be archived. 4. The notification of type 'Archiving Case Exceptions ' is configured to be available to the Administrator. | 1\. The Administrator is authenticated in RINA 2. The Administrator is assigned to the case. 3. An automatic archiving process is performed in the system and one case fails to be archived. 4. The notification of type 'Archiving Case Exceptions ' is configured to be available to the Administrator. |
| Post conditions: | The Administrator is informed about the failure of the archiving. | The Administrator is informed about the failure of the archiving. | The Administrator is informed about the failure of the archiving. |
| Main Scenario: | \# | Step actions | Expected Result |
| Main Scenario: | 1 | The Administrator identifies the received notification of type 'Archiving Case Exception ' and clicks the expand notification button, represented with the '&gt;' icon, i n the 'Notifications' workspace. | The System marks the notification as read (the System changes the font of the date, type, and description of the notification from bold to un-bolded font). The System displays the details of the notification: 'Local Case Id', the Local Id of the case automatically created by the system 'Case Type', the Sector code and the case type of the case. 'Assignees', the list of users that are assigned to the case. |

Fields Details

## Notification Centre -Notification Settings

| No. | Item name | Type | Validation/business rules |
| --- | --- | --- | --- |
| 1 | Notifications | Grid | Contains columns: Notification Type Notification Center for Admin Notification Center for Clerk Retention Period (in days) Notification Period (In days) Generate a NIE event |
| 2 | Refresh | Button |  |
| 3 | Reset | Button |  |
| 4 | Save | Button |  |

## Notification Centre -Notifications

| No. | Item name | Type | Validation/business rules |
| --- | --- | --- | --- |
| 1 | Search | Element | Has associated - X Button, used to cancel the search - Filter icon. At click on Filter, the system displays: |
| 1.1 | Severity | Check boxes | Associated values: Error, Information, Warning |
| 1.2 | Recent | Check boxes | Associated values: Read, Unread |
| 1.3 | Type | Check boxes | Associated values: A new Case Arrived, A new SED Arrived, etc |
| 2 | Notification | Grid | Contains columns: Date Type Description |

## 6.9 Logs

Use case diagrams

## Use Case View

UC_AL_01 Searching logs

| Use Case ID: | UC_AL_01 | UC_AL_01 | UC_AL_01 |
| --- | --- | --- | --- |
| Use Case Name: | Searching logs | Searching logs | Searching logs |
| Actors: | System Administrator | System Administrator | System Administrator |
| Description: | This use case describes how the system allows the Administrator to search and visualize Audit Logs, related to a time interval, or related to a search for a Case ID | This use case describes how the system allows the Administrator to search and visualize Audit Logs, related to a time interval, or related to a search for a Case ID | This use case describes how the system allows the Administrator to search and visualize Audit Logs, related to a time interval, or related to a search for a Case ID |
| Trigger: | The Administrator selects 'Logs' menu option and selects 'Audit Logs' option | The Administrator selects 'Logs' menu option and selects 'Audit Logs' option | The Administrator selects 'Logs' menu option and selects 'Audit Logs' option |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application |
| Post conditions: | The system displayed Audit Logs for a search related to a time interval or for a Case ID | The system displayed Audit Logs for a search related to a time interval or for a Case ID | The system displayed Audit Logs for a search related to a time interval or for a Case ID |
| Main Scenario: | \# | Step actions | Expected Result |
| Main Scenario: | 1 | The Administrator clicks on the 'Logs' main menu entry and then clicks on the from ' Audit Logs' button | The System displays: • 'From' - date field with calendar enabled functionality • ' t o ' subsection with buttons for selecting the number of days ahead o '1' button o '2' button o '3' button • 'Search' free text field for searching using keywords, with associated magnifying glass icon button to launch the search and x icon button to clear the search. The keyword is typed in the edit box of the searching window in the right part of the top row and the searching algorithm searches for the specific keyword against the entire logs content. The search is not Case Sensitive. The |

Status: Final / TLP: GREEN

|  |  |  | search algorithm uses only the first given keyword regardless the number of the keywords provided in the Search edit box. As keyword can be used: the participant code (i.e., bgna01), the case number (i.e. 20673), the message return by the object (i.e. error). • A filter icon button, when clicked it displays the log filtering panel • A display grid with the following fields: o column for expanding log, each entry has a '&gt;' button o column for category of log, each entry has a coloured icon o 'Date' o 'Event Time' o 'Username' o 'Action Type' |
| --- | --- | --- | --- |
|  | 2 | The Administrator fills in the 'From' and 'To' fields and clicks on the magnifying glass icon button. | The System launches the search and displays in the display grid only the log entries corresponding to the entered dates. Each entry from the display grid has a corresponding '&gt;' icon button. When clicked, the details of the entry are displayed: o 'Outcome' o 'User' o 'Action' o 'Location' o 'Source' o ' Category ' o ' Component ' o ' Objects ' o 'Participants' |
| Alternative scenario 1 |  | The Administrator fills in a keyword in the 'Search' field and clicks on the magnifying glass icon button. | The System launches the search and displays in the display grid only the log entries corresponding to the entered keyword. |
| Alternative scenario 2 |  | The Administrator fills in the 'From' and 'To' fields, fills in a keyword in the 'Search' field and clicks on the magnifying glass icon button. | The System launches the search and displays in the display grid only the log entries corresponding to the entered keyword and dates. |

Status: Final / TLP: GREEN

## UC_AL_02 Filter logs by different values

| Use Case ID: | UC_AL_02 | UC_AL_02 | UC_AL_02 |
| --- | --- | --- | --- |
| Use Case Name: | Filter by different values | Filter by different values | Filter by different values |
| Actors: | System Administrator | System Administrator | System Administrator |
| Description: | This use case describes how the system allows to the Administrator to filter and visualize Audit Logs (filter based on different values: Action type, Component type, Object type, Participant Type, Participant Role, Category Type, Event Type) | This use case describes how the system allows to the Administrator to filter and visualize Audit Logs (filter based on different values: Action type, Component type, Object type, Participant Type, Participant Role, Category Type, Event Type) | This use case describes how the system allows to the Administrator to filter and visualize Audit Logs (filter based on different values: Action type, Component type, Object type, Participant Type, Participant Role, Category Type, Event Type) |
| Trigger: | The Administrator selects 'Logs' menu option and selects 'Audit Logs' option | The Administrator selects 'Logs' menu option and selects 'Audit Logs' option | The Administrator selects 'Logs' menu option and selects 'Audit Logs' option |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application |
| Post conditions: | The system displayed the filtered options. | The system displayed the filtered options. | The system displayed the filtered options. |
| Main Scenario: | \# | Step actions | Expected Result |
| Main Scenario: | 1 | The Administrator clicks on the 'Logs' main menu entry and then clicks on the from ' Audit Logs' button | The System displays the 'Audit Logs' form |
| Main Scenario: | 2 | The Administrator clicks on the filter icon button | The System displays the subsection log filtering panel, which contains different areas: • 'All Log Types' area with checkbox fields with values o 'Success' o 'Error' o 'Unauthorized' • 'Action Type' area with checkbox fields with values o 'Read' o 'Create' o 'Update' o 'Delete' o 'Execute' • 'Component Type' area with checkbox fields with values o 'Security' o 'Notifications' o 'Search Definitions' o 'Business Messaging' o 'Cases' o 'Administration' o 'Documents' o 'Attachments' o 'Comments' o 'Technical Messaging' • 'Participant Type' area with checkbox fields with values : o 'Organization' o 'Person' |

Status: Final / TLP: GREEN

| • 'Participant Role' area with checkbox fields with values : o 'Receiver' o 'Sender' o 'Subject' • 'Object Type' area: o 'Notification' o 'Credential' o 'Business Error' o 'Business Acknowledge' o 'Alarm' o 'Comment' o 'Attachment' o 'Subdocument' o 'Search Definition' o 'Business Message' o 'Case' o 'User Profile' o 'Policy' o 'Document' o 'Technical Message' o 'Application Profile' o 'User Group' • 'Category Type' area: o 'Security' o 'Business' o 'Messaging' • 'Event Type' area: o 'Retrieve Case Id By International Id' o 'Submit Attachment On Document' o 'Create Document' o 'Import Subdocument Batch' o 'Create Search Definition' o 'Logout' o 'Delete Attachment On Document' o 'Export Subdocument Batch' o 'Application Start' o 'Submit Document' o 'Receive Technical Message' o 'Change Authorization Policy' o 'Retrieve Notifications Consolidated' 'Summary' o 'Update Document' o 'Update Search Definition' o 'Send Document' o 'Retrieve Initial Document' o 'Set Alarm' o 'Delete Attachment on Case' o 'Create User Or Group' o 'Retrieve Case By Id' o 'Send Business Message' o 'Retrieve Attachment On Document' |
| --- |

Status: Final / TLP: GREEN

Fields Details

|  |  | o 'Retrieve Case By International Id' o 'Submit Attachment on Case' o 'Retrieve Case Hash Code By Id' o 'De lete Comment On Document' o 'Retrieve Notification Time Slots' o 'Login' o 'Retrieve Case Assignments' o 'Submit Comment On Document' o 'Update User Profile' o 'Retrieve Attachment on Case' o 'Clear Alarm' o 'Delete Document' o 'Update Application Profile' o 'Retrieve Notification Summary' o 'Retrieve Document' o 'Delete Comment On Case' o 'Submit Comment On Case' o 'Notify About Received Business Message' o 'Assign Case' o 'Send Technical Message' o 'Retrieve Notification Details' o 'Create New Case' o ' Delete User Or Group' o 'Notify About Status Update' o 'Retrieve Thumbnail' o 'Application End' o 'Search Cases By Search Definition And Or Free- Text' |
| --- | --- | --- |
| 2 | The Administrator selects the filters | The System displays in the display grid the entries that match the selected filters. |

## Audit Logs

| No. | Item name | Type | Validation/business rules |
| --- | --- | --- | --- |
| 1 | Calendar | Date element | Insert date From… |
| 2 | Days (ahead) | Buttons | At click displays 3 tabs: 1 Day, 2Days, 3Days |
| 3 | Search | Search element | Search Delete (search) |

| 4 | Filter | Imagine | At click of this imagine, the system displays: |
| --- | --- | --- | --- |
| 4.1 | Filter by All Logs types | Check box | Values: Success, Error, Unauthorized |
| 4.2 | Filter by Action type | Check box | Values: Read, Create, Update, Delete, |
| 4.3 | Filter by Component type | Check box | Execute Values: Administration Attachments Business Messaging Cases Comments Documents Notifications Search Definitions Security Technical Messaging |
| 4.4 | Filter by Participant type | Check box | Values: Organization Person |
| 4.5 | Filter by Participant role | Check box | Values: Receiver Sender Subject |
| 4.6 | Filter by Object type | Check box | Values: Action Alarm Application Profile Attachment Business Acknowledge Business Error Business Message Case Comment Credential Document Notification Policy Search Definition Subdocument Technical Message User Group User Profile |
| 4.7 | Filter by Category type | Check box | Values: Security Business Messaging |
| 4.8 | Filter by Event type | Check box | Values: Application End Application Start Archive / Unarchive Case Assign Case |

Status: Final / TLP: GREEN

Use Case View

UC_TL_01 Searching technical logs

| Use Case ID: | UC_TL_01 |
| --- | --- |
| Use Case Name: | Searching technical logs |
| Actors: | System, Administrator |
| Description: | This use case describes how the System allows the Administrator to visualize basic troubleshooting information directly in the RINA portal. The Administrator perform very granular searches to pinpoint to the dates, type of information and area of interest. |

|  |  |  | Change Authorization Policy Clear Alarm Create Document Create New Case Create Search Definition Create User Or Group, etc |
| --- | --- | --- | --- |
| 5 | Total Records: | Label | The system displays the number of audit logs records |
| 6 | Audit logs | Grid | Contains columns: Date Event type Username Action Type Description |

## 6.10 Technical Logs

Use case diagrams

| Trigger: | The Administrator clicks on the 'Logs' main menu entry and then clicks on the from 'Technical Logs' button | The Administrator clicks on the 'Logs' main menu entry and then clicks on the from 'Technical Logs' button | The Administrator clicks on the 'Logs' main menu entry and then clicks on the from 'Technical Logs' button |
| --- | --- | --- | --- |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA admin | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA admin | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA admin |
| Post conditions: | The Administrator performed granular search and the system displayed troubleshooting information list. | The Administrator performed granular search and the system displayed troubleshooting information list. | The Administrator performed granular search and the system displayed troubleshooting information list. |
| Main Scenario: | \# | Step actions | Expected |
|  | 1 | The Administrator clicks on the 'Logs' main menu entry and then clicks on the from ' Technical Logs' button | Result The system displays the 'Technical Logs' form. This form contains: • 'From' - date field with calendar enabled functionality • 'to ' subsection with buttons for selecting the number of days ahead o '1' button o '2' button o '3' button • 'Search' free text field for searching using keywords, with associated magnifying glass icon button to launch the search and x icon button to clear the search. The keyword is typed in the edit box of the searching window in the right part of the top row and the searching algorithm searches for the specific keyword against the entire logs content. The search is not Case Sensitive. The search algorithm uses only the first given keyword regardless the number of the keywords provided in the ' Search ' field . • 'Search' button for launching the search • A filtering icon, when clicked it displays the technical logs filtering panel • A display grip with following columns: o column for expanding log, each entry has a '&gt;' button o column for category of log, each entry has a coloured icon o 'Date' o 'Type' o 'Level' |
|  | 2 | The Administrator fills in the 'From' and 'To' fields and clicks on the | The System launches the search and displays in the display grid only the |

Status: Final / TLP: GREEN

|  | magnifying glass icon button. | log entries corresponding to the entered dates. Each entry from the display grid has a corresponding '&gt;' icon button. When clicked, the details of the entry are displayed: o 'Source' o ' Level ' o ' Logger Name ' o ' Thread ' o ' Message ' |
| --- | --- | --- |
| Alternative scenario 1 | The Administrator fills in a keyword in the 'Search' field and clicks on the magnifying glass icon button. | The System launches the search and displays in the display grid only the log entries corresponding to the entered keyword. |
| Alternative scenario 2 | The Administrator fills in the 'From' and 'To' fields, fills in a keyword in the 'Search' field and clicks on the magnifying glass icon button. | The System launches the search and displays in the display grid only the log entries corresponding to the entered keyword and dates. |

UC_TL_02 Filter technical logs by Log level

| Use Case ID: | UC_TL_02 | UC_TL_02 | UC_TL_02 |
| --- | --- | --- | --- |
| Use Case Name: | Filter technical logs by Log level | Filter technical logs by Log level | Filter technical logs by Log level |
| Actors: | System, Administrator | System, Administrator | System, Administrator |
| Description: | This use case describes how the System allows the Administrator to visualize Technical logs filtered by log level | This use case describes how the System allows the Administrator to visualize Technical logs filtered by log level | This use case describes how the System allows the Administrator to visualize Technical logs filtered by log level |
| Trigger: | The Administrator clicks on the 'Logs' main menu entry and then clicks on the from 'Technical Logs' button | The Administrator clicks on the 'Logs' main menu entry and then clicks on the from 'Technical Logs' button | The Administrator clicks on the 'Logs' main menu entry and then clicks on the from 'Technical Logs' button |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application |
| Post conditions: | The system displayed Technical Logs filtered by log level | The system displayed Technical Logs filtered by log level | The system displayed Technical Logs filtered by log level |
| Main Scenario: | \# | Step actions | Expected Result |
|  | 1 | The Administrator clicks on the 'Logs' main menu entry and then clicks on the from ' Technical Logs' button | The System displays the ''Technical Logs' form. |
|  | 2 | The Administrator clicks on the filter icon. | The system displays the filtering panel with: • 'All Log Types' area with checkbox fields with values: o 'AP Client' o 'REST' o 'BUC Engine' • 'Log Level' area with checkbox fields with values: o 'Trace', |

Status: Final / TLP: GREEN

|  |  | o 'Error', o 'Info', o 'Fatal', o 'Debug' o 'Warn'. |
| --- | --- | --- |
| 3 | The Administrator filters by log level | The system displays the list with Technical logs related to this filter. The list can be expanded for every technical log. |

## UC_TL_03 Filter technical logs by categories

| Use Case ID: | UC_TL_03 | UC_TL_03 | UC_TL_03 |
| --- | --- | --- | --- |
| Use Case Name: | Filter technical logs by categories | Filter technical logs by categories | Filter technical logs by categories |
| Actors: | System, Administrator | System, Administrator | System, Administrator |
| Description: | This use case describes how the system allows the Administrator to visualize Technical Logs related to a particular category | This use case describes how the system allows the Administrator to visualize Technical Logs related to a particular category | This use case describes how the system allows the Administrator to visualize Technical Logs related to a particular category |
| Trigger: | The Administrator clicks on the 'Logs' main menu entry and then clicks on the from 'Technical Logs' button | The Administrator clicks on the 'Logs' main menu entry and then clicks on the from 'Technical Logs' button | The Administrator clicks on the 'Logs' main menu entry and then clicks on the from 'Technical Logs' button |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application |
| Post conditions: | The system displayed Technical Logs based on a search by category | The system displayed Technical Logs based on a search by category | The system displayed Technical Logs based on a search by category |
| Main Scenario: | \# | Step actions | Expected Result |
| Main Scenario: | 1 | The Administrator clicks on the 'Logs' main menu entry and then clicks on the from ' Technical Logs' button | The System displays the ''Technical Logs' form. |
|  | 2 | The Administrator clicks on the filter icon. | The system displays the filtering panel with: • 'All Log Types' area with checkbox fields with values: o 'AP Client' o 'REST' o 'BUC Engine' • 'Log Level' area with checkbox fields with values: o 'Trace', o 'Error', o 'Info', o 'Fatal', o 'Debug' o 'Warn'. |
|  | 3 | The Administrator filters by log type. | The system displays the list with Technical logs related to this filter. The list can be expanded for every technical log. |

Fields Details

## Technical Logs

| No. | Item name | Type | Validation/business rules |
| --- | --- | --- | --- |
| 1 | Calendar | Date element | Insert date From… |
| 2 | Days (ahead) | Buttons | At click displays 3 tabs: 1 Day, 2Days, 3Days |
| 3 | Search | Search element | Search Delete (search) |
| 4 | Filter | Imagine | At click of this imagine, the system displays: |
| 4.1 | Filter by All Logs types | Check box | Values: AP Client REST |
| 4.2 | Filter by Log Level | Check box | Values: TRACE ERROR INFO DEBUG FATAL WARN |
| 5 | Total Records: | Label | The system displays the number of audit logs records |
| 6 | Technical logs | Grid | Contains columns: Date Event type Username Action Type Description |

## 6.11 Automatic Updates

Use case diagrams

Use Case View

UC_AU_01 Configure the settings for automatic updates

| Use Case ID: | UC_AU_01 | UC_AU_01 | UC_AU_01 |
| --- | --- | --- | --- |
| Use Case Name: | Configure the settings for automatic updates | Configure the settings for automatic updates | Configure the settings for automatic updates |
| Actors: | System, Administrator | System, Administrator | System, Administrator |
| Description: | This use case describes how the system allows the Administrator to configure the settings for automatic updates | This use case describes how the system allows the Administrator to configure the settings for automatic updates | This use case describes how the system allows the Administrator to configure the settings for automatic updates |
| Trigger: | The Administrator clicks on the 'Automatic Updates' button form main menu | The Administrator clicks on the 'Automatic Updates' button form main menu | The Administrator clicks on the 'Automatic Updates' button form main menu |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application |
| Post conditions: | The Administrator has configured the settings for automatic updates | The Administrator has configured the settings for automatic updates | The Administrator has configured the settings for automatic updates |
| Main Scenario: | \# | Step actions | Expected Result |
| Main Scenario: | 1 | The Administrator clicks on the 'Automatic Updates' button form main menu | The System display s the 'Automatic Updates' form that contains : • 'Refresh' button • 'Sync' button with associated '&gt;' button - when clicked, the 'Sync Institutions' and 'Sync CDM' options become available • 'Install ' button • 'Import Organizations' button |

|  |  | • 'Search' free-text field with associated 'x' button and magnifying glass icon • 'Settings' button • filter icon button. • grid labelled 'To Install ()' - for displaying the performed automatic updates, with following structure: • header of the sub-section labelled based on the type of resource (i.e., 'Organizations' , 'SEDs', 'Transactions') with associated checkbox field for selected all resources displayed and '+/ - ' icon - when clicked expands/hides the content of the grid. • for each displayed sub-section, the following columns are available: o 'Type' o 'Status' o 'Disk Version' o 'Disk Date' |
| --- | --- | --- |
| 2 | The Administrator click on the 'Settings' button | The System displays ' Automatic Updates Settings' form, which contains: • 'Disk Resources Path on Server \*' - free text field, mandatory - the path where the content is downloaded from CSN (through AP). • 'Shared Configuration Path \*' - free text field, mandatory • 'Shared BMP Repository Path \*' - free text field • - 'Form Templates Repository Path \*' - free text field • 'Office Templates Repository Path \*' - free text field • 'Localization Resources Repository Path \*' - free text field • 'Save' button • 'Reset' button |

Status: Final / TLP: GREEN

| 3 The fills in the clicks on button |  | Administrator fields and the 'Save' | The System saves the data into the server. The System closes the 'Automatic Updates Settings' form and return s to 'Automatic Updates' form. |
| --- | --- | --- | --- |
| 1 | The Administrator fills in the fields and click on the 'Reset' button | The System discards values from the fields and return values from server. The main scenario can be resumed at step 3. | Alternative scenario 1 |

UC_AU_02 Synchronising the Institution Repository

| Use Case ID: | UC_AU_02 | UC_AU_02 | UC_AU_02 |
| --- | --- | --- | --- |
| Use Case Name: | Synchronising the Institution Repository | Synchronising the Institution Repository | Synchronising the Institution Repository |
| Actors: | System, Administrator | System, Administrator | System, Administrator |
| Description: | This use case describes how the system allows the Administrator to synchronize of the Institution Repository (IR) | This use case describes how the system allows the Administrator to synchronize of the Institution Repository (IR) | This use case describes how the system allows the Administrator to synchronize of the Institution Repository (IR) |
| Trigger: | The Administrator selects 'Automatic Updates' menu option | The Administrator selects 'Automatic Updates' menu option | The Administrator selects 'Automatic Updates' menu option |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA admin 3. The user configured the settings for automatic updates | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA admin 3. The user configured the settings for automatic updates | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA admin 3. The user configured the settings for automatic updates |
| Post conditions: | The system has synchronized the Institution Repository (IR) | The system has synchronized the Institution Repository (IR) | The system has synchronized the Institution Repository (IR) |
| Main Scenario: | \# | Step actions | Expected Result |
|  | 1 | The Administrator clicks on the 'Automatic Updates' button form main menu | The System displays the 'Automatic Updates' |
|  | 2 | The Administrator clicks on the '&gt;' button associated to the 'Sync' button and then clicks on the 'Sync Institutions' button | The System displays ' SYN002 - Request for IR Sync' form, which contains: • ' Current version ' - mandatory, free-text field - parameter is used for the IR request sent to the AP • ' Save ' button • ' Reset ' button • 'Back' button |
|  | 3 | The Administrator fills in the field and clicks on the ' Save ' button | The System sends the IR synchronisation request to the AP. (Upon finalisation of this operation, the RINA application sends a system message to the AP to request the latest IR version (SYN002 message). The AP responds in an asynchronous manner with the new version file (in case there is any), or without any file (if Current Version of RINA sent request has the latest |

Status: Final / TLP: GREEN

|  |  |  | available version). The referred file is provided as attachment onto the received SYN001 system (sync) message. Any new files are persisted under the defined (via the configuration) disk resource path of the application system) The System closes ' SYN002 - Request For IR Sync' form and displays message 'Success. Request for IR Sync.' (Recommendations : The Automatic Updates (CDM & IR Synchronisation) are time consuming operations and cannot be instantly completed (this is also depending on the volume as it is described above). Therefore, the administrator should monitor the operation progress: o related to receiving the files by checking their existence at the level of the system (Holodeck component) o o related to the deployment by pressing the refresh button periodically (with the period varying on the list of deployed files per operation, i.e., the more files, the longer the period). |
| --- | --- | --- | --- |
| Alternative Scenario 1 | 1 | The Administrator clicks on ' Reset' button | The system reset any parameter modified during editing regarding 'Current Version'. |

## UC_AU_03 Synchronisation of CDM

| Use Case ID: | UC_AU_03 |
| --- | --- |
| Use Case Name: | Synchronisation of CDM |
| Actors: | System, Administrator |
| Description: | This use case describes how the system allows the Administrator to request the synchronization of the Common Data Model (CDM) |
| Trigger: | The Administrator clicks on the 'Automatic Updates' button form main menu |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application 3. The user configured the settings for automatic updates |
| Post conditions: | The system allows synchronization of the Common Data Model (CDM) |

Status: Final / TLP: GREEN

| Main | \# | Step actions | Expected Result |
| --- | --- | --- | --- |
| Scenario: | 1 | The Administrator clicks on the 'Automatic Updates' button form main menu | The System displays the 'Automatic Updates' |
|  | 2 | The Administrator clicks on the '&gt;' button associated to the 'Sync' button and then clicks on the 'Sync CDM' button | The System displays 'SYN005 - CDM Sync Status' form, which contains: • 'CMD Sync Status' section • 4 'Artefact Request' subsections, each containing o 'Artefact Group' -mandatory radio button selection filed . The available choices for requests are: ▪ 'BMP' for Business processes ▪ 'RINA_BL' for the artefacts concerning RINA Business Layer ▪ 'RINA_PL'' for the corresponding artefacts of the RINA Protocol Layer ▪ 'AP' (Access Point) Artefacts. Each of the 4 subsections has selected a distinct value for this field o Time Sync Up To - mandatory, calendar field o Add button - add subsection Artefact Request o Delete button The Administrator provides information about which artefact group(s) need(s) to be synchronized with the AP. The number of groups to be synchronised can be customised along with the date of the latest synchronisation date in RINA to the CDM request from the AP. The Administrator can add/remove a request by simple clicking on ' Add' button or ' Delete ' button. - ' Save ' button |
|  | 2 | The Administrator fills in the fields and clicks 'Save' button | The Administrator sends the request. The system (RINA application) sends a system message to the AP to request the latest CDM content based on the related requested artefact groups (SYN005 message). The AP |

Status: Final / TLP: GREEN

|  |  |  | responds in an asynchronous manner with the new file (in case there is any newer related content), or an empty file (if RINA has the latest data content). Any new files are persisted under the defined (via the configuration) disk resource path of the application system. (Recommendation: The 'Automatic Upd ates: CDM sync' feature is used when the CDM artefacts are not installed during the installation procedure but the new CDM artefacts are published from CSN) |
| --- | --- | --- | --- |
| Alternative scenario 1 | 1 | The Administrator clicks ' Reset ' button | The System discards all values modified during editing. |

## UC_AU_04 Detecting and deploying the updated artefacts

| Use Case ID: | UC_AU_04 | UC_AU_04 | UC_AU_04 |
| --- | --- | --- | --- |
| Use Case Name: | Detecting and deploying the updated artefacts | Detecting and deploying the updated artefacts | Detecting and deploying the updated artefacts |
| Actors: | System, Administrator | System, Administrator | System, Administrator |
| Description: | This use case describes how the system allows the Administrator to perform the actions in order to complete the synchronisation processes and update all the corresponding artefacts (select the relevant 'Resource Type' category(ies), refresh the displayed information, Install artefacts) | This use case describes how the system allows the Administrator to perform the actions in order to complete the synchronisation processes and update all the corresponding artefacts (select the relevant 'Resource Type' category(ies), refresh the displayed information, Install artefacts) | This use case describes how the system allows the Administrator to perform the actions in order to complete the synchronisation processes and update all the corresponding artefacts (select the relevant 'Resource Type' category(ies), refresh the displayed information, Install artefacts) |
| Trigger: | The Administrator clicks on the 'Automatic Updates' button from main menu. | The Administrator clicks on the 'Automatic Updates' button from main menu. | The Administrator clicks on the 'Automatic Updates' button from main menu. |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application and configured the settings options. 3. The user has performed UC_AU_02 or UC_AU_03 for synchronising. | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application and configured the settings options. 3. The user has performed UC_AU_02 or UC_AU_03 for synchronising. | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application and configured the settings options. 3. The user has performed UC_AU_02 or UC_AU_03 for synchronising. |
| Post conditions: | The Administrator has filtered the artefacts, refreshed the displayed information, and initiated the installation process (started the deployment of the artefacts). | The Administrator has filtered the artefacts, refreshed the displayed information, and initiated the installation process (started the deployment of the artefacts). | The Administrator has filtered the artefacts, refreshed the displayed information, and initiated the installation process (started the deployment of the artefacts). |
| Main Scenario: | \# | Step actions | Expected Result |
| Main Scenario: | 1 | The Administrator clicks on the 'Automatic Updates' button from main menu. | The System displays the 'Automatic Updates' form. |
| Main Scenario: | 2 | The Administrator clicks on the filter icon button | The System displays the 'Filter by' subsection which contains: • area for selecting the resource type labelled 'Resource Type' with associated 'x' button for clearing the current selections. In this area, the available fields are: o 'Localization' checkbox field |

|  |  | o 'Vocabularies' checkbox field o 'SEDs' checkbox field o 'Form Templates' checkbox field 'SBDHs' checkbox field o 'Organizations' checkbox field o 'Transactions' checkbox field o 'Initial Documents' checkbox field • area for selecting the status labelled ' Status ' with associated 'x' button for clearing the current selections. In this area, the available fields are: o 'Same Version Everywhere' o 'Older Version On Disk' o 'On Disk Only' o 'Installed Only' |
| --- | --- | --- |
| 3 | The Administrator selects the desired filters and clicks on ' Refresh ' icon. | The System hides the 'Filter by' subsection and refreshes the displaying grid by displaying only the selected resources types. |
| 4 | The Administrator selects the exact resources that should be installed by clicking on the checkbox field of the resources group and clicks on the 'Install' button to trigger the deployment process of the corresponding artefacts. | The System launches the installation process (start the deployment of the artefacts). On the successful completion of the deployment operation, the red rectangle icons are converted to green colour to indicate that the resource type has been updated, meaning that there is no new relevant update available. (Recommendations: In case of a large update, where the number of generated artefacts to be synchronized is huge (i.e., hundreds or thousands of artefacts), it is strongly recommended to install ONLY one artefacts resource type at a time and to repeat the procedure until all the necessary artefacts are correctly installed. If an artefact type contains many updates to get deployed, it is also recommended to get this operation performed over multiple steps by selecting a file subset of such long lists at a time) |

## UC_AU_05 Importing Organizations

| Use Case ID: | UC_AU_05 |
| --- | --- |

| Use Case Name: | Importing Organizations | Importing Organizations | Importing Organizations |
| --- | --- | --- | --- |
| Actors: | System, Administrator | System, Administrator | System, Administrator |
| Description: | This use case describes how the system allows the Administrator the manual import of the IR from a local file | This use case describes how the system allows the Administrator the manual import of the IR from a local file | This use case describes how the system allows the Administrator the manual import of the IR from a local file |
| Trigger: | The Administrator selects 'Automatic Updates' menu option and clicks on the 'Import Organizations' button | The Administrator selects 'Automatic Updates' menu option and clicks on the 'Import Organizations' button | The Administrator selects 'Automatic Updates' menu option and clicks on the 'Import Organizations' button |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application 3. The user configured the settings for Automatic Updates | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application 3. The user configured the settings for Automatic Updates | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application 3. The user configured the settings for Automatic Updates |
| Post conditions: | The system allowed the manual import of the IR from a local file. | The system allowed the manual import of the IR from a local file. | The system allowed the manual import of the IR from a local file. |
| Main Scenario: | \# | Step actions | Expected Result |
| Main Scenario: | 1 | The Administrator clicks on the 'Automatic Updates' button form main menu | The System displays the 'Automatic Updates' form. |
| Main Scenario: | 2 | The Administrator clicks on the 'Import Organization' button | The system opens 'File Explorer' from operating system. The Administrator has the option to import an organization structure directly through local files, this action allows the manual import of the IR from a local file. |

UC_AU_06 Checking Repository Versions

| Use Case ID: | UC_AU_06 | UC_AU_06 | UC_AU_06 |
| --- | --- | --- | --- |
| Use Case Name: | Checking Repository Versions | Checking Repository Versions | Checking Repository Versions |
| Actors: | System, Administrator | System, Administrator | System, Administrator |
| Description: | This use case describes how the system allows the Administrator to check the available repository file versions | This use case describes how the system allows the Administrator to check the available repository file versions | This use case describes how the system allows the Administrator to check the available repository file versions |
| Trigger: | The Administrator selects 'Automatic Updates' menu option | The Administrator selects 'Automatic Updates' menu option | The Administrator selects 'Automatic Updates' menu option |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application 3. The user configured the settings for automatic updates | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application 3. The user configured the settings for automatic updates | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application 3. The user configured the settings for automatic updates |
| Post conditions: | The system allowed the Administrator to check the available repository file versions | The system allowed the Administrator to check the available repository file versions | The system allowed the Administrator to check the available repository file versions |
| Main Scenario: | \# | Step actions | Expected Result |
| Main Scenario: | 1 | The Administrator clicks on the 'Automatic Updates' button from main menu. | The System displays the 'Automatic Updates' form. |
| Main Scenario: | 2 | The Administrator accesses 'Automatic Updates' menu option, then main area (ex: 'Organizations ( 2 ) +)' | The System display the full (expanded) detail list via clicking the '+ ' icon next to the relevant entry. This can be reverted by clicking the relevant ' - ' icon which has replaced the ' - ' icon following the content expansion. |

Status: Final / TLP: GREEN

## Fields Details

## Automatic Updates

| No. | Item name | Type | Validation/busines s rules |
| --- | --- | --- | --- |
| 1 | Search | Search element | Search with associated X, Delete (search) |
| 2 | Filter | Imagine | At click of this imagine, the system displays: |
| 2.1 | Filter by All Resource Type | Check box | Values: Localization Vocabularies SEDs Form Templates SBDHs Organizations Transactions Initial Documents |
| 2.2 | Filter by Status | Check box | Values: Same Version Everywhere Older Version On Disk On Disk Only Installed Only Newer Version on Disk |
| 3 | Setting | Imagine | The system displays Automatic Updates Settings, which contains: |
| 3.1 | Disk Resources Path On Server | Free text box fields | Mandatory, (C:/EESSI/Share/cd m/) |
| 3.2 | Shared Configuration Path | Free text box fields | Mandatory, (C:/EESSI/Share/) |
| 3.3 | Shared BMP Repository Path | Free text box fields | Mandatory, (C:/EESSI/Share/rep ository/bmp/) |
| 3.4 | Form Templates Repository Path | Free text box fields | Mandatory, (C:/EESSI/Share/por tal/templates/) |
| 3.5 | Office Templates Repository Path | Free text box fields | Mandatory, (C:/EESSI/Share/por tal/office_templates/ ) |
| 3.6 | Localization Resources Repository Path | Free text box fields | Mandatory, (C:/EESSI/Share/por tal/localization/) |
| 3.7 | Back | Button |  |
| 3.8 | Reset | Button |  |
| 3.9 | Save | Button |  |

Status: Final / TLP: GREEN

| 4 | Import organizations | Button | At click open directory window, offers the possibility to choose a file from directory |
| --- | --- | --- | --- |
| 5 | Install 0 | Button | Disabled |
| 6 | Refresh | Button |  |
| 7 | To Install (0) | Label | Has associated imagine used to expand or contract grid |
| 8 | Organization | Grid | Contains columns: Type Status Disk version Disk date Server version Server date |
| 9 | Sync Institution | List | The system displays SYN002 - Request For IR Sync form, which contains: |
| 9.1 | Request For IR Sync | Label |  |
| 9.2 | 1.1 Current Version | Free text box field | Mandatory |
| 9.3 | Back | Button |  |
| 9.4 | Reset | Button |  |
| 9.5 | Save | Button |  |
| 10 | Sync CMD | List | The system displays SYN005 - CDM Sync Status form, which contains: |
| 10.1 | CDM Sync Status | Label |  |
| 10.2 | 1.1\[1\]. Artefact Request | Section |  |
| 10.2.1 | 1.1.1. Artefact Group | Ratio buttons | Mandatory Values: \[01\] BMP \[02\] RINA_BL \[03\] RINA_PL \[04\] AP |
| 10.2.2 | 1.1.2. Time Sync Up To | Calendar |  |
| 10.2.3 | Add | Button |  |
| 10.2.4 | Delete | Button |  |
| 10.3 | Back | Button |  |
| 10.4 | Reset | Button |  |
| 10.5 | Save | Button |  |

## 6.12 Test Center

Use case diagrams

Use Case View

UC_TC_01 Test Center & Check Status of Access Point Endpoint (Network)

| Use Case ID: | UC_TC_01 | UC_TC_01 | UC_TC_01 |
| --- | --- | --- | --- |
| Use Case Name: | Test Center & Check Status of Access Point Endpoint (Network) | Test Center & Check Status of Access Point Endpoint (Network) | Test Center & Check Status of Access Point Endpoint (Network) |
| Actors: | System, Administrator | System, Administrator | System, Administrator |
| Description: | This use case describes how the system allows the Administrator to perform some basic testing of RINA's network connectivity to EESSI International Domain. | This use case describes how the system allows the Administrator to perform some basic testing of RINA's network connectivity to EESSI International Domain. | This use case describes how the system allows the Administrator to perform some basic testing of RINA's network connectivity to EESSI International Domain. |
| Trigger: | The Administrator selects 'Test Center' from main menu | The Administrator selects 'Test Center' from main menu | The Administrator selects 'Test Center' from main menu |
| Preconditio ns: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA Admin | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA Admin | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application as RINA Admin |
| Post conditions: | The system allowed testing Rina network connectivity to EESSI International Domain | The system allowed testing Rina network connectivity to EESSI International Domain | The system allowed testing Rina network connectivity to EESSI International Domain |
| Main Scenario: | \# | Step actions | Expected Result |
|  | 1 | The Administrator clicks on the 'Test Center' button from main menu | The system displays the 'Test Center' form, where the Administrator has available: • 'Refresh' button • 'Check Status of Access Point Endpoint' button • a grid where performed tests are displayed. The grid has a dynamic label - 'Total |Successful:|Failed : ' and the following columns: o 'Date' o 'Message' o 'Status' |
|  | 2 | The Administrator clicks ' Check Status of Access Point Endpoint (Network) ' button | The System performs a ' Sanity test '. This test that can be used to test mainly the status of the Access Point (AP) at which RINA is connected. The System displays the performed test in the display grid. |
|  | 1 | The Administrator clicks on 'Refresh' button | The System redisplays the form. |

Fields Details

## Test Center

| No. | Item name | Type | Validation/business rules |
| --- | --- | --- | --- |
| 1 | Check Status of Access Point Endpoint (Network) | Button |  |
| 2 | Refresh | Button | Refresh screen |
| 3 | Total: | Successful: | Failed: | Label |  |
| 4 | (tests grid) | Grid | Contains columns: Date Message Status |

## 6.13 Business Exceptions

Use case diagrams

Use Case View

UC_BE_01 Pending messages

| Use Case ID: | UC_BE_01 |
| --- | --- |
| Use Case Name: | Pending messages |
| Actors: | System, Administrator |
| Description: | This use case describes how the Administrator can consult the list of pending messages and manually intervene for generating a business exception for the pending message. |
| Trigger: | The Administrator selects 'Business Exceptions' menu option and clicks 'Pending Messages' option |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application |

Status: Final / TLP: GREEN

| Post conditions: | The Administrator had the possibility to consult list of pending messages and to manually send back to the SED originator a | The Administrator had the possibility to consult list of pending messages and to manually send back to the SED originator a | The Administrator had the possibility to consult list of pending messages and to manually send back to the SED originator a |
| --- | --- | --- | --- |
| Main Scenario: | \# | Step actions | Expected Result |
|  | 1 | The Administrator accesses 'Business Exceptions' menu option and then 'Pending Messages' option | The system displays 'Pending Messages' form which contains: • 'Search' button • (search) free text field • filter icon button • grid displaying the pending messages with columns: o 'Date' o 'Type' o 'Description' o 'Actions' - for each displayed pending message, the Administrator has available ▪ ' Reject ' button The list with pending messages contains received SEDs for which the System identified an issue that requires a waiting period before automatically generating a business exception (this issue could be solved by receiving another SED). Additional information about these exceptions may be found in the document 'EESSI Business Use Case AD_BUC_11'. For each displayed SED, the Administrator also has available a '&gt;' icon butto n. |
|  | 2 | The Administrator selects a pending message from the grid and clicks on the '&gt;' icon button. | The System expands the display area for the selected pending message with the following fields: • 'Problem' • 'Date' • 'SED type' • 'BUC type' • 'International Case Id' • 'Sender' • 'Participants' (list with tenants) |
| Alternative Scenario 1 | 1 | The Administrator identifies the pending message and clicks on the corresponding 'Reject' button | The System displays the 'Reject Messages' form, where the Administrator has available: • 'Reason\*' - free text field for providing the rejection reason • 'Yes' button • 'No' button |
|  | 2 | The Administrator fills in the 'Reason\*' field | The System sends back to the SED originator a business exception (X050 SED) message. |

| and clicks on the 'Yes' button | The System close the 'Reject Messages' form. The System delete the pending message from the grid. |
| --- | --- |

UC_BE_02 Business exceptions

| Use Case ID: | UC_BE_02 | UC_BE_02 | UC_BE_02 |
| --- | --- | --- | --- |
| Use Case Name: | Business exceptions | Business exceptions | Business exceptions |
| Actors: | System, Administrator | System, Administrator | System, Administrator |
| Description: | This use case describes how the Administrator can consult the list of the SEDs that caused the business exception | This use case describes how the Administrator can consult the list of the SEDs that caused the business exception | This use case describes how the Administrator can consult the list of the SEDs that caused the business exception |
| Trigger: | The Administrator selects 'Business Exceptions' menu option and clicks 'Business Exceptions' option | The Administrator selects 'Business Exceptions' menu option and clicks 'Business Exceptions' option | The Administrator selects 'Business Exceptions' menu option and clicks 'Business Exceptions' option |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application |
| Post conditions: | The Administrator consulted the list of the SED that caused the business exception. | The Administrator consulted the list of the SED that caused the business exception. | The Administrator consulted the list of the SED that caused the business exception. |
| Main Scenario: | \# | Step actions | Expected Result |
| Main Scenario: | 1 | The Administrator accesses 'Business Exceptions ' main menu and then 'Business Exceptions' option | The system displays 'Business Exceptions' form which contains: • 'Search' button • (search) free text field • filter icon button • grid displaying the received SEDs that caused a business exception to be generated, with the following columns: o 'Date' o 'Type' o 'Description' For each displayed SED, the Administrator also has available a '&gt;' icon button. |
|  | 2 | The Administrator selects a SED from the grid and clicks on the corresponding '&gt;' icon button. | The System expands the display area for the selected SED with the following fields: • 'Rejection Date' • 'Rejection reason' • 'Problem' • 'Date' • 'SED type' • 'BUC type' • 'Local Case Id' • 'International Case Id' • 'Sender' • 'Participants' (list with tenants) |

## UC_BE_03 Filter, refresh, and search notification of business exceptions

| Use Case ID: | UC_BE_03 |
| --- | --- |

| Use Case Name: | Filter, refresh, and search notification of business exceptions | Filter, refresh, and search notification of business exceptions | Filter, refresh, and search notification of business exceptions |
| --- | --- | --- | --- |
| Actors: | System, Administrator | System, Administrator | System, Administrator |
| Description: | This use case describes how the system allows the Administrator to filter, refresh list and search elements in order to display and treat business exceptions, grouped by year (displayed in Navigate section) | This use case describes how the system allows the Administrator to filter, refresh list and search elements in order to display and treat business exceptions, grouped by year (displayed in Navigate section) | This use case describes how the system allows the Administrator to filter, refresh list and search elements in order to display and treat business exceptions, grouped by year (displayed in Navigate section) |
| Trigger: | The Administrator selects 'Business Exceptions' menu option and clicks on the 'Business Exceptions' option | The Administrator selects 'Business Exceptions' menu option and clicks on the 'Business Exceptions' option | The Administrator selects 'Business Exceptions' menu option and clicks on the 'Business Exceptions' option |
| Preconditions: | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application | 1\. The user is authenticated in RINA. 2. The user is authorized to access Application |
| Post conditions: | The Administrator has performed search, refresh, and filtered business exceptions | The Administrator has performed search, refresh, and filtered business exceptions | The Administrator has performed search, refresh, and filtered business exceptions |
| Main Scenario: | \# | Step actions | Expected Result |
|  | 1 | The Administrator clicks on the 'Business exceptions' button from main menu, then clicks on the 'Business exceptions' button. | The system displays 'Business Exceptions' form which contains: • 'Search' button • (search) free text field • filter icon button • grid displaying the received SEDs that caused a business exception to be generated, with the following columns: o 'Date' o 'Type' o 'Description' o 'Actions' - for each displayed SED, in this column, the Administrator has available the following buttons: ▪ 'View SED' ▪ 'View Rejection SED' For each displayed SED, the Administrator also has available a '&gt;' icon button. |
|  | 2 | The Administrator clicks on the filter icon button | The System displays the 'Filter by' subsection which contains: • 'Business Exception' label with x icon button to clear all selections • Multiple selection checkbox fields with following values: o 'Case Missing' checkbox field o 'SED Update without Create' checkbox field o 'Case Forwarded' checkbox field o 'Case Removed' checkbox field o 'SED in Wrong Sequence' checkbox field o 'Case Closed' checkbox field o 'Invalid Business Signature' checkbox field o 'Attachment failed antimalware checking' checkbox field |

| 3 The selects filters outside | Administrator the desired and clicks the 'Filter by' subsection | The System displays only the SEDs that caused a business exception related to the selected filters. |
| --- | --- | --- |
| 4 The enters the keywords by in the search clicks on | Administrator to search free text field and the 'Search' button | The System displays only the SEDs containing the keyword provided by the Administrator. |
| 1 | The Administrator clicks 'Refr esh ' button | The System redisplays the form. |

## Fields Details

## Business Exceptions -Pending messages

| No. | Item name | Type | Validation/business rules |
| --- | --- | --- | --- |
| 1 | Search | Search element | Search Delete |
| 2 | Filter by - Business exceptions | Check boxes | Values: Case Missing SED Update without Create Case Forwarded Case Removed SED in Wrong Sequence Case Closed Invalid Business Signature Attachment failed antimalware checking |
| 3 | Total Records: | Label |  |
| 4 | Pending messages | Grid | Contains columns: Date Type Description Actions |

## Business Exceptions -Business Exceptions

| No. | Item name | Type | Validation/business rules |
| --- | --- | --- | --- |
| 1 | Search | Search element | Search Delete |
| 2 | Filter by - Business exceptions | Check boxes | Values: Case Missing SED Update without Create Case Forwarded |

Status: Final / TLP: GREEN

|  |  |  | Case Removed SED in Wrong Sequence Case Closed Invalid Business Signature Attachment failed antimalware checking |
| --- | --- | --- | --- |
| 3 | Total Records: | Label |  |
| 4 | Pending messages | Grid | Contains columns: Date Type Description Actions |
