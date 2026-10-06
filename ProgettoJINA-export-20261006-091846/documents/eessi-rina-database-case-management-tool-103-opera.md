---
unique-name: eessi-rina-database-case-management-tool-103-opera
display-name: EESSI   RINA   Database Case Management Tool 1.0.3   Operations Manual
category: GENERAL
tags: ec
---

<!-- image -->

<!-- image -->

EESSI -RINA

## Database Case Management Tool DCM 1.0.3

Operations Manuals &amp; Guides

Employment, Social Affairs andInclusion

## Table of Contents

Table of Contents

1

........................................................................................ 2

Scope .................................................................................................... 5

2

3

4

5

6

7

Prerequisites  ........................................................................................... 5

Purpose of DCM Tool  ................................................................................ 6

DCM Configuration  ................................................................................... 7

4.1

Environment.properties ...................................................................... 7

4.2

Db.properties .................................................................................... 7

Executing DCM  ........................................................................................ 8

5.1

Exporting RINA cases ......................................................................... 8

5.2

5.3

Importing RINA cases  ......................................................................... 9

Deleting RINA cases ..........................................................................  10

Optional configuration  .............................................................................  11

6.1

table\_actions.xml  ..............................................................................  11

6.2

sid\_mappings.xml .............................................................................  12

Annexes ................................................................................................  13

7.1

Annex A - table\_actions.xml  ...............................................................  13

7.2

Annex B

-

sid\_mappings.xml  ..............................................................  20

<!-- image -->

<!-- image -->

## Document Control Information

| Document Control                        | Value                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Project Title                           | Electronic Exchange of Social Security Information (EESSI)                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Document Title                          | EESSI - RINA - Database Case Management Tool                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Document Category                       | Operations Manuals & Guides                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Revision                                | -                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Tool Version                            | DCM 1.0.3                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Last Publication Date Project Milestone | 8/3/2022 EESSI-2020 Fix8 or higher                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| Document Status                         | Final                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| Sensitivity (TLP) Distribution terms    | The distribution of this document is done strictly in line with the Traffic Light Protocol (TLP) established by the European Commission's note AC 790/15 REV for the EESSI project documentation. In line with the note AC 790/15 REV, this document is labelled as TLP = 'Green'. Therefore, it can be circulated widely within the EESSI community. However, the document or the information herein may not be published or posted on the Internet, nor released outside of the EESSI community. |
| Connected/Embedded Files                | None                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| Authors                                 | European Commission, DG EMPL A4, EESSI RINA                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Revised by                              | European Commission, DG EMPL A4, ECSD                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| Approved by                             | European Commission, DG EMPL A4, EESSI PMO                                                                                                                                                                                                                                                                                                                                                                                                                                                         |

## Document history

| Tool version                              | Publication Date   | Changes/Corrections/Updates Description   |
|-------------------------------------------|--------------------|-------------------------------------------|
| Database Case Management Tool - DCM 1.0.3 | 08/03/2022         | Initial Document                          |

<!-- image -->

## 1 Scope

This document describes the scope of the D atabase C ase M anagement tool (DCM), a javabased  application  that  acts  as  a  set  of  commands  integrated  into  the  Housekeeper framework.  DCM  allows  admins  to  perform  3  operations  on  their  RINA  database installations:

- Export: exports the contents of one or multiple RINA cases from PostgreSQL to disk; the exported data are stored as XML files
- Import:  imports  the  contents  of  one  or  multiple  RINA  cases  from  disk  into PostgreSQL; the data to be imported must be stored as XML files
- Delete: deletes the contents of one or multiple RINA cases from PostgreSQL

DCM only supports running the above commands on archived cases ! Cases with status different than ' archived ' are considered on-going cases and are outside the scope of the tool.

## 2 Prerequisites

- RINA version: RINA 6.2.18 or higher

DCM tool requires a connection to the RINA database. The version of deployed RINA must be RINA 6.2.18 or higher version.

- Java version:  Java 11

DCM was built and tested with Java 11.

<!-- image -->

## 3 Purpose of DCM Tool

DCM makes it easier for RINA admins to perform certain activities on the contents of RINA cases. By contents of a case, we are referring to all the data associated to a particular case and specific to that case only. By design, w e don't consider users, organisations, or other entities that may be involved in multiple cases, to belong to the case contents. Instead, these are considered external entities. DCM will not export these entities and expects them to exist in the database at the import time. DCM can be used as a case management tool. Admins can use it for purging old cases from the database, create back-ups, archive, or import cases back into RINA.

