---
unique-name: eessi-rina-6218-operations-manual
display-name: EESSI   RINA 6.2.18   Operations Manual
category: GENERAL
description: - # !!! IMPORTANT NOTE #
tags: ec
---

<!-- image -->

<!-- image -->

## EESSI RINA - RINA 6.2.18 (RINA Portal 6.2.19)

## Operations Manual

Operations Manuals &amp; Guides

<!-- image -->

## TABLE OF CONTENTS

| INTRODUCTION ..............................................................................................................................7                 | INTRODUCTION ..............................................................................................................................7                 | INTRODUCTION ..............................................................................................................................7   |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------|
| 1.1                                                                                                                                                          | GLOSSARY OF TERMS ...........................................................................................................................                | 7                                                                                                                                              |
| 1.2                                                                                                                                                          | CONTEXT ...............................................................................................................................................      | 7                                                                                                                                              |
| 1.3                                                                                                                                                          | SCOPE OF THE DOCUMENT ..................................................................................................................                     | 7                                                                                                                                              |
| 1.4                                                                                                                                                          | EESSI SYSTEM DIAGRAM ...................................................................................................................                     | 8                                                                                                                                              |
| 1.5                                                                                                                                                          | RINA COMPONENTS OVERVIEW ..........................................................................................................                          | 8                                                                                                                                              |
| 2 BACKUP AND DATA RECOVERY ............................................................................................. 10                                  | 2 BACKUP AND DATA RECOVERY ............................................................................................. 10                                  | 2 BACKUP AND DATA RECOVERY ............................................................................................. 10                    |
| 2.1                                                                                                                                                          | RINA BACKUP AND DATA RECOVERY OBJECTIVES .........................................................................                                           | 10                                                                                                                                             |
| 2.2                                                                                                                                                          | BACKUP AND DATA RECOVERY OVERVIEW .......................................................................................                                    | 10                                                                                                                                             |
| 2.2.1                                                                                                                                                        | RINA components for backup .............................................................................................11                                   |                                                                                                                                                |
| 2.2.2                                                                                                                                                        | Backing Up Logging Database ............................................................................................12                                   |                                                                                                                                                |
| 2.2.3                                                                                                                                                        | Backing Up PostgreSQL Database .....................................................................................13                                       |                                                                                                                                                |
| 2.2.4                                                                                                                                                        | Backing Up Shared File System .........................................................................................13                                    |                                                                                                                                                |
| 2.2.5                                                                                                                                                        | Data recovery overview ........................................................................................................14                            |                                                                                                                                                |
| 2.3                                                                                                                                                          | CONFIGURING THE BACKUP JOB .......................................................................................................                           | 14                                                                                                                                             |
| 2.4                                                                                                                                                          | DATA RESTORATION FOR RINA COMPONENT ..................................................................................                                       | 15                                                                                                                                             |
| 2.4.1                                                                                                                                                        | Restoring File System ............................................................................................................16                         |                                                                                                                                                |
| 2.4.2                                                                                                                                                        | Restoring logging database .................................................................................................16                               |                                                                                                                                                |
| 2.4.3                                                                                                                                                        | Restoring the PostgreSQL database .................................................................................16                                        |                                                                                                                                                |
| 2.4.4                                                                                                                                                        | General consideration regarding data restoration ......................................................16                                                    |                                                                                                                                                |
| 2.5                                                                                                                                                          | DISASTER RECOVERY .........................................................................................................................                  | 17                                                                                                                                             |
| 3 MANAGEMENT AND REPLACEMENT OF RINA CERTIFICATES ................................. 18                                                                       | 3 MANAGEMENT AND REPLACEMENT OF RINA CERTIFICATES ................................. 18                                                                       | 3 MANAGEMENT AND REPLACEMENT OF RINA CERTIFICATES ................................. 18                                                         |
| 3.1                                                                                                                                                          | CERTIFICATES IN EESSI ...................................................................................................................                    | 18                                                                                                                                             |
| 3.1.1                                                                                                                                                        | Recommended Architecture Directions on CA Hierarchies ......................................19                                                               |                                                                                                                                                |
| 3.1.2                                                                                                                                                        | Certificate usage split by communication segment ....................................................20                                                      |                                                                                                                                                |
| 3.1.3                                                                                                                                                        | Recommended Architecture Directions on PKI .............................................................20                                                   |                                                                                                                                                |
| 3.1.4                                                                                                                                                        | Using Certificates for Business Signature ......................................................................21                                           |                                                                                                                                                |
| 3.1.5                                                                                                                                                        | Certificate Requirements ......................................................................................................21                            |                                                                                                                                                |
| 3.2                                                                                                                                                          | CERTIFICATE DEPLOYMENT OVERVIEW .............................................................................................                                | 22                                                                                                                                             |
| 3.2.1                                                                                                                                                        | Obtaining Certificates .............................................................................................................22                       |                                                                                                                                                |
| 3.2.2                                                                                                                                                        | Description and Scope of RINA Certificates ...................................................................23                                             |                                                                                                                                                |
| 3.3                                                                                                                                                          | CERTIFICATE MANAGEMENT IN RINA ..............................................................................................                                | 24                                                                                                                                             |
| 3.3.1                                                                                                                                                        | Certificates used in RINA ......................................................................................................24                           |                                                                                                                                                |
| 3.3.2                                                                                                                                                        | Certificate Management Procedures for RINA ..............................................................24                                                  |                                                                                                                                                |
| 3.4                                                                                                                                                          | STEPS TO OBTAIN RINA CERTIFICATES ...........................................................................................                                | 25                                                                                                                                             |
| 4 RINA LOGGING CONFIGURATION ........................................................................................ 28                                     | 4 RINA LOGGING CONFIGURATION ........................................................................................ 28                                     | 4 RINA LOGGING CONFIGURATION ........................................................................................ 28                       |
| 4.1                                                                                                                                                          | INTRODUCTION ...................................................................................................................................             | 28                                                                                                                                             |
| 4.2                                                                                                                                                          | SCOPE AND OBJECTIVES ....................................................................................................................                    | 28                                                                                                                                             |
| 4.3                                                                                                                                                          | LOGS IN FILE SYSTEM ........................................................................................................................                 | 28                                                                                                                                             |
| 4.4                                                                                                                                                          | LOGGING INFORMATION AND ROTATION ..........................................................................................                                  | 29                                                                                                                                             |
| 4.4.1 Log4j logging utility (library) ..............................................................................................29                       | 4.4.1 Log4j logging utility (library) ..............................................................................................29                       |                                                                                                                                                |
| 4.4.2 Logstash log processing tool ...............................................................................................30                         | 4.4.2 Logstash log processing tool ...............................................................................................30                         |                                                                                                                                                |
| 4.4.3 Logging Configuration and Logfile description per Component .............................31                                                            | 4.4.3 Logging Configuration and Logfile description per Component .............................31                                                            |                                                                                                                                                |
| 4.5 AUDIT TRAIL .......................................................................................................................................      | 4.5 AUDIT TRAIL .......................................................................................................................................      | 37                                                                                                                                             |
| 4.5.1 RINA Audit Trail Architecture ..............................................................................................37                         | 4.5.1 RINA Audit Trail Architecture ..............................................................................................37                         |                                                                                                                                                |
| 4.5.2 Audit Trail Persistence ...........................................................................................................37                  | 4.5.2 Audit Trail Persistence ...........................................................................................................37                  |                                                                                                                                                |
| 4.5.3 Audit Trail Retrieval ................................................................................................................37               | 4.5.3 Audit Trail Retrieval ................................................................................................................37               | 38                                                                                                                                             |
| 4.6 AUDIT TRAIL DATA MODEL ............................................................................................................... 4.6.1 Audit Event | 4.6 AUDIT TRAIL DATA MODEL ............................................................................................................... 4.6.1 Audit Event |                                                                                                                                                |

.................................................................................................................................  38

<!-- image -->

5

6

7

8

9

CONFIGURING ETRANSLATION MODULE

5.1

<!-- image -->

......................................................................... 40

REQUEST CEF CREDENTIALS

5.2

5.3

5.4

............................................................................................................ 40

POPULATE CONFIGURATION

............................................................................................................... 40

START ETRANSLATION SERVICE

........................................................................................................ 43

INTEGRATION WITH RINA PORTAL

................................................................................................... 43

NIE COMMUNICATION VIA SSL

6.1

............................................................................................. 44

HIGH LEVEL DESCRIPTION

6.2

6.3

................................................................................................................ 44

LIMITATIONS

....................................................................................................................................... 44

CONFIGURATION

................................................................................................................................. 44

PORTAL DATA IMPORTER

........................................................................................................ 45

ADJUST ONLINE CONTEXTUAL HELP TO A NEW LANGUAGE

ADDITIONAL PARAMETERS CONFIGURATION

................................... 46

............................................................... 48

ANNEX 1: EXAMPLES ON RINA LOGGING CONFIGURATION

........................................... 49

## Table of Figures

| FIGURE 1: EESSI SYSTEM DIAGRAM ........................................................................................................ 8      |
|------------------------------------------------------------------------------------------------------------------------------------------------|
| FIGURE 2 RECOVERY METRICS ................................................................................................................. 10 |
| FIGURE 3: RINA - COMPONENTS TO BACKUP ................................................................................... 12                   |
| FIGURE 4: CERTIFICATES USAGE SCENARIOS FOR EACH EESSI APPLICATION DOMAIN 18                                                                    |
| FIGURE 5: ENVELOPED FORMAT SIGNATURE ..................................................................................... 21                  |
| FIGURE 6: CERTIFICATE DEPLOYMENT OVERVIEW .......................................................................... 22                        |
| FIGURE 7: CERTIFICATES FOR NA .......................................................................................................... 23    |
| FIGURE 8: IMPORTING THE TLS CERTIFICATES IN RINA .............................................................. 25                             |
| FIGURE 9: ADDING THE CERTIFICATE .................................................................................................. 25         |
| FIGURE 10: RINA LOGGING ARCHITECTURE - GENERATION FLOW DIAGRAM .................... 31                                                         |
| FIGURE 11: RINA AUDIT TRAIL ARCHITECTURE - COMPONENT VIEW .................................... 37                                              |
| FIGURE 12: RINA AUDIT DATA MODEL ................................................................................................. 38          |
| FIGURE 13: AN EXAMPLE OF THE AUDIT TRAIL EVENT AND THE CORRESPONDING FIELDS ON A DETAILED LIST OF AUDIT LOGS ON RINA ADMINISTRATION PORTAL. 39 |

<!-- image -->

39

<!-- image -->

## Document Control Information

| Document Control                        | Value                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Project Title                           | Electronic Exchange of Social Security Information (EESSI)                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Document Title                          | EESSI - RINA 6.2.18 - Operations Manual                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| Document Category                       | End User Manuals & Guides                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Revision                                | -                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Component Version                       | RINA 6.2.18                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| RINA Portal Version                     | RINA Portal 6.2.19                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| Last Publication Date Project Milestone | 22/12/2021 EESSI-2020 (RINA Fix8)                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Document Status                         | Final                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| Sensitivity (TLP) Distribution terms    | The distribution of this document is done strictly in line with the Traffic Light Protocol (TLP) established by the European Commission's note AC 790/15 REV for the EESSI project documentation. In line with the note AC 790/15 REV, this document is labelled as TLP = 'Green'. Therefore, it can be circulated widely within the EESSI community. However, the document or the information herein may not be published or posted on the Internet, nor released outside of the EESSI community. |
| Connected/Embedded Files                | None                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| Authors                                 | European Commission, DG EMPL A4, EESSI RINA                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Revised by                              | European Commission, DG EMPL A4, EESSI QA                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Approved by                             | European Commission, DG EMPL A4, EESSI PMO                                                                                                                                                                                                                                                                                                                                                                                                                                                         |

## Document history

| Project Milestone / Released Component Version        | Date       | Changes/Corrections Description                                                                              |
|-------------------------------------------------------|------------|--------------------------------------------------------------------------------------------------------------|
| EESSI 2019 RINA 5.6.2                                 |            | Update the content with parts moved from 'Backup and Data Recovery Guide' and 'RINA Administration Guide'    |
| EESSI 2019 RINA 5.6.2                                 |            | Add information on replacing RINA Certificates and on Logging and Monitoring topics                          |
| EESSI 2020 RINA 6.2.1 RINA Portal 6.2.3               | 18/12/2020 | A chapter for 'eTranslation', 'online help adjustments' and 'Hints on Configuration topics' have been added. |
| EESSI 2020 RINA 6.2.1 RINA Portal 6.2.3               | 18/12/2020 | Migration of SQL and replacement of the BUC Engine                                                           |
| RINA 6.2.3 RINA Portal 6.2.5                          | 15/03/2021 | Update the section ' 5 - Configuring eTranslation Module '                                                   |
| RINA 6.2.3 RINA Portal 6.2.5                          | 15/03/2021 | Update the section ' 3.4 - Steps to obtain RINA certificates '                                               |
| RINA 6.2.3 RINA Portal 6.2.5                          | 15/03/2021 | Replace the diagram on ' Figure 3: RINA - Components to backup '                                             |
| RINA 6.2.3 RINA Portal 6.2.5                          | 15/03/2021 | Update section ' 8- Adjust Online Contextual Help to a new language '                                        |
| EESSI 2020 HF6 RINA 6.2.12 RINA Portal 6.2.12         | 10/09/2021 | Add chapter '6 - NIE Communication via SSL'                                                                  |
| EESSI-2020 (RINA Fix8) RINA 6.2.18 RINA Portal 6.2.19 | 22/12/2021 | Version update.                                                                                              |

