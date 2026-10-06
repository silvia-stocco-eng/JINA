---
unique-name: jina-crsrn12284233
display-name: JINA CRs RN 12284233
category: GENERAL
description: <a id="1.4_______________References"></a>__Objective__: The primary objective of this change request is to enhance the __search functionality__ of the Business Use Cases \(BUC\) in the portal by repla
---

<a id="eltqTitle"></a><a id="_Hlk177047302"></a><a id="_Toc153988781"></a><a id="_Toc153899483"></a><a id="1.__________________Introduction"></a>

JINA\-CRs\_ RN:12284233

__                                               RN:12284233__

\(CIG 9623953142\)

	

Date: 15th Dec\.  2025

Doc\. Version: 1\.0

  Status: Draft

__Document Control Information__

__Settings__

__Value__

__Document Title:__

JINA\-CRs\_ RN\_12284233

__Project Id:__

CIG 9623953142

__Document Authors:__

EY 

__Project Owner: __

Barbara Ingrosso \(PO\)

__Project Manager: __

Milko Anselmi \(PM\)

__Doc\. Version: __

__Sensitivity: __

Reserved

__Date: __

15th Dec\. 2025

__Document Approver\(s\) and Reviewer\(s\):__

NOTE: All Approvers are required\. Records of each approver must be maintained\. All Reviewers in the list are considered required unless explicitly listed as Optional\.

__Name__

__Role__

__Action__

__Date__

*<Approve / Review>*

__Document history:__

The Document Author is authorized to make the following types of changes to the document without requiring that the document be re\-approved:

- Editorial, formatting, and spelling
- Clarification

To request a change to this document, contact the Document Author or Owner\.

Changes to this document are summarized in the following table in reverse chronological order \-\(latest version first\)\.

__Revision__

__Date__

__Created by__

__Short Description of Changes__

__Configuration Management: Document Location __

The latest version of this controlled document is stored in *EESSIGateway:  *

__INDEX__

1	Purpose	\- 5 \-

2	Current scenario \(AS\-IS\)	\- 6 \-

3	Future Scenario \(TO\-BE\)	\- 7 \-

3\.1	Use Case	\- 7 \-

4	Architecture IT	\- 8 \-

4\.1	AS\-IS	\- 8 \-

4\.2	TO\-BE	\- 8 \-

5	Non\-functional requirements	\- 9 \-

6	Service Desk ticket discussion	\- 10 \-

Appendix 1: References and Related Documents	\- 11 \-

Appendix 2: Screenshot from SDAS	\- 11 \-

Appendix 3: Attachments	\- 11 \-

Appendix 4: ACRONYMS	\- 11 \-

About this Document