NOTE: The import operation must be done on same RINA DB which was used for export operation.  As  case  contents  are  dependent  on  external  entities,  such  as  users  and organisations, they are bound to a specific RINA instance. Operations like moving cases from one RINA instance to another are outside the scope of this tool.

<!-- image -->

## 4 DCM Configuration

## 4.1 Environment.properties

The  main  configuration  file  for  DCM  is  'environment.properties' .  This  file  contains  the Housekeeper  commands  configuration  parameters.  The  parameters  that  influence  the behaviour of DCM are described below:

- import.export.config.db=&lt;folderPath&gt;/db.properties

This  parameter  defines  the  path  to  the  file  that  contains  the  database  connection parameters: db.properties.

- import.export.rina.case.files=&lt;folderPath&gt;

This parameter defines the path to the folder that is going to be used by DCM as a basis for importing and exporting. DCM export will save the contents of the exported cases in this folder. DCM import will import from the files found in this folder.

## 4.2 Db.properties

This  configuration  file  contains  the  details  for  connecting  to  the  RINA  database.  The parameters defined in this file are described below:

- dataSourceClassName=org.postgresql.ds.PGSimpleDataSource

This parameter defines the type of datasource used by DCM tool.

The parameters below define the PostgreSQL configuration details: host, port, database, user and password:

- dataSource.serverName=localhost
- dataSource.portNumber=5433
- dataSource.databaseName=eessi\_rina
- dataSource.user=rina
- dataSource.password=rina

Note : replace the values for the properties above according to your installation of the RINA database.

<!-- image -->

## 5 Executing DCM

To run DCM, first start the housekeeper application by running the command. Please note that  we  pass  as  parameter  the  configuration  file  'environment.properties'  that  we described in 4.1.

java -Dhousekeeper.environment.settings=config/environment.properties -jar rinahousekeeper.jar

## 5.1 Exporting RINA cases

Exporting is a read-only operation on the PostgreSQL database. DCM Export fetches the data associated to one or multiple cases and saves them on the disk, as XML files.

After starting Housekeeper, one can run the following command to get the parameters available for export:

housekeeper&gt; export --help

which outputs the following:

```
Command for exporting case resources -b, --bulk=<filename>     path to the file containing the list of local case id, one per line -c, --case=<caseId>       local case id -t, --threads=<threads>   number of threads
```

The tool ca be run to export a single case, or multiple cases, in bulk.

For exporting one case, one can run the following command (by replacing &lt;caseId&gt; with the local case id of the case to be exported):

housekeeper&gt; export -c &lt;caseId&gt;

For exporting multiple cases, one can run the following command (by replacing &lt;filename&gt; with the path to the file containing the local case ids, one per line, and &lt;threads&gt; with the desired number of threads):

housekeeper&gt; export -b &lt;filename&gt; -t &lt;threads&gt;

The output of DCM Export is the set of resources associated to a case, saved as XMLs on the  disk,  in  a  folder  named  case\_&lt;caseId&gt;.  All  resources  belonging  to  a  case  will  be logically  grouped  and  saved  in  the  case  folder.  Resources  of  the  same  type  (e.g., documents,  actions)  are  grouped  by  their  type  and  saved  in  an  XML  file  named &lt;tableName&gt;.xml. Below is an example of files exported for a specific case:

<!-- image -->

<!-- image -->

## 5.2 Importing RINA cases

DCM Import is an operation that takes data from the disk (XML files that adhere to the DCM Export format) and inserts it into PostgreSQL. This operation alters the database.

After starting Housekeeper, one can run the following command to get the parameters available for import:

```
housekeeper> import --help which outputs the following: -b, --bulk=<filename>     path to the file containing the list of local case
```

```
Command for importing case resources id, one per line -c, --case=<caseId>       local case id -t, --threads=<threads>   number of threads
```

The Import parameters are similar to the Export parameters. The tool ca be run to import a single case, or multiple cases, in bulk.

For importing one case, one can run the following command (by replacing &lt;caseId&gt; with the local case id of the case to be imported):

housekeeper&gt; import -c &lt;caseId&gt;

