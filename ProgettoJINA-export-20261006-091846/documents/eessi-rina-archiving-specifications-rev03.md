---
unique-name: eessi-rina-archiving-specifications-rev03
display-name: EESSI   RINA   Archiving Specifications   rev03
category: GENERAL
tags: ec
---

<!-- image -->

<!-- image -->

## EESSI -RINA Archiving Specifications rev03

Solution / Application Architecture

Employment, Social Affairs andInclusion

## Table of Contents

| Table of Contents ..............................................................................................                                                                                                       | Table of Contents ..............................................................................................                                                                                                       | 2                                                                                                                                                             |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1                                                                                                                                                                                                                      | Archiving overview.......................................................................................                                                                                                              | 6                                                                                                                                                             |
| 1.1                                                                                                                                                                                                                    | Foreword..............................................................................................                                                                                                                 | 6                                                                                                                                                             |
| 1.2                                                                                                                                                                                                                    | Data archiving benefits ..........................................................................                                                                                                                     | 6                                                                                                                                                             |
| 1.3                                                                                                                                                                                                                    | Minimal requirementsfor preservation of data / archiving                                                                                                                                                               | ........................... 7                                                                                                                                 |
| 2 EESSI RINA Scope and Domains of applicability ...............................................                                                                                                                        | 2 EESSI RINA Scope and Domains of applicability ...............................................                                                                                                                        | 8                                                                                                                                                             |
| 2.1                                                                                                                                                                                                                    | Scope ..................................................................................................                                                                                                               | 8                                                                                                                                                             |
| 2.2                                                                                                                                                                                                                    | Domains of applicability                                                                                                                                                                                               | ......................................................................... 8                                                                                   |
| 3 Common RINA Archiving principles.................................................................                                                                                                                    | 3 Common RINA Archiving principles.................................................................                                                                                                                    | 9                                                                                                                                                             |
| 3.1 Message archive approach and configuration                                                                                                                                                                         | 3.1 Message archive approach and configuration                                                                                                                                                                         | ............................................ 9                                                                                                                |
| 3.1.1                                                                                                                                                                                                                  | Approach .......................................................................................                                                                                                                       | 9                                                                                                                                                             |
| 3.1.2                                                                                                                                                                                                                  | Configuration.................................................................................10                                                                                                                       |                                                                                                                                                               |
| 3.2 Archiving locations ...............................................................................11                                                                                                              | 3.2 Archiving locations ...............................................................................11                                                                                                              |                                                                                                                                                               |
| 4 Functions, use cases and actors....................................................................12                                                                                                                | 4 Functions, use cases and actors....................................................................12                                                                                                                |                                                                                                                                                               |
| 4.1                                                                                                                                                                                                                    | Actors.................................................................................................12                                                                                                              |                                                                                                                                                               |
| 4.2                                                                                                                                                                                                                    | Functions                                                                                                                                                                                                              | ............................................................................................12                                                                |
| 4.3                                                                                                                                                                                                                    | Use cases............................................................................................12                                                                                                                |                                                                                                                                                               |
| 5 Behaviour - state machines..........................................................................14                                                                                                               | 5 Behaviour - state machines..........................................................................14                                                                                                               |                                                                                                                                                               |
| 5.1 Case state machine                                                                                                                                                                                                 | 5.1 Case state machine                                                                                                                                                                                                 | ..............................................................................14                                                                              |
| 6 Service contract..........................................................................................15                                                                                                         | 6 Service contract..........................................................................................15                                                                                                         |                                                                                                                                                               |
| 6.1 Intro...................................................................................................15                                                                                                         | 6.1 Intro...................................................................................................15                                                                                                         |                                                                                                                                                               |
| 6.1.1 RINA archiving management graph                                                                                                                                                                                  | 6.1.1 RINA archiving management graph                                                                                                                                                                                  | ..................................................15                                                                                                          |
| 6.1.2 REST API List.................................................................................16                                                                                                                 | 6.1.2 REST API List.................................................................................16                                                                                                                 |                                                                                                                                                               |
| 7 Data contract .............................................................................................18                                                                                                        | 7 Data contract .............................................................................................18                                                                                                        |                                                                                                                                                               |
| 7.1 7.2                                                                                                                                                                                                                | RESTArchivingPolicy RESTArchivingPolicies                                                                                                                                                                              | .............................................................................18 ...........................................................................18 |
| 7.3                                                                                                                                                                                                                    | RESTCaseRetentionPolicy (Deprecated)...................................................18                                                                                                                              |                                                                                                                                                               |
| 7.4                                                                                                                                                                                                                    | RESTRetentionPolicies...........................................................................18                                                                                                                     |                                                                                                                                                               |
| 7.5                                                                                                                                                                                                                    | RESTArchivingVolume...........................................................................18                                                                                                                       |                                                                                                                                                               |
| 7.6                                                                                                                                                                                                                    | RESTArchivingRepositories                                                                                                                                                                                              | ....................................................................19                                                                                        |
| 7.7                                                                                                                                                                                                                    | RESTArchivingRepositoryPolicy (Deprecated)                                                                                                                                                                             | ...........................................19                                                                                                                 |
| 7.8                                                                                                                                                                                                                    | RESTArchivingRepositoriesPolicies (Deprecated).......................................19                                                                                                                                |                                                                                                                                                               |
| 7.9 RESTArchivingOptions...........................................................................19 8 Samples ....................................................................................................20 | 7.9 RESTArchivingOptions...........................................................................19 8 Samples ....................................................................................................20 |                                                                                                                                                               |
| 8.1                                                                                                                                                                                                                    | Retrieve archiving policies (timers) request sample                                                                                                                                                                    | ..................................20                                                                                                                          |
| 8.2                                                                                                                                                                                                                    | Retrieve archiving policies (timers) response sample                                                                                                                                                                   | ................................20                                                                                                                            |
| 8.3                                                                                                                                                                                                                    | Update archiving policies (timers) request sample....................................20                                                                                                                                |                                                                                                                                                               |
| 8.4                                                                                                                                                                                                                    | Update archiving policies (timers) response sample..................................21                                                                                                                                 |                                                                                                                                                               |
| 8.5                                                                                                                                                                                                                    | Retrieve the cases retention policies request sample (Deprecated)                                                                                                                                                      | .............21                                                                                                                                               |
| 8.6                                                                                                                                                                                                                    | Retrieve the cases retention policies response sample (Deprecated)                                                                                                                                                     | ...........21                                                                                                                                                 |
| 8.7                                                                                                                                                                                                                    | Update cases retention policies request sample (Deprecated)                                                                                                                                                            | ....................21                                                                                                                                        |
| 8.8                                                                                                                                                                                                                    | Update cases retention policies response sample (Deprecated)                                                                                                                                                           | ..................21                                                                                                                                          |
| 8.9                                                                                                                                                                                                                    | Retrieve the messages retention policies request sample                                                                                                                                                                | ..........................21                                                                                                                                  |
| 8.10                                                                                                                                                                                                                   | Retrieve the messages retention policies response sample                                                                                                                                                               | ........................21                                                                                                                                    |
| 8.11                                                                                                                                                                                                                   | Update messages retention policies request sample..................................21                                                                                                                                  |                                                                                                                                                               |
| 8.12                                                                                                                                                                                                                   | Update messages retention policies response sample................................21                                                                                                                                   |                                                                                                                                                               |
| 8.13                                                                                                                                                                                                                   | Retrieve archiving repository location request sample...............................21                                                                                                                                 |                                                                                                                                                               |
| 8.14                                                                                                                                                                                                                   | Retrieve archiving repository location response sample.............................21                                                                                                                                  |                                                                                                                                                               |
| 8.15                                                                                                                                                                                                                   | Update archiving repository location request sample.................................22                                                                                                                                 |                                                                                                                                                               |
| 8.16                                                                                                                                                                                                                   | Update archiving repository location response sample...............................22                                                                                                                                  |                                                                                                                                                               |
| 8.17                                                                                                                                                                                                                   | Retrieve archiving repositories policies location request sample (Deprecated)22                                                                                                                                        |                                                                                                                                                               |
| 8.18                                                                                                                                                                                                                   | Retrieve archiving repository location response sample (Deprecated) .........22 Update archiving repositories policies location request sample (Deprecated)22                                                          |                                                                                                                                                               |
| 8.19 8.20                                                                                                                                                                                                              | Update archiving repositories policies location response sample (Deprecated)22                                                                                                                                         |                                                                                                                                                               |

