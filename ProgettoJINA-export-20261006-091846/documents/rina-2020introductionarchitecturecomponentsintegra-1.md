---
unique-name: rina-2020introductionarchitecturecomponentsintegra-1
display-name: RINA 2020 Introduction Architecture Components Integration D1afternoon
category: GENERAL
tags: ec
---

Day 1 - Afternoon

<!-- image -->

<!-- image -->

## RINA 2020

## Introduction, Architecture, Components, Integration

<!-- image -->

<!-- image -->

## Table of content

- Core functionalities

- Layers

- Architecture overview

- Components: key concepts and integration

- ➢

- Sequence diagrams: Create case, Create SED, Send message, Receive message

<!-- image -->

## RINA Core functionalities

<!-- image -->

<!-- image -->

## RINA Layers

<!-- image -->

Reusable components

Strict separation of concerns

Strict object modeling per component

APIs for integration with N.A.

Production deployment options:

1. Full stack ( Standalone / Distributed )

2. BMI - WS

3. No RINA

<!-- image -->

## RINA Layers - core functionalities

<!-- image -->

<!-- image -->

## RINA Architecture overview

<!-- image -->

## Message exchange - ebMS 3.0. AS4 protocol

<!-- image -->

<!-- image -->

## Business message

<!-- image -->

<!-- image -->

## Business messaging protocol

- Minimal standard - all N.A. must adhere to produce business messages that can be accepted as fully validated transactions within EESSI
- Defines constraints for business and data validation integrating the key aspects: BUC s, SBDH and SED models
- EESSI BMP transaction specifies rules for:
- o a specific SED
- o for a specific participant role
- o in the context of a specific BUC
- XML v1.0 - validation via XSD ( transaction XSD artefacts. Sample: P\_BUC\_01-4.2-CaseOwner-Counterparty-Start-P2000-4.2.xsd )
- Security : XAdES-BES signature with X.509 business certificates
- Types of messages: SED (Business), SYN (System)
- Business message status: READY, SENT, DELIVERED, ERROR

<!-- image -->

## BMS &amp; TMS

## BMS

- BMS core technical component: ApClient
- Translation
- Transformation
- Signing with business certificate
- Transaction validation
- Antimalware scan
- Notifies registered listeners of received messages, status updates and signatures
- Message State Machine Repository
- Generates configuration for TMS (pmodes)

## TMS

- TMS core technical component: HolodeckB2B
- Communication with AP via ebMS 3.0. AS4 protocol
- Generates receipt and error signal messages
- Signing with MSG certificate
- Compression / decompression of content
- Validates ebMS message
- Message duplication mechanism and retry mechanism
- PULL &amp; PUSH mode
- Dynamic configuration (pmodes)

<!-- image -->

## BMS MS vs. BMS WS - Client integration

<!-- image -->

<!-- image -->

<!-- image -->

## BMS &amp; TMS Integration

<!-- image -->

<!-- image -->

<!-- image -->

- Includes business logic and encapsulates stateful case processing functionalities and configuration
- Integration with BUC-Engine -synchronous execution of calls
- Exposes RESTFul Web Services
- Relational SQL database for storing business data
- Transactionality
- Caching entities on server side
- Data integrity by validations and enforcing constraints on DB level
- Data consistency across concurrent access
- Schedulers for pending messages, pending status update, pending signatures, alarms, archiving
- WebSocket for notifications
- SED Validation ( SED XSD artefacts )

<!-- image -->

## CPS - Design

<!-- image -->

REST Web Services

Transactional Spring services

Spring components

Spring Data Repository

<!-- image -->

## CPS - RESTFul Web Services

<!-- image -->

## CPS - Configuration files

- jpa.properties
- hazelcast.xml
- db.properties
- restClient.conf
- elasticSearch.conf
- casAuthentication.conf
- apmicroservice-client.conf
- niemicroservice-client.conf
- bucengine.conf
- cpiSchedulers.conf
- Single Sign On Authentication module
- Open-source third-party Java implementation by Apereo
- CAS 3.0 protocol - ticket-based
- Cache for ticket registry
- Custom implementation of authentication handlers:
1. Username / password authentication
2. LDAP authentication
- Deployable as .war

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

## NIE

- Interacts with N.A. via RESTful web services in order to exchange information regarding case management
- Subscriptions on events associated to: cases, documents, subdocuments, notifications
- Async / sync events
- Reliability :
- o save event part of the transaction
- o retry mechanism
- Integrates with CPS SQL DB
- Dynamic configuration
- Deployable as .war

