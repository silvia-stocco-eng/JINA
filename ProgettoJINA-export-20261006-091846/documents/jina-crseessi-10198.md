---
unique-name: jina-crseessi-10198
display-name: JINA CRs EESSI   10198
category: GENERAL
description: The current process for synchronizing user data with the RINA Portal
tags: cret
---

*I*

JINA-CRs

**EESSI - 10198**

(CIG 9623953142)

+-------------+---------------------------------------------+----------+\
| Date: | | Doc. |\
| 20^th^ Sep. | | Version: |\
| 2024 | | 1.0 |\
| | | |\
| | | Status: |\
| | | Draft |\
+=============+=============================================+==========+

**Document Control Information**

---

**Settings** **Value**

---

**Document Title:** JINA-CRs_Requirement_Template_EESSI_10198

**Project Id:** CIG 9623953142

**Document Authors:** EY TEAM

**Project Owner:** Barbara Ingrosso (PO)

**Project Manager:** Milko Anselmi (PM)

**Doc. Version:** 1.0

**Sensitivity:** Reserved

## **Date:** 20^th^ Sep. 2024

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

**\[Affect RINA Portal 6.2.19, RINA Completion by the user and/or\
Version/s\]{.underline}** 6.2.18 CR evaluation team.

**\[Release Date\]{.underline}** Specify the final date by Completion by the CR\
which the modification must Evaluation Team.\
be deployed to production.

**\[Slot\]{.underline}** Please specify the slot in Completion by the CR\
which the requirement Evaluation Team.\
analysis is requested.

**\[Priority\]{.underline}** Major Completion by the CR\
Evaluation Team.

**\[Reporter\]{.underline}** Portugal Completion by the user.

**\[Labels\]{.underline}** Provides European Commission Completion by the CR\
tags or keywords associated Evaluation Team.\
with the report, like '2021,\
Sector.CROSS, StrategicCR,\
etc'.

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

The current process for synchronizing user data with the RINA Portal\
through LDAP (Lightweight Directory Access Protocol) Sync in IAM\
(Identity Access Management) is causing significant inefficiencies. Each\
time a sync is performed, configurations for existing users, including\
their assigned groups and roles, are being reset. This requires\
repetitive manual reconfiguration, leading to a loss of productivity and\
an increased risk of errors.

**The proposed change aims to enhance the synchronization mechanism so\
that it preserves the configurations of existing users within the RINA\
Portal**. With this improvement, the sync will only necessitate the\
configuration of groups and roles for newly added users from the\
AD-Group (Active Directory Group), streamlining the process.

# Current scenario (AS-IS)

*\["\]{.underline}Our users in RINA Portal are created via LDAP Sync.*

*Whenever there's a new user we need to perform a LDAP Sync and every\
time we do this all the groups and roles defined for the existing users\
are lost and we have to manually recreate their groups and roles.*

*We have tenants with more than 100 users and reconfiguring the groups\
and roles for each of the user it's a very hard task and an easy target\
to erroneous situations.*

*We opened EESSI-9917 to get help for building a script that could\
backup the existing user permissions before performing the LDAP Sync and\
after put back the user permissions for the existing users.\
Unfortanetelly we didn't obtained any help on this matter. "*

Every time a synchronization with the LDAP is performed in the RINA\
Portal's IAM system, all user-specific settings, such as group\
memberships and role assignments, are reset to default for users who are\
already in the system. This requires administrators to manually\
reconfigure these settings for each existing user after every sync,\
which is time-consuming and prone to errors.

# Future Scenario (TO-BE)

"The desired situation is that everytime is performed a LDAP Sync, the\
users that were defined before the sync do not loose the configuration\
associated to the groups they belong and roles that they have."

The RINA Portal's user synchronization process will operate seamlessly.\
LDAP Sync in IAM will no longer reset configurations for existing users.\
Instead, it will intelligently distinguish and apply group and role\
settings only to new users. This will result in a more efficient system,\
where IT staff can focus on strategic tasks rather than repetitive\
manual updates. The organization will benefit from increased\
productivity, enhanced security, and a smoother onboarding experience\
for new users. Overall, this change will contribute to a more agile and\
resilient IT infrastructure.

## Use Case

**Use Case**: Automated Role Synchronization with Active Directory.

**Scenario**: At present, users must manually select one or more roles\
from the LDAP synchronization screen after their initial login.

**Problem**: The LDAP interface is unclear and gives the impression that\
only a single role can be selected.

**Solution**: The proposed solution involves automatically synchronizing\
user roles during the first login to prevent misconfigurations and\
conserve users' time.

**Key Steps**:

1. During the first login, the system will automatically establish a\
   connection to LDAP and retrieve the user's roles.

2. If the user possesses multiple roles, the system will automatically\
   assign them to the user's profile.

# Architecture IT

No architectural change is required. The supplier is referred to assess\
any impacts and modifications necessary to ensure the operability of the\
solution, which will be proposed by the supplier in order to comply with\
the requirement that is the subject of this document.

## AS-IS

## TO-BE

\*\*

# Non-functional requirements

No architectural change is required. The supplier is referred to assess\
any impacts and modifications necessary to ensure the operability of the\
solution, which will be proposed by the supplier in order to comply with\
the requirement that is the subject of this document

# Appendix 1: References and Related Documents

---

**#** **Reference or Related Source or Link/Location\
Document**

---

1 [\[\[EESSI-10198\] RINA - Improve LDAP Sync procedure - CITnet Jira\
(europa.eu)\]{.underline}](https://citnet.tech.ec.europa.eu/CITnet/jira/browse/EESSI-10198)

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