For importing multiple cases, one can run the following command (by replacing &lt;filename&gt; with the path to the file containing the local case ids, one per line, and &lt;threads&gt; with the desired number of threads):

<!-- image -->

housekeeper&gt; import -b &lt;filename&gt; -t &lt;threads&gt;

When importing, DCM first tries to locate the files on the disk containing the case data. DCM will try to import all the resources saved in the folder named 'case\_&lt;caseId&gt;' (where &lt;caseId&gt; is the local case id of the case to be imported). If the folder does not exist, DCM will:

- stop, in case of single import
- continue trying to import the next case, in case of bulk import

The import operation is transactional. This means that the whole case is considered an atomic entity. It is either fully imported, or not imported at all. In other words, any error that occurs while importing case resources will lead to the rollback of the import for the given case, and no resource belonging to this case will be saved into PostgreSQL.

DCM will throw an error when trying to import a case if there already exists a case in PostgreSQL with the same caseId.

DCM Import and Export use the same name convention and folder structure. Altering the folder name or structure, or the file names or contents may render them to be unusable, and the import may fail.

## 5.3 Deleting RINA cases

DCM  Delete  is  an  operation  that  deletes  the  contents  of  one  or  multiple  cases  from PostgreSQL. This operation cannot be undone. The delete operation does not create any back-up of the data. It is always recommended to run DCM Export (and validate the output of the export) before running DCM Delete.

After starting Housekeeper, one can run the following command to get the parameters available for delete:

housekeeper&gt; delete --help

which outputs the following:

```
Command for deleting case resources -b, --bulk=<filename>     path to the file containing the list of local case
```

```
id, one per line -c, --case=<caseId>       local case id -t, --threads=<threads>   number of threads
```

For deleting one case, one can run the following command (by replacing &lt;caseId&gt; with the local case id of the case to be imported):

housekeeper&gt; delete -c &lt;caseId&gt;

For deleting multiple cases, one can run the following command (by replacing &lt;filename&gt; with the path to the file containing the local case ids, one per line, and &lt;threads&gt; with the desired number of threads):

The delete operation is transactional. This means that the whole case is considered an atomic entity. It is either fully deleted, or not deleted at all. In other words, any error that occurs while deleting case resources will lead to the rollback of the delete for the given case.

DCM will throw an error when trying to delete a case if there is no case in PostgreSQL with that caseId.

<!-- image -->

## 6 Optional configuration

The following configurations are only necessary if the administrator specifically wants to change the internal rules of the DCM. If this is not the case, then you can skip this section.

There are 2 files worth mentioning in this section:

- table\_actions.xml and
- sid\_mappings.xml.

The definitions in these 2 files are used internally by DCM, and they influence the behaviour of operations like Import or Delete. These 2 files come preconfigured, and they do not need any change for the default behaviour. They can be updated by an admin if for example the database schema changes, removing the need to rebuild DCM.

These  files  can  be  provided  to  DCM  as  external  configuration  files,  by  specifying  the following paths in environment.properties :

- import.export.xml.rules.file=&lt;folderPath&gt;/ table\_actions.xml
- import.export.sid.mapping=&lt;folderPath&gt;/sid\_mappings.xml

## 6.1 table\_actions.xml

By default, the tool operates on a set or RINA action rules that define the order in which the import and delete actions are performed to satisfy all the FK relations in the database. This file also defines the chain of tables needed for filtering by caseId.

The structure of this file is shown below:

```
<tableActions> <tableAction> <table>table_name</table> <filter>sql_filter</filter> <action>action</action> </tableAction> <tableAction> … </tableAction> … </tableActions>
```

The file contains a list of actions to be performed for each table. These actions are ordered, meaning they will be processed in the order they are defined. In the previous example:

- table is the name of the table in PostgreSQL (e.g., document, action)
- filter defines the sql filter that is applied on the table (i.e., the sql WHERE clause)
- action is the sql operation to be performed (e.g., delete, update)

The full contents of this file are listed in ' Annex A - table\_actions.xml ' .

<!-- image -->

## 6.2 sid\_mappings.xml

DCM Import uses an internal SID mapping xml file that defines the links between tables. This  is  needed,  as  SIDs  exported  with  DCM  Export  must  be  updated  after  inserting resources into PostgreSQL, to preserve the correct data links.

