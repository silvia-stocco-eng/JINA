---
unique-name: jina-crseessi-6261
display-name: JINA CRs EESSI   6261
category: GENERAL
description: The current request aims to address a critical issue with the
tags: cret
---

JINA-CRs

**EESSI - 6261**

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

**Document Title:** JINA-CRs_Requirement_Template_EESSI - 6261

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

**\[Component/s\]{.underline}** RINA Standard field.

**\[Affect RINA 5.4.3 Completion by the user and/or\
Version/s\]{.underline}** CR evaluation team.

**\[Release Date\]{.underline}** Specify the final date by Completion by the CR\
which the modification must Evaluation Team.\
be deployed to production.

**\[Slot\]{.underline}** Please specify the slot in Completion by the CR\
which the requirement Evaluation Team.\
analysis is requested.

**\[Priority\]{.underline}** MAJOR Completion by the CR\
Evaluation Team.

**\[Reporter\]{.underline}** Netherlands Completion by the user.

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

The current request aims to address a critical issue with the\
notification interface (NIE) that is integral to the operation of our\
National Applications (NA). The interface is responsible for delivering\
system event details (SEDs) to the NAs, which are essential for the\
applications to function correctly and efficiently.

The core objective of this change is to **introduce a mechanism that\
ensures notifications are delivered reliably**. Presently, when a\
notification fails to be delivered, it results in a system error, and\
there is no existing process to automatically retry sending the\
notification. This lack of a retry mechanism has led to inconsistencies\
and incomplete data within our National Application, which in turn,\
hampers our ability to handle business use cases (BUC) effectively.

The proposed change will have a significant positive impact on the\
business by:

**Ensuring that all notifications are recognized**, even if initially\
unsuccessful, allowing for administrative intervention to correct and\
resend them as needed.

**Implementing an automated retry mechanism that will attempt to resend\
notifications without manual intervention**, thereby increasing\
efficiency and reducing the potential for human error.

Improving the consistency and completeness of production data within our\
National Application, which is crucial for reliable BUC handling.

Strategically, this change is vital for maintaining the integrity of our\
data flow and the overall performance of our National Applications. It\
is recommended that this enhancement be treated with urgency and\
deployed as a hotfix to minimize any further impact on business\
operations.

# Current scenario (AS-IS)

*"Failure of NIE events resulting in lost messages at business level.\
Rights of citizens are at stake when messages can be lost".*

Currently, the notification interface (NIE) used by our National\
Applications (NA) to receive system event details (SEDs) has a\
significant shortcoming: there is no automatic retry mechanism for\
notifications that fail to be delivered successfully. In the event of a\
delivery failure, a system error (Java exception) occurs, and the\
notification is not retried.

This deficiency has led to inconsistent and incomplete production data\
within the National Applications, undermining the reliable management of\
business use cases (BUC). Consequently, administrators lack the ability\
to recognize, process, correct, or manually resend failed notifications,\
necessitating immediate action to address the issue.

The current situation has been highlighted by several support tickets,\
which underscore the urgency of implementing a solution. The need for\
intervention has been recognized as a priority, and it is suggested that\
the fix be implemented as soon as possible, preferably through a hotfix,\
to ensure the continuity and reliability of business operations\*.\*

# Future Scenario (TO-BE)

Following the implementation of the requested change, will benefit from\
a significantly improved notification interface (NIE). The new mechanism\
for acknowledgment and automatic retry of notifications will ensure that\
all system event details (SEDs) are delivered reliably and promptly.

In the future scenario, when a notification fails to be delivered on the\
first attempt, the system will automatically initiate a retry process.\
This process will attempt to resend the notification until successful\
delivery is achieved, thus reducing the need for manual intervention and\
minimizing the risk of human error.

Administrators will have the capability to monitor the status of\
notifications, intervene in case of persistent issues, and ensure that\
all notifications are processed correctly. As a result, there will be a\
significant reduction in inconsistencies and incomplete data within the\
National Applications, leading to more reliable and uninterrupted\
business use case (BUC) management.

The adoption of this change as a hotfix will ensure that improvements\
are implemented swiftly, avoiding further negative impacts on business\
operations and enhancing customer satisfaction. Additionally, management\
will observe an increase in operational efficiency and greater\
confidence in the stability and reliability of the company's IT\
systems.

## Use Case

**Use Case**:

**Scenario**: Currently, the system's notifications regarding SED state\
changes are prone to errors, which often require administrators to\
manually verify and rectify discrepancies.

**Problem**: Frequently, these notifications fail to be dispatched,\
leading to inconsistencies and necessitating administrative intervention\
to resolve the issues.

**Solution**: Establish an automated system to guarantee the accurate\
dispatch of notifications, and provide administrators with a dashboard\
to monitor the status of notification delivery.

**Key Steps**:

1. Implement an automated system to ensure the reliable sending of\
   notifications.

2. Provide administrators with a dashboard to monitor the notification\
   delivery status, confirming the effectiveness of the automation and\
   reducing the need for manual input.

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

1 [\[\[EESSI-6261\] CAK: Create more robust NIE implementation - CITnet Jira\
(europa.eu)\]{.underline}](https://citnet.tech.ec.europa.eu/CITnet/jira/browse/EESSI-6261)

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