<!-- image -->

9

8.21

8.22

8.23

8.24

8.25

8.26

<!-- image -->

Retrieve archival parameter details for a case request sample ...................  22

Retrieve archival parameter details for a case response sample .................  22

Manually trigger the archiving process request sample  ..............................  22

Manually trigger the archiving process response sample  ............................  23

Manually trigger the un-archiving process request sample  .........................  23

Manually trigger the un-archiving process response sample  .......................  23

References  .................................................................................................  24

<!-- image -->

## Document Control Information

| Document Control                     | Value                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|--------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Project Title                        | Electronic Exchange of Social Security Information (EESSI)                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Document Name                        | EESSI - RINA - Archiving Specifications                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Document Category                    | Solution / Application Architecture                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| Revision                             | rev03                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Component Version                    | -                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| Publication Date                     | 12/02/2021                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Last Update                          | 14/12/2021                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Document Status                      | Final                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Sensitivity (TLP) Distribution terms | The distribution of this document is done strictly in line with the Traffic Light Protocol (TLP) established by the European Commission's note AC 790/15 REV for the EESSI project documentation. In line with the note AC 790/15 REV, this document is labelled as TLP = 'Green'. Therefore, it can be circulated widely within the EESSI community. However, the document or the information herein may not be published or posted on the Internet, nor released outside of the |
| Connected/Embedded Files             | None                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| Authors                              | European Commission, DG EMPL A4, EESSI RINA                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Revised by                           | European Commission, DG EMPL A4, EESSI QA                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Approved by                          | European Commission, DG EMPL A4, EESSI PMO                                                                                                                                                                                                                                                                                                                                                                                                                                        |

