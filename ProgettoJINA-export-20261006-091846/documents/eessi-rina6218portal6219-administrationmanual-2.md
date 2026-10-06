---
unique-name: eessi-rina6218portal6219-administrationmanual-2
display-name: EESSI RINA6.2.18(Portal6.2.19) AdministrationManual
category: GENERAL
description: > This document serves as a manual for [administrators]{.underline} for
tags: ec
---

![](media/image3.png)![](media/image7.png)

> EESSI -- RINA 6.2.18

*(RINA Portal 6.2.19)*

Administration Manual

> *End User Manuals & Guides*
>
> Table of Contents

1.  [Introduction 10](#introduction)

    1.  [Purpose and Audience 10](#purpose-and-audience)

    2.  [About EESSI 10](#about-eessi)

    3.  [EESSI Architecture 10](#eessi-architecture)

    4.  [Structured Electronic Documents (SEDs)
        11](#structured-electronic-documents-seds)

    5.  [Business Use Cases (BUCs) 11](#business-use-cases-bucs)

    6.  [About RINA Application 11](#about-rina-application)

2.  [General Description 13](#general-description)

    1.  [Site Map 13](#site-map)

    2.  [General Layout, Portal Navigation and Organisation
        13](#general-layout-portal-navigation-and-organisation)

    3.  [Administrator Login 15](#administrator-login)

3.  [Admin User Profile 16](#admin-user-profile)

    1.  [Localisation Settings 16](#localisation-settings)

    2.  [Change Password 17](#change-password)

    3.  [Help 17](#help)

    4.  [User Idle Time and RINA Version
        18](#user-idle-time-and-rina-version)

4.  [RINA Application Configuration Settings
    19](#rina-application-configuration-settings)

    1.  [Single Vs Multi-Tenant RINA installation configuration
        19](#single-vs-multi-tenant-rina-installation-configuration)

    2.  [Application Settings 20](#application-settings)

    3.  [Messaging Settings 34](#messaging-settings)

    4.  [NIE Settings 41](#nie-settings)

    5.  [RINA Archiving 46](#rina-archiving)

    6.  [IAM (Identity and Access Management)
        51](#iam-identity-and-access-management)

    7.  [Authorisation 63](#authorisation)

    8.  [Notification Centre 74](#notification-centre)

    9.  [Logs 84](#logs)

    10. [Automatic Updates 88](#automatic-updates)

    11. [Test Centre 92](#test-centre)

    12. [Business Exceptions 93](#business-exceptions)

[ANNEX I - RINA LDAP Synchronisation and Authentication
96](#annex-i---rina-ldap-synchronisation-and-authentication)

[A-I.1 Synchronisation and Authentication against OpenLDAP
96](#a-i.1-synchronisation-and-authentication-against-openldap)

[A-I.2 Synchronisation and Authentication against Active Directory
97](#a-i.2-synchronisation-and-authentication-against-active-directory)

[A-I.3 Saving LDAP Configuration and Triggering LDAP process
99](#_bookmark162)

[ANNEX II -- RINA Assignment Policies -- Clarifications and Examples
100](#annex-ii-rina-assignment-policies-clarifications-and-examples)

[A-II.1 Creator Policy 100](#a-ii.1-creator-policy)

[A-II.2 Case Policy 104](#a-ii.2-case-policy)

[List of figures 109](#list-of-figures)

**Document Control Information**

+----------------------+-------------------------------------------------------+
| > **Document         | > **Value**                                           |
| > Control**          |                                                       |
+======================+=======================================================+
| > Project Title      | > Electronic Exchange of Social Security Information  |
|                      | > (EESSI)                                             |
+----------------------+-------------------------------------------------------+
| > Document Name      | > EESSI - RINA 6.2.18 (Portal 6.2.19) -               |
|                      | > Administration Manual                               |
+----------------------+-------------------------------------------------------+
| Document Category    | > End User Manuals & GuidesEnd User Manuals & Guides  |
+----------------------+-------------------------------------------------------+
| > Revision           | > \-                                                  |
+----------------------+-------------------------------------------------------+
| Component Version    | > RINA 6.2.18                                         |
+----------------------+-------------------------------------------------------+
| RINA Portal Version  | > RINA Portal 6.2.19                                  |
+----------------------+-------------------------------------------------------+
| > Publication Date   | > 22/12/2021                                          |
| > Project Milestone  | >                                                     |
|                      | > EESSI-2020 (RINA Fix8)                              |
+----------------------+-------------------------------------------------------+
| > Document Status    | > Final                                               |
+----------------------+-------------------------------------------------------+
| > Sensitivity (TLP)  | > Traffic Light Protocol (TLP) = "GREEN"              |
| > Distribution terms | >                                                     |
|                      | > ![](media/image10.png){width="2.2456791338582676in" |
|                      | > height="1.0521872265966754in"}                      |
|                      | >                                                     |
|                      | > The distribution of this document is done strictly  |
|                      | > in line with the Traffic Light Protocol (TLP)       |
|                      | > established by the European Commission\'s note AC   |
|                      | > 790/15 REV for the EESSI project documentation.     |
|                      | >                                                     |
|                      | > In line with the note AC 790/15 REV, this document  |
|                      | > is labelled as TLP = "Green". Therefore, it can be  |
|                      | > circulated widely within the EESSI community.       |
|                      | > However, the document or the information herein may |
|                      | > not be published or posted on the Internet, nor     |
|                      | > released outside of the EESSI community.            |
+----------------------+-------------------------------------------------------+
| > Connected/Embedded | > None                                                |
| > Files              |                                                       |
+----------------------+-------------------------------------------------------+
| > Authors            | > European Commission, DG EMPL A4, EESSI RINA         |
+----------------------+-------------------------------------------------------+
| > Revised by         | > European Commission, DG EMPL A4, EESSI QA           |
+----------------------+-------------------------------------------------------+
| > Approved by        | > European Commission, DG EMPL A4, EESSI PM           |
+----------------------+-------------------------------------------------------+

> **Document history**

+---------------+--------------+----------------------------------------------+
| > **Project   | **Date**     | > **Changes/Corrections**                    |
| > Milestone / |              | >                                            |
| > Component   |              | > **Description**                            |
| > version**   |              |                                              |
+===============+:============:+==============================================+
| > EESSI-2019  | > 30/11/2019 | > Check the description on next page         |
| >             |              |                                              |
| > RINA 5.6.2  |              |                                              |
+---------------+--------------+----------------------------------------------+
| > EESSI-2019  |              | > The description of the section             |
| > HF2 RINA    |              | > "[4.7](#authorisation)-                    |
| > 5.6.4       |              | >                                            |
|               |              | > [Authorisation](#iam-ldap-authentication)" |
|               |              | > has been rewritten and the term "*Case     |
|               |              | > Policy*" has been introduced.              |
|               |              | > Clarifications have been added to ANNEX    |
|               |              | > II.                                        |
+---------------+--------------+----------------------------------------------+
| > EESSI-2020  | > 18/12/2020 | > Adapt to the new RINA Portal design        |
| >             |              |                                              |
| > RINA 6.2.1  |              |                                              |
+---------------+--------------+----------------------------------------------+
| > EESSI-2020  | > 15/03/2021 | > Clarifications inserted on section 4.12    |
| > HF1 RINA    |              | > about automatic generation of X050 SEDs    |
| > 6.2.3       |              |                                              |
| >             |              |                                              |
| > RINA Portal |              |                                              |
| > 6.2.5       |              |                                              |
|               |              +----------------------------------------------+
|               |              | > Compression option has been removed from   |
|               |              | > RINA Administration interface              |
|               |              +----------------------------------------------+
|               |              | > Section 4.3.1: Replace figure 34 "Global   |
|               |              | > Messaging Settings: Authentication (TLS)"  |
|               |              +----------------------------------------------+
|               |              | > The section "4.4.1 -- Creating             |
|               |              | > subscriptions" was split in 3 subsections: |
|               |              | > (i) "4.4.1.1 - Add case event", (ii)       |
|               |              | > "4.4.1.2 - Add document event" and         |
|               |              | >                                            |
|               |              | > \(iii\) "4.4.1.3 - Add notification event" |
|               |              +----------------------------------------------+
|               |              | > Section 4.8.2: Adding the additional error |
|               |              | > messages related with duplication of       |
|               |              | > messages:                                  |
|               |              |                                              |
|               |              | - A duplicate SED (update) has arrived       |
|               |              |                                              |
|               |              | - A duplicate message arrived                |
|               |              |                                              |
|               |              | - A wrong SED (update) has arrived           |
|               |              +----------------------------------------------+
|               |              | > Deprecated functionality has been removed  |
|               |              | > (i.e., Letter Templates (PD), Mail Server  |
|               |              | > settings, Policy Decision Point (PDP),     |
|               |              | > Refresh Case Assignments)                  |
|               |              +----------------------------------------------+
|               |              | > RINA case search is not case sensitive     |
|               |              | > (EESSI- 5547)                              |
|               |              +----------------------------------------------+
|               |              | > Predefined Search improvements             |
|               |              | > (EESSI-6163)                               |
+---------------+--------------+----------------------------------------------+
| > EESSI-2020  | > 21/05/2021 | > Changes of the Figures: 8, 11, 16, 18, 87, |
| > HF4 RINA    |              | > 88, 89,                                    |
| > 6.2.6       |              | >                                            |
| >             |              | > 91, 92                                     |
| > RINA Portal |              |                                              |
| > 6.2.6       |              |                                              |
|               |              +----------------------------------------------+
|               |              | > Chapter "3.1 - Localisation Settings":     |
|               |              | >                                            |
|               |              | > Explain the list of the changed time zones |
|               |              +----------------------------------------------+
|               |              | > Chapter "4.2.2 - Application Settings      |
|               |              | > General Settings":                         |
+---------------+--------------+----------------------------------------------+

+---------------+--------------+-------------------------------------+
|               |              | > Removed the references to SED     |
|               |              | > Validation in Client; this        |
|               |              | > functionality is not present      |
|               |              | > anymore in RINA 2020              |
|               |              +-------------------------------------+
|               |              | > Chapter "4.2.2.4 -- Attachments   |
|               |              | > settings":                        |
|               |              | >                                   |
|               |              | > Inserted of clarification on MIME |
|               |              | > Types                             |
|               |              +-------------------------------------+
|               |              | > Chapter "4.8.2 - Notification     |
|               |              | > Centre: Notifications":           |
|               |              | >                                   |
|               |              | > Details added about the newly     |
|               |              | > implemented filter that limit the |
|               |              | > displayed notifications time      |
|               |              | > window to max 3 days              |
+===============+==============+=====================================+
| > EESSI-2020  | > 04/06/2021 | > Deprecated functionality has been |
| > HF4 RINA    |              | > removed: Case retention           |
| > 6.2.6       |              | > (configuration/administration)    |
| >             |              |                                     |
| > RINA Portal |              |                                     |
| > 6.2.6       |              |                                     |
| >             |              |                                     |
| > rev01       |              |                                     |
+---------------+--------------+-------------------------------------+
| > EESSI-2020  | > 10/09/2021 | > Changes to screenshots to correct |
| > HF6 RINA    |              | > some outdated ones                |
| > 6.2.12      |              | >                                   |
| >             |              | > Change the title of the chapter   |
| > RINA Portal |              | > 4.2.2.2 and eliminate the         |
| > 6.2.12      |              | > references to the former Option   |
|               |              | > to Validate or not SED in the     |
|               |              | > Portal. Replaced figures 18 and   |
|               |              | > 19 to accommodate this change     |
|               |              | >                                   |
|               |              | > Clarification and recommendation  |
|               |              | > related with Max Idle Time inside |
|               |              | > chapter 4.2.2.1                   |
|               |              | >                                   |
|               |              | > Chapter 4.3 --Order change of     |
|               |              | > settings enumeration in the       |
|               |              | > beginning of the chapter          |
|               |              | >                                   |
|               |              | > Example 4 was moved from 4.3      |
|               |              | > chapter inside Chapter 4.2.5.3    |
|               |              | > where normally belongs            |
|               |              | >                                   |
|               |              | > Chapter *"4.6.1.2 - Modifying     |
|               |              | > users"*: changed the details      |
|               |              | > related with the algorithm for    |
|               |              | > searching users                   |
|               |              | >                                   |
|               |              | > Chapter "*4.9.1 - Logs: Audit     |
|               |              | > Logs"*: changed the details       |
|               |              | > related with the algorithm for    |
|               |              | > searching audit logs records      |
|               |              | >                                   |
|               |              | > Chapter *"4.9.2 - Logs: Technical |
|               |              | > Logs"*: changed the details       |
|               |              | > related with the algorithm for    |
|               |              | > searching technical logs records  |
|               |              | >                                   |
|               |              | > Chapter *"4.5.3 - RINA Archiving: |
|               |              | > Message Retention Policies":*     |
|               |              | > clarification regarding the       |
|               |              | > minimum and maximum accepted      |
|               |              | > values for message retention      |
|               |              | > period                            |
|               |              | >                                   |
|               |              | > Chapter *"4.5.4 - RINA Archiving: |
|               |              | > Archiving Repositories":*         |
|               |              | > Clarification regarding cases     |
|               |              | > that are not anymore archived to  |
|               |              | > the disk but inside RINA database |
|               |              | >                                   |
|               |              | > Chapter "*4.12.1 - Business       |
|               |              | > Exceptions: Pending Messages"*:   |
|               |              | > Clarification on case when        |
|               |              | > receiving                         |
+---------------+--------------+-------------------------------------+

+---------------+--------------+-------------------------------------+
|               |              | > messages from sender institutions |
|               |              | > that are not refreshed inside the |
|               |              | > RINA local Institution Repository |
|               |              | >                                   |
|               |              | > Chapter *"4.2.5 - Application     |
|               |              | > Settings: Case Counter            |
|               |              | > Settings":* clarification related |
|               |              | > with Local and Business Case ID   |
|               |              | > when unarchiving of a case        |
|               |              | >                                   |
|               |              | > Chapter *"4.7.2.2 - Automatic     |
|               |              | > Process Assignment"*:             |
|               |              | > clarification related with export |
|               |              | > of policies and assignments       |
+===============+==============+=====================================+
|               |              | > Replacement of several            |
|               |              | > screenshots affected by           |
|               |              | > improvements and bug fixes        |
+---------------+--------------+-------------------------------------+
| > EESSI-2020  |              | > Chapter "*3.1 - Localisation      |
| > HF7         |              | > Settings*": Add clarification     |
|               |              | > related with time zone offset     |
+---------------+--------------+-------------------------------------+
| > RINA 6.2.12 | > 15/10/2021 | > Chapter "*4.2.5.3 -- Pattern      |
| >             |              | > Type*": Examples were corrected   |
| > RINA Portal |              | > to correctly reflect the          |
| > 6.2.13      |              | > functionality related with how    |
|               |              | > Business ID is generated based    |
|               |              | >                                   |
|               |              | > on the pattern type               |
+---------------+--------------+-------------------------------------+
|               |              | > Chapter "*4.6.1.2 -- Modifying    |
|               |              | > users*": Added a note related     |
|               |              | > with the list of words when the   |
|               |              | > search mechanism in RINA do not   |
|               |              | > return results                    |
+---------------+--------------+-------------------------------------+
|               |              | > Changes to various screenshots    |
|               |              | > that were outdated                |
+---------------+--------------+-------------------------------------+
|               |              | > Chapter *4.8.2.1 -- "Notification |
|               |              | > Layout"*: Changes                 |
|               |              | >                                   |
|               |              | > of the notification status (read, |
|               |              | > unread) with "Is Read"            |
|               |              | > respectively "Is Unread"          |
+---------------+--------------+-------------------------------------+
|               |              | > Chapter *4.2.2.1 -- "Application  |
|               |              | > Id, Languages, Max Idle time,     |
|               |              | > Organisation System Password"*:   |
|               |              | > new note added to clarify the     |
|               |              | > behavior when removing languages  |
|               |              | > used in Default User profile and  |
|               |              | >                                   |
|               |              | > Localisation Settings             |
+---------------+--------------+-------------------------------------+
| > EESSI-2020  | > 22/12/2021 | > Chapter *4.2.5 -- "Application    |
| > (RINA Fix8) |              | > Settings: Case Counter            |
| >             |              | > Settings"*: Examples 1, 2 and 3   |
| > RINA 6.2.18 |              | > were adapted to the way the       |
| >             |              | > application works.                |
| > RINA Portal |              | >                                   |
| > 6.2.19      |              | > Chapter *4.3.2 -- "Messaging      |
|               |              | > Settings: Local Messaging         |
|               |              | > Settings"*: Note to clarify that  |
|               |              | > passwords for certificates are    |
|               |              | > not mandatory                     |
|               |              | >                                   |
|               |              | > anymore                           |
+---------------+--------------+-------------------------------------+
|               |              | > Chapter *4.8.2.5 --               |
|               |              | > "Clarification on Notifications   |
|               |              | > Generation"*: Changed the name of |
|               |              | > the referred                      |
|               |              | >                                   |
|               |              | > role "Unauthorised clerk" into    |
|               |              | > "Unauthorised"                    |
+---------------+--------------+-------------------------------------+
|               |              | > Chapter *4.6.1.2 -- "Modifying    |
|               |              | > Users*": Clarifications related   |
|               |              | > with some words that are not      |
|               |              | > detected while searching users.   |
|               |              | > Also, clarify when the search     |
|               |              | >                                   |
|               |              | > applies                           |
+---------------+--------------+-------------------------------------+
|               |              | > Chapter *4.6.2.2 -- "Modifying    |
|               |              | > Groups*": Clarify                 |
|               |              | >                                   |
|               |              | > when the search applies;          |
|               |              | > Clarifications related with       |
+---------------+--------------+-------------------------------------+

+---------------+----------+-------------------------------------+
|               |          | > the differences between users'    |
|               |          | > and groups' search                |
|               |          | >                                   |
|               |          | > mechanism.                        |
|               |          | >                                   |
|               |          | > Chapter *4.9.1 -- "Logs: Audit    |
|               |          | > Logs*": clarifications regarding  |
|               |          | > how searches are performed for    |
|               |          | > audit logs                        |
|               |          | >                                   |
|               |          | > Chapter *4.9.2 - "Logs: Technical |
|               |          | > Logs*": clarifications regarding  |
|               |          | > how searches are performed for    |
|               |          | > technical logs                    |
|               |          +-------------------------------------+
|               |          | > Replacement of several            |
|               |          | > screenshots affected by           |
|               |          | > improvements and bug fixes        |
|               |          | >                                   |
|               |          | > Chapter "*3.1 - Localisation      |
|               |          | > Settings*": Add clarification     |
|               |          | > related with time zone offset     |
|               |          | > (merged from HF7)                 |
|               |          +-------------------------------------+
|               |          | > Chapter 4.2.5: Definition of the  |
|               |          | > different Case ID categories and  |
|               |          | > clarifications about their        |
|               |          | > correlations.                     |
|               |          | >                                   |
|               |          | > Chapter 3.4 -- Chapter User Idle  |
|               |          | > Time and RINA version --          |
|               |          | > screenshot adapted to reflect the |
|               |          | > latest version 6.2.18             |
|               |          | >                                   |
|               |          | > Chapter 4.2.2 -- Application      |
|               |          | > settings: General Settings --     |
|               |          | > title change and description of   |
|               |          | > the new setting related with the  |
|               |          | > maximum number of results         |
|               |          | > following case search             |
|               |          | >                                   |
|               |          | > Chapter 4.8.2 -- Notification     |
|               |          | > Centre: Notifications -- explain  |
|               |          | > the role of informative icon next |
|               |          | > to Total Records                  |
|               |          | >                                   |
|               |          | > Chapter 4.9.1 -- Logs: Audit Logs |
|               |          | > -- explain the role of            |
|               |          | > informative icon next to Total    |
|               |          | > Records                           |
|               |          | >                                   |
|               |          | > Chapter 4.9.2 -- Logs: Technical  |
|               |          | > Logs -- explain the role of       |
|               |          | > informative icon next to Total    |
|               |          | > Records                           |
|               |          +-------------------------------------+
|               |          | > Changes related to various        |
|               |          | > outdated screenshots              |
|               |          | >                                   |
|               |          | > Chapter 4.6.2.3 Deleting groups - |
|               |          | > Clarification related with when   |
|               |          | > the user is allowed to delete     |
|               |          | > groups.                           |
|               |          | >                                   |
|               |          | > Chapter 4.7 Authorisation --      |
|               |          | > Remove the reminiscence related   |
|               |          | > with PDP Implementation Class     |
|               |          | >                                   |
|               |          | > Chapter 1.5 Business Use Cases -- |
|               |          | > Replace messages with SEDs        |
|               |          | >                                   |
|               |          | > Chapter 1.6 About RINA            |
|               |          | > application -- Removed the        |
|               |          | > reference to reports that are not |
|               |          | > anymore part of RINA. Also, it    |
|               |          | > was added a clarification related |
|               |          | > with protocol translation         |
|               |          | >                                   |
|               |          | > Chapter 4.1 - Single Vs           |
|               |          | > Multi-Tenant RINA installation    |
|               |          | > configuration - clarification     |
+===============+==========+=====================================+

+---------------+----------+-------------------------------------+
|               |          | > Chapter 4.2.1.1 -- Steps to add a |
|               |          | > new tenant -- Clarification       |
|               |          | > related with organization system  |
|               |          | > password that is deprecated       |
|               |          | >                                   |
|               |          | > Chapter 4.2.3 - Application       |
|               |          | > Settings: Default Case Settings   |
|               |          | > -- Rename of some figures' name   |
|               |          | >                                   |
|               |          | > Chapter 4.2.5 - Application       |
|               |          | > Settings: Default Case Settings   |
|               |          | > -- Clarifications related with    |
|               |          | > various case IDs: Local,          |
|               |          | > International and Business;       |
|               |          | > Clarifications related with Case  |
|               |          | > IDs after cases are unarchived    |
|               |          | >                                   |
|               |          | > Chapter 4.3.1 -- Messaging        |
|               |          | > Settings: Certificates --         |
|               |          | > Clarification related with the    |
|               |          | > process of changing the           |
|               |          | > certificates store and removal of |
|               |          | > the confusing warning note        |
|               |          | >                                   |
|               |          | > Chapter 4.3.2 - Messaging         |
|               |          | > Settings: Local Messaging         |
|               |          | > Settings -- Clarification inside  |
|               |          | > the warning note related with     |
|               |          | > ebMS certificates passwords       |
|               |          | > setting                           |
|               |          | >                                   |
|               |          | > Chapter 4.3.3 - Messaging         |
|               |          | > Settings: Global Messaging        |
|               |          | > Settings -- Clarification about   |
|               |          | > BPM validation mode               |
|               |          | >                                   |
|               |          | > Chapter 4.5 -- RINA archiving --  |
|               |          | > Clarification about where the     |
|               |          | > information about RINA archiving  |
|               |          | > can be found and why the          |
|               |          | > archiving name was still kept in  |
|               |          | > RINA 2020                         |
|               |          | >                                   |
|               |          | > Chapter 4.5.1 -- Definitions of   |
|               |          | > archiving and retentions periods  |
|               |          | > -- Clarification related with     |
|               |          | > Archiving period definition and   |
|               |          | > warning note related with case    |
|               |          | > statuses for which applies RINA   |
|               |          | > archiving period                  |
|               |          | >                                   |
|               |          | > Chapter 4.6.1 IAM: Users --       |
|               |          | > Clarification related with the    |
|               |          | > list of users for each tenant     |
|               |          | >                                   |
|               |          | > Chapter 4.6.2 IAM: Groups --      |
|               |          | > Clarification related with        |
|               |          | > deleting gropus having associated |
|               |          | > users                             |
|               |          | >                                   |
|               |          | > Chapter 4.7 -- Authorisation --   |
|               |          | > Clarification regarding how       |
|               |          | > administrator selects a tenant    |
|               |          | > and related the 2 available menu  |
|               |          | > items.                            |
|               |          | >                                   |
|               |          | > Chapter 4.7.1.2 -- Managing       |
|               |          | > policies -- Changes related with  |
|               |          | > the fact that policy group is not |
|               |          | > considered a policy type          |
|               |          | >                                   |
|               |          | > Chapter 4.7.1.2.1 - Creating      |
|               |          | > policies and policy groups --     |
|               |          | > Clarification regarding policies  |
|               |          | > differences depending on the      |
|               |          | > application role: Case Owner or   |
|               |          | > Counterparty                      |
|               |          | >                                   |
|               |          | > Chapter 4.7.2.2 -- Change of the  |
|               |          | > title from Automatic to Bulk      |
|               |          | > Process Assignment                |
+===============+==========+=====================================+

+---------------+----------+-------------------------------------+
|               |          | > Change 4.8.2.2 -- View            |
|               |          | > Notifications -- Clarification    |
|               |          | > related with the fact that the    |
|               |          | > case id shown when click on icon  |
|               |          | > \> is the local case id           |
|               |          | >                                   |
|               |          | > Annex II - A-II.1.2 Case Creator  |
|               |          | > Policy Assignment to a User --    |
|               |          | > Corrections applied to the role   |
|               |          | > names                             |
|               |          | >                                   |
|               |          | > AnnexII - A-II.2.1 Case Policy    |
|               |          | > Assignment to a Group for any     |
|               |          | > Application Role -- Corrections   |
|               |          | > applied to the example: role      |
|               |          | > names, screenshots username and   |
|               |          | > group name                        |
|               |          | >                                   |
|               |          | > AnnexII - A-II.2.2 A-II.2.2 Case  |
|               |          | > Policy Assignment to a User for   |
|               |          | > any Application Role --           |
|               |          | > Corrections applied to the        |
|               |          | > example: role names, screenshots  |
|               |          | > username and group name           |
+===============+==========+=====================================+

# Introduction

## Purpose and Audience

> This document serves as a manual for [administrators]{.underline} for
> the *Reference Implementation of a National Application* (RINA). It
> covers the perspective of an IT administrator and details how a RINA
> instance can be configured locally or adapted to the needs of their
> institutions.
>
> The structure of this document closely follows the structure of the
> RINA software. This introduction provides some necessary context to
> understand the basic building blocks of the EESSI system, including
> the key concepts of Business Use Cases (BUCs) and Structured
> Electronic Documents (SEDs). The final section explains the
> administrative portal main screens.

## About EESSI

> The free movement of people is a fundamental right in Europe. Citizens
> of the European Union in parallel to Iceland, Lichtenstein, Norway,
> and Switzerland can freely travel to other countries in the
> associating space and take up residence and employment there. Modern
> social security systems need to reflect this mobility and make sure
> that citizens enjoy full access to social security in cross border
> settings as well.
>
> For this reason, the European social security coordination regulations
> provide clear rules for transnational social security cases.
> Implementing these rules in practice requires a lot of communication
> between social security institutions in the participant countries. So
> far, this communication is still largely done by the exchange of
> paper-based forms, which is slow, expensive, and error-prone.
>
> The new European system for the Electronic Exchange of Social Security
> Information (EESSI) will improve this situation by allowing a direct,
> reliable, and confidential communication between social security
> institutions. Exchanges will become faster; receiving institutions
> will no longer have to deal with illegible, erroneous or incomplete
> forms and citizens will ultimately benefit from a faster and even more
> reliable calculation of their benefits.

## EESSI Architecture

> To achieve an electronic exchange between all competent social
> security institutions in Europe, a well-organised interplay between
> national components and centralised infrastructure is necessary.
> Individual users will access the system either through RINA, the
> reference application detailed in this manual, or through a dedicated
> national application. Messages sent through this system are
> transferred to a national Access Point (AP), which communicates with
> the relevant Access Points in the receiving countries. From there,
> messages are transferred to the individual social security
> institutions in these countries. A centralised infrastructure provided
> by the European Commission, the Central Service Node (CSN), regularly
> provides all Access Points with the necessary information they need to
> fulfil this routing function.
>
> ![](media/image11.jpeg){width="6.092141294838145in"
> height="2.8266666666666667in"}
>
> []{#_bookmark4 .anchor}Figure 1: EESSI General Architecture

## Structured Electronic Documents (SEDs)

> The individual messages that need to be exchanged have been harmonised
> in close cooperation with member state social security experts and
> generally take the form of a Structured Electronic Document (SED).
> SEDs have been optimised to allow for as much automated pre-processing
> as possible to automatically identify a large set of possible errors
> or omissions prior to sending (thereby reducing the need to exchange
> corrections back and forth) and to faithfully reflect the applicable
> legal standards. Because SED versions will be available in all
> official languages of the European Union, every institution can also
> use its own language version to facilitate access to the documents.
>
> Structured Electronic Documents are the successor of E-Forms, the
> existing set of harmonised documents already used in many social
> security exchanges. SEDs, however, have been optimised to take full
> advantage of the additional possibilities (such as automated error
> detection) offered by an electronic system.

## Business Use Cases (BUCs)

> The processes needed to resolve cross border social security cases
> have been standardised across the participant countries. Thus, for
> every type of cross border social security issue, the corresponding
> Business Use Case (BUC) describes exactly which SEDs should be
> exchanged in which order to successfully resolve the case. In RINA,
> every case is assigned to a specific case type corresponding to one of
> these BUCs so that the application can automatically provide guidance
> on the appropriate sequence of SEDs to be exchanged.

## About RINA Application

> RINA (*Reference Implementation of a National Application)* is a
> web-based software application for the electronic management and
> exchange of social security cases across competent institutions of the
> participant countries. RINA is developed by the Directorate- General
> for Employment, Social Affairs and Inclusion (DG EMPL) and evolved out
> of the EESSI project (*Electronic Exchange of Social Security
> Information*). The application supports the complete range of business
> use cases concerning the exchange of social security data.
> Additionally, it provides helpful tools for the management of cases
> and the optimisation of internal workflows, for example by case
> assignment tools.
>
> It is based on 3 layers which are built one on top of the other:

- **Business Messaging Services (BMS)** - provides a reusable stateless
  component for sending business messages to the Access Point using the
  technical protocol (ebMS/AS4). These services offer protocol
  translation, validation and signing of business messages to ensure
  correct exchange within the EESSI environment, and the correct receipt
  of messages from other institutions;

- **Case Processing Services (CPS)** -- provides a stateful component
  built on top of the Business Messaging Services that manages cases in
  a structured manner taking care of all the issues regarding case,
  documents, notifications, user management and provides several
  interfaces for external access. In addition to that, it also manages
  data access and repository modules in order to configure and utilise
  the application according to the business needs;

- **Portal** -- provides a UI (user interface) built on top of the Case
  Processing Services (CPS). The interface having administration
  consoles (for administrators) and case management modules (for
  business users/Clerks).

![](media/image14.png)

> Figure 2: EESSI-RINA Architecture

# General Description

## Site Map

> The Admin Portal contains the following main administrative function
> groups (displayed at the main Navigation Bar): "*Application
> Settings", "Messaging Settings", "NIE Settings", "Rina Archiving",
> "IAM", "Authorisation", "Notifications Centre", "Logs", "Automatic
> Updates", "Test Centre" and "Business Exceptions".*

![Graphical user interface, text, application Description automatically
generated](media/image16.png){width="6.341862423447069in"
height="1.8241666666666667in"}

> []{#_bookmark10 .anchor}Figure 3: RINA Admin Portal Home Screen
>
> Additionally, at the top far right (see Figure 3) the "*Admin*" item
> provides access to the following menu: *"Localisation Settings"*,
> *"Change Password"*, *"Help"* and *"Logout".*

## ![](media/image19.png)General Layout, Portal Navigation and Organisation

> []{#_bookmark12 .anchor}Figure 4: RINA Admin Portal Home Screen
> (Sections)
>
> The Navigation Bar concentrate all the relevant items and subitems
> needed to configure all the administrative RINA aspects. Most of the
> navigation items include more than one subitem. For instance,
> *"Messaging Settings"* item includes three subitems (see [Figure
> 4](#_bookmark12)): *"Certificates", "Local Messaging Settings"* and
> "*Global Messaging Settings"*.
>
> Throughout this document, all these screens and sub-screens are
> presented.
>
> **[[Navigation Bar]{.underline}]{.smallcaps}**
>
> The Navigation Bar (Main Menu) is a fixed user interface element at
> the left of the application. It contains the following navigation
> items, which are described in detail in separate sections.

+---------------------------------+----------------------------------------------+
| > **NAVIGATION ITEM**           | > **[Section]{.smallcaps}**                  |
+=================================+==============================================+
| > *[Application                 | > Section [4.2](#application-settings)       |
| > Settings]{.smallcaps}*        |                                              |
+---------------------------------+----------------------------------------------+
| > *[Messaging                   | > Section [4.3](#messaging-settings)         |
| > Settings]{.smallcaps}*        |                                              |
+---------------------------------+----------------------------------------------+
| > *[NIE Settings]{.smallcaps}*  | > Section [4.4](#nie-settings)               |
+---------------------------------+----------------------------------------------+
| > *[RINA                        | > Section [4.5](#rina-archiving)             |
| > Archiving]{.smallcaps}*       |                                              |
+---------------------------------+----------------------------------------------+
| > *IAM*                         | > Section                                    |
|                                 | > [4.6](#iam-identity-and-access-management) |
+---------------------------------+----------------------------------------------+
| > *[Authorisation]{.smallcaps}* | > Section [4.7](#authorisation)              |
+---------------------------------+----------------------------------------------+
| > *[Notifications               | > Section [4.8](#notification-centre)        |
| > Centre]{.smallcaps}*          |                                              |
+---------------------------------+----------------------------------------------+
| > *[Logs]{.smallcaps}*          | > Section [4.9](#logs)                       |
+---------------------------------+----------------------------------------------+
| > *[Automatic                   | > Section [4.10](#automatic-updates)         |
| > Updates]{.smallcaps}*         |                                              |
+---------------------------------+----------------------------------------------+
| > *[Test Centre]{.smallcaps}*   | > Section [4.11](#test-centre)               |
+---------------------------------+----------------------------------------------+
| > *[Business                    | > Section [4.12](#business-exceptions)       |
| > Exceptions]{.smallcaps}*      |                                              |
+---------------------------------+----------------------------------------------+

> **[[Secondary Menu]{.underline}]{.smallcaps}**
>
> The secondary menu contains the subitems that are available to the
> administrator once the chosen item has been selected at the Navigation
> Bar.
>
> **[[Workspace]{.underline}]{.smallcaps}**
>
> The workspace corresponds to a virtual desk. It is a dynamic view
> where the actual content depends on the selected items or subitems.

+---------------------------------------+----------------------------+
| > **[[Admin User                      | > Section                  |
| > Profile]{.underline}]{.smallcaps}** | > [3](#admin-user-profile) |
| >                                     |                            |
| > The administrator can configure     |                            |
| > here his/her own User Profile.      |                            |
+=======================================+============================+

## Administrator Login

## 

> To connect to the Admin Portal, the administrator opens a browser to
> reach the RINA Web Application. The RINA administrator should supply
> the relevant RINA URL address and the appropriate credentials
> (username/password).
>
> After the administrator types the valid URL, the *"EESSI RINA"* Home
> Page is presented (see [Figure 5](#_bookmark14)). The administrator
> clicks on the Login button in order to be redirected to *"EESSI RINA
> Service"* login page (see [Figure 6](#_bookmark15)).

![](media/image23.png)

> []{#_bookmark14 .anchor}Figure 5: EESSI RINA Home Page
>
> The RINA Login Page is presented (see [Figure 6](#_bookmark15)) and
> the administrator can type in the **Username** and the **Password**.
> Following clicking LOGIN, he/she will be redirected to the RINA
> application.
>
> The administrators and the users share the same login page. The
> default credentials (username/password) for the administrator's login
> are **admin/admin123**. The procedure to change the password is
> described at section [3.2](#change-password).

![Graphical user interface, application Description automatically
generated](media/image25.png){width="2.993121172353456in"
height="2.5946872265966756in"}

> []{#_bookmark15 .anchor}Figure 6: RINA application Login Page

# Admin User Profile

> Under the "*admin"* item on the top right side ([Figure
> 7](#_bookmark17)), there are four different subitems that can be used
> by the administrator to customise his/her account *"Localisation
> Settings"*, to change the admin password *"Change Password"*, to get
> online help about the usage of the Administration Portal *"Help"* and
> the link for ending the current session *"Logout".*

![Graphical user interface, application Description automatically
generated](media/image26.jpeg){width="2.494471784776903in"
height="1.9054166666666668in"}

> []{#_bookmark17 .anchor}Figure 7: Admin User Profile

## Localisation Settings

> In this subitem the administrator can define the administrator's local
> settings to customise the admin interface accordingly. These settings
> are the **Language**, **Number Format**, **Time and Date Format**,
> **Time Zone** and **Currency**. The new settings are applied by
> pressing the SAVE button (or its equivalent in other languages).
>
> The list of time zones contains the following entries:

- (UTC-01:00) Further-western European Time (Azores)

- (UTC) Western European Time (Dublin, Lisbon, London)

- (UTC+01:00) Central European Time (Amsterdam, Berlin, Rome, Vienna)

- (UTC+02:00) Eastern European Time (Athens, Bucharest, Helsinki, Sofia)

> ![Graphical user interface, text, application, email Description
> automatically
> generated](media/image27.png){width="5.909115266841645in"
> height="3.00875in"}The time zones offsets due to daylight saving time
> are no longer included in the list of time zones as this information
> is managed automatically by the portal. This means when the system
> will automatically change to a different time zone offset (i.e.,
> wintertime), the portal time references will automatically get adapted
> to the updated local time.
>
> []{#_bookmark19 .anchor}Figure 8: Admin: Localisation Settings

## Change Password

> The administrator may change the administrator's Password any time by
> simple selecting the "*Change Password"* subitem that is provided
> under the "*Admin"* item (see [Figure 9](#_bookmark21)). The
> administrator should follow a common change password procedure by
> providing the **Old password** and the **New Password** twice. After
> providing the old and the new password, the administrator accepts the
> change by clicking on SAVE (that is activated only on case the
> administrator has followed correctly all the steps of the described
> change password procedure).

![Graphical user interface, text, application, email Description
automatically generated](media/image28.png){width="6.3170122484689415in"
height="3.2420833333333334in"}

> []{#_bookmark21 .anchor}Figure 9: Admin: Change Password

## Help

> The administrator may also receive online help on the RINA Admin
> Portal by selecting the
>
> *"Help"* subitem under the "Admin" Item ([Figure 10](#_bookmark23)).
>
> After the selection of the "Help" choice, a complete virtual
> presentation of the RINA Admin Manual is presented. There is a direct
> connection between the in-progress action of the administrator and the
> presented content of the online Help. For example, in the case the
> administrator is working on the "*Identity and Access Management
> (IAM)*" and selects *"Help"*, then the help window will open with the
> section concerning the *"Identity and Access Management (IAM)"*. In
> any case, the administrator can use the navigation panel on the right
> or the navigation keys (up/down, PgUp/PgDn) to go through the help
> content.

![Graphical user interface, text, application Description automatically
generated](media/image29.png){width="6.347614829396325in"
height="1.925in"}

> []{#_bookmark23 .anchor}Figure 10: Admin: Help

## User Idle Time and RINA Version

> At the bottom left corner of the screen the **user idle time** is
> displayed (see Section
> [4.2.2.1](#application-id-languages-max-idle-time-organisation-system-password-case-search-results-limit)).
> Once this countdown has elapsed the current user will be automatically
> logged out. The **RINA Portal version** and the **RINA Server
> version** installed can be found at the bottom right corner of the
> screen, this information might be helpful when reporting problems to
> the National or Local Service Desk.

![](media/image31.png)

> []{#_bookmark25 .anchor}Figure 11: User idle time and RINA Version

# RINA Application Configuration Settings

## Single Vs Multi-Tenant RINA installation configuration

> A single deployment instance of RINA Application can host more than
> [one Tenant]{.underline}. Each Tenant corresponds to the respective
> \"mapping\" towards a different IR institution (as defined within the
> Institution Repository (IR) specifications).
>
> The RINA Application settings consist of two different configuration
> sets, which are:

- the application configuration that is general and shared by all
  Tenants;

- the Tenant specific application configuration.

> The Tenant-specific configuration that performed at the Tenant level
> and can be found within the following sections:

- Application Settings (for Tenant and Case Counter);

- IAM (Identity and Access Management);

- Authorisation;

- Messaging Settings (for Local Messaging Settings).

> All other application configuration settings are common and shared by
> all Tenants. Analytically, the following settings are global and
> performed at the level of the Application and shared by all the
> supported Tenants:

- Application Settings (General Settings section, Default Case Settings
  and Default User Profile);

- Messaging Settings (Global Messaging Settings section and
  Certificates);

- NIE settings;

- RINA Archiving;

- Notification Centre;

- Logs (Audit and Technical);

- Automatic Updates;

- Test Centre;

- Business Exceptions;

> The administration is performed by a single common user (user:
> *admin*) that is the same among all Tenants. On the following table,
> the General Applications and the Tenant specific settings are
> summarised:

+-------------------------------+-------------------------------+
| > **Generic Application       | > **Tenant Specific           |
| > Settings**                  | > Settings**                  |
+===============================+===============================+
| > **Application Settings      | > The "Tenant" and "Case      |
| > (General Settings section,  | > Counter" parts of the       |
| > Default Case Settings and   | >                             |
| > Default User Profile)**     | > Application Settings        |
+-------------------------------+-------------------------------+
| > **Messaging Settings        | > Messaging Settings (for     |
| > (Global Messaging Settings  | > Local Messaging Settings)   |
| > section and Certificates)** |                               |
+-------------------------------+-------------------------------+
| > **NIE settings**            | > Authorisation               |
+-------------------------------+-------------------------------+
| > **RINA Archiving**          | > IAM (Identity and Access    |
|                               | > Management)                 |
+-------------------------------+-------------------------------+
| > **Notification Centre**     |                               |
+-------------------------------+                               |
| > **Logs (Audit and           |                               |
| > Technical)**                |                               |
+-------------------------------+                               |
| > **Automatic Updates**       |                               |
+-------------------------------+                               |
| > **Test Centre**             |                               |
+-------------------------------+                               |
| > **Business Exceptions**     |                               |
+-------------------------------+-------------------------------+

> Table 1: Generic Application and Tenant specific Settings

## Application Settings

> The "*Application Settings*" item contains five subitems:

- *"Tenant Settings"* (section
  [4.2.1](#application-settings-tenant-settings)): where the
  administrator can define and configure the Institutions/Liaison
  Body/etc 1 , that are defined as Tenants in the RINA
  Application/Installation (via Add, Set Default, Enable/Disable, and
  Delete actions);

- *"General Settings"* (section
  [4.2.2](#application-settings-general-settings)): *where* the general
  application settings can be defined;

- *"Default Case Settings"* (section
  [4.2.3](#application-settings-default-case-settings)): where the
  administrator can define general case visualisation settings for the
  clerks;

- *"Default User Profile"* (section
  [4.2.4](#application-settings-default-user-profile)): where the
  administrator can define the default user profile to be used by newly
  added users;

- *"Case Counter Settings"* (section
  [4.2.5](#application-settings-case-counter-settings)): where the
  administrator can define the option concerning the Local Case
  Identification.

#### ![](media/image32.png){width="0.37911089238845147in" height="0.10579505686789151in"} Application Settings: Tenant Settings

![](media/image35.png)

> []{#_bookmark30 .anchor}Figure 12: Tenant Settings
>
> The *"Tenant Settings"* subitem, displays the list of Tenants hosted
> in this RINA and their attributes (see [Figure 12](#_bookmark30)). The
> Tenant settings can be changed by the administrator.
>
> These setting are provided below.

- **Default**: The Default Tenant is the Tenant Institution that will be
  used by the RINA Application for all System Messaging (i.e. CDM / IR
  Synchronisation). The administrator can define the Default tenant by
  clicking the SET DEFAULT of the appropriate tenant from the given
  list. The administrator can also change the Default Tenant/Institution
  by selecting another tenant.

- **Enabled/Disabled**: The administrator can switch the
  "Enabled/Disabled" status of the tenants by simply clicking on the
  ENABLE/DISABLE. Before switching the status of the Tenant, RINA asks
  the administrator for a final conformation. A Disabled Tenant cannot
  be set to Default (see [Figure 13](#_bookmark31)).

> In case of a Disabled Tenant, the corresponding users cannot login to
> RINA Case Management Portal and operate on the Cases. Also, message
> exchange is disabled.
>
> *1 Regarding tenants from this point onwards, the word Institution
> will refer to any IR entity of the National domain which can be mapped
> to an Endpoint.*
>
> Nevertheless, the administrator can login and modify the configuration
> of the disabled Tenant.

![Graphical user interface, application Description automatically
generated](media/image38.png){width="6.35040135608049in"
height="1.7370833333333333in"}

> []{#_bookmark31 .anchor}Figure 13: Tenant Settings: Disable Tenant

![Graphical user interface, application Description automatically
generated](media/image39.jpeg){width="6.3081649168853895in"
height="2.0991655730533685in"}

> []{#_bookmark32 .anchor}Figure 14: Tenant Settings: Add New Tenant
>
> Only the Free-Text searching algorithm (section 5.2 of the **EESSI
> RINA User Manual**) is applied in the ADD TENANT action.
>
> The administrator can also:

- Add a new tenant to the system by first selecting the new tenant
  (institution) and then clicking on the icon
  \[![](media/image40.png){width="0.13055555555555556in"
  height="0.1450546806649169in"}\] (see [Figure 14](#_bookmark32)). The
  choice ADD TENANT is enabled only after starting to type the name of
  the institution in the edit box.

- Remove an existing tenant by clicking on the choice DELETE of the
  selected Tenant, before the Tenant deletion RINA asks the
  administrator for a final confirmation (see [Figure
  15](#_bookmark33)).

![Graphical user interface, application Description automatically
generated](media/image41.png){width="6.337883858267716in"
height="1.8379166666666666in"}

> []{#_bookmark33 .anchor}Figure 15: Confirmation Dialog Box for the
> deletion of a Tenant

#### ![](media/image42.png){width="0.5258245844269467in" height="0.10579505686789151in"} Steps to Add a New Tenant

> For a Tenant (new or existing) to be operational all its tenant
> specific configurations should be successfully completed.
>
> For example, the simple addition of a new Tenant in the "Tenant
> Settings" item, is not enough to have a fully functional tenant.
>
> The administrator also needs to specify:

- The valid Messaging Configuration: Global Messaging Settings, Local
  Messaging settings and Certificates should be modified and set
  accordingly.

  - Authentication Private Key (TLS), Authorisation Private Key (ebMS)
    and Business Signature default certificate of the Tenant should be
    added in the Certificates section of Messaging settings (see section
    [4.3.1](#messaging-settings-certificates));

  - Next, Authorisation Private Key (ebMS) with its password is paired
    in the Local Messaging (Tenant) Settings (see section
    [4.3.2](#messaging-settings-local-messaging-settings)).

- The IAM and Authorisation Settings for the new Tenant should also be
  modified accordingly. In more details:

  - At least one Group and one regular User should be added for the new
    Tenant;

  - The user should have at least membership "Supervisor" and
    "Authorized" to this Group in order to be assigned with enough
    access rights in each case instance (see section
    [4.6.1](#iam-users));

  - A Case Creator Policy and an Case Assignment Policy should be added
    and related to this User. Both policies could be grouped to a group
    policy (see section [4.7.1](#authorisation-assignment-policies));

  - For each sector and BUC, in order for this user to be automatically
    assigned (either in case of Case Owner or Counterparty) to case
    instances, the previous case creator and case assignment policy (or
    the group policy) should be assigned to the relevant processes (see
    section [4.7.2](#authorisation-process-assignments)).

- The Case Counter Settings are Tenant dependent, and it is not
  necessary to be configured by the administrator since a default value
  is used (see section
  [4.2.5](#application-settings-case-counter-settings)).

#### ![](media/image43.png){width="0.3841119860017498in" height="0.10579505686789151in"} Application Settings: General Settings

> See below (see [Figure 16](#_bookmark35)) the screen where the
> application configuration of all tenants is performed, and the
> corresponding parameters are configured:

![](media/image45.png)

> []{#_bookmark35 .anchor}Figure 16: Application Settings: General
> Settings

#### ![](media/image46.png){width="0.5258245844269467in" height="0.10579505686789151in"} Application Id, Languages, Max Idle time, Organisation System Password, Case Search Results Limit

![](media/image48.png)

> []{#_bookmark37 .anchor}Figure 17: General Settings: Define parameters
> like Application Id, Languages, etc.

- **Use Application Id**: This setting is used to identify the sending
  and receiving application for "Intelligent routing -- IR" on AP level
  ("Intelligent Routing" can automatically route messages depending on
  certain attributes. One of the attributes is the "Application Id". For
  example, one institution could have different RINA servers using the
  same Institution ID but different Application IDs; one "Application
  Id" can be used for Pensions and Sickness sectors (i.e.
  *"application1"*,) another one for AWOD (i.e. *"application2"*) and so
  on. More information about "Application Id" and "Intelligent routing
  -- IR" is available in the document "EESSI -- AP Intelligent Routing
  Interface" in the paragraph "Condition Input Facts".

- **Languages**: This option allows the administrator to select the list
  of the languages available to all the Users of this application. A
  default language proposed to new users (along with other settings) may
  be defined in the section *Default User Profile*.

+------------------------------------------------------------------------------------------------+-------------------------------------------------------+
| > ![C:\\Users\\qveit\\AppData\\Local\\Microsoft\\Windows\\INetCache\\Content.Word\\exclamation | > ***NOTE**:*                                         |
| > (2).png](media/image37.png){width="0.5866655730533683in" height="0.5866666666666667in"}      | >                                                     |
|                                                                                                | > *In case the language that was set in Default User  |
|                                                                                                | > Profile / Localisation Settings is removed from the |
|                                                                                                | > list of languages of General Settings then, by      |
|                                                                                                | > default, the language for Default User Profile /    |
|                                                                                                | > Localisation Settings will be switched to English   |
|                                                                                                | > expecting Administrator to access the Default User  |
|                                                                                                | > Profile screen and define the new default language  |
|                                                                                                | > for the users.*                                     |
|                                                                                                | >                                                     |
|                                                                                                | > *Upon removal from General Settings of the language |
|                                                                                                | > that was set in Localisation Settings, the English  |
|                                                                                                | > language will be automatically loaded as            |
|                                                                                                | > localisation for all the users including the Admin  |
|                                                                                                | > user that is performing that change.*               |
|                                                                                                | >                                                     |
|                                                                                                | > *English language cannot be removed from the list   |
|                                                                                                | > of languages defined in General Settings being a    |
|                                                                                                | > reference language.*                                |
+================================================================================================+=======================================================+

- **Max Idle Time (in minutes)**: The administrator can configure and
  set the Maximum Idle Time for the users/clients until disconnecting
  them from the system. The default value is set to 15 minutes. Keep in
  mind that the duration of the connection of the users/clients to RINA
  depends also to the thresholds that have been set for the Session time
  (these timers are refreshed only when a CPI call is performed). The
  default session timeout is 30 minutes. If there is no activity between
  RINA Portal and RINA Server (no CPI calls) for more than 30 minutes,
  then the jsession cookie will expire and the user access to RINA
  server will be forbidden and the user will be prompted to login again
  to RINA using its credentials (user and password). It is recommended
  that max idle time not to exceed the timeout for the jsession cookie
  (30 minutes).

- **Organisation System Password**: Sets the Organisation system
  password (System User Password) that is the password of the BPM
  engine. This information is deprecated and is not reflected in RINA
  Server if set in RINA Portal.

- **Case Search Results Maximum Limit**: Sets the maximum number of
  results that will be shown while performing a free text or predefined
  criteria case search in RINA portal accessible by the clerks. By
  default the initial limit is set to 100 results. It is highly
  recommended not to use a very high limit because this will reduce
  dramatically the search performance.

#### ![](media/image49.png){width="0.5374759405074365in" height="0.10579505686789151in"} SED Validation Mode, Child Documents

![A picture containing timeline Description automatically
generated](media/image50.png){width="6.184172134733158in"
height="0.7379166666666667in"}

> []{#_bookmark38 .anchor}Figure 18: General Settings: SED validation
> Mode
>
> Option **SED Validation Mode** allows the administrator to choose the
> most appropriate from the three validation methods available in the
> REST API stateful layer of RINA (see [Figure 18](#_bookmark38)):

- *Continue When No Validation* (where the process continues even when
  an exception occurs);

- *Exception When No Validation* (where the process does not continue
  when an exception occurs);

- *No Validation* (where no validation is performed, and the SED will be
  saved/submitted anyway).

> The parameter **Maximum number of Child Documents in Bulk SED** allows
> to setup the limit for the number of child documents (individual
> claims) under the bulk SEDs (containing the global claims).

![A picture containing bar chart Description automatically
generated](media/image51.png){width="6.18625656167979in"
height="0.7379166666666667in"}

> []{#_bookmark39 .anchor}Figure 19: General Settings: Maximum number of
> child documents

#### ![](media/image52.png){width="0.540825678040245in" height="0.10738626421697288in"} Show Full Error Information, Show Process Versions

> There are various settings which an administrator can configure in
> this section (see [Figure](#_bookmark40) [20](#_bookmark40)).
>
> **Show Full Error Information**: When selecting this option, the
> application provides more information in the stack trace in case of an
> error. By default, this is not enabled.
>
> **Show Process Version**: When selecting this option, the application
> shows the version of a BUC along with its name. By default, this is
> not enabled, but it can be used for testing or other purposes.

![](media/image55.png)

> []{#_bookmark40 .anchor}Figure 20: General Settings: Full Error
> Information and Versions

![Graphical user interface Description automatically generated with
medium confidence](media/image57.png){width="3.2749989063867018in"
height="0.6083333333333333in"}

> []{#_bookmark41 .anchor}Figure 21: General Settings: Show Process
> version (RINA User Portal)
>
> The screenshot above (see [Figure 21](#_bookmark41)) illustrates the
> difference displayed from the RINA User Portal between turning the
> above feature off (top) and on (bottom). This feature can be useful
> during some troubleshooting scenarios.

#### ![](media/image58.png){width="0.5391272965879265in" height="0.10579505686789151in"} Attachments settings

> The parameter **Attachment Maximum File Size (in MB)** sets the
> maximum file size of Case attachments (per attachment) that can be
> uploaded in RINA application (see [Figure](#_bookmark42)
> [22](#_bookmark42)). The default value is 10Mbytes and the maximum
> permitted value is 1.024 Mbytes.
>
> The field Attachment Allowed Mime Types displays the allowed file
> types that may be attached to a case/SED. The administrator can
> **neither delete a predefined file type by from the list by clicking
> on \[X\] nor add other types** that are not included by just written
> in the text field.
>
> Several compressed file types are supported as attachments (see
> [Figure 22](#_bookmark42)). The basic supported types are the "zip"
> and "gzip". The additional ones ("x-zip", "x-zip-compressed" and
> "octet-stream") are derived types and used only the case of Linux OS.
> The additional types are mapped by the RINA app to the basic one's
> file types.

+------------------------------------------------------------------------------------------------+--------------------------------------------------------+
| > ![C:\\Users\\qveit\\AppData\\Local\\Microsoft\\Windows\\INetCache\\Content.Word\\exclamation | > ***NOTE**:*                                          |
| > (2).png](media/image37.png){width="0.5866655730533683in" height="0.5866666666666667in"}      | >                                                      |
|                                                                                                | > *This functionality of changing the MIME Types in    |
|                                                                                                | > the RINA Portal was disabled in RINA 2020 due to the |
|                                                                                                | > inconsistency that this might create:*               |
|                                                                                                |                                                        |
|                                                                                                | 1)  *The list of allowed MIME Types is included in     |
|                                                                                                |     SBDH and one instance of RINA should not allow     |
|                                                                                                |     additional MIME types that are not included in     |
|                                                                                                |     SBDH.*                                             |
|                                                                                                |                                                        |
|                                                                                                | 2)  *Even if an instance of RINA is limiting the       |
|                                                                                                |     attachment types that are allowed by an            |
|                                                                                                |     institution, this would apply only for sending     |
|                                                                                                |     messages and would not stop receiving messages     |
|                                                                                                |     from other RINA or NA containing attachments that  |
|                                                                                                |     are not allowed by that instance of RINA.*         |
+================================================================================================+========================================================+

![](media/image61.png)

> []{#_bookmark42 .anchor}Figure 22: General Settings: Attachments
> Settings

#### ![](media/image63.png){width="0.545825678040245in" height="0.10738626421697288in"} Default values (Importance and Criticality)

![](media/image66.png)

> []{#_bookmark43 .anchor}Figure 23: General Settings: Default Values of
> Importance/Criticality of a case
>
> **Importance and Criticality**: This Eisenhower matrix (see [Figure
> 23](#_bookmark43)) sets the default importance and criticality levels
> for new cases. The values may be changed for each case afterwards.

#### ![](media/image68.png){width="0.38246719160104986in" height="0.10738626421697288in"} Application Settings: Default Case Settings

> The options available in **View mode** and **Sort by**, along with the
> toggle for **Display flags**
>
> allow the administrator to customise the interface layout for the
> application users.
>
> ![](media/image71.png)
>
> []{#_bookmark45 .anchor}Figure 24: Application Settings: Default Case
> Settings
>
> All these settings can be customised individually by each user
> according to their preferences, through RINA User Portal, by
> overwriting the default values, stored on default User profile,
> permanently. Before the creation and saving of any custom User
> profile, the RINA default user profile, defined by the administrator,
> is always used.

![](media/image75.png)

> []{#_bookmark46 .anchor}Figure 25: Clerk section Case Settings
>
> The **View Mode** selection can be used to define whether the
> **Classic** or the **Timeline View** is incorporated at the Case
> Management tab at the User portal. For every selection of the **View
> Mode**, a view-dependent part appears where the administrator can
> select the 1 or 2-columns view (in the case of **Timeline View**) or
> to check/uncheck the options that allows the grouping per month and
> the SED preview appearance (in the case of **Classic View**) (see
> [Figure 25](#_bookmark46)).
>
> ![Graphical user interface, application Description automatically
> generated](media/image77.png){width="6.351618547681539in"
> height="3.041353893263342in"}
>
> []{#_bookmark47 .anchor}Figure 26: Example of Classic View (User
> Portal)

![Graphical user interface, text, application Description automatically
generated](media/image78.png){width="6.300738188976378in"
height="3.29in"}

> []{#_bookmark48 .anchor}Figure 27: Example of Timeline View (User
> Portal)
>
> In addition, the SED sorting method can be defined. Analytically, SEDs
> can be sorted on Case Management view based either on the **Creation**
> on **Last Update** date.
>
> **Alarm settings**: It allows the administrator to set reminders for
> cases sent by users (see section [4.8](#notification-centre)). All
> these settings may be changed individually by each user according to
> their preferences.

![](media/image81.png)

> []{#_bookmark49 .anchor}Figure 28: General Settings: Alarm Settings

#### ![](media/image83.png){width="0.38582239720034994in" height="0.10579505686789151in"} Application Settings: Default User Profile

> Here, the administrator can configure the *"Default User Profile"* by
> the following settings:

### Language, Number format, Date and Time format, Currency and Time Zone.

![](media/image85.jpeg)

> []{#_bookmark51 .anchor}Figure 29: General Settings: Default User
> Profile

#### ![](media/image86.png){width="0.38246719160104986in" height="0.10738626421697288in"} Application Settings: Case Counter Settings

> There are 3 category of IDs there are defined for each business case:

- The Local ID is a numeric case id automatically generated on the local
  RINA database and at the moment is not transported when the case is
  sent to the other case participant(s);

- The Business Case ID is a local RINA database identification number
  (ID) of the case generated by applying a specific pattern that has
  been defined in advance by the RINA administrator inside the RINA
  Admin section of RINA Portal with the purpose to construct a unique
  ID, case relevant parameters (such as: BUC type, Sector, etc.); it is
  not transported when the case is sent to the other case
  participant(s); The business ID must be unique across the tenant
  institution's cases. The uniqueness cannot be checked prior to the
  generation of the ID, so the administrator should have deep
  understanding of the creation process.

- The International ID is an ID generated by RINA/NA application
  locally, remains unchanged, stored in SBDH, follows the message
  exchanges of the Case and can be used to identify the specific Case
  across the EESSI ecosystem

> The relationship between the local and business ID categories for
> cases created/received
>
> in RINA 2020, when the "Default" type is used:

- When a case is unarchived, the same Local and Business Case ID will be
  used after the case becomes unarchived.

> On the other hand, the relationship between the local and business ID
> categories for cases
>
> created/received up to RINA 2019, when the "Default" type was used:

- When a case was unarchived, a different Local from Business Case IDs
  was used after the case has been unarchived (status Closed or
  Removed).

> The *"Case Counter Settings"* page is used by the administrator to
> choose the Case Counter type and to define the relevant type-dependent
> settings per Tenant (see [Figure 30](#_bookmark53) &
> [Figure](#_bookmark54) [31](#_bookmark54)). Based on these settings
> RINA will create an additional **Business ID** string for every case.
> This Business ID is also displayed in the portal and can be searched
> by through the relevant fields.

![Graphical user interface Description automatically
generated](media/image87.png){width="6.255146544181978in"
height="0.8387489063867016in"}

> []{#_bookmark53 .anchor}Figure 30: Case Counter Settings
>
> The administrator can select one of the three available types that are
> the following:

- The **Default** type: the counter engine provides a default sequence,
  ensuring uniqueness and search ability;

- The **HTTP CallBack** type: the counter is received through an
  integration with an external provider that generates IDs;

- The **Pattern** type: the Business Case ID is generated by applying a
  specific pattern that has been defined in advance by the administrator
  with the purpose to construct a unique ID, case relevant parameters
  (such as: BUC type, Sector, etc.).

![](media/image89.png)

#### ![](media/image90.png){width="0.5258245844269467in" height="0.10738626421697288in"} Default Type

> When the administrator selects the type **Default**, there is not any
> other parameter that has to be defined (see [Figure
> 31](#_bookmark54)). This setting will use the same internal ID created
> by the system also for the business ID. This will always be unique.
>
> ![](media/image93.png)After any selection, the administrator should
> click on SAVE to have all the selections applied.
>
> []{#_bookmark54 .anchor}Figure 31: Case Counter Settings: Default Type

#### ![](media/image95.png){width="0.5374759405074365in" height="0.10738626421697288in"} HTTP Callback Type

> In this case, the administrator selects the **HTTP Callback** type,
> and a new screen is displayed with an edit field for the URL of the
> external provider. The administrator may also test the given URL to
> check its validity (see [Figure 32](#_bookmark55)).
>
> This URL will be called always when a case is created, and it is in
> the implementation responsibility to ensure the uniqueness of the IDs.
> RINA will issue a GET request to the specified URL and will use
> whichever string that gets received in response as the business ID
> parameter.

![](media/image98.png)

> []{#_bookmark55 .anchor}Figure 32: Case Counter Settings: HTTP
> Callback Type

#### ![](media/image100.png){width="0.540825678040245in" height="0.10738626421697288in"} Pattern Type

> At last, when the administrator chooses the third Counter generation
> type, the specified pattern will be parsed when creating a case and
> the business ID will be created. With this setting the administrator
> must provide a pattern in the displayed field.
>
> The below figure (see [Figure 33](#_bookmark56)) shows the way of
> choosing and configuring the templates and the pattern. The choice of
> the templates (for selection purposes to the pattern) is performed by
> clicking on the SAVE icon at the right end of the template description
> line. The administrator can also type the pattern by hand into the
> field.

![](media/image103.png)

> []{#_bookmark56 .anchor}Figure 33: Case Counter Settings: Pattern Type
>
> The pattern can be any string, but there are predefined character
> sequences, which will be replaced by generated values:

- \<BUC_TYPE\> -- this character sequence will be replaced by the BUC
  type of the case (e.g. P_BUC_01);

- \<SECTOR\> -- this character sequence will be replaced by the Case
  sector name (e.g. PENSION);

- \<SECTORSHORT\> - this character sequence will be replaced by the Case
  Sector short name ID, (e.g. the letter \'P\' for PENSION);

- \<SEQ(TYPE, OFFSET, MININUM_LENGTH)\> -- this character sequence will
  be replaced by a sequence number in the defined format. The pattern
  must be defined with three parameters, which influence the look and
  context of the sequence number. The attributes are explained below:

  - TYPE -- name of the sequence. There are three available sequence
    types:

    - Global -- incremental number for all the cases of the tenant
      institution;

    - BUC -- incremental number for all the cases of the given BUC type.
      This is evaluated when the case is created, i.e. the BUC type is
      known;

    - Sector - incremental number for all the cases of the given sector
      type. This is evaluated when the case is created, i.e. the sector
      type is known.

  - OFFSET -- defines the offset, which will be added to the generated
    number. Must be an integer value. Example: if the generated number
    was 10 and the offset set to 1000, the final sequence number will be
    1010;

  - MINIMUM_LENGTH -- defines the minimum length of the generated
    sequence number. If the character length of the generated number is
    shorter than the minimum length, it will be padded with zeros '0'.
    Example: if the generated sequence number was 1234 and the minimum
    length is set to 8, the final sequence string will be 00001234.

- DATE(\<FORMAT\>) -- this character sequence will be replaced by the
  date of the case creation in the given format.

> To illustrate the correct usage, some examples for the pattern type
> are provided below:

+-------------+-----------------------------------------------------+
| > **Example | > *The institution would like to generate the       |
| > 1**       | > Business ID containing the sector abbreviation    |
|             | > together with a sequence number for the sector    |
|             | > type and minimum length of 8 characters. The two  |
|             | > information categories should be divided by a     |
|             | > dash character. The desired pattern should look   |
|             | > like this:*                                       |
|             | >                                                   |
|             | > *Pattern:                                         |
|             | > **\<SECTORSHORT\>-\<SEQ(sector,0,8)\>***          |
|             | >                                                   |
|             | > *This pattern would generate a following business |
|             | > ID for a 5th case of type P_BUC_01**:             |
|             | > P-00000005**.*                                    |
+=============+=====================================================+

+-------------+-------------------------------------------------------------+
| > **Example | > *The institution would like to generate the Business ID   |
| > 2**       | > containing the institution name shortcut (e.g. INST),     |
|             | > full sector name, BUC type and a global sequence number   |
|             | > for all the cases of the tenant institution with minimum  |
|             | > length of 8 characters, starting at 1000. All the         |
|             | > information should be divided by a dash character. The    |
|             | > desired pattern should look like this:*                   |
|             | >                                                           |
|             | > ***INST-\<SECTOR\>-\<BUC_TYPE\>-\<SEQ(global,1000,8)\>*** |
|             | >                                                           |
|             | > *This pattern would generate a following business ID for  |
|             | > a 500th case of the institution with type P_BUC_01:       |
|             | > **INST-PENSION-P_BUC_01- 00001500**.*                     |
+=============+=============================================================+

+-------------+------------------------------------------------------------------+
| > **Example | > *The institution would like to generate the business ID        |
| > 3**       | > containing the institution name shortcut (e.g. INST), full     |
|             | > sector name, date of creation in the from dd/MM/yyyy and       |
|             | > sector sequence number with minimum length of 8 characters.    |
|             | > All the information should be divided by a dash character. The |
|             | > desired pattern should look like this:*                        |
|             | >                                                                |
|             | > ***INST-\<SECTOR\>-\<DATE(dd/MM/yyyy)\>-\<SEQ(sector,0,8)\>*** |
|             | >                                                                |
|             | > *This pattern would generate a following business ID for a     |
|             | > 1500th case of type P_BUC_01 created on 24th of December 2017: |
|             | > **INST-PENSION-24/12/2017-00001500**.*                         |
+=============+==================================================================+

+-------------+-----------------------------------------------------+
| > **Example | > *The following example shows a wrongly defined    |
| > 4**       | > pattern, which would fail to define a unique      |
|             | > Business ID per Case.*                            |
|             | >                                                   |
|             | > *Pattern:*                                        |
|             | >                                                   |
|             | > ***INST-\<SECTOR\>***                             |
|             | >                                                   |
|             | > *This pattern would successfully generate a       |
|             | > business id for the first case in each sector,    |
|             | > but would fail on every other, because there is   |
|             | > no uniqueness in the generation. For every cases  |
|             | > of the same sector, the business ID would look    |
|             | > the same.*                                        |
+=============+=====================================================+

## Messaging Settings

> There are three subitems in Messaging Settings:

- Certificates

- Local Messaging Settings

- Global Messaging Settings

#### ![](media/image105.png){width="0.37911089238845147in" height="0.10738626421697288in"} Messaging Settings: Certificates

![](media/image107.png)

> []{#_bookmark59 .anchor}Figure 34: Global Messaging Settings:
> Authentication (TLS)
>
> Within this section, all certificates (TLS, ebMS and Business
> signatures) for RINA application are managed. The relevant options are
> presented below:
>
> **Authentication (TLS=Transport Layer Security)**: Under this section
> (visible either by default, or once the administrator navigates upon
> pressing onto the related button), the administrator can add/remove
> the certificates for Authentication against the AP (see [Figure
> 34](#_bookmark59)). The certificates can be added by selecting the
> link NEW TLS PRIVATE CERTIFICATE or NEW TLS PUBLIC CERTIFICATE and can
> be removed by pressing DELETE. The Password field (for both TLS
> Keystore and TLS Truststore) allows the administrator to set the
> password for the TLS keystore. The default password is **supervisor**.
>
> In order to change the password for tlskeystore.jks, the admin user
> need to do several things:

1.  Change the password of the tlskeystore.jks itself

2.  Change the value of javax.net.ssl.keyStorePassword in Holodeck conf
    files (different in Windows and Ubuntu).

3.  Change also the password of the private TLS key in RINA Portal

4.  Make sure 1, 2 and 3 have the same value for new password.

> In the section **TLS Keystore,** the administrator will have the RINA
> TLS (private) certificate (National Domain). It is recommended to have
> a single private key in this section, since this TLS certificate
> represents the RINA server and not the tenants hosted in this server.
>
> In the section **TLS Truststore,** the administrator will have the AP
> TLS (public) certificate (National Domain).
>
> Keep in mind that any Update of the *"Global Messaging Settings"*,
> affects the Certificates installation date that is visible under the
> *"Certificate X.509"* information page available within each SED.
>
> ![Graphical user interface, application Description automatically
> generated](media/image108.png){width="6.335219816272966in"
> height="2.1958333333333333in"}
>
> []{#_bookmark60 .anchor}Figure 35: Global Messaging Settings:
> Authorisation (Signatures)
>
> **Authorisation (Signatures)**: Under this section (visible once the
> administrator navigates upon pressing onto the related button), the
> administrator can add/remove certificates for signing Messages (see
> [Figure 35](#_bookmark60)). The certificates can be added by selecting
> the link NEW MSG PRIVATE CERTIFICATE or NEW MSG PUBLIC CERTIFICATE and
> can be removed by pressing DELETE. The Password field (for both MSG
> Keystore and MSG Truststore) allows the administrator to set the
> password for the MSG keystore. The default password is **supervisor**.
> The ebMS certificates are normally handled in this section. Additional
> information about the Authorisation is available in the document
> "EESSI -- AS4 Messaging Profile".
>
> The section **MSG Keystore** should contain the (private) ebMS signing
> National Domain certificate(s) of every Tenant hosted by RINA.
>
> In the section **MSG Truststore,** the administrator has the (public)
> ebMS International Domain (TESTA) certificate of the AP.

![Graphical user interface, application Description automatically
generated](media/image109.png){width="6.259356955380578in"
height="1.525in"}

> []{#_bookmark61 .anchor}Figure 36: Global Messaging Settings: Business
> Signatures
>
> **Business Signatures**: Under this section (visible once the
> administrator navigates upon pressing onto the related button) the
> administrator can add/remove certificates which are used for signing
> the SEDs (see [Figure 36](#_bookmark61)). Multiple certificates are
> allowed. The certificates can be added by selecting the link NEW
> BUSINESS PRIVATE CERTIFICATE and can be removed by pressing DELETE.
>
> Each Tenant can use its own Business signature certificate that can be
> added in this tab. The pairing between the Business signature
> certificate and the Tenant can be specified in the next section
> *"Local Messaging Settings"*.

#### ![](media/image110.png){width="0.3841119860017498in" height="0.10738626421697288in"} Messaging Settings: Local Messaging Settings

> Under Local Messaging Settings contains shared Local Messaging
> Settings that are shared between all Tenants and specific settings of
> each Tenant.

![](media/image113.png)

> []{#_bookmark63 .anchor}Figure 37: Local Messaging Settings (PUSH
> example)
>
> The content of the screen depends on the **Transport Mode** (PULL or
> PUSH) that was configured in *"Global Messaging Settings"*.
>
> ![](media/image117.png)
>
> []{#_bookmark64 .anchor}Figure 38: Local Messaging Settings (PULL
> example)
>
> Initially, the administrator can verify the **Access Point** data (see
> [Figure 37](#_bookmark63) and [Figure](#_bookmark64)
> [38](#_bookmark64)), as defined through the RINA Installation and
> Configuration process that is:

- The communication **Protocol** (http or https);

- The **IP** address (in terms of the Fully Qualified Domain Name -
  FQDN);

- And the appropriate **Port**.

> These settings can be adapted accordingly when necessary.
>
> The following settings of the Access Point **Business Endpoints** (for
> SED exchange) and
>
> **System Endpoints** (for synchronisation activities) are displayed:

- **Inbox** (Business/System): The AP application context related
  service where messages are being retrieved from (only used when the
  Transport Mode is set to \'*Pull*\' mode); this is configured in
  CSN/AP and defined through installation scripts in RINA application;

- **Outbox** (Business/System): the AP application context related
  service where the messages are being sent to; this is configured in
  CSN/AP and defined through installation scripts in RINA application;

> **Tenant Settings:** For each Tenant, the administrator should
> configure the following:

### the Default Business Signature Alias;

- the following parameters for Business and System Endpoints:

  - the URL of the **Messaging Partition Channel (MPC)** can be
    configured; this is configured in CSN/AP and defined through
    installation scripts in RINA application, while also retrieved from
    the AP;

  - the **Pulling Interval** specifies the period where the ebMS client
    will pull messages from the AP Inbox queues (only used when the
    Transport Mode is set to \'*Pull*\' mode);

  - the ebMS Certificate **Alias** to be used for Business and System;

  - the **Password** of the abovementioned ebMS Certificates.

> To have the new settings applied, the SAVE button should be pressed.
>
> In-depth information about these settings is available within "EESSI
> -- CSN Repository
>
> Structure and Management" documentation.

#### ![](media/image119.png){width="0.38246719160104986in" height="0.10738626421697288in"} Messaging Settings: Global Messaging Settings

> All *"Global Messaging Settings"* are shared among all Tenants.

![](media/image121.png)

> []{#_bookmark65 .anchor}Figure 39: Global Messaging Settings
>
> **BMP Validation Mode** allows the administrator to configure the
> validation against the local XSD files, at the business message
> services (BMS) layer, ApClient microservice, (see [Figure
> 39](#_bookmark65)):

- *Continue When No Validation* (Validation is active for demonstration
  purposes, but the process continues);

- *Exception When No Validation* (Processing does not continue when an
  exception occurs);

- *No Validation* (No validation is performed).

> **Transport Mode**: This option needs to be defined either as *Pull*
> or *Push*.
>
> **Max Message Size (KB)**: This attribute sets the message maximum
> permitted size that can be sent from RINA application. This is not a
> limitation per file, but for the entire exchanged message (including
> the SOAP ebMS envelope, the SED and the attachments). Also note that
> currently the maximum limit is set to 2GB.
>
> The default value is 51.200 KBytes.
>
> **Retry interval (sec)**: This attribute sets the message retry
> interval (in secs). The default value is 237600 seconds (66 hours).
>
> **Maximum retries**: This attribute sets the maximum number of retries
> to send a message. The default value is 1.
>
> **Default pull request interval (sec)**: This attribute is where the
> frequency of checking for new data is set when the Transport Mode is
> set to *Pull*. The default setting is 60.
>
> **Antimalware Mode**: This attribute controls the mode of the
> Antimalware function. There are 3 different selectable Antimalware
> modes:

- **None** (default): No antimalware control is applied (see [Figure
  40](#_bookmark66) 1st selection).

- **Periodic Check**: the antimalware is applied periodically. The
  administrator configures the **Timeframe Settings** (see [Figure
  40](#_bookmark66), 2nd selection). It is not recommended to set a high
  value for antimalware periodic check since it affects the system
  performance. Prefer value for timeframe less than 45 secs;

- **Triggered**: the antimalware starts when the administrator calls it.
  The administrator must define the **Scan Command** and the
  **Antimalware Inf code** (see [Figure 40](#_bookmark66), 3rd
  selection).

![](media/image124.png)

> []{#_bookmark66 .anchor}Figure 40: Global Messaging Settings:
> Antimalware

## NIE Settings

> **National Information Exchange (NIE)** is a RINA stateful interface
> that allows participant countries to exchange information with their
> National Applications/Systems. Also, it allows RINA to receive
> documents and/or be notified when configurable events occur during the
> lifecycle of a case and including its documents, based on
> subscriptions to specific events during the case handling lifecycle at
> both Case and Document levels.
>
> RINA uses the NIE client to connect to a listener at National level.
> This listener will be notified by RINA when a specific
> Case/Document/Notification event happens. For a Document (SED) Level
> example, in such an event -- the system can create notifications when
> a new P5000 SED in a Survivors Pension Claim case is received.
>
> When the event -- to which the administrator subscribed -- happens,
> RINA will notify a specific listener in the National Application and
> provide it with the appropriate (file) resources. The call to the
> National Application is synchronous, allowing the National Application
> to modify \[where needed\] the resources and exchange back additional
> information relevant from a business perspective.
>
> More information about NIE is available in "EESSI -- RINA National
> Information Exchange
>
> Interface (NIE)".

#### ![](media/image126.png){width="0.37911089238845147in" height="0.1039676290463692in"} Creating subscriptions

![](media/image129.png)

> []{#_bookmark68 .anchor}Figure 41: NIE Settings
>
> By default, no case/document/notifications subscriptions are defined.
> The administrator can add NIE events (through RINIE -- Reference
> Implementation of National Information Exchange) via "*Add Case
> Event"*, "*Add Document Event"* or "*Add Notification Event"* subitems
> (see [Figure 41](#_bookmark68)).

#### ![](media/image131.png){width="0.5258245844269467in" height="0.1039676290463692in"} Add case event

![](media/image134.png)

> []{#_bookmark69 .anchor}Figure 42: NIE Settings: Add Case Event
> Subscription
>
> The following example depicts how to subscribe to a new Case event
> (see [Figure 42](#_bookmark69)):

- In this form, the administrator is required to fill in the
  **Subscription Name**, the relevant **BUC** and **Version** along with
  other relevant fields depending on the purpose of the subscription.
  The NIE listener for cases runs under the location mentioned on the
  form. As an example, the settings could be populated in the form of
  the following data:
  \'*http://10.1.2.35:8080/eessi-rina-nie/CasesEvents*\', \'*Pension
  1*\', \'*P_BUC_01*\', \'*1.0*\' respectively);

- When done, the administrator should press SAVE button to add the new
  subscription.

#### ![](media/image136.png){width="0.5374759405074365in" height="0.10579505686789151in"} Add document event

> In a similar way, a document subscription can also be added (see
> [Figure 43](#_bookmark70)).
>
> Again, fill in the **Subscription Name** and **Document**, and then
> the URL for the relevant events. The NIE listener for documents runs
> under the location mentioned on the form. When done, press SAVE to
> finish (at the bottom right corner of the form). The URL for NIE needs
> to be implemented by the participant countries, in accordance with the
> specifications published in "EESSI National Information Exchange
> Interface" documentation
>
> ![](media/image139.png)
>
> []{#_bookmark70 .anchor}Figure 43: NIE Settings: Add Document Event
> Subscription
>
> The administrator can add a subscription for more than one case or
> more than one document.
>
> To add more documents, press the ADD button selecting each document
> the administrator wishes to add through the relevant subscription.
>
> However, please be aware that even though the administrator can create
> a complex subscription for either multiple cases or documents (see
> [Figure 44](#_bookmark71)), it is recommended to create one or
> multiple individual subscriptions for each event type as a risk averse
> approach against error prone configurations.
>
> ![Graphical user interface, application Description automatically
> generated](media/image141.png){width="6.291458880139983in"
> height="3.223957786526684in"}
>
> []{#_bookmark71 .anchor}Figure 44: NIE Settings: Manage multiple Case
> Event Subscriptions

#### ![](media/image142.png){width="0.540825678040245in" height="0.10738626421697288in"} Add notification event

> Finally, the administrator can create Notification's events by
> selecting the "*Add Notification Event"* subitem (see [Figure
> 45](#_bookmark72)).

![](media/image145.png)

> []{#_bookmark72 .anchor}Figure 45: NIE Settings: Add Notification
> Event
>
> The administrator must enter a **Subscription Name** followed by the
> URL of the listener where the URL defines the location where the
> notification's templates should be saved (as an example: URL:
> \'*http://10.1.2.35:8080/eessi-rina-nie/NotificationsEvents'.*)

#### ![](media/image147.png){width="0.3841119860017498in" height="0.10579505686789151in"} Deleting subscriptions

> To delete a subscription, the administrator can simply press on the
> DELETE button located at the right of each existing subscription (see
> [Figure 46](#_bookmark73)).

![](media/image150.png)

> []{#_bookmark73 .anchor}Figure 46: NIE settings: Delete existing
> subscription.
>
> The administrator may press YES to confirm the subscription deletion,
> or NO to abort the operation (see [Figure 47](#_bookmark74)).

![](media/image154.png)

> []{#_bookmark74 .anchor}Figure 47: NIE Settings: Confirmation for
> Deleting Subscriptions

## RINA Archiving

> RINA archiving is described in the document "EESSI -- RINA Archiving
> Specifications". RINA is able to archive the closed cases together
> with documents, comments and attachments. The name \'archiving\' has
> been retained (from previous versions) for historical reasons, since
> the intention is to avoid confusion for the users with different
> terminology. Furthermore, the zipping of the case archiving is no
> longer performed since this operation can be executed directly on the
> DB with the new approach. On the other hand, the message archiving has
> been retained.
>
> ![](media/image156.png){width="0.37911089238845147in"
> height="0.10579505686789151in"} ***Definitions of Archiving and
> Retention Periods***

### Case Archiving:

> For the Case Archiving procedure, the administrator defines the
> Archiving Period based on the following definitions and on the state
> transition diagram given on [Figure 48](#_bookmark76)):

- **Archive period:** period of time during which a **Closed Case** or
  Removed Case is retained at such state, prior to **automatically**
  getting to Archived state. For a case at Archive state only Case
  metadata are available to the user.

![](media/image159.png)

> []{#_bookmark76 .anchor}Figure 48: Case State Transition Diagram

### Message Archiving:

- **Archive period**: period during which a Message is retained at the
  system, prior to

> **automatically** getting **Archived**.

- **Retention period**: period during which an **Archived** Message is
  retained into the system, prior to **automatically** getting
  **Deleted**.

#### ![](media/image161.png){width="0.3841119860017498in" height="0.10738626421697288in"} RINA Archiving: Archiving Policies

![Graphical user interface, text, application Description automatically
generated](media/image162.jpeg){width="6.34935476815398in"
height="2.085415573053368in"}

> []{#_bookmark77 .anchor}Figure 49: RINA Archiving: Archiving Policies
>
> The screen *"Archiving policies"* (see [Figure 49](#_bookmark77))
> allows the creation of policies for archiving cases. To create a case
> archiving policy the administrator must click on ADD POLICIES. To
> choose whether messages should also be **archived** the administrator
> needs to go to SETTINGS in the top right corner and check the
> **Archive Messages** checkbox, here also the **Default Archiving
> Period** for cases and messages can be configured. Optionally, the
> administrator may EDIT the **Archiving Period** for any of the
> existing Archiving policies.

![](media/image165.png)

> []{#_bookmark78 .anchor}Figure 50: RINA Archiving: Archiving Policy -
> Cases
>
> After clicking on ADD POLICIES the administrator can configure the new
> archiving policy in the Archiving Policies Form (see [Figure
> 50](#_bookmark78)), the administrator can select the business sector
> from the drop-down list (i.e. AWOD, Family Benefits, Pension etc.) and
> then select one or more (or even all) BUCs. Then, he/she can select
> **Process Owner** or **Counter Party** (or even both as case role(s))
> and an **Archiving Period**, if different from the default period.
> Then, by pressing SAVE, the administrator can finalise the setup of
> the archiving policy. Otherwise, by pressing BACK, the operation gets
> aborted.

#### ![](media/image167.png){width="0.38246719160104986in" height="0.10738626421697288in"} RINA Archiving: Message Retention Policies

![](media/image170.png)

> []{#_bookmark79 .anchor}Figure 51: RINA Archiving: Message Retention
> policies
>
> The *"Message retention policies"* screen (see [Figure
> 51](#_bookmark79)) allows the administrator to set the **Default
> Retention Period** for messages prior to getting **Removed**. The
> administrator may leave the **Default period** of 90 days or change it
> to another natural number between 1 and 3650 days. At the end, the
> administrator should review the selected options and press SAVE, for
> the system to save the changes.

#### ![](media/image172.png){width="0.38582239720034994in" height="0.10579505686789151in"} RINA Archiving: Archiving Repositories

![](media/image174.png)

> []{#_bookmark80 .anchor}Figure 52: RINA Archiving: Archiving
> Repositories
>
> The **Archiving repositories** screen (see [Figure 52](#_bookmark80))
> is the screen where the administrator can configure the location of
> the messages repositories. The cases are not anymore archived on the
> disk but inside RINA database so there is no need to define volumes in
> the Portal for cases archiving. The screenshot above shows the default
> configuration (such as **Volume Names**, **Minimum Threshold in MBs**,
> and **Location**). The administrator may change the existing settings
> by pressing EDIT or delete an archive volume by pressing DELETE.
> Additional volumes can be added by the ADD REPOSITORY button.
>
> ![](media/image176.png)
>
> []{#_bookmark81 .anchor}Figure 53: RINA Archiving: Archiving
> Repositories - Edit Volume

![](media/image178.png)

> []{#_bookmark82 .anchor}Figure 54: RINA Archiving: Archiving
> Repositories - Add Volume
>
> By pressing ADD VOLUME button, a new screen is presented with various
> settings. The administrator may provide **Volume Name** of the new
> archiving repository volume and the minimum capacity threshold in
> MBytes (**Min. Threshold (MB)**). The administrator may add a location
> path on a RINA volume by pressing on ADD. Once the procedure has been
> completed the administrator selects SAVE button for the system to save
> the changes or BACK button to abort the operation.

#### ![](media/image179.png){width="0.38246719160104986in" height="0.10579505686789151in"} RINA Archiving: Message Archiving Repository Policy

![](media/image182.png)

> []{#_bookmark83 .anchor}Figure 55: RINA Archiving: Message Archiving
> Repository Policy
>
> The **Message archiving repository policy** screen allows the
> administrator to select the volume where the messages will be stored
> for archiving purposes (see [Figure 55](#_bookmark83)).
>
> The administrator can select the desired **Volume** (defined in the
> section Archiving repositories) and press SAVE for the system to save
> the configuration changes.

## IAM (Identity and Access Management)

> **IAM** functionality allows configuring users and groups in RINA. All
> IAM settings are distinguished and independent between each RINA
> Tenant. This item is split in three subitems: *"Users", "Groups"* and
> *"LDAP Configuration"*. Also, the following table displays which
> actions the RINA roles can perform (more information can be found in
> the document *\"EESSI - RINA -- Identity and Access Management
> (IAM)\").*

+--------------------------------------------------+--------------+--------------+----------------+-----------+----------+-----------+-------+------------+
| > **RINA**                                       | > Supervisor | > Authorised | > Unauthorised | > Auditor | > Viewer | > Medical | > VIP | > Everyone |
| >                                                |              |              |                |           |          |           |       |            |
| > **[User Roles]{.smallcaps}**                   |              |              |                |           |          |           |       |            |
+===========================+======================+:============:+==============+================+===========+==========+===========+=======+============+
| > ![](media/image185.png) | > Assign Case        | > ✔          |              |                |           |          |           |       |            |
|                           +----------------------+--------------+--------------+----------------+-----------+----------+-----------+-------+------------+
|                           | > Request Assignment | > ✔          | > ✔          | > ✔            | > ✔       | > ✔      | > ✔       | > ✔   | > ✔        |
|                           +----------------------+--------------+--------------+----------------+-----------+----------+-----------+-------+------------+
|                           | > Authorise          | > ✔          |              |                |           |          |           |       |            |
|                           | > Assignment         |              |              |                |           |          |           |       |            |
+---------------------------+----------------------+--------------+--------------+----------------+-----------+----------+-----------+-------+------------+
|                           | > Create Case        |              | > ✔          | > ✔            |           |          |           |       |            |
|                           +----------------------+--------------+--------------+----------------+-----------+----------+-----------+-------+------------+
|                           | > Create SED         |              | > ✔          | > ✔            |           |          |           |       |            |
|                           +----------------------+--------------+--------------+----------------+-----------+----------+-----------+-------+------------+
|                           | > View SED           | > ✔          | > ✔          | > ✔            | > ✔       | > ✔      |           |       |            |
|                           +----------------------+--------------+--------------+----------------+-----------+----------+-----------+-------+------------+
|                           | > Send SED           | > ✔          | > ✔          |                |           |          |           |       |            |
|                           +----------------------+--------------+--------------+----------------+-----------+----------+-----------+-------+------------+
|                           | > Request Approval   |              |              | > ✔            |           |          |           |       |            |
|                           | > for sending        |              |              |                |           |          |           |       |            |
|                           +----------------------+--------------+--------------+----------------+-----------+----------+-----------+-------+------------+
|                           | > Approve and Send   | > ✔          | > ✔          |                |           |          |           |       |            |
|                           | > SED                |              |              |                |           |          |           |       |            |
|                           +----------------------+--------------+--------------+----------------+-----------+----------+-----------+-------+------------+
|                           | > View/Upload/       |              |              |                |           |          | > ✔       |       |            |
|                           | > Delete/            |              |              |                |           |          |           |       |            |
|                           | > Send/Download      |              |              |                |           |          |           |       |            |
|                           | > medical            |              |              |                |           |          |           |       |            |
|                           | > attachments        |              |              |                |           |          |           |       |            |
|                           +----------------------+--------------+--------------+----------------+-----------+----------+-----------+-------+------------+
|                           | > View VIPS          |              |              |                |           |          |           | > ✔   |            |
|                           +----------------------+--------------+--------------+----------------+-----------+----------+-----------+-------+------------+
|                           | > Change Case        | > ✔          | > ✔          | > ✔            |           |          |           |       |            |
|                           | > Metadata \*        |              |              |                |           |          |           |       |            |
|                           +----------------------+--------------+--------------+----------------+-----------+----------+-----------+-------+------------+
|                           | > Manual case        | > ✔          | > ✔          |                |           |          |           |       |            |
|                           | > archiving          |              |              |                |           |          |           |       |            |
|                           +----------------------+--------------+--------------+----------------+-----------+----------+-----------+-------+------------+
|                           | > Manual case        | > ✔          | > ✔          |                |           |          |           |       |            |
|                           | > unarchiving        |              |              |                |           |          |           |       |            |
|                           +----------------------+--------------+--------------+----------------+-----------+----------+-----------+-------+------------+
|                           | > Set/clear alarms   | > ✔          | > ✔          | > ✔            |           |          |           |       |            |
|                           +----------------------+--------------+--------------+----------------+-----------+----------+-----------+-------+------------+
|                           | > View case          | > ✔          | > ✔          | > ✔            | > ✔       | > ✔      | > ✔       | > ✔   | > ✔        |
|                           | > metadata\*2        |              |              |                |           |          |           |       |            |
|                           +----------------------+--------------+--------------+----------------+-----------+----------+-----------+-------+------------+
|                           | > View/download/send | > ✔          | > ✔          | > ✔            | > ✔       | > ✔      |           |       |            |
|                           | > regular            |              |              |                |           |          |           |       |            |
|                           | > attachments        |              |              |                |           |          |           |       |            |
|                           +----------------------+--------------+--------------+----------------+-----------+----------+-----------+-------+------------+
|                           | > Add-Upload/delete  |              | > ✔          | > ✔            |           |          |           |       |            |
|                           | > regular            |              |              |                |           |          |           |       |            |
|                           | > attachments        |              |              |                |           |          |           |       |            |
|                           +----------------------+--------------+--------------+----------------+-----------+----------+-----------+-------+------------+
|                           | > Add/delete         | > ✔          | > ✔          | > ✔            | > ✔       | > ✔      |           |       |            |
|                           | > comments           |              |              |                |           |          |           |       |            |
+---------------------------+----------------------+--------------+--------------+----------------+-----------+----------+-----------+-------+------------+
|                           | > View Audit         | > ✔          |              |                | > ✔       |          |           |       |            |
+---------------------------+----------------------+--------------+--------------+----------------+-----------+----------+-----------+-------+------------+

> []{#_bookmark86 .anchor}Table 2: RINA Roles - Actions Matrix
>
> *\* i.e. Subject block (username, name, gender and birth date or the
> relevant institution description in bilateral reimbursement cases),
> Case participants & assignments, document list (SEDs), alarms, SED and
> Case level comments*
>
> **Notes / Clarifications:**
>
> *A User/Clerk can have multiple roles. A user with multiple roles can
> perform any action permitted by all the assigned roles. As an example,
> a clerk having authorised role that has also a medical role can send
> SEDs (permitted by the authorised role) and also read classified
> medical attachments (permitted by the medical role);*
>
> *In general, Medical and VIP roles have limited permissions (view
> metadata and handle Medical and VIP data) and can be considered as
> [supplementary]{.underline} roles that are assigned to specific users
> when access to critical data is required;*
>
> *Only users having VIP role are able to select/unselect the
> "Sensitive" flag in the "Case Metadata" popup;*
>
> *A user having a VIP role may set "Sensitive Case" flag BUT in order
> to create/edit documents must have also authorised / unauthorised
> role. In order to send documents, the clerk must have authorised role.
> In order to view case documents, the clerk must have authorised /
> unauthorised, supervisor and/or viewer roles.*
>
> *A user having Medical role can tag/untag an attachment as medical. To
> add must have also authorised / unauthorised role. To view it, the
> user must have authorised / unauthorised, supervisor and/or Viewer
> roles.*
>
> *Supervisors, Authorised, and unauthorised roles allow users to be
> able to change the Criticality and Importance properties (Case
> Assignments)*
>
> *Some groups can be labelled with the "Organisational Unit" flag (the*
>
> *equivalent of the OU in LDAP). This is used to represent the
> branches.*
>
> Based on the multi-tenancy feature of RINA, there is an option to
> configure the IAM settings related to the specific tenant by selecting
> the relevant tenant value on the top left hand side of the screen (see
> [Figure 56](#_bookmark87)). If there is only one tenant, the system
> displays only the default one. After the Tenant selection, all the IAM
> settings (Users & Groups settings, LDAP configuration) corresponds to
> the selected tenant.

![](media/image188.png)

> []{#_bookmark87 .anchor}Figure 56: IAM: Select Tenants

#### ![](media/image190.png){width="0.37911089238845147in" height="0.10738626421697288in"} IAM: Users

![](media/image193.png)

> []{#_bookmark89 .anchor}Figure 57: IAM: User Settings
>
> In the *"Users"* screen (see [Figure 57](#_bookmark89)), the
> administrator can perform management of RINA users. The administrator
> can ADD USER, EDIT, or DELETE users accordingly.
>
> The users list is refreshed automatically when a tenant is selected
> from the list of tenants.

#### ![](media/image195.png){width="0.5258245844269467in" height="0.10738626421697288in"} Creating users

![Graphical user interface, application Description automatically
generated](media/image196.png){width="6.330146544181977in"
height="3.0806244531933507in"}

> []{#_bookmark91 .anchor}Figure 58: IAM: Add Users
>
> To add a new user, the administrator can press the ADD USER button in
> the top right-hand side of the screen.
>
> In the **User Form**, the administrator can fill in the relevant
> fields (see [Figure 58](#_bookmark91)):

- *Username*;

- *Password* (twice for Confirmation);

- *First* and L*ast Name*;

- *Email* address;

- *Mobile number;*

- *Business Keystore Certificate Alias* and whether the account is
  *Enabled* or not (the user can be provisioned for a later date but may
  not be currently active).

> In the section **Memberships**, the administrator can add the relevant
> groups and roles. Membership is the link between the user, the group
> and the user's role in the group. From the **Group** pick-list the
> administrator can select the relevant group and then continue
> selecting the subsequent pick-list(s) until the administrator reaches
> the appropriate (sub) group.
>
> More information about roles and the user rights associated with each
> is available in the document "EESSI RINA Identity and Access
> Management (IAM)" and in the sub-section *RINA User roles* (under
> section *Logical components*) describing the mapping between the
> actions and user roles.
>
> The administrator may select the relevant role from the **Role**
> drop-down list for each group membership and he/she may add more than
> one group membership, with an identical or a different role for each
> IAM setting of every tenant.
>
> After selecting the appropriate group from the **Group** list by
> clicking on its name and the **Role** from the available and
> predefined Roles, the administrator presses ADD in order to insert a
> new assignment.
>
> The administrator may also assign more than one role per group (for
> instance, a user may have the role VIP in the group Family Benefits
> and the roles of Viewer and Medical Viewer in the group Pensions).
>
> When all the user's details and group memberships have been added, the
> administrator needs to press SAVE for the system to save the
> configuration changes.

#### ![](media/image197.png){width="0.5374759405074365in" height="0.10738626421697288in"} Modifying users

![Graphical user interface, application Description automatically
generated](media/image198.png){width="6.336202974628171in"
height="3.2872911198600177in"}

> []{#_bookmark93 .anchor}Figure 59: IAM: Modify Users RINA
>
> To edit a user, the administrator can use the "Search" field on the
> top of the screen to search for a particular user by means of the RINA
> free-text search engine. The search mechanism applies after the user
> presses the search button
> (![](media/image199.png){width="0.20069335083114612in"
> height="0.20812445319335082in"}).
>
> RINA free-text search engine has the following features:

- Any search applies to each one of the following searchable users'
  fields:

  - Username

  - First name

  - Last name

  - Email

  - Mobil number

- It supports **more than one word** in a single search separated by
  spaces; if user searches using multiple words, the search is executed
  assuming an "AND" operator between the words -- it will require all of
  the terms of the searching string to be present in the results

- The searches are performed in a **case insensitive** mode Specific
  special characters/operators/formats are supported:

<!-- -->

- The **character '+'** signifies a logical AND operation (this operator
  is optional since the space also signifies a logical 'AND'); this
  option should be used when searching for entire words not in the case
  of using approximative search using \* character. Example: *'user
  test'* or *'user + 'test'* will return results that contain both the
  words *'user* and *'test'* in any of the searchable fields;

- It can be used **OR operator between words** and this would mean
  searching for results containing first word or containing the second
  word not necessarily both of them in the same case as in the situation
  of AND operator;

- The **character '-'** negates a single token and returns results that
  do not match the specific tokens; [Beware]{.underline}: in order for
  this algorithm to provide the proper results, the hyphen ("-") needs
  to be adjacent to the value to exclude from the search results
  (without any spaces between); hence, no space character should be
  between them; this option should be used when searching for entire
  words not in the case of using approximative search using \*
  character;

> Example: 'user -test' will return users that match with the value
> 'user in any
>
> searchable field and NOT the value 'test'.

- In case of using numbers to search by then **the number must be
  positioned in the beginning of the searched text** and not in the
  middle or at the end of it; Example: in case of using numbers the
  sequence to search by should be "8415 case"; do not use sequences like
  "case 8415" or "comment 8415 submit" because the engine will return no
  results;

- Starting from RINA 6.\* release **the search mechanism has been
  improved** and it is using a more advanced and improved text search
  algorithm. So when the user type a key word in the search box this
  does not do an exclusive search for the exact word, but instead it
  knows about plural/singular, feminine/masculine and so on, and also
  different forms of a word for example jump/jumping/jumped (this
  applies only for English language);

- A partial search can be applied if **a star character (\*) is added at
  the end of the searched word** (e.g. Ada\* in order to search for
  users having words starting with "ada" in the searchable fields); if
  the user wants to perform partial search for each searched word then
  an AND or an OR operator must be used between partial words (e.g. Jo\*
  AND Sm\* in order to search for users having words starting with "Jo"
  and words starting with "Sm"; Jo\* OR Ad\* in order to search for
  users having words starting with "Jo" or words starting with "Ad")

> Once the desired user is displayed, the administrator may change any
> of the fields or group membership, as explained in the section
> [4.6.1.1](#creating-users) "*[Creating users](#creating-users)"* by
> just pressing EDIT (see [Figure 57](#_bookmark89)). For security
> reasons, the users\' passwords are not displayed.

#### ![](media/image200.png){width="0.540825678040245in" height="0.10738626421697288in"} Deleting users

> To delete a user, the administrator can use the "Search" field on the
> left-hand side of the screen to search for a particular user (see).
> The searching mechanism is described in the previous section (see
> section [4.6.1.2](#modifying-users))

![](media/image203.png)

> []{#_bookmark94 .anchor}Figure 60: IAM: Users: Deleting user
>
> Once the correct user that should be deleted is selected, the
> administrator presses DELETE. The administrator can press YES in the
> pop-up window to confirm the user deletion, or NO to abort the
> operation (see [Figure 60](#_bookmark94)).

#### ![](media/image205.png){width="0.3841119860017498in" height="0.10738626421697288in"} IAM: Groups

![](media/image208.png)

> []{#_bookmark95 .anchor}Figure 61: IAM: Groups
>
> As a general practice, not only relevant to RINA application, is
> advisable to use groups to assign permissions, instead of assigning
> rights individually to users. This concept targets the ease of
> management when users join, change position in, or leave the default
> organisation selected for the specific installation. A practical
> example may be found in the "EESSI -- RINA Identity and Access
> Management (IAM)" guide, in the sub-section "*Process owner example*"
> (under section \"*Illustrative scenario example -- external filtering
> rules*\").
>
> The default group structure is relatively simple. The administrator
> can opt it to be as complex and granular as needed, but it is
> recommended to keep a logical and simple structure, for easy
> management and troubleshooting in the future as the default
> organisation evolves.
>
> In the **Groups** screen (see [Figure 61](#_bookmark95)), the
> administrator can perform group administration tasks, such as ADD
> GROUP, EDIT, or DELETE. Once the selected group\'s structure is in
> place, the administrator can assign users to groups (memberships) and
> then assign authorisation policies to groups and resources. Assigning
> authorisation policies will be covered later in this document (section
> [4.7](#authorisation)).

#### ![](media/image210.png){width="0.5258245844269467in" height="0.10738626421697288in"} Creating groups

![](media/image213.png)

> []{#_bookmark97 .anchor}Figure 62: IAM: Add new group
>
> While creating a group, by pressing ADD GROUP, the administrator needs
> to decide its position/location in the group hierarchy, which means it
> is needed to decide first which will be its parent group. For this
> example, it is assumed that the group will be located in **EESSI
> Members**. To select a group (resulting to navigating into that
> group), the administrator may press on the drop-down list in **Parent
> Group** (see [Figure 63](#_bookmark98)).

![](media/image217.png)

> []{#_bookmark98 .anchor}Figure 63: IAM: New Group configuration
>
> Once the administrator navigates to the **Group** where he/she wants
> to create the new subgroup (the administrator may see the path in the
> section **Parent Group**), types a **Name** and **Description**
> (description is not mandatory but recommended) and also select if this
> new Group is an **Organisation Unit** (OU). An OU is intended to be a
> 'super-group'; for instance, it may be used to represent/cover a
> branch (in a multi-branch environment). When done, press SAVE to
> create the group (see [Figure 63](#_bookmark98)).

#### ![](media/image219.png){width="0.5374759405074365in" height="0.10738626421697288in"} Modifying groups

![](media/image223.png)

> []{#_bookmark99 .anchor}Figure 64: IAM: Modify Groups
>
> When there are many groups created in the system the administrator may
> use the search bar too look for the group he/she wants to modify. The
> search applies after the user presses the search button
> (![](media/image199.png){width="0.20069335083114612in"
> height="0.20812445319335082in"}).
>
> The search mechanism for groups is different than the users' search
> mechanism: The groups search is performed on the client (html search)
> following the initial call that brings all groups from RINA Server.
> The Users' search mechanism is always performed on the server side of
> RINA (each search will transmit the free-text search to the server and
> will bring a new result set from there that will be shown to the
> user).
>
> Once the group is displayed, the administrator can press EDIT to
> change its name, add/change a description, and change whether it is an
> **Organisation Unit** or not. Once the administrator is satisfied with
> the changes, he/she can press SAVE to update the group (see [Figure
> 64](#_bookmark99)).

#### ![](media/image226.png){width="0.540825678040245in" height="0.10738626421697288in"} Deleting groups

![](media/image229.png)

> []{#_bookmark100 .anchor}Figure 65: IAM: Deleting Groups
>
> The administrator can select the group to be deleted, by using the
> search bar.
>
> Once the group is displayed in the screen, the administrator can press
> DELETE to delete it (see [Figure 65](#_bookmark100)).
>
> Following the above step, a popup window appears where the
> administrator can confirm the group deletion by pressing YES, or abort
> the operation by pressing NO (see [Figure 65](#_bookmark100)).
>
> Please note that deleting a group is possible only if the group is
> empty (not having users attached).

#### ![](media/image231.png){width="0.38246719160104986in" height="0.10738626421697288in"} IAM: LDAP Configuration

![](media/image234.png)

> []{#_bookmark101 .anchor}Figure 66: IAM: LDAP Configuration
>
> The *"LDAP Configuration"* screen is the place where the administrator
> can add the configuration for synchronising RINA users and groups (for
> a specific Tenant) with the structure residing at an LDAP server (see
> [Figure 66](#_bookmark101)).

### Configuration

> To set up LDAP sync, the administrator needs to configure the
> connection parameters:

- *[User]{.underline}*: - the user account used to authenticate to the
  LDAP server (for example,
  \"cn=install,ou=people,dc=testdomain,dc=com\")

- *[Password]{.underline}:* the password for *auth_user_dn auth_ssl* --
  define whether SSL is used for authentication. Accepted values: *true*
  or *false*;

- *[Url]{.underline}:* FQDN/ IP Address and port of the LDAP server to
  synchronise from

- *[Security Authentication]{.underline}:* simple (specifies the
  authentication mechanism to use. Possible values "simple", "none",
  "sasl_mech", etc)

- *[LDAP User Search Base]{.underline}:* users_provider_dn for example,
  \"OU=people, DC=testdomain, DC=com\");

- *[LDAP Group Search Base:]{.underline}* users_provider_dn, for
  example, \"OU=people, DC=testdomain, DC=com\"

- *[User Search String:]{.underline}* LDAP query to filter user. For
  example:\"(&(objectClass=inetOrgPerson)(!(uid=install)))\"

- *[Group Search String]{.underline}:* Group filtering. For example,
  \"(objectclass=posixGroup)\"

> *groups_mapping* -- Mapping of the groups \"group_name=cn
> description=description\"

### Group Mappings

> The following Group attributes can be mapped to LDAP values, if they
> are available:

- *[LDAP Unique Identifier:]{.underline}* LDAP attribute, which is
  unique and used to identify the group, in most LDAP implementations is
  "distinguishedName" or "sAMAccountName"

- *[Group name]{.underline}*: the full qualified name of the group

- *[Display Name]{.underline}*: the short name of the group

- *[Description]{.underline}*: the description of group from LDAP

- *[Is group Organisation Unit]{.underline}*: Boolean to declare if the
  given entity is an organisation unit

- *[Is group reassigned]{.underline}*: Boolean to check if the given
  entity needs reassignment

- *[Parent group Id]{.underline}*: the id of the parent Group

- *[Group's path]{.underline}*: the full path of the Group to root unit

- *[Creation Date]{.underline}*: the Group creation date

- *[Last Update]{.underline}*: the last update of the Group

- *[Groups members]{.underline}*: Attribute of a group which maps
  members of this group (users). If it is set, members of this group
  will be synchronised, even if they are not looked up by user search
  string

### User Mappings

> Following attributes of user can be mapped to LDAP values, if they are
> available:

- *[LDAP Unique Identifier:]{.underline}* LDAP attribute which is unique
  and used to identify the group, in most LDAP implementations is
  "distinguishedName" or "sAMAccountName"

- *[Username]{.underline}*: the full qualified User name

- *[First Name]{.underline}*: the User's first name

- *[Last Name]{.underline}*: the User's last name

- *[Email]{.underline}*: the User's email

- *[Phone Number]{.underline}*: the User's phone number

- *[Is enabled]{.underline}*: Boolean to declare if the User is enabled
  or not

- *[Is administrator]{.underline}*: Boolean to declare if the User is
  the administrator or not

- *[Creation Date]{.underline}*: the User creation date in the system

- *[Last update]{.underline}*: the last update of the User info

- *[User's groups]{.underline}*: the property mapping to LDAP Groups to
  which the User belongs

- *[User's role]{.underline}*: the appropriate selection from a User's
  roles list (see [Figure 66](#_bookmark101))

> Once all the parameters have been set, the administrator can press
> SYNCHRONISE LDAP button to synchronise the content with one at an LDAP
> server.
>
> The Group & User Mapping between the RINA internal authentication DB
> and external LDAP provider fields, follows the LDAP Synchronisation.
> The administrator can define the most appropriate mapping for the
> selected institution (Tenant).
>
> Detailed information concerning LDAP synchronisation and
> Authentication is provided in
>
> "ANNEX I -- RINA LDAP Synchronisation and Authentication".

#### ![](media/image236.png){width="0.38582239720034994in" height="0.10738626421697288in"} IAM: LDAP Authentication

> After successful synchronisation with LDAP server, it is possible to
> log in to system with LDAP credentials. Usernames for users which
> comes from LDAP synchronisation are created using a pattern:
> "tenantId\\LDAPusername". After configuring CAS server to authenticate
> with LDAP server, users entering tenantId\\LDAPusername username and
> their LDAP password can log in to application.
>
> To enable LDAP authentication following entries should be added to
> cas.properties file:
>
> *cas.authn.ldap\[0\].ldapUrl: URL of LDAP server*
>
> *cas.authn.ldap\[0\].useSsl= is SSL used, for example "false"*
>
> *cas.authn.ldap\[0\].allowMultipleDns= should multiple DNS be allowed,
> for example "false" cas.authn.ldap\[0\].baseDn: users_provider_dn, for
> example, \"OU=people, DC=testdomain, DC=com\"*
>
> *cas.authn.ldap\[0\].userFilter= LDAP query to look up user objects,
> for example*
>
> *"(&(uid={user})(objectClass=people))"*
>
> *cas.authn.ldap\[0\].subtreeSearch= should subtree search be possible,
> for example "false" cas.authn.ldap\[0\].bindDn= username used to
> connect to LDAP server, for example,
> \"cn=install,ou=people,dc=testdomain,dc=com\"*
>
> *cas.authn.ldap\[0\].bindCredential= password used to connect to LDAP
> server*
>
> It is possible to configure more than one LDAP servers to authenticate
> with. For the next LDAP server entries should be added with next
> ordinal number for index in square parenthesis, for example
> "cas.authn.ldap\[1\].ldapUrl", etc.
>
> CAS configuration for enabling LDAP authentication is described in
> official CAS server
> documentation:*"[[https://apereo.github.io/cas/5.1.x/installation/Configuration-]{.underline}](https://apereo.github.io/cas/5.1.x/installation/Configuration-Properties.html)
> [[Properties.html]{.underline}](https://apereo.github.io/cas/5.1.x/installation/Configuration-Properties.html)"*

## Authorisation

> Authorisation is the function of specifying rights/privileges to
> perform specific actions on EESSI Cases. Formally, Authorisation is
> the definition of specific access policies that correlate the three
> different policy parts: (i) the conditions that should be fulfilled,
> (ii) the actions that can be performed and (iii) the actors that
> perform the actions.
>
> In the case of multi-tenancy, the authorisation settings are tenant
> dependant and must be defined per tenant.
>
> Firstly, the administrator selects the appropriate tenant from the
> drop down list on the choice **Select tenant** appeared on the top
> right side of the screen (See [Figure 67](#_bookmark104)). If there is
> only one (1) tenant, the system just displays the default value. See
> also the relevant ANNEX II (RINA Assignment Policies -- Clarifications
> and Examples)

![](media/image238.jpeg)

> []{#_bookmark104 .anchor}Figure 67: Authorisation: Select Tenant
>
> ![](media/image240.jpeg)
>
> []{#_bookmark105 .anchor}Figure 68: Authorisation: Assignment Policies
>
> The item "*Authorisation"* contains two subitems: (i) the "*Assignment
> Policies"* where the policies for the automatic assignments are
> created and configured, (ii) the "*Process Assignments"* where the
> created policies are mapped with the Sectors, Process Types (BUCs),
> Application Roles and RINA Actors (see [Figure 68](#_bookmark105)).

#### ![](media/image241.png){width="0.37911089238845147in" height="0.1039676290463692in"} Authorisation: Assignment Policies

> **Definition:** An Authorisation Policy is a set of rules that
> correlates the Case related conditions (Application role, Sector,
> Application Type/BUC), the specific actions that described by RINA
> actors/roles and can be performed on the Cases (create, assign, open,
> view, etc) and finally, the users/groups that are authorised to
> perform the specific actions.
>
> The "*Assignment Policies"* screen contains a detailed list of the
> available policies and policy groups, at the top is located the policy
> searching function.

#### ![](media/image242.png){width="0.5258245844269467in" height="0.1039676290463692in"} Policy types and Policy Groups

> Taking into consideration the permissions to perform actions, based on
> roles, on created cases, two different policy types are defined in
> RINA application:

- The **Creator Policy** type that defines the rules according to which
  the new Case creation right is granted to specific user(s)/group(s);

- The **Case Policy** that defines the conditions under which the Case
  operations (except the Case Creation) reflected by the selected RINA
  actors/roles can be performed by the listed user(s) and/or group(s) on
  received Cases or Cases created after the activation of the **Case
  Policy**.

> RINA provides also a policy grouping option (**Policy Group**) that
> can be considered as a policy container and allows the easier
> management of the policies. For example, instead of assigning five
> policies to each business sector or case, the administrator may create
> a **Policy Group** that contains the five policies and then only
> assign the **Policy Group** to each user group (section
> [4.7.2](#authorisation-process-assignments)). The **Policy Group**
> option should not be considered as a policy type.
>
> By default, RINA installation includes three pre-defined policies as
> described below (one default policy per policy type):

- The built-in policies, the *[creator policy]{.underline}* and the
  *[supervisor policy]{.underline}*:

  - *"Creator policy"* provides the permission to create new Cases in
    RINA application to specific User(s)/Group(s);

  - *"Supervisor policy"* (as type **Case Policy**) assigns, by default
    all the cases to the roles: *supervisor* and *Authorised-clerk.*

- The built-in policy group "*dev policy*" (as type **Policy Group**)
  that groups the built- in policies "*creator policy*" and "*supervisor
  policy*".

> By default, the "*dev policy"* is assigned to all process types in all
> sectors (more information about this topic is provided in the section
> [4.7.2](#authorisation-process-assignments)).

#### ![](media/image243.png){width="0.5374759405074365in" height="0.10579505686789151in"} Managing Policies

> In this section, it is described how the administrator can handle the
> policies by providing the appropriate guidelines to create new
> policies, to edit and/or to delete the existing ones.

1.  []{#_bookmark107 .anchor}Creating policies and policy groups

> In order to create a policy (see [Figure 69](#_bookmark108)), the
> administrator should follow the next steps:

- to create a **Case Policy**, **Creator Policy**, or **Policy Group**

- to provide the necessary policy information (name, description,
  colour)

- to configure the relevant rules that define when a policy is
  activated.

> During the first step, the administrator selects from top right side
> part of the screen **Assignment Policies**, the most appropriate
> selection between the available ones NEW POLICY, NEW CREATOR POLICY
> and NEW POLICY GROUP links, depending on the required **Case Policy**,
> **Creator Policy**, or **Policy Group**.
>
> ![](media/image246.png)
>
> []{#_bookmark108 .anchor}Figure 69: Authorisation: New policy
> Management
>
> After pressing NEW CREATOR POLICY link (see [Figure
> 69](#_bookmark108)) the New Creator Policy form is displayed (see
> [Figure 70](#_bookmark109)), and the administrator should provide the
> values for **Name** and **Description** fields. A relevant **Name**
> should be given to the creator policy ("Pensions Creator policy"
> instead of "Policy 1").
>
> The **Description** field is optional, but it is strongly recommended
> to populate it. It is a good practice to use something that makes a
> long-term sense and can be valuable when the administrator reviews the
> policies.
>
> The administrator may also pick a **Colour** which may provide visual
> indications in the section Process assignments.
>
> Once the administrator picks a name and description, he/she may begin
> adding rules. Every rule contains a set of conditions and a set of
> actions triggered by the conditions and applied by specific
> user(s)/group(s).
>
> Within the section **When these conditions are met**, the option
> Process Owner from the section Application Role is preselected.
>
> For **Sector**, the administrator may pick one, more or even all
> sectors available. For this
>
> case, the sector "Pension" is the only one selected.
>
> For **Process Type**, one or more (or even all) Processes may be
> selected.
>
> In the next sections, a detailed description of the three Policy
> creation procedures is given by describing the specific parameters
> that should be configured in each case. The three different policy
> creation procedures correspond to the three policy types that have
> already been described.
>
> [**New Creator policy** (Policy type: *"Creator Policy"*)]{.underline}

![](media/image252.png)

> []{#_bookmark109 .anchor}Figure 70: Authorisation: New Creator Policy
>
> In general, the **Rule** area can be separated into two sections (see
> [Figure 70](#_bookmark109)):

- The Section **A**, where the conditions (i.e., Application Role,
  Sector(s) and Process Type(s)) of a specific policy rule are defined;

- The Section **B**, where the User(s)/Group(s) that can perform the
  Case action (Case Creation action and Creator Actor for the specific
  example given on the above figure) are defined when the conditions of
  section A are fulfilled.

> Therefore, the provided logic can be expressed by the following
> statement:
>
> *When the conditions of Section A are met, THEN the actions defined by
> the Actors listed in "Assign to Actors" choice, can be performed by
> the selected Groups and/or Users presented on Section B*
>
> Once the administrator defines the conditions, the desired actions
> should be mentioned (by selecting the relevant actors). Since this
> configuration is related to "*Creator Policy*", the only action option
> for assignment is preselected as **Creator** (other options are greyed
> out).
>
> In the section B and at the choice **These users and groups** the
> administrator should add all the groups and users that need to be able
> to create cases in the Pension Sector.
>
> [**New Policy** (Policy Type: *"Case Policy")*]{.underline}

![](media/image256.png){width="6.300600393700788in"
height="3.2708333333333335in"}

> []{#_bookmark110 .anchor}Figure 71: Authorisation: New Policy
>
> After pressing NEW POLICY link, the New Policy form is displayed (see
> [Figure 71](#_bookmark110)), there is a need to provide values for
> **Name** and **Description** fields. A relevant **Name** can be given
> to the policy (like "Pensions Case Policy"). The **Description** field
> is optional, but it is strongly recommended to populate it.
>
> It is a good practice to use something that will make sense in longer
> term (6 months or three years from the moment of the creation) when
> the administrator is reviewing the policies. The administrator may
> also pick a **Colour**, which may provide visual indications in the
> section Process assignments.
>
> Once the administrator picks a name and description, he/she may begin
> adding rules. Every rule contains a set of conditions and a set of
> actions triggered by the conditions.
>
> Within the section **When these conditions are met***,* the
> administrator can:

- select the Application Role (Process Owner, Counterparty or Any) by
  clicking on one of the selections of the field **Application Role
  In**;

- specify the **Sector** of the Policy. The administrator may pick one,
  more or even all the available sectors. For the example on the
  previous figure, the sector "Pension" is selected;

- also select the **Process Type** *(*BUC Type) by picking one or more
  BUCs out of the provided BUC list (Check all/Uncheck All options are
  available).

> Once the conditions have been defined, the administrator may select
> the desired action. Since this is a policy of "*Case Policy*" type,
> the administrator picks one or more roles (for example,
> Authorized_Clerk and Supervisor) and then selects the relevant User(s)
> and/or Group(s).
>
> Analytically, the administrator can:

- choose specific roles to assign the policy through the choice **Assign
  To Actors**. One or more roles can be selected (through the roles
  assignments the administrator defines the permitted actions following
  the Roles/Actions table given in *[Table 2:](#_bookmark86) [RINA
  Roles - Actions Matrix](#_bookmark86)*;

- finally select the group(s) and/or the user(s) of the groups by
  clicking on them and then pressing ADD. The administrator may add
  groups and/or users that should perform operations on the Cases in the
  selected Sector(s).

> It is valuable to notice that the specific way of defining the policy
> conditions is **Application Role** dependant (see [Figure
> 72](#_bookmark111)). For example, the group(s) of the Case Creator
> should be defined when using **Process Owner** and the details of the
> Owner Country and Owner Organisation could be provided when the
> **Counter Party** choice is selected.
>
> When the rules definition has been completed, the administrator can
> press SAVE for the system to save the policy.

![](media/image259.png)

> []{#_bookmark111 .anchor}Figure 72: Conditions, Actors and
> Users/Groups Role dependent selections
>
> For NEW POLICY and NEW CREATOR POLICY choices, the administrator can
> create as many rules as needed by using the selection NEW RULE and
> eventually, he can remove any rule by clicking on the appropriate
> button REMOVE RULE.
>
> If more than one rule has been created, RINA applies these rules
> sequentially until the first successful rule (i.e. the rule that
> completely fulfils the criteria and conditions that have been set).
> Therefore, the order of the rules in the provided list defines the
> priority in which RINA processes the rules. The administrator can
> enforce a specific rule by changing their order on the list. The order
> change can be done by using the selections buttons MOVE UP and MOVE
> DOWN ([Figure 73](#_bookmark112)).
>
> The legend AND STOP PROCESSING MORE RULES, has been located at the end
> of each rule to clearly indicate that RINA stops processing the rules
> queue sequentially if the specific rule fulfils completely the
> conditions.

![](media/image262.png)

> []{#_bookmark112 .anchor}Figure 73: Authorisation: New Rule, Remove
> Rule and change rule's priority
>
> [**New Policy Group** (Policy type: *"Policy Group")*]{.underline}
>
> After pressing NEW POLICY GROUP link (see [Figure 74](#_bookmark113)),
> there is a need to provide values for **Name** and **Description**
> fields. A relevant **Name** can be given to the policy group (like
> "Pensions Policy Group"). The **Description** field is optional, but
> it is strongly recommended to populate it. It is a good practice to
> use something that will make sense in longer term (6 months or three
> years from the moment of the creation) when the administrator is
> reviewing the policies. The administrator may also pick a **Colour**,
> which may provide visual indications in the section Process
> assignments.

![](media/image265.png)

> []{#_bookmark113 .anchor}Figure 74: Authorisation: New Policy Group
>
> Once the administrator picks a name and description, he/she may also
> begin to add existing policies. The administrator can add other
> "*Policy Groups" too*, but he/she should be careful to avoid extensive
> convoluted nesting, which may complicate the
>
> troubleshooting procedure. The administrator can press in the field
> EXISTING POLICY to select from the existing policies and policy
> groups. If the administrator needs to remove a policy from the policy
> group, he/she can just uncheck it by clicking on the icon at the left
> of each policy.
>
> When all the policies have been added (and policy groups), the
> administrator presses on SAVE button for the system to finalise the
> operation (see [Figure 74](#_bookmark113)).

2.  Changing/deleting existing policies and policy groups

> To change a policy or policy group, the administrator simply needs to
> query for it by using the SEARCH field (in case the administrator has
> a very long list of policies and policy groups) and then click on EDIT
> on the individual entry. When the changes are done, the administrator
> can press SAVE button for the system to update the relevant policy or
> policy group (see [Figure 75](#_bookmark114)).

![](media/image269.png)

> []{#_bookmark114 .anchor}Figure 75: Authorisation: Changing/Deleting
> Policies
>
> To delete a policy or policy group, the administrator simply needs to
> look for it (like above mentioned) and press on the DELETE button on
> the right side (see [Figure 75](#_bookmark114)). The administrator can
> press YES in the pop-up window to confirm the deletion, or NO to abort
> the operation (see [Figure 76](#_bookmark115)).

![](media/image273.png)

> []{#_bookmark115 .anchor}Figure 76: Policy Deletion Confirmation

#### ![](media/image275.png){width="0.3841119860017498in" height="0.10579505686789151in"} Authorisation: Process Assignments

![Graphical user interface, application, website Description
automatically
generated](media/image276.jpeg){width="6.2981113298337705in"
height="2.1921872265966753in"}

> []{#_bookmark117 .anchor}Figure 77: Authorisation: Process Assignments
> overview without assigned policies
>
> The screen *"Process Assignments"* contains a view of all the
> **Sectors**, **Processes***,* **Application Roles***,* **Actors** and
> all policies assigned at each level. Next to each Sector/
> Process/Application Role/Actors the administrator may notice the
> colour-code of the policies (or policy groups) linked to them.
>
> The administrator may assign more than one policy to a Sector or
> Process. The administrator may do this manually or automatically.

#### ![](media/image277.png){width="0.5258245844269467in" height="0.10579505686789151in"} Manual Process Assignment

![Graphical user interface, application Description automatically
generated](media/image278.jpeg){width="6.330568678915135in"
height="2.7125in"}

> []{#_bookmark118 .anchor}Figure 78: Authorisation: Process Assignments
> assign additional policies
>
> To get more details about the policies or policy groups assigned to a
> Sector, Process, Application Role or Actor, the administrator can
> press the appropriate section to retrieve the list of **Assigned
> Policies** (see [Figure 78](#_bookmark118))*.* If the administrator
> wants to add more, he/she can press within the field POLICY or POLICY
> GROUP query textbox to get the list of all available policies and then
> select the appropriate policy(ies) or policy group(s). When all
> policies or policy groups have been assigned, he can press SAVE button
> for the system to finalise the operation. In the screenshot above, the
> **Pensions Policy Group** (created in the section
> [4.7.1.2.1](#_bookmark107)) gets assigned to the Pension Sector.
>
> As the policy group was linked at the Sector level, it will apply to
> all its nested containers (all Processes, all Application Roles and
> Actors -- see [Figure 79](#_bookmark119)).
>
> ![](media/image280.jpeg)
>
> []{#_bookmark119 .anchor}Figure 79: Authorisation: Process Assignments
> validate assignment
>
> The administrator may go as granular and complex as needed, but it is
> recommended to keep the structure of groups and policies as simple as
> possible as a best practice, to have a clear view of the installed
> environment and easy troubleshooting (whenever applicable).

![Graphical user interface, text, application Description automatically
generated](media/image281.jpeg){width="6.2758628608923885in"
height="2.6878116797900264in"}

> []{#_bookmark120 .anchor}Figure 80: Authorisation: Process Assignments
> -- Assigned Policies management
>
> To remove a linked policy or policy group, the administrator can press
> the container (Sector, Process etc.) to retrieve the assigned policies
> and policy groups (see [Figure 80](#_bookmark120)). Then, from the
> list he/she can uncheck the corresponding the policy (or policy group)
> required to be removed. When done, he/she can press SAVE button for
> the system to update the list.

#### ![](media/image282.png){width="0.5374759405074365in" height="0.10579505686789151in"} Bulk Process Assignment

> If a RINA institution has already been configured with a Process
> Assignment and access policies, the administrator may export the
> configuration file (only for backup purposes for the same institution
> (tenant) on the same server and not to be used for other institutions
> (tenants) even on the same server) by clicking on EXPORT POLICIES AND
> ASSIGNMENTS button (see [Figure 81](#_bookmark121)).
>
> ![Graphical user interface, application Description automatically
> generated](media/image283.jpeg){width="6.227608267716535in"
> height="1.874478346456693in"}
>
> []{#_bookmark121 .anchor}Figure 81: Authorisation: Process Assignments
> -- Export/Import
>
> To import a Process Assignment configuration file, the administrator
> can press the relevant location on the upper-right sections of the
> screen, namely the IMPORT POLICIES AND ASSIGNMENTS button (see [Figure
> 81](#_bookmark121)).
>
> In terms of exporting option, following the pressing of the button,
> RINA generates a JSON file named *Process Definition Assignments*
> which holds the policies and process assignments. This file can be
> opened by the administrator or saved at the proper location.
>
> To import, following the pressing of the IMPORT POLICIES AND
> ASSIGNMENTS button, the administrator can select the JSON file
> previously exported (see [Figure 82](#_bookmark122)). A small progress
> bar will appear. It is important to notice that once the import is
> complete, the existing (if any) process assignments will be replaced
> by the configuration from the selected JSON file.
>
> It may be a good measure to export a (backup) file of the existing
> process assignment and policies structure before importing operation
> (for later review or to avoid troubleshooting time-consuming errors).

![Graphical user interface, application Description automatically
generated](media/image284.jpeg){width="6.3327657480314965in"
height="2.118333333333333in"}

> []{#_bookmark122 .anchor}Figure 82: Authorisation: Process
> Assignments - Import Policies and Assignments

## ![](media/image287.png)Notification Centre

> []{#_bookmark124 .anchor}Figure 83: Notification Centre
>
> The *"Notification Centre"* item covers all aspects of case
> notification specific for administration activity. RINA automatically
> generates notifications to inform the system administrator about
> business exceptions and errors in the SED delivery process.
>
> For RINA Administrators the following features, related to
> notifications, are available (see [Figure 83](#_bookmark124)):

- Settings covering the notifications to be shown to the users (Clerks)
  on RINA Portal Notification Centre;

- Settings covering the notifications to be shown to the administrators
  on RINA Administrator Portal Notification Centre;

- Configuration of the retention and notification periods for
  administrators of RINA;

- Configuration of the generation NIE events per Notification type.

#### ![](media/image289.png){width="0.37911089238845147in" height="0.10738626421697288in"} Notification Centre: Notification Settings

> In *"Notification Settings"* the RINA administrator can set the rules
> related to which notifications will be visible for end users and
> administrator. The administrator can also configure the retention and
> notification periods for the Business Exceptions (see
> [Figure](#_bookmark124) [83](#_bookmark124)). This means that the
> administrator can configure when the Business Exception can be
> automatically sent by the RINA application without any manual
> intervention by administrator in certain time of period, (see [Figure
> 84](#_bookmark126)).

![](media/image292.png)

> []{#_bookmark126 .anchor}Figure 84: Notification Centre: Configuration
> Management
>
> The administrator can configure the following certain artefacts to be
> visible from the business users (Clerks) and from the administrator
> account:
>
> ![](media/image295.jpeg)
>
> []{#_bookmark127 .anchor}Figure 85: Notification Centre: Values to be
> configured
>
> The administrator may configure different retention settings depending
> on criteria such as Receiving a SED for a missing Case, SED Update for
> a non-existing SED etc. (see [Figure](#_bookmark127)
> [85](#_bookmark127)).
>
> Specifically, for the Business Exceptions the administrator except
> from defining whether the Clerks and/or the administrator will receive
> Notifications for the Business Exceptions, he/she can also configure
> the retention and notification periods by selecting the appropriate
> values in the given edit boxes ([Figure 85](#_bookmark127)).
>
> **Business Exception Retention period** (in days) is the period of
> time that needs to elapse since the appearance of the relevant
> messages under the *"Business Exceptions:Pending Message"* screen.
> Upon the expiration of the Retention period, RINA automatically
> generates Business Exceptions for the respective incoming Pending
> Messages (see [Figure 104](#_bookmark154)) and the exception is moved
> from Pending Messages to Business Exceptions.
>
> **Business Exception Notification period** (in days) is the period
> that needs to elapse since the appearance of the relevant messages
> under the *"Business Exceptions: Pending Message"* screen (see [Figure
> 103](#_bookmark153)). Upon this expiration of notification period,
> RINA automatically generates the respective Notifications visible in
> the Notification Centres.

![Graphical user interface, application, table Description automatically
generated](media/image296.png){width="6.343258967629047in"
height="3.0387489063867017in"}

> []{#_bookmark128 .anchor}Figure 86: Retention and Notification Period
> definition
>
> Initially the administrator selects the relevant Notification types
> and configures the appropriate Retention and Notifications periods.
> Then the administrator presses the SAVE button to ensure that new
> configuration and selections are saved. The administrator may
> configure also the NIE event generation for all the above-mentioned
> Notification types (see [Figure 86](#_bookmark128)).
>
> According to approved business specifications the Default values for
> **Retention Period**
>
> and **Notification Period** for the Business Exceptions given on the
> Table below:

+-------------------------+------------------+------------------+
| > **Business            | > **Retention    | > **Notification |
| > Exceptions**          | > Period (in     | > Period (in     |
|                         | > days)**        | > days)**        |
+=========================+:================:+:================:+
| > **Attachment failed   | 0                | > 0              |
| > antimalware           |                  |                  |
| > checking**            |                  |                  |
+-------------------------+------------------+------------------+
| > **Case Forwarded**    | 1                | > 0              |
+-------------------------+------------------+------------------+
| > **Case Closed**       | 1                | > 0              |
+-------------------------+------------------+------------------+
| > **Unknown Cause**     | 1                | > 0              |
+-------------------------+------------------+------------------+
| > **Invalid Business    | 0                | > 0              |
| > Signature**           |                  |                  |
+-------------------------+------------------+------------------+
| > **SED in Wrong        | 1                | > 0              |
| > Sequence**            |                  |                  |
+-------------------------+------------------+------------------+
| > **SED update without  | 1                | > 0              |
| > Create**              |                  |                  |
+-------------------------+------------------+------------------+
| > **Case Removed**      | 1                | > 0              |
+-------------------------+------------------+------------------+
| > **Case Missing**      | 1                | > 0              |
+-------------------------+------------------+------------------+

> Table 3: Retention & Notification Periods default values

#### ![](media/image297.png){width="0.3841119860017498in" height="0.10738626421697288in"} Notification Centre: Notifications

> The notification Centre for administrators offers a similar view that
> any user can access through the User Portal. The only difference is
> that the administrator does not have access to the Cases of the
> relevant notifications. RINA automatically generates notifications to
> inform about updates and changes within the existing and about new
> cases. Case notifications are divided into three category groups (or
> notification **severities**) in RINA:

+-------------------------------+---------------------------------------------------------------+
| - Errors:                     | > ![Graphical user interface, application Description         |
|                               | > automatically                                               |
|   - A duplicate SED (update)  | > generated](media/image298.png){width="2.7999989063867017in" |
|     has arrived               | > height="6.583333333333333in"}                               |
|                               |                                                               |
|   - A duplicate message       |                                                               |
|     arrived                   |                                                               |
|                               |                                                               |
|   - A wrong SED (update) has  |                                                               |
|     arrived                   |                                                               |
|                               |                                                               |
|   - Archiving Case Exception; |                                                               |
|                               |                                                               |
|   - Archiving Case Problem;   |                                                               |
|                               |                                                               |
|   - Attachment failed         |                                                               |
|     antimalware checking;     |                                                               |
|                               |                                                               |
|   - Case Assignment           |                                                               |
|     Exception;                |                                                               |
|                               |                                                               |
|   - Case Closed;              |                                                               |
|                               |                                                               |
|   - Case Forwarded;           |                                                               |
|                               |                                                               |
|   - Case Missing;             |                                                               |
|                               |                                                               |
|   - Case Removed;             |                                                               |
|                               |                                                               |
|   - Invalid Business          |                                                               |
|     Signature;                |                                                               |
|                               |                                                               |
|   - SED Failed to be          |                                                               |
|     Delivered;                |                                                               |
|                               |                                                               |
|   - SED Not Matching Case;    |                                                               |
|                               |                                                               |
|   - SED Update without        |                                                               |
|     Create;                   |                                                               |
|                               |                                                               |
|   - SED in a wrong Sequence;  |                                                               |
|                               |                                                               |
|   - Unknown Cause;            |                                                               |
|                               |                                                               |
| - Warnings:                   |                                                               |
|                               |                                                               |
|   - A New Case Arrived;       |                                                               |
|                               |                                                               |
|   - A New SED Arrived;        |                                                               |
|                               |                                                               |
|   - An Updated SED Arrived;   |                                                               |
|                               |                                                               |
|   - Approval for Sending      |                                                               |
|     Required for SED;         |                                                               |
|                               |                                                               |
|   - Request to Assign Case;   |                                                               |
|                               |                                                               |
|   - Request to Assign Case    |                                                               |
|     Accepted;                 |                                                               |
|                               |                                                               |
|   - Request to Assign Case    |                                                               |
|     Rejected;                 |                                                               |
|                               |                                                               |
|   - Your Alarm Expired.       |                                                               |
|                               |                                                               |
| - Information:                |                                                               |
|                               |                                                               |
|   - Case Assigned;            |                                                               |
|                               |                                                               |
|   - Case Automatically        |                                                               |
|     Closed;                   |                                                               |
|                               |                                                               |
|   - Case SEDs Automatically   |                                                               |
|     Sent to New Participant;  |                                                               |
|                               |                                                               |
|   - Case Unassigned;          |                                                               |
|                               |                                                               |
|   - SED Delivered.            |                                                               |
+===============================+===============================================================+

> There are four main triggers for case notifications:

- A case workflow action has been executed by a case participant;

- A request to assign a case to a certain user arrived, has been
  accepted or rejected;

- An error occurred;

- An internal alarm has expired.

> A detailed explanation on the RINA Notifications, describing the
> reason that generates each notification is given on "[**Table 4:
> Detailed explanations of RINA Notifications**](#_bookmark129)".

+---------------------------------+----------------------------------+
| > **Notification**              | > **Description / Explanation**  |
+=================================+==================================+
| > **Errors**                                                       |
+---------------------------------+----------------------------------+
| > A duplicate SED (update) has  | > An update SED has arrived from |
| > arrived                       | > Sender and cannot be processed |
|                                 | > because it is a duplicate and  |
|                                 | > an internal notification will  |
|                                 | > be generated. The received     |
|                                 | > version is a previous than or  |
|                                 | > the same compared to the       |
|                                 | > existing current one.          |
+---------------------------------+----------------------------------+
| > A duplicate message arrived   | > For every received message     |
|                                 | > with START/ STARTFORWARD Case  |
|                                 | > Action, if the case already    |
|                                 | > exists with the same           |
|                                 | > International Case ID then the |
|                                 | > case will not be created and   |
|                                 | > an internal notification will  |
|                                 | > be generated.                  |
+---------------------------------+----------------------------------+
| > A wrong SED (update) has      | > For every message with UPDATE  |
| > arrived                       | > Case Action, if CaseID         |
|                                 | > (international) and Document   |
|                                 | > Type are the not the same with |
|                                 | > the existing SED (which is     |
|                                 | > related to the update action)  |
|                                 | > then the SED will not be       |
|                                 | > updated, and an internal       |
|                                 | > notification will be           |
|                                 | > generated.                     |
+---------------------------------+----------------------------------+
| > Archiving Case Exception      | > It is generated in case of the |
|                                 | > system cannot archive a case   |
|                                 | > (because of error(s)).         |
+---------------------------------+----------------------------------+
| > Archiving Case Problem        | > Notification for clerk to      |
|                                 | > inform about exception during  |
|                                 | > the archiving process to       |
|                                 | > contact the administrator.     |
+---------------------------------+----------------------------------+
| > Attachment failed antimalware | > \[Business exception\] - for   |
| > checking                      | > failures in case of            |
|                                 | > antimalware checking.          |
+---------------------------------+----------------------------------+
| > Case Assignment Exception     | > The case could not be          |
|                                 | > assigned.                      |
+---------------------------------+----------------------------------+
| > Case Closed                   | > \[Business exception\] - when  |
|                                 | > a SED is received for a global |
|                                 | > closed Case.                   |
+---------------------------------+----------------------------------+
| > Case Forwarded                | > \[Business exception\] - when  |
|                                 | > a SED is received after the    |
|                                 | > case was forwarded to another  |
|                                 | > participant.                   |
+---------------------------------+----------------------------------+
| > Case Missing                  | > \[Business exception\] - when  |
|                                 | > a SED (except the starter) is  |
|                                 | > received for a missing case.   |
+---------------------------------+----------------------------------+
| > Case Removed                  | > \[Business exception\] - when  |
|                                 | > a SED is received after the    |
|                                 | > case was removed by receiving  |
|                                 | > a X006 SED (Remove             |
|                                 | > participant).                  |
+---------------------------------+----------------------------------+
| > Invalid Business Signature    | > \[Business exception\] - when  |
|                                 | > a message is received with an  |
|                                 | > invalid business signature.    |
+---------------------------------+----------------------------------+
| > SED Failed to be Delivered    | > In case of error at delivery   |
|                                 | > of a message.                  |
+---------------------------------+----------------------------------+
| > SED Not Matching Case         | > It is generated as information |
|                                 | > for presence of a business     |
|                                 | > exception.                     |
+---------------------------------+----------------------------------+

+---------------------------------+----------------------------------+
| > SED Update without Create     | > \[Business exception\] - when  |
|                                 | > an update is received for a    |
|                                 | > missing SED.                   |
+=================================+==================================+
| > SED in a wrong Sequence       | > \[Business exception\] - when  |
|                                 | > a SED is received in the wrong |
|                                 | > sequence (not like in the      |
|                                 | > BUC).                          |
+---------------------------------+----------------------------------+
| > Unknown Cause                 | > \[Business exception\] - other |
|                                 | > causes.                        |
+---------------------------------+----------------------------------+
| > **Warnings**                                                     |
+---------------------------------+----------------------------------+
| > A New Case Arrived            | > A new case has been created    |
|                                 | > (based on a starter SED).      |
+---------------------------------+----------------------------------+
| > A New SED Arrived             | > A new SED has been received.   |
+---------------------------------+----------------------------------+
| > An Updated SED Arrived.       | > An update (for a SED) has been |
|                                 | > received.                      |
+---------------------------------+----------------------------------+
| > Approval for Sending Required | > A sending required for SED has |
| > for SED                       | > been approved.                 |
+---------------------------------+----------------------------------+
| > Your Alarm Expired            | > When an alarm (related to the  |
|                                 | > user) has expired.             |
+---------------------------------+----------------------------------+
| > Request to Assign Case        | > It is a notification received  |
|                                 | > by a Supervisor for Assigning  |
|                                 | > a Case.                        |
+---------------------------------+----------------------------------+
| > Request to Assign Case        | > It is the positive answer for  |
| > Accepted                      | > a *Request to Assign Case*.    |
+---------------------------------+----------------------------------+
| > Request to Assign Case        | > It is the negative answer for  |
| > Rejected                      | > a Request to Assign Case.      |
+---------------------------------+----------------------------------+
| > **Information**               |                                  |
+---------------------------------+----------------------------------+
| > Case Unassigned               | > The case has been unassigned   |
|                                 | > (from the user(s)/ group(s)).  |
+---------------------------------+----------------------------------+
| > Case Assigned                 | > The case has been assigned (to |
|                                 | > the user(s)/ group(s)).        |
+---------------------------------+----------------------------------+
| > Case Automatically Closed     | > When a case has been           |
|                                 | > automatically closed (when     |
|                                 | > applicable).                   |
+---------------------------------+----------------------------------+
| > SED Delivered                 | > When a SED has been delivered  |
|                                 | > to the recipient(s).           |
+---------------------------------+----------------------------------+
| > Case SEDs Automatically Sent  | > In case of forward/ add new    |
| > to New Participant            | > participant, the existing      |
|                                 | > sending SED are automatically  |
|                                 | > sent to the new participant.   |
+---------------------------------+----------------------------------+

> []{#_bookmark129 .anchor}***Table 4: Detailed explanations of RINA
> Notifications***
>
> At any time, the administrator may click on any row to expand it and
> get more detailed information about the respective notification (see
> [Figure 87](#_bookmark130)).
>
> ![Graphical user interface, text, application, email Description
> automatically
> generated](media/image299.png){width="6.271975065616798in"
> height="2.446353893263342in"}
>
> []{#_bookmark130 .anchor}Figure 87: Opening the Notifications Centre

#### ![](media/image300.png){width="0.5258245844269467in" height="0.10738626421697288in"} Notifications Layout

![Graphical user interface, application Description automatically
generated](media/image301.png){width="6.298432852143482in"
height="3.3422911198600174in"}

> []{#_bookmark131 .anchor}Figure 88: Notifications centre: Layout
>
> The *"Notifications"* screen collects all case notifications (see
> [Figure 88](#_bookmark131)).

+-----+-------------------------------------------------------+
| > 1 | > The admin can filter, by using the checkboxes,      |
|     | > between Severities (**Error**,                      |
|     | >                                                     |
|     | > **Information** and **Warning**) and Recent (**Is   |
|     | > Read** and **Is Unread**).                          |
+=====+:======================================================+
| > 2 | > The main part of the *"Notifications"* screen is    |
|     | > used to display the individual notifications.       |
|     | >                                                     |
|     | > Total Records number is followed by an informative  |
|     | > icon that allows the user to see how many           |
|     | > notifications were sent in total (grouped per each  |
|     | > day) from the horizon of maximum 3 days             |
+-----+-------------------------------------------------------+
| > 3 | > The Search Area can be used to quickly access       |
|     | > specific notifications based on local case id.      |
+-----+-------------------------------------------------------+

+---------------------------------------------------------+-------------------------------------------------------+
| > 4                                                     | > Once the administrator uses the filter icon a bar   |
|                                                         | > is displayed a wide range of filters related to the |
|                                                         | > Notification Types. For more details, please refer  |
|                                                         | > to section [4.8.2.4](#filter-notifications).        |
+=========================================================+:======================================================+
| > ![](media/image302.jpeg){width="0.4499945319335083in" | > Landing on the page will be filtered only with the  |
| > height="0.46125in"}                                   | > notifications from the current date. The user will  |
|                                                         | > have the possibility to see notifications for       |
|                                                         | > maximum 3 days starting with a specified date (e.g. |
|                                                         | > if the user will select From Date = \'04/05/2021\'  |
|                                                         | > and select 1 day ahead followed by pressing search  |
|                                                         | > button then the notifications will be shown only    |
|                                                         | > for the 04/05/2021; if the users select 3 days      |
|                                                         | > ahead then the search will be performed between     |
|                                                         | >                                                     |
|                                                         | > 04/05/2021 and 06/05/2021 included)                 |
+---------------------------------------------------------+-------------------------------------------------------+

#### ![](media/image303.png){width="0.5374759405074365in" height="0.10738626421697288in"} View Notifications

> The *"Notifications"* screen presents notifications in chronological
> order. Individual notifications are displayed as rows in the
> Notifications Centre's list (see [Figure 89](#_bookmark132)). Each row
> begins with a checkbox that serves to select it and allows the
> administrator to mark it as Read or Unread by pressing MARK AS READ or
> MARK AS UNREAD, respectively. Next to the checkbox, the user will find
> an arrow that expands or contracts the notification details. Next
> column indicates the priority of the case that the notification refers
> to, then the notification type and at the end the notification
> description.

![Graphical user interface, text, application, email Description
automatically generated](media/image304.png){width="6.292833552055993in"
height="1.9761450131233596in"}

> []{#_bookmark132 .anchor}Figure 89: Notifications inside the
> Notifications Centre's list
>
> Clicking on the icon **\>** on an individual notification opens a
> detailed view, which provides information about the local case ID, the
> case type, and a list of assignees (see [Figure 90](#_bookmark133)).
> For alerts that require a reaction within a specified time frame, the
> detail view will also show by which date an action is required.
>
> ![](media/image307.png)
>
> []{#_bookmark133 .anchor}Figure 90: Detailed view of a notification

#### ![](media/image309.png){width="0.540825678040245in" height="0.10738626421697288in"} Notification Actions

> A notification can have these following states:

- UNREAD;

- READ.

> As it can be observed, a notification can be set to read state by
> clicking MARK AS READ button. Its status is also set to read
> automatically after opening it. The state can be reset to unread by
> clicking MARK AS UNREAD button in the notification actions.
>
> To help the administrator in managing own notifications, bulk
> operations can be performed. For example, administrator can indicate
> as read multiple notifications at once by first selecting the
> notifications and then executing a case action, (see [Figure
> 91](#_bookmark134)).

![](media/image311.png)

> []{#_bookmark134 .anchor}Figure 91: Bulk operation for marking
> multiple notifications as read at once

#### ![](media/image312.png){width="0.5391272965879265in" height="0.10738626421697288in"} Filter Notifications

> At the top right of the *"Notifications"* screen the administrator
> will find the filter icon, to be used to filter notifications by
> **Severity**, **Recent** status and notification **Type**. On the pop-
> up window, a wide spectrum of additional filters is available (see
> [Figure 92](#_bookmark136)).
>
> ![Graphical user interface, text, application, email Description
> automatically
> generated](media/image313.jpeg){width="6.277987751531058in"
> height="2.719582239720035in"}
>
> []{#_bookmark136 .anchor}Figure 92: Filter options inside the
> Notifications Centre

#### ![](media/image314.png){width="0.545825678040245in" height="0.10738626421697288in"} Clarification on Notifications Generation

> Especially for the "Case Assigned" and "Case Unassigned" notifications
> and the two different perspective they processed, the following
> rules/recommendations should be taken into account:
>
> Selections "Case Assigned" and "Case Unassigned" notifications on
> column \"Notification Centre for Clerk\":

- For the case of Case Creator and Case Assignees, the selection of
  "Case Assigned"

> notification initiates the Notification generation for all involved
> roles in the Case

- "Case Unassigned" notification is generated only after removing all
  the roles assigned to the clerk to whom the Case is assigned.

> Selections "Case Assigned" and "Case Unassigned" notifications on
> column \"Generate a NIE Event\":

- "Case Assigned" and "Case Unassigned": the selections should be
  applied to have the NIE event normally generated.

## Logs

> The *"Logs"* item contains the *"Audit Logs"* and *"Technical Logs"*
> subitems.

#### ![](media/image315.png){width="0.37911089238845147in" height="0.10738626421697288in"} Logs: Audit Logs

![Graphical user interface Description automatically
generated](media/image316.jpeg){width="6.273252405949257in"
height="1.8490616797900263in"}

> []{#_bookmark138 .anchor}Figure 93: Logs: Audit Logs: Layout

+-----+-------------------------------------------------------+
| > 1 | > The main screen of the *"Audit Logs"* on which the  |
|     | > selected Audit logs list is displayed for           |
|     | > troubleshooting and review purposes.                |
|     | >                                                     |
|     | > Total Records number is followed by an informative  |
|     | > icon that allows the user to see how many audit     |
|     | > logs were created in total (grouped per each day)   |
|     | > from the horizon of maximum 3 days                  |
+=====+:======================================================+
| > 2 | > The Navigation panel is to specify the interested   |
|     | > time interval of which the Audit logs should be     |
|     | > displayed: landing on the page will show only the   |
|     | > audit logs for the current date. The user will have |
|     | > the possibility to see audit logs for maximum 3     |
|     | > days starting with a specified date (e.g. if the    |
|     | > user will select From Date = \'04/05/2021\' and     |
|     | > select 1 day ahead followed by pressing search      |
|     | > button then the audit logs will be shown only for   |
|     | > the 04/05/2021; if the users select 3 days ahead    |
|     | > then the search will be performed between           |
|     | > 04/05/2021 and 06/05/2021 included); while search   |
|     | > is performed, the search and refresh buttons are    |
|     | > blocked until the results are presented to the      |
|     | > user.                                               |
+-----+-------------------------------------------------------+
| > 3 | > The Filtering panel on which the filtering options  |
|     | > concerning the different log types can be defined.  |
|     | > The administrator can modify the searching criteria |
|     | > by defining the Log Type (Success, Error and        |
|     | > Unauthorised), Action, Object, Participant,         |
|     | > Component, Category and Event Types and the         |
|     | > Participant Role                                    |
+-----+-------------------------------------------------------+
| > 4 | > The text-based searching functionality that can be  |
|     | > used to search by defining specific keywords as     |
|     | > searching criteria in order to limit the display    |
|     | > logs list to the required one.                      |
+-----+-------------------------------------------------------+

> "*Audit logs"* provide a graphical interface for troubleshooting or
> review purposes.
>
> There are several criteria that provide granular search options. In
> order to filter the provided list and locate more quickly the required
> information, the administrator can define the values of the following
> types that are used as searching criteria:

- *All Log type* with values: "Success", "Error", "Unauthorised";

- *Action type* with values: "Create", "Delete", "Update", "Execute",
  "Read";

- *Component Type* with values: "Security", "Notifications", "Search
  Definitions", "Business Messaging", "Cases", "Administration",
  "Documents", "Attachments", "Comments", and "Technical Messaging";

- *Participant Type* with values: "Organisation" and "Person";

- *Participant Role* with values: "Receiver", "Sender", and "Subject";

- *Object type* with values "Notification", "Credential", "Business
  Error", Business Acknowledge", "Alarm", "Comment", "Attachment",
  "Case", "Policy", "Document", "Application Profile", "Business
  Message", "Action", "Search Definition", "Subdocument", "Technical
  message", "User Group", "User Profile";

- *Category Type* with values: "Security", "Business" and "Messaging";

- *Event Type* with values : \"Application End\", \"Application Start\",
  \"Archive / Unarchive Case\", \"Assign Case\", \"Change Authorisation
  Policy\", \"Clear Alarm\", \"Create Document\", \"Create New Case\",
  \"Create Search Definition\", \"Create User Or Group\", \"Delete
  Attachment On Document\", \"Delete Attachment on Case\", \"Delete
  Comment On Case\", \"Delete Comment On Document\", \"Delete
  Document\", \"Delete Search Definition\", \"Delete User Or Group\",
  \"Export Subdocument Batch\", \"Import Subdocument Batch\", \"Login\",
  \"Logout\", \"Notify About Received Business Message\", \"Notify About
  Status Update\", \"Process Received Business Message\", \"Receive
  Business Message\", \"Receive New Case\", \"Receive Technical
  Message\", \"Retrieve Attachment On Document\", \"Retrieve Attachment
  on Case\", \"Retrieve Case Assignments\", \"Retrieve Case By Business
  Id\", \"Retrieve Case By Id\", \"Retrieve Case Hash Code By Id\",
  \"Retrieve Case Id By International Id\", \"Retrieve Document\",
  \"Retrieve Initial Document\", \"Retrieve Notification Details\",
  \"Retrieve Notification Summary\", \"Retrieve Notification Time
  Slots\", \"Retrieve Notifications Consolidated Summary\", \"Retrieve
  Thumbnail\", \"Search Cases By Search Definition And Or FreeText\",
  \"Send Business Message\", \"Send Document\", \"Send Technical
  Message\", \"Set Alarm\", \"Submit Attachment On Document\", \"Submit
  Attachment on Case\", \"Submit Comment On Case\", \"Submit Comment On
  Document\", \"Submit Document\", \"Update Application Profile\",
  \"Update Document\", \"Update Notification\", \"Update Search
  Definition\", \"Update User Profile\"

> Additionally, the administrator may filter for a particular time
> period by choosing a date from the calendar as **from** and choosing
> between 1, 2 or 3 days ahead as **to** followed by pressing the search
> button (see [Figure 94](#_bookmark139)).

![Graphical user interface, application Description automatically
generated](media/image317.jpeg){width="6.2784241032370955in"
height="1.9697911198600175in"}

> []{#_bookmark139 .anchor}Figure 94: Logs: Audit Logs: Time period
> search
>
> At last, the administrator may search in the Audit Logs. RINA
> free-text search engine will apply for searching mechanism.
>
> RINA free-text search engine has the following features:

- Any search applies to each one of the following searchable users'
  fields:

  - Event type

  - Username

  - Description

  - Action Type

- It supports **more than one word** in a single search separated by
  spaces; if user searches using multiple words, the search is executed
  assuming an "AND" operator between the words -- it will require all of
  the terms of the searching string to be present in the results

- The searches are performed in a **case insensitive** mode Specific
  special characters/operators/formats are supported:

  - The **character '+'** signifies a logical AND operation (this
    operator is optional since the space also signifies a logical
    'AND'); this option should be used when searching for entire words
    not in the case of using approximative search using \* character
    Example: *'user test'* or *'user + 'test'* will return results that
    contain both the words

> *'user* and *'test'* in any of the searchable fields;

- It can be used **OR operator between words** and this would mean
  searching for results containing first word or containing the second
  word not necessarily both of them in the same case as in the situation
  of AND operator;

- The **character '-'** negates a single token and returns results that
  do not match the specific tokens; [Beware]{.underline}: in order for
  this algorithm to provide the proper results, the hyphen ("-") needs
  to be adjacent to the value to exclude from the search results
  (without any spaces between); hence, no space character should be
  between them; this option should be used when searching for entire
  words not in the case of using approximative search using \*
  character;

> Example: *'retrieve -admin'* will return audit logs that match with
> the value '*retrieve* in any searchable field and NOT the value
> '*test*'.

- In case of using numbers to search by then **the number must be
  positioned in the beginning of the searched text** and not in the
  middle or at the end of it; Example: in case of using numbers the
  sequence to search by should be "8415

> case"; do not use sequences like "case 8415" or "comment 8415 submit"
> because
>
> the engine will return no results;

- Starting from RINA 6.\* release **the search mechanism has been
  improved** and it is using a more advanced and improved text search
  algorithm. So when the user type a key word in the search box this
  does not do an exclusive search for the exact word, but instead it
  knows about plural/singular, feminine/masculine and so on, and also
  different forms of a word for example jump/jumping/jumped (this
  applies only for English language);

- A partial search can be applied if **a star character (\*) is added at
  the end of the searched word** (e.g. Retri\* in order to search for
  audit logs records having words starting with "Retri" in the
  searchable fields); if the user wants to perform partial search for
  each searched word then an AND or an OR operator must be used between
  partial words (e.g. Retri\* AND Det\* in order to search for users
  having words starting with "Retri" and words starting with "Det";
  Retri\* OR Det\* in order to search for users having words starting
  with "J"o or words starting with "Ad")

#### ![](media/image318.png){width="0.3841119860017498in" height="0.10738626421697288in"} Logs: Technical Logs

![](media/image320.jpeg)

> []{#_bookmark140 .anchor}Figure 95: Logs: Technical Logs
>
> *"Technical Logs"* screen provides basic troubleshooting information
> directly in the RINA portal. Similarly, to the *"Audit Logs"* screen,
> the administrator may perform very granular searches in order to
> pinpoint to the dates, type of information and area of interest. The
> information is once again correlated with the RINA Audit Trail and
> Reporting API (see [Figure 95](#_bookmark140)).
>
> ![](media/image321.png){width="0.17198272090988626in"
> height="0.1857458442694663in"}To find more quickly the required
> information, the administrator may filter the results by using the \[
> \] icon:

- *All Log Types:* searching for logs concerning BUC Engine, AP Client
  (business messaging services layer) or REST (case processing services
  layer) specifically.

- *Log level*: The administrator may toggle between one or more of the
  following

> categories: "*Trace", "Error", "Info", "Fatal", "Debug" and "Warn"*.
>
> Additionally, the administrator may filter for a particular time
> period by choosing a date from the calendar as **from** and choosing
> between 1, 2 or 3 days ahead as **to** followed by pressing the search
> button (see [Figure 95](#_bookmark140)). While search is performed,
> the search and refresh buttons are blocked until the results are
> presented to the user.
>
> Total Records number is followed by an informative icon that allows
> the user to see how many technical logs were created in total (grouped
> per each day) from the horizon of maximum 3 days.
>
> The administrator may search for a specific term/keyword or a set of
> keywords separated by space character (e.g. exception error). The
> *Keywords* are typed in the free-text search text box available in
> upper right hand side of the Technical Logs window (see the above
> screenshot from [Figure 95](#_bookmark140)) and the searching
> algorithm searches for the specific *Keyword* against the following
> fields: level, logger name, thread, message. The search is **not Case
> Sensitive.** The search algorithm uses all the keywords provided in
> the Search text box.

## Automatic Updates

![](media/image324.png)

> []{#_bookmark142 .anchor}Figure 96: Automatic Updates
>
> The "*Automatic Updates"* screen is used to synchronise either IR
> (Institution repository) or CDM (Common Data Model) retrieved from
> CSN, through the AP component (see [Figure](#_bookmark142)
> [96](#_bookmark142)).
>
> ![](media/image321.png){width="0.17198272090988626in"
> height="0.1857458442694663in"}In order to find more quickly the
> required information, the administrator may filter the results by
> using the \[ \] icon (see [Figure 97](#_bookmark143)):

- **Resource Type***:* "Localisation", "Vocabularies", "SEDs", "Form
  Templates",

> "SBDHs", "Organisations", "Transactions", "Initial Documents";

- **Status**: \"Same Version Everywhere\", \"Older Version On Disk\",
  \"On Disk Only\", \"Installed Only\", \"Newer Version on Disk\";

![](media/image329.png)

> []{#_bookmark143 .anchor}Figure 97: Automatic Updates: Search
> filtering
>
> There is also a search feature that provides granular search options.
> To quickly detect the required information, the administrator may
> filter the displayed list by using keywords.
>
> To configure the settings for automatic updates, the administrator can
> press the SETTINGS icon in the top right section of the screen. In the
> next screen ([Figure 98](#_bookmark144)), the administrator can define
> the path of the local repository (**Disk Resources Path on Server**),
> which is the path where the content is downloaded from CSN (through
> AP).
>
> Other configuration options are related to elements such as: **Shared
> Configuration Path**, **Shared BMP Repository Path**, **Form Templates
> Repository Path**, **Office Templates Repository Path** and
> **Localisation Resources Repository Path**.
>
> ![](media/image334.png)
>
> []{#_bookmark144 .anchor}Figure 98: Automatic Updates: Configuration
> Settings
>
> In case of any updates to the configuration content, the administrator
> needs to press SAVE for the system to save changes.
>
> Following the process configuration, the administrator should apply 3
> discrete manual steps in order to synchronise the IR and/or CDM
> repositories:

1.  Start the procedure by requesting the relevant synchronisation
    artefacts, through options SYNC INSTITUTIONS or SYNC CDM
    accordingly;

2.  Select the relevant artefacts by using the filter provided on the
    right side of the screen in order to automatically (through this
    action) get them copied from the receiving folders to the processing
    ones and visualise them (as new content) by clicking on the REFRESH
    icon. The existing artefacts are tagged with a green rectangle \[
    ![](media/image336.png){width="0.15138888888888888in"
    height="0.13697069116360455in"} \] icon and the artefacts that could
    be updated (through their deployment) with a red rectangle \[
    ![](media/image337.png){width="0.10520778652668417in"
    height="9.819335083114611e-2in"} \] icon. The administrator may
    select all the artefacts to be copied and select the relevant ones
    by applying the appropriate filters on the displayed results;

3.  The administrator selects the exact artefacts that should be
    installed by clicking on the artefacts group check boxes or on the
    appropriate red rectangle icon and select INSTALL (XX) button to
    trigger the deployment process of the corresponding artefacts.

> The IR and CDM synchronisation processes are described in detail in
> the next sections
> ([4.10.1](#synchronise-institution-repository-request-sync-institutions)
> and [4.10.2](#synchronise-the-common-data-model-request-sync-cdm)).
>
> On a different topic, the administrator has the option to import an
> organisation structure directly through this section by pressing the
> IMPORT ORGANISATIONS button, which allows the manual import of the IR
> from a local file (see [Figure 99](#_bookmark145)).

![](media/image340.png)

> []{#_bookmark145 .anchor}Figure 99: Automatic Updates: Import
> Organisations

#### ![](media/image342.png){width="0.4774737532808399in" height="0.10738626421697288in"}Synchronise Institution Repository request (Sync Institutions)

> The administrator requests the synchronisation of the Institution
> Repository (IR) by clicking on SYNC INSTITUTIONS button (see [Figure
> 96](#_bookmark142)). Next screen appears, see [Figure
> 100](#_bookmark147), and the version of the existing IR is provided
> (**Current Version**). The **Current Version** parameter is used for
> the IR request sent to the AP. RINA sends the IR synchronisation
> request to the AP when the button SAVE is pressed.
>
> In case the **Current Version** parameter has been modified during
> editing, the administrator can reset it via pressing the RESET button.
> Upon finalisation of this operation, the RINA application sends a
> *system* message to the AP to request the latest IR version (SYN002
> message). The AP responds in an asynchronous manner with the new
> version file (in case there is any), or without any file (if Current
> Version of RINA sent request has the latest available version). The
> referred file is provided as attachment onto the received SYN001
> system (sync) message. Any new files are persisted under the defined
> (via the configuration) disk resource path of the application system.

![](media/image345.png)

> []{#_bookmark147 .anchor}Figure 100: Automatic Updates: Request for IR
> Sync (Institutions Synchronisation)

#### ![](media/image347.png){width="0.4824737532808399in" height="0.10738626421697288in"}Synchronise the Common Data Model request (Sync CDM)

> The administrator can request the synchronisation of the Common Data
> Model (CDM) via pressing on SYNC CDM button (see [Figure
> 101](#_bookmark149)). The following window pops up where the
> administrator can provide information about which artefact group(s)
> need(s) to be synchronised with the AP. The available choices for
> requests are:

- BMP for Business processes;

- RINA_BL for the artefacts concerning RINA Business Layer;

- RINA_PL for the corresponding artefacts of the RINA Protocol Layer;

- AP (Access Point) Artefacts.

> The number of groups to be synchronised can be customised along with
> the date of the latest synchronisation date in RINA to the CDM request
> from the AP. The administrator can add/remove a request by simple
> clicking on ADD or DELETE buttons, respectively. The administrator can
> press on SAVE button for the system to send the request. In case the
> version value has been modified during editing, the administrator can
> reset it via pressing the RESET button. The administrator can upon
> finalisation of this operation, the RINA application will send a
> *system* message to the AP to request the latest CDM content based on
> the related requested artefact groups (SYN005 message). The AP will
> respond in an
>
> asynchronous manner with the new file (in case there is any newer
> related content), or an empty file (if RINA has the latest data
> content). Any new files will be persisted under the defined (via the
> configuration) disk resource path of the application system.

![](media/image350.png)

> []{#_bookmark149 .anchor}Figure 101: Automatic Updates: CDM
> synchronisation (Sync CDM)
>
> ![](media/image353.png)***Recommendations:***

- *The "Automatic Updates: CDM sync" feature is used when the CDM
  artefacts are not installed during the installation procedure but the
  new CDM artefacts are published from CSN.*

- *In case of a large update, where the number of generated artefacts to
  be synchronised is huge (i.e. hundreds or thousands of artefacts), it
  is strongly recommended to install ONLY one artefacts resource type at
  a time and to repeat the procedure until all the necessary artefacts
  are correctly installed. If an artefact type contains many updates to
  get deployed, it is also recommended to get this operation performed
  over multiple steps by selecting a file subset of such long lists at a
  time.*

- *The Automatic Updates (CDM & IR Synchronisation) are time consuming
  operations and cannot be instantly completed (this is also depending
  on the volume as it is described above). Therefore, the administrator
  should monitor the operation progress:*

  - *related to receiving the files by checking their existence at the
    level of the system (Holodeck component);*

  - *related to the deployment by pressing the refresh button
    periodically (with the period varying on the list of deployed files
    per operation, i.e., the more files, the longer the period).*

## Test Centre

> *"Test Centre"* allows performing some basic testing of RINA's network
> connectivity to EESSI International Domain. There is a Sanity test
> available that can be used to test mainly the status of the Access
> Point (AP) at which RINA is connected (CHECK STATUS OF ACCESS POINT
> ENDPOINT). The administrator can select the test by simply pressing on
> the appropriate button (see [Figure 102](#_bookmark151)). Refreshing
> the screen (or page) after a few seconds will display the updated test
> results.

![](media/image356.png)

> []{#_bookmark151 .anchor}Figure 102: Test Centre & Check Status of
> Access Point Endpoint (Network)
>
> Sample test result of the **Check Status of Access Point Endpoint** is
> presented on [Figure 102](#_bookmark151)**.**

## ![](media/image359.png)Business Exceptions

> []{#_bookmark153 .anchor}Figure 103: Business Exceptions: Pending
> Messages
>
> RINA can detect certain issues on incoming messages, such as: when
> receiving SED with invalid signature, or receiving SED/attachment
> failing anti-malware validation and automatically creates
> messages/exceptions related to them which the administrator can review
> in the screen "*Business Exceptions: Business Exceptions*".
>
> The other situations (apart from the two mentioned above) could
> involve manual intervention from the administrator (in case business
> exceptions have not been automatically generated by RINA based on time
> intervals settings description in section
> [4.8.1](#notification-centre-notification-settings)). Additional
> information about these exceptions may be found in the document "EESSI
> Business Use Case AD_BUC_11".
>
> There are two types of exceptions:

a)  Business exceptions that can be solved but require (manual or
    automatic) intervention (located in the screen "*Business
    Exceptions: Pending Messages" -- see* [Figure 103](#_bookmark153)),
    and

b)  Notifications about exceptions that cannot be solved, are generated
    for review in the screen "*Business Exceptions: Business
    Exceptions"* (see [Figure 104](#_bookmark154)). An error SED (X050)
    is also automatically generated and sent to the SED originator
    related to this exception. This is not applicable for the case where
    an error message (X050) has been received upon another (X050) one
    originated from the own local RINA. This exclusion has been
    performed in order to avoid an endless loop creation of such error
    message exchanges.

![](media/image361.png)

> []{#_bookmark154 .anchor}Figure 104: Business Exceptions: Business
> Exceptions

#### ![](media/image362.png){width="0.4774737532808399in" height="0.10579505686789151in"}Business Exceptions: Pending Messages

> Regarding the Pending Messages which requires intervention, the
> administrator also has the possibility to see the SED details by
> pressing on VIEW SED button, or even to manually send back to the SED
> originator a business exception (X050 SED) message by pressing the
> REJECT button (both buttons located at the right of each Pending
> Message -- see [Figure](#_bookmark155) [105](#_bookmark155)).
> Alternatively, this reject operation will be performed automatically
> by RINA once the Retention Period of the corresponding Business
> Exception category elapses (see section
> [4.8.1](#notification-centre-notification-settings)).
>
> ![Graphical user interface, application Description automatically
> generated](media/image363.png){width="6.265358705161855in"
> height="2.1222911198600176in"}
>
> []{#_bookmark155 .anchor}Figure 105: Business Exceptions: Pending
> Messages - Actions
>
> When rejecting pending messages, a popup window will be displayed
> where the rejection reason must be provided. Then, the X050 message
> can be sent when the administrator presses YES, alternatively he/she
> can press NO to abort the operation (see [Figure 105](#_bookmark155)).
> The administrator may see all rejected messages in the screen
> "Business Exceptions".

#### Business Exceptions: Business Exceptions

> ![](media/image364.png){width="0.4824737532808399in"
> height="0.10579505686789151in"}Regarding the Business Exceptions, the
> administrator may visualise the SED that caused the business exception
> or even see the Rejection SED generated for this SED, by pressing the
> corresponding buttons VIEW SED and VIEW REJECTION SED respectively.
>
> ![Graphical user interface, text, application, email Description
> automatically
> generated](media/image365.png){width="6.240991907261592in"
> height="2.4145833333333333in"}
>
> []{#_bookmark156 .anchor}Figure 106: Business Exceptions: Business
> Exceptions - Actions
>
> More detailed information is provided for each message by pressing
> either of the buttons VIEW SED (related to the original SED previously
> appearing as a pending message), or VIEW REJECTION SED (related to its
> business exception - X050 SED).

## ANNEX I - RINA LDAP Synchronisation and Authentication

- By using *"LDAP Configuration"* in IAM RINA you can synchronise users
  and groups from openLDAP or Active Directory.

- Notice that roles/memberships are not synchronised from LDAP.
  Memberships can be added later manually or via CPI.

- Synchronisation: you can define one LDAP Configuration per tenant.

- Authentication: you can define as many LDAP sources as needed per RINA
  server, this configuration is done in CAS:

  - C:\\EESSI\\REST\\Tomcat\\cas\\config\\cas.properties

  - /eessi/rest/tomcat/cas/config/cas.properties

- The values to be used in **Group Mappings** and **User Mappings** will
  depend on your local LDAP configuration.

- Users that belong to one or more groups can be synchronised with a
  selected User\'s role. (i.e. Authorised_clerk, supervisor).

- Group\'s members and User\'s groups can be used to link imported users
  to imported groups with the selected User\'s role.

## A-I.1 Synchronisation and Authentication against OpenLDAP

#### A-I.1.1 Synchronisation from OpenLDAP

> An example of LDAP synchronisation from LDAP Server (OpenLDAP) is
> presented below (see [Figure 107](#_bookmark159)):

![](media/image370.png)

> []{#_bookmark159 .anchor}Figure 107: Synchronisation and
> Authentication against OpenLDAP

#### A-I.1.2 Authentication against OpenLDAP

> The relevant values of the CAS properties file (cas.properties) in
> order to have correct LDAP authentication against OpenLDAP is given
> below (see also [Figure 107](#_bookmark159)):
>
> **\## Reference LDAP configuration**
> [*cas.authn.policy.req.handlerName 🡺*]{.underline}
> eessiLdapAuthenticationHandler [*cas.authn.ldap\[0\].ldapUrl
> 🡺*]{.underline} ldap://\<LDAP-FQDN\>:389
> *[cas.authn.ldap\[0\].useSsl]{.underline}* 🡺 false
> *[cas.authn.ldap\[0\].allowMultipleDns]{.underline}*=true
>
> [*cas.authn.ldap\[0\].baseDn 🡺*]{.underline} ou=users,dc=rina,dc=lab
> *[cas.authn.ldap\[0\].userFilter]{.underline}* 🡺
> (&(uid={user})(objectClass=inetOrgPerson))
> *[cas.authn.ldap\[0\].subtreeSearch]{.underline}* 🡺 true
>
> *[cas.authn.ldap\[0\].bindDn]{.underline}* 🡺
> CN=UserAdmin,dc=rina,dc=lab
>
> *[cas.authn.ldap\[0\].bindCredential]{.underline}* 🡺 \<The LDAP
> password for User "UserAdmin"\>

## A-I.2 Synchronisation and Authentication against Active Directory

#### A-I.2.1 Synchronisation from Active Directory

> An example of LDAP synchronisation from Active Directory is presented
> below (see [Figure](#_bookmark161) [108](#_bookmark161)):

![](media/image376.png)

> []{#_bookmark161 .anchor}Figure 108: Synchronisation and
> Authentication against Active Directory

#### A-I.2.2 Authentication against Active Directory

> The relevant values of the CAS properties file (cas.properties) in
> order to have correct LDAP authentication against Active Directory
> Server is given below (see also [Figure 108](#_bookmark161)):
>
> **\## Reference Active Directory configuration**
> *[cas.authn.ldap\[1\].ldapUrl]{.underline}* 🡺 ldap://\<AD-FQDN\>:389
> *[cas.authn.ldap\[1\].useSsl]{.underline}* 🡺 false
> *[cas.authn.ldap\[1\].allowMultipleDns]{.underline}* 🡺 true
> *[cas.authn.ldap\[1\].baseDn]{.underline}* 🡺 OU=users,DC=rina,DC=lab
>
> *[cas.authn.ldap\[1\].userFilter]{.underline}* 🡺
> (&(sAMAccountName={user})(objectClass=user))
>
> *[cas.authn.ldap\[1\].subtreeSearch]{.underline}* 🡺 true
>
> *[cas.authn.ldap\[1\].bindDn]{.underline}* 🡺 UserAdmin
>
> *[cas.authn.ldap\[1\].bindCredential]{.underline}* 🡺 \<Password of the
> UserAdmin\>
>
> ***Notes:***
>
> *Special attention should be paid on the special characters exist in
> the names of the "User accounts" that are going to be imported for the
> synchronisation and authentication of the RINA users. In general,
> special can be used characters within a distinguished name. However,
> certain special characters should be escaped (i.e., special characters
> should always follow an additional escape character).*
>
> *The following special characters must be escaped when used in a
> distinguished name:*

- *Plus sign (+)*

- *Semicolon (;)*

- *Comma (,)*

- *Backward slash (\\)*

- *Double quote (\")*

- *Less than (\<)*

- *Greater than (\>)*

- *Pound sign (#)*

> *The good knowledge of the structure of the existing Active Directory
> is considered as prerequisite for the configuration for LDAP (in this
> case Active Directory).*
>
> *User for LDAP synchronisation is a **READ** only user (with read
> permissions on Active Directory.*
>
> []{#_bookmark162 .anchor}**A-I.3 Saving LDAP Configuration and
> Triggering LDAP process** Once the LDAP configuration and the Group
> and User Mappings have been completed, the administrator clicks on
> SAVE button to save the configuration parameters.

![Graphical user interface, application Description automatically
generated](media/image378.png){width="6.304259623797026in"
height="3.1in"}

> []{#_bookmark163 .anchor}Figure 109: Synchronisation from OpenLDAP
> Server
>
> At last, when everything has been configured and the CAS properties
> have been correctly configured the synchronisation process can be
> initiated by clicking on the button SYNCHRONISE LDAP located at the
> bottom left corner of the LDAP Configuration page (see [Figure
> 109](#_bookmark163)).

# ANNEX II -- RINA Assignment Policies -- Clarifications and Examples

> In general, there are two different policy types that can be
> configured and assigned under the item *"Authorisation"*:

- The **Creator Policy** that used only to assign the Case creation
  capability to Users and/or Groups.

- The **Case Policy** that used to provide all the necessary permissions
  to a user/clerk to perform all the other actions except the Case
  Creator.

> In addition, the parameters area of the assignment page can be
> distinguished into two basic sections (see [Figure
> 110](#_bookmark166)):

- Section A, where the conditions (i.e. Application Role, Sector(s) and
  Process Type(s)) of a specific policy rule are defined;

- Section B, where it is defined the actor(s) that can perform the Case
  Creation (for the Creator Policy) action when the conditions of
  section A are fulfilled.

> So the provided functionality is: **IF** the conditions of Section A
> are met, **THEN** the specific actions can be applied by the mentioned
> Groups and/or Users.

## A-II.1 Creator Policy

### Creator Policy Characteristics:

- Creator Policy defines only the Case Creator.

- Applicable only for Process Owner (PO) and no other option is
  available for Application Role.

> Concerning section B, the field **Assign to actors** (which include
> the list of RINA available roles) has two different behaviours
> depending on the assignment type (Group or User).

![](media/image381.png)

> []{#_bookmark166 .anchor}Figure 110: Creator Policy parameter sections

#### A-II.1.1 Case Creator Policy Assignment to a Group

> The administrator can choose to assign the Creator Policy to one or
> multiple Groups by choosing the appropriate Groups in section B and
> clicking on SAVE. In case of defining only the Group(s) to assign the
> Creator Policy, every user that belongs to the specific Group(s) at
> the specific moment of the assignment who has also an assigned role
> that provides the permissions to create a Case (Authorised
> Clerk/Un-Authorised Clerk) is able to create a Case for the specified
> Sector(s) and Process Type(s) that defined in section A.
>
> An example explaining the relation between the assigned Role and the
> Group(s) permissions resulted from Case Creator assignment is
> presented below. On [Figure 111](#_bookmark167) the role assignment
> (in IAM) of the user **supervisorTest** is presented. The user
>
> **supervisorTest** belongs to **ECMATest** group and has the RINA
> roles **SUPERVISOR** and

### AUTHORIZED_CLERK.

![](media/image385.png)

> []{#_bookmark167 .anchor}Figure 111: Creator Policy Group assignment
> example (IAM configuration)
>
> In Authorisation section (Assignment Policies: Creator Policy
> Definition), the administrator adds a Case Creator policy for the
> specific **ECMATest** Group for any Sector and any Process Type (see
> [Figure 112](#_bookmark168)).

![](media/image385.png)

> []{#_bookmark168 .anchor}Figure 112: Creator Policy Group assignment
> example (Authorisation configuration) Consequently, the user
> **supervisorTest** acquires the Case Creator capability for all the
> Sectors and Process types (BUC types) according to the policy rule
> defined above. The final assignment is **activated** at "*Process
> Assignments"* subitem where all the Process assignments are presented
> on [Figure 113](#_bookmark169) below.
>
> ![](media/image391.png)
>
> []{#_bookmark169 .anchor}Figure 113: Process Assignments for the roles
> and actors defined in the example Therefore, in the case of assigning
> a Case Creator Policy to a Group the users of the Group acquire the
> Case Creator capability only if it is permitted by their Role.

#### A-II.1.2 Case Creator Policy Assignment to a User

> In case of selecting a User of a defined Group (section B), the
> specific User is able to create a Case for the sector(s) and Process
> Type(s) defined in fields "*Sector in"* and "*Process Type in"* of
> section A, regardless the role assigned to this User (in IAM) which
> permits Create Case action (Authorised Clerk or Un-Authorised Clerk).
>
> *A Policy assignment to a specific User overwrites the **[Roles
> permissions]{.underline}** defined in IAM.*
>
> For example, in the case the User **supervisorTest** belongs to
> **ECMATest** (in IAM) group and has assigned only **SUPERVISOR** role,
> the User cannot create a Case because the Role **SUPERVISOR** does not
> permit the Case creation action (see [Figure 114](#_bookmark170)).

![](media/image395.png)

> []{#_bookmark170 .anchor}Figure 114: IAM configuration for the user
> supervisor with Role \"SUPERVISOR\"
>
> In Authorisation section (Assignment Policies: Creator Policy
> Definition), a case Creator policy is added for user
> **supervisorTest** for any Sector and any Process Type (see
> [Figure](#_bookmark171) [115](#_bookmark171)).
>
> ![](media/image395.png)
>
> []{#_bookmark171 .anchor}Figure 115: Creator Policy assignment to User
> supervisor
>
> Following the above IAM configuration and the Case Creation policy
> assignments, the user **supervisorTest** can create a case for the
> sector(s) and Process type(s) selected in section A of the rule
> definition even if the role (**Supervisor**) does not permit the
> specific action.
>
> Consequently, the permissions acquired by the Users through the
> Policies assignment path overwrite the permissions inherited through
> the Role definition in the case of assigning the Case Creator policy
> to specific users.

## A-II.2 Case Policy

### Characteristics:

- The *"Case Policy"* or simply "Policy" as referred on RINA admin
  portal, determines the Users/Groups that are assigned to new created
  cases or to received ones with specific roles (the role define the
  allowed actions);

- Applicable at the level of Process Owner or Counterparty or both
  (Any).

#### A-II.2.1 Case Policy Assignment to a Group for any Application Role

![](media/image401.png)

> []{#_bookmark173 .anchor}Figure 116: New General Policy definition
> (Conditions/Actors)
>
> In case of choosing to assign a *"Case Policy*" to a Group (in section
> B), **every user** that belongs to the specific Group is assigned to
> the Cases which fulfil the defined conditions in fields "*Sector in"*
> and "*Process Type in"* (section A). The permitted actions for the
> users are those that are inherited from the Roles defined for the
> users of the Group in IAM section (see [Figure 116](#_bookmark173)).

![Graphical user interface, application, email Description automatically
generated](media/image403.png){width="6.234014654418198in"
height="3.0661450131233594in"}

> []{#_bookmark174 .anchor}Figure 117: Case Policy example: IAM
> configuration
>
> For example, in the case the User **user01** belongs to **ECMA** group
> (in IAM) group and has the role **Authorised** role (see [Figure
> 117](#_bookmark174)).
>
> In Authorisation section, it is added a *"Case Policy"* for group
> **ECMA**, for Pension (*Sector in* = Pension) and the first BUC type
> (*Process Type in* = P_BUC_01) for users of the Group **ECMA** that
> have assigned as **Authorised** in IAM component.
>
> ![Graphical user interface, application, Teams Description
> automatically
> generated](media/image404.png){width="6.235161854768154in"
> height="3.088020559930009in"}
>
> []{#_bookmark175 .anchor}Figure 118: Case Policy example: Policy
> Definition
>
> Based on the previous stated rules, user **user01** is assigned to all
> cases of Sector=Pension and Process type=P_BUC_01 to which the policy
> that contains the rule defined above is assigned in *Process
> Assignments* subitem (Pension sector in the sample below).

![](media/image407.png)

> []{#_bookmark176 .anchor}Figure 119: Case Policy example: Process
> Assignments
>
> The actions applicable for user **user01** for the assigned cases are
> those related to
>
> **Authorised** role defined in IAM component at the user's level.

#### A-II.2.2 Case Policy Assignment to a User for any Application Role

> In case of selecting a specific User (Section B) to assign a policy,
> this user is assigned to Cases for the sector(s) and BUCs types
> defined in fields **Sector in** and **Process Type in** *(*section A)
> and with actions related to Role(s) defined (section B) through
> **Assign to actors** independently from the roles assigned to these
> users in IAM section. For example,
>
> in IAM component the user **user01** belongs to **ECMA** group and has
> ONLY the **Supervisor**
>
> role.

![](media/image410.png)

> []{#_bookmark177 .anchor}Figure 120: Assignment Policy to User -
> example: IAM configuration
>
> In Authorisation section, the Assignment Policy is added for user
> **user01** for all cases with Sector=Pension and Process type=P_BUC_01
> for which the policy that contains the rule defined above is assigned
> in *Process Assignments* subitem. The actions applicable for user
> **user01** for the assigned cases are those related to **Authorised**
> role selected in rule definition section (see [Figure
> 121](#_bookmark178)).

![](media/image412.png)

> []{#_bookmark178 .anchor}Figure 121: Assignment Policy to User -
> example: Assignment Policy configuration

#### A-II.2.3 Case Policy Assignment to a Group or User for a Process Owner or Counterparty

> These cases are subsets of the cases with **Any** Application Role
> that described in previous paragraphs with a few supplementary
> attributes. The general rules applicable for all the available
> combination are:

- For **Group** assignments -- the field **Assign to actors** from the
  rule conditions area (section B) works as **filter**;

- For **User** assignments -- the field **Assign to actors** from
  section B of the rule works as **assignment**. In this case the Roles
  defined in IAM for this user are not anymore applicable for this rule.

> **Counterparty** tab -- supplementary fields:

- **Owner Country in** -- it is used to pre-filter the country of
  received cases from a case owner. It permits multiple selection;

- **Owner Organisation in** -- this field is used to pre-filter the
  sending institution of a received case. It permits multiple
  selections;

- **Subject Address like** (deprecated function, recommended not to use
  it) - the purpose of the field is to filter the cases based on a value
  find in the Region from the address of the Subject (Person/Citizen) of
  a Case.

> **Process Owner** tab -- supplementary fields. When the **Process
> Owner** Tab is selected during the "*New Policy*" creation procedure,
> three additional choices are available (**Case Creator in** at the
> conditions block and the choices **Creator User** and **Creator's
> branch** at the top of the User/Group selection block).
>
> Any supplementary choice does not cancel or limit the effect of the
> normal choices and can be considered as additional ones that used as
> additional filters or as an implementation of exceptional cases that
> are easily covered:

- **Case Creator in** -- it is used to choose the group to which the
  Process Owner belongs;

- **These users and groups** -- it permits to select **Creator user**,
  **Creator\'s branch**

> or both, i.e.:

- **Creator user** - the case is assigned to the creator directly;

> In this case the actions assigned to the Creator are those related to
> the roles selected in Assign to Actors (section B -- Rule conditions)

- **Creator\'s branch**-- the case is assigned to the Creator branch.
  This choice is valid only if the Group have been characterized as
  **Organisation Unit** by selecting the relevant choice during the
  group creation process (section [4.6.2.1](#creating-groups) and
  [Figure 63](#_bookmark98)). In this case the actions assigned to the
  creator(s) are those that related to the roles defined in IAM
  component at the user's level

> ![](media/image353.png)

# List of figures

> [Figure 1: EESSI General Architecture 11](#_bookmark4)
>
> [Figure 2: EESSI-RINA Architecture
> 12](https://eessi365.sharepoint.com/sites/EESSIProjectDocumentation/EESSI%20Publishing%20Catalogue/EESSI%20-%202020/EESSI%20-%202020%20HF8/EESSI%20-%20RINA%206.2.18%20(Portal%206.2.19)%20-%20Administration%20Manual.docx#_Toc91011802)
>
> [Figure 3: RINA Admin Portal Home Screen 13](#_bookmark10)
>
> [Figure 4: RINA Admin Portal Home Screen (Sections)
> 13](https://eessi365.sharepoint.com/sites/EESSIProjectDocumentation/EESSI%20Publishing%20Catalogue/EESSI%20-%202020/EESSI%20-%202020%20HF8/EESSI%20-%20RINA%206.2.18%20(Portal%206.2.19)%20-%20Administration%20Manual.docx#_Toc91011804)
>
> [Figure 5: EESSI RINA Home Page 15](#_bookmark14)
>
> [Figure 6: RINA application Login Page 15](#_bookmark15)
>
> [Figure 7: Admin User Profile 16](#_bookmark17)
>
> [Figure 8: Admin: Localisation Settings 16](#_bookmark19)
>
> [Figure 9: Admin: Change Password 17](#_bookmark21)
>
> [Figure 10: Admin: Help 17](#_bookmark23)
>
> [Figure 11: User idle time and RINA Version 18](#_bookmark25)
>
> [Figure 12: Tenant Settings 20](#_bookmark30)
>
> [Figure 13: Tenant Settings: Disable Tenant 21](#_bookmark31)
>
> [Figure 14: Tenant Settings: Add New Tenant 21](#_bookmark32)
>
> [Figure 15: Confirmation Dialog Box for the deletion of a Tenant
> 21](#_bookmark33)
>
> [Figure 16: Application Settings: General Settings 23](#_bookmark35)
>
> [Figure 17: General Settings: Define parameters like Application Id,
> Languages, etc 23](#_bookmark37)
>
> [Figure 18: General Settings: SED validation Mode 24](#_bookmark38)
>
> [Figure 19: General Settings: Maximum number of child documents
> 25](#_bookmark39)
>
> [Figure 20: General Settings: Full Error Information and Versions
> 25](#_bookmark40)
>
> [Figure 21: General Settings: Show Process version (RINA User Portal)
> 25](#_bookmark41)
>
> [Figure 22: General Settings: Attachments Settings 26](#_bookmark42)
>
> [Figure 23: General Settings: Default Values of Importance/Criticality
> of a case 26](#_bookmark43)
>
> [Figure 24: Application Settings: Default Case Settings
> 27](#_bookmark45)
>
> [Figure 25: Clerk section Case Settings 27](#_bookmark46)
>
> [Figure 26: Example of Classic View (User Portal) 28](#_bookmark47)
>
> [Figure 27: Example of Timeline View (User Portal) 28](#_bookmark48)
>
> [Figure 28: General Settings: Alarm Settings 28](#_bookmark49)
>
> [Figure 29: General Settings: Default User Profile 29](#_bookmark51)
>
> [Figure 30: Case Counter Settings 30](#_bookmark53)
>
> [Figure 31: Case Counter Settings: Default Type 30](#_bookmark54)
>
> [Figure 32: Case Counter Settings: HTTP Callback Type
> 31](#_bookmark55)
>
> [Figure 33: Case Counter Settings: Pattern Type 31](#_bookmark56)
>
> [Figure 34: Global Messaging Settings: Authentication (TLS)
> 34](#_bookmark59)
>
> [Figure 35: Global Messaging Settings: Authorisation (Signatures)
> 35](#_bookmark60)
>
> [Figure 36: Global Messaging Settings: Business Signatures
> 35](#_bookmark61)
>
> [Figure 37: Local Messaging Settings (PUSH example) 36](#_bookmark63)
>
> [Figure 38: Local Messaging Settings (PULL example) 37](#_bookmark64)
>
> [Figure 39: Global Messaging Settings 39](#_bookmark65)
>
> [Figure 40: Global Messaging Settings: Antimalware 40](#_bookmark66)
>
> [Figure 41: NIE Settings 41](#_bookmark68)
>
> [Figure 42: NIE Settings: Add Case Event Subscription
> 42](#_bookmark69)
>
> [Figure 43: NIE Settings: Add Document Event Subscription
> 43](#_bookmark70)
>
> [Figure 44: NIE Settings: Manage multiple Case Event Subscriptions
> 44](#_bookmark71)
>
> [Figure 45: NIE Settings: Add Notification Event 44](#_bookmark72)
>
> [Figure 46: NIE settings: Delete existing subscription
> 45](#_bookmark73)
>
> [Figure 47: NIE Settings: Confirmation for Deleting Subscriptions
> 45](#_bookmark74)
>
> [Figure 48: Case State Transition Diagram 46](#_bookmark76)
>
> [Figure 49: RINA Archiving: Archiving Policies 47](#_bookmark77)
>
> [Figure 50: RINA Archiving: Archiving Policy - Cases 47](#_bookmark78)
>
> [Figure 51: RINA Archiving: Message Retention policies
> 48](#_bookmark79)
>
> [Figure 52: RINA Archiving: Archiving Repositories 48](#_bookmark80)
>
> [Figure 53: RINA Archiving: Archiving Repositories - Edit Volume
> 49](#_bookmark81)
>
> [Figure 54: RINA Archiving: Archiving Repositories - Add Volume
> 49](#_bookmark82)
>
> [Figure 55: RINA Archiving: Message Archiving Repository Policy
> 50](#_bookmark83)
>
> [Figure 56: IAM: Select Tenants 52](#_bookmark87)
>
> [Figure 57: IAM: User Settings 53](#_bookmark89)
>
> [Figure 58: IAM: Add Users 53](#_bookmark91)
>
> [Figure 59: IAM: Modify Users RINA 55](#_bookmark93)
>
> [Figure 60: IAM: Users: Deleting user 56](#_bookmark94)
>
> [Figure 61: IAM: Groups 57](#_bookmark95)
>
> [Figure 62: IAM: Add new group 58](#_bookmark97)
>
> [Figure 63: IAM: New Group configuration 58](#_bookmark98)
>
> [Figure 64: IAM: Modify Groups 59](#_bookmark99)
>
> [Figure 65: IAM: Deleting Groups 59](#_bookmark100)
>
> [Figure 66: IAM: LDAP Configuration 60](#_bookmark101)
>
> [Figure 67: Authorisation: Select Tenant 63](#_bookmark104)
>
> [Figure 68: Authorisation: Assignment Policies 63](#_bookmark105)
>
> [Figure 69: Authorisation: New policy Management 65](#_bookmark108)
>
> [Figure 70: Authorisation: New Creator Policy 66](#_bookmark109)
>
> [Figure 71: Authorisation: New Policy 67](#_bookmark110)
>
> [Figure 72: Conditions, Actors and Users/Groups Role dependent
> selections 68](#_bookmark111)
>
> [Figure 73: Authorisation: New Rule, Remove Rule and change rule's
> priority 69](#_bookmark112)
>
> [Figure 74: Authorisation: New Policy Group 69](#_bookmark113)
>
> [Figure 75: Authorisation: Changing/Deleting Policies
> 70](#_bookmark114)
>
> [Figure 76: Policy Deletion Confirmation 70](#_bookmark115)
>
> [Figure 77: Authorisation: Process Assignments overview without
> assigned policies 71](#_bookmark117)
>
> [Figure 78: Authorisation: Process Assignments assign additional
> policies 71](#_bookmark118)
>
> [Figure 79: Authorisation: Process Assignments validate assignment
> 72](#_bookmark119)
>
> [Figure 80: Authorisation: Process Assignments -- Assigned Policies
> management 72](#_bookmark120)
>
> [Figure 81: Authorisation: Process Assignments -- Export/Import
> 73](#_bookmark121)
>
> [Figure 82: Authorisation: Process Assignments - Import Policies and
> Assignments 73](#_bookmark122)
>
> [Figure 83: Notification Centre 74](#_bookmark124)
>
> [Figure 84: Notification Centre: Configuration Management
> 74](#_bookmark126)
>
> [Figure 85: Notification Centre: Values to be configured
> 75](#_bookmark127)
>
> [Figure 86: Retention and Notification Period definition
> 75](#_bookmark128)
>
> [Figure 87: Opening the Notifications Centre 80](#_bookmark130)
>
> [Figure 88: Notifications centre: Layout 80](#_bookmark131)
>
> [Figure 89: Notifications inside the Notifications Centre's list
> 81](#_bookmark132)
>
> [Figure 90: Detailed view of a notification 82](#_bookmark133)
>
> [Figure 91: Bulk operation for marking multiple notifications as read
> at once 82](#_bookmark134)
>
> [Figure 92: Filter options inside the Notifications Centre
> 83](#_bookmark136)
>
> [Figure 93: Logs: Audit Logs: Layout 84](#_bookmark138)
>
> [Figure 94: Logs: Audit Logs: Time period search 85](#_bookmark139)
>
> [Figure 95: Logs: Technical Logs 87](#_bookmark140)
>
> [Figure 96: Automatic Updates 88](#_bookmark142)
>
> [Figure 97: Automatic Updates: Search filtering 88](#_bookmark143)
>
> [Figure 98: Automatic Updates: Configuration Settings
> 89](#_bookmark144)
>
> [Figure 99: Automatic Updates: Import Organisations 89](#_bookmark145)
>
> [Figure 100: Automatic Updates: Request for IR Sync (Institutions
> Synchronisation) 90](#_bookmark147)
>
> [Figure 101: Automatic Updates: CDM synchronisation (Sync CDM)
> 91](#_bookmark149)
>
> [Figure 102: Test Centre & Check Status of Access Point Endpoint
> (Network) 92](#_bookmark151)
>
> [Figure 103: Business Exceptions: Pending Messages 93](#_bookmark153)
>
> [Figure 104: Business Exceptions: Business Exceptions
> 93](#_bookmark154)
>
> [Figure 105: Business Exceptions: Pending Messages - Actions
> 94](#_bookmark155)
>
> [Figure 106: Business Exceptions: Business Exceptions - Actions
> 95](#_bookmark156)
>
> [Figure 107: Synchronisation and Authentication against OpenLDAP
> 96](#_bookmark159)
>
> [Figure 108: Synchronisation and Authentication against Active
> Directory 97](#_bookmark161)
>
> [Figure 109: Synchronisation from OpenLDAP Server 99](#_bookmark163)
>
> [Figure 110: Creator Policy parameter sections 100](#_bookmark166)
>
> [Figure 111: Creator Policy Group assignment example (IAM
> configuration) 101](#_bookmark167)
>
> [Figure 112: Creator Policy Group assignment example (Authorisation
> configuration) 101](#_bookmark168)
>
> [Figure 113: Process Assignments for the roles and actors defined in
> the example 102](#_bookmark169)
>
> [Figure 114: IAM configuration for the user supervisor with Role
> \"SUPERVISOR\" 102](#_bookmark170)
>
> [Figure 115: Creator Policy assignment to User supervisor
> 103](#_bookmark171)
>
> [Figure 116: New General Policy definition (Conditions/Actors)
> 104](#_bookmark173)
>
> [Figure 117: Case Policy example: IAM configuration
> 104](#_bookmark174)
>
> [Figure 118: Case Policy example: Policy Definition
> 105](#_bookmark175)
>
> [Figure 119: Case Policy example: Process Assignments
> 105](#_bookmark176)
>
> [Figure 120: Assignment Policy to User - example: IAM configuration
> 106](#_bookmark177)
>
> [Figure 121: Assignment Policy to User - example: Assignment Policy
> configuration 106](#_bookmark178)