This document serves as a template for the correct submission of change requests by users on the [SDAS platform](https://portal.servicedesk.eng.it/#/SystemAccess?DOOR=ENG-GUESTS)\. It outlines the business needs of the customer and is not intended to describe the impact and effort of potential development\. Following its completion and signature by the change request evaluation team, this document will be forwarded to the supplier in order to request an impact analysis of the requirement\. The drafting of this document is the responsibility of the change request evaluation team, which retains the intellectual property of the requirement itself\.

__Status__

Waiting for Customer

Compilation to be completed by the CR Evaluation Team\.

Indicates the current state of the Compliance Report, such as 'Approved’\.

__Project__

RINA Handover

Standard field\.

__Component/s__

JINA

Standard field\.

__Affect Version/s__

Completion by the user and/or CR evaluation team\.

Specifies the version\(s\) impacted by the issue, if any\.

__Release Date__

Completion by the CR Evaluation Team\.

Specify the final date by which the modification must be deployed to production\.

__Slot__

Completion by the CR Evaluation Team\.

Please specify the slot in which the requirement analysis is requested\.

__Priority__

Completion by the CR Evaluation Team\.

Priority given by the CRs Evaluation Team respect the slot\.

__Reporter__

ANSELMI MILKO \(IT\)

Completion by the user\.

Names the entity or individual who reported the issue, for example, 'EESSI CAB Secretariat'\.

__Labels__

Completion by the CR Evaluation Team\.

Provides European Commission tags or keywords associated with the report, like '2021, Sector\.CROSS, StrategicCR, etc’\.

__Category__

Urgent Change

Completion by the CR Evaluation Team\.

Specify the categories as follows: compliance, SLAs and messages, development specific, Infrastructure, operations and team allocation and all\.

__Impact area__

Others

Completion by the CR Evaluation Team\.

Specify the Impact area as follow: compliance, security, system operations, message delivery, versions compatibility, cases, model, architecture, interfacess and messages specifications, databases, software EESSI component, translations, conformance testing framework  upgrades, manuals, procedures, communications and certificates, hardware, external licencess, external supporting software updates, trainings, EESSI team allocations, quantitative impact

__Issue Links__

Completion by the user and/or CR evaluation team\.

Lists related EEssi issues or tickets, such as 'EESSI\-XXXX, EESSI\-XXXX\.

# <a id="_Toc185600793"></a>Purpose

<a id="1.4_______________References"></a>__Objective__: The primary objective of this change request is to enhance the __search functionality__ of the Business Use Cases \(BUC\) in the portal by replacing the current Full Text search system with a more advanced search solution, such as a semantic or auto\-complete search system\.

__Business Impact__: The existing search system is inadequate, requiring users to know the exact spelling of search terms, which poses challenges in a multilingual environment\. This limitation has been a recurring concern among participating countries, highlighting the need for a more effective search capability\. By implementing an advanced search system, the aim is to improve user experience, increase search accuracy, and reduce the time spent on locating relevant information\.

# <a id="_Toc152585007"></a><a id="_Toc152587129"></a><a id="_Toc152259512"></a><a id="_Toc152259725"></a><a id="_Toc152585008"></a><a id="_Toc152587130"></a><a id="_Toc185600794"></a>Current scenario \(AS\-IS\)

The current search system of the Business Use Cases \(BUC\) in the portal is limited and ineffective\. Users must know the exact spelling of search terms, which is particularly challenging in a multilingual context\. The search experience varies widely among users, hindering collaboration and knowledge sharing\. Feedback from participating countries has consistently called for improvements, with a strong desire for a more intuitive solution\.

![A screenshot of a computer

AI-generated content may be incorrect.]()

# <a id="_Toc185600795"></a><a id="_Toc353553051"></a><a id="_Ref369009157"></a><a id="_Ref369009174"></a>Future Scenario \(TO\-BE\)

The future system will utilize semantic search or auto\-complete technologies, allowing users to find relevant information more efficiently and intuitively in the portal\.

In this improved environment, users will no longer need to know the exact spelling of search terms, as the system will interpret variations in language and spelling\. 

The advanced search capabilities will support multiple languages seamlessly, ensuring that all users can access the information they need, regardless of their linguistic background\. 

## <a id="_Toc185600796"></a>Use Case 

__Use Case: __Enhanced Search Functionality for BUC

__Scenario: __Users will be able to efficiently find relevant information of the BUCs in the portal across multiple languages without needing to know exact spellings, thereby improving collaboration and knowledge sharing\.

__Key steps__: 

- An advanced search system will be integrated that supports semantic search and auto\-complete functionalities, enhancing the user experience\.

# <a id="_Toc185600797"></a>Architecture IT 

*As part of the feasibility study, the supplier is requested to specify any potential impact on the CPI, as well as the solution or library that the TGC intends to use to address this requirement\.*

*No architectural modification is required\. The supplier is referred to assess any impacts and modifications necessary to ensure the operability of the solution, which will be proposed by the supplier in order to comply with the requirement that is the subject of this document\.*

## <a id="_Toc185600798"></a>AS\-IS

## <a id="_Toc185600799"></a>TO\-BE

# <a id="_Toc185600800"></a>Non\-functional requirements

No modification is required\. As a result, the log management process may be subject to change\. The supplier is referred to assess any impacts and modifications necessary to ensure the operability of the solution, which will be proposed by the supplier in order to comply with the requirement that is the subject of this document\.

<a id="_Toc366515858"></a><a id="_Toc366516748"></a><a id="_Toc353541186"></a>

# <a id="_Toc178791183"></a><a id="_Toc185600801"></a>Service Desk ticket discussion

__Contact__

__Activity__

__Date__

__Comments__

MASINI SILVIA

03/12/2025 17:14:04

From Active to Waiting for Customer: This request is forwarded to the "CRs evaluation Team" of the JPA beneficiaries\. The TGC asks to evaluate the request and to register it in the CRs backlog\. The "CRs evaluation Team" is invited to indicate to the TGC the priority, the desired development slot, and is also invited to provide a detailed description approved by the JPA beneficiaries\. It is recalled that the development requests to the TGC must be sent officially through the CRs backlog according to the Slot management project dates\.

MASINI SILVIA

03/12/2025 17:13:40

From Accepted to Active:

MASINI SILVIA

03/12/2025 17:13:36

From Invoked to Accepted:

ANSELMI MILKO

03/12/2025 16:48:06

From Intake to Invoked: null

ANSELMI MILKO

03/12/2025 16:48:06

From to Intake:

ANSELMI MILKO

03/12/2025 16:48:06

Created new Request: RN:12284233

# <a id="_Toc185600802"></a>Appendix 1: References and Related Documents

__\#__

__Reference or Related Document__

__Source or Link/Location__

1

# <a id="_Toc185600803"></a>Appendix 2: Screenshot from SDAS

__\#__

__Reference or Related Document__

__Source or Link/Location__

1



# <a id="_Toc185600804"></a>Appendix 3: Attachments

__\#__

__Related File__

__Source or Link/Location__

1

# <a id="_Toc185600805"></a>Appendix 4: ACRONYMS 

__Acronyms__

__Description__

*CDM*

*Command Data Model*

*CTS*

*Software Compatibility Test Suite*

*DEV*

*Development*

*Doc*

*Documents*

*EESSI*

*Electronic Exchange of Social Security Information*

*ENV*

*Environment*

*FP*

*Function Point*

*HL*

*High Level*

*MB*

*Management Board*

*PT*

*Penetration Test*

*SAST*

*Static Analysis*

*SD&AS*

*Service Desk & Asset System*

*SSU *

*Scheda di Start\-Up \(Italian\)*

*SW*

*Software*

*TB*

*Technical Board*

*TGC*

*Temporary Grouping of Companies*

*WAPT*

*Web Application Penetration Test*