<!-- image -->

<!-- image -->

## BUC-Engine

- Custom lightweight BUC processing framework
- Custom BUC definition language ( XML )
- Common Case and Document processing ( Java )
- API for integration
- Strict modeling / Domain objects
- Abstract persistence layer
- Supports action locking mechanism
- Class loader per BUC-process version
- Deployed as a library in CPS

<!-- image -->

## BUC-Engine

<!-- image -->

<!-- image -->

## Audit &amp; Logging Trailing

## CPS Auditing

- Part of the business transaction
- Audit logs persisted in SQL Database
- Retrieval authorization: admin vs. regular users

## BMS Auditing

- Audit logs persisted in ES Database

## Technical Logging

- On all components
- Log4j - external files
- CPS and BMS logs ingested by Logstash and persisted in ElasticSearch
- CPS header enhanced with username and tenant id
- GDPR compliant

<!-- image -->

## Performance improvements

- Upgrade to Java 11 &amp; library upgrades ( Spring 5.2, CAS 6.1.6 )
- Custom, lightweight BUC-Engine framework, deployed as library inside CPS
- BUC processes as JARs, xml definition and Java handlers
- Synchronous calls between CPS and BUC-Engine
- Relational database
- Caching
- Tuning
- Refactored code, strict layers
- Improved resilience between components
- Improved security

<!-- image -->

## Sequence diagram: Create case

<!-- image -->

<!-- image -->

CreateCase Portal CaseProcessing Interface(CPI)

CreateCase

watchCase

GetCase&amp;actions

GetCase&amp;actions CaseProcessing Interface Subscription NewCase CasesService Institution Services CheckBUCAssignments Authorisation Services BUCEngine Subscribe to case CreatenewCo Case compute assignments notify case created notify New Notification(s)

Notifications Service

execute actjon,

process and persist hext actions

create notifications

audit New Case triggerAsyncNIEEvent notify newCase Audit Service Subscription Service new Case commited internal event NIE Service notify NIE listenernew Case

## Sequence diagram: Send message

<!-- image -->

<!-- image -->

Create SED

Send SED

Portal Create SED (Open Form)

Case Processing

Interface (CPI)

Case

Listener Interface

Processing Message

retrieve

initial document

Sequence diagram: Send message

SED(Subm

Send SED (Get Initial Send Form)

Send SED (submit action)

Document Services

Validate &amp; persist

Execute Create SED Action

Document Content validate, execute and unlock acion process and persist next actions

audit, notify subscriptions, create notificatios

trigger NIE Event validate, execute and unlock acion trigger send process and persist next actions send action commit event

BUC Engine Messaging Services BMS MS

transform to business message

publish internal send event

async send TMI

(ang ))

validate, transform,

antimalware etc

sign,

ananbua dequeue TMS

send to AP

## Sequence diagram: Receive message

<!-- image -->

<!-- image -->

Receive Message dequeuereceived message internal processing

(transformation etc)

on Message Received Case

Sequence diagram: Receive message

enqueue receiveMessage route message persist pending message async process (handle)

Message create case or and document metadata and content dispatch Message store attachments audit,notify subscriptionsreatenotificatis trigger NIE Event BUC Engine dispatchandersistuemssauatemtadt execute action, compute and persist next actions

## Reference

- EESSI 2020 - RINA - Architecture Overview
- EESSI 2020 - RINA - Case Processing Interface (CPI)
- EESSI 2020 - RINA - CPI Reference Documentation
- EESSI 2020 - RINA - Business Messaging Interface (BMI)
- EESSI 2020 - RINA - National Information Exchange Interface (NIE)
- EESSI 2020 - RINA - Identity and Access Management (IAM)
- EESSI - RINA - Business Use Case Engine Architecture
- EESSI - AS4 - Messaging profile
- EESSI - Business Messaging Protocol
- EESSI - Business Message Signing
- EESSI - CDM - SBDH Implementation guide
- EESSI 2020 - RINA - 6.2.1 Operations manual ( also 6.2.3 version could be used instead )
- EESSI 2020 - RINA - 6.2.1 Deployment guidelines ( also 6.2.3 version could be used instead )

<!-- image -->

## Thank you

<!-- image -->

## © European Union 1995 - 2021

Unless otherwise noted the reuse of this presentation is authorised under the CC BY 4.0 license. For any use or reproduction of elements that are not owned by the EU, permission may need to be sought directly from the respective right holders.

<!-- image -->