## Document history

| Milestone /           | Date       | Changes/Corrections                                                                                 |
|-----------------------|------------|-----------------------------------------------------------------------------------------------------|
| Component version     |            | Description                                                                                         |
| EESSI-2019 RINA 5.6.2 | 30/11/2019 | Update the document metadata file names                                                             |
| EESSI-2019 RINA 5.6.2 | 30/11/2019 | Included ZIP file                                                                                   |
| EESSI-2019 RINA 5.6.2 | 30/11/2019 | Reference to archiving locations                                                                    |
| EESSI-2020 RINA 6.2.1 | 18/12/2020 | Updates for RINA 2020                                                                               |
| EESSI-2020 rev01      | 12/02/2021 | Minor clarifications in section 5.1.                                                                |
| EESSI-2020 rev02      | 13/12/2021 | Clarifications in sections 1 & 3.                                                                   |
| EESSI-2020 rev02      | 13/12/2021 | Clarifications in sections 6.1.2.2 and 7.4                                                          |
| EESSI-2020 rev03      | 14/12/2021 | Rewrite the section 1 to provide additional clarifications on the new RINA archiving implementation |

<!-- image -->

## 1 Archiving overview

## 1.1 Foreword

RINA 2020 brings a new enhancement regarding the message archiving to benefit from the migration to a relational DB -PostgreSQL. The improvement consists in replacing the storage of archives from files on disk to data in the Rina SQL database. This means the archives  are  not  anymore  present  as  files  on  disk,  instead  the  archived  cases  and documents will be flagged as archived in the new SQL database.

Data archiving is the process of marking data as archived in the database (for 'case' and 'message' data) or moving data (for xml messages) that is no longer active to a separate storage device for a longer-term retention. Archive data consists of older data that is still important to the organization and may be needed for future reference, as well as data that must be retained for regulatory compliance.

The name 'archiving' has been retained (from previous versions) for historical reasons, since  the  intention  is  to  avoid  confusion  for  the  users  with  different  terminology. Furthermore, the zipping of the case archiving is no longer performed since this operation can be executed directly on the DB with the new approach. On the other hand, the message archiving has been retained.

Note :  It  is  worth  pointing  that  it  will  be  more  performant  and  logical  for  a  country  to partition a database instance in such a way that all the archived cases reside in a separate partition.

## 1.2 Data archiving benefits

Expected benefits of archiving include:

- Reduced costs . Data archiving is largely, though not exclusively, an effort to lower costs. This is measured as cost / gigabyte stored.
- Compliance .  Governmental  requirements  and  legal  liability  are  key  reasons  to implement a data archiving strategy;
- Knowledge retention. In an era of big data, organizations are learning the value of analysing vast amounts of data. Here, the consideration isn't cost, but the desire to gain a competitive edge in the marketplace;
- Improved performance . By reducing the amount of data to manage, or partitioning unused data from active data, organizations may see substantial improvement in system performance.

<!-- image -->

<!-- image -->

## 1.3 Minimal requirements 1 for preservation of data / archiving

A comprehensive archive policy must exist. This is a formalized set of procedures dictating the rules for the archival process.

Archiving shall meet at minimum the following data archiving requirements:

- Suitability for long-term preservation
- o Use of industry-standard and publicly available file formats
- o Migration of media
- o System change management
- Integrity
- o Guaranteed by storage on media:
- Physical readonly /Write Once Read Many (here under 'WORM');
- Logical read-only /WORM on fixed media with events log and techniques and procedures for detection and prevention of substitution of input;
- Logical read-only /WORM on removable media;
- o Capture process of archives.
- Security
- o Access / Authentication management
- o Backup of archives
- o Controlled archiving operations (identification &amp; traceability)
- o Continuity of access to archives
- Traceability
- o Date and time stamping
- o Maintenance of a technical file (archival policy, standard, general condition of services, lifecycle of document, etc.)
- o Maintenance of audit trail of archives lifecycles and events log.

1 See ISO 14641-1:2012 - Electronic Archiving -Part 1: Specifications concerning the design and operation of an information system for electronic information preservation