Project Milestone /

<!-- image -->

## 1 Introduction

## 1.1 Glossary of Terms

| Term/Acronym   | Definition                                         |
|----------------|----------------------------------------------------|
| EESSI          | Electronic Exchange of Social Security Information |
| RINA           | Reference Implementation of a National Application |
| AP             | Access Point                                       |
| SEDs           | Structured Electronic Document(s)                  |
| BUCs           | Business Use Case(s)                               |
| NAs            | National Application(s)                            |
| NAS            | Network Attached Storage (Shared File System)      |

## 1.2 Context

Electronic Exchange of Social Security Information (EESSI) is a messaging system between administrations in Social Security field, where communication is based on use of messages (SEDs) which are sent between endpoints (e.g., National Applications). Additionally, the communication is organised according to predefined processes (BUCs).

EESSI  network  is  constructed  by  means  of  a  hybrid  star/mesh  topology  where  we distinguish:

- The EESSI international domain including TESTA network, and a central coordination hub called Central Service Node are managed by European Commission.
- The Access Points , installed at the border between the International and National domains,  are  deployed  and  managed  by  Member  States  (and  connected  to  both TESTA via a TESTA Access Point (TAP) and to the local networks/institutions).
- The Reference Implementation of a National Application (RINA) is provided as an example application for creating and exchanging electronic messages.

## 1.3 Scope of the Document

The scope of this document is to generate a useful handbook for the operational manager by providing accurate information on operation issues of RINA related topics in a single document.

Analytically, the document contains valuable information of the following topics:

- In Chapter 2, detailed information in ' Backup and Data Recovery ' topic is presented and specific guidelines are given;
- In Chapter 3, information on the procedure of importing/updating RINA certificates is provided;
- Additionally, in Chapter 4 and 5, extensive information on ' Logging configuration and Rotation' and on 'RINA monitoring' is presented;
- In the last chapter (Chapter 6 ), the necessary guidelines in order to ' Adjust Online contextual help to a new language ' is described in order to h elp the administrator to easily  adapt  the  English  language  that  is  used  by  the  online  help  to  the  local language;
- The directory structure for Linux and Windows is presented in ANNEX 1

<!-- image -->

## 1.4 EESSI System Diagram

The overall system architecture is:

Figure 1: EESSI System Diagram

<!-- image -->

Deployment environments connected to the TESTA network include: TEST, ACCEPTANCE and PRODUCTION.

## 1.5 RINA components overview

For  the  EESSI  Production  deployment  the  following  components  are  deployed  in  each participating installation (Participating Country):

- One or more Access Point (AP);
- One  or  more  RINA  deployment  instances  or  National  Applications/NAs  (each application is related with only one Access Point).

RINA  deployment  instances  (for  full-stack)  contains  the  following  main functional components:

- Logging Database (Elasticsearch)
- PostgreSQL
- HolodeckB2B
- Logstash
- REST (Tomcat)
- LoadBalancer (Apache)
- Shared folder

<!-- image -->

<!-- image -->

Note: The  deployment  of  RINA  application  can  be  a  selected  as  a  single  server configuration or a distributed configuration.

## References:

- EESSI -RINA - Installation and Configuration - Windows
- EESSI -RINA - Installation and Configuration -Ubuntu
- EESSI -RINA -Deployment Guidelines

<!-- image -->

## 2 Backup and Data Recovery

## 2.1 RINA Backup and Data Recovery Objectives

The metrics applicable in the industry are:

- Recovery Point Objective (RPO): the amount of data loss acceptable for business
- Recovery Time Objective (RTO): the amount of time acceptable for business for performing a recovery

Figure 2 Recovery metrics

<!-- image -->

The minimum RPO depends on the frequency of the backup for RINA (time when last backup was performed) -daily recommended.

The  minimum  RTO  depends  on  the  amount  of  time  required  to  perform  the  recovery procedure.

In the context of a High Availability (HA) configuration for RINA, the following technologies minimise the downtime (RTO) and data loss (RPO):

- Clustering for PostgreSQL: the data replication could be assured by using PostgreSQL Log Shipping.
- The storage Area Networks (SAN) used to store the databases and files of the RINA must use redundant volumes (RAID1 or RAID5).
- The network devices used for connectivity between servers must provide redundant connections.

The above technologies do not exclude the need the backup the RINA components. The backup can be used to recover the data and configuration.

## 2.2 Backup and Data Recovery Overview

Backup and recovery for EESSI RINA is one of the processes that can ensure business continuity.

This does not exclude the other strategies for business continuity:

- Using a high availability configuration for the RINA which minimises the interruptions and provides redundancy.

<!-- image -->

- Using PostgreSQL Log Shipping which provides an implementation of Data Recovery solution.

The  procedures  are  based  on  Backup  and  Data  recovery  procedures  related  to  the technology of the platforms used for build RINA.

## Backup procedures include:

- Backup procedure for PostgreSQL databases (related to Holodeck database, RINA and ApClient database)
- Backup procedure for Shared File System (related to Holodeck, REST Loadbalancer, components and some configuration files)

The backup and data recovery procedures can be used to recover from the following failure scenarios:

- Hardware failure in the server running Document Database
- Hardware failure in the server running PostgreSQL
- Hardware failure of the NAS

When using  virtualisation  platforms  for  hosting  RINA  components,  additional  recovery scenarios are enabled by periodically taking the virtual machines offline and making copies of the virtual machines' disks and configuration. These copies allow the acceleration of the recovery process.

## 2.2.1 RINA components for backup

There are five main components which store business data and configuration data that need to be backup (see Figure 3 ):

- The backup procedure concerns the following databases:
- o PostgresSQL database instances:
- -Holodeck B2B database
- -RINA database
- -AP Client database
- o ElasticSearch database:
- -Logging database
- Shared File system (NAS)

<!-- image -->

NOTE: All  the  PostgreSQL  databases  should  use  the  same  instance,  so backup is performed for this single PostgreSQL instance.

Figure 3 : RINA - Components to backup

<!-- image -->

<!-- image -->

All these components need to be backed up at the same time to avoid data discrepancies and to perform end-to-end backup and restore for RINA.

<!-- image -->

NOTE: The  content  of  database  related  to  Holodeck  B2B  are  exclusively controlled  by  the  product  ('black -box'  database),  therefore  the  data  are generated by using specific interfaces exposed by the product (not with direct transactions  into  database  through  custom  development  tools/  software procedures)

## Recommended frequency of backup:

- Daily for PostegreSQL Databases
- Daily or Weekly for Shared file system (it depends on hardware configuration)

## 2.2.2 Backing Up Logging Database

All specific technical procedures related to Logging Database (Elasticsearch) are applicable. Either a complete backup or an incremental backup can be used (by using the snapshot functionality)

<!-- image -->

The  name  and  path  of  backup  files  for  Elasticsearch  database  depend  on  the  specific configuration of backup script(s).

## 2.2.3 Backing Up PostgreSQL Database

All specific technical procedures related to PostgreSQL Database are applicable. Depending on the solution, there are specific procedures that are applicable to specific versions of the database.

In RINA, these are the PostgreSQL versions used:

- Ubuntu: PostgreSQL 12.3.1
- Windows: PostgreSQL 12.3.1

For further information about backup and recovery in PostgreSQL please see: ' https://www.postgresql.org/docs/12.3/static/backup.html '

The PostgreSQL Databases which are included for backup are:

- HOLODECKB2B database
- RINA database
- APCLIENT database

Depending  on  the  configuration  scripts,  the  PostgreSQL  databases  can  be  backed  up separately (pg\_dump command) or in full, backing up the cluster (pg dumpall command).

## 2.2.4 Backing Up Shared File System

The 'Share' stores messages (sent and received) and also some configuration files.

It is recommended to back up configuration files whenever the Admin makes changes to the RINA configuration.

Messages  should  be  backed  up  daily.  Periodically  (monthly),  historical  files  should  be removed from the shared space.

The file system can be backed up incrementally (daily) or in full (weekly).

The shared drive path is set during the RINA installation: In both Windows and Ubuntu installations,  the  parameter  which  defines  the  path  is  $EESSI\_SHARE  declared  at installation time.

The main resources stored in the shared drive are:

- Sent and received message files.
- The CDM files (validation files, forms, etc).
- The RINA keystores.
- The pmodes files used by HolodeckB2B.
- Application configuration

## 2.2.5 Data recovery overview

The possible data restore scenarios are related to some possible malfunction of the RINA components:

- Entire system crashed (databases and file system)
- File System crashed
- Elasticsearch database crashed
- PostgreSQL databases crashed. This scenario could be extended with many other scenarios in case of there are separate platform/ installation for each PostgreSQL database.

The restoration of data is based on the last available backup. Therefore, some of data created / changed / sent / received between last backup time and crashed time could be lost, or the consistency / completeness could be affected. In this case should be taken into consideration to recreate manually the lost data.

General solution in case of inconsistency inside a Case:

- The Case Owner closes the existing Case Owner and adds a new Case
- The local Counter Party closes the existing Case and the Case Owner creates a new Case

## 2.3 Configuring the Backup Job

Backup tasks include the following:

- Scripts to back up PostgreSQL databases
- Scripts to back up the logging database
- Scripts to back up the $EESSI\_SHARE folder

The backup script for the shared file system is executed separately.

Note: The scripts and cron jobs are not provided by EESSI Project and should be created according to the deployment type and architecture.

Before the  execution  of  backup  scripts,  it  is  mandatory  to  ensure  that  RINA  does  not process  any  messages  (incoming  or  outgoing)  and  there  is  no  user  connected  to  the platform. This is done by using specific scripts for switch the RINA platform into 'offline' mode. These scripts are used for stopping the following components in this order after the ongoing active transactions are finished:

- REST component
- HolodeckB2B component

Before  the  REST  component,  the  Load  Balancer  service  should  also  be  stopped,  if applicable.

The automatic scripts for putting RINA in 'offline' mode include (this is the mandatory sequence which will be executed):

<!-- image -->

<!-- image -->

- Command(s) for stopping the HolodeckB2B service - all the current transactions are finished and then the service is stopped and no messages are exchanged with the AP.
- Command(s) for stopping the Apache WebServer service -all external access to CPI is stopped and no operations will be performed during the backup process.
- Command(s) for stopping the REST service -based on this, RINA is accessible to users (by means of the portal or any other component which is using REST services).
- Command(s) for checking the status of services related to REST and HolodeckB2B. Once the services are stopped, the backup script is started.

<!-- image -->

NOTE: RINA  should  be in  'offline'  mode  before  starting the  backup procedure. Please make sure your backup script checks the status of the REST and HolodeckB2B services (which should be stopped) before starting the backup.

Once the backup is finished, the stopped components should be started in the following order by specific automatic scripts to put RINA 'online' :

- HolodeckB2B component.
- REST component.
- Load Balancer.

The scripts applicable for backup depend on the platform (Ubuntu/ Windows).

## 2.4 Data Restoration for RINA component

Data restoring is applicable in case of one of the RINA components (document database, PostgreSQL databases or file system) is corrupted or  is  crashed  and there is no  other alternative to recover the data.

In  case  of  one  of  the  component  data  must  be  restore,  the  restoring  procedures  is applicable for all the other components for ensuring data consistency between them.

Data restoring steps are the following:

## Step 1. Switch the RINA platform to ' offline ' mode:

- Stop service for thre REST component
- Stop service for the  HolodeckB2B component (stop 'holodeckb2b'/ Stop 'EESSI HolodeckB2B' );
- Stop the LoadBalancer service The scripts are the same used for backup.
- Step 2. Data restoring for shared File system;
- Step 3. Data restoring for logging database;
- Step 4. Data restoring for PostgreSQL database;
- Step 5. Put R INA platform into ' online ' mode by starting the following services (in the given order):

<!-- image -->

- HolodeckB2B (start  'holodeckb2b' or Start  'EESSI  HolodeckB2B' for  Linux  and Windows respectively);
- REST
- Load balancer.

## 2.4.1 Restoring File System

The data from File System can be recovered using the last available backup, preserving the structure of the folders and files.

## 2.4.2 Restoring logging database

If necessary, document database could be reinstalled.

Data  restoration  is  implemented  by  using  specific  tool/command  for  logging  database (Elasticsearch):

- https://www.elastic.co/guide/en/elasticsearch/reference/7.2/modulessnapshots.html
- https://www.elastic.co/guide/en/elasticsearch/guide/master/\_restoring\_from\_a\_sn apshot.html

<!-- image -->

NOTE: Stay up to date with new versions of products and/or documents about the Document database (Elasticsearch).

## 2.4.3 Restoring the PostgreSQL database

If necessary, PostgreSQL database could be reinstalled.

Specific documentation for restore PostgreSQL can be found at:

- https://www.postgresql.org/docs/12.31/static/backup.html

Bear in mind the exact release of PostgreSQL in each type of installation.

<!-- image -->

NOTE: Stay up to date with new versions of products and/or documents about the PostgreSQL database.

## 2.4.4 General consideration regarding data restoration

It is possible that some data regarding a Case could be unrecoverable. In this context the Case has to be manually re-created.

The following aspects should be taken into consideration:

- Every affected case should be analysed separately.