The structure of this file is shown below:

```
<metadata> <table> <name>table_name</name> <field> <name>column_name</name> <type>relation</type> <referredTable>table_name</referredTable> </field> <field> … </field> … </table> … </metadata>
```

The file contains a list of definitions that link tables. In the previous example:

- &lt;name&gt;table\_name&lt;/name&gt; specifies the name of the table in PostgreSQL (e.g., document, action)
- &lt;name&gt;column\_name&lt;/name&gt; specifies the column (e.g., fk\_case\_sid, fk\_document\_sid)
- &lt;type&gt;relation&lt;/type&gt; specifies the type of relation (e.g., PK, FK)
- &lt;referredTable&gt;table\_name&lt;/referredTable&gt; specifies the table that is referred (if relation is of type FK)

The full contents of this file are listed in ' Annex B -sid\_mappings.xml '.

<!-- image -->

## 7 Annexes

## 7.1 Annex A - table\_actions.xml

```
<?xml version="1.0" encoding="UTF-8" standalone="yes"?> <tableActions> <tableAction> <table>action_tag</table> <filter>fk_action_sid  in  (select  sid  from  "action"  where  fk_case_sid  in (select sid from rina_case where id= ?))</filter> <action>delete</action> </tableAction> <tableAction> <table>action</table> <filter>fk_case_sid in (select sid from rina_case where id= ?)</filter> <action>delete</action> </tableAction> <tableAction> <table>assignment_group</table> <filter>fk_assignment_sid in (select sid from "assignment" where fk_case_sid in (select sid from rina_case where id= ?))</filter> <action>delete</action> </tableAction> <tableAction> <table>assignment_user</table> <filter>fk_assignment_sid in (select sid from "assignment" where fk_case_sid in (select sid from rina_case where id= ?))</filter> <action>delete</action> </tableAction> <tableAction> <table>assignment</table> <filter>fk_case_sid in (select sid from rina_case where id= ?)</filter> <action>delete</action> </tableAction> <tableAction> <table>case_participant</table> <filter>fk_case_sid in (select sid from rina_case where id= ?)</filter> <action>delete</action> </tableAction> <tableAction> <table>case_prefill</table>
```

<!-- image -->

<!-- image -->

```
<filter>fk_case_sid in (select sid from rina_case where id= ?)</filter> <action>delete</action> </tableAction> <tableAction> <table>case_comment</table> <filter>fk_case_sid in (select sid from rina_case where id= ?)</filter> <action>delete</action> </tableAction> <tableAction> <table>case_property</table> <filter>fk_case_sid in (select sid from rina_case where id= ?)</filter> <action>delete</action> </tableAction> <tableAction> <table>case_attachment</table> <filter>fk_case_sid in (select sid from rina_case where id= ?)</filter> <action>delete</action> </tableAction> <tableAction> <table>case_subject_org</table> <filter>fk_case_sid in (select sid from rina_case where id= ?)</filter> <action>delete</action> </tableAction> <tableAction> <table>subdocument_bversion</table> <filter>fk_subdoc_content_sid=null where fk_subdoc_sid in (select sid from "subdocument" where fk_case_sid in (select sid from rina_case where id= ?)) </filter> <action>update</action> </tableAction> <tableAction> <table>subdocument_content</table> <filter>fk_subdoc_sid in (select sid from "subdocument" where fk_case_sid in (select sid from rina_case where id= ?))</filter> <action>delete</action> </tableAction> <tableAction> <table>subdocument</table>
```

<!-- image -->

```
<filter>fk_subdoc_bversion_sid=null where fk_case_sid in (select sid from rina_case where id= ?)</filter> <action>update</action> </tableAction> <tableAction> <table>doc_bversion_subdoc_bversion</table> <filter>fk_subdoc_bversion_sid  in  (select  sid  from  subdocument_bversion where fk_subdoc_sid in (select sid from "subdocument" where fk_case_sid in (select sid from rina_case where id= ?))) </filter> <action>delete</action> </tableAction> <tableAction> <table>subdoc_bversion_attachment</table> <filter>fk_subdoc_bversion_sid  in  (SELECT  sid  from  subdocument_bversion where fk_subdoc_sid in (select sid from "subdocument" where fk_case_sid in (select sid from rina_case where id= ?))) </filter> <action>delete</action> </tableAction> <tableAction> <table>subdocument_bversion</table> <filter>fk_subdoc_sid in (select sid from "subdocument" where fk_case_sid in (select sid from rina_case where id= ?));</filter> <action>delete</action> </tableAction> <tableAction> <table>subdocument_attachment</table> <filter>fk_subdoc_sid in (select sid from "subdocument" where fk_case_sid in (select sid from rina_case where id= ?))</filter> <action>delete</action> </tableAction> <tableAction> <table>subdocument_prefill</table> <filter>fk_subdoc_sid in (select sid from "subdocument" where fk_case_sid in (select sid from rina_case where id= ?))</filter> <action>delete</action> </tableAction> <tableAction> <table>subdocument_history</table>
```