<!-- image -->

## 2 EESSI RINA Scope and Domains of applicability

## 2.1 Scope

The  scope  of  archiving  consists  in  all  the  cases  (including  attachments  and  portable documents) for which the status has been set up to 'closed' (local or global 'closed' ) or forwarded (including when the participant is removed from respective case) and messages sent or received.

For these cases and messages, the archival process timer, retention period, and archive repository/location can be specified through a decision table in which the above-mentioned parameters can be set up depending on the Sector, BUC Type and Application Role.

For the cases to be archived the related documents (sent and received) will be archived.

## 2.2 Domains of applicability

The domains of applicability for archiving consist in the local RINA implementation.

## 3 Common RINA Archiving principles

There are four ways by which a case can be archived:

- Firstly, once a case has been removed, which is achieved by forwarding the case to another participant (X007 SED).
- Secondly by removing it, by sending/receiving an X006 SED.
- Thirdly when it has been closed, by sending/receiving an X001 SED.
- Finally, by executing a local close, but in this case this depends on the type of BUC involved.

A case in the above statuses may be archived by:

- Directly by a clerk, who needs to execute the action 'Archive' in the case window.
- Secondly  it  is  performed  automatically  when  the  case  is  in  the 'removed/closed' status and has expired the retention period.

The retention period can be set via the RINA administration portal under RINA Archiving -&gt; Archiving Policies -&gt; Default Period (days).

When a case is archived, it becomes obsolete through the available programmatic and user interfaces  (CPI/NIE/Portal).  Through  those  interfaces,  it  is  only  available  for  searching purposes, it then only displays some context information about that case, including its archived status. The case has to be then unarchived if further information is needed such as reading/editing the SED, comments, attachments etc. As mentioned before, a case in archived status is retained at the DB repository.

## 3.1 Message archive approach and configuration

## 3.1.1 Approach

The messages sent and received will be archived (zipped) following the approach depicted in the table below:

| File to archive                   | File / folder name                                               | Archive name      |
|-----------------------------------|------------------------------------------------------------------|-------------------|
| Received messages                 | Received messages                                                | Received messages |
| Message                           | <received_message_name.xml> <received_message_name.xml> + '.zip' |                   |
| <received_payload_file_name.x ml> | <received_payload_file_name.xml> + '.zip'                        | Payload files     |
| Sent messages                     | Sent messages                                                    | Sent messages     |
| <sent_message_name>               | <sent_message_name> + '.zip'                                     | Message           |
| <sent_payloads_folder_name>       | <sent_folder_payloads_name> + '.zip'                             | Payloads folder   |

<!-- image -->

<!-- image -->

An illustrative example of the above approaches are presented below:

## RECEIVED MESSAGES

- To be archived (message file and payload file):
- o Message file: 1dead413-1a6d-4916-ba7c45ef1d9282ed@10.1.0.6\_SED\_IN\_6b65257b-fe2c-42a5-9163-d689410a0904.xml
- o Payloads file: pl-1dead413-1a6d-4916-ba7c-45ef1d9282ed\_10.1.0.6-6b65257bfe2c-42a5-9163-d689410a0904.xml
- Archived:
1. 1dead413-1a6d-4916-ba7c-45ef1d9282ed@10.1.0.6\_SED\_IN\_6b65257b-fe2c-42a59163-d689410a0904.xml. zip
2. pl-1dead413-1a6d-4916-ba7c-45ef1d9282ed\_10.1.0.6-6b65257b-fe2c-42a5-9163d689410a0904.xml. zip

## SENT MESSAGES

- To be archived (message file and folder which contains the payloads):
1. Message file: 6cf6fe42-fe10-452d-a937-4ecff8190ef6@127.0.1.1.accepted
2. Payloads folder: 6cf6fe42-fe10-452d-a9374ecff8190ef6@127.0.1.1\_payload\_out
- Archived:
1. 6cf6fe42-fe10-452d-a937-4ecff8190ef6@127.0.1.1.accepted .zip
2. 6cf6fe42-fe10-452d-a937-4ecff8190ef6@127.0.1.1\_payload\_out .zip

## 3.1.2 Configuration

In Holodeck B2B there is an option to log the SOAP envelope of all received and sent messages

On the AS4 messaging level the SOAP envelopes are archived and this ensures that only meta-data and no personal/sensitive data is archived.

The  archiving  of  the  SOAP  envelopes  is  now  done  using  the  Log4j  framework,  so  the configuration of the archiving is done through the log4j configuration as below settings (in the conf/log4j.properties file for Holodeck B2B):

## SOAP ENVELOPE LOG INBOUND

## SOAP ENVELOPE LOG OUTBOUND