<!-- image -->

- The Case Owner should close the existing case and add a new case.
- The local Counter Party (whose data were lost) can also close and then the Case Owner can add a new case.

## 2.5 Disaster Recovery

In case that a disaster recovery is necessary, all the components of RINA have to be reinstalled.

This is done by means of the RINA installation and configuration procedure or using copy of virtual machines, thus restoring data based on the last backup available.

The steps of the Disaster recovery procedure are given below:

- Install the servers
- Proceed with a new plain RINA Installation
- Restore the configuration folders to replace the default configuration with the most updated ones
- Synchronise IR and CDM
- Restore the Business specific data

<!-- image -->

## 3 Management and Replacement of RINA Certificates 3.1 Certificates in EESSI

The certificates needed for the EESSI system are divided into certificates needed for the International Domain (CSN, APs), and certificates needed for the National Domain (APs, RINAs):

- Web Server to  Node  authentication  and  authorisation :  a  certificate  will  be installed on the webserver to prove the identity of the server (server authentication)
- Node to Node Authentication and Authorisation: Transport Layer Security (TLS) authentication and authorisation between AP → CSN, AP → AP, NA/NG → AP, based on the AP specific "authentication and authorisation list"
- Secure communication TLS channel: Establishing Transport Layer Security (TLS) channels between AP → CSN, AP → AP, NA/NG → AP
- ebMS Message Authentication and Authorisation: The signing certificate must belong to the sending institution/tenants for any message type at ebMS level. The "authorisation lists" of institutions/tenants which can send messages is maintained centrally in the Institution Repository in CSN and then replicated to APs and NA/NGs;
- Sign technical messages: Signing / Signature validation to verify integrity at ebMS messages
- Secure Communication AP to AP Message Encryption: Message encryption at ebMS level in the International Domain
- Sign business messages: Signing / Signature validation to verify integrity of SEDs at the business level

The above cases are described in the ' EESSI -Architecture Overview Document '. The following diagram presents the security domains used in  EESSI and illustrates the certificate usage scenarios for each EESSI application domain.

Figure 4: Certificates usage scenarios for each EESSI application domain

<!-- image -->

## International Domain

<!-- image -->

- TLS Authentication and Authorisation: Between AP → CSN, AP → AP. Each Access Point has a TLS Authorisation list, which contains all other Access Points and CSN  certificate  thumbprints.  This  list  is  maintained  centrally  on  the  CSN  and synchronised towards the Access Points.
- TLS  Channel: Between  AP → CSN,  AP → AP. TLS  Pass-Through  is recommended.
- Message Authentication and Authorisation: The signing certificate must belong to the sending institution/node for any message type at ebMS (technical) level. The "authorisation  lists"  of  institutions/nodes  which  can  send  messages  is  maintained centrally in the Institution Repository in CSN and then replicated to APs and NA/NGs.
- Sign ebMS messages : Signing / Signature validation to verify integrity at ebMS level.
- AP to AP Message Encryption at the ebMS level.

## EESSI Domain

- Message Authentication and Authorisation : The ebMS signing certificate must be assigned to the sending institution/node for any message type at ebMS level. The "authorisation  lists"  of  institutions/nodes  which  can  send  ebMS  messages  is maintained centrally in the Institution Repository in CSN and then replicated to APs and NA/NGs via the synchronisation mechanism.
- Sign ebMS messages : Signing / Signature validation of ebMS messages to verify message integrity and to have message non-repudiation at ebMS messaging level.
- Sign business message s: Signing / Signature validation to verify integrity and to have  SED  non-repudiation  at  business  level.  National  Applications  will  perform signature validation for SEDs. The SEDs have to be signed by institutions with a valid certificate with corresponding public key being registered in the Institution Repository.

## 3.1.1 Recommended Architecture Directions on CA Hierarchies

A certificate can be issued by any approved Certificate Authority.

The recommended architecture directions regarding the issuance of certificates are:

- Use of National CAs for National Trust Domains and EESSI Trust Domain.
- Use of sTesta CA for International Trust Domain (CSN and APs will use certificates issued by sTesta CA).
- Use of Authorisation List for establishing trust between EESSI organisations - one authorisation list for each Trust Domain.
- The public key certificates used for EESSI Trust Domain Authorisation lists will be stored in the CSN Institution Repository and will be synchronised in AP.
- The International Trust Domain Authorisation List will be stored locally on each Access Point and on CSN. This list can be configured by AP/CSN administrators.
- The National Trust Domain Authorisation List will be stored locally on each Access Point. This list can be configured by AP administrators.
- National Applications will only trust their local Access Point.

This  approach  offers  the  flexibility  for  the  Participating  Countries  to  install  certificates issued by National CAs to be used for authentication between NA/NG and local Access Point, and also for message signature / signature validation.

<!-- image -->

The corresponding public key of the ebMS and business signing certificates have to be uploaded in the CSN Institution Repository and included in the corresponding Authorisation Lists for National Trust Domains and EESSI Trust Domain.

For the International Trust Domain, CSN and APs will use certificates issued by sTESTA CA. Additional recommendations on certificate usage:

- The digital certificate used for signing technical messages should not be the same with the digital certificate used for TLS communication.
- A generic digital certificate that represents the Institution will be used for business signature.

## 3.1.2 Certificate usage split by communication segment

If we break down the certificate usage by segment of communication, AP → AP

- TLS channels (authentication &amp; encryption).
- TLS authorisation for International Trust Domain.
- ebMS Signing / Signature validation (ebMS signatures).
- Message encryption.

## NA/NG → AP

- TLS channels (authentication &amp; encryption).
- TLS authorisation for National Trust Domain.
- ebMS Signing / Signature validation (ebMS signatures).
- Business Signature.

NA → NA (approx. 10,000 institutions)

- Signing / Signature validation (ebMS signatures).
- Signing / Signature validation (business signatures).

## AP → CSN

- TLS channels (authentication &amp; encryption).
- TLS authorisation for International Trust Domain.
- ebMS Signing / Signature validation (ebMS signatures).

## 3.1.3 Recommended Architecture Directions on PKI

The following architecture directions are related to Public Key Infrastructure:

- Node's identity (AP, NA, NG) has to be provided by a digital certificate.
- The Certificate Authorities, Registration Authority and Revocation Authority services will be used from third parties (a list with the CAs to be used in EESSI has to be agreed).

To summarise, certificates have three functions in the EESSI architecture:

- TLS authentication and authorisation and secure channel
- ebMS Signature and optional AP to AP encryption
- Business Signature

<!-- image -->

The next sections are providing additional details on certificate usage.

## 3.1.4 Using Certificates for Business Signature

Business signature is described in the architecture document: ' EESSI - Business Message Signing '

The technical solution used for business message signing is the XAdES Basic Electronic Signature (hereunder 'XAdES -BES' or 'XAdES') enveloped format where the signature will be made exclusively for the business document/ SED.

XAdES-BES stands for XML Advanced Electronic Signatures -Basic Electronic Signature, and is an extension for the IETF/W3CXML-Signature Syntax and Processing specification (XMLDSIG) that includes support for non-repudiation. The standards defined in XAdES aim to  generate  advanced  electronic  signatures  that  remain  valid  over  long  periods,  are compliant with the European  Directive EU-DIR-  and  incorporate  additional useful information in common use cases (like indication of the commitment got by the signature production).

Figure 5: Enveloped format signature

<!-- image -->

## 3.1.5 Certificate Requirements

Certificates  used  in  the  EESSI  system  must  follow  a  set  of  requirements.  Both  the certificate templates, as well as all key elements and algorithm requirements regarding asymmetric encryption, symmetric encryption, hashing, key derivation and TLS 1.2 cipher suites can be found in the document: ' EESSI Certificate &amp; Cryptographic Key Management Standard (SEC 3.2c) .'

## 3.2 Certificate Deployment Overview

The following certificates are deployed and used on the various EESSI systems:

## On the Central Service Node

- TLS Certificate for connection to the International network (TESTA).
- ebMS Certificate for the Central Service Node.

## On the Access Point

- TLS Certificate for connection to the International network (TESTA).
- TLS Certificate for connection to the National network.
- ebMS Certificate for the Access Point.

## On the National Application

- TLS Certificate for connection to the National network.
- ebMS Certificate for the National Application.
- Business Signature Certificate for the National Application.

Figure 6: Certificate Deployment Overview

<!-- image -->

## 3.2.1 Obtaining Certificates

Certificates can be obtained from the following certification authorities:

- TESTA Certification Authority (provided by EESSI Central Service Desk)
- o TLS and ebMS certificates for CSN and AP (International domain).
- o Issued on testa.eu domain name.
- National Certification Authorities
- o TLS Certificate for AP (National domain).
- o TLS, ebMS and Business Signature certificates for NA.
- o Issued on national domain names.

<!-- image -->

<!-- image -->

Service Desk facilitates the process of obtaining certificates for the Access Point needed for the International Domain -TLS AP certificate and ebMS AP certificate. Certificates are based  on  the  CSR  received  from  the  Member  State  according  to  the 'EESSI -  AP  MS Certificate Request Procedur e' .

## 3.2.2 Description and Scope of RINA Certificates

<!-- image -->

National

Network

Figure 7: Certificates for NA

Business Signature Certificate: used for signing SEDs created by RINA/NAs:

- The certificate is issued on the National domain name.
- The private key is installed on RINA/NA.
- The public key is stored in Institution Repository.

ebMS Certificate: used for signing ebMS messages created by the RINA/NA

- The certificate is issued on the National domain name.
- The private key installed on RINA/NA.
- The public key is stored in Institution Repository.

TLS Certificate:

used for authentication and authorisation of TLS connection to AP

- The certificate is issued on the RINA server FQDN.
- The private key is installed on RINA/NA.
- The thumbprint of the certificate can be included in the authorisation list of the Access Point by the AP Administrator.

The public keys for the Business Signature and ebMS certificates are imported by the IR SPOC in  the  Institution  Repository  and  associated  to  the  Institution.  This  operation  is performed using the CSN Institution Repository Management Console (IMC).

<!-- image -->

## NOTE:

TLS Certificates of RINA/NA are not stored in the Institution Repository at CSN (IR)

## 3.3 Certificate Management in RINA

## 3.3.1 Certificates used in RINA

RINA uses the following stores for certificates:

- the Key Stores contain private keys used by RINA and
- the Trust Stores contain public keys from the local AP server.

To enable RINA to connect to the local Access Point (AP), at least the following certificates need to be imported in the corresponding stores.

Table 1: Certificate Management in RINA

| Key                                                                                                                                              | Private Storage                                                                                                                                                                                                                                     | Public Key Trust Storage   |
|--------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------|
| • Content: National Application Private Key for TLS (key password must be supervisor) • Name: tlskeystore.jks • JKS default password: supervisor | • Content: Access Point Public Key for TLS (National Domain) • Name: tlstruststore.jks • JKS default password: supervisor                                                                                                                           | Authentication (TLS)       |
| • Content: National Application Private Key for ebMS signature • Name: privatekeys.jks • JKS default password: supervisor                        | • Content: Access Point Public Key for ebMS signature (International/Testa Domain) • Name: publickeys.jks • JKS default password: supervisor                                                                                                        | Authorisation (Signatures) |
| • Content: National Application Private Key for Business Signature • Name: businessSignatureKeystore.jks • JKS default password: supervisor123   |                                                                                                                                                                                                                                                     | Business Signature         |
| • • •                                                                                                                                            | Content: All Certification Authorities (Root, Intermediate and Issuer) required to build the chain of trust for all certificates used by all National domains and International Domain (Testa) Name: trustedcerts.jks JKS default password: trusted | Certificate Authority (CA) |

## 3.3.2 Certificate Management Procedures for RINA

Use the following procedures to import the required certificates in RINA.

## Importing the certificates in RINA (see Figure 8)

- Access RINA Admin Portal and login as admin user.
- Select the ' Messaging Settings/Certificates ' .
- Select ' New TLS Private certificate) ' .

<!-- image -->

Figure 9: Adding the certificate

## 3.4 Steps to obtain RINA certificates

This  RINA  Certificates  Updating  procedure  is  followed  in  order  to  handle  RINA/NA certificates (root and intermediate) in EESSI ecosystem and aims to facilitate a smoother implementation of the EESSI software security features. The procedure applies every time

<!-- image -->

- Select from the dropdown list the type of certificate you want to import

Figure 8: Importing the TLS certificates in RINA

<!-- image -->

## Adding the certificate (see 9a and 9b)

- Import the certificate by pressing the import certificate button
- The button will transform, click it again to import the certificate
- Introduce the KeyStore password and the certificate password (if it is a private key)
- Click save

<!-- image -->

## Figure 9a

Figure 9b

<!-- image -->

<!-- image -->

the  RINA/NA  certificates  expire  and  need  to  be  re-issued.  These  certificates  (root  and intermediate) are checked by-default in RINA/NA and, in order not to impact the system functionality, the counter party's certificates (root and intermediate) need to be imported locally in RINAs/NAs. In  short,  countries  are  asked  to  provide  the  root  and  intermediate  (one  or  many) certificates for your National Applications (RINA/NA) to the Services Desk email address (EMPL-EESSI-SERVICE-DESK@ec.europa.eu). Based on this, the EESSI Service Desk will centralize and update all the root and intermediates certificates received from Member States  in  the  files  described  below;  these  files  can  be  easily  imported  by  the  systemadministrators in their RINA/NA. Additional tools are also made available as per below, namely scripts for importing the certificates in the AP or for verifying the accuracy of the import procedure.

