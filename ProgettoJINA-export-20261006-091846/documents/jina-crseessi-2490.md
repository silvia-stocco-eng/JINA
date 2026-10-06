---
unique-name: jina-crseessi-2490
display-name: JINA CRs EESSI   2490
category: GENERAL
description: The NAV aims to significantly strengthen the security measures of its
tags: cret
---

JINA-CRs

**EESSI - 2490**

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

**Document Title:** JINA-CRs_Requirement_Template_EESSI - 2490

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

**\[Affect RINA 5.0.3 Completion by the user and/or\
Version/s\]{.underline}** CR evaluation team.

**\[Release Date\]{.underline}** Specify the final date by Completion by the CR\
which the modification must Evaluation Team.\
be deployed to production.

**\[Slot\]{.underline}** Please specify the slot in Completion by the CR\
which the requirement Evaluation Team.\
analysis is requested.

**\[Priority\]{.underline}** MAJOR Completion by the CR\
Evaluation Team.

**\[Reporter\]{.underline}** Norway Completion by the user.

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

The NAV aims to significantly strengthen the security measures of its\
application programming interfaces (APIs). **This enhancement is\
targeted at ensuring that only authorized clerks have the capability to\
access critical case and document event information that is exchanged\
with RINA**, an external system utilized by NAV.

The strategic enhancement of API security is paramount for NAV as it\
directly correlates with the protection of their data infrastructure.\
**By implementing rigorous authentication and authorization protocols**,\
NAV not only adheres to industry-standard data security practices but\
also solidifies the confidence that stakeholders have in the\
organization's ability to safeguard sensitive information.

**The anticipated security improvements are expected to yield a\
fortified system architecture** where the likelihood of unauthorized\
access is markedly diminished. This proactive measure is intended to\
avert potential data breaches and guarantee the secure and seamless\
exchange of information. Furthermore, NAV's initiative to secure its\
APIs could serve as a benchmark for security within the industry,\
promoting a wider adoption of stringent cybersecurity measures.

NAV is currently evaluating various strategies to secure its APIs within\
the constraints of its existing technological ecosystem, including the\
Bonita platform. The organization seeks to develop a solution that not\
only fulfills its immediate security requirements but also establishes a\
model for future technological integrations. NAV welcomes further\
dialogue to refine its strategy and ensure the adoption of the most\
effective security measures

# Current scenario (AS-IS)

NAV has developed its own application that exposes specific APIs to\
handle events related to cases and documents (RestCase and RestDocument\
events). These APIs are crucial for the operation of NAV's services and\
are currently accessible through RINA.

NAV has identified a critical need to enhance the security of these\
APIs. The goal is to ensure that only authorized individuals,\
specifically designated clerks, can invoke these APIs and access the\
sensitive information they handle. This requirement stems from the\
necessity to maintain strict control over who can perform actions within\
the system, thereby protecting the data from unauthorized access and\
potential security breaches.

To achieve this, NAV is looking to implement a system where the identity\
of the clerk who performed an action in RINA is carried over and\
verified when an event is sent to the API. This means that the API must\
be able to authenticate and authorize requests based on the clerk's\
identity to ensure that only those with the proper permissions can\
access the information.

NAV recognizes that securing APIs in this manner is likely a common\
security requirement that could benefit other organizations as well.\
Therefore, they are open to discussing potential solutions that could be\
applied within the constraints of their current technological setup,\
including the Bonita platform. NAV has some initial ideas on how to\
proceed and is seeking input and collaboration to explore what is\
possible and to discuss these ideas further\*.\*

# Future Scenario (TO-BE)

The NAV will have successfully implemented advanced security protocols\
for its application programming interfaces (APIs). This will ensure that\
only authorized clerks are able to access and interact with sensitive\
case and document event information. The APIs, which facilitate\
communication with the external system RINA, will feature robust\
authentication and authorization mechanisms that are seamlessly\
integrated into NAV's existing applications.

As a result of these enhancements, NAV's data infrastructure will be\
significantly more secure. The risk of unauthorized access to sensitive\
information will be greatly reduced, leading to a more trusted and\
reliable system. The organization's commitment to data security will be\
evident, reinforcing stakeholder confidence and setting a high standard\
for data protection within the industry.

The strategic foresight and proactive measures taken by NAV will have\
not only protected its own data assets but also paved the way for a more\
secure digital environment across the board. The organization will\
continue to monitor and update its security measures to stay ahead of\
evolving threats, ensuring the long-term integrity and confidentiality\
of its data exchanges.

## Use Case

**Use Case**: Implement a secure layer to ensure that only authorized\
clerks can call the APIs.

**Scenario**: Currently, NAV has identified that the APIs lack an\
authorization layer.

**Problem**: The absence of an authorization layer could allow\
unauthorized users to call the APIs.

**Solution**: The proposed solution is for NAV to implement an\
authorization layer to ensure that only authorized clerks have access to\
and can interact with sensitive case and document event information.

**Key Steps**:

1. NAV will implement an authentication layer.

2. API consumers will adjust their procedures to include the new\
   authentication token.

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

1 [\[\[EESSI-2490\] Support for identity propagation (security context) from the NIE\
interface - CITnet Jira\
(europa.eu)\]{.underline}](https://citnet.tech.ec.europa.eu/CITnet/jira/browse/EESSI-2490)

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