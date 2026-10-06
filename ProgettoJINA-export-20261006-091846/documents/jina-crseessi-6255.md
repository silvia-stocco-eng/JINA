---
unique-name: jina-crseessi-6255
display-name: JINA CRs EESSI   6255
category: GENERAL
description: **The proposed change aims to improve the tracking and processing of
tags: cret
---

JINA-CRs

**EESSI - 6255**

(CIG 9623953142)

+-------------+---------------------------------------------+----------+\
| Date: | | Doc. |\
| 25^th^ Sep. | | Version: |\
| 2024 | | 1.0 |\
| | | |\
| | | Status: |\
| | | Draft |\
+=============+=============================================+==========+

**Document Control Information**

---

**Settings** **Value**

---

**Document Title:** JINA-CRs_Requirement_Template_EESSI_6255

**Project Id:** CIG 9623953142

**Document Authors:** EY TEAM

**Project Owner:** Barbara Ingrosso (PO)

**Project Manager:** Milko Anselmi (PM)

**Doc. Version:** 1.0

**Sensitivity:** Reserved

## **Date:** 25^th^ Sep. 2024

**Document Approver(s) and Reviewer(s):**

NOTE: All Approvers are required. Records of each approver must be\
maintained. All Reviewers in the list are considered required unless\
explicitly listed as Optional.

---

**Name** **Role** **Action** **Date**

---

```
                                  *\<Approve /      
                                  Review\>*         
```

---

**Document history:**

The Document Author is authorized to make the following types of changes\
to the document without requiring that the document be re-approved:

- Editorial, formatting, and spelling

- Clarification

To request a change to this document, contact the Document Author or\
Owner.

Changes to this document are summarized in the following table in\
reverse chronological order -(latest version first).

---

**Revision** **Date** **Created by** **Short Description of Changes**

---

---

**Configuration Management: Document Location**

The latest version of this controlled document is stored in\
*EESSIGateway:*

**INDEX**