The steps of RINA Certificates handling procedure are described below:

- Send separate  emails  to  the  EESSI  Service  Desk  concerning  the  three different environments (TEST/ACC/PROD) -this is important in order to optimize the size and content of the JKS (for RINAs/NAs) and it's highly recommended not to mix certificates between environments.
- Email subject -make sure that always use the relevant email subject in accordance with the pattern applicable for each system environment (Test / Acc / Prod), i.e.:
- o Root and intermediate certificates (Test env) -[Institution name] -[Country Code]
- o Root and intermediate certificates (Acc env) -[Institution name] -[CountryCode]
- o Root and intermediate certificates (Prod env) -[Institution  name] -[CountryCode]
- Attach to the email the archive (zip archive is recommended) containing the certificates per environment; change the file extension from '.zip' to another one (i.e. '.zzz' ) in order to avoid any potential filtering of the mail systems.
- Follow  the  certificates'  naming  convention below:  The  naming  convention proposal received from countries should be followed and to ensure that the JKS file will be more transparent and more relevant for all MSs (everyone will be able to see which country/institution's certificates are included in the JKS) you are kindly asked to rename the root and intermediate certificates before sending them as follows:
- o Certificates for a single institution:
- [ROOT-CA]\_COUNTRY CODE\_INSTITUTION CODE\_CERTIFICATE NAME.cer Example: '[ROOT -

CA]\_NO\_NAVT002\_Buypass\_Class\_3\_Test4\_Root\_CA.cer'

- [CA]\_COUNTRY CODE\_INSTITUTION CODE\_CERTIFICATE NAME.cer Example: '[CA]\_NO\_NAVT002\_Buypass\_Class\_3\_Test4\_CA\_3.cer'
- o Certificates used by many/all institutions in that country:
- [ROOT-CA]\_COUNTRY CODE\_ALL\_CERTIFICATE NAME.cer Example : ' [ROOTCA]\_NO\_ALL\_Buypass\_Class\_3\_Test4\_Root\_CA.cer'
- [CA]\_COUNTRY CODE\_ALL\_CERTIFICATE NAME.cer Example: '[CA]\_NO\_ALL\_Buypass\_Class\_3\_Test4\_CA\_3.cer'.