```
log4j.appender.soapenv_in_FILE=org.apache.log4j.RollingFileAppender log4j.appender.soapenv_in_FILE.File=logs/soapin.log log4j.appender.soapenv_in_FILE.MaxFileSize=5120KB log4j.appender.soapenv_in_FILE.Append=true log4j.appender.soapenv_in_FILE.layout=org.apache.log4j.PatternLayout log4j.appender.soapenv_in_FILE.layout.ConversionPattern=%d{ISO8601} - %m%n log4j.appender.soapenv_out_FILE=org.apache.log4j.RollingFileAppender log4j.appender.soapenv_out_FILE.File=logs/soapout.log log4j.appender.soapenv_out_FILE.MaxFileSize=5120KB log4j.appender.soapenv_out_FILE.Append=true log4j.appender.soapenv_out_FILE.layout=org.apache.log4j.PatternLayout
```

```
log4j.appender.soapenv_out_FILE.layout.ConversionPattern=%d{ISO8601} - %m%n
```

## LOGGERS

## The loggers to configure are:

- log4j.logger.org.holodeckb2b.msgproc.soapenvlog.IN and
- log4j.logger.org.holodeckb2b.msgproc.soapenvlog.OUT

for received respectively sent messages.

The log level should be INFO to enable the logging or higher to disable it.

## SOAP ENVELOPE LOGGERS

```
log4j.logger.org.holodeckb2b.msgproc.soapenvlog.IN=INFO, soapenv_in_FILE log4j.logger.org.holodeckb2b.msgproc.soapenvlog.OUT=INFO, soapenv_out_FILE
```

## APPENDERS

Currently these logs use a RollingFileAppender2 which are used to specify the place where the logs should be created. (through the use of appenders config).

```
log4j.appender.HibFILE=org.apache.log4j.RollingFileAppender log4j.appender.HibFILE.File=logs/hibernate.log log4j.appender.HibFILE.MaxFileSize=5120KB log4j.appender.HibFILE.Append=true log4j.appender.HibFILE.layout=org.apache.log4j.PatternLayout log4j.appender.HibFILE.layout.ConversionPattern=%d{ISO8601}  [%-5p]  %c  %x  %m%n
```

## 3.2 Archiving locations

Archived messages are saved in volumes configured by RINA administrators. Those volume can be configured in the Admin Portal or by using the CPI (information under section 6.1.2 and ' RINA - Case Processing Interface (CPI) -Reference ' documentation) .

Error!  Reference  source  not  found. The  configuration  sets  the  file  path  and  the maximum number of cases to be stored per volume. There are configurations for Message Archiving.

org.apache.log4j  - Class RollingFileAppender:

2

https://logging.apache.org/log4j/1.2/apidocs/org/apache/log4j/RollingFileAppender.html

<!-- image -->

## 4 Functions, use cases and actors

## 4.1 Actors

The actors used in the RINA archiving management interface will be the following:

- RINA Administrator who will manage the parameter of the archiving interface.
- RINA Clerk 3  who will manage archiving actions for cases on which he is owner or have the right to perform such actions
- RINA Automated Archiving system is an automated process which performs the archival based on some defined triggers.

## 4.2 Functions

The main function related to RINA archiving interface management are:

- Archiving policy management;
- Archiving alert/notifications * ;
- Archiving process management.

*Note : The implementation of the notifications management function is done within the service &amp; data contracts related to the archiving repositories

## 4.3 Use cases

The use cases for the RINA Archiving parameters management functions are:

## Archiving policy management:

- Case archive timers' management definition;
- Message archive retention periods management definition;
- Archiving repository location definition;

## Archiving alert/notifications management:

- Alert / notification in case of unavailability of storage space.

## Archiving process management 4 :

- Automatic case archiving;
- Automatic message archiving;

3 The RINA Clerk is having an indirect role in archiving. The archiving process is always automatically triggered after closing a case. The RINA Clerk is the only actor who can execute a local or global close of a case which further on will trigger the archiving process for the respective case.

4 Additionally, to the actions mentioned here there is also the Automatic archiving which is triggered when the case status is changed to closed or forwarded (including the situations when participant is removed). In this cases the archiving process is triggered when the specific archiving timer (specific to each BUC type) is done.

<!-- image -->

<!-- image -->

- Retrieving information about a case in scope of archival process
- Manual case archiving;
- Manual case un-archiving;

Note: The automatic process for archiving is triggered by closing case process (local / global close). Depending on the Sector, BUC Type and Application Role the respective case and messages in scope of archival can have different trigger timers for archiving. Also, it can be associated to trigger (configurable) timers for message retention. The archiving process will also trigger a change in the case status which will be updated to

## ' archived ' .

## 5 Behaviour - state machines

## 5.1 Case state machine

The case state machine is used to keep track of the case state on either the case owner the counterparty/ies sides:

- Open -In this state the sender party (case owner) creates the case, and the receiver party (counterparty) opens the case for the first time. After all the work is done on this particular case, the involved participant may close it. If other participant should be responsible for this case from now on, an existing participant can forward the case. If the case owner is not interested anymore in the case. The case can be deleted if no SEDs have been exchanged. When deleted, a case is removed from the system, and it has no specific status. This action cannot be reversed and the Case cannot be undeleted
- Closed -  The participant closed the case, from this state the case can be opened again; also un-archiving a case which was closed will bring the case from archived back to a closed status;
- Removed -  When  a  case  has  been  forwarded  to  another  participant  or  own participant has been removed and is no longer part of the case; in the latter case, the case will be read-only;
- Archived -A case is archived either automatically by the system following normal archiving  process  (following  case  closing,  case  forwarding,  or  case  removed participant according to the defined timers for respective case's BU C Type), or either manually by the user.

.

<!-- image -->

Figure 1: Case state machine

<!-- image -->

## 6 Service contract

## 6.1 Intro

## 6.1.1 RINA archiving management graph

The Archiving management interface is provided as a RESTful web service that can be modelled with UML where each resource is represented by a class with the stereotype &lt;resource&gt; and the URL is constructed by applying dependencies  with the stereotype &lt;path&gt; between classes

The diagram below shows the UML model for the Archiving management interface:

Figure 2 - Archiving management interface UML model

<!-- image -->

<!-- image -->

## 6.1.2 REST API List

## 6.1.2.1 Archiving policy management API

| HTTP Verb                                                         | URI Structure                                                     | Description                                                        |
|-------------------------------------------------------------------|-------------------------------------------------------------------|--------------------------------------------------------------------|
| Case archive timers management definition                         | Case archive timers management definition                         | Case archive timers management definition                          |
| GET                                                               | /ApplicationProfile/ArchivingPolicies                             | Retrieve the archiving policy (timers)                             |
| PUT                                                               | /ApplicationProfile/ArchivingPolicies                             | Update the archiving policy (timers)                               |
| Case archive retention periods management definition (Deprecated) | Case archive retention periods management definition (Deprecated) | Case archive retention periods management definition (Deprecated)  |
| GET (Deprecated)                                                  | /ApplicationProfile/CaseRetentionPolicies                         | Retrieve the retention period (archive delete timers) for cases    |
| PUT (Deprecated)                                                  | /ApplicationProfile/CaseRetentionPolicies                         | Update the retention period (archive delete timers) for cases      |
| Message archive retention periods management definition           | Message archive retention periods management definition           | Message archive retention periods management definition            |
| GET                                                               | /ApplicationProfile/MessageRetentionPolicies                      | Retrieve the retention period (archive delete timers) for messages |
| PUT                                                               | /ApplicationProfile/MessageRetentionPolicies                      | Update the retention period (archive delete timers) for messages   |
| Archiving repository location definition                          | Archiving repository location definition                          | Archiving repository location definition                           |
| GET                                                               | /ApplicationProfile/ArchivingRepositories                         | Retrieve the location for archive repository                       |
| PUT                                                               | /ApplicationProfile/ArchivingRepositories                         | Update the location for archive repository                         |
| Archiving repositories policies location definition (Deprecated)  | Archiving repositories policies location definition (Deprecated)  | Archiving repositories policies location definition (Deprecated)   |
| GET (Deprecated)                                                  | /ApplicationProfile/ArchivingRepositoriesPolicies                 | Retrieve the location for archive repositories policies            |
| PUT (Deprecated)                                                  | /ApplicationProfile/ArchivingRepositoriesPolicies                 | Update the location for archive repositories policies              |

<!-- image -->

## 6.1.2.2 Archiving process management API

The automatic processes for case archiving and message archiving are managed directly inside the system based on archiving policies, therefore any definition in the below table is not applicable.

| HTTP Verb                                                        | URI Structure                                                    | Description                                                                                                                                                                                           |
|------------------------------------------------------------------|------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Retrieving information about a case in scope of archival process | Retrieving information about a case in scope of archival process | Retrieving information about a case in scope of archival process                                                                                                                                      |
| GET                                                              | /Cases/{id}/ArchivingOptions                                     | Retrieve info about the archiving status (true/false), close/remove date and the date when the case will be archived if it was not archived yet                                                       |
| Manual case archiving/un-archiving                               | Manual case archiving/un-archiving                               | Manual case archiving/un-archiving                                                                                                                                                                    |
| PUT                                                              | /Cases/{id}/ArchivingOptions                                     | Manually trigger the archiving/restoring process for a specific Case. The triggered operation depends on the case state: if the case was archived it will be restored, otherwise it will be archived. |

<!-- image -->

## 7 Data contract

## 7.1 RESTArchivingPolicy

| Attribute         | Description                                                                                                                           | Data Type   |
|-------------------|---------------------------------------------------------------------------------------------------------------------------------------|-------------|
| Id                | The ID of the archiving policy / rule                                                                                                 | Integer     |
| Sector            | The name of the Sector                                                                                                                | String      |
| sectorId          | The ID of the Sector                                                                                                                  | String      |
| bucType           | The business use case                                                                                                                 | String      |
| bucTypeId         | The business use case ID                                                                                                              | String      |
| applicationRole   | The application role                                                                                                                  | String      |
| applicationRoleId | The application role ID                                                                                                               | String      |
| policy            | The archiving timer used by archiving process. Closed or forwarded cases will be archived after the specific time (specified in days) | Integer     |

## 7.2 RESTArchivingPolicies

| Attribute              | Description                                                                                           | Data Type                |
|------------------------|-------------------------------------------------------------------------------------------------------|--------------------------|
| defaultArchivingPeriod | The default value use for the default archiving period. By default this value has been set to 90.     | Integer                  |
| archiveMessages        | This flag is use to check whether the messages should be archived or not.FALSE - will not be archived | boolean                  |
| archivingPoliciesTable | This collection of ArchivingPolicyDto is used to hold the policies that will be archived.             | List<ArchivingPolicyDto> |

## 7.3 RESTCaseRetentionPolicy (Deprecated)

## 7.4 RESTRetentionPolicies

| Attribute                  | Description                                                                                                             | Data Type   |
|----------------------------|-------------------------------------------------------------------------------------------------------------------------|-------------|
| defaultCaseRetentionPeriod | The retention timer used by case archiving process. Archived cases will be deleted after the specified timer (in days). | Integer     |

## 7.5 RESTArchivingVolume

| Attribute         | Description                 | Data Type   |
|-------------------|-----------------------------|-------------|
| archivingVolumeId | Archiving volume identifier | String      |
| archivingVolume   | Archiving volume name       | String      |

3

<!-- image -->

<!-- image -->

| achivingMinSpaceThreshold   | The minimum space threshold per volume for the archiving process (in MB)   | Integer      |
|-----------------------------|----------------------------------------------------------------------------|--------------|
| physicalLocations           | The physical locations attached to volumes                                 | List<String> |

## 7.6 RESTArchivingRepositories

| Attribute                 | Description                                                        | Data Type                  |
|---------------------------|--------------------------------------------------------------------|----------------------------|
| defaultMessagesVolume *   | The volume used for messages archives                              | String                     |
| archivingRepositoriesList | The decision table containing all the archiving repositories rules | List <RESTArchivingVolume> |

## 7.7 RESTArchivingRepositoryPolicy (Deprecated)

## 7.8 RESTArchivingRepositoriesPolicies (Deprecated)

| Attribute   | Description   | Data Type   |
|-------------|---------------|-------------|

## 7.9 RESTArchivingOptions

| Attribute         | Description                                                                                                    | Data Type   |
|-------------------|----------------------------------------------------------------------------------------------------------------|-------------|
| archived          | Flag used for archiving & un- archiving actions. (False - for cases to be archived, True - for archived cases) | Boolean     |
| archivingVolume   | The volume of the archive                                                                                      | String      |
| closedRemovedDate | The date when a case changes its status to CLOSED or FORWARDED/REMOVED and the archival process started        | Date        |
| archivalDate      | The date when a case will be archived (for CLOSED or REMOVED cases) or has been archived (ARCHIVED cases)      | Date        |
| deletionDate      | The estimated date when a case archive should be deleted.                                                      | Date        |

## 8 Samples

## 8.1 Retrieve archiving policies (timers) request sample

GET /ApplicationProfile/ArchivingPolicies

## 8.2 Retrieve archiving policies (timers) response sample

```
{ "defaultArchivingPeriod": 90, "archiveMessages": true, "archivingPoliciesTable": [ { "id": "5baf6e2cd57649ee8af35f774b63337c", "sectorId": "1", "sector": "PENSION", "bucType": "Old Age Pension Claim", "bucTypeId": "P_BUC_01", "applicationRoleId": "PO", "applicationRole": "CaseOwner", "policy": 89 }, { "id": "b461629c03044508a7152cd1cbe9d86e", "sectorId": "1", "sector": "PENSION", "bucType": "Survivors Pension Claim", "bucTypeId": "P_BUC_02", "applicationRoleId": "PO", "applicationRole": "CaseOwner", "policy": 90 }, { "id": "48ea838501fb4715894f1ea741e029a4", "sectorId": "1", "sector": "PENSION", "bucType": "Invalidity Pension Claim", "bucTypeId": "P_BUC_03", "applicationRoleId": "PO", "applicationRole": "CaseOwner", "policy": 90 } ] }
```

## 8.3 Update archiving policies (timers) request sample

```
PUT /ApplicationProfile/ArchivingPolicies { "defaultArchivingPeriod": 90, "archiveMessages": true, "archivingPoliciesTable": [ { "id": "5baf6e2cd57649ee8af35f774b63337c", "sectorId": "1", "sector": "PENSION", "bucType": "Old Age Pension Claim", "bucTypeId": "P_BUC_01", "applicationRoleId": "PO", "applicationRole": "CaseOwner", "policy": 89 }, { "id": "b461629c03044508a7152cd1cbe9d86e", "sectorId": "1", "sector": "PENSION", "bucType": "Survivors Pension Claim", "bucTypeId": "P_BUC_02", "applicationRoleId": "PO", "applicationRole": "CaseOwner", "policy": 90 }, { "id": "48ea838501fb4715894f1ea741e029a4", "sectorId": "1",
```

<!-- image -->

```
"sector": "PENSION", "bucType": "Invalidity Pension Claim", "bucTypeId": "P_BUC_03", "applicationRoleId": "PO", "applicationRole": "CaseOwner", "policy": 90 } ] }
```

## 8.4 Update archiving policies (timers) response sample

N/A

## 8.5 Retrieve the cases retention policies request sample (Deprecated)

GET/ApplicationProfile/CaseRetentionPolicies

## 8.6 Retrieve the cases retention policies response sample (Deprecated)

Ν/Α

## 8.7 Update cases retention policies request sample (Deprecated)

PUT /ApplicationProfile/CaseRetentionPolicies

## 8.8 Update cases retention policies response sample (Deprecated)

N/A

## 8.9 Retrieve the messages retention policies request sample

GET/ApplicationProfile/MessageRetentionPolicies

## 8.10 Retrieve the messages retention policies response sample

```
{ "defaultMessageRetentionPeriod": 90 }
```

## 8.11 Update messages retention policies request sample

```
PUT /ApplicationProfile/MessageRetentionPolicies
```

```
{ "defaultMessageRetentionPeriod": 90 }
```

## 8.12 Update messages retention policies response sample

N/A

## 8.13 Retrieve archiving repository location request sample

GET/ApplicationProfile/ArchivingRepositories

## 8.14 Retrieve archiving repository location response sample

```
{ "archivingRepositoriesList": [ { "archivingVolume": "Volume default cases", "physicalLocations": [ "/all/archiving/cases/" ], "archivingVolumeId": "volumeDefaultCases", "achivingMinSpaceThreshold": 300 }, { "archivingVolume": "Volume default messages", "physicalLocations": [ "/all/archiving/messages/" ], "archivingVolumeId": "volumeDefaultMessages",
```

<!-- image -->

```
"defaultMessagesVolume": "volumeDefaultMessages"
```

```
"achivingMinSpaceThreshold": 300 } ] }
```

## 8.15 Update archiving repository location request sample

```
PUT /ApplicationProfile/ArchivingRepositories { "archivingRepositoriesList": [ { "archivingVolume": "Volume default cases", "physicalLocations": [ "/all/archiving/cases/" ], "archivingVolumeId": "volumeDefaultCases", "achivingMinSpaceThreshold": 300 }, { "archivingVolume": "Volume default messages", "physicalLocations": [ "/all/archiving/messages/" ], "archivingVolumeId": "volumeDefaultMessages", "achivingMinSpaceThreshold": 300 } ]    "defaultMessagesVolume": "volumeDefaultMessages" }
```

## 8.16 Update archiving repository location response sample

N/A

- 8.17 Retrieve  archiving  repositories  policies  location  request  sample (Deprecated)

GET/ApplicationProfile/ArchivingRepositoriesPolicies

- 8.18 Retrieve archiving repository location response sample (Deprecated)

N/A

- 8.19 Update  archiving  repositories  policies  location  request  sample (Deprecated)

PUT /ApplicationProfile/ArchivingRepositoriesPolicies

- 8.20 Update  archiving  repositories  policies  location  response  sample (Deprecated)

N/A

## 8.21 Retrieve archival parameter details for a case request sample

GET /Cases/12/ArchivingOptions

- 8.22 Retrieve archival parameter details for a case response sample

```
{ "archived": false, "closedRemovedDate": "2020-12-10T09:57:13.311Z", "archivalDate": "2020-12-10T09:57:13.311Z" }
```

## 8.23 Manually trigger the archiving process request sample

PUT/Cases/12/ArchivingOptions

<!-- image -->

<!-- image -->

## 9 References

The following references have been used to create this specification and are useful for development:

- ' ISO 14641-1:2012 Electronic Archiving -Part 1: Specifications concerning the design and operation of an information system for electronic information preservation. '

<!-- image -->