1 Purpose [- 5 -](#purpose)

2 Current scenario (AS-IS) [- 6 -](#current-scenario-as-is)

3 Future Scenario (TO-BE) [- 7 -](#future-scenario-to-be)

3.1 Use Case [- 7 -](#use-case)

4 Architecture IT [- 8 -](#architecture-it)

4.1 AS-IS [- 8 -](#as-is)

4.2 TO-BE [- 8 -](#to-be)

5 Non-functional requirements [- 9 -](#non-functional-requirements)

Appendix 1: References and Related Documents [- 10\
-](#appendix-1-references-and-related-documents)

Appendix 2: Attachments [- 10 -](#appendix-2-attachments)

Appendix 3: ACRONYMS [- 10 -](#appendix-3-acronyms)

About this Document

This document serves as a template for the correct submission of change\
requests by users. It outlines the business needs of the customer and is\
not intended to describe the impact and effort of potential development.\
Following its completion and signature by the change request evaluation\
team, this document will be forwarded to the supplier in order to\
request an impact analysis of the requirement. The drafting of this\
document is the responsibility of the change request evaluation team,\
which retains the intellectual property of the requirement itself.

---

**\[Status\]{.underline}** Indicates the current state Compilation to be completed\
of the Compliance Report, by the CR Evaluation Team.\
such as 'Approved'.

---

**\[Project\]{.underline}** RINA Handover Standard field.

**\[Component/s\]{.underline}** JINA Standard field.

**\[Affect RINA 5.4.1 Completion by the user and/or\
Version/s\]{.underline}** CR evaluation team.

**\[Release Date\]{.underline}** Specify the final date by Completion by the CR\
which the modification must Evaluation Team.\
be deployed to production.

**\[Slot\]{.underline}** Please specify the slot in Completion by the CR\
which the requirement Evaluation Team.\
analysis is requested.

**\[Priority\]{.underline}** MAJOR Completion by the CR\
Evaluation Team.

**\[Reporter\]{.underline}** Czech Republic Completion by the user.

**\[Labels\]{.underline}** RinaHO Completion by the CR\
Evaluation Team.

**\[Category\]{.underline}** Software Completion by the CR\
Evaluation Team.

**\[Impact area\]{.underline}** Specify the Impact area as Completion by the CR\
follow: compliance, security, Evaluation Team.\
system operations, message\
delivery, versions\
compatibility, cases, model,\
architecture, interfacess and\
messages specifications,\
databases, software EESSI\
component, translations,\
conformance testing framework\
upgrades, manuals,\
procedures, communications\
and certificates, hardware,\
external licencess, external\
supporting software updates,\
trainings, EESSI team\
allocations, quantitative\
impact,

## **\[Issue Links\]{.underline}** Lists related issues or Completion by the user and/or\
tickets, such as CR evaluation team.\
'EESSI-3965, EESSI-9278'.

# Purpose

**The proposed change aims to improve the tracking and processing of\
document-related events within our National Application**. Currently,\
when we receive notifications such as "SED Delivered" and "SED Failed\
to be Delivered," we lack critical information---specifically, the\
document ID and version number. This omission hinders our ability to\
accurately associate these events with the correct documents, especially\
when multiple versions or similar documents exist within a single case.

By including the document ID and version number in the event payload, we\
will significantly enhance our tracking precision. This will enable us\
to link events to the appropriate documents effortlessly, streamlining\
our case management process and reducing the potential for errors.

Additionally, **reclassifying these notifications** from "notification\
events" to "document events" will **align them more closely with\
their nature and purpose**, further clarifying event handling and\
improving organizational efficiency.

# Current scenario (AS-IS)

*"The notification events related to documents (e.g. document delivered)\
do not contain the document ID and document version. As a result the\
notifications cannot be safely linked with the right document/version."*

In the current context, our National Application receives notification\
events such as "SED Delivered" and "SED Failed to be Delivered" from\
the NIE module. These events are crucial for tracking the status of\
documents within the cases managed by the application. However, the\
payload of these events---the information that accompanies the\
notification---is incomplete: it includes only the document type (for\
example, H001) and does not provide the document ID or version number.

This limitation poses a significant challenge: when there are multiple\
versions of a document or multiple documents of the same type within a\
case, we cannot accurately determine which specific document the event\
refers to. As a result, this can lead to confusion and potential errors\
in case management, as it is not possible to make a direct and reliable\
link between the event and the relevant document.

Furthermore, the events are currently categorized as "notification\
events," a category that may not fully reflect their direct relevance\
to the documents and their status. This classification can affect the\
clarity and efficiency with which events are managed within the system.

# Future Scenario (TO-BE)

Once the requested change is implemented, the National Application will\
have a significantly improved ability to track and manage\
document-related events. Whenever an event such as "SED Delivered" or\
"SED Failed to be Delivered" is received, the event payload will\
include the document ID and version number. This will allow case\
managers to immediately and accurately identify the specific document\
the event refers to, even when multiple documents or versions exist\
within the same case.

Case management will become more efficient and less prone to errors, as\
the confusion stemming from associating events with incorrect documents\
will be eliminated. Moreover, reclassifying events under the "document\
events" category will make their management more intuitive and improve\
consistency within the application.

Staff responsible for monitoring and auditing will benefit from a more\
transparent and traceable system, with a clear correspondence between\
events and documents. This will lead to greater ease in reviewing past\
actions and ensuring compliance with internal protocols and regulatory\
standards.

Overall, the organization will experience an improvement in the quality\
of service provided, with reduced response times and an increase in both\
internal and client satisfaction. The ability to respond quickly and\
accurately to information requests or correction needs will be enhanced,\
strengthening the company's position as an efficient and reliable\
leader in its field.

## Use Case

**Use Case**: Enhancing NIE Notifications with Document Version and ID

**Scenario**: Currently, when SED status update notifications are sent,\
they lack the inclusion of the document version and ID. This omission\
results in confusion due to the presence of multiple documents with\
identical names but different versions associated with the SED.

**Problem**: The absence of the document version and ID in the\
notifications leads to ambiguity and prevents operators from accurately\
associating a notification with the correct document version.

**Solution**: The recommended solution is to incorporate the missing\
information (document ID and document version) into the NIE notification\
content. This addition will assist operators in promptly identifying the\
document related to the status change. Furthermore, it is advised that\
SED state change notifications be reclassified under 'Document Events'\
to streamline management and enhance coherence within the application.

**Key Steps**:

1. Integrate the document ID and version into NIE notifications.

2. Relocate SED state change notifications to fall under 'Document\
   Events' for more intuitive management and to maintain consistency\
   across the application.

# Architecture IT

No architectural change is required. The supplier is referred to assess\
any impacts and modifications necessary to ensure the operability of the\
solution, which will be proposed by the supplier in order to comply with\
the requirement that is the subject of this document.

## AS-IS

## TO-BE

# Non-functional requirements

No architectural change is required. The supplier is referred to assess\
any impacts and modifications necessary to ensure the operability of the\
solution, which will be proposed by the supplier in order to comply with\
the requirement that is the subject of this document.

# Appendix 1: References and Related Documents

---

**#** **Reference or Related Source or Link/Location\
Document**

---

1 [\[\[EESSI-6255\] Add document ID and version number for notification events related to\
documents - CITnet Jira\
(europa.eu)\]{.underline}](https://citnet.tech.ec.europa.eu/CITnet/jira/browse/EESSI-6255)

---

# Appendix 2: Attachments

---

**#** **Related File** **Source or Link/Location**

---

1

## 2

# Appendix 3: ACRONYMS

---

**Acronyms** **Description**

---

*CDM* *Command Data Model*

*CTS* *Software Compatibility Test Suite*

*DEV* *Development*

*Doc* *Documents*

*EESSI* *Electronic Exchange of Social\
Security Information*

*ENV* *Environment*

*FP* *Function Point*

*HL* *High Level*

*MB* *Management Board*

*PT* *Penetration Test*

*SAST* *Static Analysis*

*SD&AS* *Service Desk & Asset System*

*SSU* *Scheda di Start-Up (Italian)*

*SW* *Software*

*TB* *Technical Board*

*TGC* *Temporary Grouping of Companies*

## *WAPT* *Web Application Penetration Test*