<!-- image -->

```
<filter>fk_subdoc_sid in (select sid from "subdocument" where fk_case_sid in (select sid from rina_case where id= ?))</filter> <action>delete</action> </tableAction> <tableAction> <table>subdocument</table> <filter>fk_case_sid in (select sid from rina_case where id= ?)</filter> <action>delete</action> </tableAction> <tableAction> <table>document_bversion</table> <filter>fk_doc_content_sid=null where fk_doc_sid in (select sid from "document" where fk_case_sid in (select sid from rina_case where id= ?)) </filter> <action>update</action> </tableAction> <tableAction> <table>document_content</table> <filter>fk_doc_sid  in  (select  sid  from  "document"  where  fk_case_sid  in (select sid from rina_case where id= ?))</filter> <action>delete</action> </tableAction> <tableAction> <table>document</table> <filter>fk_doc_bversion_sid=null  where  fk_case_sid  in  (select  sid  from rina_case where id= ?)</filter> <action>update</action> </tableAction> <tableAction> <table>conv_participant</table> <filter>fk_conv_sid in (select sid from document_conversation where fk_doc_sid in (select sid from "document" where fk_case_sid in (select sid from rina_case where id= ?))); </filter> <action>delete</action> </tableAction> <tableAction> <table>signature</table> <filter>fk_message_sid in (select sid from user_message where fk_doc_conv_sid in (select sid from document_conversation where
```

Status: Final/ TLP: GREEN

<!-- image -->

```
fk_doc_sid in (select sid from "document" where fk_case_sid in (select sid from rina_case where id= ?)))) </filter> <action>delete</action> </tableAction> <tableAction> <table>user_message_response</table> <filter>fk_message_sid in (select sid from user_message where fk_doc_conv_sid in (select sid from document_conversation where fk_doc_sid in (select sid from "document" where fk_case_sid in (select sid from rina_case where id= ?)))) </filter> <action>delete</action> </tableAction> <tableAction> <table>user_message</table> <filter>fk_doc_conv_sid  in  (select  sid  from  document_conversation  where fk_doc_sid in (select sid from "document" where fk_case_sid in (select sid from rina_case where id= ?))) </filter> <action>delete</action> </tableAction> <tableAction> <table>document_conversation</table> <filter>fk_doc_sid  in  (select  sid  from  "document"  where  fk_case_sid  in (select sid from rina_case where id= ?))</filter> <action>delete</action> </tableAction> <tableAction> <table>doc_bversion_attachment</table> <filter>fk_doc_bversion_sid  in  (SELECT  sid  from  document_bversion  where fk_doc_sid in (select sid from "document" where fk_case_sid in (select sid from rina_case where id= ?))) </filter> <action>delete</action> </tableAction> <tableAction> <table>document_history</table> <filter>fk_doc_sid  in  (select  sid  from  "document"  where  fk_case_sid  in (select sid from rina_case where id= ?))</filter> <action>delete</action>
```

Status: Final/ TLP: GREEN

<!-- image -->

