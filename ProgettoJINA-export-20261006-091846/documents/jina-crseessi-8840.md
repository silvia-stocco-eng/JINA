---
unique-name: jina-crseessi-8840
display-name: JINA CRs EESSI   8840
category: GENERAL
description: The organization is seeking to augment the RINA application\'s capacity
tags: cret
---

JINA-CRs

**EESSI - 8840**

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

**Document Title:** JINA-CRs_Requirement_Template_EESSI - 8840

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

**\[Affect RINA 2020 Completion by the user and/or\
Version/s\]{.underline}** CR evaluation team.

**\[Release Date\]{.underline}** Specify the final date by Completion by the CR\
which the modification must Evaluation Team.\
be deployed to production.

**\[Slot\]{.underline}** Please specify the slot in Completion by the CR\
which the requirement Evaluation Team.\
analysis is requested.

**\[Priority\]{.underline}** MAJOR Completion by the CR\
Evaluation Team.

**\[Reporter\]{.underline}** Greece Completion by the user.

**\[Labels\]{.underline}** 2021 - Rina HO Completion by the CR\
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

## **\[Issue Links\]{.underline}** Lists related issues or Completion by the user and/or\\

tickets, such as CR evaluation team.\
'EESSI-3965, EESSI-9278'.

# Purpose

The organization is seeking to augment the RINA application's capacity\
for seamless data exchange with National Applications. This enhancement\
is of strategic importance as it aims to optimize operational workflows\
and align with external data sources, thereby bolstering decision-making\
processes and increasing overall efficiency.

**While the current mechanism for exporting data from RINA is robust and\
effective, challenges have been identified in the import process**.\
Specifically, when information is received from National Applications\
via NIE callbacks, the system is capable of processing and updating this\
information accurately. However, a gap has been noted in the user\
interface of RINA during the reintegration of updated data.

Currently, **RINA users do not receive notifications of ongoing\
communications with National Applications**, which may lead to\
confusion. Additionally, users are unable to view updated information in\
real-time within RINA. Instead, they are required to close and reopen\
the document to verify the latest updates, which interrupts the workflow\
and reduces efficiency.

The organization is investigating potential functionalities within RINA\
that could enable live updates to be displayed and user notifications to\
be activated during the data exchange process. **The implementation of\
such functionalities is anticipated to significantly enhance the user\
experience and streamline operations, ensuring that staff have immediate\
access to updated information without disruption to their activities**.

# Current scenario (AS-IS)

In the current scenario, the organization's RINA application is\
designed to interact with National Applications for the purpose of\
exchanging information. This interaction is facilitated by the use of\
NIE (National Interoperability Exchange) protocols.

The process for exporting data from RINA to National Applications is\
well-established and functions effectively. The RINA application can\
send out information as needed, and this part of the process does not\
present any significant issues.

However, when it comes to importing information into RINA from National\
Applications, the organization faces a challenge. The import process\
begins when a new document event is triggered in the National\
Application, which sends information to RINA through NIE callbacks. The\
RINA application is capable of receiving this information and processing\
it correctly. The system updates the information and prepares to send it\
back to RINA.

The problem arises after the updated information is sent back to RINA.\
At this point, the RINA user interface does not provide any indication\
to the user that a communication with another application is taking\
place. Users are left without visual cues, such as a loader icon, that\
would inform them of the ongoing data exchange. Furthermore, once the\
information is returned to RINA and updated, users are not able to see\
these updates reflected live in the system. Instead, they must close and\
reopen the specific document (SED) to see the changes that have been\
made by the National Application\*.\*

# Future Scenario (TO-BE)

In the envisioned future scenario, the RINA application will be fully\
integrated with National Applications, providing a seamless and\
automated exchange of information. This advanced interoperability will\
be characterized by the following features:

**Real-Time Notifications**: RINA users will receive immediate\
notifications during the data exchange process with National\
Applications. This will keep users informed of the ongoing\
communications and data updates, enhancing transparency and user\
awareness.

**Live Data Updates**: As soon as information is updated from National\
Applications and processed by RINA, the changes will be reflected live\
within the user interface. Users will no longer need to close and reopen\
documents to confirm updates, as the information will be dynamically\
refreshed, providing an uninterrupted and real-time view of the latest\
data.

**User Experience Enhancement**: The user interface of RINA will include\
visual cues, such as loader icons or progress indicators, to signal\
active communication with National Applications. This will provide a\
more intuitive and user-friendly experience, reducing confusion and\
increasing user satisfaction.

**Operational Efficiency**: The streamlined process will eliminate\
redundant steps and manual interventions, thereby reducing the time and\
effort required to manage data exchanges. This efficiency gain will free\
up resources and allow staff to focus on higher-value activities.

**Data Accuracy and Timeliness**: With the automated and immediate\
synchronization of data, the organization will benefit from having\
access to the most current and accurate information. This will support\
better decision-making and ensure that all actions are based on the\
latest available data.

**Strategic Alignment**: The enhanced capabilities of RINA will align\
with the organization's strategic objectives of leveraging technology\
to improve processes, increase agility, and maintain a competitive edge\
in the market.

## Use Case

**Use Case**: Enable Real-Time Notifications for SED Updates and\
National Application Communications.

**Scenario**: Currently, there is a delay between SED updates and the\
ongoing communications of national applications on RINA.

**Problem**: Users are required to close and reopen the SED to access\
the updated documentation and do not receive ongoing communications from\
national applications.

**Solution**: The proposed solution is to enable open SEDs to receive\
notifications about document updates while they are being reviewed by\
the operator, and to include ongoing communications from national\
applications in these notifications.

**Key Steps**:

1. Implement a real-time notification system to alert users about SED\
   updates.

2. Ensure that notifications also encompass ongoing communications from\
   national applications.

3. 

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

1 [\[\[EESSI-8840\] Exchanging information using NIE settings in RINA - CITnet Jira\
(europa.eu)\]{.underline}](https://citnet.tech.ec.europa.eu/CITnet/jira/browse/EESSI-8840)

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