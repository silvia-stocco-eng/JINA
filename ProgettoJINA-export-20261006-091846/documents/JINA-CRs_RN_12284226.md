---
unique-name: JINA-CRs_RN_12284226
display-name: JINA-CRs RN:12284226 — Archiving and Backup Solution for RINA/JINA
category: CR
description: Change Request RN:12284226 — Implementazione di una soluzione dedicata di archiviazione e backup per i dati RINA/JINA, per ridurre l'espansione continua del disco e migliorare le performance di PostgreSQL e Elasticsearch. Categoria: Urgent Change, Reporter: Anselmi Milko.
tags: change-request, cret
---

# JINA-CRs_RN_12284226

JINA-CRs\_ RN:12284226

RN:12284226

(CIG 9623953142)

| Column 1 | Column 2 | Column 3 |
| --- | --- | --- |
| Date: 15th Dec. 2025 |  | Doc. Version: 1.0<br>Status: Draft |

## Document Control Information

| Settings | Value |
| --- | --- |
| Document Title: | JINA-CRs\_ RN_12284226 |
| Project Id: | CIG 9623953142 |
| Document Authors: | EY |
| Project Owner: | Barbara Ingrosso (PO) |
| Project Manager: | Milko Anselmi (PM) |
| Doc. Version: |  |
| Sensitivity: | Reserved |
| Date: | 15th Dec. 2025 |

| Name | Role | Action | Date |
| --- | --- | --- | --- |
|  |  | &lt;Approve / Review&gt; |  |

| Revision | Date | Created by | Short Description of Changes |
| --- | --- | --- | --- |

## About this Document

This document serves as a template for the correct submission of change requests by users on the SDAS platform. It outlines the business needs of the customer and is not intended to describe the impact and effort of potential development. Following its completion and signature by the change request evaluation team, this document will be forwarded to the supplier in order to request an impact analysis of the requirement.

| Status | Waiting for Customer |
| --- | --- |
| Project | RINA Handover |
| Component/s | JINA |
| Affect Version/s |  |
| Release Date |  |
| Slot |  |
| Priority |  |
| Reporter | ANSELMI MILKO (IT) |
| Labels |  |
| Category | Urgent Change |
| Impact area | Others |
| Issue Links |  |

# Purpose

## Objective

The primary objective of this change request is to implement a dedicated archiving and backup solution for the data currently stored in RINA/JINA.

The existing system lacks the necessary components for effective data archiving and backup, leading to continuous disk space expansion. This situation not only increases infrastructure costs but also negatively affects system performance, particularly the response times of our PostgreSQL database and queries on Elastic Search.

By introducing a dedicated archiving tool and establishing common guidelines for all participating countries, we aim to streamline data management processes. This change will enhance system efficiency, reduce operational costs, and improve overall performance.

The cost estimate for this initiative has been developed based on parametric analysis, considering the technical specifications and scale of the system.

## Business Impact

Implementing this change is crucial for maintaining optimal system performance.

For more information regarding the different case statuses, see the attached screen in the Appendix 1: References and Related Documents taken from the User Manual.

# Current scenario (AS-IS)

The current scenario involves significant challenges in managing data within the RINA/JINA system due to the absence of dedicated archiving and backup components. This lack of tools necessitates continuous expansion of disk space, leading to rising infrastructure costs and deteriorating performance, particularly in the response times of the PostgreSQL database and Elastic Search queries. Additionally, there are no standardized guidelines for data management across participating countries, resulting in inefficiencies. Over time, these countries have expressed a clear need for a structured solution to address these issues, underscoring the urgency for improvement in data management practices.

# Future Scenario (TO-BE)

The future scenario envisions the implementation of a dedicated archiving and backup solution for the RINA/JINA system. This will enable efficient data management, significantly reducing the need for continuous disk space expansion and lowering infrastructure costs. With improved tools in place, the performance of the PostgreSQL database and Elastic Search queries will enhance, leading to faster response times and a better user experience. Additionally, standardized guidelines for data management will be established across all participating countries, promoting consistency and efficiency. Overall, this strategic initiative will position the organization to manage data more effectively, support future growth, and optimize operational performance.

## Use Case

Use Case: Data Management Improvement for RINA/JINA System

Scenario: The RINA/JINA system will implement dedicated archiving and backup components, leading to efficient data management and reduced infrastructure costs.

Key steps:

- The archiving and backup solution will be developed and implemented, ensuring integration with existing systems and improved performance metrics for databases and queries.
- Standardized data management guidelines and training programs will be established for all countries to promote consistency and efficiency in data handling.

# Architecture IT

No architectural modification is required. The supplier is referred to assess any impacts and modifications necessary to ensure the operability of the solution, which will be proposed by the supplier in order to comply with the requirement that is the subject of this document.

## AS-IS

## TO-BE

# Non-functional requirements

No modification is required. As a result, the log management process may be subject to change. The supplier is referred to assess any impacts and modifications necessary to ensure the operability of the solution, which will be proposed by the supplier in order to comply with the requirement that is the subject of this document.

# Service Desk ticket discussion

| Contact | Activity | Date | Comments |
| --- | --- | --- | --- |
| MASINI SILVIA |  | 03/12/2025 17:16:13 | From Active to Waiting for Customer: Correction: 'fast track change' should read 'urgent change'. |
| MASINI SILVIA |  | 03/12/2025 17:14:55 | From Customer Action Ready to Active: |
| MASINI SILVIA |  | 03/12/2025 17:14:52 | From Waiting for Customer to Customer Action Ready: |
| MASINI SILVIA |  | 03/12/2025 17:11:45 | From Active to Waiting for Customer: This request is forwarded to the "CRs evaluation Team" of the JPA beneficiaries. The TGC asks to evaluate the request and to register it in the CRs backlog. This Change Request is categorized as Fast Track since it has already been agreed upon during the Technical Board with the supplier. |
| MASINI SILVIA |  | 03/12/2025 17:10:46 | From Accepted to Active: |
| MASINI SILVIA |  | 03/12/2025 17:10:42 | From Invoked to Accepted: |
| ANSELMI MILKO |  | 03/12/2025 16:46:13 | From Intake to Invoked: null |
| ANSELMI MILKO |  | 03/12/2025 16:46:13 | Created new Request: RN:12284226 |

# Appendix 1: References and Related Documents

| \# | Reference or Related Document | Source or Link/Location |
| --- | --- | --- |
| 1 |  |  |

# Appendix 2: Screenshot from SDAS

| \# | Reference or Related Document | Source or Link/Location |
| --- | --- | --- |
| 1 |  |  |

# Appendix 3: Attachments

| \# | Related File | Source or Link/Location |
| --- | --- | --- |
| 1 |  |  |

# Appendix 4: ACRONYMS

| Acronyms | Description |
| --- | --- |
| CDM | Command Data Model |
| CTS | Software Compatibility Test Suite |
| DEV | Development |
| Doc | Documents |
| EESSI | Electronic Exchange of Social Security Information |
| ENV | Environment |
| FP | Function Point |
| HL | High Level |
| MB | Management Board |
| PT | Penetration Test |
| SAST | Static Analysis |
| SD&AS | Service Desk & Asset System |
| SSU | Scheda di Start-Up (Italian) |
| SW | Software |
| TB | Technical Board |
| TGC | Temporary Grouping of Companies |
| WAPT | Web Application Penetration Test |