```
</tableAction> <tableAction> <table>document_bversion</table> <filter>fk_doc_sid  in  (select  sid  from  "document"  where  fk_case_sid  in (select sid from rina_case where id= ?))</filter> <action>delete</action> </tableAction> <tableAction> <table>document_attachment</table> <filter>fk_doc_sid  in  (select  sid  from  "document"  where  fk_case_sid  in (select sid from rina_case where id= ?))</filter> <action>delete</action> </tableAction> <tableAction> <table>document_comment</table> <filter>fk_doc_sid  in  (select  sid  from  "document"  where  fk_case_sid  in (select sid from rina_case where id= ?))</filter> <action>delete</action> </tableAction> <tableAction> <table>notification_user</table> <filter>fk_notification_sid in (select sid from notification where fk_case_sid in (select sid from rina_case where id= ?))</filter> <action>delete</action> </tableAction> <tableAction> <table>notification</table> <filter>fk_case_sid in (select sid from rina_case where id= ?)</filter> <action>delete</action> </tableAction> <tableAction> <table>notification_alarm</table> <filter>fk_case_sid in (select sid from rina_case where id= ?)</filter> <action>delete</action> </tableAction> <tableAction> <table>document</table> <filter>fk_case_sid in (select sid from rina_case where id= ?)</filter> <action>delete</action> </tableAction>
```

```
<tableAction> <table>rina_case</table> <filter>id= ?</filter> <action>delete</action> </tableAction> </tableActions>
```

<!-- image -->

## 7.2 Annex B -sid\_mappings.xml

```
<?xml version="1.0" encoding="UTF-8" standalone="yes"?> <metadata> <table> <name>action</name> <field> <name>sid</name> <type>PK</type> </field> <field> <name>fk_document_sid</name> <type>FK</type> <referredTable>document</referredTable> </field> <field> <name>fk_parent_document_sid</name> <type>FK</type> <referredTable>document</referredTable> </field> <field> <name>fk_doc_type_version_sid</name> <type>FK</type> <referredTable>document_type_version</referredTable> </field> <field> <name>fk_case_sid</name> <type>FK</type> <referredTable>rina_case</referredTable> </field> </table> <table> <name>action_tag</name> <field> <name>sid</name> <type>PK</type> </field> <field> <name>fk_action_sid</name> <type>FK</type>
```

<!-- image -->

```
<referredTable>action</referredTable> </field> </table> <table> <name>assignment</name> <field> <name>sid</name> <type>PK</type> </field> <field> <name>fk_role_sid</name> <type>FK</type> <referredTable>role</referredTable> </field> <field> <name>fk_case_sid</name> <type>FK</type> <referredTable>rina_case</referredTable> </field> </table> <table> <name>assignment_group</name> <field> <name>fk_group_sid</name> <type>FK</type> <referredTable>iam_group</referredTable> </field> <field> <name>fk_assignment_sid</name> <type>FK</type> <referredTable>assignment</referredTable> </field> </table> <table> <name>assignment_user</name> <field> <name>fk_user_sid</name> <type>FK</type> <referredTable>iam_user</referredTable>
```

<!-- image -->

Status: Final/ TLP: GREEN

```
</field> <field> <name>fk_assignment_sid</name> <type>FK</type> <referredTable>assignment</referredTable> </field> </table> <table> <name>case_attachment</name> <field> <name>sid</name> <type>PK</type> </field> <field> <name>fk_case_sid</name> <type>FK</type> <referredTable>rina_case</referredTable> </field> </table> <table> <name>case_comment</name> <field> <name>sid</name> <type>PK</type> </field> <field> <name>fk_case_sid</name> <type>FK</type> <referredTable>rina_case</referredTable> </field> </table> <table> <name>case_participant</name> <field> <name>sid</name> <type>PK</type> </field> <field> <name>fk_case_sid</name>
```

<!-- image -->

```
<type>FK</type> <referredTable>rina_case</referredTable> </field> <field> <name>fk_org_sid</name> <type>FK</type> <referredTable>organisation</referredTable> </field> </table> <table> <name>case_prefill</name> <field> <name>sid</name> <type>PK</type> </field> <field> <name>fk_case_sid</name> <type>FK</type> <referredTable>rina_case</referredTable> </field> </table> <table> <name>case_property</name> <field> <name>sid</name> <type>PK</type> </field> <field> <name>fk_case_sid</name> <type>FK</type> <referredTable>rina_case</referredTable> </field> </table> <table> <name>case_subject_org</name> <field> <name>fk_org_sid</name> <type>FK</type> <referredTable>organisation</referredTable>
```

<!-- image -->

Status: Final/ TLP: GREEN

<!-- image -->

