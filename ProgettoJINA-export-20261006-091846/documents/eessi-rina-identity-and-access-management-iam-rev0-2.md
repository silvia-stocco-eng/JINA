---
unique-name: eessi-rina-identity-and-access-management-iam-rev0-2
display-name: EESSI   RINA   Identity and Access Management (IAM)   rev02
category: GENERAL
description: [Table of Contents [2](#_Toc112872)](#_Toc112872)
tags: ec
---

![](media/image6.png)

# Table of Contents 

[Table of Contents [2](#_Toc112872)](#_Toc112872)

[1 EESSI Identity and Access Management Overview
[6](#eessi-identity-and-access-management-overview)](#eessi-identity-and-access-management-overview)

[2 Functions and use cases
[8](#functions-and-use-cases)](#functions-and-use-cases)

[2.1 IAM configuration [8](#iam-configuration)](#iam-configuration)

[2.2 IAM authentication [9](#iam-authentication)](#iam-authentication)

[2.3 External - Internal repository synchronization
[10](#external---internal-repository-synchronization)](#external---internal-repository-synchronization)

[2.4 External rules for process assignment
[11](#external-rules-for-process-assignment)](#external-rules-for-process-assignment)

[2.4.1 Execution of external rules
[11](#execution-of-external-rules)](#execution-of-external-rules)

[2.4.2 Logical components
[13](#logical-components)](#logical-components)

[2.4.3 Illustrative scenario example -- external filtering rules
[16](#illustrative-scenario-example-external-filtering-rules)](#illustrative-scenario-example-external-filtering-rules)

[2.4.4 XACML Concepts [16](#xacml-concepts)](#xacml-concepts)

[3 Behaviour [18](#behaviour)](#behaviour)

[3.1 IAM authentication
[18](#iam-authentication-1)](#iam-authentication-1)

[3.1.1 Internal User Authentication
[20](#internal-user-authentication)](#internal-user-authentication)

[3.1.2 External User Authentication -- LDAP reference implementation
[20](#external-user-authentication-ldap-reference-implementation)](#external-user-authentication-ldap-reference-implementation)

[3.2 WebSocket Authentication
[22](#websocket-authentication)](#websocket-authentication)

[3.3 LDAP- synchronization
[22](#ldap--synchronization)](#ldap--synchronization)

[4 IAM external interfaces
[24](#iam-external-interfaces)](#iam-external-interfaces)

[5 Configuration of SAML 2.0
[25](#configuration-of-saml-2.0)](#configuration-of-saml-2.0)

[5.1 Limitations [25](#limitations)](#limitations)

[5.1.1 IdP SingleSignOnService Binding
[25](#idp-singlesignonservice-binding)](#idp-singlesignonservice-binding)

[5.1.2 User Identification in RINA Context
[25](#user-identification-in-rina-context)](#user-identification-in-rina-context)

[5.2 Workflow [25](#workflow)](#workflow)

[5.3 Configuration [26](#configuration)](#configuration)

[5.3.1 CAS Configuration [26](#cas-configuration)](#cas-configuration)

[5.3.2 RINA Configuration
[27](#rina-configuration)](#rina-configuration)

[6 Configuration for JWT Authentication
[29](#configuration-for-jwt-authentication)](#configuration-for-jwt-authentication)

[7 Configuration of Single-Sign-On
[30](#configuration-of-single-sign-on)](#configuration-of-single-sign-on)

[8 Other Authentication Plugins
[31](#other-authentication-plugins)](#other-authentication-plugins)

[8.1 Other Authentication Plugins
[31](#other-authentication-plugins-1)](#other-authentication-plugins-1)

[9 Samples [33](#samples)](#samples)

[9.1 Update LDAP connection settings request
[33](#update-ldap-connection-settings-request)](#update-ldap-connection-settings-request)

[9.2 Get LDAP connection settings response
[33](#get-ldap-connection-settings-response)](#get-ldap-connection-settings-response)

[9.3 Update LDAP group parameters mapping request
[33](#update-ldap-group-parameters-mapping-request)](#update-ldap-group-parameters-mapping-request)

[9.4 Get LDAP group parameters mapping resonse
[33](#get-ldap-group-parameters-mapping-resonse)](#get-ldap-group-parameters-mapping-resonse)

[9.5 Get LDAP group parameters keys
[34](#get-ldap-group-parameters-keys)](#get-ldap-group-parameters-keys)

[9.6 Update LDAP user parameters keys request
[34](#update-ldap-user-parameters-keys-request)](#update-ldap-user-parameters-keys-request)

[9.7 Get LDAP user parameters keys
[34](#get-ldap-user-parameters-keys)](#get-ldap-user-parameters-keys)

[9.8 Get LDAP user parameters keys
[35](#get-ldap-user-parameters-keys-1)](#get-ldap-user-parameters-keys-1)

[9.9 Synchronize LDAP [35](#synchronize-ldap)](#synchronize-ldap)

[9.10 Reassign group affected cases
[35](#reassign-group-affected-cases)](#reassign-group-affected-cases)

[9.11 Retrieves a list of policies, optionally filtered
[35](#retrieves-a-list-of-policies-optionally-filtered)](#retrieves-a-list-of-policies-optionally-filtered)

[9.12 Retrieves a policy [36](#retrieves-a-policy)](#retrieves-a-policy)

[9.13 Creates a policy [37](#creates-a-policy)](#creates-a-policy)

[9.14 Updates a policy [37](#updates-a-policy)](#updates-a-policy)

[9.15 Deletes a policy [38](#deletes-a-policy)](#deletes-a-policy)

[9.16 Associates an existing policy to a target
[38](#associates-an-existing-policy-to-a-target)](#associates-an-existing-policy-to-a-target)

[9.17 Associates existing policies to a target
[38](#associates-existing-policies-to-a-target)](#associates-existing-policies-to-a-target)

[9.18 Removes a target from a policy
[38](#removes-a-target-from-a-policy)](#removes-a-target-from-a-policy)

[10 PDP - Case Assignment Policy Decision Point
[39](#pdp---case-assignment-policy-decision-point)](#pdp---case-assignment-policy-decision-point)

[10.1 Service contracts / interface
[39](#service-contracts-interface)](#service-contracts-interface)

[10.2 Data contracts / model
[39](#data-contracts-model)](#data-contracts-model)

[10.2.1 Actor [39](#actor)](#actor)

[10.2.2 UserOrGroup [39](#userorgroup)](#userorgroup)

[10.2.3 Case properties [39](#case-properties)](#case-properties)

[10.2.4 Participant [40](#participant)](#participant)

[10.2.5 Organisation (inherits Entity)
[40](#organisation-inherits-entity)](#organisation-inherits-entity)

[10.2.6 Person (inherits Entity)
[40](#person-inherits-entity)](#person-inherits-entity)

[10.2.7 Entity [40](#entity)](#entity)

[10.2.8 Address [40](#address)](#address)

[10.3 Fault contracts / exceptions
[41](#fault-contracts-exceptions)](#fault-contracts-exceptions)

[11 Development impact [42](#development-impact)](#development-impact)

[12 How-to\'s [42](#how-tos)](#how-tos)

[12.1 How to configure the synchronizer
[42](#how-to-configure-the-synchronizer)](#how-to-configure-the-synchronizer)

[12.2 How to develop my external rules
[42](#how-to-develop-my-external-rules)](#how-to-develop-my-external-rules)

[12.3 How to configure LDAP
[44](#how-to-configure-ldap)](#how-to-configure-ldap)

[12.3.1 Authentication [44](#authentication)](#authentication)

[13 Relevant links & References
[45](#relevant-links-references)](#relevant-links-references)

[14 Limitations of the current version
[45](#limitations-of-the-current-version)](#limitations-of-the-current-version)

**Document Control Information**

+--------------------------------------------------------------------------------------------+
| **Document Control Value**                                                                 |
+:====================================+:=====================================================+
| > **Project Title**                 | > Electronic Exchange of Social Security Information |
|                                     | > (EESSI)                                            |
+-------------------------------------+------------------------------------------------------+
| > **Document Name**                 | > EESSI -- RINA - Identity and Access Management     |
|                                     | > (IAM)                                              |
+-------------------------------------+------------------------------------------------------+
| > **Document Category**             | > Solution / Application Architecture                |
+-------------------------------------+------------------------------------------------------+
| > **Revision**                      | > \-                                                 |
+-------------------------------------+------------------------------------------------------+
| > **Component Version**             | > \-                                                 |
+-------------------------------------+------------------------------------------------------+
| > **Last Publication Date**         | > 6/5/2022                                           |
| >                                   | >                                                    |
| > **Project Milestone**             | > EESSI-2020 RINA Fix10                              |
+-------------------------------------+------------------------------------------------------+
| > **Document Status**               | > Final                                              |
+-------------------------------------+------------------------------------------------------+
| > **Sensitivity (TLP)**             | > **Traffic Light Protocol (TLP) = "GREEN"**         |
| >                                   | >                                                    |
| > **Distribution terms**            | > ![](media/image11.jpg){width="2.311111111111111in" |
|                                     | > height="1.1131944444444444in"}                     |
|                                     | >                                                    |
|                                     | > The distribution of this document is done strictly |
|                                     | > in line with the Traffic Light Protocol (TLP)      |
|                                     | > established by the European Commission\'s note AC  |
|                                     | > 790/15 REV for the EESSI project documentation.    |
|                                     | >                                                    |
|                                     | > In line with the note AC 790/15 REV, this document |
|                                     | > is labelled as TLP = "Green". Therefore, it can be |
|                                     | > circulated widely within the EESSI community.      |
|                                     | > However, the document or the information herein    |
|                                     | > may not be published or posted on the Internet,    |
|                                     | > nor released outside of the EESSI community.       |
+-------------------------------------+------------------------------------------------------+
| > **Connected/Embedded**            | > None                                               |
| >                                   |                                                      |
| > **Files**                         |                                                      |
+-------------------------------------+------------------------------------------------------+
| > **Authors**                       | > European Commission, DG EMPL A4, EESSI ARCH/RINA   |
+-------------------------------------+------------------------------------------------------+
| > **Revised by**                    | > European Commission, DG EMPL A4, EESSI QA          |
+-------------------------------------+------------------------------------------------------+
| > **Approved by**                   | > European Commission, DG EMPL A4, EESSI PM          |
+-------------------------------------+------------------------------------------------------+

**Document history**

+------------------------+------------+----------------------------------+
| > **Document Title**   | **Date**   | > **Changes/Corrections**        |
| >                      |            | >                                |
| > **(revision)**       |            | > **Description**                |
| >                      |            |                                  |
| > **Project            |            |                                  |
| > milestone**          |            |                                  |
+:=======================+:===========+:=================================+
| > **EESSI -- RINA --   | 11/2019    | > Added a new method in the      |
| > Identity and Access  |            | > service contract               |
| > Management**         |            |                                  |
| >                      |            |                                  |
| > **(IAM)**            |            |                                  |
| >                      |            |                                  |
| > **EESSI-2019**       |            |                                  |
|                        |            +----------------------------------+
|                        |            | > Remove chapter 4               |
|                        |            +----------------------------------+
|                        |            | > Add chapter 7 for SSO          |
|                        |            | > configuration. The detailed    |
|                        |            | > technical information about    |
|                        |            | > Data and Services contracts    |
|                        |            | > are presented in the CPI       |
|                        |            | > reference guide                |
+------------------------+------------+----------------------------------+
| > **EESSI -- RINA --   | 18/12/2020 | > Description updated to reflect |
| > Identity and Access  |            | > then new RINA developments and |
| > Management**         |            | > architectural improvements     |
| >                      |            |                                  |
| > **(IAM)**            |            |                                  |
| >                      |            |                                  |
| > **EESSI-2020 / RINA  |            |                                  |
| > 6.2.1**              |            |                                  |
+------------------------+------------+----------------------------------+
| > **EESSI -- RINA --   | 20/11/2021 | > Minor adjustments in section   |
| > Identity and Access  |            | > 2.4.2 (matrix user             |
| > Management**         |            | > roles/actions)                 |
| >                      |            |                                  |
| > **(IAM) rev01**      |            |                                  |
| >                      |            |                                  |
| > **EESSI-2020 (RINA   |            |                                  |
| > HF1 --**             |            |                                  |
| >                      |            |                                  |
| > **RINA 6.2.3)**      |            |                                  |
|                        |            +----------------------------------+
|                        |            | > Updated the chapter 5 about    |
|                        |            | > the SAML2 integration.         |
|                        |            +----------------------------------+
|                        |            | > Added new configuration        |
|                        |            | > properties and a paragraph     |
|                        |            | > about a possible domain name   |
|                        |            | > problem.                       |
+------------------------+------------+----------------------------------+
| > **EESSI -- RINA --   | 06/05/2022 | > Clarifications on the user     |
| > Identity and Access  |            | > roles description on "*Table   |
| > Management**         |            | > 1: RINA User Roles and the     |
| >                      |            | > permitted* actions" and the    |
| > **(IAM) rev02**      |            | > related notes in section       |
| >                      |            | > *"2.4.2 - Logical components"* |
| > **EESSI-2020 RINA    |            |                                  |
| > Fix10**              |            |                                  |
|                        |            +----------------------------------+
|                        |            | > Added Websocket Authentication |
+------------------------+------------+----------------------------------+

# EESSI Identity and Access Management Overview 

Part of the National Institutions Domain, RINA (Reference Implementation
for National Applications) consists of a collection of infrastructure
and communication services, foundation, repository and publishing
services, business, integration and user interface services which will
provide for clerks and their organizations, the tools to implement the
EESSI specific International Protocol of Data Exchange based on
Structured Electronic Documents in Social Security belonging to European
Community Member States and Associated States.

RINA is based on 4 layers which are built one on top of the other, plus
the CAS module:

- *Technical Message Services (TMS).-* provide the mechanism for
  sending/receiving technical messages to the Access Point. It works
  based on the protocol ebMS3.0 - AS4 profile. It is an internal layer
  and cannot be used by third parties, being its unique client the RINA
  BMS.

- *Business Messaging Services (BMS)* - provide a reusable component for
  sending business messages to the Access Point via the TMS layer. These
  services provide the translation (business message to technical
  message and vice versa), transformation (converting IDs to GUIDs),
  validation and signing of the business messages for correct exchange
  with the EESSI environment, and the correct reception of messages from
  other institutions. It offers the BMI WS interface making available
  the integration of third-party applications to the EESSI ecosystem.

- *Case Processing Services (CPS)* -- provide a state full component
  built on top of the Business Messaging Services that manage cases in a
  structured manner taking care of all the issues regarding case flow,
  documents, notifications, user management and provides two interfaces
  for external access (NIE and CPI)

- *Portal* -- provides an UI build on top of the Case Processing
  Services (CPS) having administration consoles and case Processing
  modules

- *CAS Authentication Server* -- the SSO (Single Sign On) server
  providing the authentication to users/clients requesting to use a
  service

> ![](media/image12.png){width="4.614583333333333in"
> height="3.7118055555555554in"}

*Figure 1. Rina Functional Layers, modules, and Interfaces*

The scope of this document is to provide a specification document for
the Identity and Access Management Interface, part of the Case
Processing Services (CPS).

Here is a short description of how this document is structured:

- Interface overview -- this chapter, an introduction to what this
  interface is about, where its place is and why it is needed;

- Functions and use cases -- a presentation of high-level functions and
  use cases that drive this service component;

- Behaviour - Sequence diagrams -- behavioural diagrams that describe
  the flow between components;

- IAM - Service contract -- a list of REST operations that make up the
  API;

- IAM - Data contract -- the REST data model used for this service;

- Samples -- some samples that show how to use this API;

- Development Impact;

- How to's;

- Relevant links.

This interface provides a RESTful web service that allows the RINA
portal or national systems to interact with the Identity and Access
Management service that is one component part of the Case Processing
Services.

The Identity and Access Management service provides the following
capabilities:

- Central Authentication Server (CAS) -- provides a Single-Sign-On
  server for authenticating to RINA services (currently only CPI). This
  provides also a functionality for SAML 2.0 delegated authentication,
  LDAP authentication, etc;

- Identity provider configuration -- it is possible to choose between an
  internal and an external identity provider implementation. RINA offers
  an LDAP integration as a reference external identity provider
  implementation;

- Authentication -- the users are authenticated against the identity
  provider configured in CAS;

- Identity synchronization interface -- an interface for synchronization
  the users from the external source to the internal environment;

- External rules for process assignment -- an API for setting up rules
  that say who can manage what case type depending on the rules that can
  be configured externally.

# Functions and use cases 

The Identity and Access Management top-level function is a collection of
services that enables the system to securely control access to RINA
resources for internal or external users.

It comprises four basic functions as shows in the diagram:

> ![](media/image13.jpg){width="3.0076388888888888in"
> height="4.735416666666667in"}

*Figure 2. Identity and access management use cases*

A short description for each basic function:

- IAM Configuration - The RINA IAM can be configured to use the internal
  identity provider that is the system default source or an external
  data source;

- User authentication - When the user logs into the system, he must be
  authenticated against the configured identity provider;

- External-Internal synchronization -- When external identity provider
  is selected for managing the organization, a tool synchronizes all the
  users and groups from the external repository with the internal
  repository;

- External rules for process assignment -- Rules that say who can manage
  what process;

## IAM configuration 

The RINA system administrator must be able to configure the Identity and
Access Management module.

This module has two major configuration parts as depicted in the use
case below.

The 'Configure Authentication' use case enables the RINA system
administrator to choose the identity provider from one of the options
available. RINA currently provides following authentication providers:

- Internal (default) -- the users are authenticated against their
  username/password stored in RINA datastore.

- LDAP provider -- the users are authenticated against an external LDAP
  server. The user/group profiles are still to be stored (synchronized)
  in the internal datastore, however the passwords are not needed.

- SAML 2.0 provider -- enables to authenticate the users against an
  external SAML 2.0 identity provider. The user/group profiles are still
  to be stored (synchronized) in the internal datastore, however the
  passwords are not needed.

- JWT Token -- enables the authentication through a self-containing Java
  Web Token.

It is important to note that all external identity providers are used
for the user authentication only. The user and group profiles must still
be stored in the RINA datastore. RINA provides a synchronization
functionality to be able to create/update these profiles from external
databases.

There are no restrictions on the supported external identity providers,
however, they must be accessible from the RINA infrastructure (i.e.
firewalls settings, etc.).

The 'Configure Synchronizer Tool' use case sets up the configuration for
a tool that synchronizes users and groups profiles from the external
LDAP repository into the default repository. Synchronization from other
repositories (like SQL) are not provided out-of-thebox but there is an
import API which can be used. Another possibility is also to synchronize
the users/groups profiles directly into the Rina datastore.

The following properties should be at least specified for the user
synchronization tool:

- Server URL -- the URL of the external repository server;

- User credentials -- username and password for accessing the external
  identity provider;

- LDAP user search base -- organization and domain in LDAP server for
  users synchronization;

- LDAP group search base -- organization and domain in LDAP server for
  groups synchronization;

- Security authentication -- type of security used in given LDAP server;

- User and group filters -- provide a way to filter all the users and
  groups.

Apart from this, mappings between internal user and group properties and
LDAP attributes should be provided.

## IAM authentication 

This use case is a prerequisite of performing any actions in the RINA
application.

The user authentication ('Authenticate User' use case) is done either
against the internal repository or against an external identity provider
as depicted below:

> ![](media/image14.jpg){width="4.336805555555555in"
> height="2.160972222222222in"} *Figure 3. IAM Authentication use case*

The 'Authenticate User Internal' extended use case implements the use
case where the user logs into the system as a known RINA user and both
the username and password can be verified in the local repository.

The 'Authenticate User External' extended use case implements the use
case where user logs into the system as a known external repository user
and only the username can be verified in the local repository. The
internal repository does not store any password or other cryptographic
material, so the credentials validation takes place against an external
data source via a connector.

The reference external authentication implementation offered by RINA is
currently one of the following:

- LDAP

- Delegated SAML 2.0 Identity Provider

- JSON Web Token

## External - Internal repository synchronization 

In the case of the external authentication, the RINA system must
synchronize the users and groups from the external source as shown
below:

The synchronization takes place in one direction, from the external
source to the internal destination, so the external repository is never
changed.

The synchronization tool must perform all the CRUD (Create, Read,
Update, Delete) operations in the internal repository so that the users
and groups match as close as possible the attributes from the external
source.

The synchronization tool connects to both sources and performs the
following actions:

- It reads all the users from external repository and creates them in
  the internal repository;

- It reads all the groups from the external repository and creates them
  in the internal repository;

- Updates all the memberships (user, group, role) in internal repository
  to match the external membership.

> ![](media/image15.jpg){width="4.107638888888889in"
> height="1.7986111111111112in"} *Figure 4. External - Internal
> repository synchronisation*

## External rules for process assignment 

There are two parts to consider when dealing with the process
assignments:

- Configuration -- the management part where the rules for assigning are
  created and setup;

- Execution -- the action part, when the filter rules are being applied
  on the process.

> ![](media/image16.jpg){width="4.126805555555555in"
> height="1.6854166666666666in"} *Figure 5. External rules for process
> assignment use case*

### Execution of external rules 

The execution of external rules is triggered as shown in the figure
below, when a case is received or created.

> ![](media/image17.png){width="5.225833333333333in"
> height="1.7909722222222222in"} *Figure 6. Execution of external case
> assignment rules*

This triggers a method which calculates the case assignments based on
the case context and the defined assignment policies.

***Notes:***

- The assignment policies are defined by RINA administrator initially
  before users start to use RINA;

- The assignment policies / automatic rules are defined by RINA
  administrator;

- The user assignments created automatically can be later edited /
  changed by supervisors of each case;

- The case assignment policies are used to assign users and/or groups to
  individual cases when the cases are created (either locally, either
  received from another party); but to decide which users are allowed to
  create different types of cases in the first place, a special type of
  policies are used: "Creator policies". These have the same structure
  and are managed the same way as the regular policies;

- An administrator can decide to create as many policies as needed, but
  only policies that are actually assigned to targets are taken into
  account when calculating the assignments.

More technical details can be consulted in section *0*

*PDP - Case Assignment Policy* Decision Point*.*

### Logical components 

The process assignments have the following logical components:

- Sectors -- these are predefined sector areas the processes are being
  part of. (For instance Pension, Sickness, Family Benefits are sector
  examples);

- Process -- each sector is driven by one or more business processes
  (for example in the Pension sector there are currently defined several
  case types, "Invalidity Pension Claim" and "Old Age Pension Claim"
  being two of them);

- Application roles -- Each process has two application roles:

  - Process owner -- this is the party that creates and starts the whole
    case; o Counterparty -- this is the party that receives the initial
    case;

- User/ actor - An actor is a placeholder specified in the process
  definition for the users. Actors are the individuals called to
  complete a Task (they become -- potentially different - users in the
  course of each case). All human tasks have at least one actor
  assigned;

- Group -- A set of individual users, defined by the Administrator;

- Membership -- Users which are belonging, either individually or
  collectively, to a group with a specific role within it;

- Sender country;

- Assigned users/groups -- the users or group of users that can be
  assigned for each type of actor;

- Role -- The title/position/job of an individual user. The user roles
  consists in the following:

  - Manager/Supervisor; o Authorised Clerk; o Un-authorised Clerk; o
    Auditor; o Viewer; o Medical User; o VIP User;

The actions that the above described above user roles can perform are
described in the table below:

+---------------------------------------------+--------------+--------------+----------------+-----------+----------+-----------+-----+------------+
| **RINA**                                    | > Supervisor | > Authorised | > Unauthorised | > Auditor | > Viewer | > Medical | Vip | > Everyone |
|                                             |              |              |                |           |          |           |     |            |
| **USER ROLES**                              |              |              |                |           |          |           |     |            |
+:=========================+:=================+:============:+:============:+:==============:+:=========:+:========:+:=========:+:===:+:==========:+
|                          | > Assign Case    | ✓            |              |                |           |          |           |     |            |
+--------------------------+------------------+--------------+--------------+----------------+-----------+----------+-----------+-----+------------+
|                          | > Request        | ✓            | ✓            | ✓              | ✓         | > ✓      | ✓         | > ✓ | ✓          |
|                          | >                |              |              |                |           |          |           |     |            |
|                          | > Assignment     |              |              |                |           |          |           |     |            |
+--------------------------+------------------+--------------+--------------+----------------+-----------+----------+-----------+-----+------------+
| ![](media/image120.png)  | > Authorise      | ✓            |              |                |           |          |           |     |            |
|                          | >                |              |              |                |           |          |           |     |            |
|                          | > Assignment     |              |              |                |           |          |           |     |            |
+--------------------------+------------------+--------------+--------------+----------------+-----------+----------+-----------+-----+------------+
| > ![](media/image16.png) | > Create Case    |              | ✓            | ✓              |           |          |           |     |            |
|                          +------------------+--------------+--------------+----------------+-----------+----------+-----------+-----+------------+
|                          | > Create SED     |              | ✓            | ✓              |           |          |           |     |            |
|                          +------------------+--------------+--------------+----------------+-----------+----------+-----------+-----+------------+
|                          | > View SED       | ✓            | ✓            | ✓              | > ✓       | > ✓      |           |     |            |
|                          +------------------+--------------+--------------+----------------+-----------+----------+-----------+-----+------------+
|                          | > Send SED       | ✓            | ✓            |                |           |          |           |     |            |
|                          +------------------+--------------+--------------+----------------+-----------+----------+-----------+-----+------------+
|                          | > Request        |              |              | ✓              |           |          |           |     |            |
|                          | >                |              |              |                |           |          |           |     |            |
|                          | > Approval for   |              |              |                |           |          |           |     |            |
|                          | > sending        |              |              |                |           |          |           |     |            |
|                          +------------------+--------------+--------------+----------------+-----------+----------+-----------+-----+------------+
|                          | > Approve and    | ✓            | ✓            |                |           |          |           |     |            |
|                          | > Send SED       |              |              |                |           |          |           |     |            |
|                          +------------------+--------------+--------------+----------------+-----------+----------+-----------+-----+------------+
|                          | > Upload/Delete/ |              |              |                |           |          | ✓         |     |            |
|                          | > Download       |              |              |                |           |          |           |     |            |
|                          | > medical        |              |              |                |           |          |           |     |            |
|                          | > attachments    |              |              |                |           |          |           |     |            |
|                          +------------------+--------------+--------------+----------------+-----------+----------+-----------+-----+------------+
|                          | > View VIPs[^1]  |              |              |                |           |          |           | > ✓ |            |
|                          +------------------+--------------+--------------+----------------+-----------+----------+-----------+-----+------------+
|                          | > Change Case    | ✓            | ✓            | ✓              |           |          |           |     |            |
|                          | > Metadata[^2]   |              |              |                |           |          |           |     |            |
|                          +------------------+--------------+--------------+----------------+-----------+----------+-----------+-----+------------+
|                          | > Manual case    | ✓            | ✓            |                |           |          |           |     |            |
|                          | > archiving      |              |              |                |           |          |           |     |            |
|                          +------------------+--------------+--------------+----------------+-----------+----------+-----------+-----+------------+
|                          | > Manual case    | ✓            | ✓            |                |           |          |           |     |            |
|                          | > unarchiving    |              |              |                |           |          |           |     |            |
|                          +------------------+--------------+--------------+----------------+-----------+----------+-----------+-----+------------+
|                          | > Set/clear      | ✓            | ✓            | ✓              |           |          |           |     |            |
|                          | > alarms         |              |              |                |           |          |           |     |            |
|                          +------------------+--------------+--------------+----------------+-----------+----------+-----------+-----+------------+
|                          | > View case      | ✓            | ✓            | ✓              | > ✓       | > ✓      | ✓         | > ✓ | ✓          |
|                          | > metadata[^3]   |              |              |                |           |          |           |     |            |
+--------------------------+------------------+--------------+--------------+----------------+-----------+----------+-----------+-----+------------+

+-------------------------+---------------+------+------+--------+-----+-----+----+---+-----+
|                         | Download      | ✓    | ✓    | ✓      | > ✓ | > ✓ |    |   |     |
|                         | standard      |      |      |        |     |     |    |   |     |
|                         | attachments   |      |      |        |     |     |    |   |     |
|                         +---------------+------+------+--------+-----+-----+----+---+-----+
|                         | Upload/delete |      | ✓    | ✓      |     |     |    |   |     |
|                         | standard      |      |      |        |     |     |    |   |     |
|                         | attachments   |      |      |        |     |     |    |   |     |
|                         +---------------+------+------+--------+-----+-----+----+---+-----+
|                         | Add/delete    | ✓    | ✓    | ✓      | > ✓ | > ✓ |    |   |     |
|                         | comments      |      |      |        |     |     |    |   |     |
+:=======================:+:==============+:====:+:====:+:======:+====:+:===:+:==:+:=:+:===:+
| ![](media/image170.png) | View Audit    | ✓    |      |        | ✓   |     |    |   |     |
+-------------------------+---------------+------+------+--------+-----+-----+----+---+-----+

> *Table 2: RINA User Roles and the permitted actions*

For automatic process assignment, external rules filtering policies can
be used.

+-----------------------------------------------------------------------+
| **Notes:**                                                            |
|                                                                       |
| > ![](media/image25.png){width="0.5833333333333334in"                 |
| > height="0.5833333333333334in"}*A User/Clerk can have multiple       |
| > roles. A user with multiple roles can perform any action permitted  |
| > by all the assigned roles. As an example, an authorised clerk that  |
| > is also a medical user can send SEDs (permitted by the authorised   |
| > clerk role) and also read classified medical attachments (permitted |
| > by the medical user role);*                                         |
| >                                                                     |
| > *In general, Medical and VIP roles have limited permissions (view   |
| > metadata and handle Medical and VIP data) and can be considered as  |
| > [supplementary]{.underline} roles that are assigned to specific     |
| > users when access to critical data is required;*                    |
| >                                                                     |
| > *Only VIP users are able to classify a case as 'sensitive', or      |
| > declassify it to back to a normal one (by selecting/unselecting the |
| > "Sensitive" flag in the "Case Metadata" popup);*                    |
| >                                                                     |
| > *VIP user may set "Sensitive Case" flag BUT in order to create/edit |
| > documents must be also authorised/unauthorised clerk. In order to   |
| > send documents the clerk must be authorised. In order to view case  |
| > documents, the clerk must be authorised/unauthorised, supervisor    |
| > and/or viewer;*                                                     |
| >                                                                     |
| > *Medical user can classify a standard attachment as medical, or     |
| > declassify a medical to a standard one. To add must be also         |
| > authorised/unauthorised*                                            |
+=======================================================================+

### Illustrative scenario example -- external filtering rules 

For external filtering rules, an illustrative example for each
application role is given below: **Process owner example**

The organization has a number of branches.

Each branch has its own departments in the areas of the well-known
sectors.

Each department has people that can be part of other branches as well.

One external rule that must be supported is the following:

- When a user creates a case all the users from the group the owner is
  part of should be assigned automatically for that case. If the user
  creator is part of more groups (for example the user is both in the
  Pension and Sickness sectors) the group should be selected.

**Counterparty example**

The organization has a number of user experts that can deal with cases
from specific parts of the world.

One external rule that must be supported is the following:

- When a case arrives from Germany, all the users from the Western
  Europe group are automatically assigned to the case.

### XACML Concepts 

The concepts used in the current document for the external rules for
process assignment consist in a re-interpretation of the XACML concepts.

A mapping to the XACML concepts is introduced in the table below.

+---------------------------------+---------------------------------+
| **XACML concept**               | **RINA concept**                |
+:================================+:================================+
| **PAP**                         | > Assignment Policies           |
|                                 | > Administration:               |
| Policy Administration Point.    | >                               |
|                                 | > the /AssignmentPolicies REST  |
|                                 | > API & the Process Assignments |
|                                 | > tab from RINA Admin           |
|                                 | >                               |
|                                 | > Portal.                       |
+---------------------------------+---------------------------------+
| **Policy**                      | > Policy                        |
|                                 |                                 |
| A Policy represents a single    |                                 |
| access control policy,          |                                 |
| expressed through a set of      |                                 |
| Rules.                          |                                 |
+---------------------------------+---------------------------------+
| **PolicySet**                   | > Policy group.                 |
|                                 |                                 |
| A PolicySet is a container that |                                 |
| can hold other Policies or      |                                 |
| PolicySets.                     |                                 |
+---------------------------------+---------------------------------+
| **Rule**                        | > Rule.                         |
|                                 |                                 |
| A policy can have any number of |                                 |
| Rules which contain the core    |                                 |
| logic of an XACML policy.       |                                 |
+---------------------------------+---------------------------------+
| **Target**                      | > Target: A fragment of the     |
|                                 | > process definitions tree to   |
| Basically a set of simplified   | > which a policy can be         |
| conditions for the subject,     | > associated to. (i.e. Sector,  |
| resource, and action that must  | > Process Definition,           |
| be met for a policy set,        | > Application role, etc.)       |
| policy, or rule to apply.       |                                 |
+---------------------------------+---------------------------------+
| **Subject**                     | > The collection of             |
|                                 | > groups/users that will be     |
| The entity requesting access.   | > assigned to a specific actor. |
+---------------------------------+---------------------------------+
| **Resource**                    | > The case instance.            |
|                                 |                                 |
| The resource that is being      |                                 |
| accessed.                       |                                 |
+---------------------------------+---------------------------------+
| **Action**                      | > The assignment as an actor to |
|                                 | > the case instance.            |
| The type of access requested on |                                 |
| the resource.                   |                                 |
+---------------------------------+---------------------------------+
| **Condition**                   | > Condition: a collection of 0  |
|                                 | > or more conditions, which     |
| A Boolean function. If the      | > must be met in order for a    |
| Condition evaluates to true,    | > rule to be applied.           |
| then the Rule\'s Effect is      |                                 |
| returned.                       |                                 |
+---------------------------------+---------------------------------+
| **Combining algorithms**        | > There are only use 3 types of |
|                                 | > combining algorithms:         |
| This algorithm is responsible   |                                 |
| for combining outcome from      | - the rules inside a policy are |
| multiple policy evaluations.    |   always combined with the      |
|                                 |   \"first matching rule\"       |
|                                 |   algorithm;                    |
|                                 |                                 |
|                                 | - the policies, except          |
|                                 |   *"Creator Policy"* inside a   |
|                                 |   policy group are always       |
|                                 |   combined with the \"intersect |
|                                 |   outcomes\" algorithm; The     |
|                                 |   intersection combination is   |
|                                 |   applicable inside the same    |
|                                 |   group;                        |
|                                 |                                 |
|                                 | - when a target has more        |
|                                 |   policies or policy groups     |
|                                 |   assigned to it , there is an  |
|                                 |   implied combining algorithm   |
|                                 |   of the results: "union        |
|                                 |   outcomes";                    |
+---------------------------------+---------------------------------+
| **Effect**                      | > In RINA, all rules have an    |
|                                 | > implied \"permit\" effect.    |
| Permit/Deny.                    |                                 |
+---------------------------------+---------------------------------+
| **PDP**                         | > Case Assignment Policy        |
|                                 | > Decision Point                |
| Policy Decision Point.          | >                               |
|                                 | > It evaluates the assignment   |
|                                 | > policies for each case        |
|                                 | > instance and decides which    |
|                                 | > users/groups will be assigned |
|                                 | > as actors of this case        |
|                                 | > instance.                     |
|                                 | >                               |
|                                 | > (see section 0                |
|                                 | >                               |
|                                 | > PDP - Case Assignment Policy  |
|                                 | > Decision                      |
|                                 | >                               |
|                                 | > Point)                        |
+---------------------------------+---------------------------------+

# Behaviour 

RINA is shipped with a Central Authentication Server (CAS), which
handles the authentication of a user. Internal, as well as external
authentication is always managed through the CAS server. Below, you will
find the authentication schema used by RINA CPI (and possibly other
system components).

The CAS server acts as a single-sign-on server, similar to the former
OAuth 2 authentication server, however it provides many out-of-the-box
integrations with third party systems and authentication protocols.

## IAM authentication 

This diagram shows the general flow for user authentication, from the
moment the client initiates the login until it receives the
authenticated session cookie. It displays the sequence of the steps,
independent from the type of authentication that is used.

![](media/image26.jpg){width="5.753472222222222in" height="4.05in"}

*Figure 7. IAM Authentication sequence diagram*

The RINA CPI uses the CAS 3.0 protocol for authentication (specification
can be found here:
https://apereo.github.io/cas/6.2.x/protocol/CAS-Protocol.html).
Following parties are present in the scenario:

- CAS Authentication Server -- the SSO CAS server providing the
  authentication of users which want to use a given service.

- Service -- CAS is providing the authentication for registered
  services. In our case, the registered services are:

o RINA REST CPI module

- Portal/UI -- is the client, which tries to access the service and
  needs to obtain an authentication from the CAS server.

The communication with the BPM Engine is executed through a single
system user.

To understand the interaction of the parties, it is first required to
define a couple of terms from the CAS 3.0 protocol. The protocol can be
viewed similar to OAuth 2.0, however, instead of tokens the focus is on
tickets. CAS issues 2 types of tickets for our context:

- Ticket-Granting-Ticket (TGT) -- is generated by the CAS server after a
  successful authentication and this ticket is a long-term ticket. TGT
  is used for generating service tickets (ST), which are used for
  authentication in the service. The service itself is agnostic of any
  credentials of the authenticated user.

- Service Ticket (ST) -- is generated by the CAS server for the client,
  which has already been authenticated (i.e. has obtained a TGT) when
  trying to access the service. ST is a short-term valid ticket (default
  is 10 seconds) and can be validated only once. Any ST, which has
  already been validated would fail in another validation.

After successfully obtaining a service ticket, this must be validated by
the service and if it is valid, an authenticated and authorized session
is created associated with a session ID.

Following is the description of the authentication process as shown on
the figure 7:

- ***Step 1:*** RINA Portal (or any other client) wants to access the
  RINA CPI (the service registered in CAS). It redirects the user to the
  CAS server with the service ID parameter.

- ***Step 2:*** The user authenticates against the configured identity
  provider (RINA internal, LDAP, SAML 2.0 or by a JWT token). If the
  user is authenticated successfully, a SSO session in the CAS server is
  created (represented by the TGT).

- ***Step 3:*** The CAS server generates a service ticket (ST) for the
  service ID sent in the request in the point 1. The service ID is also
  the URL which receives the ST in the HTTP 302 Redirect response. The
  user is redirected to the provided service ID URL with the generated
  service ticket.

- ***Step 4:*** The client calls a "login" method of the RINA CPI with
  the service ticket and the service ID, which was used to obtain a
  service ticket.

- ***Step 5:*** The RINA CPI security module authenticates the received
  service ticket by calling the CAS server API method. To do this, it
  sends the ST together with the retrieved Service ID to the validation
  endpoint of the CAS server.

- ***Step 6:*** The CAS Server returns the authentication response,
  which contains the user ID (optionally also other attributes).

- ***Step 7:*** The security module in the RINA CPI tries to find the
  profile for the received user ID and creates an authenticated session.

- ***Step 8:*** The security module in the RINA CPI returns back to the
  client an HTTP-only cookie with the name JSESSIONID, which must be
  sent with any subsequent request to the RINA CPI.

.

The CAS server is provided as **eessi-cas-server** maven project and is
built as a deployable WAR file. It can be deployed in the same server as
the RINA CPI module or on a separate one. The maven project contains the
custom internal authentication module and accesses the RINA datastore
through a dependency on the RINA services.

Important to notice: the CAS protocol uses HTTP redirects or other HTTP
communications, which can contain the TGT or ST. None of those should
ever get disclosed. From this reason, it is always **recommended to use
SSL/TLS for securing the communication channel**.

### Internal User Authentication 

As stated earlier in this document, the internal authentication (as well
as the external) is always managed by the CAS server. The difference
lies in the storage of the authentication material. The internal user
authentication authenticates users against their profiles stored in the
RINA internal database.

To successfully authenticate a user, the authentication module needs the
username and the password (RINA only stores a hash of a password and a
random salt used with the hashing function). Once the user enters the
username and password following steps are performed by the
***EessiUserAuthenticationHandler***:

- Find a user with by the provided username, which is not marked as
  deleted. If the user is not found an exception is thrown.

- The provided password is hashed together with the salt stored in the
  user document. This hash is then compared with the one stored in the
  user document. If it does not match an exception is thrown.

- The \"*isEnabled*\" flag on the user document is checked. If the value
  is false an exception is thrown.

- The \"*isLocked*\" flag on the user document is checked. If the value
  is false an exception is thrown.

![](media/image27.jpg){width="6.177084426946632in"
height="2.828472222222222in"}

Figure 8 depicts the sequence diagram when using the internal
authentication in the context of the RINA services.

*Figure 8. Internal user authentication*

### External User Authentication -- LDAP reference implementation 

This sequence diagram is a zoom-in for the external IAM authentication
with LDAP diagram that shows how the EESSIAuthenticationService is
implemented to give access to an external data source.

> ![](media/image28.jpg){width="6.102083333333334in"
> height="3.876388888888889in"} *Figure 9. External user authentication*

- Based on configuration of authentication handler in cas.properties
  file it is determined what kind of authentication is used.

- It is possible to use internal (PostgreSQL) and external (LDAP)
  authentication in the same time.

- It is also possible to use multiple LDAP sources. In this case
  authentication service iterates over defined sources and uses the
  first one which successfully authenticates user.

If authentication is not successful in any of the sources, exception is
thrown.

## WebSocket Authentication 

The WebSocket connection uses the same authentication context as the
usual HTTP connection to the CPI. During the handshake, the underlying
HTTP connection is inspected and it's security context is identified. If
it does not contain the authenticated principal, the connection is
closed and an exception is thrown.

When using the fullstack RINA together with the portal, all of the above
described functionality happens automatically on the background and
there is no need for any configuration change. The WebSocket connection
is always initiated first after successful login, hence it will contain
the authenticated session.

However, if a third party client needs to establish a WebSocket
connection it must first get an authenticated session from the CPI. Once
this is done, it needs to be used when connecting to a WebSocket (i.e.
the JSESSIONID cookie must be sent with the request).

The default behaviour, where the authentication for WebSocket connection
is required, can be overridden by setting the following configuration
parameter in the **casAuthentication.conf** file to false:
authentication.ws.enabled=false

## LDAP- synchronization 

This sequence diagram shows how the synchronization tool interacts with
the LDAP source and PostgreSQL DB.

> ![](media/image29.jpg){width="6.197222222222222in"
> height="3.2391666666666667in"}

*Figure 10. External LDAP synchronization*

The synchronization takes place in one direction, from the LDAP source
to the DB destination, so the LDAP directory is never changed. The steps
from the diagram are explained bellow:

- Reads all Users in the source LDAP directory

- Creates or updates Users in PostgreSQL which orgin is given LDAP
  configuration

- Reads all Groups in the source LDAP directory

- Creates or updates Groups in PostgreSQL which origin is given LDAP
  configuration

- Retrieves all Users that are belonging to the groups in the source
  LDAP directory

- Retrieves all Users that are belonging to the groups in PostgreSQL

Please note that if another external identity provider besides LDAP is
used, this sequence diagram is still valid, just that instead of the
LDAP source there will be the other external source.

> ***NOTE:***
>
> *The following special characters should be escaped when used in a
> distinguished name: Plus sign (+), Semicolon (;), Comma (,), Backward
> slash (\\), Double quote (\"), Less than (\<), Greater than (\>),
> Pound sign (#)*

# IAM external interfaces 

RINA IAM supports the following external authentication providers:

- LDAP

- SAML 2.0

- JSON Web Token (JWT)

RINA offers a REST endpoint implementation as a part of the Case
Processing Interface (CPI) for configuring the institution LDAP data
source synchronization.

The actual authentication REST flow from the sequence diagram Figure 3
is described in the specifications document ***EESSI-RINA Case
Processing Interface*** in the chapter ***2.1 User Authentication***.

A detailed description of the Service and Data contracts is given in the
automatically generated Technical reference guide ("*EESSI -- RINA Case
Processing (CPI) -- Reference*") that provides all the necessary
technical information about the REST API.

# Configuration of SAML 2.0 

The CAS authentication server provides an option to use delegated
authentication in terms of the SAML 2.0 protocol. In this case a user
can get authenticated by an external delegated SAML 2.0 identity
provider.

## Limitations 

### IdP SingleSignOnService Binding 

RINA authentication server (CAS) currently supports delegated SAML2.0
IdP integration in HTTP-Redirect Binding, i.e. the identity provider
meta-data must define at least one SingleSignOnService with following
attributes:

\<md:SingleSignOnService
Binding=\"urn:oasis:names:tc:SAML:2.0:bindings:HTTP-

Redirect\" Location=\"\<URL\>\" index=\"\<INDEX\>\"
isDefault=\"\<IS_DEFAULT\>\"/\>

### User Identification in RINA Context 

The *userId,* which will be used as a unique user identifier to obtain
his profile in RINA is retrieved from the Subject's *NameId* element.
That's why the *NameId* should have a "*persistent*" or "*unspecified*"
*NameFormat* (see chapter "8.3 Name Identifier Format Identifiers" in
[*http://docs.oasis-open.org/security/saml/v2.0/saml-core-2.0-os.pdf*)](http://docs.oasis-open.org/security/saml/v2.0/saml-core-2.0-os.pdf).

## Workflow 

The authentication process starts as described in the *section 3.1*.
However, the user does not provide any username/password on the CAS
server login page. Instead, he selects to authenticate with the SAML 2.0
identity provider by clicking the red button as shown on the next
figure:

> ![](media/image30.jpg){width="3.618472222222222in"
> height="2.911111111111111in"}

*Figure 11. Identity and access management use cases*

This redirects the user to the identity provider where he logs in. After
a successful log in, the SAML 2.0 assertions are sent back to the CAS
server, which creates the TGT and ST for the user and the user continue
back to the RINA page, where the CPI module authenticates the ST in the
same way as with any other authentication provider.

The workflow with all the RINA components involved is depicted on the
Figure 12.

![](media/image31.jpg){width="6.090278871391076in"
height="3.9606955380577427in"}

*Figure 12. Sequence diagram with delegated SAML 2 IdP*

## Configuration 

To allow to authenticate against an external SAML 2.0 identity provider,
two crucial configurations must be performed:

- Insert the SAML 2.0 settings into the ***cas.properties*** file.

- Import user accounts into RINA IAM datastore with the correct username
  field.

### CAS Configuration 

The CAS configuration regarding the SAML 2.0 authentication can be found
at
[[https://apereo.github.io/cas/6.2.x/integration/Delegate-Authentication.html]{.underline}](https://apereo.github.io/cas/6.2.x/integration/Delegate-Authentication.html)
*[and]{.underline}*
[https://apereo.github.io/cas/6.2.x/integration/Configuring-SAML-SP-Integrations.html.](https://apereo.github.io/cas/6.2.x/integration/Configuring-SAML-SP-Integrations.html)

Our provided CAS server is already built with all the needed
dependencies. The remaining part is to correctly setup the configuration
properties in the ***cas.properties*** file (this file is located
usually somewhere in the shared location -- consult the RINA
installation KIT tutorial to locate the file).

Following is an example SAML 2.0 configuration from the above mentioned
file:

\### Following lines must be commented, to not require the RINA
authentication handler to

\### always succeed. This is because it is now enough to authenticate a
user through the SAML2

\### delegated authentication handler

\# cas.authn.policy.req.tryAll=true

\# cas.authn.policy.req.handlerName=eessiUserAuthenticationHandler

+-------------------------------------------------------------------------------------------------------------------------------------+
| \# cas.authn.policy.req.enabled=true                                                                                                |
|                                                                                                                                     |
| \# SAML 2.0 configuration                                                                                                           |
|                                                                                                                                     |
| cas.authn.pac4j.saml\[0\].keystorePassword=pac4j-demo-passwd cas.authn.pac4j.saml\[0\].privateKeyPassword=pac4j-demo-passwd         |
|                                                                                                                                     |
| cas.authn.pac4j.saml\[0\].serviceProviderEntityId=urn:mace:saml:pac4j.org                                                           |
|                                                                                                                                     |
| cas.authn.pac4j.saml\[0\].serviceProviderMetadataPath=file:/all/NAS/configuration/cas/config/spmetadata.xml                         |
|                                                                                                                                     |
| cas.authn.pac4j.saml\[0\].keystorePath=file:/all/NAS/configuration/cas/config/samlKeystore.jks                                      |
|                                                                                                                                     |
| cas.authn.pac4j.saml\[0\].identityProviderMetadataPath=https://dev648667.oktapreview.com/app/exkbqk7h6afPxMvQ90h7/sso/saml/metadata |
| cas.authn.pac4j.saml\[0\].maximumAuthenticationLifetime=18000 cas.authn.pac4j.saml\[0\].clientName=SAML2Client0                     |
+=====================================================================================================================================+

**Settings parameter:**

- *keystorePassword* -- java keystore password of the keystore where
  some keying material for communication with this identity provider
  will be stored

- *privateKeyPassword* -- password which is used to access the private
  key

- *serviceProviderEntityId* -- entity ID of the service provider, which
  should also be used in the service provider metadata

- *serviceProviderMetadataPath* -- location of the service provider
  metadata file (typically stored near the CAS configuration file)

- *keystorePath* -- location of the keystore (if the keystore does not
  exist, it will be created). This password of the keystore (and of the
  primary key) must be the ones specified.

- *maximumAuthenticationLifetime* -- lifetime of this authentication in
  seconds.

- *clientName* -- unique identifier of this delegated IDP

Important to notice is, that when using a CAS REST API to obtain the TGT
or ST, CAS will not automatically resend any username/password to the
delegated identity provider. In this case a custom implementation must
be used to handle this.

After the CAS server is started, it will automatically generate all the
keystores and metadata files needed for the SAML2 to work inside the CAS
configuration directory. However, depending on the configuration of the
tomcat server, where CAS is deployed, the sp-metadata.xml file might be
generated containing wrong domain name for the SAML2 endpoints. In this
case, the file sp-metadata.xml must be opened and manually updated with
the correct domain name.

### RINA Configuration 

If a delegated SAML 2.0 identity provider is used, the user is
authenticated on a different system and CAS will receive the SAML 2.0
assertion. The RINA CPI security module will always get the unique
identifier of the user when validating the service ticket.

The user objects must still be present in the RINA database and be able
to be found by this unique identification. Because the user objects are
identified by the username, this requires the user objects, which are
able to log in through a SAML 2.0 identity provider, to have the
username equal to this identifier.

CAS provides two ways how this user identifier will be returned:

- Typed - includes a predefined type prefix. This is in case of SAML2.0
  following org.pac4j.saml.profile.SAML2Profile#\<the-actual-userid\>

- Untyped -- in this case only the user id will be returned without the
  type prefix.

\<the-actual-userid\>

This can be controlled by the following configuration setting in the
***cas.properties*** file:

\# use typed identifier cas.authn.pac4j.typedIdUsed=true

\# use untyped identifier cas.authn.pac4j.typedIdUsed=false

Depending on the configuration used, RINA must contain a user object
with the username set to that identifier (either typed or untyped).

# Configuration for JWT Authentication 

To find out more about the CAS configuration when using JWT token for
authentication please also read this document:

https://apereo.github.io/cas/6.2.x/installation/Configure-ServiceTicket-JWT.html

To enable the JWT authentication following properties need to be defined
in the service configuration file configuration file:

{

\"@class\" : \"org.apereo.cas.services.RegexRegisteredService\",

\"name\" : \"EESSI Rina CPI\",

\"id\" : 101,

\"theme\" : \"rina\",

\"serviceId\": \"\^(https\|http)://localhost.\*\",

\"attributeReleasePolicy\" : {

\"@class\" : \"org.apereo.cas.services.ReturnAllAttributeReleasePolicy\"

},

\"properties\" : {

\"@class\" : \"java.util.HashMap\",

\"jwtSigningSecret\" : {

\"@class\" :
\"org.apereo.cas.services.DefaultRegisteredServiceProperty\",

\"values\" : \[ \"java.util.HashSet\", \[ \<SIGNATURE_KEY\> \] \]

},

\"jwtEncryptionSecret\" : {

\"@class\" :
\"org.apereo.cas.services.DefaultRegisteredServiceProperty\",

\"values\" : \[ \"java.util.HashSet\", \[ \<ENCRYPTION_KEY\> \] \]

},

\"jwtSigningSecretAlg\" : {

\"@class\" :
\"org.apereo.cas.services.DefaultRegisteredServiceProperty\",

\"values\" : \[ \"java.util.HashSet\", \[ \<SIGNING_ALGORITHM\> \] \]

},

\"jwtEncryptionSecretAlg\" : {

\"@class\" :
\"org.apereo.cas.services.DefaultRegisteredServiceProperty\",

\"values\" : \[ \"java.util.HashSet\", \[ \<ENCRYPTION_ALGORITHM\> \] \]

},

\"jwtEncryptionSecretMethod\" : {

\"@class\" :
\"org.apereo.cas.services.DefaultRegisteredServiceProperty\",

\"values\" : \[ \"java.util.HashSet\", \[ \<ENCRYPTION_SECRET_METHOD\>
\] \]

}

}

}

The JWT token is a self-containing token, which contains the user
information. In this kind of authentication, there is no external system
connected to the process, but everything is contained within the token.
Once this is successfully authenticated a service ticket is generated
and the authentication process continues within the CAS 3.0 protocol.

Following is a sequence of HTTP calls (with *CURL*), which can be used
to obtain an authenticated session by providing a JWT token instead of
username/password.

+----------------------------------------------------------------------------------+
| curl -ki -XGET                                                                   |
| \"\<SERVER_URL\>/eessiCas/login?service=\<SERVICE_ID_URL\>&token=\<JWT_TOKEN\>\" |
|                                                                                  |
| HTTP/1.1 302 Found                                                               |
|                                                                                  |
| Server: Apache-Coyote/1.1 Cache-Control: no-store Pragma:                        |
|                                                                                  |
| Expires:                                                                         |
|                                                                                  |
| Strict-Transport-Security: max-age=15768000 ; includeSubDomains                  |
|                                                                                  |
| X-Content-Type-Options: nosniff                                                  |
|                                                                                  |
| X-Frame-Options: DENY                                                            |
|                                                                                  |
| X-XSS-Protection: 1; mode=block                                                  |
|                                                                                  |
| Set-Cookie: TGC=\<TGC_COOKIE_VALUE\>; Path=/eessiCas/; Secure; HttpOnly          |
|                                                                                  |
| Location: \<SERVICE_ID_URL\>?ticket=\<SERVICE_TICKET\> Content-Length: 0         |
|                                                                                  |
| Date: Wed, 28 Feb 2018 09:31:52 GMT                                              |
+==================================================================================+

With the generated service ticket, you are able to obtain the
authenticated session by calling the REST CPI login method.

# Configuration of Single-Sign-On 

The CAS authentication server provides Single-Sign-On(SSO) capabilities.
This means, that if the authenticated SSO session (represented by the
TGC -- ticket-granting-cookie) is still valid, the user does not have to
provide credentials again and will be automatically granted a Service
Ticket upon accessing CAS login page.

This behaviour is important when changing context of the application. In
the case of RINA, we have the following application context:

• Case processing interface (together with the administration part)

A user will receive two separate JSESSION_ID cookies for each context.
In order for the user not provide his credentials every time when
switching the contexts, the SSO will automatically assign a
Service-Ticket to the user if he is already signed in the CAS.

By default, this behaviour is available only if the channel is secure,
i.e. SSL/TLS is used on the CAS. If the CAS is deployed without SSL/TLS
configured, the user will have to provide his credentials every time he
is switching contexts or the session will expiry.

We **STRONGLY** recommend to use SSL/TLS. However, if the SSL/TLS is not
used, there is a possibility how to enable the SSO behaviour anyway:

- Set the secure flag on the Tomcat connector to "**true"**, where the
  CAS is deployed:

> *\<Connector port=\"8080\" protocol=\"HTTP/1.1\"
> connectionTimeout=\"20000\" secure=\"true\" /\>*

- In the *"cas.properties"* file add the following configuration
  property:

> *cas.tgc.secure=false*

Please keep in mind, that this setting can be understood as a security
breach, because the TGC cookie is the SSO security context holder.
Making this change in the configuration will enable transferring the
cookie through an unsecure connection.

# Other Authentication Plugins 

To keep the size of the binary of RINA CAS authentication server
reasonably big, only some of the authentication plugins are built in and
were tested against a sample environment:

- Delegated authentication (SAML 2.0, OAuth2, OpenID and CAS) -- see

> *"https://apereo.github.io/cas/6.2.x/integration/Delegate-Authentication.htmlJWT"*

- Token Authentication -- see

> "*https://apereo.github.io/cas/6.2.x/installation/Configure-ServiceTicket-JWT.html"*

LDAP Authentication -- see
https://apereo.github.io/cas/6.2.x/installation/LDAPAuthentication.htmlRINA
CAS authentication server supports, however, other authentication
mechanisms as well.

## Other Authentication Plugins 

The recommended way to install other authentication plugins is to extend
the WAR artefact of the RINA CAS Server with the maven-war-plugin as a
war overlay. This way the developers are free to add additional
dependencies or even custom code. For this to work you have to manually
install the artefact file into your local repository:

mvn install:install-file -Dfile=\<path to eessiCas.war\>

This command (depending on you maven version, please see
[*https://maven.apache.org/guides/mini/guide-3rd-party-jars-local.html*](https://maven.apache.org/guides/mini/guide-3rd-party-jars-local.html)
) will put the eessiCas.war artefact into your maven repository. The
next step is to create a new maven project with the WAR packaging and
include the following into the pom.xml file (example is just for
demonstration purposes):

+-------------------------------------------------------------------------------------------------------------------------------+
| \<project xmlns=\"http://maven.apache.org/POM/4.0.0\" xmlns:xsi=\"http://www.w3.org/2001/XMLSchema-                           |
|                                                                                                                               |
| instance\" xsi:schemaLocation=\"http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd\"\>             |
| \<modelVersion\>4.0.0\</modelVersion\>                                                                                        |
|                                                                                                                               |
| \<groupId\>com.example.rinacas\</groupId\>                                                                                    |
|                                                                                                                               |
| \<artifactId\>custom-cas\</artifactId\>                                                                                       |
|                                                                                                                               |
| \<version\>0.0.1-SNAPSHOT\</version\>                                                                                         |
|                                                                                                                               |
| \<packaging\>war\</packaging\>                                                                                                |
|                                                                                                                               |
| \<name\>custom-cas\</name\>                                                                                                   |
|                                                                                                                               |
| \<properties\>                                                                                                                |
|                                                                                                                               |
| \<cas.version\>6.1.6\</cas.version\>                                                                                          |
|                                                                                                                               |
| \<maven.compiler.source\>11\</maven.compiler.source\>                                                                         |
|                                                                                                                               |
| \<maven.compiler.target\>11\</maven.compiler.target\>                                                                         |
|                                                                                                                               |
| \<project.build.sourceEncoding\>UTF-8\</project.build.sourceEncoding\>                                                        |
|                                                                                                                               |
| \<rina.version\>6.2.1\</rina.version\>                                                                                        |
|                                                                                                                               |
| \</properties\>                                                                                                               |
|                                                                                                                               |
| \<build\>                                                                                                                     |
|                                                                                                                               |
| \<finalName\>custom-cas\</finalName\>                                                                                         |
|                                                                                                                               |
| \<plugins\>                                                                                                                   |
|                                                                                                                               |
| \<plugin\>                                                                                                                    |
|                                                                                                                               |
| \<groupId\>org.apache.maven.plugins\</groupId\>                                                                               |
|                                                                                                                               |
| \<artifactId\>maven-war-plugin\</artifactId\>                                                                                 |
|                                                                                                                               |
| \<version\>3.0.3\</version\>                                                                                                  |
|                                                                                                                               |
| \<configuration\>                                                                                                             |
|                                                                                                                               |
| \<warName\>custom-cas\</warName\>                                                                                             |
|                                                                                                                               |
| \<failOnMissingWebXml\>false\</failOnMissingWebXml\>                                                                          |
|                                                                                                                               |
| \<recompressZippedFiles\>false\</recompressZippedFiles\>                                                                      |
|                                                                                                                               |
| \<archive\>                                                                                                                   |
|                                                                                                                               |
| \<compress\>false\</compress\>                                                                                                |
|                                                                                                                               |
| \<manifestFile\>\${project.build.directory}/war/work/eu.ec.dgempl.eessi/eessi-casserver/META-INF/MANIFEST.MF\</manifestFile\> |
|                                                                                                                               |
| \</archive\>                                                                                                                  |
|                                                                                                                               |
| \<overlays\>                                                                                                                  |
|                                                                                                                               |
| \<overlay\>                                                                                                                   |
+===============================================================================================================================+

\<groupId\>eu.ec.dgempl.eessi\</groupId\>

\<artifactId\>eessi-cas-server\</artifactId\>

\</overlay\>

\</overlays\>

\</configuration\>

\</plugin\>

\<plugin\>

\<groupId\>org.apache.maven.plugins\</groupId\>

\<artifactId\>maven-compiler-plugin\</artifactId\>

\<version\>3.3\</version\>

\</plugin\>

\</plugins\>

\</build\>

\<dependencies\>

\<dependency\>

\<groupId\>eu.ec.dgempl.eessi\</groupId\>

\<artifactId\>eessi-cas-server\</artifactId\>

\<version\>\${rina.version}\</version\>

\<type\>war\</type\>

\<scope\>runtime\</scope\>

\</dependency\>

\<!---- Other Dependencies \--\>

\</dependencies\>

\</project\>

After building such project, the resulting WAR file can be deployed
instead of the one provided. Depending on the name of the resulting
deployment and it's context you may need to also change the
configuration files of RINA.

To see other authentication plugins and their configuration please visit
the following link:
https://apereo.github.io/cas/6.2.x/installation/Configuring-AuthenticationComponents.html.

If none of the provided authentication plugins is well suited for your
environment, there is also a possibility to implement a custom plugin by
yourself. To learn more about the way to implement you custom
authentication handler, follow this documentation:
https://apereo.github.io/cas/6.2.x/installation/Configuring-Custom-Authentication.html
. The custom implementation can be included as a source code in the
maven WAR overlay as described earlier.

> ***NOTE:***
>
> *There is no support for the overlaying of the RINA CAS Server module
> and using other plugins or custom implementations than the ones
> provided in the binary release. This is due to the fact, that it is
> not manageable for the EESSI team to test all the plugins and the
> possible scenarios, nor the custom implementations.*

# Samples 

## Update LDAP connection settings request 

PUT /Configurations/LdapConnectionSettings

{

\"id\": \"example_id\",

\"version\": 1,

\"institutionId\": \"institution_name\",

\"providerUrl\": \"ldap://provider_address:389\",

\"securityAuthentication\": \"simple\",

\"user\": \"user@domain.name\",

\"password\": \"secretPassword\",

\"ldapUserSearchBase\": \"OU=istitution,DC=domain,DC=suffix\",

\"ldapGroupSearchBase\": \"OU=istitution_group,DC=domain,DC=suffix\",

\"userSearchString\": null,

\"groupSearchString\": null

}

## Get LDAP connection settings response 

+-----------------------------------------------------------------------+
| GET /Configurations/LdapConnectionSettings/{institutionId} {          |
|                                                                       |
| \"id\": \"example_id\",                                               |
|                                                                       |
| \"version\": 1,                                                       |
|                                                                       |
| \"institutionId\": \"institution_name\",                              |
|                                                                       |
| \"providerUrl\": \"ldap://provider_address:389\",                     |
|                                                                       |
| \"securityAuthentication\": \"simple\",                               |
|                                                                       |
| \"user\": \"user@domain.name\",                                       |
|                                                                       |
| \"password\": \"secretPassword\",                                     |
|                                                                       |
| \"ldapUserSearchBase\": \"OU=istitution,DC=domain,DC=suffix\",        |
|                                                                       |
| \"ldapGroupSearchBase\": \"OU=istitution_group,DC=domain,DC=suffix\", |
|                                                                       |
| \"userSearchString\": null,                                           |
|                                                                       |
| \"groupSearchString\": null                                           |
|                                                                       |
| }                                                                     |
+=======================================================================+

## Update LDAP group parameters mapping request 

PUT /Configurations/LdapGroupParametersMapping

{

\"institutionId\": \"institution_name\",

\"ldapUniqueIdentifier\": \"identifier_attribute\",

\"creationDate\": \"whencreated\",

\"description\": null,

\"displayName\": \"cn\",

\"isOrganisationUnit\": null,

\"lastUpdate\": null,

\"name\": \"cn\",

\"needReassignment\": null,

\"organisationUnit\": null,

\"parentGroupId\": null,

\"members\": null,

\"path\": null,

\"version\": 1

}

## Get LDAP group parameters mapping resonse 

GET /Configurations/LdapGroupParametersMapping/{institutionId}

{

\"id\": \"group_id\",

\"institutionId\": \"institution_name\",

\"ldapUniqueIdentifier\": \"identifier_attribute\",

\"creationDate\": \"whencreated\",

\"description\": null,

\"displayName\": \"cn\",

\"isOrganisationUnit\": null,

\"lastUpdate\": null,

\"name\": \"cn\",

\"needReassignment\": null,

\"organisationUnit\": null,

\"parentGroupId\": null,

\"members\": null,

\"path\": null,

\"version\": 1

}

## Get LDAP group parameters keys 

GET /Configurations/LdapGroupParametersKeys

\[

\"ldapUniqueIdetifier\",

\"name\",

\"displayName\",

\"description\",

\"isOrganisationUnit\",

\"needReassignment\",

\"parentGroupId\",

\"path\",

\"creationDate\",

\"lastUpdate\",

\"members\"\]

## Update LDAP user parameters keys request 

PUT /Configurations/LdapUserParametersMapping/{institutionId}

{

\"version\": 0,

\"institutionId\": \"institution_name\",

\"ldapUniqueIdentifier\": \"identifier_attribute\",

\"username\": \"userPrincipalName\",

\"email\": \"userPrincipalName\",

\"firstName\": \"givenName\",

\"lastName\": \"sn\",

\"creationDate\": null,

\"groups\": null,

\"phoneNumber\": null,

\"isEnabled\": null,

\"isLocked\": null,

\"isAdministrator\": null,

\"lastUpdate\": null,

"groups": "memberOf",

"role": "EVERYONE"

}

## Get LDAP user parameters keys 

GET /Configurations/LdapUserParametersMapping/{instituionId}

{

\"id\": \"example_id\",

\"version\": 1,

"ldapUniqueIdentifier\": \"dn\",

\"institutionId\": \"institution_id\",

\"username\": \"userPrincipalName\",

\"email\": \"userPrincipalName\",

\"firstName\": \"givenName\",

\"lastName\": \"sn\",

\"creationDate\": null,

\"groups\": null,

\"phoneNumber\": null,

\"isEnabled\": null,

\"isLocked\": null,

\"isAdministrator\": null,

\"lastUpdate\": null,

"groups": "memberOf",

"role": "EVERYONE"

}

## Get LDAP user parameters keys 

GET /Configurations/LdapUserParametersKeys

\[

\"ldapUniqueIdetifier\",

\"username\",

\"firstName\",

\"lastName\",

\"email\",

\"phoneNumber\",

\"isEnabled\",

\"isLocked\",

\"isAdministrator\",

\"creationDate\",

\"lastUpdate\",

\"groups\",

\"role\"

\]

## Synchronize LDAP 

#### *request* 

POST
/ApplicationProfile/IAMSettings/LdapSynchronization/{institutionId}}

#### *response* 

## Reassign group affected cases 

***request***

> POST /ApplicationProfile/LdapSynchronization/Reassignment

#### *response* 

None.

## Retrieves a list of policies, optionally filtered 

Retrieves a list of policies, optionally filtered by policy name or by
an associated target.

#### *Request* 

GET /AssignmentPolicies?institutionId=1&name=POLICY&targetId=P

#### *Response* 

\[{

id: \"policy1\",

name: \"WE vs EE assignment policy\",

appRole: \"CP\",

rules: \[ {

id: \"rule1\",

userGroups: \[ { id: \"101\", name: \"/Pensions/WE\", type: \"Group\" },
{ id: \"102\", name: \"/Sickness/WE\", type: \"Group\" }, { id: \"103\",
name: \"/Unemployment/WE\", type: \"Group\" }, actors: \[\], condition:
{

appRole: \"CP\",

ownerCountry: \[ \"BE\", \"DE\", \"FR\", \"UK\" \]

}

}, {

id: \"rule2\",

userGroups: \[ { id: \"201\", name: \"/Pensions/EE\", type: \"Group\" },
{ id: \"202\", name: \"/Sickness/EE\", type: \"Group\" }, { id: \"203\",
name: \"/Unemployment/EE\", type: \"Group\" }, actors: \[
\"Supervisor\", \" Authorized\", \"Nonauthorized\", \"Viewer\",
\"Auditor\"\],

+-----------------------------------------------------------------------+
| condition: {                                                          |
|                                                                       |
| appRole: \"CP\",                                                      |
|                                                                       |
| ownerCountry: \[ \"BG\", \"RO\", \"HU\", \"SK\" \]                    |
|                                                                       |
| }                                                                     |
|                                                                       |
| }                                                                     |
|                                                                       |
| \]                                                                    |
|                                                                       |
| },                                                                    |
|                                                                       |
| {                                                                     |
|                                                                       |
| id: \"policy2\",                                                      |
|                                                                       |
| name: \"Assignment by sector policy \",                               |
|                                                                       |
| appRole: \"CP\",                                                      |
|                                                                       |
| rules: \[{                                                            |
|                                                                       |
| id: \"rule3\",                                                        |
|                                                                       |
| userGroups: \[ { id: \"10\", name: \"/Sickness\", type: \"Group\" }   |
| \], actors: \"actors\" : \[\"Auditor\", \"Authorized\", \"Medical\",  |
| \"Nonauthorized\",                                                    |
|                                                                       |
| \"Supervisor\", \"Viewer\", \"Vip\"\],,                               |
|                                                                       |
| condition: { appRole: \"CP\",                                         |
|                                                                       |
| sector: \[ \"S\" \]                                                   |
|                                                                       |
| }                                                                     |
|                                                                       |
| }, {                                                                  |
|                                                                       |
| id: \"rule4\",                                                        |
|                                                                       |
| userGroups: \[ { id: \"11\", name: \"/Pensions\", type: \"Group\" }   |
| \],                                                                   |
|                                                                       |
| actors: \[\], condition: { appRole: \"CP\",                           |
|                                                                       |
| sector: \[ \"P\" \]                                                   |
|                                                                       |
| }                                                                     |
|                                                                       |
| }, {                                                                  |
|                                                                       |
| id: \"rule5\",                                                        |
|                                                                       |
| userGroups: \[ { id: \"12\", name: \"/Unemployment\", type: \"Group\" |
| } \], actors: \[ \], condition: { appRole: \"CP\",                    |
|                                                                       |
| sector: \[ \"UB\" \]                                                  |
|                                                                       |
| }                                                                     |
|                                                                       |
| }                                                                     |
|                                                                       |
| \]                                                                    |
|                                                                       |
| }\]                                                                   |
+=======================================================================+

## Retrieves a policy 

#### *Request* 

GET /AssignmentPolicies/policy2?institutionId=1

#### *Response* 

+----------+-----------------+-------------------------------------------------------+
| > {      | id:             | name: \"Assignment by sector policy \",               |
|          | \"policy2\",    |                                                       |
|          |                 | id: \"rule3\",                                        |
|          | appRole:        |                                                       |
|          | \"CP\",         | userGroups: \[ { id: \"10\", name: \"/Sickness\",     |
|          |                 | type: \"Group\" } \], actors: \[\],                   |
|          | rules: \[{      |                                                       |
|          |                 | condition: {                                          |
|          |                 |                                                       |
|          |                 | appRole: \"CP\",                                      |
|          |                 |                                                       |
|          |                 | sector: \[ \"S\" \]                                   |
|          |                 |                                                       |
|          |                 | }                                                     |
+:====+:===+:=======+:=======+:======================================================+
|          | }, {            | id: \"rule4\",                                        |
|          |                 |                                                       |
|          |                 | userGroups: \[ { id: \"11\", name: \"/Pensions\",     |
|          |                 | type: \"Group\" } \], actors: \[\],                   |
|          |                 |                                                       |
|          |                 | condition: {                                          |
|          |                 |                                                       |
|          |                 | appRole: \"CP\",                                      |
|          |                 |                                                       |
|          |                 | sector: \[ \"P\" \]                                   |
|          |                 |                                                       |
|          |                 | }                                                     |
+----------+-----------------+-------------------------------------------------------+
|          | }, {            | id: \"rule5\",                                        |
|          |                 |                                                       |
|          |                 | userGroups: \[ { id: \"12\", name: \"/Unemployment\", |
|          |                 | type: \"Group\" } \], actors: \[\],                   |
|          |                 |                                                       |
|          |                 | condition: {                                          |
|          |                 |                                                       |
|          |                 | appRole: \"CP\", sector: \[ \"UB\" \]                 |
+-----+----+--------+--------+-------------------------------------------------------+
|     |             | }      | }                                                     |
+-----+-------------+--------+-------------------------------------------------------+
| > } | > \]        |        |                                                       |
+-----+-------------+--------+-------------------------------------------------------+

## Creates a policy 

#### *Request* 

+-----------------------------------------------------------------------+
| POST /AssignmentPolicies?institutionId=1                              |
|                                                                       |
| {                                                                     |
|                                                                       |
| name: \"WE vs EE assignment policy\",                                 |
|                                                                       |
| appRole: \"CP\",                                                      |
|                                                                       |
| rules: \[ {                                                           |
|                                                                       |
| id: \"rule1\",                                                        |
|                                                                       |
| userGroups: \[ { id: \"101\", name: \"/Pensions/WE\", type: \"Group\" |
| },                                                                    |
|                                                                       |
| { id: \"102\", name: \"/Sickness/WE\", type: \"Group\" },             |
|                                                                       |
| { id: \"103\", name: \"/Unemployment/WE\", type: \"Group\" },         |
|                                                                       |
| actors: \[\"Auditor\", \"Authorized\", \"Medical\",                   |
| \"Nonauthorized\", \"Supervisor\",                                    |
|                                                                       |
| \"Viewer\", \"Vip\"\],                                                |
|                                                                       |
| condition: {                                                          |
|                                                                       |
| appRole: \"CP\",                                                      |
|                                                                       |
| ownerCountry: \[ \"BE\", \"DE\", \"FR\", \"UK\" \]                    |
|                                                                       |
| }                                                                     |
|                                                                       |
| }, {                                                                  |
|                                                                       |
| id: \"rule2\",                                                        |
|                                                                       |
| userGroups: \[ { id: \"201\", name: \"/Pensions/EE\", type: \"Group\" |
| },                                                                    |
|                                                                       |
| { id: \"202\", name: \"/Sickness/EE\", type: \"Group\" }, { id:       |
| \"203\", name: \"/Unemployment/EE\", type: \"Group\" }, actors: \[\], |
| condition: {                                                          |
|                                                                       |
| appRole: \"CP\",                                                      |
|                                                                       |
| ownerCountry: \[ \"BG\", \"RO\", \"HU\", \"SK\" \]                    |
|                                                                       |
| }                                                                     |
|                                                                       |
| }                                                                     |
|                                                                       |
| \]                                                                    |
|                                                                       |
| }                                                                     |
+=======================================================================+

***Response*** policy1

## Updates a policy 

***Request***

+----------------------------------------------------------------------------------------------------------------------------------+
| PUT /AssignmentPolicies/policy2?institutionId=1                                                                                  |
|                                                                                                                                  |
| {                                                                                                                                |
|                                                                                                                                  |
| id: \"policy2\",                                                                                                                 |
|                                                                                                                                  |
| name: \"Assignment by sector policy \",                                                                                          |
|                                                                                                                                  |
| appRole: \"CP\",                                                                                                                 |
|                                                                                                                                  |
| rules: \[{                                                                                                                       |
|                                                                                                                                  |
| id: \"rule3\",                                                                                                                   |
|                                                                                                                                  |
| userGroups: \[ { id: \"10\", name: \"/Sickness\", type: \"Group\" } \],                                                          |
|                                                                                                                                  |
| actors: \[\], condition: { appRole: \"CP\",                                                                                      |
|                                                                                                                                  |
| sector: \[ \"S\" \]                                                                                                              |
|                                                                                                                                  |
| }                                                                                                                                |
|                                                                                                                                  |
| }, {                                                                                                                             |
|                                                                                                                                  |
| id: \"rule4\",                                                                                                                   |
|                                                                                                                                  |
| userGroups: \[ { id: \"11\", name: \"/Pensions\", type: \"Group\" } \],                                                          |
|                                                                                                                                  |
| actors: \[\], condition: { appRole: \"CP\",                                                                                      |
|                                                                                                                                  |
| sector: \[ \"P\" \]                                                                                                              |
|                                                                                                                                  |
| }                                                                                                                                |
|                                                                                                                                  |
| }, {                                                                                                                             |
|                                                                                                                                  |
| id: \"rule5\",                                                                                                                   |
|                                                                                                                                  |
| userGroups: \[ { id: \"12\", name: \"/Unemployment\", type: \"Group\" } \],                                                      |
|                                                                                                                                  |
| actors:\], condition: {                                                                                                          |
+:==================+:==================+:==================+:==================+:=================================================+
|                   |                   |                   |                   | appRole: \"CP\", sector: \[ \"UB\" \]            |
+-------------------+-------------------+-------------------+-------------------+--------------------------------------------------+
|                   |                   | }                 | }                 |                                                  |
+-------------------+-------------------+-------------------+-------------------+--------------------------------------------------+
| > }               | \]                |                   |                   |                                                  |
+-------------------+-------------------+-------------------+-------------------+--------------------------------------------------+

#### *Response* 

## Deletes a policy 

#### *Request* 

DELETE /AssignmentPolicies/policy1?institutionId=1

#### *Response* 

## Associates an existing policy to a target 

#### *Request* 

PUT /AssignmentPolicies/policy2/Targets/PO_S_BUC_01?institutionId=1

#### *Response* 

## Associates existing policies to a target 

#### *Request* 

PUT /AssignmentPolicies/Target/PO_S_BUC_01?institutionId=1

\[\"acc6e419738b4ec39e969a7eb51827f7\",\"ae0b1256186e4c1aaa384e03de9383aa\"\]

#### *Response* 

## Removes a target from a policy 

#### *Request* 

DELETE /AssignmentPolicies/policy2/Targets/PO_S_BUC_01?institutionId=1

#### *Response* 

# PDP - Case Assignment Policy Decision Point 

The case assignment policy decision point is called once for every new
case instance.

The input is an object representing the case instance. The output is the
list of case assignments.

Based on the case instance properties, Case Assignment Policy Decision
Point determines the applicable policies, evaluates them and computes
the list of case assignments for this case (a list of groups and/or
users for each actor).

## Service contracts / interface 

interface CaseAssignmentsPDP {

List\<Actor\> calculateCaseAssignments(String institutionId,
CaseProperties caseProperties) throws InvalidCaseException,
NoApplicablePolicyException, PolicyProcessingException;

}

## Data contracts / model 

### Actor 

The actor of a case

+----------------+--------------------------------------+---------------------+
| **Attribute**  | **Description**                      | **Data Type**       |
+:===============+:=====================================+:====================+
| id             | > The id of the actor                | String              |
+----------------+--------------------------------------+---------------------+
| name           | > The name of the actor              | String              |
+----------------+--------------------------------------+---------------------+
| userGroups     | > A list of users or groups that     | List\<UserOrGroup\> |
|                | > will be assigned to the case as    |                     |
|                | > this actor                         |                     |
+----------------+--------------------------------------+---------------------+

### UserOrGroup 

Represents a user or a group.

+---------------+------------------------------------------+--------------+
| **Attribute** | **Description**                          | **Data       |
|               |                                          | Type**       |
+:==============+==========================================+:=============+
| > id          | The id of this user/group in RINA.       | > String     |
|               | Specific constants are used to represent |              |
|               | the \<Creator\'s Group\> and \<Creator   |              |
|               |                                          |              |
|               | User\> placeholders                      |              |
+---------------+------------------------------------------+--------------+
| > name        | The name of \"User\" or \"Group\"        | > String     |
+---------------+------------------------------------------+--------------+
| > type        | Selection of \"User\" or \"Group\"       | > String     |
+---------------+------------------------------------------+--------------+

### Case properties 

Represents a new case instance.

+-----------------------+-------------------------------------+-----------------------+
| **Attribute**         | **Description**                     | **Data Type**         |
+:======================+:====================================+:======================+
| id                    | > the id of the case                | > String              |
+-----------------------+-------------------------------------+-----------------------+
| processDefinitionName | > the identifier of the process of  | > String              |
|                       | > this case (e.g.                   |                       |
|                       | >                                   |                       |
|                       | > CP_P_BUC_07)                      |                       |
+-----------------------+-------------------------------------+-----------------------+
| participants          | > the list of participants to this  | > List\<Participant\> |
|                       | > case                              |                       |
+-----------------------+-------------------------------------+-----------------------+
| subject               | the person or organization that     | Entity                |
|                       | this case is about                  |                       |
+-----------------------+-------------------------------------+-----------------------+
| creator               | the creator user of this case       | UserOrGroup           |
+-----------------------+-------------------------------------+-----------------------+

### Participant 

+-----------------+--------------------------------------+----------------+
| > **Attribute** | > **Description**                    | > **Data       |
|                 |                                      | > Type**       |
+:================+:=====================================+:===============+
| role            | > The application role of this       | > String       |
|                 | > participant (PO/CP)                |                |
+-----------------+--------------------------------------+----------------+
| organisation    | > the participant organization       | > Organisation |
+-----------------+--------------------------------------+----------------+

### Organisation (inherits Entity) 

+-----------------+--------------------------------------+-------------+
| > **Attribute** | > **Description**                    | > **Data    |
|                 |                                      | > Type**    |
+:================+:=====================================+:============+
| id              | > The id of the organisation         | > String    |
+-----------------+--------------------------------------+-------------+
| name            | > The organisation name              | > String    |
+-----------------+--------------------------------------+-------------+
| acronym         | > The acronym for the organisation   | > String    |
+-----------------+--------------------------------------+-------------+
| countryCode     | > The Country code                   | > String    |
+-----------------+--------------------------------------+-------------+

### Person (inherits Entity) 

+-----------------+--------------------------------------+-------------+
| > **Attribute** | > **Description**                    | > **Data    |
|                 |                                      | > Type**    |
+:================+:=====================================+:============+
| pid             | > The id of the person               | > String    |
+-----------------+--------------------------------------+-------------+
| name            | > The name of the person             | > String    |
+-----------------+--------------------------------------+-------------+
| surname         | > The surname of the person          | > String    |
+-----------------+--------------------------------------+-------------+
| birthday        | > The birthday of the person         | > Date      |
+-----------------+--------------------------------------+-------------+
| sex             | > The sex of the person              | > String    |
+-----------------+--------------------------------------+-------------+

### Entity 

+-----------------+--------------------------------------+-------------+
| > **Attribute** | > **Description**                    | > **Data    |
|                 |                                      | > Type**    |
+:================+:=====================================+:============+
| address         | > The address of the entity          | > Address   |
+-----------------+--------------------------------------+-------------+

### Address 

+-----------------+--------------------------------------+-------------+
| > **Attribute** | > **Description**                    | > **Data    |
|                 |                                      | > Type**    |
+:================+:=====================================+:============+
| street          | > The street of the entity           | > String    |
+-----------------+--------------------------------------+-------------+
| town            | > The town of the entity             | > String    |
+-----------------+--------------------------------------+-------------+
| postalCode      | > The postalCode of the entity       | > String    |
+-----------------+--------------------------------------+-------------+
| region          | > The region of the entity           | > String    |
+-----------------+--------------------------------------+-------------+
| country         | > The country of the entity          | > String    |
+-----------------+--------------------------------------+-------------+

## Fault contracts / exceptions 

+-----------------------------------------------------------------------+
| **InvalidCaseException**: { // something is missing or invalid in the |
| input }                                                               |
|                                                                       |
| **NoApplicablePolicyException**: { // could not find an applicable    |
| policy }                                                              |
|                                                                       |
| **PolicyProcessingException**: { // something else went wrong when    |
| evaluating policies }                                                 |
+=======================================================================+

# Development impact 

Changing the authentication way is going to imply that an interface is
needed to select which one of Internal RINA or LDAP is preferred, coming
with a few constraints:

- IAM Related:

  - Using an external DB like LDAP to store the credentials (and the
    authorizations) means that RINA *depends* on LDAP. Therefore, it is
    not possible to create/update/delete users or groups from the
    application (through the use of LDAP); However, the default role
    assigned during synchronization can be updated and other group
    memberships can be added. o All the cases\' assignments must be
    updated when the group changes, so a tool must be created to
    accommodate this synchronization;

  - Add user to multiple groups support as currently the users cannot
    belong to more than one group;

  - Add membership (role of a user inside a group).

- IAM Related and External Rules: Two types of rules: process owner and
  counterparty based.

# How-to\'s 

## How to configure the synchronizer 

See ***Error! Reference source not found.*** for the fields\'
descriptions

## How to develop my external rules 

The basic structure of a rule is: \"Assign \<*Groups or Users*\> as
\<*Actors*\> if \<*Conditions*\>.

In the editing screen, fill-in all fields:

- sector / process

- role

- actor

- groups (e.g.: sending country). assigned users/groups

All fields left blank are not considered, therefore it means "any".

A common scenario would be having inside an organization specific group
of users to be assigned to every sector, like the groups in this image:

> ![](media/image33.jpeg)

*Figure 13. Illustrative example on having specific groups of users*

To address this scenario, a single assignment policy like the one
described below can be created and then assigned to all BUC sectors:

> The policy would contain several assigning rules, each rule linking
> one of the sectors to the corresponding user group (e.g. the "P"
> sector to the "/EESSI/Pensions" group):

{

\"name\": \"Assign EESSI subgroups by sector\",

\"description\": \"This policy assigns every case to the corresponding
subgroup based on the sector (Pension, Sickness etc)\",

\"color\": \"green\",

\"type\": \"POLICY\",

\"rules\": \[{

\"userGroups\": \[{

\"name\": \"/EESSI/AWOD\",

\"id\": \"101\",

\"type\": \"Group\"

}

\],

\"actors\": \[\],

\"condition\": {

\"sector\": \[\"AW\"\]

}

}, {

\"userGroups\": \[{

\"name\": \"/EESSI/FB\",

\"id\": \"102\",

\"type\": \"Group\"

}

\],

\"actors\": \[\],

\"condition\": {

\"sector\": \[\"FB\"\]

}

}, {

\"userGroups\": \[{

\"name\": \"/EESSI/Horizontal\",

\"id\": \"103\",

\"type\": \"Group\"

}

\],

\"actors\": \[\],

\"condition\": {

\"sector\": \[\"H\"\]

}

}, {

+-----+------+----+---------------------+---------------------+--------------------------------------------+
|     |      |    | \"userG             | roups\":            | \[{                                        |
|     |      |    |                     |                     |                                            |
|     |      |    |                     | }                   | \"name\": \"/EESSI/LegApp\",               |
|     |      |    |                     |                     |                                            |
|     |      |    |                     |                     | \"id\": \"104\",                           |
|     |      |    |                     |                     |                                            |
|     |      |    |                     |                     | \"type\": \"Group\"                        |
+:====+:=====+:===+:====================+:====================+:===========================================+
|     |      |    | \],                                                                                    |
|     |      |    |                                                                                        |
|     |      |    | \"actors\": \[\],                                                                      |
|     |      |    |                                                                                        |
|     |      |    | \"condition\": {                                                                       |
|     |      |    |                                                                                        |
|     |      |    | \"sector\": \[\"LA\"\]                                                                 |
|     |      |    |                                                                                        |
|     |      |    | }                                                                                      |
+-----+------+----+---------------------+---------------------+--------------------------------------------+
|     |      | }, | \"userG             | roups\":            | \[{                                        |
|     |      | {  |                     |                     |                                            |
|     |      |    |                     | }                   | \"name\": \"/EESSI/Pensions\",             |
|     |      |    |                     |                     |                                            |
|     |      |    |                     |                     | \"id\": \"105\",                           |
|     |      |    |                     |                     |                                            |
|     |      |    |                     |                     | \"type\": \"Group\"                        |
+-----+------+----+---------------------+---------------------+--------------------------------------------+
|     |      |    | \],                                                                                    |
|     |      |    |                                                                                        |
|     |      |    | \"actors\": \[\],                                                                      |
|     |      |    |                                                                                        |
|     |      |    | \"condition\": {                                                                       |
|     |      |    |                                                                                        |
|     |      |    | \"sector\": \[\"P\"\]                                                                  |
|     |      |    |                                                                                        |
|     |      |    | }                                                                                      |
+-----+------+----+---------------------+---------------------+--------------------------------------------+
|     |      | }, | \"userG             | roups\":            | \[{                                        |
|     |      | {  |                     |                     |                                            |
|     |      |    |                     | }                   | \"name\": \"/EESSI/Recovery\",             |
|     |      |    |                     |                     |                                            |
|     |      |    |                     |                     | \"id\": \"107\",                           |
|     |      |    |                     |                     |                                            |
|     |      |    |                     |                     | \"type\": \"Group\"                        |
+-----+------+----+---------------------+---------------------+--------------------------------------------+
|     |      |    | \],                                                                                    |
|     |      |    |                                                                                        |
|     |      |    | \"actors\": \[\],                                                                      |
|     |      |    |                                                                                        |
|     |      |    | \"condition\": {                                                                       |
|     |      |    |                                                                                        |
|     |      |    | \"sector\": \[\"R\"\]                                                                  |
|     |      |    |                                                                                        |
|     |      |    | }                                                                                      |
+-----+------+----+---------------------+---------------------+--------------------------------------------+
|     |      | }, | \"userG             | roups\":            | \[{                                        |
|     |      | {  |                     |                     |                                            |
|     |      |    |                     | }                   | \"name\": \"/EESSI/Sickness\",             |
|     |      |    |                     |                     |                                            |
|     |      |    |                     |                     | \"id\": \"108\",                           |
|     |      |    |                     |                     |                                            |
|     |      |    |                     |                     | \"type\": \"Group\"                        |
+-----+------+----+---------------------+---------------------+--------------------------------------------+
|     |      |    | \],                                                                                    |
|     |      |    |                                                                                        |
|     |      |    | \"actors\": \[\],                                                                      |
|     |      |    |                                                                                        |
|     |      |    | \"condition\": {                                                                       |
|     |      |    |                                                                                        |
|     |      |    | \"sector\": \[\"S\"\]                                                                  |
|     |      |    |                                                                                        |
|     |      |    | }                                                                                      |
+-----+------+----+---------------------+---------------------+--------------------------------------------+
|     |      | }, | \"userG             | roups\":            | \[{                                        |
|     |      | {  |                     |                     |                                            |
|     |      |    |                     | }                   | \"name\": \"/EESSI/UB\",                   |
|     |      |    |                     |                     |                                            |
|     |      |    |                     |                     | \"id\": \"109\",                           |
|     |      |    |                     |                     |                                            |
|     |      |    |                     |                     | \"type\": \"Group\"                        |
+-----+------+----+---------------------+---------------------+--------------------------------------------+
|     |      | }  | \],                                                                                    |
|     |      |    |                                                                                        |
|     |      |    | \"actors\": \[\],                                                                      |
|     |      |    |                                                                                        |
|     |      |    | \"condition\": {                                                                       |
|     |      |    |                                                                                        |
|     |      |    | \"sector\": \[\"UB\"\]                                                                 |
|     |      |    |                                                                                        |
|     |      |    | }                                                                                      |
+-----+------+----+----------------------------------------------------------------------------------------+
| > } | > \] |    |                                                                                        |
+-----+------+----+----------------------------------------------------------------------------------------+

## How to configure LDAP 

### Authentication 

+-----------------------------------------------------------------------------+
| cas.authn.ldap\[0\].ldapUrl=ldap://ldapServerIpAddress:389                  |
| cas.authn.ldap\[0\].useSsl=false cas.authn.ldap\[0\].allowMultipleDns=true  |
|                                                                             |
| cas.authn.ldap\[0\].baseDn=OU=instName,DC=rinaldp,DC=lab                    |
|                                                                             |
| cas.authn.ldap\[0\].userFilter=(&(samAccountName={user})(objectClass=user)) |
| cas.authn.ldap\[0\].subtreeSearch=true                                      |
| cas.authn.ldap\[0\].bindDn=install@rinaldp.lab                              |
| cas.authn.ldap\[0\].bindCredential=pass123                                  |
+=============================================================================+

# Relevant links & References 

The following links have been used to create this specification and are
useful for development:

- LDAP Community milestones for supporting LDAP
  *https://www.openldap.org/*

- LDAP Authentication

- XACML - eXtensible Access Control Markup Language (XACML) Version 3.0
  [*http://docs.oasis-open.org/xacml/3.0/xacml-3.0-core-spec-os-en.html*](http://docs.oasis-open.org/xacml/3.0/xacml-3.0-core-spec-os-en.html)

# Limitations of the current version 

In the current version the RINA external rules interface is not yet
fully defined. Therefore, in the next versions of this document, for the
external rules interface the following may be defined:

- Service contract o This will define the operations, which are exposed
  by the RINA external rules interface service to the exterior. The
  service contract will describe what external rules interface APIs and
  relevant details (i.e., URI, description, etc.);

- Data contract o This will define the data class models of the
  information that will be exchange between the CPS and the RINA
  external rules interface service;

- Fault contract o This provides documented view for error accorded in
  the RINA external rules interface service to client. Due to the error
  masking, as the service throws any error which will not reach CPS, the
  fault contract will help to easy identify what error has occurred, and
  where.

**References:**

*"EESSI -- RINA Case Processing Interface (CPI) -- Reference"*

[^1]: full case/SED content related to \"sensitive" cases (associated to
    protected persons)

[^2]: Case assignments, case criticality, alarms, Case level comments
    and attachments

[^3]: Subject block (username, name, gender and birth date or the
    relevant institution description in bilateral reimbursement cases),
    Case participants, Case assignments, Case criticality/importance,
    Case alarms, Case level comments & attachments