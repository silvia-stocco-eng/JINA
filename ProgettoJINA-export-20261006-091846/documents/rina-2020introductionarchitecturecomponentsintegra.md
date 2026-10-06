---
unique-name: rina-2020introductionarchitecturecomponentsintegra
display-name: RINA 2020 Introduction Architecture Components Integration
category: GENERAL
tags: ec
---

<!-- image -->

<!-- image -->

## RINA 2020

## Introduction, Architecture, Components, Integration

<!-- image -->

<!-- image -->

## EESSI introduction

- Training calendar &amp; agenda
- EESSI introduction
- EESSI architecture
- CSN
- AP
- RINA integration

<!-- image -->

## Training calendar

- RINA - introduction, architecture, components, integration 30 - 31 March
- Business Use Cases - BUC Engine / BUC Processes 29 - 30 April
- RINA Case Processing Service (CPS) / RINA Business Messaging Service (BMS) 25 - 26 May
- RINA Portal 24 - 25 June
- RINA DevOps / tools / maintenance 14 - 16 July

<!-- image -->

## Training agenda

- Day 1
- EESSI introduction
- RINA presentation
- RINA demo
- Questions / Answers

## · Day 2

- BUC Processes
- RINA Portal
- BUC Processes demo
- RINA portal demo
- Questions / Answers

<!-- image -->

## EESSI

- Electronic Exchange of Social Security Information
- EESSI is a system that allows institutions in charge of tasks related to the social security to exchange data electronically
- Main benefits
- Faster handling and exchange of data and decision-making process
- More efficient validation of data exchanged
- Exchanges will be done electronically

<!-- image -->

## EESSI

- Connects about 6.000 social security institutions across Europe and support the international data exchanges
- EESSI supports data exchanges for the implementation of the European social security regulations
- 2 fundamentals area of networks
- International Domain
- National Domain

<!-- image -->

## EESSI system layout

<!-- image -->

<!-- image -->

## EESSI presentation

- Architecture overview
- business, information, application, technology
- EESSI components
- CSN
- AP
- RINA
- RINA in EESSI platform

<!-- image -->

## Business architecture

- Business Use Case (BUC)
- BUC specifications using UML
- Each BUC includes
- BPMN 2.0
- The Decision of the Business Documents
- Case
- An instance of a BUC
- 2 primary actors : Case Owner (CO), Counterparty (CP)

<!-- image -->

## Business architecture

<!-- image -->

Core Business Process-Instantiableprocesshandlinga specificbusinessscenario

Sub Process - Reusable process part that is used by a core process or another sub process

- More than 100 BUCS organized in 9 sectors
- Administrative BUCs
- Sub Processes

<!-- image -->

## Information architecture

<!-- image -->

- Structured Electronic Documents (SED)
- Standard Business Document Header (SBDH)
- Business Messaging Protocol (BMP)
- Common Data Model (CDM)

<!-- image -->

## EESSI Message exchange representation

<!-- image -->

<!-- image -->

## Technology architecture

- CSN
- ASP.net MVC, Angular
- Windows deployment
- AP
- BizTalk Server
- Windows deployment
- RINA
- JAVA 11, Angular 10
- Windows or Ubuntu deployment
- EESSI Central Service Node (CSN)
- Designating the components that will be hosted centrally (e.g. hosted by European Commission)

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

## CSN

- Main functions
- Repository Management
- Repository Synchronisation
- Authentication and Authorisation Management
- Reporting and Statistics
- Logging and Audit Trail

<!-- image -->

## AP

- Holds components common to all countries
- Built on top of BizTalk Server
- Developed centrally, but deployed and hosted in the participant countries
- Main components
- AS4 messaging
- Business (EESSI cases)
- System (IR Sync, CDM Sync, Audit trail sync)
- Monitoring API - exposed for CSN
- Management portal

<!-- image -->

## Thank you

<!-- image -->

© European Union 1995 - 2021

Unless otherwise noted the reuse of this presentation is authorised under the CC BY 4.0 license. For any use or reproduction of elements that are not owned by the EU, permission may need to be sought directly from the respective right holders.

<!-- image -->