```
</field> <field> <name>fk_case_sid</name> <type>FK</type> <referredTable>rina_case</referredTable> </field> </table> <table> <name>conv_participant</name> <field> <name>sid</name> <type>PK</type> </field> <field> <name>fk_conv_sid</name> <type>FK</type> <referredTable>document_conversation</referredTable> </field> <field> <name>fk_org_sid</name> <type>FK</type> <referredTable>organisation</referredTable> </field> </table> <table> <name>doc_bversion_attachment</name> <field> <name>fk_doc_attachment_sid</name> <type>FK</type> <referredTable>document_attachment</referredTable> </field> <field> <name>fk_doc_bversion_sid</name> <type>FK</type> <referredTable>document_bversion</referredTable> </field> </table> <table> <name>doc_bversion_subdoc_bversion</name>
```

Status: Final/ TLP: GREEN

<!-- image -->

```
<field> <name>fk_subdoc_bversion_sid</name> <type>FK</type> <referredTable>subdocument_bversion</referredTable> </field> <field> <name>fk_doc_bversion_sid</name> <type>FK</type> <referredTable>document_bversion</referredTable> </field> </table> <table> <name>document</name> <field> <name>sid</name> <type>PK</type> </field> <field> <name>fk_case_sid</name> <type>FK</type> <referredTable>rina_case</referredTable> </field> <field> <name>fk_doc_type_version_sid</name> <type>FK</type> <referredTable>document_type_version</referredTable> </field> <field> <name>fk_doc_bversion_sid</name> <type>FK</type> <referredTable>document_bversion</referredTable> </field> <field> <name>fk_parent_sid</name> <type>FK</type> <referredTable>document</referredTable> </field> </table> <table>
```

<!-- image -->

```
<name>document_attachment</name> <field> <name>sid</name> <type>PK</type> </field> <field> <name>fk_doc_sid</name> <type>FK</type> <referredTable>document</referredTable> </field> </table> <table> <name>document_bversion</name> <field> <name>sid</name> <type>PK</type> </field> <field> <name>fk_doc_content_sid</name> <type>FK</type> <referredTable>document_content</referredTable> </field> <field> <name>fk_doc_sid</name> <type>FK</type> <referredTable>document</referredTable> </field> </table> <table> <name>document_comment</name> <field> <name>sid</name> <type>PK</type> </field> <field> <name>fk_doc_sid</name> <type>FK</type> <referredTable>document</referredTable> </field>
```

Status: Final/ TLP: GREEN

<!-- image -->

```
</table> <table> <name>document_content</name> <field> <name>sid</name> <type>PK</type> </field> <field> <name>fk_doc_sid</name> <type>FK</type> <referredTable>document</referredTable> </field> </table> <table> <name>document_conversation</name> <field> <name>sid</name> <type>PK</type> </field> <field> <name>fk_doc_sid</name> <type>FK</type> <referredTable>document</referredTable> </field> <field> <name>fk_doc_bversion_sid</name> <type>FK</type> <referredTable>document_bversion</referredTable> </field> </table> <table> <name>document_history</name> <field> <name>sid</name> <type>PK</type> </field> <field> <name>fk_doc_type_version_sid</name> <type>FK</type>
```

Status: Final/ TLP: GREEN

<!-- image -->

```
<referredTable>document_type_version</referredTable> </field> <field> <name>fk_doc_sid</name> <type>FK</type> <referredTable>document</referredTable> </field> <field> <name>fk_case_sid</name> <type>FK</type> <referredTable>rina_case</referredTable> </field> <field> <name>fk_doc_bversion_sid</name> <type>FK</type> <referredTable>document_bversion</referredTable> </field> </table> <table> <name>notification</name> <field> <name>sid</name> <type>PK</type> </field> <field> <name>fk_document_type_sid</name> <type>FK</type> <referredTable>document_type</referredTable> </field> <field> <name>fk_receiver_org_sid</name> <type>FK</type> <referredTable>organisation</referredTable> </field> <field> <name>fk_sender_org_sid</name> <type>FK</type> <referredTable>organisation</referredTable> </field>
```

