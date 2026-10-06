---
unique-name: eessi-rina-6218-reports-configuration-manual
display-name: EESSI   RINA 6.2.18   Reports Configuration Manual
category: GENERAL
tags: ec
---

<!-- image -->

## EESSI -RINA 6.2.18

## Reports Configuration Manual

Operations Manuals &amp; Guides

Employment, Social Affairs andInclusion

<!-- image -->

## Table of Contents

1

2

3

4

Introduction  .................................................................................................  5

1.1

Reference .............................................................................................  5

1.2

1.3

Audience ..............................................................................................  5

Definitions, Acronyms and Abbreviations ..................................................  5

JasperReports ..............................................................................................  6

2.1

Architecture ..........................................................................................  6

Installation  ..................................................................................................  7

3.1

Setup a RINA reporting DB .....................................................................  7

3.2

3.3

3.4

Install JasperReport Server  .....................................................................  7

Configure Data Source ...........................................................................  7

Upload provided report templates ............................................................  7

Reports Customization ..................................................................................  8

4.1

Customization Procedure ........................................................................  8

4.2

Figures  .................................................................................................  9

<!-- image -->

<!-- image -->

## Document Control Information

| Document Control                        | Value                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|-----------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Project Title                           | Electronic Exchange of Social Security Information (EESSI)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Document Name                           | EESSI - RINA Reports Configuration Manual                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Document Category                       | Operations Manuals & Guides                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| Revision                                | -                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Component Version                       | RINA 6.2.18                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| Portal Version                          | RINA 6.2.19                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| Last Publication Date Project Milestone | 22/12/2021 EESSI 2020                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Document Status                         | Final                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Sensitivity (TLP) Distribution terms    | Traffic Light Protocol (TLP) = ' GREEN ' The distribution of this document is done strictly in line with the Traffic Light Protocol (TLP) established by the European Commission's note AC 790/15 REV for the EESSI project documentation. In line with the note AC 790/15 REV, this document is labelled as TLP = 'Green'. Therefore, it can be circulated widely within the EESSI community. However, the document or the information herein may not be published or posted on the Internet, nor released outside of the EESSI community. |
| Connected/Embedded Files                | None                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Authors                                 | European Commission, DG EMPL A4, EESSI RINA/DevOps                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Revised by                              | European Commission, DG EMPL A4, EESSI QA/QC                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| Approved by                             | European Commission, DG EMPL A4, EESSI PMO team                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |

## Document history

| Project Milestone                         | Date       | Changes/Corrections Description   |
|-------------------------------------------|------------|-----------------------------------|
| EESSI-2020 RINA 6.2.1                     | 18/12/2020 | Initial Document                  |
| EESSI-2020 RINA 6.2.18 RINA Portal 6.2.19 | 22/12/2021 | Minor version updates             |

<!-- image -->

## 1 Introduction

This document describes the option for reporting in RINA. Also describes the procedure for the end user to customize the existing RINA reporting templates.

## 1.1 Reference

References

## Jaspersoft Community Website: https://community.jaspersoft.com/ PostgreSQL Website: https://www.postgresql.org/

## 1.2 Audience

The applicable Audience of the documents

## 1.3 Definitions, Acronyms and Abbreviations

List of the definitions (Glossary), Acronyms and Abbreviations

<!-- image -->

## 2 JasperReports

JasperReports is an open-source Java reporting tool that can write to a variety of targets, such as: screen, printer, into PDF, HTML, Microsoft Excel, RTF, ODT, Comma-separated

values or XML files.

It  can be used in Java-enabled applications, including Java EE or web applications, to generate dynamic content.

In  the  context  of  RINA,  there  are  2  relevant  products,  JasperReports  Studio  and JasperReports Server.

JasperReports  Studio  is  an  IDE  based  on  Eclipse  and  used  to  create  and  modify  the reporting templated. Reports can also be manually run in the Studio or transferred to the JasperReports Server application, where the runs can be scheduled.

JasperReports Server is a java EE application, so more suited to run on a server.

## 2.1 Architecture

Best practice would be to replicate or sync the data from the RINA DB to a database created for reporting. The instruction in this manual assumes the used of PostgreSQL as is used for the RINA DB. JasperReports can be configured to query several different SQL databases  and  well  as  other  types  of  Databases  or  Data  Structures,  so  there  is  no limitation to use PostgreSQL, but the provided templates might not work unless modified if another data source is used.

The  JasperReports  Server  software  can  be  installed  on  the  server  hosting  the  RINA Reporting DB or it can be installed on a separate server. We will refer to the JasperReports website for the binaries and installations instructions.

The JasperReports Studio is a desktop application.

<!-- image -->

## 3 Installation

## 3.1 Setup a RINA reporting DB

It's out of scope for this document to give exact instructions on how to setup a RINA Reporting DB. The PostgreSQL documentation does cover replication of a PostgreSQL DB. The most optimal solution would be dependent local knowledge and resources.

PostgreSQL: Documentation: 19.6. Replication

## 3.2 Install JasperReport Server

Current documentation and binaries can found on the community website

JasperReports® Server | Jaspersoft Community

Binaries  currently  exists  for  Windows,  Linux  and  MacOS.  There  are  no  functional differences, choose the platform best suited for the local environment.

## 3.3 Configure Data Source

- Login to the JasperReport Server admin url
- Add  a  data  source  to  the  JasperReports  Server  Repository.  This  is  the  JBDC connection to the RINA Reporting DB. Create a new data adapter and name it RINA:
- o Select the postgresql driver
- o The JDBC URL should be in the format: jdbc:postgresql://[host\_name]:[db\_port]/[db\_name]. The values in square parenthesis should be supplied by your sysadmin.
- o The user and password should be supplied by your sysadmin.
- In the report dataset and query dialog select the RINA adapter and 'sql' language.

## 3.4 Upload provided report templates

- Report templates have been taken out of WAR and expose in an external directory (e.g. $EESSI\_RELEASE\reports), the files can be upladed via the admin url or with JasperReports Studio

<!-- image -->

## 4 Reports Customization

## 4.1 Customization Procedure

Please follow below procedure to customize the Jasper reports:

1. Please download the Jasper Studio Standalone edition from: https://community.jaspersoft.com/project/jaspersoft-studio and install it.
2. Create a project by adding the RINA Jasper templates from $EESSI\_RELEASE\reports.  Report  templates  have  been  taken  out  of  WAR  and expose  in  an  external  directory  (e.g.  $EESSI\_RELEASE\reports)  to  give  RINA users,  clerks  the  possibility  to  customize,  modify  and/or  translate  the  Jasper templates  WITH  THE  EXCEPTION  of  the  database  and  calculated  fields  (e.g. $F{caseid},  $F{process},  $F{role},  etc..)  presented  in  chapter  2  in  current document. Images from templates are to be placed in same directory as Jasper templates in order to work;
3. The user are encouraged to translate displayed labels like title ('Cases Report') or column names: 'Case Id', 'Process Definition' and images, layout BUT DO NOT MODIFY the fields names.

Also, user can try any layout or cosmetic changes as long he DOES NOT touch the aforementioned  value  fields  and  as  long  the  modified  template  is  compiled correctly in Jasper studio.

4. After each changing of the reports, the user should compile the report in Jasper Studio to check its sanity -no ERRORS!
5. The new templates must can then be uploaded to JasperReport Server and used to generate reports

<!-- image -->

## 4.2 Figures

Style restrictions of reports:

Please  do  not  change/localize  any  of  the  variable  marked  bellow.  They  have  a  1:1 correspondence in the code.

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

Any other style customization do not affect look &amp; feel of the report:

<!-- image -->