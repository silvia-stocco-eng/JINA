---
unique-name: jina-crseessi-7112
display-name: JINA CRs EESSI   7112
category: GENERAL
description: The core objective of this change request is to urgently implement
tags: cret
---

*.*

JINA-CRs

**EESSI - 7112**

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

**Document Title:** JINA-CRs\_ Requirement_Template_EESSI - 7112

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

**\[Affect RINA 5.4.2, RINA 5.4.3, RINA Completion by the user and/or\
Version/s\]{.underline}** 5.6.2 CR evaluation team.

**\[Release Date\]{.underline}** Specify the final date by Completion by the CR\
which the modification must Evaluation Team.\
be deployed to production.

**\[Slot\]{.underline}** Please specify the slot in Completion by the CR\
which the requirement Evaluation Team.\
analysis is requested.

**\[Priority\]{.underline}** Major Completion by the CR\
Evaluation Team.

**\[Reporter\]{.underline}** United Kindom Completion by the user.

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

The core objective of this change request is to urgently implement\
pagination on the search and notification screens within our system.\
This enhancement is strategically important as it aims to address the\
current challenges faced by users when dealing with large volumes of\
records and notifications. The existing setup, which lacks pagination,\
renders the screens unusable when more than 100 records are retrieved,\
often leading to system timeouts or crashes.

By introducing pagination, we will significantly improve the user\
experience by allowing users to navigate through results in manageable\
increments, rather than being overwhelmed by excessive data. This change\
is not just a matter of convenience; it is a necessary upgrade to\
maintain the efficiency and effectiveness of our case workers. The\
ability to page through search results, limited to 100 records per page,\
will eliminate the need for users to redefine searches to manage data\
overload.

Additionally, the notifications screen is currently ineffective due to\
the inability to filter notifications by specific dates. The proposed\
pagination will enable users to view notifications for selected dates\
without the system having to process an excessive amount of data at\
once, thereby enhancing performance and reducing browser strain.

The business impact of this change is clear: by improving the system's\
usability, we will streamline case management processes, reduce the risk\
of system failures, and increase overall productivity. This upgrade is\
not only crucial for day-to-day operations but also aligns with our\
strategic goal of leveraging technology to provide a more robust and\
reliable platform for our workforce.

# Current scenario (AS-IS)

"*The notifications screen and case search screen have no pagination and\
are impossible to navigate around with the browser being unable to\
handle the volume of data presented to the screens".*

Currently, the system is facing significant challenges with the search\
and notification screens, especially when it comes to handling a large\
number of records. Without pagination functionality, users are\
confronted with overloaded screens whenever more than 100 records are\
retrieved. This data overload renders the screens virtually unusable,\
causing extended wait times and, in some cases, system freezes or\
crashes.

When case workers attempt to assign cases in bulk, the lack of a\
pagination option forces them to redefine the search to reduce the\
number of records displayed, a process that is not always possible or\
practical. This issue is compounded by the need to manage large volumes\
of cases, which requires efficient viewing and interaction with the\
data.

Regarding the notification screen, users face a similar situation. The\
screen is currently cluttered with an excessive number of notifications,\
without the ability to filter them by a specific date. The date\
selection option located in the top right corner of the screen is\
insufficient, as it merely links to another section of the screen while\
the rest of the data remains in the browser, overloading it each time a\
date is selected.

In summary, the current scenario is marked by inefficiencies and\
limitations that hinder user productivity and compromise system\
stability. The absence of pagination is clearly impacting the ability of\
users to work effectively, highlighting the urgent need for an upgrade\
to improve system usability and performance.

# Future Scenario (TO-BE)

Once pagination is successfully implemented, the future scenario for our\
system's search and notification screens will be markedly improved:

**Enhanced User Experience**: Users will encounter a more intuitive and\
user-friendly interface. The ability to navigate through search results\
and notifications in a paginated format will reduce frustration and\
increase productivity. Users will no longer face the issue of system\
timeouts or crashes due to data overload.

**Efficient Case Management**: Case workers will be able to manage and\
assign cases more effectively. With the ability to view 100 records at a\
time, they can quickly identify and process relevant cases without the\
need to constantly redefine search parameters.

**Improved System Performance**: The system will operate more smoothly\
as the load on the browser and backend systems will be significantly\
reduced. This means faster response times and a more reliable platform\
for users to carry out their tasks.

**Streamlined Notification Process**: The notifications screen will\
become more manageable, with users being able to filter and view\
notifications by specific dates. This targeted approach will allow for a\
more organized review of important alerts and updates, ensuring that no\
critical information is missed.

**Data Processing Optimization**: With pagination in place, the browser\
and server will process smaller chunks of data at any given time, which\
will lead to better memory management and reduced chances of performance\
bottlenecks.

**Scalability and Future Growth**: As the organization grows and the\
volume of data increases, the paginated system will be able to handle\
the expansion more gracefully. This scalability is essential for\
supporting future growth without compromising on system performance.

**Strategic Alignment with Technological Advancements**: The move\
towards a paginated interface reflects the organization's commitment to\
staying current with technological trends and best practices. It\
positions the company as a forward-thinking entity that values\
efficiency and continuous improvement.

## Use Case

**Use Case**: Introduce Pagination and Additional Date Filters for\
Notifications.

**Scenario**: Currently, users who access the notification center\
encounter a continuous stream of notifications without pagination, and\
the existing date filters are insufficient.

**Problem**: The absence of pagination is causing application errors and\
confusion among the operators, who have also expressed the need for more\
specific date filters.

**Solution**: Implement pagination for notifications and introduce new\
date filters to address these issues.

**Key Steps**:

1. Implement pagination in the notification center to decrease the\
   application's workload and improve performance.

2. Introduce additional date filters to allow operators to more\
   accurately sort through notifications.

# Architecture IT

No architectural change is required. The supplier is referred to assess\
any impacts and modifications necessary to ensure the operability of the\
solution, which will be proposed by the supplier in order to comply with\
the requirement that is the subject of this document\*.\*

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

1 [\[\[EESSI-7112\] Introduce pagination to search and notifications screen - CITnet Jira\
(europa.eu)\]{.underline}](https://citnet.tech.ec.europa.eu/CITnet/jira/browse/EESSI-7112)

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