The following deliverables concerning RINA certificates are available on confluence under Release Management Space (https://citnet.tech.ec.europa.eu/CITnet/confluence/pages/viewpage.action?spaceKey=E ESSI&amp;title=EESSI+root+and+intermediates+certificates+handling)

<!-- image -->

Note: The page is updated with the latest information and procedures regarding the CA certificates management so you should check it periodically.

Table 2: Provided ".jks" files on EESSI confluence space

| Deliverable                  | Comments                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| TEST_trustedcerts_v_ *_*.jks | The up-to-date JKS files (per environment) containing the root and intermediates certificates (including the T-Systems root and intermediates certificates). These files can be directly imported in RINA/NA by renaming the published JKS file to 'trustedcerts.jks' and replacing the existing 'trustedcerts.jks' from your RINA/NA with the renamed one. Don't forget to add also the national TLS certification authorities for your RINA/NA and AP. |
| ACC_trustedcerts_v_* _*.jks  | The up-to-date JKS files (per environment) containing the root and intermediates certificates (including the T-Systems root and intermediates certificates). These files can be directly imported in RINA/NA by renaming the published JKS file to 'trustedcerts.jks' and replacing the existing 'trustedcerts.jks' from your RINA/NA with the renamed one. Don't forget to add also the national TLS certification authorities for your RINA/NA and AP. |
| PROD_trustedcerts_v_ *_*.jks | The up-to-date JKS files (per environment) containing the root and intermediates certificates (including the T-Systems root and intermediates certificates). These files can be directly imported in RINA/NA by renaming the published JKS file to 'trustedcerts.jks' and replacing the existing 'trustedcerts.jks' from your RINA/NA with the renamed one. Don't forget to add also the national TLS certification authorities for your RINA/NA and AP. |

Some valueable recommendations and prerequisites concerning the replacement of RINA certificates are presented on the Table below:

Table 3: Recommendations and Risks on the process of replacing RINA Certificates

| Component/ Certificate            | Recommendations                                                                                                                                                                                                                                                                                                       | Risks/Issues                                                       |
|-----------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------|
| RINA Business & ebMS Certificates | • Add the certificates in RINA (private key) before the expiration of the existing certificates. • The certificate activation in RINA follows the addition of certificates to the Institution Repository (IR) of CSN. Due of IR synchronisation the information new Certificates at AP level.                         | to the delays process, of could be missing and National (receiver) |
| RINA TLS Certificate              | • Replace the certificates in RINA (private key) before the expiration of the existing certificates. Only one TLS Certificate should be active at RINA level. • The corresponding Certificate at the AP level (public key) should be Possible delays due to Certificates configuration/ installation at the AP level. |                                                                    |

## 4 RINA Logging Configuration

## 4.1 Introduction

Each RINA component stores relevant information about the performed actions and current status to dedicated log files. Some of them are directly accessible through RINA Portal (GUI) and/or corresponding CPI endpoints.

The  amount  of  information  that  RINA  software  stores  to  the  logs  is  adjustable,  by configuring the logging capabilities (i.e. the administrator is able to increase the amount of log information when an issue makes it necessary to gather as much information as possible, or to decrease the amount when there is not enough space in the File System (FS) to store the gathered data).

The RINA administrator has full access to the Technical Logging information through the RINA Admin Portal.

Technical  Logs provide  basic  troubleshooting  information  directly  in  the  RINA  Admin portal. Similarly to the case of Audit Logs, the administrator can perform very granular searches in order to find dates, types of information, and areas of interest.

## 4.2 Scope and Objectives

The objectives of the chapter ' RINA Logging Configuration ' are:

- To provide an overview of the used libraries and logging utilities ( 'Log4j' )
- To provide an overview of the 'Logstash' logs processing tool that used to collect, process and store the logs in the Elasticsearch
- To describe the RINA components logging functionality along with:
- o the applied logging utility (Log4j or proprietary)
- o the location of the log files
- o the location of the configuration files
- o the critical parameters and recommended/default  logging levels
- o the relevant Databases on which the logs are stored using RINA Back-end
- o the tools used to collect, process, stream and store the logs/data collection on the relevant databases

## 4.3 Logs in File system

Since it is very important for the administrator to be aware of the location each log file is stored,  a  detailed  list  with  the  log  generated  per  RINA  module  and  the  corresponding location  is  given  on  the  Tables  below  (see  Table  4  for  Windows  and  Table  5  for  Linux deployment).

<!-- image -->

Table 4: Logs in File system for WINDOWS OS

<!-- image -->

<!-- image -->

| ElasticSearch   | EESSl\Elasticsearch\logs     |
|-----------------|------------------------------|
| HolodeckB2B     | EESSI\HolodeckB2B\logs       |
| LoadBalancer    | EESSl\Apache\logs            |
| PostgresSQL     | EESSI\PostgreSQL\12\data\log |
| Rest            | EESSi\Tomcat\logs            |
| BUC Engine      | EESSi\Tomcat\logs            |
| APClient        | EESSi\Tomcat\logs            |
| BMIWS           | EESSl\Tomcat\logs            |
| Logstash        | EESSl\Logstash\logs          |
| CAS             | EESSi\Tomcat\cas\logs        |

Table 5: Logs in File system for Linux

<!-- image -->

<!-- image -->

| ElasticSearch   | /eessi/elasticsearch/logs   |
|-----------------|-----------------------------|
| HolodeckB2B     | /eessi/holodeckb2b/logs     |
| LoadBalancer    | /var/log/apache2            |
| PostgresSQL     | /var/log/postgresql         |
| Rest            | /eessi/tomcat/logs          |
| BUC Engine      | /eessi/tomcat/logs          |
| APClient        | /eessi/tomcat/logs          |
| BMIWS           | /eessi/tomcat/logs          |
| Logstash        | eessi/logstash/logs         |
| CAS             | /eessi/tomcat/cas/logs      |

## 4.4 Logging Information and Rotation

## 4.4.1 Log4j logging utility (library)

Log4j is a logging/tracing utility (library) initially developed in the SEMPER project (part of the European Commission's ACTS Programme). It is distributed under the Apache Software License, a fully-fledged open source license certified by the open source initiative.

The latest version of log4j (log4j v2.x), includes full-source code and documentation can be found at ' https://logging.apache.org/log4j/2.x/ ' . Additional information can be found at ' https://en.wikipedia.org/wiki/Log4j ' .

There are 8 standard logging levels available to RINA administrator, as presented below (Table 6):

<!-- image -->

<!-- image -->

Table 6: Logging levels of Log4j logging utility

| Standard log levels built-in to Log4j   | Standard log levels built-in to Log4j   |
|-----------------------------------------|-----------------------------------------|
| Standard Level description              | intLevel                                |
| OFF                                     | 0                                       |
| FATAL                                   | 100                                     |
| ERROR                                   | 200                                     |
| WARN                                    | 300                                     |
| INFO                                    | 400                                     |
| DEBUG                                   | 500                                     |
| TRACE                                   | 600                                     |
| ALL                                     | Integer.MAX_VALUE                       |

In Log4j 2 utility, custom log levels can be easily defined in code or in configuration files.

The following RINA  components are using Log4j utility either natively or via additional modules in order to configure the way of keeping log data:

- REST (CPS)IBUC Engine
- ElasticSearch
- Logstash
- BMI
- APClient
- CAS
- Holodeck

RINA components that do not use Log4j, but incorporate their own logging functionality are the following:

- LoadBalancer
- PostgreSQL

Logs from the various RINA components are aggregated using Logstash, and they are stored in Elasticsearch.

## 4.4.2 Logstash log processing tool

Logging information from different RINA components is collected and stored (forwarded) in ElasticSearch by using Logstash log processing tool.

Logstash aggregates the logs fromCPS and BMS components.

Holodeck component logs do not get persisted into the ElasticSearch database.

The Logstash tool generates log info in logfile and the default configuration is a rolling log with a maximum size of 1 GB. Depending on the number of Logstash operations, this might not be enough and may need to be adjusted. The old log data is overwritten when log is reaching capacity.

Logstash  collects  and  processes  the  RINA  components  logging  data  so  its  proper configuration  affects  the  RINA  overall  logging  procedure.  Actually,  Logstash  should  be configured properly by using the relevant configuration file.

<!-- image -->

The  following  diagram  depicts  the  RINA  logging  architecture,  as  it  was  previously explained. Please note this is the default Log4J configuration. RINA Administrators could define different logging strategies by modifying the Log4J and Logstash configuration.

Figure 10: RINA Logging Architecture -generation flow diagram

<!-- image -->

## 4.4.3 Logging Configuration and Logfile description per Component

## 4.4.3.1 Configuring logging of CPS and BMS

REST and AP Client are using the logging functionality provided by Apache Tomcat, which is based on Log4j.

| Components: CPS (BUC-Engine, CPI, Audit log) and BMS (APClient, BMI-WS)   | Components: CPS (BUC-Engine, CPI, Audit log) and BMS (APClient, BMI-WS)                                                                                                                                                                                                                                            |
|---------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Information                                                               | Description                                                                                                                                                                                                                                                                                                        |
| Location of the Logs                                                      | • Windows: EESSI\REST\Tomcat\logs • Linux: /eessi/rest/tomcat/logs                                                                                                                                                                                                                                                 |
| Location of the Configuration file                                        | REST\Tomcat\shared\lib\log4j2.xml                                                                                                                                                                                                                                                                                  |
| Important Parameters of the configuration file                            | • Appenders : each appender has different attributes associated with it, and these properties indicate the behaviour of the object. o Console defines the default target of the logger for the standard output. o Socket makes it possible to specify the remote socket server's hostname and the port where it is |

<!-- image -->

Table 7: Configuration details of CPS and APClient components

|                                     | listening for log events. Rina declares 3 sockets which are used to communicate to Logstash. o PatternLayout defines the format of a log entry. o RollingFile allows the definition of properties to rotate a log file: file name, file pattern, path, policies, etc. Here 3 RollingFiles have been specified for the Rest api, apclient-audit and ApClient. All three use the default TimeBasedTriggeringPolicy which causes a rollover once the date/time pattern no longer applies to the active file. • Loggers : The main loggers defined are: o Logger root, which defines the log level and behaviour for the technical logger of REST App. o Logger audit, which defines the log level and behaviour for the audit logger of REST and ApClient. o Logger ApClient, which defines the log level and behaviour for the technical logger of ApClient   |
|-------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Default Logging Level               | INFO                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Logs Collection and Processing Tool | Logstash                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| Appender Storage                    | Filesystem (rolling file) - Elasticsearch (Sockets via logstash)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| Logging utility (lib) / (Loggers)   | Log4j 2 utility on Apache Tomcat                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| Suggested production logging level  | INFO                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |

## 4.4.3.2 Configuring logging of CAS

CAS is using the logging functionality provided by Apache Tomcat, which is based on Log4j.

| Components: CAS                                | Components: CAS                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Information                                    | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Location of the Logs                           | • Windows: EESSI\REST\Tomcat\cas\logs • Linux: /eessi/rest/tomcat/cas\logs                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Location of the Configuration file             | REST\Tomcat\cas\config\log4j2.xml                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Important Parameters of the configuration file | • Appenders : each appender has different attributes associated with it, and these properties indicate the behaviour of the object. o Console defines the default target of the logger for the standard output. o PatternLayout defines the format of a log entry. o RollingFile allows the definition of properties to rotate a log file: file name, file pattern, path, policies, etc. Here 3 RollingFiles have been defined with SizeBasedTriggeringPolicy of 10MB. • Loggers : defined by Asynchronous loggers |
| Default Logging Level                          | INFO                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| Logs Collection and Processing Tool            | Logstash                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |

<!-- image -->

Table 8: Configuration details of CAS component

| Appender Storage                   | Filesystem (rolling file) - Elasticsearch (Logstash retrieving data from the Filesystem)   |
|------------------------------------|--------------------------------------------------------------------------------------------|
| Logging utility (lib)              | Log4j 2 utility on Apache Tomcat                                                           |
| Suggested production logging level | WARN                                                                                       |

## 4.4.3.3 Configuring logging of ElasticSearch

Table 9: Configuration details of ElasticSearch component

| Components: ElasticSearch                      | Components: ElasticSearch                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Information                                    | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| Location of the Logs                           | • Windows: EESSI\ElasticSearch\logs • Linux: /eessi/elasticsearch/logs                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| Location of the Configuration file             | \config\log4j2.properties                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| Important Parameters of the configuration file | • Appenders: each appender has different attributes associated with it, and these properties indicate the behaviour of the object. o Console defines the default target of the logger for the standard output. o PatternLayout defines the format of a log entry. o RollingFile allows the definition of properties to rotate a log file: file name, file pattern, path, policies, etc. • Loggers: The Loggers 'index.search.slowlog' and 'index.indexing.slowlog.index' define the log for Elasticsearch logging entries |
| Default Logging Level                          | INFO                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Default log rotation parameter                 | Rolling file Size: maximum 1GB Overwrite the existing data after the size threshold is reached                                                                                                                                                                                                                                                                                                                                                                                                                            |
| Logs Collection and Processing Tool            | Proprietary                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| Appender Storage                               | Filesystem (rolling file)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| Logging utility (lib)                          | Through Elasticsearch plugin implementation of Log4j2                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Suggested production logging level             | WARN (warning)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| Xpack Security Audit log file level            | INFO                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |

## 4.4.3.4 Configuring logging of Holodeck B2B

| Components: Holodeck B2B           | Components: Holodeck B2B                                           |
|------------------------------------|--------------------------------------------------------------------|
| Information                        | Description                                                        |
| Location of the Logs               | • Windows: EESSI\HolodeckB2B\logs • Linux: /eessi/holodeckb2b/logs |
| Location of the Configuration file | conf\log4j2.xml                                                    |

<!-- image -->

Table 10: Configuration details of HolodeckB2B component

| Important Parameters of the configuration file   | • Appenders: each appender has different attributes associated with it, and these properties indicate the behaviour of the object. o PatternLayout defines the format of a log entry. o RollingFile allows the definition of properties to rotate a log file: file name, file pattern, path, policies, etc. • Loggers: define loggers for: o Received ebMS errors o The SOAP Envelopes of outgoing messages o The SOAP Envelopes of received messages o All other logs with ERROR or higher level will be logged   |
|--------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Default Logging Level                            | INFO                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| Logs Collection and Processing Tool              | Proprietary                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Appender Storage                                 | Filesystem (rolling file)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Logging utility (lib)                            | Log4j2                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Type:                                            | The default configuration is a rolling log with a maximum size of 1 GB. Depending on the number of ElasticSearch operations, this may need to be adjusted. The old log data is overwritten when log is reaching capacity.                                                                                                                                                                                                                                                                                          |
| Suggested production logging level               | INFO                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |

## 4.4.3.5 Configuring logging of LoadBalancer

Table 11: Configuration details of LoadBalancer component

| Components: LoadBalancer                       | Components: LoadBalancer                                                                                                                                                                                                                                                                                                                                                                      |
|------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Information                                    | Description                                                                                                                                                                                                                                                                                                                                                                                   |
| Location of the Logs                           | • Windows: EESSI\Apache\logs • Linux: /var/log/apache2                                                                                                                                                                                                                                                                                                                                        |
| Location of the Configuration file             | EESSI \Apache\conf\httpd.conf                                                                                                                                                                                                                                                                                                                                                                 |
| Important Parameters of the configuration file | • ErrorLog: defines the location of the error logfile. • ErrorLogFormat: makes it possible to specify what supplementary information is logged in the error log in addition to the actual log message. • LogLevel: defines the logging level and consequentially the number of messages logged to the error log. Possible values are: DEBUG, INFO, NOTICE, WARN, ERROR, CRIT, ALERT and EMERG |
| Default Logging Level                          | DEBUG                                                                                                                                                                                                                                                                                                                                                                                         |
| Logs Collection and Processing Tool            | N/A                                                                                                                                                                                                                                                                                                                                                                                           |
| Appender Storage                               | N/A                                                                                                                                                                                                                                                                                                                                                                                           |
| Logging utility (lib)                          | Default Apache logging functionality                                                                                                                                                                                                                                                                                                                                                          |
| Suggested production logging level             | WARN                                                                                                                                                                                                                                                                                                                                                                                          |

## 4.4.3.6 Configuring logging of PostgreSQL

Table 12: Configuration details of PostgreSQL component

| Components: PostgreSQL                                          | Components: PostgreSQL                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|-----------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Information                                                     | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Location of the Logs                                            | • Windows: EESSI\PostgreSQL\12\data\log • Linux: /var/log/postgresql                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| Location of the Configuration file                              | Postgresql.conf                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Important Parameters of the configuration file                  | • log_destination: output type (device) of the log. • log_directory: directory where log files are written. • log_filename: log filename pattern • log_rotation_age: this parameter defines the time period after which the automatic logfiles rotation happens • log_rotation_size: on reaching this specific logfile size, automatic logfiles rotation happens • client_min_messages: controls which message levels are sent to the client • log_min_messages: controls which message levels are written to the server log • log_min_ error_statement: define the logging level per logging type. |
| Default Logging Level (depending on the logging type selection) | • Notice (for the case of client_min_messages) • Warning (for the case of log_min_messages) • Error (for the case of log_min_error_statement)                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Logs Collection and Processing Tool                             | N/A                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| Appender Storage                                                | Filesystem (rolling file)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Logging utility (lib)                                           | Default logging functionality of PostgesSQL.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Suggested production logging level                              | WARN                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |

<!-- image -->

<!-- image -->

<!-- image -->

## Recommendations - Guidelines:

1. The default logging level for the relevant Audit and Technical logs for all RINA application modules is set to ' INFO '
2. It is not recommended to change the logging level of the Technical Logs in  the  Production  environment  because  it  affects  the  level  of  logging details  aggregated  by  Logstash  and  inserted  in  Elasticsearch  and consequently the quantity of the stored logging data.
3. The default logging level for Audit logs is ' INFO ' and it is recommended to  remain  unchanged  because  all  the  provided  logging  info  has  been classified under ' INFO ' level.
4. It is always recommended to save a copy of the original configuration file provided in the RINA distribution before any change.
5. Changes to the configuration file should be applied only for troubleshooting  purposes.  It  is  recommended  to  save  a  copy  of  the configuration  file  before  applying  any  change  and  to  revert  log  level changes to the suggested ones as soon as the troubleshooting is finalised by debugging the application and collecting/analysing the appropriate data.
6. In  general,  the  logging  configuration  (i.e.,  rotation,  level  etc)  should meet the national  policies  having  in  mind,  before  any  change  on  the Production  (especially  of  the  logging  level),  that  the  influence  on  the system performance and resources should be exhaustively checked.
7. REST,  APClient,  CAS  andBUC  Enginee  logs  are  appended  to  the ElasticSearch database by Logstash.
8. The logs generated by Holodeck module are not inserted/appended by Logstash to the ElasticSearch database.

## NOTE:

Any  description  of  the  logging  provided  in  this  chapter  of  the 'RINA Operations Manual' refers to the default configuration delivered with EESSI RINA Installation KIT.

RINA administrator may modify the logging configuration by changing the relevant  configuration  file  (i.e.,  log4j2.xml)  according  to  the  National Application  needs and  according to the information  needed  for debugging purposes whenever a problem/issue occurs.

Nevertheless, note that any modification to the configuration of the socket appenders (that store the logs on the Elasticsearch) and/or to any logger related to them (that generate the logs) affects the RINA Portal Functionality of Technical and Audit Logs and the logs availability accordingly.

<!-- image -->

## 4.5 Audit Trail

The audit trail is a sequence of chronological records of EESSI system related events to enable the investigation of different type of incidents. These events associate to domain (business) auditing from the perspective of both the case management and application (i.e. configuration elements) context.

## 4.5.1 RINA Audit Trail Architecture

The (layers of) components generating audit data in RINA are the following ones:

- CPS
- BMS (ApClient component)

Figure 11: RINA Audit Trail architecture -Component view

<!-- image -->

## 4.5.2 Audit Trail Persistence

- Case Processing Services store audit logs (events) into the PostgreSQL Database. The  persistence  of  the  audit  events  triggered  by  CPI  is  performed  inside  the transaction of the triggering operation, to ensure that no action that is performed is not audited.
- Business Messaging Services ( ApClient component ) store audit events via the log4j infrastructure, configured by default to persist audit events in a log file using the FileAppender but also to Elasticsearch via the Logstash using SocketAppender.

## 4.5.3 Audit Trail Retrieval

Audit Events of CPS can be retrieved via CPI, and are also available in the Portal as and admin (all event types) or business (events associated to each case) user.

Audit Events of BMI can be retrieved by Elasticsearch, or/and log file, depending on the configuration of log4j.

Of  course,  Audit  events  can  be  also  retrieved  directly  from  both  repositories.  the PostgreSQL of CPS (or/and Elasticsearch).

<!-- image -->

## 4.6 Audit Trail Data Model

All different RINA Components use the same Audit Trail Data model to enable consistency and easier aggregation.

The following diagram shows the set of UML classes involved in RINA Audit Trail, as well as their relationships.

Figure 12: RINA Audit Data Model

<!-- image -->

Regarding the different domains of the Audit Model, there are two different representations

- SQL Tables for CPS in PostreSQL.
- JSON Document for CPI (CPS component layer), BMS (ApClient component layer) in Elasticsearch/Audit File.

## 4.6.1 Audit Event

An audit event is any triggered event for which a record will be created in the audit-trailing repository.

An audit event is identified by its ID and contains generic and specific info about the event depending on the category and respective event.

| Attribute       | Description                                                                                                   | Data Type          |
|-----------------|---------------------------------------------------------------------------------------------------------------|--------------------|
| Id              | The ID of the audit event                                                                                     | String             |
|                 | The type of action which is executed which can be one of the following: create, read, update, delete, execute | Action EActionType |
| userName        | The username of the user who triggered the action                                                             | String             |
| networkLocation | The network location are the identification details (machine                                                  | NetworkLocation    |

<!-- image -->

<!-- image -->

<!-- image -->

|                | & IP) on which the action has been triggered                                        |                     |
|----------------|-------------------------------------------------------------------------------------|---------------------|
| Date           | Date of the audit event                                                             | DateTime            |
| source         | The source of the event which has three attributes (category, component, type)      | EventSource         |
| outcome        | The outcome of the action triggered which can be success, error or unauthorised     | EOutcomeType        |
| outcomeDetails | When outcome is error or unauthorised, the outcomeError contains the error message. | String              |
| auditedObjects | The audited objects which are identified by id, type and details                    | List<AuditedObject> |
| participants   | The list of participants to the triggered action.                                   | List<Participant>   |
| tenantId*      | The tenantId of the tenant that triggered the action.                               | String              |

* tenantId is only available in the persisted representation (under SQL for  CPS component layer, under File/ES for BMS component layer) -hence not available through the CPI or Admin Portal.

Some Audit Trail examples taken from RINA Administrator portal are presented on Figure 13 where the fields specified  in  Audit  Trail  Event  are  pointed  out  on  a  real  Audit  trail example.

Figure 13 : An example of the Audit trail Event and the corresponding fields on a detailed list of Audit logs on RINA administration portal.

<!-- image -->

Note:  the complete RINA Audit trail data model specifications can  be found in RINA Architecture Overview document.

## 5 Configuring eTranslation Module

<!-- image -->

## 5.1 Request CEF Credentials

The administrator needs to obtain service credentials from CEF Digital team before start using the eTranslation service.

The administrator should request for ' application ' and ' password '.

Password is needed in case the CEF secure endpoint is used.

! No other information is needed to be sent to CEF Digital Team.

More details can be found here:

https://ec.europa.eu/cefdigital/wiki/display/CEFDIGITAL/Machine+Translation+service+d esk

## 5.2 Populate configuration

Next, you need to configure the CEF service parameters in the file

For Ubuntu 18.04

/eessi/tools/eTranslation-1.1.0/config/cef.properties

For Windows 2016

C:\EESSI\Tools\eTranslation-1.1.0\config\cef.properties based on the credentials that you have received from CEF Digital team.

- The eTranslation proxy parameters in the file

For Ubuntu 18.04

/eessi/tools/eTranslation-1.1.0/config/cef.properties

For Windows 2016

C:\EESSI\Tools\eTranslation-1.1.0\config\proxy.properties

<!-- image -->

<!-- image -->

## ! The eTranslation.properties file is deprecated, shall be deleted if exists

| cef.application       | MANDATORY                         | Name of the client application provided by CEF Digital team. This parameter is used by the service to check if the application is an allowed client. Any application name needs to be authorized by the CEF service before it can be used.   |
|-----------------------|-----------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| cef.defaultUri        | MANDATORY                         | The CEF Non-Secure Endpoint URI Default value: https://webgate.ec.europa.eu/etranslation/si/ WSEndpointHandlerService                                                                                                                        |
| cef.secure            | MANDATORY                         | If true the CEF Secure Endpoint will be used. Recommended value is true, since CEF Non- Secure Endpoint might be discontinued by CEF. Default value: true                                                                                    |
| cef.secure.password   | MANDATORY (if cef.secure is true) | Application password, provided by CEF Digital Team.                                                                                                                                                                                          |
| cef.secure.defaultUri | MANDATORY (if cef.secure is true) | The CEF Secure Endpoint URI Default value: https://webgate.ec.europa.eu/etranslation/si/ SecuredWSEndpointHandlerService?WSDL                                                                                                                |
| cef.priority          | OPTIONAL                          | Priority value provided by CEF Digital team. Values must be between 0 and 9, with 9 being the highest priority. Default value: 5                                                                                                             |
| cef.username          | OPTIONAL                          | The username of the submitter provided by CEF Digital team.                                                                                                                                                                                  |

Table 13: CEF Properties for eTranslation Module

| server.port         | MANDATORY   | Server port for eTranslation application   |
|---------------------|-------------|--------------------------------------------|
| server.callback.url | MANDATORY   | Public URL (IP and port) of the machine.   |

<!-- image -->

Will be used to receive the call- back CEF response.

Table 14: Proxy Properties for eTranslation Module

After  the  completion  the cef.properties and proxy.properties files  should  look  like  the examples below:

## #######################################

# CEF eTranslation Service properties # #######################################

- # !!! IMPORTANT NOTE #

- # 'cef.application' and 'cef.secure.password' are the ONLY property values needed to be requested from CEF Team (by email or else)

- # Please, do not send the complete file content to CEF Team, but only request for "application" and "password"

## #######################################

- # Application name to use CEF eTranslation service

- # Provided by CEF Team (should be requested by email or else)

cef.application=TestApplication2019

## #######################################

- # CEF Non-Secure Endpoint URI

- cef.defaultUri=https://webgate.ec.europa.eu/etranslation/si/WSEndpointHandlerService

## #######################################

- # CEF Secure Endpoint Configurations

- # If 'cef.secure' is true the Secure Endpoint of CEF eTranslation service will be used ('cef.secure.defaultUri')

- # In this case is MANDATORY to provide a correct value for the 'cef.secure.password' and 'cef.secure.defaultUri.

- # Recommendation is to use TRUE, since non secure endpoint might be discontinued by CEF #

- # If "false" the NON Secure Endpoint of CEF eTranslation service will be used (cef.defaultUri)

- # In this case is optional to provide a value for the "cef.password" property above

## cef.secure=true

- # Password, Provided by CEF Team (should be requested by email or else) cef.secure.password=mypasswordvalue2019 e?WSDL

- cef.secure.defaultUri=https://webgate.ec.europa.eu/etranslation/si/SecuredWSEndpointHandlerServic

## #######################################

- # Other OPTIONAL CEF eTranslation properties

- # The commented property-value pairs are the default used by the application

- # Uncomment if you need to modify the value

- # Priority of the CEF eTranslation request (might be discontinued by CEF).

- #cef.priority=5

- # The username of the submitter. This is free text that can be used as an additional identifier #cef.username=?

## #############################################

- # RINA eTranslation Proxy Server Properties #

#############################################

<!-- image -->

```
# The port that the RINA eTranslation Proxy Server will start server.port=8087 # The Base URL of the server running RINA eTranslation Proxy Server, that can be accessed in the Internet # Will be used to receive Callback HTTP Requests from CEF eTranslation Service # # i.e. server.callback.url=http://my.domain.com.or.ip:8081 # # You can test this setting by starting the server and navigating to the <server.callback.url>/actuator/health i.e. http://my.domain.com.or.ip:8081/actuator/health. # This should return { "status": "UP"} server.callback.url=http://my.domain.com.or.ip:8081 # Logging related settings # Enable if you want to change the Logging Level. (TRACE level will print input data) # logging.level.eu.ec.dgempl.translation = INFO # Timeout in seconds for the translation request. # eTranslation.service.response.timeout = 20
```

## 5.3 Start eTranslation service

Finally, the eTranslation module can be started by running from command line the following command

java -jar eTranslation-1.1.0.jar

## 5.4 Integration with RINA Portal

In the new version of the RINA Portal, the URL used by the portal for connecting to the eTranslation proxy server is configured in the file :

Ubuntu 18.04:

eessi/apache/portal\_new/assets/etranslation.json

Windows 2016:

C:\EESSI\Apache\htdocs\portal\_new\assets\etranslation.json

By default,  the  URL  is  ""  (empty  string).  This  value  of  the  URL  is  based  on  the  IP  or hostname of the server where the eTranslation proxy server is running, application port and / translation/ endpoint. (ex. http://localhost:8087/translation/ )

## 6 NIE Communication via SSL

This chapter describes one example of configuring NIE in a secure way.

## 6.1 High Level Description

RINA NIE Microservice is acting as the client and the NA National Implementation as the server of a two way SSL connection.

<!-- image -->

## 6.2 Limitations

If the NIE Microservice is configured to use 2-way SSL, then all the endpoints configured as  NIE  NA  Servers  shall  be  secured  (via  RINA  Admin),  since  we  cannot  have  different configuration for different endpoints in RINA other than the URL.

Nevertheless,  we  still  can  support  more  than  one  endpoints,  if  we  have  the  necessary public key of them in the trustore of the NIE Microservice. (see explanation below)

## 6.3 Configuration

Configuration A -Client and Server Side

Both client and server shall have a key-store with their own key, and a trust store that includes the public key/certificate of the other.

Configuration B -Server side

On the server part, if for example you are using a NA implementation deployed in Tomcat, you can modify the server.xml as follows to enable the two way SSL.

```
<Connector port="8449" maxThreads="150" scheme="https" secure="true" SSLEnabled="true" clientAuth="true"  sslProtocol="TLS" keystoreFile="<PATH_OF_THE_KEYSTORE>.jks" keyAlias="<KEY_ALIAS_VALUE>" keystorePass="<KEYSTORE_PASSWORD>" truststoreFile="<PATH_OF_THE_TRUSTORE>.jks"
```

<!-- image -->

/&gt;

## Configuration C -Client

On the client part,

RINA NIE Microservice is using Jersey Http Client that is creating the POST HTTP requests Jersey can be configured via the JVM environmental variables like described below:

- -Djavax.net.ssl.keyStore Location of the Java keystore file containing the certificate and private key.
- -Djavax.net.ssl.keyStorePassword Password to access the private key from the keystore file specified by javax.net.ssl.keyStore. This intends to unlock the keystore file (store password) and to decrypt the private key stored in the keystore (key password).
- -Djavax.net.ssl.trustStore - Location of the Java keystore file containing also the certificate of the server
- -Djavax.net.ssl.trustStorePassword -  Password  to  unlock  the  keystore  file specified by javax.net.ssl.trustStore.

## 7 Portal Data Importer

Portal Data Importer tool is a Java application for importing or updating translations and forms metadata for RINA Portal. It requires Java version 11 and the tool is deployed by RINA Kit in the destination folder, by default C:\EESSI\Tools or /eessi/tools

Before running the tool, please edit following parameters in config\jpa\db.properties:

```
spring.postgresql.rina.datasource.user spring.postgresql.rina.datasource.password spring.postgresql.rina.datasource.serverName spring.postgresql.rina.datasource.portNumber
```

```
spring.postgresql.rina.datasource.databaseName
```

Run the tool in command line:

java -jar portalDataImporter-1.1.jar

<!-- image -->

<!-- image -->

## 8 Adjust Online Contextual Help to a new language

The contextual online help of the RINA User and Admin portals (containing in a structured way the information given by the relevant manuals), by default is provided only in English. In the case, the administrator intends to adjust the online help (especially the online help of the user portal that focus on the RINA clerks), should perform the following steps.

The online contextual help implements a functionality that allows user to retrieve/see - in the  context  of  the  application -information  similar  to  Manuals,  which  are  delivered  in English  only.  Moreover,  is  clearly  specified  (Annex  2  of  the  AC  315/17)  that "the information does not refer however to specific national aspects/context' .

Fortunately, the way the feature was designed and implemented allows translation of the contextual  help,  depending  on  the  Language  value  set  in  the  RINA  User  Settings,  as follows:

- All the contextual help files to be translated are located in '… EESSI\Apache\htdocs\portal\_new\assets\help\ ' :
- o admin and clerk online manuals table of content for admin and clerk sections of RINA Portal,
- o content of the online manuals for admin and clerk sections of RINA Portal
- o folders including images used inside the online manuals for admin and clerk sections of RINA Portal
- In order to translate the Admin Portal contextual help is necessary to do the following steps:
1. Access the location of the help files: go to the following location EESSI\Apache\htdocs\portal\_new\assets\help\ '

## Table of Contents

2. Make a copy of the file ' admin\_toc\_en.json ' ( online manual Table of Content) and rename it to ' admin\_toc\_ &lt;LANGUAGE&gt;.json' where &lt;LANGUAGE&gt; could be as follows: bg, cs, da, de, el, es, et, fi, fr, hr, hu, it, lt, lv, mt, nl, no, pl, pt, ro, sk, sl, sv (e.g. admin\_toc\_de.json)
3. Translate  manually  the  content  of  the 'admin\_toc\_&lt;LANGUAGE&gt;.json' file: translate the titles into your desired language
4. Copy the translated 'admin\_toc\_&lt;LANGUAGE&gt;.json' file at the location specified at step 1

## Admin Online Manual and Images

5. Make a copy of the file 'admin\_manual\_en.html' and rename it to 'admin\_manual\_&lt;LANGUAGE&gt;.html', where &lt;LANGUAGE&gt; could be as follows: bg, cs, da, de, el, es, et, fi, fr, hr, hu, it, lt, lv, mt, nl, no, pl, pt, ro, sk, sl, sv (e.g. admin\_manual\_de.json)
6. Translate manually the con tent of the file 'admin\_manual\_&lt;LANGUAGE&gt;.html' into your desired language
7. Make a copy of the folder admin\_img\_en and retake all the screenshots while you are logged in using the localization settings set for your desired language; change the name of the folder to admin\_img\_&lt;LANGUAGE&gt;
4. 8.
5. Change all the references to the screenshots inside the admin\_manual\_&lt;LANGUAGE&gt;.html (e.g. &lt;img class="contextual-help-image" src="./assets/help/admin\_img\_&lt;LANGUAGE&gt;/figure34.png" /&gt; instead of &lt;img class="contextual-help-image" src="./assets/help/admin\_img\_en/figure34.png" /&gt;) and add additional ones
6. depending on the localisation needs for each separate language

<!-- image -->

9. Copy  the  translated  'admin\_manual\_&lt;LANGUAGE&gt;.json'  file at  the  location specified at step 1
10. Copy  the  adjusted  screenshots  from  the  application  as  a  folder  named admin\_img\_&lt;LANGUAGE&gt;  at the location specified at step 1
- In order to translate the User Portal contextual help:
1. Access the location of the help files: go to the following location EESSI\Apache\htdocs\portal\_new\assets\help\ '

Table of Content

2. Make a copy of the file ' user \_toc\_en.json' (online manual Table of Content) and rename it to ' user \_toc\_&lt;LANGUAGE&gt;.json' where &lt;LANGUAGE&gt; could be as follows: bg, cs, da, de, el, es, et, fi, fr, hr, hu, it, lt, lv, mt, nl, no, pl, pt, ro, sk, sl, sv (e.g. user\_toc\_de.json)
3. Translate  manually  the  content  of  the  ' user \_toc\_&lt;LANGUAGE&gt;.json' file  : translate the titles into your desired language
4. Copy the translated ' user \_toc\_&lt;LANGUAGE&gt;.json' file at the location specified at step 1

User Online Manual and Images

5. Make a copy of the file ' user \_manual\_en.html' and rename it to ' user \_manual\_&lt;LANGUAGE&gt;.html', where &lt;LANGUAGE&gt; could be as follows: bg, cs, da, de, el, es, et, fi, fr, hr, hu, it, lt, lv, mt, nl, no, pl, pt, ro, sk, sl, sv (e.g. user\_manual\_de.json)
6. Trans late manually the content of the file ' user \_manual\_&lt;LANGUAGE&gt;.html' into your desired language
7. Make a copy of the folder user\_img\_en and retake all the screenshots while you are logged in inside the RINA Portal using your desired language; change the name of  the  folder  to  user\_img\_&lt;LANGUAGE&gt;  (e.g.  folder  name  should  be 'user\_img\_de')
8. Change all the references to the screenshots inside the user\_manual\_&lt;LANGUAGE&gt;.html  (e.g.  &lt;img  class="contextual-help-image" src="./assets/help/user\_img\_&lt;LANGUAGE&gt;/figure38.png" /&gt; instead of &lt;img class="contextual-help-image"  src="./assets/help/user\_img\_en/figure34.png" /&gt;)  and  add  additional  ones  depending  on  the  localisation  needs  for  each separate language
9. Copy  the  translated  'user\_manual\_&lt;LANGUAGE&gt;.json' file  at  the  location specified at step 1
10. Copy  the  adjusted  screenshots  from  the  application  as  a  folder  named user\_img\_&lt;LANGUAGE&gt;  at the location specified at step 1

<!-- image -->

Note : National EESSI teams keep the responsibility to produce their own manual translations and follow the above-mentioned guidelines to create the new language-specific online contextual help and make it available to RINA platform and RINA clerks.

<!-- image -->

## 9 Additional Parameters configuration

## RINA User/Admin Portal:

- Max Idle  time  (Portal  timeout) :  The  administrator,  by  using  the  'Max  Idle time' parameter, can configure the idle time for RINA clients and as specified time goes by, the clients are automatically disconnected (logged out) from RINA portal. The default value is 15 minutes. Any activity (i.e., mouse movements) restarts the Idle Time counter/timer.
- Tomcat Session timeout :  The  clients  can  also  be  disconnected  from  RINA  system after specific idle periods of the application server. Apache Tomcat session timeout mainly occurs due to longer idle sessions. Usually, the default session timeout in the Apache Tomcat application server is 30 minutes. Unless it is set as per the application requirement,  it  can  result  in  website  errors.  Consequently,  the  clients  can  be disconnected from RINA portal even if there is activity on the Portal that does not result (or generate) to any relative activity of the application server (i.e. any activity like mouse movements that does not activate a CPI call, does not restart the Session timeout timer).

## Holodeck :

- PurgeAfterDays: this  Holodeck  parameter  is  used  to  configure  (from  RINA)  the Holodeck purging functionality and affects directly the messages retention period on HolodeckB2B.  Therefore,  when  the  configured  purge  time  is  shorter  than  the maximum period of retries, Holodeck B2B is not be able to execute the complete retry  cycle.  By  taking  the  specific  problem  into  consideration,  a  new  configurable parameter has been included ( ' PurgePullAfterDays ') and the default values are the following:
- o 'PurgeAfterDays': 7 days.
- o 'PurgePullAfterDays': 1  day.  It  concerns  the  pull  requests  and  the  received 'Empty MPC' Error messages .

## RINA Business Signatures:

- RINA administrator imports all the relevant certificates (Authentication, Authorisation and  Business)  as  needed,  by  selecting  the  corresponding ' jks '  files  through  the provided RINA admin portal interface. All the certificates can be considered as system certificates  but  the  'Business  Signatures'  can  be  set  at  the  user  level  (i.e.  the administrator can select which certificate to assign to a specific user while creating the user).

<!-- image -->

## Annex 1: Examples on RINA logging Configuration

## REST / APClient Example configuration file: \Tomcat\shared\lib\log4j2.xml

```
<?xml version="1.0" encoding="UTF-8"?> <Configuration status="INFO"> <Appenders> <Console name="console" target="SYSTEM_OUT"> <PatternLayout pattern="%d{HH:mm:ss.SSS} [%t] %-5level %logger{36} - %msg%n"/> </Console> <RollingFilefileName="${sys:catalina.home}/logs/rest-api.log" filePattern="${sys:catalina.home}/logs/rest-api-%d{MM-dd-yyyy}.log" name="RollingFile"> <PatternLayout pattern="%d{HH:mm:ss.SSS} [%t] %-5level %logger{36} - %msg%n"/> <Policies> <TimeBasedTriggeringPolicy/> </Policies> </RollingFile> <RollingFile fileName="${sys:catalina.home}/logs/apclient.log" filePattern="${sys:catalina.home}/logs/apclient-%d{MM-dd-yyyy}.log" name="RollingFile-apcLient"> <PatternLayout pattern="%d{HH:mm:ss.SSS} [%t] %-5level %logger{36} - %msg%n"/> <Policies> <TimeBasedTriggeringPolicy/> </Policies> </RollingFile> <Socket host="127.0.0.1" name="syslog-restlog" port="4563" reconnectionDelayMillis="100"> <RFC5424Layout newLine="true" newLineEscape=" #"> <LoggerFields> <KeyValuePair> <Key>priority</Key> <Value>%p</Value> </KeyValuePair> <KeyValuePair> <Key>stack_trace</Key> <Value>%ex</Value> </KeyValuePair> <KeyValuePair> <Key>thread</Key> <Value>%t</Value> </KeyValuePair> <KeyValuePair> <Key>logger_name</Key> <Value>%logger{36}</Value> </KeyValuePair> </LoggerFields> </RFC5424Layout> </Socket> <Socket host="127.0.0.1" name="syslog-apclientlog" port="4565" reconnectionDelayMillis="100"> <RFC5424Layout newLine="true" newLineEscape=" #"> <LoggerFields> <KeyValuePair> <Key>priority</Key> <Value>%p</Value> </KeyValuePair> <KeyValuePair> <Key>stack_trace</Key> <Value>%ex</Value> </KeyValuePair>
```

<!-- image -->

```
<KeyValuePair> <Key>thread</Key> <Value>%t</Value> </KeyValuePair> <KeyValuePair> <Key>logger_name</Key> <Value>%logger{36}</Value> </KeyValuePair> </LoggerFields> </RFC5424Layout> </Socket> <Socket host="127.0.0.1" name="syslog-auditlog" port="4569" reconnectionDelayMillis="100"> <RFC5424Layout newLine="true" newLineEscape=""> <LoggerFields> <KeyValuePair> <Key>priority</Key> <Value>%p</Value> </KeyValuePair> <KeyValuePair> <Key>stack_trace</Key> <Value>%ex</Value> </KeyValuePair> <KeyValuePair> <Key>thread</Key> <Value>%t</Value> </KeyValuePair> <KeyValuePair> <Key>logger_name</Key> <Value>%logger{36}</Value> </KeyValuePair> </LoggerFields> </RFC5424Layout> </Socket> </Appenders> <Loggers> <Root level="info"> <AppenderRef ref="console"/> <AppenderRef ref="syslog-restlog"/> <AppenderRef ref="RollingFile"/> </Root> <Logger additivity="false" level="info" name="audit"> <AppenderRef ref="syslog-auditlog"/> <AppenderRef ref="RollingFile"/> </Logger> <Logger additivity="false" level="info" name="eu.ec.dgempl.apclient"> <AppenderRef ref="syslog-apclientlog"/> <AppenderRef ref="RollingFile-apcLient"/> </Logger> <Logger additivity="false" level="info" name="eu.europa.ec.rina.apBonitaClient"> <AppenderRef ref="syslog-apclientlog"/> <AppenderRef ref="RollingFile-apcLient"/> </Logger> <Logger level="info" name="net.sf.ehcache"> <AppenderRef ref="console"/> <AppenderRef ref="RollingFile"/> </Logger> </Loggers> </Configuration>
```

## CAS Component example Configuration file: \Tomcat\cas\config\log4j2.xml

```
<?xml version="1.0" encoding="UTF-8" ?> <!-- Specify the refresh internal in seconds. --> <Configuration monitorInterval="5" packages="org.apereo.cas.logging"> <Properties> <!--Default log directory is the current directory but that can be overridden with Dcas.log.dir=<logdir> Or you can change this property to a new default --> <Property name="cas.log.dir">C:/EESSI/REST/Tomcat/cas/logs</Property> <!-- To see more CAS specific logging, adjust this property to info or debug or run server with -Dcas.log.leve=debug --> <Property name="cas.log.level">warn</Property> </Properties> <Appenders> <Console name="console" target="SYSTEM_OUT"> <PatternLayout pattern="%d %p [%c] - &lt;%m&gt;%n"/> </Console> <RollingFile name="file" fileName="${sys:cas.log.dir}/cas.log" append="true" filePattern="${sys:cas.log.dir}/cas-%d{yyyy-MM-dd-HH}-%i.log"> <PatternLayout pattern="%d %p [%c] - &lt;%m&gt;%n"/> <Policies> <OnStartupTriggeringPolicy /> <SizeBasedTriggeringPolicy size="10 MB"/> <TimeBasedTriggeringPolicy /> </Policies> </RollingFile> <RollingFile name="auditlogfile" fileName="${sys:cas.log.dir}/cas_audit.log" append="true" filePattern="${sys:cas.log.dir}/cas_audit-%d{yyyy-MM-dd-HH}-%i.log"> <PatternLayout pattern="%d %p [%c] - %m%n"/> <Policies> <OnStartupTriggeringPolicy /> <SizeBasedTriggeringPolicy size="10 MB"/> <TimeBasedTriggeringPolicy /> </Policies> </RollingFile> <RollingFile name="perfFileAppender" fileName="${sys:cas.log.dir}/perfStats.log" append="true" filePattern="${sys:cas.log.dir}/perfStats-%d{yyyy-MM-dd-HH}-%i.log"> <PatternLayout pattern="%m%n"/> <Policies> <OnStartupTriggeringPolicy /> <SizeBasedTriggeringPolicy size="10 MB"/> <TimeBasedTriggeringPolicy /> </Policies> </RollingFile> <CasAppender name="casAudit"> <AppenderRef ref="auditlogfile" /> </CasAppender> <CasAppender name="casFile"> <AppenderRef ref="file" /> </CasAppender>
```

<!-- image -->

<!-- image -->

```
<CasAppender name="casConsole"> <AppenderRef ref="console" /> </CasAppender> <CasAppender name="casPerf"> <AppenderRef ref="perfFileAppender" /> </CasAppender> </Appenders> <Loggers> <!-- If adding a Logger with level set higher than warn, make category as selective as possible --> <!-- Loggers inherit appenders from Root Logger unless additivity is false --> <AsyncLogger name="org.apereo" level="${sys:cas.log.level}" includeLocation="true"/> <AsyncLogger name="org.apereo.services.persondir" level="${sys:cas.log.level}" includeLocation="true"/> <AsyncLogger name="org.apereo.cas.web.flow" level="info" includeLocation="true"/> <AsyncLogger name="org.apache" level="debug" /> <AsyncLogger name="org.apache.http" level="error" /> <AsyncLogger name="org.springframework" level="info" /> <!--<AsyncLogger name="org.springframework.cloud.server" level="debug" /> <AsyncLogger name="org.springframework.cloud.client" level="debug" /> <AsyncLogger name="org.springframework.cloud.bus" level="debug" /> <AsyncLogger name="org.springframework.aop" level="debug" /> <AsyncLogger name="org.springframework.boot" level="debug" /> <AsyncLogger name="org.springframework.boot.actuate.autoconfigure" level="debug" /> <AsyncLogger name="org.springframework.webflow" level="debug" /> <AsyncLogger name="org.springframework.session" level="debug" /> <AsyncLogger name="org.springframework.amqp" level="error" /> <AsyncLogger name="org.springframework.integration" level="debug" /> <AsyncLogger name="org.springframework.messaging" level="debug" /> <AsyncLogger name="org.springframework.web" level="debug" /> <AsyncLogger name="org.springframework.orm.jpa" level="debug" /> <AsyncLogger name="org.springframework.scheduling" level="debug" /> <AsyncLogger name="org.springframework.context.annotation" level="debug" /> <AsyncLogger name="org.springframework.boot.devtools" level="debug" /> <AsyncLogger name="org.springframework.web.socket" level="debug" /> --> <AsyncLogger name="org.thymeleaf" level="warn" /> <AsyncLogger name="org.pac4j" level="warn" /> <AsyncLogger name="org.opensaml" level="warn"/> <AsyncLogger name="net.sf.ehcache" level="warn" /> <AsyncLogger name="com.couchbase" level="warn" includeLocation="true"/> <AsyncLogger name="com.ryantenney.metrics" level="warn" /> <AsyncLogger name="net.jradius" level="warn" /> <AsyncLogger name="org.openid4java" level="warn" /> <AsyncLogger name="org.ldaptive" level="warn" /> <AsyncLogger name="com.hazelcast" level="warn" /> <AsyncLogger name="org.jasig.spring" level="warn" /> <!-- Log perf stats only to perfStats.log --> <AsyncLogger name="perfStatsLogger" level="info" additivity="false" includeLocation="true"> <AppenderRef ref="casPerf"/> </AsyncLogger> <!-- Log audit to all root appenders, and also to audit log (additivity is not false) --> <AsyncLogger name="org.apereo.inspektr.audit.support" level="info" includeLocation="true" > <AppenderRef ref="casAudit"/>
```

<!-- image -->

```
</AsyncLogger> <!-- All Loggers inherit appenders specified here, unless additivity="false" on the Logger --> <AsyncRoot level="warn"> <AppenderRef ref="casFile"/> <!--For deployment to an application server running as service, delete the casConsole appender below --> <AppenderRef ref="casConsole"/> </AsyncRoot> </Loggers> </Configuration>
```

## ElasticSearch example Configuration file: \config\log4j2.properties

```
status = error # log action execution errors for easier debugging logger.action.name = org.elasticsearch.action logger.action.level = debug appender.console.type = Console appender.console.name = console appender.console.layout.type = PatternLayout appender.console.layout.pattern = [%d{ISO8601}][%-5p][%-25c{1.}] %marker%m%n appender.rolling.type = RollingFile appender.rolling.name = rolling appender.rolling.fileName = ${sys:es.logs.base_path}${sys:file.separator}${sys:es.logs.cluster_name}.log appender.rolling.layout.type = PatternLayout appender.rolling.layout.pattern = [%d{ISO8601}][%-5p][%-25c{1.}] %marker%.-10000m%n appender.rolling.filePattern = ${sys:es.logs.base_path}${sys:file.separator}${sys:es.logs.cluster_name}-%d{yyyy-MM-dd}.log appender.rolling.policies.type = Policies appender.rolling.policies.time.type = TimeBasedTriggeringPolicy appender.rolling.policies.time.interval = 1 appender.rolling.policies.time.modulate = true rootLogger.level = info rootLogger.appenderRef.console.ref = console rootLogger.appenderRef.rolling.ref = rolling appender.deprecation_rolling.type = RollingFile appender.deprecation_rolling.name = deprecation_rolling appender.deprecation_rolling.fileName = ${sys:es.logs.base_path}${sys:file.separator}${sys:es.logs.cluster_name}_deprecation.log appender.deprecation_rolling.layout.type = PatternLayout appender.deprecation_rolling.layout.pattern = [%d{ISO8601}][%-5p][%-25c{1.}] %marker%.-10000m%n appender.deprecation_rolling.filePattern = ${sys:es.logs.base_path}${sys:file.separator}${sys:es.logs.cluster_name}_deprecation-%i.log.gz appender.deprecation_rolling.policies.type = Policies appender.deprecation_rolling.policies.size.type = SizeBasedTriggeringPolicy appender.deprecation_rolling.policies.size.size = 1GB appender.deprecation_rolling.strategy.type = DefaultRolloverStrategy appender.deprecation_rolling.strategy.max = 4 logger.deprecation.name = org.elasticsearch.deprecation logger.deprecation.level = warn logger.deprecation.appenderRef.deprecation_rolling.ref = deprecation_rolling logger.deprecation.additivity = false appender.index_search_slowlog_rolling.type = RollingFile appender.index_search_slowlog_rolling.name = index_search_slowlog_rolling appender.index_search_slowlog_rolling.fileName = ${sys:es.logs.base_path}${sys:file.separator}${sys:es.logs.cluster_name}_index_search_slowlog.log appender.index_search_slowlog_rolling.layout.type = PatternLayout appender.index_search_slowlog_rolling.layout.pattern = [%d{ISO8601}][%-5p][%-25c] %marker%.10000m%n appender.index_search_slowlog_rolling.filePattern = ${sys:es.logs.base_path}${sys:file.separator}${sys:es.logs.cluster_name}_index_search_slowlog-%d{ yyyy-MM-dd}.log
```

<!-- image -->

<!-- image -->

```
appender.index_search_slowlog_rolling.policies.type = Policies appender.index_search_slowlog_rolling.policies.time.type = TimeBasedTriggeringPolicy appender.index_search_slowlog_rolling.policies.time.interval = 1 appender.index_search_slowlog_rolling.policies.time.modulate = true logger.index_search_slowlog_rolling.name = index.search.slowlog logger.index_search_slowlog_rolling.level = trace logger.index_search_slowlog_rolling.appenderRef.index_search_slowlog_rolling.ref = index_search_slowlog_rolling logger.index_search_slowlog_rolling.additivity = false appender.index_indexing_slowlog_rolling.type = RollingFile appender.index_indexing_slowlog_rolling.name = index_indexing_slowlog_rolling appender.index_indexing_slowlog_rolling.fileName = ${sys:es.logs.base_path}${sys:file.separator}${sys:es.logs.cluster_name}_index_indexing_slowlog.l og appender.index_indexing_slowlog_rolling.layout.type = PatternLayout appender.index_indexing_slowlog_rolling.layout.pattern = [%d{ISO8601}][%-5p][%-25c] %marker%.10000m%n appender.index_indexing_slowlog_rolling.filePattern = ${sys:es.logs.base_path}${sys:file.separator}${sys:es.logs.cluster_name}_index_indexing_slowlog-% d{yyyy-MM-dd}.log appender.index_indexing_slowlog_rolling.policies.type = Policies appender.index_indexing_slowlog_rolling.policies.time.type = TimeBasedTriggeringPolicy appender.index_indexing_slowlog_rolling.policies.time.interval = 1 appender.index_indexing_slowlog_rolling.policies.time.modulate = true logger.index_indexing_slowlog.name = index.indexing.slowlog.index logger.index_indexing_slowlog.level = trace logger.index_indexing_slowlog.appenderRef.index_indexing_slowlog_rolling.ref = index_indexing_slowlog_rolling logger.index_indexing_slowlog.additivity = false
```

## Holodeck Logging example Configuration file: conf\log4j2.xml

```
<?xml version="1.0"?> <!-- =====================================================================================< ?xml version="1.0" encoding="UTF-8"?> Holodeck B2B Logging Configuration Holodeck B2B uses the Log4j v2 logging framework, see the Log4j website for more information about configuration. When deploying in a production environment it is recommended to raise log levels to at least INFO. ===================================================================================== --> <Configuration monitorInterval="10" status="warn"><Appenders> <!-- The main log file for all Holodeck B2B related logging --> <RollingFile filePattern="logs/archive/holodeckb2b-%d{yyyyMMdd}-%i.log.gz" fileName="logs/holodeckb2b.log" name="holodeckb2b-main"><PatternLayout><Pattern>%d (%t)[%-5p] %c - %m%n</Pattern></PatternLayout><Policies><SizeBasedTriggeringPolicy size="100MB"/><TimeBasedTriggeringPolicy/></Policies><DefaultRolloverStrategy max="99" compressionLevel="9" fileIndex="min"><Delete maxDepth="2" basePath="${baseDir}"><IfFileName glob="*/holodeckb2b-*.log.gz"/><IfLastModified age="60d"/></Delete></DefaultRolloverStrategy></RollingFile> <!-- Log file for received ebMS errors --> <RollingFile filePattern="logs/archive/ebms_errors-%d{yyyyMMdd}-%i.log.gz" fileName="logs/ebms_errors.log" name="ebmsErrors"><PatternLayout><Pattern>%d - %m%n</Pattern></PatternLayout><Policies><SizeBasedTriggeringPolicy size="100MB"/><TimeBasedTriggeringPolicy/></Policies><DefaultRolloverStrategy max="99" compressionLevel="9" fileIndex="min"><Delete maxDepth="2" basePath="${baseDir}"><IfFileName glob="*/ebms_errors-*.log.gz"/><IfLastModified age="60d"/></Delete></DefaultRolloverStrategy></RollingFile> <!-- Log file for the SOAP Envelopes of outgoing messages. --> <RollingFile filePattern="logs/archive/soap_out-%d{yyyyMMdd}-%i.log.gz" fileName="logs/soap_out.log" name="soapout"><PatternLayout><Pattern>[%d] %m%n</Pattern></PatternLayout><Policies><TimeBasedTri ggeringPolicy/><SizeBasedTriggeringPolicy size="250GB"/></Policies><DefaultRolloverStrategy max="99" compressionLevel="9" fileIndex="min"><Delete maxDepth="2" basePath="${baseDir}"><IfFileName glob="*/soap_out-*.log.gz"/><IfLastModified age="60d"/></Delete></DefaultRolloverStrategy></RollingFile> <!-- Log file for the SOAP Envelopes of received messages. --> <RollingFile filePattern="logs/archive/soap_in-%d{yyyyMMdd}-%i.log.gz" fileName="logs/soap_in.log" name="soapin"><PatternLayout><Pattern>[%d] %m%n</Pattern></PatternLayout><Policies><TimeBasedTrig geringPolicy/><SizeBasedTriggeringPolicy size="250GB"/></Policies><DefaultRolloverStrategy max="99" compressionLevel="9" fileIndex="min"><Delete maxDepth="2" basePath="${baseDir}"><IfFileName glob="*/soap_in-*.log.gz"/><IfLastModified age="60d"/></Delete></DefaultRolloverStrategy></RollingFile></Appenders><Loggers> <!-- Everything with level ERROR or higher will be logged --> <Root level="INFO"><AppenderRef ref="holodeckb2b-main"/></Root> <!-- Default log level for Holodeck B2B is set to ALL so messaging processing can be followed in detail. When deploying in production it is RECOMMENDED to raise log level to at least INFO. --> <Logger name="org.holodeckb2b" level="INFO"/> <!-- Some logging of often recurring tasks is already reduced to prevent clutter --> <Logger name="org.holodeckb2b.pmode.xml.PModeWatcher" level="INFO"/><Logger name="org.holodeckb2b.as4.receptionawareness.RetransmissionWorker" level="INFO"/><Logger name="org.holodeckb2b.ebms3.workers" level="INFO"/><Logger name="org.holodeckb2b.as4.workers" level="INFO"/><Logger name="org.holodeckb2b.ebms3.pulling" level="INFO"/><Logger name="org.holodeckb2b.common.handler.BaseHandler" level="INFO"/> <!-- SOAP Envelope logging The next two logs are used to log the SOAP envelopes of sent and received messages. To enable set the log level to INFO, to disable set to OFF. --> <Logger name="org.holodeckb2b.msgproc.soapenvlog.IN" level="INFO" additivity="false"><AppenderRef ref="soapin"/></Logger><Logger name="org.holodeckb2b.msgproc.soapenvlog.OUT" level="INFO" additivity="false"><AppenderRef ref="soapout"/></Logger>
```

<!-- image -->

<!-- image -->

&lt;!-- Logging of received ebMS Errors Holodeck B2B will by default log all received ebMS Errors to this log. This is independent from the notification of the Error to the business application which is configured in the P-Mode of the message in error. To disable this log, set the log level to OFF. To enable set it to INFO. --&gt;

&lt;Logger name="org.holodeckb2b.msgproc.errors" level="INFO" additivity="false"&gt;&lt;AppenderRef ref="ebmsErrors"/&gt;&lt;/Logger&gt;&lt;/Loggers&gt;&lt;/Configuration&gt;

## PostgreSQL Configuration File: postgresql.conf

```
#------------------------------------------------------------------------------# ERROR REPORTING AND LOGGING #------------------------------------------------------------------------------# - Where to Log -log_destination = 'stderr' # Valid values are combinations of # stderr, csvlog, syslog, and eventlog, # depending on platform.  csvlog # requires logging_collector to be on. # This is used when logging to stderr: logging_collector = on # Enable capturing of stderr and csvlog # into log files. Required to be on for # csvlogs. # (change requires restart) # These are only used if logging_collector is on: #log_directory = 'pg_log' # directory where log files are written, # can be absolute or relative to PGDATA #log_filename = 'postgresql-%Y-%m-%d_%H%M%S.log'  # log file name pattern, # can include strftime() escapes #log_file_mode = 0600 # creation mode for log files, # begin with 0 to use octal notation #log_truncate_on_rotation = off # If on, an existing log file with the # same name as the new log file will be # truncated rather than appended to. # But such truncation only occurs on # time-driven rotation, not on restarts # or size-driven rotation.  Default is # off, meaning append to existing files # in all cases. #log_rotation_age = 1d # Automatic rotation of logfiles will # happen after that time.  0 disables. #log_rotation_size = 10MB # Automatic rotation of logfiles will # happen after that much log output. # 0 disables. # These are relevant when logging to syslog: #syslog_facility = 'LOCAL0' #syslog_ident = 'postgres' # This is only relevant when logging to eventlog (win32): #event_source = 'PostgreSQL' # - When to Log -#client_min_messages = notice # values in order of decreasing detail: #   debug5 #   debug4 #   debug3 #   debug2
```

<!-- image -->

<!-- image -->

```
#   debug1 #   log #   notice #   warning #   error #log_min_messages = warning # values in order of decreasing detail: #   debug5 #   debug4 #   debug3 #   debug2 #   debug1 #   info #   notice #   warning #   error #   log #   fatal #   panic #log_min_error_statement = error # values in order of decreasing detail: #   debug5 #   debug4 #   debug3 #   debug2 #   debug1 #   info #   notice #   warning #   error #   log #   fatal #   panic (effectively off) #log_min_duration_statement = -1 # -1 is disabled, 0 logs all statements # and their durations, > 0 logs only # statements running at least this number # of milliseconds # - What to Log -#debug_print_parse = off #debug_print_rewritten = off #debug_print_plan = off #debug_pretty_print = on #log_checkpoints = off #log_connections = off #log_disconnections = off #log_duration = off #log_error_verbosity = default # terse, default, or verbose messages #log_hostname = off log_line_prefix = '%t ' # special values: #   %a = application name
```

<!-- image -->

```
#   %u = user name #   %d = database name #   %r = remote host and port #   %h = remote host #   %p = process ID #   %t = timestamp without milliseconds #   %m = timestamp with milliseconds #   %i = command tag #   %e = SQL state #   %c = session ID #   %l = session line number #   %s = session start timestamp #   %v = virtual transaction ID #   %x = transaction ID (0 if none) #   %q = stop here in non-session #        processes #   %% = '%' # e.g. '<%u%%%d> ' #log_lock_waits = off # log lock waits >= deadlock_timeout #log_statement = 'none' # none, ddl, mod, all #log_replication_commands = off #log_temp_files = -1 # log temporary files equal or larger # than the specified size in kilobytes; # -1 disables, 0 logs all temp files log_timezone = 'UTC' # - Process Title -#cluster_name = '' # added to process titles if nonempty # (change requires restart) #update_process_title = on
```