```
<field> <name>fk_document_sid</name> <type>FK</type> <referredTable>document</referredTable> </field> <field> <name>fk_case_sid</name> <type>FK</type> <referredTable>rina_case</referredTable> </field> <field> <name>fk_creator_sid</name> <type>FK</type> <referredTable>iam_user</referredTable> </field> </table> <table> <name>notification_alarm</name> <field> <name>sid</name> <type>PK</type> </field> <field> <name>fk_case_sid</name> <type>FK</type> <referredTable>rina_case</referredTable> </field> </table> <table> <name>notification_user</name> <field> <name>fk_user_sid</name> <type>FK</type> <referredTable>iam_user</referredTable> </field> <field> <name>fk_notification_sid</name> <type>FK</type> <referredTable>notification</referredTable>
```

<!-- image -->

Status: Final/ TLP: GREEN

<!-- image -->

```
</field> </table> <table> <name>rina_case</name> <field> <name>sid</name> <type>PK</type> </field> <field> <name>fk_tenant_sid</name> <type>FK</type> <referredTable>tenant</referredTable> </field> <field> <name>fk_proc_def_version_sid</name> <type>FK</type> <referredTable>process_def_version</referredTable> </field> <field> <name>fk_starter_doc_type_sid</name> <type>FK</type> <referredTable>document_type</referredTable> </field> </table> <table> <name>signature</name> <field> <name>sid</name> <type>PK</type> </field> <field> <name>fk_message_sid</name> <type>FK</type> <referredTable>user_message</referredTable> </field> </table> <table> <name>subdoc_bversion_attachment</name> <field>
```

<!-- image -->

```
<name>fk_subdoc_attachment_sid</name> <type>FK</type> <referredTable>subdocument_attachment</referredTable> </field> <field> <name>fk_subdoc_bversion_sid</name> <type>FK</type> <referredTable>subdocument_bversion</referredTable> </field> </table> <table> <name>subdocument</name> <field> <name>sid</name> <type>PK</type> </field> <field> <name>fk_case_sid</name> <type>FK</type> <referredTable>rina_case</referredTable> </field> <field> <name>fk_subdoc_bversion_sid</name> <type>FK</type> <referredTable>subdocument_bversion</referredTable> </field> <field> <name>fk_document_sid</name> <type>FK</type> <referredTable>document</referredTable> </field> </table> <table> <name>subdocument_attachment</name> <field> <name>sid</name> <type>PK</type> </field> <field>
```

<!-- image -->

```
<name>fk_subdoc_sid</name> <type>FK</type> <referredTable>subdocument</referredTable> </field> </table> <table> <name>subdocument_bversion</name> <field> <name>sid</name> <type>PK</type> </field> <field> <name>fk_subdoc_content_sid</name> <type>FK</type> <referredTable>subdocument_content</referredTable> </field> <field> <name>fk_subdoc_sid</name> <type>FK</type> <referredTable>subdocument</referredTable> </field> </table> <table> <name>subdocument_content</name> <field> <name>sid</name> <type>PK</type> </field> <field> <name>fk_subdoc_sid</name> <type>FK</type> <referredTable>subdocument</referredTable> </field> </table> <table> <name>subdocument_history</name> <field> <name>sid</name> <type>PK</type>
```

<!-- image -->

```
</field> <field> <name>fk_subdoc_bversion_sid</name> <type>FK</type> <referredTable>subdocument_bversion</referredTable> </field> <field> <name>fk_subdoc_sid</name> <type>FK</type> <referredTable>subdocument</referredTable> </field> <field> <name>fk_doc_sid</name> <type>FK</type> <referredTable>document</referredTable> </field> <field> <name>fk_case_sid</name> <type>FK</type> <referredTable>rina_case</referredTable> </field> </table> <table> <name>subdocument_prefill</name> <field> <name>sid</name> <type>PK</type> </field> <field> <name>fk_subdoc_sid</name> <type>FK</type> <referredTable>subdocument</referredTable> </field> </table> <table> <name>user_message</name> <field> <name>sid</name> <type>PK</type>
```

<!-- image -->

```
</field> <field> <name>fk_doc_conv_sid</name> <type>FK</type> <referredTable>document_conversation</referredTable> </field> <field> <name>fk_receiver_sid</name> <type>FK</type> <referredTable>organisation</referredTable> </field> <field> <name>fk_sender_sid</name> <type>FK</type> <referredTable>organisation</referredTable> </field> </table> <table> <name>user_message_response</name> <field> <name>sid</name> <type>PK</type> </field> <field> <name>fk_message_sid</name> <type>FK</type> <referredTable>user_message</referredTable> </field> </table> </metadata>
```