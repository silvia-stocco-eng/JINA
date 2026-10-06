---
unique-name: eessi-rina-case-processing-interface-cpi-reference
display-name: EESSI   RINA   Case Processing Interface (CPI)   Reference   rev03
category: GENERAL
tags: ec
---

## EESSI RINA CPI - Reference Documentation

Version 6.2.22, 28-04-2022

## Table of Contents

Overview. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .

| Version information . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                   | . 1   |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------|-------|
| Tags . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .    | . 1   |
| Paths . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . | . 3   |
| Create a new activity. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                  | . 3   |
| Update a particular activity. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                       | . 3   |
| Deletes an activity associated to a particular user. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                                        | . 4   |
| Get activities for the current user over a particular time range . . . . . . . . . . . . . . . . . . . .                                                    | . 5   |
| Get all admin notifications types . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                           | . 6   |
| Update a all admin notification types . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                               | . 7   |
| Get the Application Profile. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                      | . 7   |
| Update the Application Profile . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                          | . 8   |
| Retrieving the archiving policies . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                           | . 9   |
| Update the archiving policies . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                         | . 9   |
| Retrieving the archiving repositories . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                               | 10    |
| Update the archiving repositories . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                             | 10    |
| Retrieving the archiving repositories policies . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                                      | 11    |
| Update the archiving repository policies . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                                  | 12    |
| Retrieving the cases retention policies . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                               | 13    |
| Update the case retention policies. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                             | 13    |
| Synchronize LDAP users . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                        | 14    |
| Reassign group affected cases. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                          | 15    |
| Retrieving the messages retention policies . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                                    | 15    |
| Update the message retention policies . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                                 | 16    |
| Get the Messaging Settings . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                        | 16    |
| Update the Messaging Settings . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                           | 17    |
| Get the NIE subscriptions. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                      | 18    |
| Update the NIE settings . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                     | 18    |
| Update the NIE subscription . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                         | 19    |
| Delete the NIE subscription. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                        | 20    |
| Retrieves the list of Tenants and their attributes. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                                       | 20    |
| Adds a Tenant by providing its Institution Id . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                                     | 21    |
| Retrieves the Tenant attributes by its Tenant Id. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                                       | 22    |
| Updates the Tenant attributes by its id. Enables/Disables it or/and makes it the default.                                                                   | 23    |
| Deletes a Tenant by providing its Tenant Id . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                                     | 24    |
| Retrieving the archiving repositories policies . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                                      | 24    |
| Update the archiving repository policies . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                                  | 25    |
| Create a case assignment policy. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                            | 26    |

1

| Get the case assignment policies . . . . . . . . . . . . . . . . . . . . . . . . . . . .                    |   27 |
|-------------------------------------------------------------------------------------------------------------|------|
| Creates or updates the assignment policy target . . . . . . . . . . . . . .                                 |   27 |
| Get the case assignment policy. . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                   |   28 |
| Update a case assignment policy . . . . . . . . . . . . . . . . . . . . . . . . . . . .                     |   29 |
| Delete a case assignment policy . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                   |   30 |
| Add a target to an assignment policy . . . . . . . . . . . . . . . . . . . . . . . .                        |   31 |
| Remove a target from an assignment policy. . . . . . . . . . . . . . . . . .                                |   31 |
| Retrieve the audit logs details. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                |   32 |
| Retrieve the audit log time slots . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                 |   35 |
| Submit a business exception. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                  |   37 |
| Retrieve the business exceptions details . . . . . . . . . . . . . . . . . . . . .                          |   37 |
| Retrieve the business exceptions time slots . . . . . . . . . . . . . . . . . .                             |   38 |
| Retrieve the SED content of the business exception . . . . . . . . . . .                                    |   39 |
| Retrieve the rejection SED content of the business exception . .                                            |   40 |
| Create new case . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .       |   41 |
| Search cases by parameters . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                  |   42 |
| Get a case by the business ID . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                 |   43 |
| Get a case by the international ID . . . . . . . . . . . . . . . . . . . . . . . . . . .                    |   43 |
| Get a case ID by the business ID. . . . . . . . . . . . . . . . . . . . . . . . . . . . .                   |   44 |
| Get a case ID by the international ID . . . . . . . . . . . . . . . . . . . . . . . .                       |   45 |
| Import Subdocuments . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .               |   46 |
| Submit Document . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .           |   46 |
| Retrieve Initial Document . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .               |   47 |
| Set alarm . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . |   48 |
| Get alarms of a case. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .         |   49 |
| Clear alarm . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .   |   50 |
| Update Case Assignments . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                 |   51 |
| Executes case assigment related action . . . . . . . . . . . . . . . . . . . . . .                          |   51 |
| Submit attachment on a case . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                   |   52 |
| Retrieve attachment of a case. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                  |   53 |
| Delete attachment of a case. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                |   54 |
| Update the Medical Information flag of a case attachment. . . . .                                           |   55 |
| Submit comment on case. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                 |   55 |
| Delete comment of a case. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .               |   56 |
| Submit attachment on a document . . . . . . . . . . . . . . . . . . . . . . . . . .                         |   57 |
| Retrieve attachment of a document . . . . . . . . . . . . . . . . . . . . . . . . .                         |   58 |
| Delete attachment of a document . . . . . . . . . . . . . . . . . . . . . . . . . . .                       |   59 |
| Update the Medical Information flag of a document attachment                                                |   60 |
| Export Subdocuments. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .              |   60 |
| Retrieve the Business Signing Certificate. . . . . . . . . . . . . . . . . . . . . . . .                    |   61 |
| Submit comment on document . . . . . . . . . . . . . . . . . . . . . . . . . .                              |   62 |

| Delete comment of a document . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                       |   63 |
|--------------------------------------------------------------------------------------------------------------------|------|
| Retrieve Document Details . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                  |   64 |
| Update the status of a user message . . . . . . . . . . . . . . . . . . . . . . . . . . . .                        |   65 |
| Create a Subdocument . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .               |   65 |
| Retrieve a list of subdocuments . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                    |   66 |
| Retrieve Subdocument . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .               |   68 |
| Remove a Subdocument. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                  |   69 |
| Update a Subdocument. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                |   69 |
| Submit attachment on a subdocument. . . . . . . . . . . . . . . . . . . . . . . . . .                              |   70 |
| Retrieve attachment of a subdocument . . . . . . . . . . . . . . . . . . . . . . . . .                             |   72 |
| Delete attachment of a subdocument . . . . . . . . . . . . . . . . . . . . . . . . . . .                           |   72 |
| Update the Medical Information flag of a subdocument attachment.                                                   |   73 |
| Retrieve the Version of a Subdocument . . . . . . . . . . . . . . . . . . . . . . . . .                            |   74 |
| Retrieve Thumbnail. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .            |   75 |
| Retrieve Document Version. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                   |   76 |
| Retrieve Document . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .            |   77 |
| Update case metadata sensitive flag . . . . . . . . . . . . . . . . . . . . . . . . . . . .                        |   78 |
| Get a case . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . |   79 |
| Retrieving the case archiving options. . . . . . . . . . . . . . . . . . . . . . . . . . .                         |   79 |
| Archive/Unarchive a case . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                 |   80 |
| Get case assignments. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .            |   81 |
| Get case hash code. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .          |   82 |
| Execute Check Buckets . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .              |   82 |
| Get all Check Buckets . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .            |   83 |
| Get Check Bucket Executor . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                  |   84 |
| Update check definition . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .              |   84 |
| Get all check definitions. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .             |   85 |
| Saves case counter settings.. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                |   86 |
| Get case counter settings.. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .              |   86 |
| Saves LDAP connection settings. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                      |   87 |
| Get LDAP connection settings. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                    |   88 |
| Get LDAP group parameters keys. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                        |   89 |
| Saves LDAP group parameters mapping.. . . . . . . . . . . . . . . . . . . . . . . .                                |   89 |
| Get LDAP group parameters mapping.. . . . . . . . . . . . . . . . . . . . . . . . . .                              |   90 |
| Get LDAP user parameters keys. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                       |   91 |
| Saves LDAP user parameters mapping. . . . . . . . . . . . . . . . . . . . . . . . . .                              |   91 |
| Get LDAP user parameters mapping. . . . . . . . . . . . . . . . . . . . . . . . . . . .                            |   92 |
| Update Disk Resources . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .              |   93 |
| Search entities. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .     |   93 |
| Search entities by parameters . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                    |   95 |
| Get entity by id . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .     |   96 |

| Uploads a file to the server . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .             | . 97   |
|--------------------------------------------------------------------------------------------------------|--------|
| Get the portal form metadata for a specific SED and version.                                           | . 97   |
| Get the portal forms messages for a specific language. . . . . . .                                     | . 98   |
| Create New group . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .         | . 99   |
| Get Group details . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .      | 100    |
| Update Group . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .     | 101    |
| Delete Group. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .    | 101    |
| Get groups . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . | 102    |
| Registers a new user . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .         | 103    |
| Get the roles . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .  | 104    |
| Create a new user . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .        | 105    |
| Update the current user's password. . . . . . . . . . . . . . . . . . . . . . .                        | 105    |
| Get user details by Id or Name. . . . . . . . . . . . . . . . . . . . . . . . . . . .                  | 106    |
| Update User properties. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .            | 107    |
| Deletes a user by id . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .       | 108    |
| Get all users. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . | 108    |
| Retrieves a list of users based on a group . . . . . . . . . . . . . . . . . .                         | 109    |
| Add a private certificate. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .           | 110    |
| Delete a private certificate . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .             | 111    |
| Add a private certificate. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .           | 112    |
| Delete a private certificate . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .             | 112    |
| Add a public certificate . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .           | 113    |
| Delete a public certificate . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .            | 114    |
| Add a TLS private certificate. . . . . . . . . . . . . . . . . . . . . . . . . . . . . .               | 114    |
| Delete a TLS private certificate . . . . . . . . . . . . . . . . . . . . . . . . . . .                 | 115    |
| Add a TLS public certificate . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .               | 116    |
| Delete a TLS public certificate . . . . . . . . . . . . . . . . . . . . . . . . . . . .                | 116    |
| Update the business key password . . . . . . . . . . . . . . . . . . . . . . . .                       | 117    |
| Get notification details . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .         | 118    |
| Get consolidated summary . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                 | 119    |
| Get notification summary . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .               | 120    |
| Get notification time slots . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .            | 120    |
| Update a notification. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .         | 121    |
| Retrieve the pending messages details. . . . . . . . . . . . . . . . . . . . .                         | 122    |
| Retrieve the pending messages time slots . . . . . . . . . . . . . . . . . .                           | 123    |
| Retrieve the SED content of the pending message. . . . . . . . . . .                                   | 124    |
| Import All Process Assignments. . . . . . . . . . . . . . . . . . . . . . . . . . .                    | 125    |
| Export All Process Assignments. . . . . . . . . . . . . . . . . . . . . . . . . . .                    | 125    |
| Get Process Definition Assignments . . . . . . . . . . . . . . . . . . . . . . .                       | 126    |
| Get List of Application Resources . . . . . . . . . . . . . . . . . . . . . . . . . .                  | 127    |
| Update Application Resources . . . . . . . . . . . . . . . . . . . . . . . . . . .                     | 128    |

| Update Application Resource . . . . . . . . . . . . . . . . . . . . . . . .                       |   128 |
|---------------------------------------------------------------------------------------------------|-------|
| Create a Search Definition. . . . . . . . . . . . . . . . . . . . . . . . . . .                   |   129 |
| Retrieve the List of Search Definitions . . . . . . . . . . . . . . . .                           |   130 |
| Update a Search Definition . . . . . . . . . . . . . . . . . . . . . . . . . .                    |   131 |
| Delete a Search Definition . . . . . . . . . . . . . . . . . . . . . . . . . . .                  |   131 |
| Get Sectors and Process Definitions . . . . . . . . . . . . . . . . . .                           |   132 |
| Submit Common Data Model Request Document . . . . . .                                             |   133 |
| Retrieve Initial Common Data Model Request Document                                               |   133 |
| Submit Institution Repository Request Document . . . . .                                          |   134 |
| Retrieve Initial Insitution Repository Request Document.                                          |   135 |
| Get Technical Log details . . . . . . . . . . . . . . . . . . . . . . . . . . . .                 |   135 |
| Get Technical Logs time slots . . . . . . . . . . . . . . . . . . . . . . . .                     |   137 |
| Get the User Profile . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .            |   138 |
| Update the User Profile . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                 |   138 |
| Update Process Fields . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .               |   139 |
| Get Process Fields . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .            |   140 |
| Get User Role. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .        |   140 |
| Get Vocabulary Values . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                 |   141 |
| Search organisations. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .               |   142 |
| Search organisations by parameters . . . . . . . . . . . . . . . . .                              |   143 |
| Get organisation by id. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .               |   144 |
| POST /user-auth . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .           |   145 |
| Definitions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . |   146 |
| AccessPointDto . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .          |   146 |
| AcknowledgementDto . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                    |   147 |
| ActionGroupDto . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .            |   147 |
| ActionRevisedDto. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .             |   148 |
| ActivityRevisedDto . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .              |   152 |
| ActorRevisedDto. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .            |   153 |
| AddressDto . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .        |   153 |
| AdminNotificationTypeDto . . . . . . . . . . . . . . . . . . . . . . . . . .                      |   154 |
| AlarmDto . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .      |   155 |
| AlarmSettings . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .         |   155 |
| ApiError. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .     |   156 |
| ApplicationProfileDto . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .               |   156 |
| ArchivingOptionsDto . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                 |   160 |
| ArchivingPoliciesDto. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .               |   161 |
| ArchivingPolicyDto . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .              |   161 |
| ArchivingRepositoriesDto . . . . . . . . . . . . . . . . . . . . . . . . . . .                    |   162 |
| ArchivingRepositoryPolicyDto . . . . . . . . . . . . . . . . . . . . . . .                        |   162 |
| ArchivingVolumeDto . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .                  |   164 |

| AssignedBUCDto. . . . . . . . . . . . . . . . . .      |   164 |
|--------------------------------------------------------|-------|
| AssignmentPolicyConditionDto . . . .                   |   165 |
| AssignmentPolicyDto . . . . . . . . . . . . .          |   165 |
| AssignmentPolicyRuleDto . . . . . . . . .              |   166 |
| AssignmentRequest. . . . . . . . . . . . . . .         |   167 |
| AttachementDto . . . . . . . . . . . . . . . . . .     |   167 |
| AttachmentIdentificationDto . . . . . .                |   168 |
| AuditLogsDetailDto . . . . . . . . . . . . . . .       |   169 |
| AuditLogsTimeSlotDto . . . . . . . . . . . .           |   170 |
| AuditedObjects . . . . . . . . . . . . . . . . . . .   |   170 |
| BUCTypeDto . . . . . . . . . . . . . . . . . . . . .   |   171 |
| BUCTypeVersionDto . . . . . . . . . . . . . .          |   172 |
| BpmActorDto . . . . . . . . . . . . . . . . . . . .    |   172 |
| BusinessExceptionDto . . . . . . . . . . . .           |   172 |
| BusinessExceptionsSettingsDto . . . .                  |   173 |
| BusinessKeyAliasPassword . . . . . . . .               |   174 |
| CLIENTBusinessKeyStorePassword.                        |   175 |
| CaseAssignmentActionRevisedDto .                       |   175 |
| CaseAssignmentRevisedDto . . . . . . .                 |   175 |
| CaseClassicView . . . . . . . . . . . . . . . . . .    |   176 |
| CaseCounterSettingsDto. . . . . . . . . . .            |   176 |
| CaseCreationParams . . . . . . . . . . . . . .         |   177 |
| CaseIdentificationDto . . . . . . . . . . . . .        |   177 |
| CaseInfoDto. . . . . . . . . . . . . . . . . . . . . . |   177 |
| CaseParticipantDto . . . . . . . . . . . . . . .       |   178 |
| CaseRetentionPolicyDto . . . . . . . . . . .           |   178 |
| CaseRevisedDto . . . . . . . . . . . . . . . . . .     |   179 |
| CaseTimelineView . . . . . . . . . . . . . . . .       |   181 |
| CaseTraitsDto . . . . . . . . . . . . . . . . . . . .  |   181 |
| CheckBucketDto . . . . . . . . . . . . . . . . . .     |   182 |
| CheckDefinitionDto . . . . . . . . . . . . . . .       |   182 |
| CheckInstanceDto . . . . . . . . . . . . . . . .       |   183 |
| CommentDto. . . . . . . . . . . . . . . . . . . . .    |   184 |
| ConceptDetailedRevisedDto . . . . . . .                |   184 |
| ContactMethodDto. . . . . . . . . . . . . . . .        |   185 |
| ConversationParticipantDto . . . . . . .               |   185 |
| ConversationRevisedDto . . . . . . . . . .             |   185 |
| DiskFileInfoDto. . . . . . . . . . . . . . . . . . .   |   186 |
| DocumentDetailsRevisedDto. . . . . . .                 |   186 |
| DocumentIdentificationDto. . . . . . . .               |   187 |
| DocumentInfo. . . . . . . . . . . . . . . . . . . .    |   188 |

| DocumentRevisedDto . . . . . . . . . . . . . . . . .               |   189 |
|--------------------------------------------------------------------|-------|
| Documents. . . . . . . . . . . . . . . . . . . . . . . . . . .     |   193 |
| EntityBaseDto . . . . . . . . . . . . . . . . . . . . . . . .      |   193 |
| ErrorDto. . . . . . . . . . . . . . . . . . . . . . . . . . . . .  |   193 |
| Exception . . . . . . . . . . . . . . . . . . . . . . . . . . . .  |   194 |
| ExtendedProperties. . . . . . . . . . . . . . . . . . .            |   194 |
| FailureReason. . . . . . . . . . . . . . . . . . . . . . . .       |   194 |
| FieldChooserDto. . . . . . . . . . . . . . . . . . . . . .         |   195 |
| FieldDto . . . . . . . . . . . . . . . . . . . . . . . . . . . . . |   195 |
| GroupDto . . . . . . . . . . . . . . . . . . . . . . . . . . . .   |   195 |
| InstitutionAliasMappingDto . . . . . . . . . . .                   |   197 |
| LdapConnectionSettingsDto . . . . . . . . . . .                    |   198 |
| LdapGroupParametersMappingDto . . . .                              |   199 |
| LdapUserParametersMappingDto. . . . . .                            |   200 |
| LocalizationSettings . . . . . . . . . . . . . . . . . .           |   202 |
| MembershipDto . . . . . . . . . . . . . . . . . . . . . .          |   202 |
| Message . . . . . . . . . . . . . . . . . . . . . . . . . . . . .  |   203 |
| MessageBaseDto. . . . . . . . . . . . . . . . . . . . . .          |   204 |
| MessagesRetentionPoliciesDto . . . . . . . . .                     |   204 |
| MessagingClusterNodeDto. . . . . . . . . . . . .                   |   204 |
| MessagingSettingsDto. . . . . . . . . . . . . . . . .              |   205 |
| NetworkLocationDto. . . . . . . . . . . . . . . . . .              |   207 |
| NieListenerDto . . . . . . . . . . . . . . . . . . . . . . .       |   207 |
| NieNotificationDto. . . . . . . . . . . . . . . . . . . .          |   208 |
| NieSubscriberDto. . . . . . . . . . . . . . . . . . . . .          |   208 |
| NieSubscriptionDto . . . . . . . . . . . . . . . . . . .           |   208 |
| NieSubscriptionsDto . . . . . . . . . . . . . . . . . .            |   209 |
| NotificationDto . . . . . . . . . . . . . . . . . . . . . . .      |   209 |
| NotificationRevisedDto. . . . . . . . . . . . . . . .              |   211 |
| NotificationsConsolidatedSummaryDto.                               |   212 |
| NotificationsSummaryDto. . . . . . . . . . . . .                   |   213 |
| NotificationsTimeSlotDto. . . . . . . . . . . . . .                |   213 |
| OrganisationDto. . . . . . . . . . . . . . . . . . . . . .         |   214 |
| OrganisationRevisedDto. . . . . . . . . . . . . . .                |   214 |
| ParticipantDto. . . . . . . . . . . . . . . . . . . . . . . .      |   215 |
| Participants . . . . . . . . . . . . . . . . . . . . . . . . . .   |   216 |
| PartnerDto. . . . . . . . . . . . . . . . . . . . . . . . . . .    |   216 |
| PendingMessageDto . . . . . . . . . . . . . . . . . .              |   217 |
| PersonDto . . . . . . . . . . . . . . . . . . . . . . . . . . .    |   218 |
| Principal. . . . . . . . . . . . . . . . . . . . . . . . . . . . . |   219 |
| ProcessDefinitionDto . . . . . . . . . . . . . . . . .             |   219 |

220

| ProcessDefinitionVersionDto . . . . . . . . . .                     |     |
|---------------------------------------------------------------------|-----|
| PublicKey. . . . . . . . . . . . . . . . . . . . . . . . . . . .    | 220 |
| RESTCertificate. . . . . . . . . . . . . . . . . . . . . . .        | 220 |
| RESTException . . . . . . . . . . . . . . . . . . . . . . .         | 221 |
| RESTId . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .  | 221 |
| RESTKeystoreAlias. . . . . . . . . . . . . . . . . . . .            | 221 |
| RESTSubdocument . . . . . . . . . . . . . . . . . . .               | 221 |
| RESTSubdocumentGroup. . . . . . . . . . . . . .                     | 222 |
| RESTSubdocumentList . . . . . . . . . . . . . . . .                 | 223 |
| RESTValidation . . . . . . . . . . . . . . . . . . . . . . .        | 223 |
| ResourceRevisedDto . . . . . . . . . . . . . . . . . .              | 223 |
| RetentionMessagesPoliciesDto . . . . . . . . .                      | 224 |
| RetentionPoliciesDto. . . . . . . . . . . . . . . . . .             | 224 |
| SEDTypeDto. . . . . . . . . . . . . . . . . . . . . . . . . .       | 225 |
| SearchDefinitionDto . . . . . . . . . . . . . . . . . .             | 225 |
| SectorDto . . . . . . . . . . . . . . . . . . . . . . . . . . . .   | 226 |
| SedDto. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . | 227 |
| SedIdentificationDto . . . . . . . . . . . . . . . . . .            | 227 |
| Source. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . | 227 |
| StandardBusinessDocumentHeaderDto.                                  | 230 |
| SyncInitialDocumentDto . . . . . . . . . . . . . .                  | 230 |
| TagDto. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . | 230 |
| TechnicalLogsDetailDto . . . . . . . . . . . . . . .                | 233 |
| TechnicalLogsTimeSlotDto . . . . . . . . . . . .                    | 235 |
| TenantDto . . . . . . . . . . . . . . . . . . . . . . . . . . .     | 235 |
| TimeSlotDto. . . . . . . . . . . . . . . . . . . . . . . . . .      | 235 |
| UserDto. . . . . . . . . . . . . . . . . . . . . . . . . . . . . .  | 236 |
| UserGroupDto. . . . . . . . . . . . . . . . . . . . . . . .         | 237 |
| UserMessageDto. . . . . . . . . . . . . . . . . . . . . .           | 238 |
| UserMessageResponseDto . . . . . . . . . . . . .                    | 239 |
| UserPasswordDto. . . . . . . . . . . . . . . . . . . . .            | 239 |
| UserProfileDto . . . . . . . . . . . . . . . . . . . . . . .        | 239 |
| UserTypeDto . . . . . . . . . . . . . . . . . . . . . . . . .       | 240 |
| ValidationMessageDto . . . . . . . . . . . . . . . .                | 241 |
| ValidationResultDto . . . . . . . . . . . . . . . . . .             | 241 |
| VersionDto. . . . . . . . . . . . . . . . . . . . . . . . . . .     | 241 |
| VocabularyDetailedRevisedDto . . . . . . . .                        | 242 |
| VocabularyDto . . . . . . . . . . . . . . . . . . . . . . .         | 242 |
| VocabularyStringDto. . . . . . . . . . . . . . . . . .              | 242 |
| X500Principal . . . . . . . . . . . . . . . . . . . . . . . .       | 242 |
| X509Certificate . . . . . . . . . . . . . . . . . . . . . . .       | 243 |

## Overview

Rest API Documentation for the EESSI RINA CPI module. Contains the complete reference of API methods and the object model definition.

## Version information

Version : 6.2.22

## Tags

- Activities : operations on Activities
- AdminNotificationType : operations on admin
- Alarms : operations on Alarms
- ApplicationProfile : operations on ApplicationProfile
- ApplicationProfileTenants : operations on ApplicationProfile/Tenants
- AssignmentPolicies : operations on AssignmentPolicies
- Attachments : operations on Attachments
- AuditLogs : operations on AuditLogs
- BusinessExceptions : operations on Pending Messages and Business Exceptions
- Cases : operations on Cases
- CheckBuckets : operation on CheckBuckets
- CheckDefinitions : operation on CheckDefinitions
- Comments : operations on Comments
- Configurations : Operations on application configurations.
- Documents : operations on Documents
- Entities : operations on Entities
- Files : operations on Files
- Forms : operations on Forms
- Identity : operations on Users
- Keystores : operations on Keystores
- Notifications : operations on Notifications
- ProcessDefinitions : operations on ProcessDefinitions
- Resources : operations on Resources
- SearchDefinitions : operations on SearchDefinitions
- Sectors : operations on Sectors
- Synchronizations : operations on ApplicationProfile

- TechnicalLogs : operations on TechnicalLogs
- UserProfile : operations on UserProfile
- Vocabularies : operations on Vocabularies
- organisations

## Paths

## Create a new activity

POST /Activities/Activity

## Description

Creates an Activity and returns the Object | (Available for following roles: ROLE\_REGULAR)

## Parameters

| Type   | Name          | Description       | Schema             |
|--------|---------------|-------------------|--------------------|
| Body   | body optional | The Activity data | ActivityRevisedDto |

## Responses

|   HTTP Code | Description                   | Schema                        |
|-------------|-------------------------------|-------------------------------|
|         200 | successful operation          | < ActivityRevisedDt o > array |
|         500 | Error creating a new activity | ApiError                      |

## Consumes

- application/json;charset=UTF-8

## Tags

- Activities

## Update a particular activity

PUT /Activities/Activity/{id}

## Description

Update a particular activity and return it | (Available for following roles: ROLE\_REGULAR)

## Parameters

| Type   | Name                                  | Description       | Schema             |
|--------|---------------------------------------|-------------------|--------------------|
| Query  | id optional ID of the activity object | string            |                    |
| Body   | body optional                         | The Activity data | ActivityRevisedDto |

## Responses

|   HTTP Code | Description                   | Schema              |
|-------------|-------------------------------|---------------------|
|         200 | successful operation          | ActivityRevisedDt o |
|         500 | Error updating a new activity | ApiError            |

## Consumes

- application/json;charset=UTF-8

## Tags

- Activities

## Deletes an activity associated to a particular user

DELETE /Activities/Activity/{id}

## Description

Removes an activity associated to a particular user | (Available for following roles: ROLE\_REGULAR)

## Parameters

| Type   | Name        | Description               | Schema   |
|--------|-------------|---------------------------|----------|
| Path   | id required | ID of the activity object | string   |

## Responses

|   HTTP Code | Description                 | Schema   |
|-------------|-----------------------------|----------|
|         500 | Cannot delete the activity. | ApiError |

## Produces

- application/json;charset=UTF-8

## Tags

- Activities

## Get activities for the current user over a particular time range

GET /Activities/AllActivities

## Description

Retrieves activities for current user | (Available for following roles: ROLE\_REGULAR)

## Parameters

| Type   | Name           | Description                                                                                                                                  | Schema   |
|--------|----------------|----------------------------------------------------------------------------------------------------------------------------------------------|----------|
| Query  | end required   | End parameter for the interval of activities, supports both ISO 8601 date and time format(yyyy-MM-dd'T'HH:mm:ss.SSSX) and epoch time(long)   | string   |
| Query  | start required | Start parameter for the interval of activities, supports both ISO 8601 date and time format(yyyy-MM-dd'T'HH:mm:ss.SSSX) and epoch time(long) | string   |

## Responses

|   HTTP Code | Description           | Schema                        |
|-------------|-----------------------|-------------------------------|
|         200 | successful operation  | < ActivityRevisedDt o > array |
|         500 | Cannot get activities | ApiError                      |

## Produces

- application/json;charset=UTF-8

## Tags

- Activities

## Get all admin notifications types

GET /AdminNotificationType/AllAdminNotificationTypes

## Description

Get all the types | (Available for following roles: ROLE\_ADMIN)

## Responses

|   HTTP Code | Description                            | Schema                              |
|-------------|----------------------------------------|-------------------------------------|
|         200 | successful operation                   | < AdminNotification TypeDto > array |
|         500 | Cannot get the adminNotification types | ApiError                            |

## Produces

- application/json;charset=UTF-8

## Tags

- AdminNotificationType

## Update a all admin notification types

PUT /AdminNotificationType/UpdateAllAdminNotificationTypes

## Description

Update all admin notification types | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name          | Schema                             |
|--------|---------------|------------------------------------|
| Body   | body optional | < AdminNotificationTypeDto > array |

## Responses

|   HTTP Code | Description                                 | Schema                              |
|-------------|---------------------------------------------|-------------------------------------|
|         200 | successful operation                        | < AdminNotification TypeDto > array |
|         500 | Cannot update all admin notification types. | ApiError                            |

## Tags

- AdminNotificationType

## Get the Application Profile

GET /ApplicationProfile

## Description

Retrieves the application-wide settings (except for the messaging settings) | (Available for following roles: ROLE\_ADMIN,ROLE\_REGULAR)

## Responses

|   HTTP Code | Description                | Schema                 |
|-------------|----------------------------|------------------------|
|         200 | successful operation       | ApplicationProfile Dto |
|         500 | Error during the operation | ApiError               |

## Produces

- application/json;charset=UTF-8

## Tags

- ApplicationProfile

## Update the Application Profile

PUT /ApplicationProfile

## Description

Updates  the  application-wide  settings  (except  for  the  following  parts,  which  are  taken  from  the existing object in the datastore: tenants, whoami, messagingSettings, iamSettings, nieSubscriptions, archivingPolicies, casesRetentionPolicies, messagesRetentionPolicies, archivingRepositories, archivingRepositoryPolicies, organizationSystemPassword) | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name          | Description                       | Schema                 |
|--------|---------------|-----------------------------------|------------------------|
| Body   | body required | The Application Profile to Update | ApplicationProfileDt o |

## Responses

|   HTTP Code | Description                           | Schema   |
|-------------|---------------------------------------|----------|
|         500 | Cannot update the application profile | ApiError |

## Consumes

- application/json;charset=UTF-8

## Tags

- ApplicationProfile

## Retrieving the archiving policies

GET /ApplicationProfile/ArchivingPolicies

## Description

Retrieving the archiving policies | (Available for following roles: ROLE\_ADMIN)

## Responses

|   HTTP Code | Description                       | Schema                |
|-------------|-----------------------------------|-----------------------|
|         200 | successful operation              | ArchivingPolicies Dto |
|         500 | Cannot get the archiving policies | ApiError              |

## Produces

- application/json

## Tags

- ApplicationProfile

## Update the archiving policies

PUT /ApplicationProfile/ArchivingPolicies

## Description

Update the archiving policies | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name          | Description                      | Schema               |
|--------|---------------|----------------------------------|----------------------|
| Body   | body required | The archiving policies to update | ArchivingPoliciesDto |

## Responses

|   HTTP Code | Description                          | Schema   |
|-------------|--------------------------------------|----------|
|         500 | Cannot update the archiving policies | ApiError |

## Consumes

- application/json

## Tags

- ApplicationProfile

## Retrieving the archiving repositories

GET /ApplicationProfile/ArchivingRepositories

## Description

Retrieving the archiving repositories | (Available for following roles: ROLE\_ADMIN)

## Responses

|   HTTP Code | Description                           | Schema                    |
|-------------|---------------------------------------|---------------------------|
|         200 | successful operation                  | ArchivingReposito riesDto |
|         500 | Cannot get the archiving repositories | ApiError                  |

## Produces

- application/json

## Tags

- ApplicationProfile

## Update the archiving repositories

PUT /ApplicationProfile/ArchivingRepositories

## Description

Update the archiving repositories | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name          | Description                          | Schema                    |
|--------|---------------|--------------------------------------|---------------------------|
| Body   | body required | The archiving repositories to update | ArchivingRepositori esDto |

## Responses

|   HTTP Code | Description                              | Schema   |
|-------------|------------------------------------------|----------|
|         500 | Cannot update the archiving repositories | ApiError |

## Consumes

- application/json

## Tags

- ApplicationProfile

## Retrieving the archiving repositories policies

GET /ApplicationProfile/ArchivingRepositoriesPolicies

CAUTION operation.deprecated

## Description

Retrieve the archiving repository policies | (Available for following roles: ROLE\_ADMIN)

## Responses

|   HTTP Code | Description          | Schema                                  |
|-------------|----------------------|-----------------------------------------|
|         200 | successful operation | < ArchivingReposito ryPolicyDto > array |

|   HTTP Code | Description                                  | Schema   |
|-------------|----------------------------------------------|----------|
|         500 | Cannot get the archiving repository policies | ApiError |

## Produces

- application/json

## Tags

- ApplicationProfile

## Update the archiving repository policies

PUT /ApplicationProfile/ArchivingRepositoriesPolicies

## CAUTION

operation.deprecated

## Description

Update the archiving repository policies | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name          | Description                                 | Schema                                  |
|--------|---------------|---------------------------------------------|-----------------------------------------|
| Body   | body required | The archiving repository policies to update | < ArchivingRepository PolicyDto > array |

## Responses

|   HTTP Code | Description                                     | Schema   |
|-------------|-------------------------------------------------|----------|
|         500 | Cannot update the archiving repository policies | ApiError |

## Consumes

- application/json

## Tags

- ApplicationProfile

## Retrieving the cases retention policies

GET /ApplicationProfile/CaseRetentionPolicies

CAUTION

operation.deprecated

## Description

Retrieve the cases retention policies | (Available for following roles: ROLE\_ADMIN)

## Responses

|   HTTP Code | Description                            | Schema                |
|-------------|----------------------------------------|-----------------------|
|         200 | successful operation                   | RetentionPolicies Dto |
|         500 | Cannot get the case retention policies | ApiError              |

## Produces

- application/json

## Tags

- ApplicationProfile

## Update the case retention policies

PUT /ApplicationProfile/CaseRetentionPolicies

CAUTION

operation.deprecated

## Description

Update the case retention policies | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name          | Description           | Schema               |
|--------|---------------|-----------------------|----------------------|
| Body   | body required | CaseRetentionPolicies | RetentionPoliciesDto |

## Responses

|   HTTP Code | Description                               | Schema   |
|-------------|-------------------------------------------|----------|
|         500 | Cannot update the case retention policies | ApiError |

## Consumes

- application/json

## Tags

- ApplicationProfile

## Synchronize LDAP users

POST /ApplicationProfile/IAMSettings/LdapSynchronization/{institutionId}

## Description

Synchronize users, groups and memberships with default role from LDAP | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name                   | Description                       | Schema   |
|--------|------------------------|-----------------------------------|----------|
| Path   | institutionId required | The institution Id to filter with | string   |

## Responses

|   HTTP Code | Description                                 | Schema   |
|-------------|---------------------------------------------|----------|
|         200 | successful operation                        | string   |
|         500 | Cannot run the LDAP synchronizaiton process | ApiError |

## Produces

- application/json;charset=UTF-8

## Tags

- ApplicationProfile

## Reassign group affected cases

POST /ApplicationProfile/IAMSettings/Reassignment

## Description

Rerun  the  case  assignment  for  cases  that  have  group  membership  updates  |  (Available  for following roles: ROLE\_ADMIN)

## Responses

|   HTTP Code | Description           | Schema   |
|-------------|-----------------------|----------|
|         500 | Cannot reassign cases | ApiError |

## Tags

- ApplicationProfile

## Retrieving the messages retention policies

GET /ApplicationProfile/MessageRetentionPolicies

## Description

Retrieve the message retention policies | (Available for following roles: ROLE\_ADMIN)

## Responses

|   HTTP Code | Description                               | Schema                        |
|-------------|-------------------------------------------|-------------------------------|
|         200 | successful operation                      | RetentionMessage sPoliciesDto |
|         500 | Cannot get the message retention policies | ApiError                      |

## Produces

- application/json

## Tags

- ApplicationProfile

## Update the message retention policies

PUT /ApplicationProfile/MessageRetentionPolicies

## Description

Update the message retention policies | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name          | Description                              | Schema                        |
|--------|---------------|------------------------------------------|-------------------------------|
| Body   | body required | The message retention policies to update | RetentionMessagesP oliciesDto |

## Responses

|   HTTP Code | Description                                  | Schema   |
|-------------|----------------------------------------------|----------|
|         500 | Cannot update the message retention policies | ApiError |

## Consumes

- application/json

## Tags

- ApplicationProfile

## Get the Messaging Settings

GET /ApplicationProfile/MessagingSettings

## Description

Retrieves the messaging settings | (Available for following roles: ROLE\_ADMIN)

## Responses

|   HTTP Code | Description                       | Schema                |
|-------------|-----------------------------------|-----------------------|
|         200 | successful operation              | MessagingSettings Dto |
|         500 | Cannot get the messaging settings | ApiError              |

## Produces

- application/json;charset=UTF-8

## Tags

- ApplicationProfile

## Update the Messaging Settings

PUT /ApplicationProfile/MessagingSettings

## Description

Updates  the  messaging  settings  and  configures  BPM  Service  |  (Available  for  following  roles: ROLE\_ADMIN)

## Parameters

| Type   | Name          | Description                      | Schema                |
|--------|---------------|----------------------------------|-----------------------|
| Body   | body required | The Messaging Settings to Update | MessagingSettingsDt o |

## Responses

|   HTTP Code | Description                          | Schema   |
|-------------|--------------------------------------|----------|
|         500 | Cannot update the messaging settings | ApiError |

## Consumes

- application/json;charset=UTF-8

## Tags

- ApplicationProfile

## Get the NIE subscriptions

GET /ApplicationProfile/NieSubscriptions

## Description

Retrieves the NIE subscriptions | (Available for following roles: ROLE\_ADMIN)

## Responses

|   HTTP Code | Description                      | Schema               |
|-------------|----------------------------------|----------------------|
|         200 | successful operation             | NieSubscriptionsD to |
|         500 | Cannot get the NIE subscriptions | ApiError             |

## Produces

- application/json;charset=UTF-8

## Tags

- ApplicationProfile

## Update the NIE settings

PUT /ApplicationProfile/NieSubscriptions

## Description

Updates the NIE settings | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name          | Description                | Schema              |
|--------|---------------|----------------------------|---------------------|
| Body   | body required | The NIE settings to Update | NieSubscriptionsDto |

## Responses

|   HTTP Code | Description                    | Schema   |
|-------------|--------------------------------|----------|
|         500 | Cannot update the NIE settings | ApiError |

## Consumes

- application/json;charset=UTF-8

## Tags

- ApplicationProfile

## Update the NIE subscription

PUT /ApplicationProfile/NieSubscriptions/{subscriptionId}

## Description

Updates the NIE subscription | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name                     | Description                    | Schema             |
|--------|--------------------------|--------------------------------|--------------------|
| Path   | subscriptionI d required | The Subscription Id            | string             |
| Body   | body required            | The NIE subscription to Update | NieSubscriptionDto |

## Responses

|   HTTP Code | Description                        | Schema   |
|-------------|------------------------------------|----------|
|         500 | Cannot update the NIE subscription | ApiError |

## Consumes

- application/json;charset=UTF-8

## Tags

- ApplicationProfile

## Delete the NIE subscription

DELETE /ApplicationProfile/NieSubscriptions/{subscriptionId}

## Description

Deletes the NIE subscription | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name       | Description         | Schema   |
|--------|------------|---------------------|----------|
| Path   | d required | The Subscription Id | string   |

## Responses

|   HTTP Code | Description                        | Schema   |
|-------------|------------------------------------|----------|
|         500 | Cannot delete the NIE subscription | ApiError |

## Tags

- ApplicationProfile

## Retrieves the list of Tenants and their attributes

GET /ApplicationProfile/Tenants

## Description

All Tenants are returned with their Organisation/Institution Details | (Available for following roles: ROLE\_ADMIN)

## Responses

|   HTTP Code | Description                         | Schema            |
|-------------|-------------------------------------|-------------------|
|         200 | successful operation                | < TenantDto array |
|         500 | Error trying to get List of Tenants | ApiError          |

## Produces

- application/json;charset=UTF-8

## Tags

- ApplicationProfileTenants

## Adds a Tenant by providing its Institution Id

POST /ApplicationProfile/Tenants/{tenantId}

## Description

New added Tenant is by default enabled not the default. If is the fist Tenant will also be the default. The Institution Id of the Tenant is also the Tenant Id. Insitutiton should exist with the same Id in the IR  Repository  and  should  be  part  of  the  same  Access  Point  with  any  other  existing  Tenant Institution. | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name              | Description                                 | Schema    |
|--------|-------------------|---------------------------------------------|-----------|
| Path   | tenantId required | The Tenant Id: Institution Id of the Tenant | string    |
| Body   | body optional     |                                             | TenantDto |

## Responses

|   HTTP Code | Description                | Schema   |
|-------------|----------------------------|----------|
|         200 | successful operation       | RESTId   |
|         400 | Error trying to add Tenant | ApiError |

|   HTTP Code | Description                | Schema   |
|-------------|----------------------------|----------|
|         409 | Error trying to add Tenant | ApiError |
|         500 | Error trying to add Tenant | ApiError |

## Consumes

- application/json;charset=UTF-8

## Produces

- application/json;charset=UTF-8

## Tags

- ApplicationProfileTenants

## Retrieves the Tenant attributes by its Tenant Id.

GET /ApplicationProfile/Tenants/{tenantId}

## Description

The  Tenant  Organisation/Institution  details  are  also  returned  as  found  in  local  IR  Repository  | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name              | Description                                 | Schema   |
|--------|-------------------|---------------------------------------------|----------|
| Path   | tenantId required | The Tenant Id: Institution Id of the Tenant | string   |

## Responses

|   HTTP Code | Description                | Schema    |
|-------------|----------------------------|-----------|
|         200 | successful operation       | TenantDto |
|         404 | Error trying to get Tenant | ApiError  |
|         500 | Error trying to get Tenant | ApiError  |

## Produces

- application/json;charset=UTF-8

## Tags

- ApplicationProfileTenants

## Updates the Tenant attributes by its id. Enables/Disables it or/and makes it the default.

PUT /ApplicationProfile/Tenants/{tenantId}

## Description

Only the attributes enabled and isDefault are processed for update. Organisation is ignored. The service will first validate if the update is valid and will accept or reject it. Default Tenant cannot be disabled. Single Tenant has to be default. | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name              | Description                                 | Schema    |
|--------|-------------------|---------------------------------------------|-----------|
| Path   | tenantId required | The Tenant Id: Institution Id of the Tenant | string    |
| Body   | body optional     |                                             | TenantDto |

## Responses

|   HTTP Code | Description                   | Schema   |
|-------------|-------------------------------|----------|
|         404 | Error trying to update Tenant | ApiError |
|         500 | Error trying to update Tenant | ApiError |

## Consumes

- application/json;charset=UTF-8

## Tags

- ApplicationProfileTenants

## Deletes a Tenant by providing its Tenant Id

DELETE /ApplicationProfile/Tenants/{tenantId}

## Description

The service checks if the Tenant can be deleted before proceeding to delete it. Tenants with cases or/and users cannot be deleted. Default Tenant cannot also be deleted. | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name              | Description                                 | Schema   |
|--------|-------------------|---------------------------------------------|----------|
| Path   | tenantId required | The Tenant Id: Institution Id of the Tenant | string   |

## Responses

|   HTTP Code | Description                   | Schema   |
|-------------|-------------------------------|----------|
|         404 | Error trying to delete Tenant | ApiError |
|         500 | Error trying to delete Tenant | ApiError |

## Tags

- ApplicationProfileTenants

## Retrieving the archiving repositories policies

GET /ApplicationProfile/recoveryVolume

## Description

Retrieve the archiving repository policies | (Available for following roles: ROLE\_ADMIN)

## Responses

|   HTTP Code | Description                          | Schema                                  |
|-------------|--------------------------------------|-----------------------------------------|
|         200 | successful operation                 | < ArchivingReposito ryPolicyDto > array |
|         500 | Cannot get the recovery repositories | ApiError                                |

## Produces

- text/plain

## Tags

- ApplicationProfile

## Update the archiving repository policies

PUT /ApplicationProfile/recoveryVolume

## Description

Update the archiving repository policies | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name          | Schema   |
|--------|---------------|----------|
| Body   | body optional | string   |

## Responses

|   HTTP Code | Description                     | Schema   |
|-------------|---------------------------------|----------|
|         500 | Cannot update the backup volume | ApiError |

## Consumes

- application/json

## Tags

- ApplicationProfile

## Create a case assignment policy

| POST /AssignmentPolicies   |
|----------------------------|

## Description

Creates  a  new  case  assignment  policy.  Will  not  add  the  targets  |  (Available  for  following  roles: ROLE\_ADMIN)

## Parameters

| Type                   | Name                              | Description          | Schema   |
|------------------------|-----------------------------------|----------------------|----------|
| institutionId required | The institution Id to filter with | string               | Query    |
| body required          | The case assignment policy        | AssignmentPolicyDt o | Body     |

## Responses

|   HTTP Code | Description                              | Schema        |
|-------------|------------------------------------------|---------------|
|         200 | successful operation                     | RESTId        |
|         500 | Cannot create the case assignment policy | RESTException |

## Consumes

- application/json;charset=UTF-8

## Produces

- application/json;charset=UTF-8

## Tags

- AssignmentPolicies

## Get the case assignment policies

GET /AssignmentPolicies

## Description

Retrieves a list of case assignment policies | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type                   | Name                               | Description           | Schema   |
|------------------------|------------------------------------|-----------------------|----------|
| institutionId required | The institution Id to filter with  | string                | Query    |
| name optional          | The policy name                    | string                | Query    |
| targetIds optional     | The id of the target of the policy | < string array(multi) | Query    |

## Responses

|   HTTP Code | Description                                  | Schema                         |
|-------------|----------------------------------------------|--------------------------------|
|         200 | successful operation                         | < AssignmentPolicy Dto > array |
|         500 | Cannot retrieve the case assignment policies | RESTException                  |

## Produces

- application/json;charset=UTF-8

## Tags

- AssignmentPolicies

## Creates or updates the assignment policy target

PUT /AssignmentPolicies/Target/{targetId}

## Description

Creates an association between assignment policies and a target | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type                   | Name                               | Description      | Schema   |
|------------------------|------------------------------------|------------------|----------|
| targetId required      | The id of the target of the policy | string           | Path     |
| institutionId required | The institution Id to filter with  | string           | Query    |
| body optional          | The case assignment policies array | < string > array | Body     |

## Responses

|   HTTP Code | Description                                | Schema        |
|-------------|--------------------------------------------|---------------|
|         500 | Cannot update the assignment policy target | RESTException |

## Consumes

- application/json;charset=UTF-8

## Tags

- AssignmentPolicies

## Get the case assignment policy

GET /AssignmentPolicies/{policyId}

## Description

Retrieves a case assignment policy | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name                   | Description                       | Schema   |
|--------|------------------------|-----------------------------------|----------|
| Path   | policyId required      | The policy id                     | string   |
| Query  | institutionId required | The institution Id to filter with | string   |

## Responses

|   HTTP Code | Description                                | Schema               |
|-------------|--------------------------------------------|----------------------|
|         200 | successful operation                       | AssignmentPolicy Dto |
|         500 | Cannot retrieve the case assignment policy | RESTException        |

## Produces

- application/json;charset=UTF-8

## Tags

- AssignmentPolicies

## Update a case assignment policy

PUT /AssignmentPolicies/{policyId}

## Description

Updates an existing case assignment policy. Will not update the targets | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name                   | Description                       | Schema   |
|--------|------------------------|-----------------------------------|----------|
| Path   | policyId required      | The policy id                     | string   |
| Query  | institutionId required | The institution Id to filter with | string   |

| Type   | Name          | Description                | Schema               |
|--------|---------------|----------------------------|----------------------|
| Body   | body required | The case assignment policy | AssignmentPolicyDt o |

## Responses

|   HTTP Code | Description                              | Schema        |
|-------------|------------------------------------------|---------------|
|         500 | Cannot update the case assignment policy | RESTException |

## Consumes

- application/json;charset=UTF-8

## Tags

- AssignmentPolicies

## Delete a case assignment policy

DELETE /AssignmentPolicies/{policyId}

## Description

Deletes an existing case assignment policy | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name                   | Description                       | Schema   |
|--------|------------------------|-----------------------------------|----------|
| Path   | policyId required      | The policy id                     | string   |
| Query  | institutionId required | The institution Id to filter with | string   |

## Responses

|   HTTP Code | Description                              | Schema        |
|-------------|------------------------------------------|---------------|
|         500 | Cannot delete the case assignment policy | RESTException |

## Tags

- AssignmentPolicies

## Add a target to an assignment policy

PUT /AssignmentPolicies/{policyId}/Targets/{targetId}

## Description

Creates an association between a policy and a target | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type                   | Name                               | Description   | Schema   |
|------------------------|------------------------------------|---------------|----------|
| policyId required      | The policy id                      | string        | Path     |
| targetId required      | The id of the target of the policy | string        | Path     |
| institutionId required | The institution Id to filter with  | string        | Query    |

## Responses

|   HTTP Code | Description                                 | Schema        |
|-------------|---------------------------------------------|---------------|
|         500 | Cannot add target to case assignment policy | RESTException |

## Tags

- AssignmentPolicies

## Remove a target from an assignment policy

DELETE /AssignmentPolicies/{policyId}/Targets/{targetId}

## Description

Removes  an  association between  a policy and  a target | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type                   | Name                               | Description   | Schema   |
|------------------------|------------------------------------|---------------|----------|
| policyId required      | The policy id                      | string        | Path     |
| targetId required      | The id of the target of the policy | string        | Path     |
| institutionId required | The institution Id to filter with  | string        | Query    |

## Responses

|   HTTP Code | Description                                      | Schema        |
|-------------|--------------------------------------------------|---------------|
|         500 | Cannot remove target from case assignment policy | RESTException |

## Tags

- AssignmentPolicies

## Retrieve the audit logs details

GET /AuditLogs

## Description

Retrieves the audit logs details of a specific day using some aditional filter parameters

## Parameters

| Type   | Name                | Description        | Schema   |
|--------|---------------------|--------------------|----------|
| Query  | actionType optional | The type of action | string   |

| Type   | Name                        | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       | Schema                  |
|--------|-----------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------|
| Query  | auditedObject Id optional   | The id of the audited object. The field has the following logic in connection to auditedObjectType field when checking if it is required (the parameter auditedObjectId is mandatory only in the case the parameter auditedObjectType is defined): 1.) The request parameters are considered as INVALID in the following cases: • when the length of the auditedObjectType[] array is greater than the length of the auditedObjectId[] array • when the length of the auditedObjectType[] array is less than the length of the auditedObjectId[] array and the length of the auditedObjectType[] array is not equal to 1 2.) The request parameters are considered as VALID in the following cases: • when both auditedObjectType[] and auditedObjectId[] arrays are empty • in all other cases that are not covered by the above specified cases | < string > array(multi) |
| Query  | auditedObject Type optional | The audited object, ex: case, subject, etc. Users with ROLE_REGULAR can only filter by type 'cas' < string array(multi)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           | >                       |
| Query  | categoryType optional       | The type of category                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | string                  |
| Query  | componentTy pe optional     | The type of component                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             | string                  |
| Query  | count optional              | The end index of retrieved entries                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                | integer (int32)         |
| Query  | date required               | The time slot (hour in this case)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 | string                  |

| Type Name                       | Description                          | Schema                  |
|---------------------------------|--------------------------------------|-------------------------|
| eventType optional              | string                               | Query The type of event |
| Query from optional             | The start index of retrieved entries | integer (int32)         |
| Query outcomeType optional      | The type of outcome                  | string                  |
| Query participantId optional    | The id of a participant              | string                  |
| Query le optional               | The role of a participant            | string                  |
| Query participantTy pe optional | The type of a participant            | string                  |
| Query text optional             | The free text to search by           | string                  |

## Responses

|   HTTP Code | Description                           | Schema                        |
|-------------|---------------------------------------|-------------------------------|
|         200 | successful operation                  | < AuditLogsDetailDt o > array |
|         500 | Cannot retrieve the audit log details | RESTException                 |

## Produces

- application/json

## Tags

- AuditLogs

## Retrieve the audit log time slots

GET /AuditLogs/TimeSlots

## Description

Retrieves  the  time  slots(hours  in  this  case)  when  there  are  audit  log  entries  and  the  number  of entries on those days | (Available for following roles: ROLE\_REGULAR,ROLE\_ADMIN)

## Parameters

| Type   | Name                        | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       | Schema                |
|--------|-----------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------|
| Query  | actionType optional         | The type of action                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                | string                |
| Query  | auditedObject Id optional   | The id of the audited object. The field has the following logic in connection to auditedObjectType field when checking if it is required (the parameter auditedObjectId is mandatory only in the case the parameter auditedObjectType is defined): 1.) The request parameters are considered as INVALID in the following cases: • when the length of the auditedObjectType[] array is greater than the length of the auditedObjectId[] array • when the length of the auditedObjectType[] array is less than the length of the auditedObjectId[] array and the length of the auditedObjectType[] array is not equal to 1 2.) The request parameters are considered as VALID in the following cases: • when both auditedObjectType[] and auditedObjectId[] arrays are empty • in all other cases that are not covered by the above specified cases | < string array(multi) |
| Query  | auditedObject Type optional | The audited object, ex: case, subject, etc. Users with ROLE_REGULAR can only filter by type 'cas'                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 | < string array(multi) |

| Type   | Name                      | Description                   | Schema   |
|--------|---------------------------|-------------------------------|----------|
| Query  | categoryType optional     | The type of category          | string   |
| Query  | componentTy pe optional   | The type of component         | string   |
| Query  | endDate required          | The end time(hour accuracy)   | string   |
| Query  | eventType optional        | The type of event             | string   |
| Query  | outcomeType optional      | The type of outcome           | string   |
| Query  | participantId optional    | The id of a participant       | string   |
| Query  | participantRo le optional | The role of a participant     | string   |
| Query  | participantTy pe optional | The type of a participant     | string   |
| Query  | startDate required        | The start time(hour accuracy) | string   |
| Query  | text optional             | The free text to search by    | string   |

## Responses

|   HTTP Code | Description                    | Schema                          |
|-------------|--------------------------------|---------------------------------|
|         200 | successful operation           | < AuditLogsTimeSlo tDto > array |
|         500 | Cannot retrieve the time slots | RESTException                   |

## Produces

- application/json

## Tags

- AuditLogs

## Submit a business exception

POST /BusinessExceptions

## Description

Submit  the  business  exceptions  details.  The  business  exception  is  created  based  on  an  existing Pending Message (created automatically by the system) | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name                        | Description                     | Schema                |
|--------|-----------------------------|---------------------------------|-----------------------|
| Body   | businessExce ption required | The business exceptions content | BusinessExceptionDt o |

## Responses

|   HTTP Code | Description                                              | Schema        |
|-------------|----------------------------------------------------------|---------------|
|         500 | Exception occurred when submiting the business exception | RESTException |

## Consumes

- application/json;charset=UTF-8

## Tags

- BusinessExceptions

## Retrieve the business exceptions details

| GET /BusinessExceptions   |
|---------------------------|

## Description

Retrieves the business exceptions details for a specific time period and optionally filter | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type          | Name                              | Description   | Schema   |
|---------------|-----------------------------------|---------------|----------|
| e optional    | The business exception type       | string        | Query    |
| date required | The time slot (hour in this case) | string        | Query    |
| text optional | The free text to search by        | string        | Query    |

## Responses

|   HTTP Code | Description                                    | Schema                          |
|-------------|------------------------------------------------|---------------------------------|
|         200 | successful operation                           | < BusinessException Dto > array |
|         500 | Cannot retrieve the business exception details | RESTException                   |

## Produces

- application/json;charset=UTF-8

## Tags

- BusinessExceptions

## Retrieve the business exceptions time slots

GET /BusinessExceptions/TimeSlots

## Description

Retrieves the business exceptions time slots where there are entries and the number of entries on those time slots | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name                         | Description                | Schema   |
|--------|------------------------------|----------------------------|----------|
| Query  | bexceptiontyp e optional The | business exception type    | string   |
| Query  | text optional                | The free text to search by | string   |

## Responses

|   HTTP Code | Description                    | Schema                |
|-------------|--------------------------------|-----------------------|
|         200 | successful operation           | < TimeSlotDto > array |
|         500 | Cannot retrieve the time slots | RESTException         |

## Produces

- application/json;charset=UTF-8

## Tags

- BusinessExceptions

## Retrieve the SED content of the business exception

GET /BusinessExceptions/{exceptionId}/Document

## Description

Retrieves  the  SED  content  that  caused  the  business  exception  |  (Available  for  following  roles: ROLE\_ADMIN)

## Parameters

| Type   | Name                 | Description                      | Schema   |
|--------|----------------------|----------------------------------|----------|
| Path   | exceptionId required | The id of the business exception | string   |

## Responses

|   HTTP Code | Description                                          | Schema        |
|-------------|------------------------------------------------------|---------------|
|         200 | successful operation                                 | SedDto        |
|         500 | Cannot retrieve the business exception's SED content | RESTException |

## Produces

- application/json;charset=UTF-8

## Tags

- BusinessExceptions

## Retrieve the rejection SED content of the business exception

GET /BusinessExceptions/{exceptionId}/RejectionDocument

## Description

Retrieves  the  rejection  SED  content  coresponding  to  the  business  exception  |  (Available  for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name                 | Description                      | Schema   |
|--------|----------------------|----------------------------------|----------|
| Path   | exceptionId required | The id of the business exception | string   |

## Responses

|   HTTP Code | Description                                                         | Schema        |
|-------------|---------------------------------------------------------------------|---------------|
|         200 | successful operation                                                | SedDto        |
|         500 | Cannot retrieve the rejection SED content of the business exception | RESTException |

## Produces

- application/json;charset=UTF-8

## Tags

- BusinessExceptions

## Create new case

POST /Cases

## Description

Creates a new case of the specified type | (Available for following roles: ROLE\_REGULAR)

## Parameters

| Type   | Name          | Description         | Schema             |
|--------|---------------|---------------------|--------------------|
| Body   | body required | Creation parameters | CaseCreationParams |

## Responses

|   HTTP Code | Description              | Schema   |
|-------------|--------------------------|----------|
|         200 | successful operation     | RESTId   |
|         500 | Cannot create a new case | ApiError |

## Consumes

- application/json;charset=UTF-8

## Produces

- application/json;charset=UTF-8

## Tags

- Cases

## Search cases by parameters

GET /Cases

## Description

Search cases by free text and/or a predefined search | (Available for following roles: ROLE\_REGULAR)

## Parameters

| Type                         | Name                                 | Description     | Schema   |
|------------------------------|--------------------------------------|-----------------|----------|
| limit optional               | Pagination limit                     | integer (int32) | Query    |
| offset optional              | Pagination offset                    | integer (int32) | Query    |
| searchDefiniti onId optional | The id of the predefined search      | string          | Query    |
| searchText optional          | Text that is going to be searched by | string          | Query    |

## Responses

|   HTTP Code | Description          | Schema                  |
|-------------|----------------------|-------------------------|
|         200 | successful operation | < CaseTraitsDto > array |
|         500 | Cannot search cases  | ApiError                |

## Produces

- application/json;charset=UTF-8

## Tags

- Cases

## Get a case by the business ID

GET /Cases/ByBusinessId/{businessId}

## Description

Retrieves the case information given its business id | (Available for following roles: ROLE\_REGULAR)

## Parameters

| Type   | Name                | Description                             | Schema   |
|--------|---------------------|-----------------------------------------|----------|
| Path   | businessId required | The business Id of the case to retrieve | string   |

## Responses

|   HTTP Code | Description                        | Schema         |
|-------------|------------------------------------|----------------|
|         200 | successful operation               | CaseRevisedDto |
|         500 | Cannot get case by its business ID | ApiError       |

## Produces

- application/json;charset=UTF-8

## Tags

- Cases

## Get a case by the international ID

GET /Cases/ByInternationalId/{internationalId}

## Description

Retrieves the case information  given  its international id | (Available for following roles: ROLE\_REGULAR)

## Parameters

| Type   | Name                      | Description                                  | Schema   |
|--------|---------------------------|----------------------------------------------|----------|
| Path   | internationalI d required | The international Id of the case to retrieve | string   |

## Responses

|   HTTP Code | Description                             | Schema         |
|-------------|-----------------------------------------|----------------|
|         200 | successful operation                    | CaseRevisedDto |
|         500 | Cannot get case by its international ID | RESTException  |

## Produces

- application/json;charset=UTF-8

## Tags

- Cases

## Get a case ID by the business ID

GET /Cases/IdByBusinessId/{businessId}

## Description

Retrieves the case ID of a case given its business id | (Available for following roles: ROLE\_REGULAR)

## Parameters

| Type   | Name                | Description                             | Schema   |
|--------|---------------------|-----------------------------------------|----------|
| Path   | businessId required | The business Id of the case to retrieve | string   |

## Responses

|   HTTP Code | Description                                          | Schema   |
|-------------|------------------------------------------------------|----------|
|         200 | successful operation                                 | string   |
|         500 | Cannot get case ID from the case by it's business ID | ApiError |

## Produces

- application/json;charset=UTF-8

## Tags

- Cases

## Get a case ID by the international ID

GET /Cases/IdByInternationalId/{internationalId}

## Description

Retrieves  the  case  ID  of  a  case  given  its  international  id  |  (Available  for  following  roles: ROLE\_REGULAR)

## Parameters

| Type   | Name                      | Description                                  | Schema   |
|--------|---------------------------|----------------------------------------------|----------|
| Path   | internationalI d required | The international Id of the case to retrieve | string   |

## Responses

|   HTTP Code | Description                                               | Schema        |
|-------------|-----------------------------------------------------------|---------------|
|         200 | successful operation                                      | string        |
|         500 | Cannot get case ID from the case by it's international ID | RESTException |

## Produces

- application/json;charset=UTF-8

## Tags

- Cases

## Import Subdocuments

POST /Cases/{caseId}/Actions/{actionId}/Batch

## Description

Import subdocuments from XML file on a specific document of a case. | (Available for following roles: ROLE\_REGULAR)

## Parameters

| Type      | Name              | Description                                     | Schema   |
|-----------|-------------------|-------------------------------------------------|----------|
| Path      | actionId required | The id of the Import Action of a batch document | string   |
| Path      | caseId required   | The Id of the Case                              | string   |
| FormDat a | file required     | The file to be imported                         | file     |

## Responses

|   HTTP Code | Description                | Schema   |
|-------------|----------------------------|----------|
|         500 | Cannot import Subdocuments | ApiError |

## Consumes

- multipart/form-data

## Tags

- Documents

## Submit Document

PUT /Cases/{caseId}/Actions/{actionId}/Document

## Description

Submits/saves the document for a case and an action thereby executing the action. | (Available for following roles: ROLE\_REGULAR)

## Parameters

| Type                           | Name                 | Description          | Schema   |
|--------------------------------|----------------------|----------------------|----------|
| Path actionId required         | The id of the Action | string               |          |
| Path caseId required           | The Id of the Case   | string               |          |
| Body documentCon tent required | The Document content | < string, object map | >        |

## Responses

|   HTTP Code | Description                | Schema         |
|-------------|----------------------------|----------------|
|         200 | successful operation       | RESTValidation |
|         500 | Cannot submit the document | ApiError       |

## Consumes

- application/json;charset=UTF-8

## Tags

- Documents

## Retrieve Initial Document

GET /Cases/{caseId}/Actions/{actionId}/InitialDocument

## Description

Retrieves  the  Initial  Document  specific  to  a  case  and  an  action  |  (Available  for  following  roles: ROLE\_REGULAR)

## Parameters

| Type   | Name Description                           | Schema   |
|--------|--------------------------------------------|----------|
| Path   | actionId required The id of the Action     | string   |
| Path   | caseId required The Id of the Case         | string   |
| Query  | cumentId The Id of the related Subdocument | string   |

## Responses

|   HTTP Code | Description                      | Schema                 |
|-------------|----------------------------------|------------------------|
|         200 | successful operation             | < string, object > map |
|         500 | Cannot retrieve initial Document | ApiError               |

## Produces

- application/json;charset=UTF-8

## Tags

- Documents

## Set alarm

POST /Cases/{caseId}/Alarms

## Description

Create a local alarm of a case | (Available for following roles: ROLE\_REGULAR)

## Parameters

| Type   | Name            | Description               | Schema   |
|--------|-----------------|---------------------------|----------|
| Path   | caseId required | The Id of the Case        | string   |
| Body   | body required   | The details of the Alarmm | AlarmDto |

## Responses

|   HTTP Code | Description                | Schema        |
|-------------|----------------------------|---------------|
|         200 | successful operation       | RESTId        |
|         500 | Error during the operation | RESTException |

## Consumes

- application/json;charset=UTF-8

## Produces

- application/json;charset=UTF-8

## Tags

- Alarms

## Get alarms of a case

GET /Cases/{caseId}/Alarms

## Description

Retrieves the list of alarms of a case | (Available for following roles: ROLE\_REGULAR)

## Parameters

| Type   | Name            | Description        | Schema   |
|--------|-----------------|--------------------|----------|
| Path   | caseId required | The Id of the Case | string   |

## Responses

|   HTTP Code | Description                | Schema           |
|-------------|----------------------------|------------------|
|         200 | successful operation       | < AlarmDto array |
|         500 | Error during the operation | RESTException    |

## Produces

- application/json;charset=UTF-8

## Tags

- Alarms

## Clear alarm

DELETE /Cases/{caseId}/Alarms/{alarmId}

## Description

Delete a local alarm of a case | (Available for following roles: ROLE\_REGULAR)

## Parameters

| Type   | Name             | Description         | Schema   |
|--------|------------------|---------------------|----------|
| Path   | alarmId required | The Id of the Alarm | string   |
| Path   | caseId required  | The Id of the Case  | string   |

## Responses

|   HTTP Code | Description                | Schema        |
|-------------|----------------------------|---------------|
|         500 | Error during the operation | RESTException |

## Tags

- Alarms

## Update Case Assignments

PUT /Cases/{caseId}/Assignment

## Description

Assign and/or unassign users and groups to the roles of a case instance | (Available for following roles: ROLE\_REGULAR)

## Parameters

| Type                 | Name                       | Description               | Schema   |
|----------------------|----------------------------|---------------------------|----------|
| Path caseId required | The Id of the Case         | string                    |          |
| body required        | The case Assigment Details | CaseAssignmentRevi sedDto | Body     |

## Responses

|   HTTP Code | Description                    | Schema   |
|-------------|--------------------------------|----------|
|         500 | Cannot update case assignments | ApiError |

## Consumes

- application/json;charset=UTF-8

## Produces

- application/json;charset=UTF-8

## Tags

- Cases

## Executes case assigment related action

POST /Cases/{caseId}/Assignment/Actions

## Description

Executes one of the 3 possible assignment related actions: request assignment, accept assignment

## Parameters

| Type            | Name                       | Description                     | Schema   |
|-----------------|----------------------------|---------------------------------|----------|
| caseId required | The Id of the Case         | string                          | Path     |
| body required   | The case Assigment Details | CaseAssignmentActi onRevisedDto | Body     |

## Responses

|   HTTP Code | Description                                  | Schema   |
|-------------|----------------------------------------------|----------|
|         500 | Cannot execute case assigment related action | ApiError |

## Consumes

- application/json;charset=UTF-8

## Produces

- application/json;charset=UTF-8

## Tags

- Cases

## Submit attachment on a case

POST /Cases/{caseId}/Attachments

## Description

Submits  an  attachment  for  a  case,  returns  the  attachment  id  |  (Available  for  following  roles: ROLE\_REGULAR)

## Parameters

| Type   | Name            | Description                                            | Schema   |
|--------|-----------------|--------------------------------------------------------|----------|
| Path   | caseId required | The Id of the case, on which the attachment belongs to | string   |

| Type      | Name          | Description             | Schema   |
|-----------|---------------|-------------------------|----------|
| FormDat a | file required | The file to be attached | file     |

## Responses

|   HTTP Code | Description                  | Schema        |
|-------------|------------------------------|---------------|
|         200 | successful operation         | RESTId        |
|         500 | Cannot submit the attachment | RESTException |

## Consumes

- multipart/form-data

## Produces

- application/json;charset=UTF-8

## Tags

- Attachments

## Retrieve attachment of a case

GET /Cases/{caseId}/Attachments/{id}

## Description

Retrieves  the  attachment  coresponding  to  a  case  by  its  id  |  (Available  for  following  roles: ROLE\_REGULAR)

## Parameters

| Type   | Name            | Description                                            | Schema   |
|--------|-----------------|--------------------------------------------------------|----------|
| Path   | caseId required | The Id of the case, on which the attachment belongs to | string   |
| Path   | id required     | The Id of the Attachment                               | string   |

## Responses

|   HTTP Code | Description                    | Schema        |
|-------------|--------------------------------|---------------|
|         200 | successful operation           | string (byte) |
|         500 | Cannot retrieve the attachment | RESTException |

## Tags

- Attachments

## Delete attachment of a case

DELETE /Cases/{caseId}/Attachments/{id}

## Description

Deletes the attachment specified by the case id and attachment id | (Available for following roles: ROLE\_REGULAR)

## Parameters

| Type   | Name            | Description                                            | Schema   |
|--------|-----------------|--------------------------------------------------------|----------|
| Path   | caseId required | The Id of the case, on which the attachment belongs to | string   |
| Path   | id required     | The Id of the Attachment                               | string   |

## Responses

|   HTTP Code | Description                  | Schema        |
|-------------|------------------------------|---------------|
|         500 | Cannot delete the attachment | RESTException |

## Tags

- Attachments

## Update the Medical Information flag of a case attachment

PUT /Cases/{caseId}/Attachments/{id}/Metadata

## Description

Update  the  Medical  Information  flag  of  a  case  attachment  |  (Available  for  following  roles: ROLE\_REGULAR)

## Parameters

| Type            | Name                                                          | Description          | Schema   |
|-----------------|---------------------------------------------------------------|----------------------|----------|
| caseId required | The Id of the Case                                            | string               | Path     |
| id required     | The Id of the Attachment                                      | string               | Path     |
| body required   | The value of the medical information flag for this attachment | < string, object map | Body     |

## Responses

|   HTTP Code | Description                       | Schema        |
|-------------|-----------------------------------|---------------|
|         500 | Cannot update the attachment flag | RESTException |

## Tags

- Attachments

## Submit comment on case

POST /Cases/{caseId}/Comments

## Description

Submits a new comment on a case | (Available for following roles: ROLE\_REGULAR)

## Parameters

| Type   | Name            | Description        | Schema     |
|--------|-----------------|--------------------|------------|
| Path   | caseId required | The Id of the Case | string     |
| Body   | body required   | Comment to submit  | CommentDto |

## Responses

|   HTTP Code | Description                           | Schema   |
|-------------|---------------------------------------|----------|
|         200 | successful operation                  | RESTId   |
|         500 | Cannot submit the comment on the case | ApiError |

## Consumes

- application/json;charset=UTF-8

## Produces

- application/json;charset=UTF-8

## Tags

- Comments

## Delete comment of a case

DELETE /Cases/{caseId}/Comments/{id}

## Description

Deletes a comment of a case | (Available for following roles: ROLE\_REGULAR)

## Parameters

| Type   | Name            | Description        | Schema   |
|--------|-----------------|--------------------|----------|
| Path   | caseId required | The Id of the Case | string   |

| Type   | Name        | Description           | Schema   |
|--------|-------------|-----------------------|----------|
| Path   | id required | The Id of the Comment | string   |

## Responses

|   HTTP Code | Description                           | Schema   |
|-------------|---------------------------------------|----------|
|         404 | Cannot delete the comment of the case | ApiError |

## Tags

- Comments

## Submit attachment on a document

POST /Cases/{caseId}/Documents/{documentId}/Attachments

## Description

Submit  attachment  on  a  document,  returns  the  attachment  id  |  (Available  for  following  roles: ROLE\_REGULAR)

## Parameters

| Type      | Name                | Description                                                | Schema   |
|-----------|---------------------|------------------------------------------------------------|----------|
| Path      | caseId required     | The Id of the case, on which the attachment belongs to     | string   |
| Path      | documentId required | The Id of the Document, on which the attachment belongs to | string   |
| FormDat a | file required       | The file to be attached                                    | file     |

## Responses

|   HTTP Code | Description          | Schema   |
|-------------|----------------------|----------|
|         200 | successful operation | RESTId   |

|   HTTP Code | Description                  | Schema        |
|-------------|------------------------------|---------------|
|         500 | Cannot submit the attachment | RESTException |

## Consumes

- multipart/form-data

## Produces

- application/json;charset=UTF-8

## Tags

- Attachments

## Retrieve attachment of a document

GET /Cases/{caseId}/Documents/{documentId}/Attachments/{id}

## Description

Retrieves the attachment coresponding to a document of a case by its id | (Available for following roles: ROLE\_REGULAR)

## Parameters

| Type                | Name                                                       | Description   | Schema   |
|---------------------|------------------------------------------------------------|---------------|----------|
| caseId required     | The Id of the case, on which the attachment belongs to     | string        | Path     |
| documentId required | The Id of the Document, on which the attachment belongs to | string        | Path     |
| id required         | The Id of the Attachment                                   | string        | Path     |

## Responses

|   HTTP Code | Description          | Schema        |
|-------------|----------------------|---------------|
|         200 | successful operation | string (byte) |

|   HTTP Code | Description                    | Schema        |
|-------------|--------------------------------|---------------|
|         500 | Cannot retrieve the attachment | RESTException |

## Tags

- Attachments

## Delete attachment of a document

DELETE /Cases/{caseId}/Documents/{documentId}/Attachments/{id}

## Description

Deletes  the  attachment  specified  by  the  case  id,  document  id  and  attachment  id  |  (Available  for following roles: ROLE\_REGULAR)

## Parameters

| Type                | Name                     | Description   | Schema   |
|---------------------|--------------------------|---------------|----------|
| caseId required     | The Id of the Case       | string        | Path     |
| documentId required | The id of the document   | string        | Path     |
| id required         | The id of the attachment | string        | Path     |

## Responses

|   HTTP Code | Description                  | Schema        |
|-------------|------------------------------|---------------|
|         500 | Cannot delete the attachment | RESTException |

## Tags

- Attachments

## Update the Medical Information flag of a document attachment

PUT /Cases/{caseId}/Documents/{documentId}/Attachments/{id}/Metadata

## Description

Update the  Medical  Information  flag  of  a  document  attachment  |  (Available  for  following  roles: ROLE\_REGULAR)

## Parameters

| Type                     | Name                                                          | Description          | Schema   |
|--------------------------|---------------------------------------------------------------|----------------------|----------|
| Path caseId required     | The Id of the Case                                            | string               |          |
| Path documentId required | The Id of the Document                                        | string               |          |
| Path id required         | The Id of the Attachment                                      | string               |          |
| body required            | The value of the medical information flag for this attachment | < string, object map | Body     |

## Responses

|   HTTP Code | Description                       | Schema        |
|-------------|-----------------------------------|---------------|
|         500 | Cannot update the attachment flag | RESTException |

## Tags

- Attachments

## Export Subdocuments

GET /Cases/{caseId}/Documents/{documentId}/Batch

## Description

Export subdocuments to a XML file. | (Available for following roles: ROLE\_REGULAR)

## Parameters

| Type   | Name                | Description            | Schema   |
|--------|---------------------|------------------------|----------|
| Path   | caseId required     | The Id of the Case     | string   |
| Path   | documentId required | The Id of the Document | string   |

## Responses

|   HTTP Code | Description                | Schema                |
|-------------|----------------------------|-----------------------|
|         200 | successful operation       | < string (byte) array |
|         500 | Cannot export Subdocuments | ApiError              |

## Produces

- application/octet-stream

## Tags

- Documents

## Retrieve the Business Signing Certificate

GET /Cases/{caseId}/Documents/{documentId}/Certificate

## Description

Retrieves  the  Business  Signing  Certificate  of  the  SED/document.  |  (Available  for  following  roles: ROLE\_REGULAR)

## Parameters

| Type   | Name                | Description            | Schema   |
|--------|---------------------|------------------------|----------|
| Path   | caseId required     | The Id of the Case     | string   |
| Path   | documentId required | The Id of the Document | string   |

## Responses

|   HTTP Code | Description                                  | Schema          |
|-------------|----------------------------------------------|-----------------|
|         200 | successful operation                         | X509Certificate |
|         500 | Cannot retrieve Business Signing Certificate | ApiError        |

## Tags

- Documents

## Submit comment on document

POST /Cases/{caseId}/Documents/{documentId}/Comments

## Description

Submits  a  new  comment  on  a  specified  document  of  a  specified  case  |  (Available  for  following roles: ROLE\_REGULAR)

## Parameters

| Type                | Name                   | Description   | Schema   |
|---------------------|------------------------|---------------|----------|
| caseId required     | The Id of the Case     | string        | Path     |
| documentId required | The Id of the Document | string        | Path     |
| body optional       | Comment to submit      | CommentDto    | Body     |

## Responses

|   HTTP Code | Description                               | Schema   |
|-------------|-------------------------------------------|----------|
|         200 | successful operation                      | RESTId   |
|         500 | Cannot submit the comment on the document | ApiError |

## Consumes

- application/json;charset=UTF-8

## Produces

- application/json;charset=UTF-8

## Tags

- Comments

## Delete comment of a document

DELETE /Cases/{caseId}/Documents/{documentId}/Comments/{id}

## Description

Delete  comment  on  a  specified  document  for  a  specific  case  |  (Available  for  following  roles: ROLE\_REGULAR)

## Parameters

| Type                | Name                   | Description   | Schema   |
|---------------------|------------------------|---------------|----------|
| caseId required     | The Id of the Case     | string        | Path     |
| documentId required | The Id of the Document | string        | Path     |
| id required         | The Id of the Comment  | string        | Path     |

## Responses

| HTTP Code   | Description          | Schema     |
|-------------|----------------------|------------|
| default     | successful operation | No Content |

## Tags

- Comments

## Retrieve Document Details

GET /Cases/{caseId}/Documents/{documentId}/Details

## Description

Retrieves  the  details  of  a  specific  SED  -  document  relation.  |  (Available  for  following  roles: ROLE\_REGULAR)

## Parameters

| Type   | Name                | Description            | Schema   |
|--------|---------------------|------------------------|----------|
| Path   | caseId required     | The Id of the Case     | string   |
| Path   | documentId required | The Id of the Document | string   |

## Responses

|   HTTP Code | Description                                 | Schema                     |
|-------------|---------------------------------------------|----------------------------|
|         200 | successful operation                        | DocumentDetailsR evisedDto |
|         500 | Cannot retrieve the details of the Document | ApiError                   |

## Produces

- application/json;charset=UTF-8

## Tags

- Documents

## Update the status of a user message

PUT /Cases/{caseId}/Documents/{documentId}/Messages/{id}/Metadata

## Description

Send again an already sent user message associated with an existing conversation of a document | (Available for following roles: ROLE\_REGULAR)

## Parameters

| Type                | Name                       | Description    | Schema   |
|---------------------|----------------------------|----------------|----------|
| caseId required     | The Id of the Case         | string         | Path     |
| documentId required | The Id of the Document     | string         | Path     |
| id required         | The id of the User Message | string         | Path     |
| body required       | The User Message status    | UserMessageDto | Body     |

## Responses

|   HTTP Code | Description                           | Schema   |
|-------------|---------------------------------------|----------|
|         500 | Cannot update the user message status | ApiError |

## Consumes

- application/json;charset=UTF-8

## Tags

- Documents

## Create a Subdocument

POST /Cases/{caseId}/Documents/{documentId}/Subdocuments

## Description

Create a Subdocument on a Document and return the saved subdocument metadata, including the validation status. | (Available for following roles: ROLE\_REGULAR)

## Parameters

| Type                                 | Name                              | Description          | Schema   |
|--------------------------------------|-----------------------------------|----------------------|----------|
| Path caseId required                 | The Id of the Case                | string               |          |
| Path documentId required             | The Id of the Document            | string               |          |
| Query relatedSubdo cumentId optional | The Id of the related Subdocument | string               |          |
| body required                        | The Subdocument content           | < string, object map | Body     |

## Responses

|   HTTP Code | Description               | Schema           |
|-------------|---------------------------|------------------|
|         200 | successful operation      | RESTSubdocumen t |
|         500 | Cannot create Subdocument | ApiError         |

## Consumes

- application/json;charset=UTF-8

## Produces

- application/json;charset=UTF-8

## Tags

- Documents

## Retrieve a list of subdocuments

## Description

Retrieve a list of subdocuments for a specified document on a specified case, with optional search criteria and pagination. | (Available for following roles: ROLE\_REGULAR)

## Parameters

| Type                     | Name                                                              | Description                                           | Schema                |
|--------------------------|-------------------------------------------------------------------|-------------------------------------------------------|-----------------------|
| Path caseId required     | The Id of the Case                                                | string                                                |                       |
| Path documentId required | The Id of the Document                                            | string                                                |                       |
| Query ment optional      | currentDocu Whether to retrieve subdocuments the current document | only from                                             | boolean               |
| Query                    | docTypes optional                                                 | The parent document types of the subdocuments         | < string array(multi) |
| Query                    | limit optional                                                    | Pagination limit                                      | integer (int32)       |
| Query                    | offset optional                                                   | Pagination offset                                     | integer (int32)       |
| Query                    | searchText optional                                               | Text that is going to be searched by                  | string                |
| Query                    | validationStat us optional                                        | The validation status that is going to be searched by | string                |

## Responses

|   HTTP Code | Description          | Schema               |
|-------------|----------------------|----------------------|
|         200 | successful operation | RESTSubdocumen tList |

|   HTTP Code | Description                               | Schema   |
|-------------|-------------------------------------------|----------|
|         500 | Error retrieving the list of subdocuments | ApiError |

## Produces

- application/json;charset=UTF-8

## Tags

- Documents

## Retrieve Subdocument

GET /Cases/{caseId}/Documents/{documentId}/Subdocuments/{id}

## Description

Retrieve Subdocument content | (Available for following roles: ROLE\_REGULAR)

## Parameters

| Type                | Name                      | Description   | Schema   |
|---------------------|---------------------------|---------------|----------|
| caseId required     | The Id of the Case        | string        | Path     |
| documentId required | The Id of the Document    | string        | Path     |
| id required         | The Id of the Subdocument | string        | Path     |

## Responses

|   HTTP Code | Description                 | Schema                 |
|-------------|-----------------------------|------------------------|
|         200 | successful operation        | < string, object > map |
|         500 | Cannot retrieve Subdocument | ApiError               |

## Produces

- application/json;charset=UTF-8

## Tags

- Documents

## Remove a Subdocument

DELETE /Cases/{caseId}/Documents/{documentId}/Subdocuments/{id}

## Description

Remove a Subdocument from a Document. | (Available for following roles: ROLE\_REGULAR)

## Parameters

| Type                | Name                      | Description   | Schema   |
|---------------------|---------------------------|---------------|----------|
| caseId required     | The id of the case        | string        | Path     |
| documentId required | The id of the document    | string        | Path     |
| id required         | The id of the subdocument | string        | Path     |

## Responses

|   HTTP Code | Description               | Schema   |
|-------------|---------------------------|----------|
|         500 | Cannot remove Subdocument | ApiError |

## Tags

- Documents

## Update a Subdocument

PUT /Cases/{caseId}/Documents/{documentId}/Subdocuments/{subdocumentId}

## Description

Update a Subdocument on a Document and return the saved subdocument metadata, including the validation status. | (Available for following roles: ROLE\_REGULAR)

## Parameters

| Type                         | Name                      | Description          | Schema   |
|------------------------------|---------------------------|----------------------|----------|
| Path caseId required         | The Id of the Case        | string               |          |
| Path documentId required     | The Id of the Document    | string               |          |
| Path subdocumentI d required | The Id of the Subdocument | string               |          |
| body required                | The Subdocument content   | < string, object map | Body     |

## Responses

|   HTTP Code | Description               | Schema           |
|-------------|---------------------------|------------------|
|         200 | successful operation      | RESTSubdocumen t |
|         500 | Cannot update Subdocument | ApiError         |

## Consumes

- application/json;charset=UTF-8

## Produces

- application/json;charset=UTF-8

## Tags

- Documents

## Submit attachment on a subdocument

## Description

Submit attachment on a subdocument, returns the attachment id | (Available for following roles: ROLE\_REGULAR)

## Parameters

| Type      | Name                    | Description                                                   | Schema   |
|-----------|-------------------------|---------------------------------------------------------------|----------|
| Path      | caseId required The     | Id of the case, on which the attachment belongs to            | string   |
| Path      | documentId required     | The Id of the Document, on which the attachment belongs to    | string   |
| Path      | subdocumentI d required | The Id of the Subdocument, on which the attachment belongs to | string   |
| FormDat a | file required           | The file to be attached                                       | file     |

## Responses

|   HTTP Code | Description                  | Schema        |
|-------------|------------------------------|---------------|
|         200 | successful operation         | RESTId        |
|         500 | Cannot submit the attachment | RESTException |

## Consumes

- multipart/form-data

## Produces

- application/json;charset=UTF-8

## Tags

- Attachments

## Retrieve attachment of a subdocument

## GET

/Cases/{caseId}/Documents/{documentId}/Subdocuments/{subdocumentId}/Attachments/{id}

## Description

Retrieves  the  attachment  coresponding  to  a  subdocument  of  a  case  by  its  id  |  (Available  for following roles: ROLE\_REGULAR)

## Parameters

| Type                         | Name                                                      | Description   | Schema   |
|------------------------------|-----------------------------------------------------------|---------------|----------|
| Path caseId required         | The Id of the case, on which the attachment belongs to    | string        |          |
| Path documentId required     | The Id of the Document, on which attachment belongs to    | the           | string   |
| Path id required             | The Id of the Attachment                                  | string        |          |
| Path subdocumentI d required | The Id of the Subdocument, on which attachment belongs to | the           | string   |

## Responses

|   HTTP Code | Description                    | Schema        |
|-------------|--------------------------------|---------------|
|         200 | successful operation           | string (byte) |
|         500 | Cannot retrieve the attachment | RESTException |

## Tags

- Attachments

## Delete attachment of a subdocument

## DELETE

/Cases/{caseId}/Documents/{documentId}/Subdocuments/{subdocumentId}/Attachments/{id}

## Description

Deletes the attachment specified by the case id, document id, subdocument id and attachment id | (Available for following roles: ROLE\_REGULAR)

## Parameters

| Type                         | Name                     | Description               | Schema   |
|------------------------------|--------------------------|---------------------------|----------|
| caseId required              | The Id of the Case       | string                    | Path     |
| documentId required          | The id of the document   | string                    | Path     |
| id required                  | The id of the attachment | string                    | Path     |
| Path subdocumentI d required |                          | The id of the subdocument | string   |

## Responses

|   HTTP Code | Description                  | Schema        |
|-------------|------------------------------|---------------|
|         500 | Cannot delete the attachment | RESTException |

## Tags

- Attachments

## Update the Medical Information flag of a subdocument attachment

PUT

/Cases/{caseId}/Documents/{documentId}/Subdocuments/{subdocumentId}/Attachments/{id}/M etadata

## Description

Update the Medical Information flag of a subdocument attachment | (Available for following roles: ROLE\_REGULAR)

## Parameters

| Type                     | Name                                                          | Description          | Schema   |
|--------------------------|---------------------------------------------------------------|----------------------|----------|
| Path caseId required     | The Id of the Case                                            | string               |          |
| Path documentId required | The Id of the Document                                        | string               |          |
| Path id required         | The Id of the Attachment                                      | string               |          |
| Path d required          | The Id of the Subdocument                                     | string               |          |
| body required            | The value of the medical information flag for this attachment | < string, object map | Body     |

## Responses

|   HTTP Code | Description                       | Schema        |
|-------------|-----------------------------------|---------------|
|         500 | Cannot update the attachment flag | RESTException |

## Tags

- Attachments

## Retrieve the Version of a Subdocument

```
GET /Cases/{caseId}/Documents/{documentId}/Subdocuments/{subdocumentId}/Versions/{versionI
```

d}

## Description

Retrieve  the  content  of  a  specific  version  of  a  Subdocument  |  (Available  for  following  roles: ROLE\_REGULAR)

## Parameters

| Type                    | Name                      | Description   | Schema   |
|-------------------------|---------------------------|---------------|----------|
| caseId required         | The Id of the Case        | string        | Path     |
| documentId required     | The Id of the Document    | string        | Path     |
| subdocumentI d required | The Id of the Subdocument | string        | Path     |
| versionId required      | The Id of the Version     | string        | Path     |

## Responses

|   HTTP Code | Description                                   | Schema                 |
|-------------|-----------------------------------------------|------------------------|
|         200 | successful operation                          | < string, object > map |
|         500 | Cannot retrive the version of the Subdocument | ApiError               |

## Produces

- application/json;charset=UTF-8

## Tags

- Documents

## Retrieve Thumbnail

GET /Cases/{caseId}/Documents/{documentId}/Thumbnail

## Description

Retrieves the Thumbnail of an existing SED/document. | (Available for following roles: ROLE\_REGULAR)

## Parameters

| Type   | Name                | Description            | Schema   |
|--------|---------------------|------------------------|----------|
| Path   | caseId required     | The Id of the Case     | string   |
| Path   | documentId required | The Id of the Document | string   |

## Responses

|   HTTP Code | Description          | Schema        |
|-------------|----------------------|---------------|
|         200 | successful operation | string (byte) |
|         500 | Cannot get Thumbnail | ApiError      |

## Produces

- application/octet-stream

## Tags

- Documents

## Retrieve Document Version

GET /Cases/{caseId}/Documents/{documentId}/Versions/{versionId}

## Description

Retrieves the content of a specific version of an existing SED/document. | (Available for following roles: ROLE\_REGULAR)

## Parameters

| Type   | Name                | Description            | Schema   |
|--------|---------------------|------------------------|----------|
| Path   | caseId required     | The Id of the Case     | string   |
| Path   | documentId required | The Id of the Document | string   |

| Type   | Name               | Description           | Schema   |
|--------|--------------------|-----------------------|----------|
| Path   | versionId required | The Id of the Version | string   |

## Responses

|   HTTP Code | Description                                 | Schema                 |
|-------------|---------------------------------------------|------------------------|
|         200 | successful operation                        | < string, object > map |
|         500 | Cannot retrieve the Version of the Document | ApiError               |

## Produces

- application/json;charset=UTF-8

## Tags

- Documents

## Retrieve Document

GET /Cases/{caseId}/Documents/{id}

## Description

Retrieves a document/SED specified by his case and document ids. | (Available for following roles: ROLE\_REGULAR)

## Parameters

| Type   | Name            | Description            | Schema   |
|--------|-----------------|------------------------|----------|
| Path   | caseId required | The Id of the Case     | string   |
| Path   | id required     | The Id of the Document | string   |

## Responses

|   HTTP Code | Description              | Schema                 |
|-------------|--------------------------|------------------------|
|         200 | successful operation     | < string, object > map |
|         500 | Cannot retrieve Document | ApiError               |

## Produces

- application/json;charset=UTF-8

## Tags

- Documents

## Update case metadata sensitive flag

PUT /Cases/{caseId}/Metadata/Sensitive

## Description

Update the metadata flag 'sensitive' of the Case | (Available for following roles: ROLE\_REGULAR)

## Parameters

| Type   | Name                   | Description                   | Schema   |
|--------|------------------------|-------------------------------|----------|
| Path   | caseId required        | The Id of the Case            | string   |
| Query  | caseSensitive required | The flag if case is sensitive | boolean  |

## Responses

|   HTTP Code | Description                       | Schema   |
|-------------|-----------------------------------|----------|
|         500 | Cannot update case sensitive flag | ApiError |

## Tags

- Cases

## Get a case

GET /Cases/{id}

## Description

Retrieves the case information given its id | (Available for following roles: ROLE\_REGULAR)

## Parameters

| Type   | Name        | Description        | Schema   |
|--------|-------------|--------------------|----------|
| Path   | id required | The Id of the Case | string   |

## Responses

|   HTTP Code | Description          | Schema         |
|-------------|----------------------|----------------|
|         200 | successful operation | CaseRevisedDto |
|         500 | Cannot get case      | ApiError       |

## Produces

- application/json;charset=UTF-8

## Tags

- Cases

## Retrieving the case archiving options

GET /Cases/{id}/ArchivingOptions

## Description

Retrieve archival parameter details for a case (if archived, archive location, closed/removed date, estimated archival date, actual archival date, estimated deletion date - depending on the case status some  of  the  aforementioned  parameters  will  be  N/A  or  NULL).  |  (Available  for  following  roles: ROLE\_REGULAR)

## Parameters

| Type   | Name        | Description        | Schema   |
|--------|-------------|--------------------|----------|
| Path   | id required | The Id of the Case | string   |

## Responses

|   HTTP Code | Description                           | Schema               |
|-------------|---------------------------------------|----------------------|
|         200 | successful operation                  | ArchivingOptions Dto |
|         500 | Cannot get the case archiving options | ApiError             |

## Produces

- application/json;charset=UTF-8

## Tags

- Cases

## Archive/Unarchive a case

PUT /Cases/{id}/ArchivingOptions

## Description

Archive/Unarchive a case - Archive / Unarchive a case. Depending of the case status it will be either archived either unarchived (the 'archived' field -Boolean - in the archiving options states if the case is archived or not) | (Available for following roles: ROLE\_REGULAR)

## Parameters

| Type   | Name        | Description        | Schema   |
|--------|-------------|--------------------|----------|
| Path   | id required | The Id of the Case | string   |

## Responses

|   HTTP Code | Description                       | Schema   |
|-------------|-----------------------------------|----------|
|         500 | Cannot archive/unarchive the case | ApiError |

## Produces

- application/json;charset=UTF-8

## Tags

- Cases

## Get case assignments

GET /Cases/{id}/Assignment

## Description

Retrieves case assignments (roles with assigned users and groups) of the specified case | (Available for following roles: ROLE\_REGULAR)

## Parameters

| Type   | Name        | Description        | Schema   |
|--------|-------------|--------------------|----------|
| Path   | id required | The Id of the Case | string   |

## Responses

|   HTTP Code | Description                | Schema                    |
|-------------|----------------------------|---------------------------|
|         200 | successful operation       | CaseAssignmentR evisedDto |
|         500 | Cannot get case assigment: | ApiError                  |

## Produces

- application/json;charset=UTF-8

## Tags

- Cases

## Get case hash code

GET /Cases/{id}/HashCode

## Description

Get the hash code of a specified case. Used for figuering out if the case is in ready state. | (Available for following roles: ROLE\_REGULAR)

## Parameters

| Type   | Name        | Description        | Schema   |
|--------|-------------|--------------------|----------|
| Path   | id required | The Id of the Case | string   |

## Responses

|   HTTP Code | Description          | Schema          |
|-------------|----------------------|-----------------|
|         200 | successful operation | integer (int32) |
|         500 | Cannot get hash code | ApiError        |

## Tags

- Cases

## Execute Check Buckets

POST /CheckBuckets

## Description

Executes Check Buckets | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name          | Description             | Schema         |
|--------|---------------|-------------------------|----------------|
| Body   | body required | Check Bucket to Execute | CheckBucketDto |

## Responses

|   HTTP Code | Description                   | Schema        |
|-------------|-------------------------------|---------------|
|         200 | successful operation          | RESTId        |
|         500 | Error Executing Check Buckets | RESTException |

## Consumes

- application/json

## Produces

- application/json

## Tags

- CheckBuckets

## Get all Check Buckets

GET /CheckBuckets

## Description

Retrieves all Check Buckets | (Available for following roles: ROLE\_ADMIN)

## Responses

|   HTTP Code | Description                        | Schema                   |
|-------------|------------------------------------|--------------------------|
|         200 | successful operation               | < CheckBucketDto > array |
|         500 | Error retrieving all Check Buckets | RESTException            |

## Produces

- application/json

## Tags

- CheckBuckets

## Get Check Bucket Executor

GET /CheckBuckets/{id}

## Description

Retrieves Check Bucket Executor by Id | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name        | Description                | Schema   |
|--------|-------------|----------------------------|----------|
| Path   | id required | The Id of the check bucket | string   |

## Responses

|   HTTP Code | Description                       | Schema         |
|-------------|-----------------------------------|----------------|
|         200 | successful operation              | CheckBucketDto |
|         500 | Error retrieving the Check Bucket | RESTException  |

## Produces

- application/json

## Tags

- CheckBuckets

## Update check definition

POST /CheckDefinitions

CAUTION

operation.deprecated

## Description

Updates a check definition | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name          | Description                    | Schema             |
|--------|---------------|--------------------------------|--------------------|
| Body   | body required | The Check Definition To Update | CheckDefinitionDto |

## Responses

|   HTTP Code | Description                       | Schema     |
|-------------|-----------------------------------|------------|
|         500 | Error updating a check definition | No Content |

## Consumes

- application/json

## Tags

- CheckDefinitions

## Get all check definitions

GET /CheckDefinitions

## Description

Retrieves all check definitions | (Available for following roles: ROLE\_ADMIN)

## Responses

|   HTTP Code | Description                       | Schema                        |
|-------------|-----------------------------------|-------------------------------|
|         200 | successful operation              | < CheckDefinitionDt o > array |
|         500 | Cannot retrieve check definitions | No Content                    |

## Produces

- application/json

## Tags

- CheckDefinitions

## Saves case counter settings.

PUT /Configurations/CaseCounterSettings

## Description

Saves the settings to control how a business ID of a case is generated. Case counter Settings are independent for each Tenant. | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name          | Schema                 |
|--------|---------------|------------------------|
| Body   | body optional | CaseCounterSettingsDto |

## Responses

|   HTTP Code | Description                        | Schema        |
|-------------|------------------------------------|---------------|
|         500 | Cannot save case counter settings. | RESTException |

## Produces

- application/json

## Tags

- Configurations

## Get case counter settings.

GET /Configurations/CaseCounterSettings/{institutionId}

## Description

Retrieves the settings to control how a business ID of a case is generated. | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name                   | Description                       | Schema   |
|--------|------------------------|-----------------------------------|----------|
| Path   | institutionId required | The institution Id to filter with | string   |

## Responses

|   HTTP Code | Description                                | Schema                  |
|-------------|--------------------------------------------|-------------------------|
|         200 | successful operation                       | CaseCounterSettin gsDto |
|         500 | Cannot retrieve the case counter settings. | RESTException           |

## Produces

- application/json

## Tags

- Configurations

## Saves LDAP connection settings.

PUT /Configurations/LdapConnectionSettings

## Description

Saves the settings to control LDAP connection. | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name          | Schema                    |
|--------|---------------|---------------------------|
| Body   | body optional | LdapConnectionSettingsDto |

## Responses

|   HTTP Code | Description                           | Schema        |
|-------------|---------------------------------------|---------------|
|         500 | Cannot save LDAP connection settings. | RESTException |

## Produces

- application/json;charset=UTF-8

## Tags

- Configurations

## Get LDAP connection settings.

GET /Configurations/LdapConnectionSettings/{institutionId}

## Description

Retrieves the LDAP connection settings. | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name                   | Description                       | Schema   |
|--------|------------------------|-----------------------------------|----------|
| Path   | institutionId required | The institution Id to filter with | string   |

## Responses

|   HTTP Code | Description                                   | Schema                     |
|-------------|-----------------------------------------------|----------------------------|
|         200 | successful operation                          | LdapConnectionSe ttingsDto |
|         404 | The LDAP connection settings were not found   | RESTException              |
|         500 | Cannot retrieve the LDAP connection settings. | RESTException              |

## Produces

- application/json;charset=UTF-8

## Tags

- Configurations

## Get LDAP group parameters keys.

GET /Configurations/LdapGroupParametersKeys

## Description

Retrieves the LDAP group parameters keys. | (Available for following roles: ROLE\_ADMIN)

## Responses

|   HTTP Code | Description                                     | Schema           |
|-------------|-------------------------------------------------|------------------|
|         200 | successful operation                            | < string > array |
|         500 | Cannot retrieve the LDAP group parameters keys. | RESTException    |

## Produces

- application/json;charset=UTF-8

## Tags

- Configurations

## Saves LDAP group parameters mapping.

PUT /Configurations/LdapGroupParametersMapping

## Description

Saves  the  settings  to  control  LDAP  group  parameters  mapping.  |  (Available  for  following  roles: ROLE\_ADMIN)

## Parameters

| Type   | Name          | Schema                        |
|--------|---------------|-------------------------------|
| Body   | body optional | LdapGroupParametersMappingDto |

## Responses

|   HTTP Code | Description                                | Schema        |
|-------------|--------------------------------------------|---------------|
|         500 | Cannot save LDAP group parameters mapping. | RESTException |

## Produces

- application/json;charset=UTF-8

## Tags

- Configurations

## Get LDAP group parameters mapping.

GET /Configurations/LdapGroupParametersMapping/{institutionId}

## Description

Retrieves the LDAP group parameters mapping. | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name                   | Description                       | Schema   |
|--------|------------------------|-----------------------------------|----------|
| Path   | institutionId required | The institution Id to filter with | string   |

## Responses

|   HTTP Code | Description                                        | Schema                         |
|-------------|----------------------------------------------------|--------------------------------|
|         200 | successful operation                               | LdapGroupParam etersMappingDto |
|         404 | The LDAP group parameters mapping not found.       | RESTException                  |
|         500 | Cannot retrieve the LDAP group parameters mapping. | RESTException                  |

## Produces

- application/json;charset=UTF-8

## Tags

- Configurations

## Get LDAP user parameters keys.

GET /Configurations/LdapUserParametersKeys

## Description

Retrieves the LDAP user parameters keys. | (Available for following roles: ROLE\_ADMIN)

## Responses

|   HTTP Code | Description                                    | Schema           |
|-------------|------------------------------------------------|------------------|
|         200 | successful operation                           | < string > array |
|         500 | Cannot retrieve the LDAP user parameters keys. | RESTException    |

## Produces

- application/json;charset=UTF-8

## Tags

- Configurations

## Saves LDAP user parameters mapping.

PUT /Configurations/LdapUserParametersMapping

## Description

Saves  the  settings  to  control  LDAP  user  parameters  mapping.  |  (Available  for  following  roles: ROLE\_ADMIN)

## Parameters

| Type   | Name          | Schema                       |
|--------|---------------|------------------------------|
| Body   | body optional | LdapUserParametersMappingDto |

## Responses

|   HTTP Code | Description                               | Schema        |
|-------------|-------------------------------------------|---------------|
|         500 | Cannot save LDAP user parameters mapping. | RESTException |

## Produces

- application/json;charset=UTF-8

## Tags

- Configurations

## Get LDAP user parameters mapping.

GET /Configurations/LdapUserParametersMapping/{institutionId}

## Description

Retrieves the LDAP user parameters mapping. | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name                   | Description                       | Schema   |
|--------|------------------------|-----------------------------------|----------|
| Path   | institutionId required | The institution Id to filter with | string   |

## Responses

|   HTTP Code | Description                                       | Schema                        |
|-------------|---------------------------------------------------|-------------------------------|
|         200 | successful operation                              | LdapUserParamet ersMappingDto |
|         404 | The LDAP user parameters mapping not found.       | RESTException                 |
|         500 | Cannot retrieve the LDAP user parameters mapping. | RESTException                 |

## Produces

- application/json;charset=UTF-8

## Tags

- Configurations

## Update Disk Resources

PUT /DiskResources/{resourceId}

## Description

Updates disk resources from a resource description file(only organisations are supported for now) | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type                     | Name                                           | Description Schema   |
|--------------------------|------------------------------------------------|----------------------|
| Path resourceId required | The name/id of the resource                    | string               |
| Body body required       | The path to the disk file containing resources | the DiskFileInfoDto  |

## Responses

|   HTTP Code | Description                   | Schema        |
|-------------|-------------------------------|---------------|
|         500 | Error Updating Disk Resources | RESTException |

## Produces

- application/json;charset=UTF-8

## Tags

- Resources

## Search entities

| GET /Entities   |
|-----------------|

## Description

Searches entities by entity type, flow type and free text. The result list is limited to 10 results. | (Available for following roles: ROLE\_REGULAR,ROLE\_ADMIN)

## Parameters

| Type                   | Name                                                                                      | Description   | Schema   |
|------------------------|-------------------------------------------------------------------------------------------|---------------|----------|
| accessPointId optional | If only Entities of the same Access Point should be returned                              | string        | Query    |
| appRole optional       | PO, CP                                                                                    | string        | Query    |
| entityType required    | The type of the entity(only 'organisation' suported for now                               | is string     | Query    |
| filterTenants optional | If entities of the same Access Point should not contain the installed Tenant Institutions | boolean       | Query    |
| flowType optional      | The process definition name                                                               | string        | Query    |
| searchText optional    | The free text to search for                                                               | string        | Query    |

## Responses

|   HTTP Code | Description              | Schema                    |
|-------------|--------------------------|---------------------------|
|         200 | successful operation     | < OrganisationDto > array |
|         500 | Error filtering entities | ApiError                  |

## Produces

- application/json;charset=UTF-8

## Tags

- Entities

## Search entities by parameters

GET /Entities/searchByParams

## Description

Searches entities by various parameters like sectors, validity, BUCs, etc… | (Available for following roles: ROLE\_REGULAR,ROLE\_ADMIN)

## Parameters

| Type   | Name                      | Description                                                                 | Schema                                                                                                                                |
|--------|---------------------------|-----------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------|
| Query  | applicationRo le optional | Application role of the BUC competence, which the institution must support. | enum (PO, CP)                                                                                                                         |
| Query  | bucType optional          | Type of the BUC, which the institution must support.                        | string                                                                                                                                |
| Query  | countryCode required      | Country code.                                                               | enum (AT, BE, BG, CH, CY, CZ, DE, DK, EE, EL, ES, FI, FR, HR, HU, IS, IE, IT, LV, LI, LT, LU, MT, NL, NO, PL, PT, RO, SE, SI, SK, UK) |
| Query  | from optional             | Pagination parameter to specify the starting point.                         | integer (int32)                                                                                                                       |
| Query  | sector optional           | Name of the sector.                                                         | string                                                                                                                                |
| Query  | size optional             | Number of entries returned from the starting position. Defaults to 50.      | integer (int32)                                                                                                                       |
| Query  | validFrom optional        | Minimum start validity of the BUC competence.                               | string (date-time)                                                                                                                    |
| Query  | validTo optional          | Maximum end validity of the BUC competence.                                 | string (date-time)                                                                                                                    |

## Responses

|   HTTP Code | Description              | Schema                    |
|-------------|--------------------------|---------------------------|
|         200 | successful operation     | < OrganisationDto > array |
|         500 | Error filtering entities | ApiError                  |

## Produces

- application/json;charset=UTF-8

## Tags

- Entities

## Get entity by id

GET /Entities/{id}

## Description

Retrieves a sinle entity given its id | (Available for following roles: ROLE\_REGULAR,ROLE\_ADMIN)

## Parameters

| Type   | Name        | Description          | Schema   |
|--------|-------------|----------------------|----------|
| Path   | id required | The Id of the entity | string   |

## Responses

|   HTTP Code | Description                 | Schema          |
|-------------|-----------------------------|-----------------|
|         200 | successful operation        | OrganisationDto |
|         500 | Error retrieving the entity | ApiError        |

## Produces

- application/json;charset=UTF-8

## Tags

- Entities

## Uploads a file to the server

| POST /Files   |
|---------------|

## Description

Uploads a file to the server and returns its full path on the server | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type      | Name          | Description             | Schema   |
|-----------|---------------|-------------------------|----------|
| FormDat a | file required | The file to be attached | file     |

## Responses

|   HTTP Code | Description                          | Schema          |
|-------------|--------------------------------------|-----------------|
|         200 | successful operation                 | DiskFileInfoDto |
|         500 | Cannot upload the file to the server | RESTException   |

## Consumes

- multipart/form-data

## Produces

- application/json;charset=UTF-8

## Tags

- Files

## Get the portal form metadata for a specific SED and version

## Description

Get  the  portal  form  metadata  for  a  specific  SED  and  version  |  (Available  for  following  roles: ROLE\_REGULAR,ROLE\_ADMIN)

## Parameters

| Type   | Name             | Schema   |
|--------|------------------|----------|
| Query  | sedType required | string   |
| Query  | version required | string   |

## Responses

|   HTTP Code | Description                    | Schema   |
|-------------|--------------------------------|----------|
|         200 | successful operation           | string   |
|         404 | Portal form metadata not found | ApiError |

## Produces

- application/json;charset=UTF-8

## Tags

- Forms

## Get the portal forms messages for a specific language

GET /Forms/Translations

## Description

Get the portal forms messages for a specific language | (Available for following roles: ROLE\_REGULAR,ROLE\_ADMIN)

## Parameters

| Type   | Name                  | Schema   |
|--------|-----------------------|----------|
| Query  | languageCode required | string   |

## Responses

|   HTTP Code | Description                     | Schema   |
|-------------|---------------------------------|----------|
|         200 | successful operation            | string   |
|         404 | Portal forms messages not found | ApiError |

## Produces

- application/json;charset=UTF-8

## Tags

- Forms

## Create New group

POST /Identity/Group

## Description

Creates a Group and returns its id | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name          | Description    | Schema   |
|--------|---------------|----------------|----------|
| Body   | body required | The Group data | GroupDto |

## Responses

|   HTTP Code | Description          | Schema   |
|-------------|----------------------|----------|
|         200 | successful operation | RESTId   |

|   HTTP Code | Description                | Schema   |
|-------------|----------------------------|----------|
|         500 | Error creating a new group | ApiError |

## Consumes

- application/json;charset=UTF-8

## Produces

- application/json;charset=UTF-8

## Tags

- Identity

## Get Group details

GET /Identity/Group/{groupId}

## Description

Retrieves a Group given its id | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name             | Description   | Schema   |
|--------|------------------|---------------|----------|
| Path   | groupId required | The Group Id  | string   |

## Responses

|   HTTP Code | Description          | Schema   |
|-------------|----------------------|----------|
|         200 | successful operation | GroupDto |
|         500 | Cannot get group     | ApiError |

## Produces

- application/json;charset=UTF-8

## Tags

- Identity

## Update Group

PUT /Identity/Group/{groupId}

## Description

Updates a Group properties | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name             | Description    | Schema   |
|--------|------------------|----------------|----------|
| Path   | groupId required | The Group Id   | string   |
| Body   | body required    | The Group data | GroupDto |

## Responses

|   HTTP Code | Description            | Schema   |
|-------------|------------------------|----------|
|         500 | Error updating a group | ApiError |

## Consumes

- application/json;charset=UTF-8

## Produces

- application/json;charset=UTF-8

## Tags

- Identity

## Delete Group

DELETE /Identity/Group/{groupId}

## Description

Deletes a Group given its id | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name             | Description   | Schema   |
|--------|------------------|---------------|----------|
| Path   | groupId required | The Group Id  | string   |

## Responses

|   HTTP Code | Description              | Schema   |
|-------------|--------------------------|----------|
|         200 | successful operation     | string   |
|         404 | Cannot delete the group. | ApiError |
|         500 | Cannot delete the group. | ApiError |

## Produces

- application/json;charset=UTF-8

## Tags

- Identity

## Get groups

GET /Identity/Groups

## Description

Retrieves all groups (evtl. of a parent Group) | (Available for following roles: ROLE\_REGULAR,ROLE\_ADMIN)

## Parameters

| Type   | Name          | Description                               | Schema          |
|--------|---------------|-------------------------------------------|-----------------|
| Query  | from optional | Pagination parameter to start from index. | integer (int32) |

| Type                   | Name                                           | Description   | Schema          |
|------------------------|------------------------------------------------|---------------|-----------------|
| institutionId required | The institution Id to filter with              | string        | Query           |
| Query d                | The parent Group Id                            |               | string          |
| Query size optional    | Pagination parameter do specify the size page. | of            | integer (int32) |

## Responses

|   HTTP Code | Description          | Schema           |
|-------------|----------------------|------------------|
|         200 | successful operation | < GroupDto array |
|         500 | Cannot get groups    | ApiError         |

## Produces

- application/json;charset=UTF-8

## Tags

- Identity

## Registers a new user

POST /Identity/Registration

## Description

Register  new  user  (or  an  authenticated  one  from  an  external  source)  |  (Available  for  following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name          | Description   | Schema   |
|--------|---------------|---------------|----------|
| Body   | body required | The User data | UserDto  |

## Responses

|   HTTP Code | Description              | Schema   |
|-------------|--------------------------|----------|
|         200 | successful operation     | RESTId   |
|         500 | Error registering a user | ApiError |

## Consumes

- application/json;charset=UTF-8

## Tags

- Identity

## Get the roles

GET /Identity/Roles

## Description

Get all the roles | (Available for following roles: ROLE\_ADMIN)

## Responses

|   HTTP Code | Description          | Schema                                                                                                       |
|-------------|----------------------|--------------------------------------------------------------------------------------------------------------|
|         200 | successful operation | < enum (SUPERVISOR, AUTHORIZED_CLE RK, UNAUTHORIZED_ CLERK, AUDITOR, VIEWER, MEDICAL, VIP, EVERYONE) > array |
|         500 | Cannot get the roles | ApiError                                                                                                     |

## Produces

- application/json;charset=UTF-8

## Tags

- Identity

## Create a new user

POST /Identity/User

## Description

Creates a User and returns its id | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name          | Description   | Schema   |
|--------|---------------|---------------|----------|
| Body   | body required | The User data | UserDto  |

## Responses

|   HTTP Code | Description               | Schema   |
|-------------|---------------------------|----------|
|         200 | successful operation      | RESTId   |
|         500 | Error creating a new user | ApiError |

## Consumes

- application/json;charset=UTF-8

## Produces

- application/json;charset=UTF-8

## Tags

- Identity

## Update the current user's password

PUT /Identity/User/Password

## Description

Updates the current user's password | (Available for following roles: ROLE\_REGULAR,ROLE\_ADMIN)

## Parameters

| Type   | Name                           | Schema          |
|--------|--------------------------------|-----------------|
| Body   | The new user password required | UserPasswordDto |

## Responses

|   HTTP Code | Description              | Schema   |
|-------------|--------------------------|----------|
|         500 | Error registering a user | ApiError |

## Consumes

- application/json;charset=UTF-8

## Tags

- Identity

## Get user details by Id or Name

GET /Identity/User/{userId}

## Description

Retrieves a User given its id | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name            | Description   | Schema   |
|--------|-----------------|---------------|----------|
| Path   | userId required | The User Id   | string   |

## Responses

|   HTTP Code | Description          | Schema   |
|-------------|----------------------|----------|
|         200 | successful operation | UserDto  |
|         500 | Cannot get user      | ApiError |

## Produces

- application/json;charset=UTF-8

## Tags

- Identity

## Update User properties

PUT /Identity/User/{userId}

## Description

Updates a User's properties | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name            | Description                | Schema   |
|--------|-----------------|----------------------------|----------|
| Path   | userId required | The id of the User Message | string   |
| Body   | body required   | The User data              | UserDto  |

## Responses

|   HTTP Code | Description           | Schema   |
|-------------|-----------------------|----------|
|         200 | successful operation  | UserDto  |
|         500 | Error updating a user | ApiError |

## Consumes

- application/json;charset=UTF-8

## Tags

- Identity

## Deletes a user by id

DELETE /Identity/User/{userId}

## Description

Deletes a user with the specified id | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name            | Description   | Schema   |
|--------|-----------------|---------------|----------|
| Path   | userId required | The User Id   | string   |

## Responses

|   HTTP Code | Description            | Schema   |
|-------------|------------------------|----------|
|         500 | Cannot delete the user | ApiError |

## Tags

- Identity

## Get all users

GET /Identity/Users

## Description

Retrieves all users | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name          | Description                               | Schema          |
|--------|---------------|-------------------------------------------|-----------------|
| Query  | from optional | Pagination parameter to start from index. | integer (int32) |

| Type                   | Name                                           | Description   | Schema        |
|------------------------|------------------------------------------------|---------------|---------------|
| institutionId required | The institution Id to filter with              | string        | Query         |
| Query sion optional    | The free text to search for                    | string        |               |
| size optional          | Pagination parameter do specify the size page. | of integer    | Query (int32) |

## Responses

|   HTTP Code | Description          | Schema            |
|-------------|----------------------|-------------------|
|         200 | successful operation | < UserDto > array |
|         500 | Cannot get users     | ApiError          |

## Produces

- application/json;charset=UTF-8

## Tags

- Identity

## Retrieves a list of users based on a group

GET /Identity/Users/Group

## Description

Retrieves a list of users based on a group | (Available for following roles: ROLE\_ADMIN,ROLE\_REGULAR)

## Parameters

| Type   | Name          | Description                               | Schema          |
|--------|---------------|-------------------------------------------|-----------------|
| Query  | from required | Pagination parameter to start from index. | integer (int32) |

| Type                    | Name                                                               | Description   | Schema   |
|-------------------------|--------------------------------------------------------------------|---------------|----------|
| includeAdmin s optional | Specifies if the admin users should also be list. Default is false | boolean       | Query    |
| Query d                 | The parent User Group Id                                           | string        |          |
| Query size required     | Pagination parameter do specify the size page.                     | of integer    | (int32)  |

## Responses

|   HTTP Code | Description                       | Schema            |
|-------------|-----------------------------------|-------------------|
|         200 | successful operation              | < UserDto > array |
|         500 | Cannot get users based on a group | ApiError          |

## Produces

- application/json;charset=UTF-8

## Tags

- Identity

## Add a private certificate

POST /Keystores/BusinessPrivate

## Description

Add a private certificate | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name                 | Description        | Schema          |
|--------|----------------------|--------------------|-----------------|
| Body   | certificate required | Certificate to Add | RESTCertificate |

## Responses

|   HTTP Code | Description                             | Schema        |
|-------------|-----------------------------------------|---------------|
|         500 | Error when adding a private certificate | RESTException |

## Consumes

- application/json;charset=UTF-8

## Tags

- Keystores

## Delete a private certificate

DELETE /Keystores/BusinessPrivate/{alias}

## Description

Delete a private certificate | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name           | Description           | Schema   |
|--------|----------------|-----------------------|----------|
| Path   | alias required | The certificate alias | string   |

## Responses

|   HTTP Code | Description                               | Schema            |
|-------------|-------------------------------------------|-------------------|
|         200 | successful operation                      | RESTKeystoreAlias |
|         500 | Error when deleting a private certificate | RESTException     |

## Produces

- application/json;charset=UTF-8

## Tags

- Keystores

## Add a private certificate

POST /Keystores/MSGprivate

## Description

Add a private certificate | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name                 | Description        | Schema          |
|--------|----------------------|--------------------|-----------------|
| Body   | certificate required | Certificate to Add | RESTCertificate |

## Responses

|   HTTP Code | Description                             | Schema        |
|-------------|-----------------------------------------|---------------|
|         500 | Error when adding a private certificate | RESTException |

## Consumes

- application/json;charset=UTF-8

## Tags

- Keystores

## Delete a private certificate

DELETE /Keystores/MSGprivate/{alias}

## Description

Delete a private certificate | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name           | Description           | Schema   |
|--------|----------------|-----------------------|----------|
| Path   | alias required | The certificate alias | string   |

## Responses

|   HTTP Code | Description                               | Schema            |
|-------------|-------------------------------------------|-------------------|
|         200 | successful operation                      | RESTKeystoreAlias |
|         500 | Error when deleting a private certificate | RESTException     |

## Produces

- application/json;charset=UTF-8

## Tags

- Keystores

## Add a public certificate

POST /Keystores/MSGpublic

## Description

Add a public certificate | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name                 | Description        | Schema          |
|--------|----------------------|--------------------|-----------------|
| Body   | certificate required | Certificate to Add | RESTCertificate |

## Responses

|   HTTP Code | Description                            | Schema        |
|-------------|----------------------------------------|---------------|
|         500 | Error when adding a public certificate | RESTException |

## Consumes

- application/json;charset=UTF-8

## Tags

- Keystores

## Delete a public certificate

DELETE /Keystores/MSGpublic/{alias}

## Description

Delete a public certificate | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name           | Description           | Schema   |
|--------|----------------|-----------------------|----------|
| Path   | alias required | The certificate alias | string   |

## Responses

|   HTTP Code | Description                              | Schema            |
|-------------|------------------------------------------|-------------------|
|         200 | successful operation                     | RESTKeystoreAlias |
|         500 | Error when deleting a public certificate | RESTException     |

## Produces

- application/json;charset=UTF-8

## Tags

- Keystores

## Add a TLS private certificate

POST /Keystores/TLSprivate

## Description

Add a TLS private certificate | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name                 | Description        | Schema          |
|--------|----------------------|--------------------|-----------------|
| Body   | certificate required | Certificate to Add | RESTCertificate |

## Responses

|   HTTP Code | Description                                 | Schema        |
|-------------|---------------------------------------------|---------------|
|         500 | Error when adding a TLS private certificate | RESTException |

## Consumes

- application/json;charset=UTF-8

## Tags

- Keystores

## Delete a TLS private certificate

DELETE /Keystores/TLSprivate/{alias}

## Description

Delete a TLS private certificate | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name           | Description           | Schema   |
|--------|----------------|-----------------------|----------|
| Path   | alias required | The certificate alias | string   |

## Responses

|   HTTP Code | Description                               | Schema            |
|-------------|-------------------------------------------|-------------------|
|         200 | successful operation                      | RESTKeystoreAlias |
|         500 | Error when deleting a private certificate | RESTException     |

## Produces

- application/json;charset=UTF-8

## Tags

- Keystores

## Add a TLS public certificate

POST /Keystores/TLSpublic

## Description

Add a TLS public certificate | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name                 | Description        | Schema          |
|--------|----------------------|--------------------|-----------------|
| Body   | certificate required | Certificate to Add | RESTCertificate |

## Responses

|   HTTP Code | Description                                | Schema        |
|-------------|--------------------------------------------|---------------|
|         500 | Error when adding a TLS public certificate | RESTException |

## Consumes

- application/json;charset=UTF-8

## Tags

- Keystores

## Delete a TLS public certificate

DELETE /Keystores/TLSpublic/{alias}

## Description

Delete a TLS public certificate | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name           | Description           | Schema   |
|--------|----------------|-----------------------|----------|
| Path   | alias required | The certificate alias | string   |

## Responses

|   HTTP Code | Description                                  | Schema            |
|-------------|----------------------------------------------|-------------------|
|         200 | successful operation                         | RESTKeystoreAlias |
|         500 | Error when deleting a TLS public certificate | RESTException     |

## Produces

- application/json;charset=UTF-8

## Tags

- Keystores

## Update the business key password

POST /Keystores/UpdateBusinessAliasPassword

## Description

Update the business key password | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name          | Schema                         |
|--------|---------------|--------------------------------|
| Body   | body required | CLIENTBusinessKeyStorePassword |

## Responses

|   HTTP Code | Description                          | Schema        |
|-------------|--------------------------------------|---------------|
|         500 | Cannot update the business key alias | RESTException |

## Consumes

- application/json;charset=UTF-8

## Tags

- Keystores

## Get notification details

GET /Notifications

## Description

Retrieves the notification details for the specified date and/or case id and/or notification ids. There are3 accepted combinations of filter criteria and the order of evaluation is exactly like following: * Date and case id are provided* Only date is provided* Date and Notification id list is provided

If  there  is  not  notification  that  meets  the  criteria,  an  empty  response  is  provided.  If  other combination of filter criteria is provided, an error is returned (described bellow). | (Available for following roles: ROLE\_REGULAR,ROLE\_ADMIN)

## Parameters

| Type                      | Name                     | Description           | Schema   |
|---------------------------|--------------------------|-----------------------|----------|
| caseId optional           | The Id of the Case       | string                | Query    |
| date optional             | The date of notification | string                | Query    |
| notificationId s optional | Notification ids         | < string array(multi) | Query    |

## Responses

|   HTTP Code | Description                              | Schema                    |
|-------------|------------------------------------------|---------------------------|
|         200 | successful operation                     | < NotificationDto > array |
|         500 | Error in receiving notifications details | ApiError                  |

## Produces

- application/json;charset=UTF-8

## Tags

- Notifications

## Get consolidated summary

GET /Notifications/ConsolidatedSummary

## Description

Retrieves  the  number  of  unread,  error,  warning  and  information  notifications.  If  a  non-existing case  id  is  provided,  the  response  will  be  an  empty  json.  |  (Available  for  following  roles: ROLE\_REGULAR,ROLE\_ADMIN)

## Parameters

| Type   | Name            | Description        | Schema   |
|--------|-----------------|--------------------|----------|
| Query  | caseId optional | The Id of the Case | string   |

## Responses

|   HTTP Code | Description                                              | Schema                                          |
|-------------|----------------------------------------------------------|-------------------------------------------------|
|         200 | successful operation                                     | < NotificationsCons olidatedSummary Dto > array |
|         500 | Error in receiving the notification consolidated summary | ApiError                                        |

## Produces

- application/json;charset=UTF-8

## Tags

- Notifications

## Get notification summary

GET /Notifications/Summary

## Description

Retrieves the list of ids for unread, error, warning and information notifications | (Available for following roles: ROLE\_REGULAR,ROLE\_ADMIN)

## Parameters

| Type   | Name            | Description        | Schema   |
|--------|-----------------|--------------------|----------|
| Query  | caseId optional | The Id of the Case | string   |

## Responses

|   HTTP Code | Description                                 | Schema                   |
|-------------|---------------------------------------------|--------------------------|
|         200 | successful operation                        | NotificationsSum maryDto |
|         500 | Error in receiving the notification summary | ApiError                 |

## Produces

- application/json;charset=UTF-8

## Tags

- Notifications

## Get notification time slots

| GET   | /Notifications/TimeSlots   |
|-------|----------------------------|

## Description

Retrieves the notification time slots (days and number of notifications on that day) for a case or for all. | (Available for following roles: ROLE\_REGULAR,ROLE\_ADMIN)

## Parameters

| Type   | Name            | Description        | Schema   |
|--------|-----------------|--------------------|----------|
| Query  | caseId optional | The Id of the Case | string   |

## Responses

|   HTTP Code | Description                       | Schema                              |
|-------------|-----------------------------------|-------------------------------------|
|         200 | successful operation              | < NotificationsTime SlotDto > array |
|         500 | Error in receiving the time slots | ApiError                            |

## Produces

- application/json;charset=UTF-8

## Tags

- Notifications

## Update a notification

PUT /Notifications/{id}

## Description

Updates  a  notification,  namely  the  suppress  and/or  isRead  properties.  |  (Available  for  following roles: ROLE\_REGULAR,ROLE\_ADMIN)

## Parameters

| Type   | Name                              | Description         | Schema                  |
|--------|-----------------------------------|---------------------|-------------------------|
| Path   | id required                       | The notification id | string                  |
| Body   | body required The notification to | update              | NotificationRevised Dto |

## Responses

|   HTTP Code | Description                             | Schema   |
|-------------|-----------------------------------------|----------|
|         500 | Error in updating a notification detail | ApiError |

## Consumes

- application/json;charset=UTF-8

## Produces

- application/json;charset=UTF-8

## Tags

- Notifications

## Retrieve the pending messages details

GET /PendingMessages

## Description

Retrieves the pending messages details for a specific time period and optionally filter | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type                     | Name                              | Description   | Schema   |
|--------------------------|-----------------------------------|---------------|----------|
| bexceptiontyp e optional | The business exception type       | string        | Query    |
| date required            | The time slot (hour in this case) | string        | Query    |
| text optional            | The free text to search by        | string        | Query    |

## Responses

|   HTTP Code | Description                                  | Schema                       |
|-------------|----------------------------------------------|------------------------------|
|         200 | successful operation                         | < PendingMessageD to > array |
|         500 | Cannot retrieve the pending messages details | RESTException                |

## Produces

- application/json;charset=UTF-8

## Tags

- BusinessExceptions

## Retrieve the pending messages time slots

GET /PendingMessages/TimeSlots

## Description

Retrieves the pending messages time slots where there are entries and the number of entries on those time slots | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name                     | Description                 | Schema   |
|--------|--------------------------|-----------------------------|----------|
| Query  | bexceptiontyp e optional | The business exception type | string   |
| Query  | text optional The free   | text to search by           | string   |

## Responses

|   HTTP Code | Description          | Schema                |
|-------------|----------------------|-----------------------|
|         200 | successful operation | < TimeSlotDto > array |

|   HTTP Code | Description                    | Schema        |
|-------------|--------------------------------|---------------|
|         500 | Cannot retrieve the time slots | RESTException |

## Produces

- application/json;charset=UTF-8

## Tags

- BusinessExceptions

## Retrieve the SED content of the pending message

GET /PendingMessages/{messageId}/Document

## Description

Retrieves  the  SED  content  that  caused/generated  the  pending  message  |  (Available  for  following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name               | Description                   | Schema   |
|--------|--------------------|-------------------------------|----------|
| Path   | messageId required | The id of the pending message | string   |

## Responses

|   HTTP Code | Description                                            | Schema        |
|-------------|--------------------------------------------------------|---------------|
|         200 | successful operation                                   | SedDto        |
|         500 | Cannot retrieve the SED content of the pending message | RESTException |

## Produces

- application/json;charset=UTF-8

## Tags

- BusinessExceptions

## Import All Process Assignments

POST /ProcessDefinitions/Assignments

## Description

Imports all Assignment Policies and Process Assignments from a json file | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type      | Name                   | Description                       | Schema   |
|-----------|------------------------|-----------------------------------|----------|
| Query     | institutionId required | The institution Id to filter with | string   |
| FormDat a | file required          | The file to be imported           | file     |

## Responses

|   HTTP Code | Description                                     | Schema   |
|-------------|-------------------------------------------------|----------|
|         500 | Error importing process definition assignments: | ApiError |

## Consumes

- multipart/form-data

## Tags

- ProcessDefinitions

## Export All Process Assignments

GET /ProcessDefinitions/Assignments

## Description

Exports all Assignment Policies and Process Assignments to a json file and download it | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name                   | Description                       | Schema   |
|--------|------------------------|-----------------------------------|----------|
| Query  | institutionId required | The institution Id to filter with | string   |

## Responses

|   HTTP Code | Description                                     | Schema        |
|-------------|-------------------------------------------------|---------------|
|         200 | successful operation                            | string (byte) |
|         500 | Error exporting process definition assignments: | ApiError      |

## Tags

- ProcessDefinitions

## Get Process Definition Assignments

GET /ProcessDefinitions/{processDefinitionName}/Assignment

## Description

Retireves the Actors of a Process Definition | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name              | Description                    | Schema   |
|--------|-------------------|--------------------------------|----------|
| Path   | tionName required | The process definition name/id | string   |

## Responses

|   HTTP Code | Description                                | Schema                |
|-------------|--------------------------------------------|-----------------------|
|         200 | successful operation                       | < BpmActorDto > array |
|         500 | Cannot get process definitions assignments | ApiError              |

## Produces

- application/json;charset=UTF-8

## Tags

- ProcessDefinitions

## Get List of Application Resources

GET /Resources

## Description

Retrieves the list of application resources (from the disk and installed) | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type                       | Name                                                           | Description           | Schema   |
|----------------------------|----------------------------------------------------------------|-----------------------|----------|
| hardRefresh required       | Boolean, true to reload resources by rescanning the disk       | boolean               | Query    |
| resourceIds optional       | Resource type list                                             | < string array(multi) | Query    |
| resourceLocat ion required | The location of the resources. Possible values: DISK or SERVER | string                | Query    |

## Responses

|   HTTP Code | Description             | Schema              |
|-------------|-------------------------|---------------------|
|         200 | successful operation    | ResourceRevisedD to |
|         500 | Error getting resources | RESTException       |

## Produces

- application/json;charset=UTF-8

## Tags

- Resources

## Update Application Resources

PUT /Resources

## Description

Updates/installs all resources from the disk in a single shot and returnes a list with resources that couldn't be installed | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name          | Description             | Schema                                       |
|--------|---------------|-------------------------|----------------------------------------------|
| Body   | body required | The resources to update | < string, < ResourceRevisedDto > array > map |

## Responses

|   HTTP Code | Description              | Schema              |
|-------------|--------------------------|---------------------|
|         200 | successful operation     | ResourceRevisedD to |
|         500 | Error updating resources | RESTException       |

## Produces

- application/json;charset=UTF-8

## Tags

- Resources

## Update Application Resource

PUT /Resources/{resourceId}

## Description

Updates/installs one resource from the disk | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type                        | Name                                                                     | Description                                           | Schema   |
|-----------------------------|--------------------------------------------------------------------------|-------------------------------------------------------|----------|
| Path resourceId required    | The name/id of the resource                                              | string                                                |          |
| Query resourceType required | The type of the resource. Possible organisation, vocabulary, initialdoc, | values: process, sbdh, sed, transaction, form, report | string   |
| Query on required           | The version of the resource                                              |                                                       | string   |

## Responses

|   HTTP Code | Description             | Schema        |
|-------------|-------------------------|---------------|
|         500 | Error updating resource | RESTException |

## Produces

- application/json;charset=UTF-8

## Tags

- Resources

## Create a Search Definition

POST /SearchDefinitions

## Description

Createa a Search Defintion with the specified name, color and search properties. | (Available for following roles: ROLE\_REGULAR)

## Parameters

| Type   | Name          | Description                      | Schema              |
|--------|---------------|----------------------------------|---------------------|
| Body   | body required | The Search Definition properties | SearchDefinitionDto |

## Responses

|   HTTP Code | Description                            | Schema     |
|-------------|----------------------------------------|------------|
|         500 | Error creating a new Search Definition | No Content |

## Consumes

- application/json;charset=UTF-8

## Tags

- SearchDefinitions

## Retrieve the List of Search Definitions

GET /SearchDefinitions

## Description

Retrieve  the  list  of  search  definitions  of  the  current  user  |  (Available  for  following  roles: ROLE\_REGULAR)

## Responses

|   HTTP Code | Description                         | Schema                         |
|-------------|-------------------------------------|--------------------------------|
|         200 | successful operation                | < SearchDefinitionD to > array |
|         500 | Error retrieving Search Definitions | RESTException                  |

## Produces

- application/json;charset=UTF-8

## Tags

- SearchDefinitions

## Update a Search Definition

PUT /SearchDefinitions/{id}

## Description

Updates a Search Defintion identified by its id | (Available for following roles: ROLE\_REGULAR)

## Parameters

| Type   | Name          | Description                      | Schema              |
|--------|---------------|----------------------------------|---------------------|
| Path   | id required   | The id of the search definition  | string              |
| Body   | body required | The Search Definition properties | SearchDefinitionDto |

## Responses

|   HTTP Code | Description                        | Schema        |
|-------------|------------------------------------|---------------|
|         500 | Error updating a Search Definition | RESTException |

## Consumes

- application/json;charset=UTF-8

## Tags

- SearchDefinitions

## Delete a Search Definition

DELETE /SearchDefinitions/{id}

## Description

Deletes a Search Defintion by its id | (Available for following roles: ROLE\_REGULAR)

## Parameters

| Type   | Name        | Description                     | Schema   |
|--------|-------------|---------------------------------|----------|
| Path   | id required | The id of the search definition | string   |

## Responses

|   HTTP Code | Description                        | Schema        |
|-------------|------------------------------------|---------------|
|         500 | Error deleting a Search Definition | RESTException |

## Tags

- SearchDefinitions

## Get Sectors and Process Definitions

GET /Sectors

## Description

Retrieves  the  list  of  sectors  along  with  the  list  of  availible  business  use  cases  for  each  sector.  If called  by  admin  user  without  the  parameter  Institution  Id,  the  merged  list  of  the  sectors  of  all Tenant institutions will be returned. | (Available for following roles: ROLE\_REGULAR,ROLE\_ADMIN)

## Parameters

| Type   | Name                   | Description                       | Schema   |
|--------|------------------------|-----------------------------------|----------|
| Query  | institutionId optional | The institution Id to filter with | string   |

## Responses

|   HTTP Code | Description              | Schema            |
|-------------|--------------------------|-------------------|
|         200 | successful operation     | < SectorDto array |
|         500 | Error retrieving sectors | ApiError          |

## Produces

- application/json;charset=UTF-8

## Tags

- Sectors

## Submit Common Data Model Request Document

PUT /Synchronizations/CDM/Document

## Description

Submits/saves the document for a Common Data Model Request. | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name                          | Description      | Schema               |
|--------|-------------------------------|------------------|----------------------|
| Body   | documentCon tent required The | Document content | < string, object map |

## Responses

|   HTTP Code | Description                | Schema        |
|-------------|----------------------------|---------------|
|         500 | Cannot submit the document | RESTException |

## Consumes

- application/json;charset=UTF-8

## Tags

- Synchronizations

## Retrieve Initial Common Data Model Request Document

GET /Synchronizations/CDM/InitialDocument

## Description

Retrieves  the  Initial  Document  specific  to  a  case  and  an  action  |  (Available  for  following  roles: ROLE\_ADMIN)

## Responses

|   HTTP Code | Description                                                | Schema                  |
|-------------|------------------------------------------------------------|-------------------------|
|         200 | successful operation                                       | SyncInitialDocum entDto |
|         500 | Cannot retrieve initial Common Data Model Request Document | RESTException           |

## Produces

- application/json;charset=UTF-8

## Tags

- Synchronizations

## Submit Institution Repository Request Document

PUT /Synchronizations/IR/Document

## Description

Submits/saves the document for an Institution Repository Request. | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type   | Name                          | Description      | Schema               |
|--------|-------------------------------|------------------|----------------------|
| Body   | documentCon tent required The | Document content | < string, object map |

## Responses

|   HTTP Code | Description                | Schema        |
|-------------|----------------------------|---------------|
|         500 | Cannot submit the document | RESTException |

## Consumes

- application/json;charset=UTF-8

## Tags

- Synchronizations

## Retrieve Initial Insitution Repository Request Document

GET /Synchronizations/IR/InitialDocument

## Description

Retrieves  the  Initial  Document  specific  to  a  case  and  an  action  |  (Available  for  following  roles: ROLE\_ADMIN)

## Responses

|   HTTP Code | Description                                                     | Schema                  |
|-------------|-----------------------------------------------------------------|-------------------------|
|         200 | successful operation                                            | SyncInitialDocum entDto |
|         500 | Cannot retrieve initial Institution Repository Request Document | RESTException           |

## Produces

- application/json;charset=UTF-8

## Tags

- Synchronizations

## Get Technical Log details

GET /TechnicalLogs

## Description

Retrieves  Technical  Log  details  for  the  specified  start  time,  end  time,  start  index,  end  index. Optionally, a free text filter can be applied. | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type                       | Name                                 | Description                             | Schema                 |
|----------------------------|--------------------------------------|-----------------------------------------|------------------------|
| Query count optional       | The end index of retrieved entries   | integer (int32)                         | integer (int32)        |
| Query date required        | The time with hour accuracy          | string                                  | string                 |
| Query from optional        | The start index of retrieved entries | integer (int32)                         | integer (int32)        |
| Query logPriority optional | The log priority                     | < enum ERROR, DEBUG, WARN) array(multi) | (TRACE, INFO, FATAL, > |
| Query logType optional     | The log type                         | string                                  | string                 |
| Query text optional        | The free text                        |                                         | string                 |

## Responses

|   HTTP Code | Description                               | Schema                            |
|-------------|-------------------------------------------|-----------------------------------|
|         200 | successful operation                      | < TechnicalLogsDet ailDto > array |
|         500 | Error in retrieving technical log details | RESTException                     |

## Produces

- application/json;charset=UTF-8

## Tags

- TechnicalLogs

## Get Technical Logs time slots

GET /TechnicalLogs/TimeSlots

## Description

Retrieves Technical Log time slots for the specified date interval. Optionally, a free text filter can be applied. | (Available for following roles: ROLE\_ADMIN)

## Parameters

| Type                       | Name                          | Description                                                    | Schema   |
|----------------------------|-------------------------------|----------------------------------------------------------------|----------|
| Query endDate required     | The end time(hour accuracy)   |                                                                | string   |
| Query logPriority optional | The log priority              | < enum (TRACE, ERROR, INFO, DEBUG, FATAL, WARN) > array(multi) |          |
| Query logType optional     | The log type                  |                                                                | string   |
| Query startDate required   | The start time(hour accuracy) |                                                                | string   |
| Query text optional        | The free text                 |                                                                | string   |

## Responses

|   HTTP Code | Description                | Schema                              |
|-------------|----------------------------|-------------------------------------|
|         200 | successful operation       | < TechnicalLogsTim eSlotDto > array |
|         500 | Error during the operation | RESTException                       |

## Produces

- application/json;charset=UTF-8

## Tags

- TechnicalLogs

## Get the User Profile

GET /UserProfile

## Description

Retrieves the current user profile | (Available for following roles: ROLE\_REGULAR,ROLE\_ADMIN)

## Responses

|   HTTP Code | Description                | Schema         |
|-------------|----------------------------|----------------|
|         200 | successful operation       | UserProfileDto |
|         500 | Error getting User Profile | ApiError       |

## Produces

- application/json;charset=UTF-8

## Tags

- UserProfile

## Update the User Profile

PUT /UserProfile

## Description

Updates the current user profile | (Available for following roles: ROLE\_REGULAR,ROLE\_ADMIN)

## Parameters

| Type   | Name          | Description      | Schema         |
|--------|---------------|------------------|----------------|
| Body   | body required | The User Profile | UserProfileDto |

## Responses

|   HTTP Code | Description                     | Schema   |
|-------------|---------------------------------|----------|
|         500 | Error updating the User Profile | ApiError |

## Consumes

- application/json;charset=UTF-8

## Tags

- UserProfile

## Update Process Fields

PUT /UserProfile/ProcessDefinitionFields/{processDefinitionId}

## Description

Updates process fields given its id | (Available for following roles: ROLE\_REGULAR)

## Parameters

| Type   | Name                          | Description                | Schema          |
|--------|-------------------------------|----------------------------|-----------------|
| Path   | processDefini tionId required | The processs definition id | string          |
| Body   | body required                 | Process fields payload     | FieldChooserDto |

## Responses

|   HTTP Code | Description                   | Schema        |
|-------------|-------------------------------|---------------|
|         500 | Error updating process fields | RESTException |

## Consumes

- application/json;charset=UTF-8

## Tags

- UserProfile

## Get Process Fields

GET /UserProfile/ProcessDefinitionFields/{processDefintionId}

## Description

Retrieves the fields of a process definition and their properties (display, sort, order).These are used for displaying the case instances. | (Available for following roles: ROLE\_REGULAR)

## Parameters

| Type   | Name           | Description                | Schema   |
|--------|----------------|----------------------------|----------|
| Path   | ionId required | The processs definition id | string   |

## Responses

|   HTTP Code | Description                             | Schema          |
|-------------|-----------------------------------------|-----------------|
|         200 | successful operation                    | FieldChooserDto |
|         500 | Error getting process definition fields | RESTException   |

## Produces

- application/json;charset=UTF-8

## Tags

- UserProfile

## Get User Role

GET /UserProfile/Type

## Description

Retrieves the user role: normal or admin.

## Responses

|   HTTP Code | Description             | Schema      |
|-------------|-------------------------|-------------|
|         200 | successful operation    | UserTypeDto |
|         500 | Error reading user role | ApiError    |

## Tags

- UserProfile

## Get Vocabulary Values

GET /Vocabularies/{id}

## Description

Retrieve all the concepts of a specific Vocabulary type providing the name of the type | (Available for following roles: ROLE\_REGULAR,ROLE\_ADMIN)

## Parameters

| Type   | Name          | Description                          | Schema   |
|--------|---------------|--------------------------------------|----------|
| Path   | id required   | The id of the vocabulary             | string   |
| Query  | text optional | The free text to filter vocabularies | string   |

## Responses

|   HTTP Code | Description                | Schema        |
|-------------|----------------------------|---------------|
|         200 | successful operation       | VocabularyDto |
|         500 | Error during the operation | ApiError      |

## Produces

- application/json;charset=UTF-8

## Tags

- Vocabularies

## Search organisations

GET /organisations

## Description

Searches organisations by organisation type, flow type and free text. The result list is limited to 10 results. | (Available for following roles: ROLE\_REGULAR,ROLE\_ADMIN)

## Parameters

| Type                   | Name                                                                                      | Description   | Schema   |
|------------------------|-------------------------------------------------------------------------------------------|---------------|----------|
| accessPointId optional | If only Entities of the same Access Point should be returned                              | string        | Query    |
| appRole optional       | PO, CP                                                                                    | string        | Query    |
| bucType optional       | The process definition name                                                               | string        | Query    |
| filterTenants optional | If entities of the same Access Point should not contain the installed Tenant Institutions | boolean       | Query    |
| searchText optional    | The free text to search for                                                               | string        | Query    |

## Responses

|   HTTP Code | Description                   | Schema                    |
|-------------|-------------------------------|---------------------------|
|         200 | successful operation          | < OrganisationDto > array |
|         500 | Error filtering organisations | ApiError                  |

## Produces

- application/json;charset=UTF-8

## Tags

- organisations

## Search organisations by parameters

GET /organisations/searchByParams

## Description

Searches  organisations  by  various  parameters  like  sectors,  validity,  BUCs,  etc…  |  (Available  for following roles: ROLE\_REGULAR,ROLE\_ADMIN)

## Parameters

| Type                      | Name Description                                                            | Schema                                                |
|---------------------------|-----------------------------------------------------------------------------|-------------------------------------------------------|
| applicationRo le optional | Application role of the BUC competence, which the institution must support. | Query enum (PO, CP)                                   |
| Query bucType optional    | Type of the BUC, which the institution must support.                        | string                                                |
| countryCode required      | Country code.                                                               | Query EE, EL, ES, FI, HR, HU, IS, IE, LI, LT, LU, MT, |
| Query from optional       | Pagination parameter to specify the starting point.                         | integer (int32)                                       |
| Query sector optional     | Name of the sector.                                                         | string                                                |
| Query size optional       | Number of entries returned from the starting position. Defaults to 50.      | integer (int32)                                       |

| Type   | Name               | Description                                   | Schema             |
|--------|--------------------|-----------------------------------------------|--------------------|
| Query  | validFrom optional | Minimum start validity of the BUC competence. | string (date-time) |
| Query  | validTo optional   | Maximum end validity of the BUC competence.   | string (date-time) |

## Responses

|   HTTP Code | Description                   | Schema                    |
|-------------|-------------------------------|---------------------------|
|         200 | successful operation          | < OrganisationDto > array |
|         500 | Error filtering organisations | ApiError                  |

## Produces

- application/json;charset=UTF-8

## Tags

- organisations

## Get organisation by id

GET /organisations/{id}

## Description

Retrieves a single organisation given its id | (Available for following roles: ROLE\_REGULAR,ROLE\_ADMIN)

## Parameters

| Type Name                 | Description Schema                                                                                      |
|---------------------------|---------------------------------------------------------------------------------------------------------|
| Path countryCode required | CH, CY, CZ, DE, DK, EE, EL, ES, FI, FR, HR, HU, IS, IE, IT, LV, LI, LT, LU, MT, NL, NO, PL, PT, RO, SE, |
| Path id required          | The Id of the organisation string                                                                       |

## Responses

|   HTTP Code | Description                       | Schema          |
|-------------|-----------------------------------|-----------------|
|         200 | successful operation              | OrganisationDto |
|         500 | Error retrieving the organisation | ApiError        |

## Produces

- application/json;charset=UTF-8

## Tags

- organisations

## POST /user-auth

## Parameters

| Type   | Name          | Schema   |
|--------|---------------|----------|
| Body   | body optional | UserDto  |

## Responses

| HTTP Code   | Description          | Schema     |
|-------------|----------------------|------------|
| default     | successful operation | No Content |

## Definitions

## AccessPointDto

Access Point Details

| Name                            | Description                                                                      | Schema   |
|---------------------------------|----------------------------------------------------------------------------------|----------|
| accessPointIp optional          | The IP of the Access Point                                                       | string   |
| accessPointPo rt optional       | The port of the Access Point                                                     | string   |
| channel optional                | The business channel used for pulling, this is the last part of the business MPC | string   |
| countryCode optional            | The country code of the Access Point                                             | string   |
| id optional                     | The Id of the Access Point                                                       | string   |
| inboxService optional           | The inbox Service URL of the Access Point                                        | string   |
| name optional                   | The name of the Access Point                                                     | string   |
| outboxService optional          | The outbox Service URL of the Access Point                                       | string   |
| protocol optional               | The protocol of the Access Point                                                 | string   |
| technicalChan nel optional      | The system channel used for pulling, this is the last part of the system MPC     | string   |
| technicalInbo xService optional | The technical inbox Service URL of the Access Point                              | string   |

| Name                             | Description                                          | Schema   |
|----------------------------------|------------------------------------------------------|----------|
| technicalOutb oxService optional | The technical outbox Service URL of the Access Point | string   |
| technicalProt ocol optional      | The technical protocol of the Access Point           | string   |

## AcknowledgementDto

Business  Acknowledgment/  Receipt  of  a  specific  User  Message  from  the  receiver  destination Institution

| Name              | Description                           | Schema             |
|-------------------|---------------------------------------|--------------------|
| date optional     | The date when ACK was received        | string (date-time) |
| id optional       | The Id of the message                 | string             |
| receiver optional | The receiver Organisation/Institution | EntityBaseDto      |
| sender optional   | The sender Organisation/Institution   | EntityBaseDto      |

## ActionGroupDto

Action group

| Name                 | Description                       | Schema   |
|----------------------|-----------------------------------|----------|
| DMProcessId optional | DMprocess ID                      | string   |
| DocumentId optional  | Document ID for this action group | string   |
| Operation optional   | Operation of this action group    | string   |

| Name                         | Description                              | Schema   |
|------------------------------|------------------------------------------|----------|
| ParentDocId optional         | Parent document ID for this action group | string   |
| ParentType optional          | Parent type for this action group        | string   |
| Type optional                | Type for this action group               | string   |
| activityInstan ceId optional | Activity instance ID                     | string   |
| hasLocalClose optional       | If the action group has local close      | boolean  |

## ActionRevisedDto

Available Action of a specific Case Instance or Document

| Name                 | Description                                 | Schema         |
|----------------------|---------------------------------------------|----------------|
| actionGroup optional | Action group                                | ActionGroupDto |
| actor optional       | Actor for this action                       | string         |
| bulk optional        |                                             | boolean        |
| canClose optional    | Can close                                   | boolean        |
| caseId optional      | Case ID of this action                      | string         |
| caseRelated optional |                                             | boolean        |
| displayName optional | The name for display purposes of the Action | string         |

| Name                              | Description                                          | Schema   |
|-----------------------------------|------------------------------------------------------|----------|
| documentId optional               | The document Id that the action is related to        | string   |
| documentRela ted optional         |                                                      | boolean  |
| documentTyp e optional            | The type of the document associated with this action | string   |
| hasBusinessV alidation optional   | If this action has a business validation             | boolean  |
| hasSendValid ationOnBulk optional | Has send validation on bulk                          | boolean  |
| id optional                       | The id of the Action                                 | string   |
| isBulk optional                   | If this action is a bulk action                      | boolean  |
| isCaseRelated optional            | If is an action related to a case                    | boolean  |
| isDocumentRe lated optional       | If is an action related to a document                | boolean  |
| name optional                     | The name of the Action                               | string   |

| Name               | Description                   |                                                                                                                                                                                                                                                                                                                                                                                                                  |
|--------------------|-------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| operation optional | Operation name of this action | Schema enum (CREATE, UPDATE, SEND, DELETE, SUBDOCUMENT, CREATE_LETTER, READ, CLOSE, REOPEN, DELETE_CASE, LOCAL_CLOSE, LOCAL_REOPEN, ARCHIVE_CASE, BACKUP_CASE, RESTORE_CASE, SEND_PARTICIPANT S, SELECT_PARTICIPA NTS, READ_PARTICIPANT S, UPDATE_PARTICIPA NTS, ADD_ATTACHMENT, REQUEST_APPROVA L, ADD_SUBDOCUMEN T, UPDATE_SUBDOCU MENT, REMOVE_SUBDOCU MENT, IMPORT_SUBDOCU MENT, CREATE_CASE, REMOVE_ATTACHM |

| Name                            | Description                                                                  | Schema                                                                                                                |
|---------------------------------|------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------|
| parentDocum entId optional      | The parent document Id that the action is related to                         | string                                                                                                                |
| poolGroup optional              | Pool group                                                                   | ActionGroupDto                                                                                                        |
| requiresValid Document optional | If requires a valid document                                                 | boolean                                                                                                               |
| status optional                 | Status of this action                                                        | enum (ACTIVE, SUSPENDED, CANCELLED, EXECUTED, SYSTEM_SUSPENDE D, SYSTEM_CLAIMED, EMPTY, NEW, SENT, RECEIVED, FORWARD) |
| subdocumentI d optional         | The subdocument Id that the action is related to                             | string                                                                                                                |
| tags optional                   | type is Map<String,String>, The tagss (pairs of key and value) of the Action | TagDto                                                                                                                |
| tempDocume ntId optional        | The id of the temporary document for the action                              | string                                                                                                                |
| template optional               | The template used by the client to render the Action Form                    | string                                                                                                                |
| type optional                   | The type of the Action                                                       | string                                                                                                                |
| typeVersion optional            | The type/template version used by the client to render the Action Form       | string                                                                                                                |

## ActivityRevisedDto

User Activity

| Name                         | Description                              | Schema                                  |
|------------------------------|------------------------------------------|-----------------------------------------|
| caseDto optional             | The case associated to the activity      | CaseRevisedDto                          |
| caseId optional              | The case Id of the Activity              | string                                  |
| colour optional              | The type's colour of the Activity        | enum (BLUE, RED, GREEN, ORANGE, PURPLE) |
| dayInterval optional         | The interval of the repetition           | integer (int64)                         |
| deleted optional             |                                          | boolean                                 |
| id optional                  | The id of the Activity                   | string                                  |
| isDeleted optional           | The status of the Activity               | boolean                                 |
| message optional             | The message of the Activity              | string                                  |
| occurrences optional         | The occurence of the repetition          | integer (int64)                         |
| repeating optional           | The repetition of the Activity           | boolean                                 |
| repetitionPar entId optional | The repetition parent Id of the Activity | string                                  |
| startDate optional           | The start date of the Activity           | string (date-time)                      |

| Name             | Description                 | Schema          |
|------------------|-----------------------------|-----------------|
| title optional   | The title of the Activity   | string          |
| userId optional  | The user-id of the Activity | string          |
| version optional | The version of the Activity | integer (int64) |

## ActorRevisedDto

BPMN Actor of a specific Case Instance

| Name                | Description                                         | Schema                                                                                             |
|---------------------|-----------------------------------------------------|----------------------------------------------------------------------------------------------------|
| id optional         | The id of the Actor                                 | string                                                                                             |
| name optional       | The name of the Actor                               | enum (SUPERVISOR, AUTHORIZED_CLER K, UNAUTHORIZED_CL ERK, AUDITOR, VIEWER, MEDICAL, VIP, EVERYONE) |
| userGroups optional | The Users or/and the Groups that Actor is mapped to | < UserGroupDto > array                                                                             |

## AddressDto

Address details

| Name                | Description                            | Schema   |
|---------------------|----------------------------------------|----------|
| country optional    | The country of the Address details     | string   |
| postalCode optional | The postal code of the Address details | string   |
| region optional     | The region of the Address details      | string   |

| Name            | Description                       | Schema   |
|-----------------|-----------------------------------|----------|
| street optional | The street of the Address details | string   |
| town optional   | The town of the Address details   | string   |

## AdminNotificationTypeDto

AdminNotificationType details

| Name                         | Description                                                     | Schema          |
|------------------------------|-----------------------------------------------------------------|-----------------|
| be optional                  | Flag to activate the Notification Centre for Business Exception | boolean         |
| forAdmin optional            | Value of Notification Centre for Admin checkbox                 | boolean         |
| forClerk optional            | Value of the Notification Centre for Clerk checkbox             | boolean         |
| generateNIEE vent optional   | The generate NIE evemt of theAdminNotificationType              | boolean         |
| id optional                  | The id of the AdminNotificationType                             | string          |
| notificationPe riod optional | The notification period of the AdminNotificationType            | integer (int64) |
| notificationTy pe optional   | The notification Type of the AdminNotificationType              | string          |
| retentionPeri od optional    | The retention period of the AdminNotificationType               | integer (int64) |
| showForAdmi n optional       | Flag to activate the Notification Centre for Admin checkbox     | boolean         |

| Name                  | Description                                                 | Schema          |
|-----------------------|-------------------------------------------------------------|-----------------|
| showForClerk optional | Flag to activate the Notification Centre for Clerk checkbox | boolean         |
| version optional      | The version of the AdminNotificationType                    | integer (int64) |

## AlarmDto

Alarm details

| Name                  | Description                                | Schema             |
|-----------------------|--------------------------------------------|--------------------|
| caseId optional       | The id of the case the alarm is related to | string             |
| creationDate optional | The date the alarm was created             | string (date-time) |
| creator optional      | The user that created the alarm            | UserGroupDto       |
| date optional         | The date of the alarm                      | string (date-time) |
| description optional  | The description of the alarm               | string             |
| id optional           | The id of the case the alarm is related to | string             |

## AlarmSettings

Alarm Settings and Defaults

| Name                    | Description                                | Schema          |
|-------------------------|--------------------------------------------|-----------------|
| autoSetDays optional    | The default interval for an alarm, in days | integer (int32) |
| autoSetOnSen d optional | Auto set alarm on Send action              | boolean         |

## ApiError

Error Message of a specific error/exception occured while processing a request

| Name                                  | Description                        | Schema           |
|---------------------------------------|------------------------------------|------------------|
| cummulative Errors optional read-only | The description of the Exception   | < string > array |
| error optional read-only              | The short message of the Exception | string           |
| error_descrip tion optional read-only | The description of the Exception   | string           |
| stack optional read-only              | The stack of the Exception         | string           |

## ApplicationProfileDto

Personalised details metadata of User

| Name                                   | Description                                          | Schema                                  |
|----------------------------------------|------------------------------------------------------|-----------------------------------------|
| applicationId optional                 | The application id of this institution if applicable | string                                  |
| archivingPolic ies optional            | The archiving policies container                     | ArchivingPoliciesDto                    |
| archivingRep ositories optional        | The archiving repositories container                 | ArchivingRepositori esDto               |
| archivingRep ositoryPolicie s optional | Archiving cases repository policies                  | < ArchivingRepository PolicyDto > array |

| Name                                  | Description                                   | Schema                         |
|---------------------------------------|-----------------------------------------------|--------------------------------|
| attachmentAll owedMimeTy pes optional | Attachment Allowed Mime Types                 | < string > array               |
| attachmentDi rectoryPath optional     | Attachment directory path                     | string                         |
| attachmentM axFileSize optional       | Attachment Maximum File Size (in Kb)          | integer (int32)                |
| autoSyncCDM optional                  | Auto Sync Common Data Model (in minutes)      | integer (int32)                |
| autoSyncIR optional                   | Auto Sync Institution Repository (in minutes) | integer (int32)                |
| bulkSEDMaxN umberChildre n optional   | Maximum Number of Child Documents in Bulk SED | integer (int32)                |
| businessExce ptionsSettings optional  | Business exceptions settings                  | BusinessExceptionsS ettingsDto |
| casesRetentio nPolicies optional      | Cases retention policies container            | RetentionPoliciesDto           |
| characterSet optional                 | The charcter set used in the application      | string                         |
| defaultCritica lity optional          | The default criticality                       | string                         |
| defaultImport ance optional           | The default importance                        | string                         |

| Name                                     | Description                                                                   | Schema                        |
|------------------------------------------|-------------------------------------------------------------------------------|-------------------------------|
| defaultLangu age optional                | The default/fall-back language                                                | string                        |
| defaultUserPr ofile optional             | The default user profile                                                      | UserProfileDto                |
| formReposito ryPath optional             | The form (html) shared repository path                                        | string                        |
| letterTemplat esRepositoryP ath optional | The path to the office letters templates                                      | string                        |
| localizationRe positoryPath optional     | The path to the BUC localization resources                                    | string                        |
| maxIdleTime optional                     | The maximum idle time (in minutes)                                            | integer (int32)               |
| messagesRete ntionPolicies optional      | Messaging retention policies container                                        | MessagesRetentionP oliciesDto |
| multitenantM ode optional                | Is multitenant mode                                                           | boolean                       |
| name optional                            | The name of the Application Profile                                           | string                        |
| organizationS ystemPasswor d optional    | Organization system password, needed to execute sanity tests (bonita process) | string                        |
| pdpAssignme ntsImplClass optional        | Automatic Case Assignments Policy Decision Point: full class name             | string                        |

| Name                               | Description                                                                  | Schema              |
|------------------------------------|------------------------------------------------------------------------------|---------------------|
| processAssign mentsPolicy optional | Automatic Process Assignments Policies: (all, me, rules)                     | string              |
| recoveryVolu mePath optional       | Recovery Volume path                                                         | string              |
| resourcesDisk Path optional        | The disk path to the resources(process definitions, vocabularies) to install | string              |
| searchCasesM axResults optional    | Search case maximum results                                                  | integer (int32)     |
| sedValidation Mode optional        | The type of backend validation of SEDs against xsd                           | string              |
| showFullErro r optional            | Show Full Error Information                                                  | boolean             |
| showProcessV ersion optional       | Show process version                                                         | boolean             |
| showSoftware Versions optional     | Show versions for installed software                                         | boolean             |
| supportedLan guages optional       | The list of supported languages                                              | < string > array    |
| tenants optional                   | The tenant InstitutionIds of the application                                 | < TenantDto > array |
| ticketDestinat ionEmail optional   | The ticket destination mail address                                          | string              |

| Name                          | Description                                       | Schema        |
|-------------------------------|---------------------------------------------------|---------------|
| ticketRelayEm ail optional    | The ticket relay mail address                     | string        |
| ticketRelayPa ssword optional | The ticket relay password                         | string        |
| ticketRelaySe rver optional   | The ticket relay mail server                      | string        |
| useApplicatio nId optional    | Whether this institution uses an application id   | boolean       |
| validateSED optional          | Validation of SED in the portal                   | boolean       |
| whoami optional               | The organisation / Institution of the application | EntityBaseDto |

## ArchivingOptionsDto

Archiving options details

| Name                        | Description                                                                                                        | Schema             |
|-----------------------------|--------------------------------------------------------------------------------------------------------------------|--------------------|
| archivalDate optional       | The date when a case will be archived (for CLOSED or REMOVED cases) or has been archived (ARCHIVED cases)          | string (date-time) |
| archived optional           | Attribute used for archiving & un-archiving actions. (False - for cases to be archived, True - for archived cases) | boolean            |
| archivingVolu me optional   | The volume of the archive                                                                                          | string             |
| closedRemove dDate optional | The date when a case changed status to CLOSED or FORWARDED/REMOVED and the archival process started                | string (date-time) |

| Name                  | Description                                   | Schema             |
|-----------------------|-----------------------------------------------|--------------------|
| deletionDate optional | The estimated date when acase archive will be | string (date-time) |

## ArchivingPoliciesDto

Archiving repositories details

| Name                             | Description                                                                                   | Schema                       |
|----------------------------------|-----------------------------------------------------------------------------------------------|------------------------------|
| archiveMessa ges optional        | The Boolean value which specify if the messages will be archived.                             | boolean                      |
| archivingPolic iesTable optional | The decision table containing all the cases archiving policies rules                          | < ArchivingPolicyDto > array |
| defaultArchiv ingPeriod optional | The default volume which will be used for cases archives when no match in the decision table. | integer (int32)              |

## ArchivingPolicyDto

Archiving policy details

| Name               | Description                           | Schema            |
|--------------------|---------------------------------------|-------------------|
| applicationRo      |                                       |                   |
| le optional        | The application role                  | string            |
| applicationRo      |                                       |                   |
| leId optional      | The application role ID               | enum (PO, CP, IR) |
| bucType optional   | The business use case                 | string            |
| bucTypeId optional | The business use case ID              | string            |
| id optional        | The ID of the archiving policy - rule | string            |

| Name              | Description                                                                                                                                                                      | Schema          |
|-------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------|
| policy optional   | The archiving timer used by archiving process. Closed or forwarded cases will be archived after the specified timer (number of days - e.g.7 days a week, 365 days a year, etc. ) | integer (int32) |
| sector optional   | The name of the Sector                                                                                                                                                           | string          |
| sectorId optional | The ID of the Sector                                                                                                                                                             | string          |
| tenant optional   | The tenant                                                                                                                                                                       | string          |
| tenantId optional | The tenant ID                                                                                                                                                                    | string          |

## ArchivingRepositoriesDto

Archiving repositories details

| Name                                  | Description                                                                                                                          | Schema                       |
|---------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------|------------------------------|
| archivingRep ositoriesList optional   | The decision table containing all the archiving repositories rules                                                                   | < ArchivingVolumeDto > array |
| defaultCaseAr chivingVolum e optional | This field is not relevant annymore. (The default volume which will be used for cases archives when no match in the decision table.) | string                       |
| defaultMessag esVolume optional       | The volume used for messages archives                                                                                                | string                       |

## ArchivingRepositoryPolicyDto

Archiving repository policy details

| Name                        | Description                                                                                                                                                                      | Schema            |
|-----------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------|
| applicationRo le optional   | The application role                                                                                                                                                             | string            |
| applicationRo leId optional | The application role ID                                                                                                                                                          | enum (PO, CP, IR) |
| archivingVolu me optional   | The volume on which the matched rule will use for archival                                                                                                                       | string            |
| archivingVolu meId optional | The volume ID on which the matched rule will use for archival                                                                                                                    | string            |
| bucType optional            | The business use case                                                                                                                                                            | string            |
| bucTypeId optional          | The business use case ID                                                                                                                                                         | string            |
| id optional                 | The ID of the archiving policy - rule                                                                                                                                            | string            |
| policy optional             | The archiving timer used by archiving process. Closed or forwarded cases will be archived after the specified timer (number of days - e.g.7 days a week, 365 days a year, etc. ) | integer (int32)   |
| sector optional             | The name of the Sector                                                                                                                                                           | string            |
| sectorId optional           | The ID of the Sector                                                                                                                                                             | string            |
| tenant optional             | The tenant                                                                                                                                                                       | string            |
| tenantId optional           | The tenant ID                                                                                                                                                                    | string            |

## ArchivingVolumeDto

Archiving volume details

| Name                                 | Description                                                          | Schema           |
|--------------------------------------|----------------------------------------------------------------------|------------------|
| achivingMinS paceThreshol d optional | The minimum space threshold per volume for archiving process (in MB) | integer (int32)  |
| archivingVolu me optional            | Volume name                                                          | string           |
| archivingVolu meId optional          | Volume identifier                                                    | string           |
| physicalLocat ions optional          | The physical locations attached to volumes                           | < string > array |

## AssignedBUCDto

| Name                        | Description                 | Schema             |
|-----------------------------|-----------------------------|--------------------|
| applicationRo le optional   | The application Role        | string             |
| bucType optional            | The BUC Type                | string             |
| isEESSIReady optional       | Is ready for usage in EESSI | boolean            |
| validityEndDa te optional   | End day of the validity     | string (date-time) |
| validityStartD ate optional | Start day of the validity   | string (date-time) |

## AssignmentPolicyConditionDto

Assignment Rule Condition details

| Name                        | Description                                                     | Schema                  |
|-----------------------------|-----------------------------------------------------------------|-------------------------|
| appRole optional            | The case should have this application role (PO/CP)              | string                  |
| creatorGroup optional       | The creator of the case should be in one of these groups        | < UserGroupDto > array  |
| ownerCountry optional       | The PO of the case should be from one of these countries        | < string > array        |
| ownerOrganiz ation optional | The PO of the case should be one of these organizations         | < EntityBaseDto > array |
| process optional            | The process type of the case should match one of this list      | < string > array        |
| sector optional             | The sector of the case should match one of this list            | < string > array        |
| subjectAddres s optional    | The case subject's address (the region) should match this value | string                  |

## AssignmentPolicyDto

Assignment Policy details

| Name                 | Description                                          | Schema   |
|----------------------|------------------------------------------------------|----------|
| appRole optional     | The optional application role of this policy (PO/CP) | string   |
| color optional       | The color of the policy                              | string   |
| description optional | The policy description                               | string   |

| Name                   | Description                                                             | Schema                             |
|------------------------|-------------------------------------------------------------------------|------------------------------------|
| id optional            | The id of the policy                                                    | string                             |
| institutionId optional | The institution id of the policy                                        | string                             |
| name optional          | The name of the policy                                                  | string                             |
| policies optional      | List of existing policy ids, meaning that this policy is a policy group | < string > array                   |
| rules optional         | List of rules contained in this policy                                  | < AssignmentPolicyRu leDto > array |
| targets optional       | List of assignment policy target IDs                                    | < string > array                   |
| type optional          | The type of this policy                                                 | enum (POLICY, GROUP, CREATOR)      |

## AssignmentPolicyRuleDto

Assignment Rule details

| Name                | Description                                                              | Schema                        |
|---------------------|--------------------------------------------------------------------------|-------------------------------|
| actors optional     | The actors the groups above will be assigned as                          | < string > array              |
| condition optional  | The condition that must be met by a case instance for this rule to apply | AssignmentPolicyCo nditionDto |
| id optional         | The id of this rule, optional                                            | string                        |
| name optional       | The name of this rule, optional                                          | string                        |
| userGroups optional | The collection of users or groups to be assigned                         | < UserGroupDto > array        |

## AssignmentRequest

The Roles associated with AssignmentRequest

| Name            | Description                                 | Schema           |
|-----------------|---------------------------------------------|------------------|
| actors optional | The Roles associated with AssignmentRequest | < string > array |

## AttachementDto

## Attachment details

| Name                          | Description                                                                               | Schema             |
|-------------------------------|-------------------------------------------------------------------------------------------|--------------------|
| caseId optional               | Case Id of the associated case                                                            | string             |
| creationDate optional         | The date that the Document was created                                                    | string (date-time) |
| creator optional              | The creator User or Group of the Document                                                 | UserGroupDto       |
| documentId optional           | Document Id of the associated document (in case the attachment is attached to a document) | string             |
| fileName optional             | The name of the file of the Attachment                                                    | string             |
| hasMultipleVe rsions optional | True if the document has multiple versions                                                | boolean            |
| id optional                   | The Id of the Document                                                                    | string             |
| internalId optional           | Internal ID of the attachment                                                             | string             |
| lastUpdate optional           | The date that the Document was last updated                                               | string (date-time) |
| medical optional              | Medical information flag                                                                  | boolean            |

| Name                       | Description                          | Schema               |
|----------------------------|--------------------------------------|----------------------|
| mimeType optional          | The mime type of the Document        | string               |
| name optional              | The name of the Document             | string               |
| parentDocum entId optional | The Id of parent document            | string               |
| versions optional          | The list of Versions of the Document | < VersionDto > array |

## AttachmentIdentificationDto

| Name                            | Description                                         | Schema   |
|---------------------------------|-----------------------------------------------------|----------|
| contentLocati on optional       | The content location                                | string   |
| fileName optional               | The attachment file name                            | string   |
| id optional                     | The Document Id                                     | string   |
| identifier optional             | The document attachment identifier                  | string   |
| internetMedia TypeCode optional | The media type code for the file                    | string   |
| isMedical optional              | Flag indicating if the attachment is medical or not | boolean  |
| mimeType optional               | The mimeType                                        | string   |
| sectionRefere nce optional      | The section reference for the attachment            | string   |

## AuditLogsDetailDto

Audit logs details

| Name                      | Description                                                                             | Schema          |
|---------------------------|-----------------------------------------------------------------------------------------|-----------------|
| @timestamp optional       | Timestamp of the log entry                                                              | string          |
| @version optional         | Version of the log entry                                                                | string          |
| host optional             | The network machine (IP address) who generated the log entry                            | string          |
| logger_name optional      | Technical attribute consisting in the full Java class name that generated the log entry | string          |
| message optional          | The actual audit entry properties                                                       | Message         |
| port optional             | Port of the machine                                                                     | integer (int32) |
| priority optional         | The logging system levels (DEBUG, INFO, WARNING, ERROR, TRACE, etc.)                    | string          |
| stack_trace optional      |                                                                                         | string          |
| syslog5424_ap p optional  |                                                                                         | string          |
| syslog5424_ho st optional |                                                                                         | string          |
| syslog5424_pri optional   |                                                                                         | string          |
| syslog5424_pr oc optional |                                                                                         | string          |

| Name                           | Description                                                           | Schema   |
|--------------------------------|-----------------------------------------------------------------------|----------|
| syslog5424_ts optional         | Syslog specific attributes                                            | string   |
| syslog5424_ve r optional       |                                                                       | string   |
| syslog_facility optional       |                                                                       | string   |
| syslog_facility _code optional |                                                                       | string   |
| syslog_severit y optional      |                                                                       | string   |
| syslog_severit y_code optional |                                                                       | string   |
| thread optional                | The OS thread which generated the log entry.                          | string   |
| type optional                  | The RINA component that generated the log entry (BMS/Messaging, REST) | string   |

## AuditLogsTimeSlotDto

The time slot information for audit logs

| Name            | Description                     | Schema             |
|-----------------|---------------------------------|--------------------|
| date optional   | The day of the slot             | string (date-time) |
| number optional | The number of items in the slot | integer (int64)    |

## AuditedObjects

The audited object

| Name             | Description                                                                               | Schema                                                                                                                                                                                                                                            |
|------------------|-------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| details optional | In case of error the object triggered by REST shall be recorded here                      | string                                                                                                                                                                                                                                            |
| id optional      | The id of the audited object                                                              | string                                                                                                                                                                                                                                            |
| type optional    | The type of the audited object (e.g. attachment, case credential, policy, document, etc.) | enum (ATTACHMENT, ACTION, CASE, COMMENT, DOCUMENT, SUBDOCUMENT, NOTIFICATION, ALARM, SEARCH_DEFINITIO N, USER_GROUP, USER_PROFILE, APPLICATION_PROF ILE, CREDENTIAL, POLICY, BUSINESS_MESSAGE , TECHNICAL_MESSA GE, BUSINESS_ACK, BUSINESS_ERROR) |

## BUCTypeDto

User Activity

| Name             | Description          | Schema   |
|------------------|----------------------|----------|
| id optional      | The BUC type Id      | string   |
| name optional    | The BUC type name    | string   |
| sector optional  | The BUC sector       | string   |
| version optional | The BUC type version | string   |

| Name              | Description          | Schema                      |
|-------------------|----------------------|-----------------------------|
| versions optional | The list of versions | < BUCTypeVersionDto > array |

## BUCTypeVersionDto

Version description of a BUC type

| Name                | Description                       | Schema             |
|---------------------|-----------------------------------|--------------------|
| activeFrom optional | Active since the given date time. | string (date-time) |
| version optional    | The ID of the version.            | string             |

## BpmActorDto

BPMN Actor of a specific Case Instance

| Name          | Description           | Schema   |
|---------------|-----------------------|----------|
| id optional   | The id of the Actor   | string   |
| name optional | The name of the Actor | string   |

## BusinessExceptionDto

Business Exception

| Name              | Description                                  | Schema               |
|-------------------|----------------------------------------------|----------------------|
| date optional     | The rejection date of the business error     | string               |
| document optional | The identification of the rejection-x050 BUC | SedIdentificationDto |
| id optional       | The id of the business error                 | string               |

| Name            | Description                                | Schema               |
|-----------------|--------------------------------------------|----------------------|
| reason optional | The rejection reason of the business error | string               |
| source optional | The source/cause of the business error     | < string, object map |
| type optional   | The rejection reason of the business error | string               |

## BusinessExceptionsSettingsDto

Business Exception Settings

| Name                                                              | Description   | Schema   |
|-------------------------------------------------------------------|---------------|----------|
| ReceivedASed AttachmentW hichFailedAnt imalwareChec king optional |               | string   |
| ReceivedASed InCaseInWron gSequence optional                      |               | string   |
| ReceivedASed WhenCaseInG lobalClosedSt atus optional              |               | string   |
| ReceivedASed WithAnInvali dBusinessSign ature optional            |               | string   |

| Name                                                                  | Description                    | Schema          |
|-----------------------------------------------------------------------|--------------------------------|-----------------|
| ReceivingASe dAfterCaseFo rwardedAnot herParticipan t optional        |                                | string          |
| ReceivingASe dAfterCaseRe movedByRece ivingAX006Se d optional         |                                | string          |
| ReceivingASe dForAMissing Case optional                               |                                | string          |
| ReceivingASe dForAMissing SetldSedUpda teForANonExi stingSed optional |                                | string          |
| UnknownCaus e optional                                                |                                | string          |
| missingCaseTi meout optional                                          | The path to the xsd repository | integer (int32) |

## BusinessKeyAliasPassword

| Name                              | Schema   |
|-----------------------------------|----------|
| certificateAlias optional         | string   |
| certificateAliasPassword optional | string   |

## CLIENTBusinessKeyStorePassword

| Name                              | Schema   |
|-----------------------------------|----------|
| certificateAlias optional         | string   |
| certificateAliasPassword optional | string   |

## CaseAssignmentActionRevisedDto

Parameters used to execute a case assignment action

| Name                    | Description                                                                                    | Schema                                                                                                       |
|-------------------------|------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|
| action optional         | The action type of the assignment operation: request to assign, accept request, reject request | enum (REQUEST, ACCEPT_REQUEST, REJECT_REQUEST)                                                               |
| actors optional         | The list of actors for this case assignment action                                             | < enum (SUPERVISOR, AUTHORIZED_CLER K, UNAUTHORIZED_CL ERK, AUDITOR, VIEWER, MEDICAL, VIP, EVERYONE) > array |
| notificationId optional | The notification id on which to execute an assignment operation                                | string                                                                                                       |
| reason optional         | The reason of assignment operation: in case of reject action                                   | string                                                                                                       |

## CaseAssignmentRevisedDto

Case Assignment details

| Name            | Description                          | Schema                    |
|-----------------|--------------------------------------|---------------------------|
| actors optional | The List of Actors of case assigment | < ActorRevisedDto > array |

| Name                | Description                                  | Schema               |
|---------------------|----------------------------------------------|----------------------|
| id optional         | The Id of the Case                           | string               |
| properties optional | The importance case property for assignments | < string, string map |

## CaseClassicView

The Case Management Classic View Settings

| Name                   | Description                                                              | Schema   |
|------------------------|--------------------------------------------------------------------------|----------|
| groupByMont h optional | Enable/Disable month grouping in document list                           | boolean  |
| showPreview optional   | Enable/Disable showing of the document preview at the bottom of the list | boolean  |

## CaseCounterSettingsDto

Case counter settings

| Name                   | Description               | Schema                            |
|------------------------|---------------------------|-----------------------------------|
| callbackUrl optional   | callbackUrl               | string                            |
| counterType optional   | counterType               | enum (DEFAULT, PATTERN, CALLBACK) |
| id optional            | The id of the object      | string                            |
| institutionId optional | institutionId             | string                            |
| pattern optional       | pattern                   | string                            |
| version optional       | The version of the object | integer (int64)                   |

## CaseCreationParams

| Name                           | Schema                 |
|--------------------------------|------------------------|
| initialVariables optional      | < string, string > map |
| processDefinitionName optional | string                 |

## CaseIdentificationDto

| Name                        | Description                                                                                                   | Schema   |
|-----------------------------|---------------------------------------------------------------------------------------------------------------|----------|
| identifier optional         | Globally unique case identifier to allow the correlation of all the SEDs exchanged within a business use case | string   |
| isProtectedPe rson optional | Is person's identity protected                                                                                | boolean  |
| protectedPers on optional   |                                                                                                               | boolean  |
| type optional               | The business use case                                                                                         | string   |
| version optional            | The version of the business use case                                                                          | string   |

## CaseInfoDto

The caseInfo details of the notification

| Name                | Description                                                       | Schema               |
|---------------------|-------------------------------------------------------------------|----------------------|
| id optional         | The case Id                                                       | string               |
| properties optional | type is Map<String,String>, The Map of the properties of the case | < string, string map |
| subject optional    | The subject of the case                                           | EntityBaseDto        |

| Name          | Description               | Schema     |
|---------------|---------------------------|------------|
| type optional | The case type information | BUCTypeDto |

## CaseParticipantDto

Participating Institution in a case instance

| Name                  | Description                                                      | Schema                                        |
|-----------------------|------------------------------------------------------------------|-----------------------------------------------|
| organisation optional | The Organisation/Institution that the participant corresponds to | EntityBaseDto                                 |
| role optional         | The role of the participant in in a conversation or in a case    | enum (CaseOwner, CounterParty, IntelligentRA) |
| selected optional     | Is participant selected                                          | boolean                                       |

## CaseRetentionPolicyDto

Case retention policy details

| Name          | Description                           | Schema            |
|---------------|---------------------------------------|-------------------|
| applicationRo |                                       |                   |
| le optional   | The application role                  | string            |
| applicationRo |                                       |                   |
| leId optional | The application role ID               | enum (PO, CP, IR) |
| bucType       |                                       |                   |
| optional      | The business use case                 | string            |
| bucTypeId     |                                       |                   |
| optional      | The business use case ID              | string            |
| id            |                                       |                   |
| optional      | The ID of the archiving policy - rule | string            |

| Name              | Description                                                                                                                                                                      | Schema          |
|-------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------|
| policy optional   | The archiving timer used by archiving process. Closed or forwarded cases will be archived after the specified timer (number of days - e.g.7 days a week, 365 days a year, etc. ) | integer (int32) |
| sector optional   | The name of the Sector                                                                                                                                                           | string          |
| sectorId optional | The ID of the Sector                                                                                                                                                             | string          |
| tenant optional   | The tenant                                                                                                                                                                       | string          |
| tenantId optional | The tenant ID                                                                                                                                                                    | string          |

## CaseRevisedDto

## Case Metadata

| Name                        | Description                                            | Schema                     |
|-----------------------------|--------------------------------------------------------|----------------------------|
| actions optional            | The list of Actions available in the Case              | < ActionRevisedDto > array |
| applicationRo leId optional | The application Role id                                | string                     |
| attachments optional        | The list of Attachments that are contained in the Case | < AttachementDto > array   |
| businessId optional         | Business Id of the Case                                | string                     |
| caseType optional           |                                                        | string                     |
| comments optional           | The list of comments in the Case                       | < CommentDto > array       |
| creator optional            | The creator User or Group of the Case                  | UserGroupDto               |

| Name                               | Description                                          | Schema                        |
|------------------------------------|------------------------------------------------------|-------------------------------|
| documents optional                 | The list of Documents that are contained in the Case | < DocumentRevisedDt o > array |
| hashCode optional                  | The hash Code of the Case                            | integer (int32)               |
| id optional                        | The id of the Case                                   | string                        |
| initialVariabl es optional         | The initial variables of the Case                    | < string, string > map        |
| internationalI d optional          | International correlation Id of the Case             | string                        |
| lastUpdate optional                | The date when the Case was last updated              | string (date-time)            |
| participants optional              | The list of Participants in the Case                 | < CaseParticipantDto > array  |
| processDefini tionName optional    | The Case's process definition Name                   | string                        |
| processDefini tionVersion optional | The Case's process definition Version                | string                        |
| properties optional                | The importance case property for assignments         | < string, string > map        |
| sensitive optional                 | The sensitivity status of the Case                   | boolean                       |
| sensitiveCom mitted optional       | If the sensitivity status has been committed         | boolean                       |

| Name               | Description                                                 | Schema                                         |
|--------------------|-------------------------------------------------------------|------------------------------------------------|
| startDate optional | The date that the Case is started                           | string (date-time)                             |
| status optional    | The current status of the Case                              | enum (OPEN, CLOSED, ACTIVE, REMOVED, ARCHIVED, |
| subject optional   | The subject Person or Organisation that the Case belongs to | EntityBaseDto                                  |

## CaseTimelineView

The Case Management Timeline View Settings

| Name                        | Description                          | Schema   |
|-----------------------------|--------------------------------------|----------|
| displayMode optional        | The display mode: one or two columns | string   |
| displayThumb nails optional | Show or hide the Thumbnails          | boolean  |

## CaseTraitsDto

Metadata of Specific Case Instance

| Name                          | Description                                                       | Schema   |
|-------------------------------|-------------------------------------------------------------------|----------|
| applicationRo leId optional   | The application role of the Case (Process Owner or Counter Party) | string   |
| id optional                   | The id of the Case                                                | string   |
| processDefini tionId optional | The process definition Id of the Case                             | string   |

| Name                | Description                                                                                         | Schema             |
|---------------------|-----------------------------------------------------------------------------------------------------|--------------------|
| properties optional | type is Map<String,String>, The pairs of key and value of the properties (urgency and importance) < | string, string map |
| status optional     | The status of the Case (open,closed,archived,removed)                                               | string             |
| traits optional     | type is Map<String,String>, The pairs of key and value of the traits <                              | string, string map |

## CheckBucketDto

Bucket of Check Instances

| Name                               | Description                        | Schema                     |
|------------------------------------|------------------------------------|----------------------------|
| checkInstance s optional read-only | The list of Check Instances        | < CheckInstanceDto > array |
| id optional                        | The id of the Check Bucket         | string                     |
| size optional                      | Total Number of Check Instances    | integer (int32)            |
| startDate optional                 | The Start Date of the Check Bucket | string                     |

## CheckDefinitionDto

Check Definition Details

| Name                    | Description                             | Schema   |
|-------------------------|-----------------------------------------|----------|
| checkCategor y optional | The category of the Check Definition    | string   |
| description optional    | The description of the Check Definition | string   |

| Name                | Description                                       | Schema               |
|---------------------|---------------------------------------------------|----------------------|
| id optional         | The id of the Check Definition                    | string               |
| name optional       | The name of the Check Definition                  | string               |
| properties optional | Properties of the Check Definition                | < string, string map |
| valid optional      | The validity of execution of the Check Definition | boolean              |

## CheckInstanceDto

Check Instance Details

| Name                          | Description                                    | Schema   |
|-------------------------------|------------------------------------------------|----------|
| checkDefiniti onId optional   | The id of the Check Definition of the instance | string   |
| endDate optional              | The Start Date of the Check Instance           | string   |
| id optional                   | The id of the Check Instance                   | string   |
| message optional              | The message of the Check Instance              | string   |
| name optional                 | The name of the Check Instance                 | string   |
| parentCheckB ucketId optional | The id of the parent Check Bucket              | string   |
| startDate optional            | The Start Date of the Check Instance           | string   |
| status optional               | The Status of the Check Instance               | string   |

## CommentDto

Comment details

| Name                | Description                                       | Schema             |
|---------------------|---------------------------------------------------|--------------------|
| caseId optional     | The Id of the Case that the comment refers to     | string             |
| comment optional    | The text of the Comment                           | string             |
| creator optional    | The creator User or Group of the Comment          | UserGroupDto       |
| date optional       | The date of creation of the Comment               | string (date-time) |
| documentId optional | The Id of the Document that the comment refers to | string             |
| id optional         | The id of the Comment                             | string             |

## ConceptDetailedRevisedDto

The concept detailed model - set of properties from datavocabularies.json

| Name                 | Schema   |
|----------------------|----------|
| alt_color optional   | string   |
| color optional       | string   |
| description optional | string   |
| icon optional        | string   |
| name optional        | string   |

| Name              | Schema   |
|-------------------|----------|
| severity optional | string   |
| template optional | string   |
| value optional    | string   |

## ContactMethodDto

Contact Method details

| Name           | Description                                      | Schema   |
|----------------|--------------------------------------------------|----------|
| type optional  | The type of the Contact Method                   | string   |
| value optional | The value of the specific type of Contact Method | string   |

## ConversationParticipantDto

Participating Institution in a conversation

| Name                  | Description                                                      | Schema                               |
|-----------------------|------------------------------------------------------------------|--------------------------------------|
| organisation optional | The Organisation/Institution that the participant corresponds to | EntityBaseDto                        |
| role optional         | The role of the participant in in a conversation or in a case    | enum (SENDER, RECEIVER, PARTICIPANT) |
| selected optional     | Is participant selected                                          | boolean                              |

## ConversationRevisedDto

Container of User Message exchanges between Organisations

| Name                  | Description                                                    | Schema                                |
|-----------------------|----------------------------------------------------------------|---------------------------------------|
| date optional         | The date of the Conversation                                   | string (date-time)                    |
| id optional           | The id of the conversation                                     | string                                |
| participants optional | The List of participants involved in the Conversation          | < ConversationPartici pantDto > array |
| receiveDate optional  | The date of the Conversation                                   | string (date-time)                    |
| userMessages optional | The List of User Messages included in the Conversation         | < UserMessageDto > array              |
| versionId optional    | The version id of the Document that the conversation refers to | string                                |

## DiskFileInfoDto

Information about a file on the disk

| Name              | Description                   | Schema   |
|-------------------|-------------------------------|----------|
| fullPath optional | The absolute path to the file | string   |

## DocumentDetailsRevisedDto

Base Class for Document, Attachment

| Name                  | Description                            | Schema                   |
|-----------------------|----------------------------------------|--------------------------|
| attachments optional  | The attachements of the Document       | < AttachementDto > array |
| comments optional     | The list of comments in the document   | < CommentDto > array     |
| creationDate optional | The date that the document was created | string (date-time)       |

| Name                     | Description                                            | Schema                                |
|--------------------------|--------------------------------------------------------|---------------------------------------|
| displayName optional     | Display name of the document                           | string                                |
| lastUpdate optional      | The date that the document was last updated            | string (date-time)                    |
| parentDocum ent optional | Parent document for given one                          | DocumentDetailsRev isedDto            |
| participants optional    | The List of participants involved in the conversations | < ConversationPartici pantDto > array |
| subdocument s optional   | List of subdocuments                                   | < DocumentDetailsRev isedDto > array  |
| type optional            | The type of the document                               | string                                |
| versionId optional       | Document version id                                    | string                                |

## DocumentIdentificationDto

The SED identification information

| Name                      | Description              | Schema                                                |
|---------------------------|--------------------------|-------------------------------------------------------|
| action optional           | The case action type     | enum (START, NEW, UPDATE, START_FORWARD, NEW_FORWARD) |
| contentLocati on optional | The SED content location | string                                                |
| creationDate optional     | The date of creation     | string (date-time)                                    |

| Name                           | Description                                                | Schema   |
|--------------------------------|------------------------------------------------------------|----------|
| id optional                    | The SED Id                                                 | string   |
| identifier optional            | The identification of the SED                              | string   |
| relatedDocum entId optional    | The Related Document Id                                    | string   |
| relatedSetIde ntifier optional | The ID of a document set to which this document is related | string   |
| schemaVersio n optional        | The XSD version                                            | string   |
| setIdentifier optional         | The identification of the set of SED                       | string   |
| type optional                  | The SED/document type                                      | string   |
| version optional               | The SED version                                            | string   |

## DocumentInfo

The SED details of the notification

| Name              | Description                                    | Schema        |
|-------------------|------------------------------------------------|---------------|
| id optional       |                                                | string        |
| name optional     | The document type name (Old age pension claim) | string        |
| receiver optional | The document recipient/receiver                | EntityBaseDto |

| Name                 | Description              | Schema   |
|----------------------|--------------------------|----------|
| type optional        | The document type(P2000) | string   |
| typeVersion optional |                          | string   |

## DocumentRevisedDto

Document details

| Name                            | Description                                               | Schema                            |
|---------------------------------|-----------------------------------------------------------|-----------------------------------|
| DMProcessId optional            | The process id of the document manager                    | integer (int64)                   |
| ParentType optional             | Parent type of this document                              | string                            |
| admin optional                  |                                                           | boolean                           |
| allowsAttach ments optional     | The document allows having attachments. Default is false. | boolean                           |
| attachments optional            | The attachements of the Document                          | < AttachementDto > array          |
| bulk optional                   | Whether or not the document is a Bulk(Batch) Document     | boolean                           |
| canBeSentWit houtChild optional | True if the document can be sent without any children.    | boolean                           |
| comments optional               | The comments on the Document                              | < CommentDto > array              |
| conversations optional          | The conversations related to the Document                 | < ConversationRevise dDto > array |

| Name                            | Description                                                                | Schema             |
|---------------------------------|----------------------------------------------------------------------------|--------------------|
| createTempla te optional        | Template for creating the document                                         | string             |
| creationDate optional           | The date that the Document was created                                     | string (date-time) |
| creator optional                | The creator User or Group of the Document                                  | UserGroupDto       |
| direction optional              | The direction of the Document                                              | enum (IN, OUT)     |
| displayName optional            | The display name of the Document                                           | string             |
| dmprocessId optional            |                                                                            | integer (int64)    |
| dummyDocu ment optional         |                                                                            | boolean            |
| firstDocumen t optional         |                                                                            | boolean            |
| hasBusinessV alidation optional | Requires any business side validation before any action. Default is false. | boolean            |
| hasCancel optional              | has cancel                                                                 | boolean            |
| hasClarify optional             | has clarify                                                                | boolean            |
| hasLetter optional              | Has letter                                                                 | boolean            |
| hasMultipleVe rsions optional   | True if the document has multiple versions                                 | boolean            |

| Name                      | Description                                 | Schema             |
|---------------------------|---------------------------------------------|--------------------|
| hasReject optional        | Has reject                                  | boolean            |
| hasReplyClari fy optional | Has reply clarify                           | boolean            |
| id optional               | The Id of the Document                      | string             |
| isAdmin optional          | If this is an admin document                | boolean            |
| isDummyDoc ument optional | True if the document is just a dummy.       | boolean            |
| isFirstDocum ent optional | True if this is the first document          | boolean            |
| isMLC optional            | True if this is MLC document                | boolean            |
| isSendExecute d optional  | If document already sent                    | boolean            |
| lastUpdate optional       | The date that the Document was last updated | string (date-time) |
| mimeType optional         | The mime type of the Document               | string             |
| mlc optional              |                                             | boolean            |
| name optional             | The name of the Document                    | string             |
| order optional            | Order                                       | integer (int32)    |

| Name                         | Description                                    | Schema                                               |
|------------------------------|------------------------------------------------|------------------------------------------------------|
| parentDocum entId optional   | The Id of the parent Document                  | string                                               |
| receiveDate optional         | Date when the document was received            | string (date-time)                                   |
| selectParticip ants optional | If select participants                         | boolean                                              |
| sendExecuted optional        |                                                | boolean                                              |
| starter optional             | If the document is the starter Document        | boolean                                              |
| status optional              | The status of the Document                     | enum (NEW, EMPTY, ACTIVE, SENT, CANCELLED, RECEIVED) |
| subProcessId optional        | The status of the Document                     | integer (int64)                                      |
| tags optional                | The tags on the Document                       | < string, string > map                               |
| toSenderOnly optional        | If the document is only to sender              | boolean                                              |
| type optional                | The type of the Document                       | string                                               |
| typeVersion optional         | The typeVersion of the Document                | string                                               |
| validation optional          | Validation status of a document or subdocument | ValidationResultDto                                  |
| versions optional            | The list of Versions of the Document           | < VersionDto > array                                 |

## Documents

The Case Management SED View Settings

| Name                 | Description                                                 | Schema   |
|----------------------|-------------------------------------------------------------|----------|
| displayMode optional | The display mode of the case documents: timeline or classic | string   |
| showFlags optional   | Enable/Disable displaying flags of the sender of a documen  | boolean  |
| sortBy optional      | Filed by which to sort documents: creationDate, lastUpdate  | string   |

## EntityBaseDto

Base Class for Entities: Organisation, Person, User Group

| Name                     | Description                               | Schema                     |
|--------------------------|-------------------------------------------|----------------------------|
| address optional         | The address of the Entity                 | AddressDto                 |
| contactMetho ds optional | The list of contact methods of the Entity | < ContactMethodDto > array |
| id optional              | The id of the Entity                      | string                     |

## ErrorDto

Error Message of a specific User Message from the receiver destination Institution

| Name                 | Description                          | Schema             |
|----------------------|--------------------------------------|--------------------|
| date optional        | The date when the error was received | string (date-time) |
| description optional | The description of the Error Message | string             |
| id optional          | The Id of the message                | string             |

| Name              | Description                           | Schema        |
|-------------------|---------------------------------------|---------------|
| receiver optional | The receiver Organisation/Institution | EntityBaseDto |
| sender optional   | The sender Organisation/Institution   | EntityBaseDto |

## Exception

Error Message details of a specific User Message from the receiver destination Insittution

| Name                 | Description                  | Schema   |
|----------------------|------------------------------|----------|
| code optional        | The code of the error        | string   |
| description optional | The description of the error | string   |

## ExtendedProperties

The caseInfo extended properties of the notification

| Name                   | Description                                   | Schema    |
|------------------------|-----------------------------------------------|-----------|
| failureReason optional | The failure reason details                    | Exception |
| reason optional        | The reason of the alarm, scheduled event, etc | string    |

## FailureReason

Information wrapper around the failure reason

| Name                 | Description                  | Schema   |
|----------------------|------------------------------|----------|
| code optional        | The code of the error        | string   |
| description optional | The description of the error | string   |

## FieldChooserDto

List of Fields to be shown in Case Search Results

| Name                          | Description                                                | Schema             |
|-------------------------------|------------------------------------------------------------|--------------------|
| fields optional               | The list of the Fields of the Field Chooser                | < FieldDto > array |
| processDefini tionId optional | The process definition Id that the Field Chooser refers to | string             |
| userName optional             | The user name that the Field Chooser belongs to            | string             |

## FieldDto

Field details in a specific Field Chooser instance

| Name          | Description                                               | Schema   |
|---------------|-----------------------------------------------------------|----------|
| id optional   | The Id of the Field                                       | string   |
| name optional | The Name of the Field                                     | string   |
| show optional | The flag to determine if the Field is to be shown or not  | boolean  |
| sort optional | The direction that the values of the Field will be sorted | string   |
| type optional | The Type of the Field                                     | string   |

## GroupDto

| Name                  | Description                    | Schema             |
|-----------------------|--------------------------------|--------------------|
| creationDate optional | The creation date of the Group | string (date-time) |

| Name                         | Description                          | Schema          |
|------------------------------|--------------------------------------|-----------------|
| description optional         | The description of the Group         | string          |
| displayName optional         | The display name of the Group        | string          |
| id optional                  | The id of the object                 | string          |
| institutionId optional       | The institutionId of the Group       | string          |
| isOrganisatio nUnit optional | If Group is an Organisation Unit     | boolean         |
| name optional                | The name of the Group                | string          |
| needReassign ment optional   |                                      | boolean         |
| organisationU nit optional   |                                      | boolean         |
| origin optional              | Origin of the Group                  | string          |
| parentGroupI d optional      | The id of the parent Group           | string          |
| parentPath optional          | The path of the parent of this Group | string          |
| path optional                | The path of the Group                | string          |
| version optional             | The version of the object            | integer (int64) |

## InstitutionAliasMappingDto

The mapping between aliases of the keys and institutions

| Name                              | Description                                                                                                   | Schema          |
|-----------------------------------|---------------------------------------------------------------------------------------------------------------|-----------------|
| default optional                  |                                                                                                               | boolean         |
| defaultBusine ssKeyAlias optional | The default alias of key, for the key stored in Business keystore                                             | string          |
| isPrivateKeyS tore optional       | True if the alias of key is stored in private keystore or false if the alias of key is stored in public store | boolean         |
| keyAlias optional                 | The key alias for the key stored in keystore                                                                  | string          |
| mpc optional                      | The business MPC of institution                                                                               | string          |
| organisation optional             | The organisation details                                                                                      | EntityBaseDto   |
| password optional                 | The password for the private key                                                                              | string          |
| privateKeySto re optional         |                                                                                                               | boolean         |
| pullingInterv al optional         | The specific pulling request interval of institution                                                          | integer (int32) |
| technicalKeyA lias optional       | The key alias for the key stored in keystore                                                                  | string          |
| technicalMpc optional             | The system MPC of institution                                                                                 | string          |

| Name                               | Description                                                 | Schema          |
|------------------------------------|-------------------------------------------------------------|-----------------|
| technicalPass word optional        | The technical password for the private key                  | string          |
| technicalPulli ngInterval optional | The specific system pulling request interval of institution | integer (int32) |

## LdapConnectionSettingsDto

LDAP connection settings

| Name                             | Description            | Schema   |
|----------------------------------|------------------------|----------|
| groupSearchB ase optional        | groupSearchBase        | string   |
| groupSearchS tring optional      | groupSearchString      | string   |
| id optional                      | The id of the object   | string   |
| institutionId optional           | Tenant id              | string   |
| password optional                | password               | string   |
| providerUrl optional             | providerUrl            | string   |
| securityAuthe ntication optional | securityAuthentication | string   |
| user optional                    | user                   | string   |

| Name                       | Description               | Schema          |
|----------------------------|---------------------------|-----------------|
| userSearchBa se optional   | userSearchBase            | string          |
| userSearchStr ing optional | userSearchString          | string          |
| version optional           | The version of the object | integer (int64) |

## LdapGroupParametersMappingDto

LDAP group parameters mapping

| Name                           | Description                      | Schema   |
|--------------------------------|----------------------------------|----------|
| creationDate optional          | The creation date of the Group   | string   |
| description optional           | The description of the Group     | string   |
| displayName optional           | The display name of the Group    | string   |
| id optional                    | The id of the object             | string   |
| institutionId optional         | Tenant id                        | string   |
| institutionId Mapping optional | The institutionId of the Group   | string   |
| isOrganisatio nUnit optional   | If Group is an Organisation Unit | string   |
| lastUpdate optional            | Last update of the entity        | string   |

| Name                          | Description                 | Schema          |
|-------------------------------|-----------------------------|-----------------|
| ldapUniqueId etifier optional | LDAP unique idetifier       | string          |
| members optional              | Members of groups           | string          |
| name optional                 | The name of the Group       | string          |
| needReassign ment optional    | If Group needs reassignment | string          |
| parentGroupI d optional       | The id of the parent Group  | string          |
| path optional                 | The path of the Group       | string          |
| version optional              | The version of the object   | integer (int64) |

## LdapUserParametersMappingDto

LDAP user parameters mapping

| Name                  | Description                   | Schema   |
|-----------------------|-------------------------------|----------|
| creationDate optional | The creation date of the User | string   |
| email optional        | The email address of the User | string   |
| firstName optional    | The first name of the User    | string   |
| groups optional       | User groups                   | string   |

| Name                           | Description                                        | Schema                                                                                             |
|--------------------------------|----------------------------------------------------|----------------------------------------------------------------------------------------------------|
| id optional                    | The id of the object                               | string                                                                                             |
| institutionId optional         | Tenant id                                          | string                                                                                             |
| institutionId Mapping optional | The institutionId of the Group                     | string                                                                                             |
| isAdministrat or optional      | Flag defining if this user is administrator or not | string                                                                                             |
| isEnabled optional             | Flag indicating if this user is enabled or not     | string                                                                                             |
| isLocked optional              | Flag indicating if the account is locked           | string                                                                                             |
| lastName optional              | The last name of the User                          | string                                                                                             |
| lastUpdate optional            | Last update of the entity                          | string                                                                                             |
| ldapUniqueId etifier optional  | LDAP unique idetifier                              | string                                                                                             |
| phoneNumber optional           | Phone number                                       | string                                                                                             |
| role optional                  | Role for given synchronization                     | enum (SUPERVISOR, AUTHORIZED_CLER K, UNAUTHORIZED_CL ERK, AUDITOR, VIEWER, MEDICAL, VIP, EVERYONE) |
| username optional              | The user-name of the User                          | string                                                                                             |

| Name             | Description               | Schema          |
|------------------|---------------------------|-----------------|
| version optional | The version of the object | integer (int64) |

## LocalizationSettings

The localization preferences and settings of a user

| Name                   | Description               | Schema   |
|------------------------|---------------------------|----------|
| currency optional      | The currency              | string   |
| dateFormat optional    | The format of the dates   | string   |
| language optional      | The language              | string   |
| numberForm at optional | The format of the numbers | string   |
| timeFormat optional    | The format of the time    | string   |
| timeZone optional      | The time zone             | string   |

## MembershipDto

User membership details

| Name           | Description                            | Schema   |
|----------------|----------------------------------------|----------|
| group optional | The group of which the user is part of | GroupDto |

| Name          | Description         | Schema                                                                                             |
|---------------|---------------------|----------------------------------------------------------------------------------------------------|
| role optional | The membership role | enum (SUPERVISOR, AUTHORIZED_CLER K, UNAUTHORIZED_CL ERK, AUDITOR, VIEWER, MEDICAL, VIP, EVERYONE) |

## Message

The Message (Audit Event) properties

| Name                      | Description                                                                                                   | Schema                                       |
|---------------------------|---------------------------------------------------------------------------------------------------------------|----------------------------------------------|
| action optional           | The type of action which is executed which can be one of the following: create, read, update, delete, execute | enum (CREATE, UPDATE, READ, DELETE, EXECUTE) |
| auditedObject s optional  | The audited objects which are identified by id, type and details                                              | < AuditedObjects > array                     |
| date optional             | Date of the audit event                                                                                       | string                                       |
| id optional               | The ID of the audit event                                                                                     | string                                       |
| networkLocat ion optional | The network location are the identification details (machine & IP) on which the action has been triggered     | NetworkLocationDto                           |
| outcome optional          | The outcome of the action triggered which can be success , error or unauthorised                              | enum (SUCCESS, ERROR, UNAUTHORIZED)          |
| outcomeDetai ls optional  | When outcome is error or unauthorised, the outcomeError contains the error message.                           | string                                       |
| participants optional     | The list of participants to the triggered action.                                                             | < Participants > array                       |

| Name              | Description                                                                    | Schema   |
|-------------------|--------------------------------------------------------------------------------|----------|
| source optional   | The source of the event which has three attributes (category, component, type) | Source   |
| userName optional | The username of the user who triggered the action                              | string   |

## MessageBaseDto

Base Class Of Message between Organisations

| Name              | Description                           | Schema        |
|-------------------|---------------------------------------|---------------|
| id optional       | The Id of the message                 | string        |
| receiver optional | The receiver Organisation/Institution | EntityBaseDto |
| sender optional   | The sender Organisation/Institution   | EntityBaseDto |

## MessagesRetentionPoliciesDto

Retention policies for messages

| Name                                     | Description                           | Schema          |
|------------------------------------------|---------------------------------------|-----------------|
| defaultMessag eRetentionPer iod optional | The retention period for the messages | integer (int32) |

## MessagingClusterNodeDto

Messaging cluster node specific details

| Name               | Description                      | Schema   |
|--------------------|----------------------------------|----------|
| name optional      | The node name                    | string   |
| pmodePath optional | The local pull pmode folder path | string   |

## MessagingSettingsDto

The messaging settings

| Name                                    | Description                                                 | Schema                                |
|-----------------------------------------|-------------------------------------------------------------|---------------------------------------|
| antimalwareI nfectedSetting s optional  | Additional settings of antimalware check for infected files | string                                |
| antimalware Mode optional               | What kind of antimalware check should be made.              | enum (NONE, PERIODIC, INSTANT)        |
| antimalwareS ettings optional           | Additional settings of antimalware check                    | string                                |
| bmpValidatio nMode optional             | The Business Messaging Protocol Validation                  | string                                |
| businessKeyA liasPasswordL ist optional |                                                             | < BusinessKeyAliasPas sword > array   |
| businessKeyst orePassword optional      |                                                             | string                                |
| clusterNodes optional                   | The list of cluster nodes                                   | < MessagingClusterNo deDto > array    |
| defaultPulling Interval optional        | Default pulling interval                                    | integer (int32)                       |
| institutionAli asMappings optional      | The mapping between aliases of the keys and institutions    | < InstitutionAliasMap pingDto > array |

| Name                               | Description                                                             | Schema                              |
|------------------------------------|-------------------------------------------------------------------------|-------------------------------------|
| maxMessageS ize optional           | Specify the maximum size of a message                                   | integer (int64)                     |
| maxRetries optional                | Maximum number of retries                                               | integer (int32)                     |
| mshPath optional                   | The root path of MSH                                                    | string                              |
| operationMod e optional            | Determine if client should work in loopback, AP mode or Rina2Rina mode. | enum (AP_MODE, RINA2RINA, LOOPBACK) |
| privateKeysto reAliasList optional | The list of the private aliases from private keystore                   | < string > array                    |
| privateKeysto rePassword optional  | The password to access the private keystore                             | string                              |
| publicKeystor eAliasList optional  | The list of the private aliases from public keystore                    | < string > array                    |
| publicKeystor ePassword optional   | The password to access the public truststore                            | string                              |
| retryInterval optional             | The retry interval                                                      | integer (int32)                     |
| tlsKeystoreAli asList optional     | The list of the private aliases from TLS keystore                       | < string > array                    |
| tlsKeystorePa ssword optional      | The password to access the TLS keystore                                 | string                              |
| tlsTruststoreA liasList optional   | The list of the aliases from TLS truststore                             | < string > array                    |

| Name                            | Description                                          | Schema   |
|---------------------------------|------------------------------------------------------|----------|
| tlsTruststoreP assword optional | The password to access the TLS truststore            | string   |
| useCompressi on optional        | The compression will be used if is true              | boolean  |
| usePullMode optional            | If use pull mode or push mode                        | boolean  |
| whoamiId optional               | The organisation / Institution id of the application | string   |
| xsdRepository                   |                                                      |          |
| Path optional                   | The path to the xsd repository                       | string   |

## NetworkLocationDto

## Network location

| Name             | Description   | Schema   |
|------------------|---------------|----------|
| ip optional      | IP address    | string   |
| machine optional | Machine name  | string   |

## NieListenerDto

The NIE subscription listener

| Name           | Description               | Schema   |
|----------------|---------------------------|----------|
| id optional    | The id of listener        | string   |
| label optional | The label of the listener | string   |

| Name              | Description   | Schema   |
|-------------------|---------------|----------|
| listener optional | The listener  | string   |

## NieNotificationDto

The NIE notification listener

| Name           | Description                   | Schema   |
|----------------|-------------------------------|----------|
| id optional    | The id of notification        | string   |
| label optional | The label of the notification | string   |
| url optional   | The URL                       | string   |

## NieSubscriberDto

The NIE subscriber

| Name             | Description                   | Schema   |
|------------------|-------------------------------|----------|
| id optional      | The id of NIE subscriber      | string   |
| version optional | The version of NIE subscriber | string   |

## NieSubscriptionDto

The NIE subscription

| Name          | Description                | Schema   |
|---------------|----------------------------|----------|
| case optional |                            | boolean  |
| id optional   | The id of NIE subscription | string   |

| Name                       | Description                                                                                                       | Schema                       |
|----------------------------|-------------------------------------------------------------------------------------------------------------------|------------------------------|
| isCase optional            | Flag that indicate if is a subscription of a cases or of a documents; when true is a cases and false is documents | boolean                      |
| listeners optional         | The listeners list to be called when events of this type occurs                                                   | < NieListenerDto > array     |
| notifications optional     | The list of notifications subscribers                                                                             | < NieNotificationDto > array |
| subscribers optional       | The subscriber participating to the subscription                                                                  | < NieSubscriberDto > array   |
| subscriptionN ame optional | The name of subscription                                                                                          | string                       |

## NieSubscriptionsDto

The NIE subscriptions settings

| Name                          | Description                                                     | Schema                       |
|-------------------------------|-----------------------------------------------------------------|------------------------------|
| eventsSubscri ptions optional | The list of NIE subscriptions                                   | < NieSubscriptionDto > array |
| nieClientImpl Class optional  | The fully qualified name of the NIE client implementation class | string                       |

## NotificationDto

The Notification details

| Name                              | Description                                       | Schema            |
|-----------------------------------|---------------------------------------------------|-------------------|
| assignmentRe quest optional       | The roles associated to the assignment request    | AssignmentRequest |
| assignmentRe questStatus optional | The assignment request status of the notification | string            |

| Name                         | Description                                          | Schema                 |
|------------------------------|------------------------------------------------------|------------------------|
| caseId optional              | The id of the case for this notification             | string                 |
| caseInfo optional            | The case details referred by notification            | CaseInfoDto            |
| category optional            | The category of the notification                     | string                 |
| creationDate optional        | The creation date of the notification                | string                 |
| creator optional             | The user who created the notification (e.g. system)  | UserGroupDto           |
| document optional            | The referred document details                        | DocumentInfo           |
| dueDate optional             | The due date of the notification                     | string                 |
| extendedProp erties optional | Notification extended properties like failure reason | ExtendedProperties     |
| failureReason optional       | The information about the failure reason             | FailureReason          |
| id optional                  | The id of the Notification                           | string                 |
| isRead optional              | Is the notification read?                            | string                 |
| lastUpdate optional          | The last update of the notification                  | string                 |
| reason optional              | The reason of the Notification                       | string                 |
| responsiblePa rties optional | The parties which will receive the notifications     | < UserGroupDto > array |

| Name                | Description                                                 | Schema   |
|---------------------|-------------------------------------------------------------|----------|
| severity optional   | The type of severity (e.g. warning, error, information)     | string   |
| sourceType optional | The source of the notification (messaging, business, other) | string   |
| status optional     | The status of the notification                              | string   |
| type optional       | The type of the notification (e.g. new message arrived)     | string   |

## NotificationRevisedDto

The Notification details

| Name                              | Description                                         | Schema             |
|-----------------------------------|-----------------------------------------------------|--------------------|
| assignmentRe quest optional       | The roles associated to the assignment request      | AssignmentRequest  |
| assignmentRe questStatus optional | The assignment request status of the notification   | string             |
| caseId optional                   | The id of the case for this notification            | string             |
| caseInfo optional                 | The case details referred by notification           | CaseInfoDto        |
| category optional                 | The category of the notification                    | string             |
| creationDate optional             | The creation date of the notification               | string (date-time) |
| creator optional                  | The user who created the notification (e.g. system) | UserGroupDto       |
| document optional                 | The referred document details                       | DocumentInfo       |

| Name                         | Description                                                 | Schema                 |
|------------------------------|-------------------------------------------------------------|------------------------|
| dueDate optional             | The due date of the notification                            | string (date-time)     |
| extendedProp erties optional | Notification extended properties like failure reason        | ExtendedProperties     |
| failureReason optional       | The information about the failure reason                    | FailureReason          |
| id optional                  | The id of the Notification                                  | string                 |
| isRead optional              | Is the notification read?                                   | string                 |
| lastUpdate optional          | The last update of the notification                         | string                 |
| reason optional              | The reason of the Notification                              | string                 |
| responsiblePa rties optional | The parties which will receive the notifications            | < UserGroupDto > array |
| severity optional            | The type of severity (e.g. warning, error, information)     | string                 |
| sourceType optional          | The source of the notification (messaging, business, other) | string                 |
| status optional              | The status of the notification                              | string                 |
| type optional                | The type of the notification (e.g. new message arrived)     | string                 |

## NotificationsConsolidatedSummaryDto

| Name                 | Description                    | Schema          |
|----------------------|--------------------------------|-----------------|
| error optional       | Number of errors               | integer (int64) |
| information optional | Number of infos                | integer (int64) |
| unread optional      | Number of unread notifications | integer (int64) |
| warning optional     | Number of warnings             | integer (int64) |

## NotificationsSummaryDto

| Name                 | Description                  | Schema           |
|----------------------|------------------------------|------------------|
| error optional       | List of errors               | < string > array |
| information optional | Number of infos              | < string > array |
| unread optional      | List of unread notifications | < string > array |
| warning optional     | Number of warnings           | < string > array |

## NotificationsTimeSlotDto

The time slot information for notifications

| Name            | Description                                 | Schema             |
|-----------------|---------------------------------------------|--------------------|
| date optional   | The day of the slot                         | string (date-time) |
| number optional | The number of the notifications in the slot | string             |

## OrganisationDto

Polymorphism : Composition

| Name                     | Description                                                                  | Schema                     |
|--------------------------|------------------------------------------------------------------------------|----------------------------|
| accessPoint optional     | The access point that the Organisation belongs to                            | AccessPointDto             |
| acronym optional         | The acronym of the Organisation/Institution                                  | string                     |
| activeSince optional     | The date that the Organisation/Institution is active since                   | string (date-time)         |
| address optional         | The address of the Entity                                                    | AddressDto                 |
| assignedBUCs optional    | The list of assigned BUCs for current Organisation                           | < AssignedBUCDto > array   |
| contactMetho ds optional | The list of contact methods of the Entity                                    | < ContactMethodDto > array |
| countryCode optional     | The country code of the country that the Organisation/Institution belongs to | string                     |
| id optional              | The id of the Entity                                                         | string                     |
| location optional        | The geographical location of the Organisation/Institution                    | string                     |
| name optional            | The name of the Organisation/Institution                                     | string                     |
| registryNumb er optional | The registry number of the Organisation/Institution                          | string                     |

## OrganisationRevisedDto

Institution Details

| Name                     | Description                                                                  | Schema                                                                                                                                |
|--------------------------|------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------|
| accessPoint optional     | The access point that the Organisation belongs to                            | AccessPointDto                                                                                                                        |
| acronym optional         | The acronym of the Organisation/Institution                                  | string                                                                                                                                |
| activeSince optional     | The date that the Organisation/Institution is active since                   | string (date-time)                                                                                                                    |
| address optional         | The address of the Entity                                                    | AddressDto                                                                                                                            |
| assignedBUCs optional    | The list of assigned BUCs for current Organisation                           | < AssignedBUCDto > array                                                                                                              |
| contactMetho ds optional | The list of contact methods of the Entity                                    | < ContactMethodDto > array                                                                                                            |
| countryCode optional     | The country code of the country that the Organisation/Institution belongs to | enum (AT, BE, BG, CH, CY, CZ, DE, DK, EE, EL, ES, FI, FR, HR, HU, IS, IE, IT, LV, LI, LT, LU, MT, NL, NO, PL, PT, RO, SE, SI, SK, UK) |
| id optional              | The id of the Entity                                                         | string                                                                                                                                |
| location optional        | The geographical location of the Organisation/Institution                    | string                                                                                                                                |
| name optional            | The name of the Organisation/Institution                                     | string                                                                                                                                |
| registryNumb er optional | The registry number of the Organisation/Institution                          | string                                                                                                                                |

## ParticipantDto

Participating Institution in a conversation or case instance

| Name                  | Description                                                      | Schema        |
|-----------------------|------------------------------------------------------------------|---------------|
| organisation optional | The Organisation/Institution that the participant corresponds to | EntityBaseDto |
| role optional         | The role of the participant in in a conversation or in a case    | string        |
| selected optional     | Is participant selected                                          | boolean       |

## Participants

The participant which are taking part to a triggered event.

| Name          | Description                                                                                   | Schema                           |
|---------------|-----------------------------------------------------------------------------------------------|----------------------------------|
| id optional   | The id of the participant                                                                     | string                           |
| role optional | The role of participant in a triggered event/audited object (i.e. sender , receiver, subject) | enum (SENDER, RECEIVER, SUBJECT) |
| type optional | The type of the participant which can be person or organisation                               | enum (PERSON, ORGANISATION)      |

## PartnerDto

Standard business document header

| Name                            | Description                                  | Schema                                                                       |
|---------------------------------|----------------------------------------------|------------------------------------------------------------------------------|
| authority optional              | The authority that regulates the identifiers | string                                                                       |
| contactTypeId entifier optional | The role of the partner                      | enum (CASE_OWNER, COUNTERPARTY, DATASOURCE, DATADESTINATION, INTELLIGENT_RA) |
| identifier optional             | The participant's identifier                 | string                                                                       |

## PendingMessageDto

| Name                               | Description                                                                   | Schema                                 |
|------------------------------------|-------------------------------------------------------------------------------|----------------------------------------|
| BUCType optional                   | The type of the BUC                                                           | BUCTypeDto                             |
| SEDType optional                   | The type information of the BUC                                               | SEDTypeDto                             |
| actionType optional                | Message Action Type                                                           | string                                 |
| atachmentIde ntifications optional | The list of attachment identification information                             | < AttachmentIdentific ationDto > array |
| buctype optional                   |                                                                               | BUCTypeDto                             |
| cause optional                     | The cause of the pending message, ex: case missing, SED update without create | string                                 |
| date optional                      | The creation date of the message                                              | string                                 |
| documentIde ntification optional   | The SED identification information                                            | DocumentIdentificat ionDto             |
| id optional                        | The id of the pending message                                                 | string                                 |
| international CaseId optional      | The international case id                                                     | string                                 |
| localCaseId optional               | The local case id                                                             | string                                 |
| participants optional              | The participants(organizations) of the conversation of the message            | < ParticipantDto > array               |

| Name             | Description                                       | Schema        |
|------------------|---------------------------------------------------|---------------|
| processOwner     |                                                   |               |
| Id optional      | The Process Owner (organization) id of the case   | string        |
| protectedPers    |                                                   |               |
| on optional      | The list of attachment identification information | boolean       |
| receiver         |                                                   |               |
| optional         | The receiver(organization) of the message         | EntityBaseDto |
| sedtype optional |                                                   | SEDTypeDto    |
| sender optional  | The sender(organization) of the message           | EntityBaseDto |

## PersonDto

Polymorphism : Composition

| Name                     | Description                               | Schema                     |
|--------------------------|-------------------------------------------|----------------------------|
| address optional         | The address of the Entity                 | AddressDto                 |
| age optional             | The age of the Person                     | string                     |
| birthday optional        | The birthday of the Person                | string (date-time)         |
| contactMetho ds optional | The list of contact methods of the Entity | < ContactMethodDto > array |
| id optional              | The id of the Entity                      | string                     |
| name optional            | The name of the Person                    | string                     |

| Name             | Description               | Schema   |
|------------------|---------------------------|----------|
| pid optional     | The pid of the Person     | string   |
| sex optional     | The sex of the Person     | string   |
| surname optional | The surname of the Person | string   |
| title optional   | The title of the Person   | string   |

## Principal

| Name          | Schema   |
|---------------|----------|
| name optional | string   |

## ProcessDefinitionDto

Process Definition Details

| Name                          | Description                                        | Schema                                 |
|-------------------------------|----------------------------------------------------|----------------------------------------|
| defaultFieldC hooser optional | The default FieldChooser of the Process Definition | FieldChooserDto                        |
| id optional                   | The id of the Process Definition                   | string                                 |
| name optional                 | The name of the Process Definition                 | string                                 |
| sector optional               | The sector of the Process Definition               | string                                 |
| versions optional             | The list of versions of the Process Definition     | < ProcessDefinitionVe rsionDto > array |

## ProcessDefinitionVersionDto

Process Definition Version Details

| Name                | Description                                                             | Schema   |
|---------------------|-------------------------------------------------------------------------|----------|
| activeFrom optional | The activation/valability date of the version of the Process Definition | string   |
| activeTo optional   | The activation/valability date of the version of the Process Definition | string   |
| version optional    | The version of the Process Definition                                   | string   |

## PublicKey

| Name               | Schema                  |
|--------------------|-------------------------|
| algorithm optional | string                  |
| encoded optional   | < string (byte) > array |
| format optional    | string                  |

## RESTCertificate

Certificate Details

| Name                          | Description                             | Schema   |
|-------------------------------|-----------------------------------------|----------|
| alias optional                | The alias of the key in the keystore    | string   |
| certificatePas sword optional | The password of the private certificate | string   |
| certificatePat h optional     | The certificate path                    | string   |

| Name              | Description                  | Schema   |
|-------------------|------------------------------|----------|
| password optional | The password of the keystore | string   |

## RESTException

Error Message of a specific error/exception occured while processing a request

| Name                        | Description                        | Schema   |
|-----------------------------|------------------------------------|----------|
| error optional              | The short message of the Exception | string   |
| error_descrip tion optional | The description of the Exception   | string   |
| stack optional              | The stack of the Exception         | string   |

## RESTId

ID wrapper

| Name        | Description          | Schema   |
|-------------|----------------------|----------|
| id optional | The id of any object | string   |

## RESTKeystoreAlias

Wrapper around the alias from a keystore

| Name           | Description                 | Schema   |
|----------------|-----------------------------|----------|
| alias optional | The alias of keystore entry | string   |

## RESTSubdocument

Subdocument details

| Name                          | Description                                 | Schema                   |
|-------------------------------|---------------------------------------------|--------------------------|
| attachments optional          | The attachments of the Subdocument          | < AttachementDto > array |
| creationDate optional         | The date that the Document was created      | string (date-time)       |
| creator optional              | The creator User or Group of the Document   | UserGroupDto             |
| hasMultipleVe rsions optional | True if the document has multiple versions  | boolean                  |
| id optional                   | The Id of the Document                      | string                   |
| lastUpdate optional           | The date that the Document was last updated | string (date-time)       |
| mimeType optional             | The mime type of the Document               | string                   |
| name optional                 | The name of the Document                    | string                   |
| parentDocum entId optional    | The Id of the parent Document               | string                   |
| traits optional               | The searchable traits of the subdocument    | < string, string > map   |
| type optional                 | The type of the parent Document             | string                   |
| versions optional             | The list of Versions of the Document        | < VersionDto > array     |

## RESTSubdocumentGroup

Details of a group of related subdocuments

| Name                   | Description                                                                                             | Schema                    |
|------------------------|---------------------------------------------------------------------------------------------------------|---------------------------|
| id optional            | The id of the Subdocument Group                                                                         | string                    |
| no optional            | A numberic value indicating the order of this Subdocument Group in a list of subdocument search results | number (double)           |
| subdocument s optional | The list of subdocuments in this Subdocument Group                                                      | < RESTSubdocument > array |

## RESTSubdocumentList

Subdocument list details

| Name                | Description                           | Schema                          |
|---------------------|---------------------------------------|---------------------------------|
| items optional      | The subdocuments in this list         | < RESTSubdocumentG roup > array |
| totalCount optional | The total count of items in this list | integer (int64)                 |

## RESTValidation

Validation status of a document or subdocument

| Name              | Description         | Schema           |
|-------------------|---------------------|------------------|
| messages optional | Validation messages | < string > array |
| status optional   | Validation status   | string           |

## ResourceRevisedDto

The information about components that are installed as part of RINA

| Name          | Description              | Schema             |
|---------------|--------------------------|--------------------|
| date optional | The date of the Resource | string (date-time) |

| Name               | Description                 | Schema                                                                                                                                |
|--------------------|-----------------------------|---------------------------------------------------------------------------------------------------------------------------------------|
| id optional        | The id of the Resource      | string                                                                                                                                |
| storageId optional | A storageId of the Resource | string                                                                                                                                |
| tag optional       | A tag of the Resource       | string                                                                                                                                |
| type optional      | The type of the Resource    | enum (organisation, vocabulary, initialdoc, process, sbdh, sed, transaction, form, report, APPLICATION, letterTemplate, localization) |
| version optional   | The version of the Resource | string                                                                                                                                |

## RetentionMessagesPoliciesDto

Retention messages policies details

| Name                                     | Description                                                                                                                  | Schema          |
|------------------------------------------|------------------------------------------------------------------------------------------------------------------------------|-----------------|
| defaultMessag eRetentionPer iod optional | The retention timer used by message archiving process. Archived messages will be deleted after the specified timer (in days) | integer (int32) |

## RetentionPoliciesDto

Retention policies details

| Name                                | Schema                           |
|-------------------------------------|----------------------------------|
| caseRetentionPoliciesTable optional | < CaseRetentionPolicyDto > array |

| Name                                   | Schema          |
|----------------------------------------|-----------------|
| defaultCaseRetentionPeriod required    | integer (int32) |
| defaultMessageRetentionPeriod optional | integer (int32) |

## SEDTypeDto

The SED type identification information

| Name                  | Description                | Schema   |
|-----------------------|----------------------------|----------|
| id optional           | The SED type Id            | string   |
| name optional         | The SED type name          | string   |
| readTemplate optional | The SED read template name | string   |
| version optional      | The SED type version       | string   |

## SearchDefinitionDto

Details of predefined Search

| Name                   | Description                              | Schema             |
|------------------------|------------------------------------------|--------------------|
| color optional         | The color of the predefined Search       | string             |
| criticalities optional | The criticalities of the cases           | < string > array   |
| endDate optional       | The end date of the custom time interval | string (date-time) |
| id optional            | The id of the predefined Search          | string             |

| Name                         | Description                                               | Schema                                                                                    |
|------------------------------|-----------------------------------------------------------|-------------------------------------------------------------------------------------------|
| importances optional         | The importance of the cases                               | < string > array                                                                          |
| name optional                | The name of the predefined Search                         | string                                                                                    |
| participants optional        | The participants of a case                                | < EntityBaseDto > array                                                                   |
| processDefini tions optional | A list of possible process definitions                    | < ProcessDefinitionDt o > array                                                           |
| startDate optional           | The start date of the custom time interval                | string (date-time)                                                                        |
| statuses optional            | The statuses of the cases                                 | < string > array                                                                          |
| timeIntervalT ype optional   | The type of the time interval                             | enum (ANY_TIME, PAST_HOUR, PAST_24_HOURS, PAST_MONTH, PAST_WEEK, PAST_YEAR, CUSTOM_RANGE) |
| userGroups optional          | The user names or the group part of the cases assignments | < UserGroupDto > array                                                                    |
| userName optional            | The username of the owner of this definition              | string                                                                                    |

## SectorDto

Sector details

| Name          | Description            | Schema   |
|---------------|------------------------|----------|
| code optional | The code of the Sector | string   |

| Name                         | Description                                                  | Schema                          |
|------------------------------|--------------------------------------------------------------|---------------------------------|
| id optional                  | The id of the Sector                                         | string                          |
| name optional                | The name of the Sector                                       | string                          |
| processDefini tions optional | The list of the Process Definitions that the Sector contains | < ProcessDefinitionDt o > array |

## SedDto

| Name             | Description             | Schema               |
|------------------|-------------------------|----------------------|
| content optional | The Icontent of the SED | < string, object map |
| id optional      | The Id of the Sed       | string               |

## SedIdentificationDto

| Name                  | Description                | Schema   |
|-----------------------|----------------------------|----------|
| id optional           | The SED Id                 | string   |
| readTemplate optional | The SED read template name | string   |
| typeId optional       | The SED type Id            | string   |
| typeVersion optional  | The SED type version       | string   |
| version optional      | The SED version            | string   |

## Source

Details and identify the source of an event.

| Name                    | Description                                                                                             | Schema                                                                                                                                                  |
|-------------------------|---------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|
| categoryType optional   | The category of an event source (i.e. messaging, security, business)                                    | enum (MESSAGING, SECURITY, BUSINESS)                                                                                                                    |
| componentTy pe optional | The component of an event source (e.g. attachment, case, business messaging, technical messaging, etc.) | enum (ATTACHMENTS, CASES, COMMENTS, DOCUMENTS, NOTIFICATIONS, SEARCH_DEFINITIO NS, SECURITY, ADMINISTRATION, BUSINESS_MESSAGI NG, TECHNICAL_MESSA GING) |

| Name               | Description                                                                              | Schema                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|--------------------|------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| eventType optional | The type of an event source which consist in the actual action which triggered the event | enum (SUBMIT_ATTACHM ENT_ON_CASE, DELETE_ATTACHME NT_ON_CASE, RETRIEVE_ATTACH MENT_ON_CASE, SUBMIT_ATTACHME NT_ON_DOCUMENT, RETRIEVE_ATTACH MENT_ON_DOCUME NT, DELETE_ATTACHME NT_ON_DOCUMENT, SEARCH_CASES_BY_ SEARCH_DEFINITIO N_AND_OR_FREE_TE XT, RETRIEVE_CASE_BY_ ID, RETRIEVE_CASE_BY_ BUSINESS_ID, RETRIEVE_CASE_BY_ INTERNATIONAL_ID , RETRIEVE_CASE_ID_ BY_INTERNATIONA L_ID, CREATE_NEW_CASE, ASSIGN_CASE, UPDATE_CASE_SENS ITIVE, SET_CASE_METADA TA, RETRIEVE_CASE_HA SHCODE_BY_ID, RETRIEVE_CASE_AS SIGNMENTS, ARCHIVE_UNARCHI VE_CASE, RECEIVE_NEW_CAS E, SUBMIT_COMMENT_ ON_CASE, DELETE_COMMENT_ ON_CASE, SUBMIT_COMMENT_ ON_DOCUMENT, |

## StandardBusinessDocumentHeaderDto

Standard business document header DELETE\_COMMENT\_ ON\_DOCUMENT, RETRIEVE\_INITIAL\_

ATION\_SUMMARY,

| Name                             | Description                                                  | DOCUMENT, Schema                                                             |
|----------------------------------|--------------------------------------------------------------|------------------------------------------------------------------------------|
| attachments optional             | Attachment identification                                    | SUBMIT_DOCUMEN T, RETRIEVE_DOCUME NT, < AttachmentIdentific ationDto > array |
| caseIdentifica tion optional     | The business context all the information related to the case | RETRIEVE_THUMBN AIL, CREATE_DOCUMEN T, CaseIdentificationDt o                |
| documentIde ntification optional | All the SED information                                      | UPDATE_DOCUMEN T, DELETE_DOCUMEN T, DocumentIdentificat ionDto               |
| headerVersio n optional          | The SBDH version                                             | SEND_DOCUMENT, IMPORT_BATCH, EXPORT_BATCH, LOG_IN, LOG_OUT, string           |
| receivers optional               | The list of the receiver participants                        | RETRIEVE_NOTIFIC ATIONS_DETAILS, RETRIEVE_NOTIFIC < PartnerDto > array       |
| sender optional                  | The sender participant                                       | ATIONS_CONSOLID ATED_SUMMARY, RETRIEVE_NOTIFIC PartnerDto                    |

## SyncInitialDocumentDto

| Name                      | Description                         | ION, CREATE_SEARCH_D Schema                                  |
|---------------------------|-------------------------------------|--------------------------------------------------------------|
| initialDocume nt optional | The initial document                | EFINITION, UPDATE_SEARCH_D EFINITION, < string, object > map |
| type optional             | The type of the SYN Document        | DELETE_SEARCH_D EFINITION, UPDATE_USER_PRO string            |
| typeVersion optional      | The typeVersion of the SYN Document | FILE, UPDATE_APPLICATI ON_PROFILE, string                    |

## TagDto

Tags

## RETRIEVE\_NOTIFIC ATION\_TIME\_SLOTS, UPDATE\_NOTIFICAT

UP,

UPDATE\_USER\_GRO

UP,

DELETE\_USER\_GRO

UP,

CHANGE\_AUTHORIZ

| Name                 | Description   | Schema                                                                                                                                                                                                                                                                    |
|----------------------|---------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| DMProcessId optional | DMProcessId   | ATION_POLICY, SEND_BUSINESS_ME integer (int64)                                                                                                                                                                                                                            |
|                      |               | NOTIFY_ABOUT_REC EIVED_BUSINESS_M ESSAGE, NOTIFY_ABOUT_STA TUS_UPDATE, RECEIVE_BUSINESS_ MESSAGE, PROCESS_RECEIVED _BUSINESS_MESSAG E, SEND_TECHNICAL_ MESSAGE, RECEIVE_TECHNICA L_MESSAGE, APPLICATION_STAR T, APPLICATION_END, SET_ALARM, CLEAR_ALARM, EXECUTE_CASE_ASS |

| Name               | Description    |                                                                                                                                                                                                                                                                                                                                                                                                   |
|--------------------|----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Operation optional | Operation type | Schema enum (CREATE, UPDATE, SEND, DELETE, SUBDOCUMENT, CREATE_LETTER, READ, CLOSE, REOPEN, DELETE_CASE, LOCAL_CLOSE, LOCAL_REOPEN, ARCHIVE_CASE, BACKUP_CASE, RESTORE_CASE, SEND_PARTICIPANT S, SELECT_PARTICIPA NTS, READ_PARTICIPANT S, UPDATE_PARTICIPA NTS, ADD_ATTACHMENT, REQUEST_APPROVA L, ADD_SUBDOCUMEN T, UPDATE_SUBDOCU MENT, REMOVE_SUBDOCU MENT, IMPORT_SUBDOCU MENT, CREATE_CASE, |

| Name                 | Description   | Schema                                                              |
|----------------------|---------------|---------------------------------------------------------------------|
| category optional    | Category      | enum (CASE_ACTIONS, DOCUMENTS, HORIZONTAL_DOCU MENTS, PARTICIPANTS) |
| dmprocessId optional |               | integer (int64)                                                     |
| type optional        | Tags          | enum (ADMIN, SECTORIAL)                                             |

## TechnicalLogsDetailDto

Technical logs details

| Name                 | Description                                                                             | Schema          |
|----------------------|-----------------------------------------------------------------------------------------|-----------------|
| @timestamp optional  | Timestamp of the log entry                                                              | string          |
| @version optional    | Version                                                                                 | string          |
| btm-gtrid optional   | Btm-grid                                                                                | string          |
| host optional        | The network machine (IP address) who generated the log entry                            | string          |
| logger_name optional | Technical attribute consisting in the full Java class name that generated the log entry | string          |
| message optional     | The actual technical log entry message                                                  | string          |
| port optional        | Port                                                                                    | integer (int64) |
| priority optional    | The logging system levels (DEBUG, INFO, WARNING, ERROR, TRACE, etc.)                    | string          |

| Name                           | Description                                  | Schema          |
|--------------------------------|----------------------------------------------|-----------------|
| stack_trace optional           | The stack trace                              | string          |
| syslog5424_ap p optional       | The system log application                   | string          |
| syslog5424_ho st optional      | The system log host                          | string          |
| syslog5424_pri optional        | The system log pri                           | string          |
| syslog5424_pr oc optional      | The system log proc                          | string          |
| syslog5424_ts optional         | Syslog specific attributes                   | string          |
| syslog5424_ve r optional       | The system log version                       | string          |
| syslog_facility optional       | The system log facility                      | string          |
| syslog_facility _code optional | The system log facility code                 | integer (int64) |
| syslog_severit y optional      | The system log severity                      | string          |
| syslog_severit y_code optional | The system log code                          | integer (int64) |
| thread optional                | The OS thread which generated the log entry. | string          |

| Name          | Description Schema                                                           |
|---------------|------------------------------------------------------------------------------|
| type optional | The RINA component that generated the log entry (BMS/Messaging, REST) string |

## TechnicalLogsTimeSlotDto

The time slot information for technical logs

| Name            | Description                     | Schema   |
|-----------------|---------------------------------|----------|
| date optional   | The hour of the slot            | string   |
| number optional | The number of items in the slot | string   |

## TenantDto

Tenant definition object

| Name                  | Description                                    | Schema        |
|-----------------------|------------------------------------------------|---------------|
| enabled optional      | True if the tenant is enabled, false otherwise | boolean       |
| id optional           | The ID of the tenant                           | string        |
| isDefault optional    |                                                | boolean       |
| organisation optional | Organisation definition of the tenant          | EntityBaseDto |

## TimeSlotDto

| Name            | Description                | Schema             |
|-----------------|----------------------------|--------------------|
| date optional   | The date of the timeslot   | string (date-time) |
| number optional | The number of the timeslot | integer (int64)    |

## UserDto

User details

| Name                      | Description                                                  | Schema             |
|---------------------------|--------------------------------------------------------------|--------------------|
| administrator optional    |                                                              | boolean            |
| creationDate optional     | The creation date of the User                                | string (date-time) |
| deleted optional          |                                                              | boolean            |
| email optional            | The email address of the User                                | string             |
| enabled optional          |                                                              | boolean            |
| firstName optional        | The first name of the User                                   | string             |
| id optional               | The id of the object                                         | string             |
| institutionId optional    | The institutionId of the User                                | string             |
| isAdministrat or optional | True is the user is technical user                           | boolean            |
| isEnabled optional        | True is the user is enabled                                  | boolean            |
| isSystem optional         | True is the user is enabled                                  | boolean            |
| keystoreAlias optional    | The default business keystore certificate alias of this user | string             |
| lastName optional         | The last name of the User                                    | string             |

| Name                 | Description                   | Schema                  |
|----------------------|-------------------------------|-------------------------|
| memberships optional | The memberships               | < MembershipDto > array |
| origin optional      | Origin of the user            | string                  |
| password optional    | The password of the User      | string                  |
| phoneNumber optional | The mobile number of the User | string                  |
| system optional      |                               | boolean                 |
| username optional    | The user-name of the User     | string                  |
| version optional     | The version of the object     | integer (int64)         |

## UserGroupDto

User or Group details

| Name                     | Description                               | Schema                     |
|--------------------------|-------------------------------------------|----------------------------|
| address optional         | The address of the Entity                 | AddressDto                 |
| contactMetho ds optional | The list of contact methods of the Entity | < ContactMethodDto > array |
| id optional              | The id of the Entity                      | string                     |
| name optional            | The name of the User or the Group         | string                     |
| organisation optional    | The organisation of the user              | EntityBaseDto              |

| Name          | Description                | Schema   |
|---------------|----------------------------|----------|
| type optional | The type of the User/Group | string   |

## UserMessageDto

Polymorphism : Composition

| Name              | Description                                                          | Schema                                                |
|-------------------|----------------------------------------------------------------------|-------------------------------------------------------|
| ack optional      | The Ack Message that is sent by the destination of the UserMessage   | AcknowledgementDt o                                   |
| action optional   | The case action type                                                 | enum (START, NEW, UPDATE, START_FORWARD, NEW_FORWARD) |
| error optional    | The Error Message that is sent by the destination of the UserMessage | ErrorDto                                              |
| id optional       | The Id of the message                                                | string                                                |
| isSent optional   | I sent                                                               | boolean                                               |
| receiver optional | The receiver Organisation/Institution                                | EntityBaseDto                                         |
| sbdh optional     | Standard business document header                                    | StandardBusinessDo cumentHeaderDto                    |
| sender optional   | The sender Organisation/Institution                                  | EntityBaseDto                                         |
| sent optional     |                                                                      | boolean                                               |
| status optional   | The Status of the User Message                                       | enum (SENT, DELIVERED, ERROR, RESENT)                 |

## UserMessageResponseDto

Polymorphism : Composition

| Name                 | Description                           | Schema                         |
|----------------------|---------------------------------------|--------------------------------|
| date optional        | The date when the error was received  | string (date-time)             |
| description optional | The description of the Error Message  | string                         |
| id optional          | The Id of the message                 | string                         |
| receiver optional    | The receiver Organisation/Institution | EntityBaseDto                  |
| sender optional      | The sender Organisation/Institution   | EntityBaseDto                  |
| type optional        | The type of the message, ACK or ERROR | enum (USERMESSAGE, ACK, ERROR) |

## UserPasswordDto

User's newPassword wrapper

| Name                 | Description                | Schema   |
|----------------------|----------------------------|----------|
| newPassword optional | The user's newPassword     | string   |
| oldPassword optional | The user's old newPassword | string   |

## UserProfileDto

The preferences and settings of a user

| Name                   | Description                 | Schema        |
|------------------------|-----------------------------|---------------|
| alarmSettings optional | Alarm Settings and Defaults | AlarmSettings |

| Name                               | Description                                         | Schema               |
|------------------------------------|-----------------------------------------------------|----------------------|
| caseClassicVie w optional          | The Case Management Classic View Settings           | CaseClassicView      |
| caseTimeline View optional         | The Case Management Timeline View Settings          | CaseTimelineView     |
| currentProces sDefinition optional | The process definition selected in breadcrumb       | string               |
| documents optional                 | The document related settings                       | Documents            |
| filterActionTy pe optional         | The active filter of case actions                   | string               |
| language optional                  | Language                                            | string               |
| localizationSe ttings optional     | The localization preferences and settings of a user | LocalizationSettings |
| origin optional                    | The origin of the user                              | string               |
| userName optional                  | The name of the user                                | string               |

## UserTypeDto

User type details

| Name                   | Description                    | Schema   |
|------------------------|--------------------------------|----------|
| id optional            | The id of the User             | string   |
| institutionId optional | The institution Id of the User | string   |

| Name          | Description                            | Schema   |
|---------------|----------------------------------------|----------|
| name optional | The name of the User                   | string   |
| type optional | The type of the User: regular or admin | string   |

## ValidationMessageDto

Validation message status of a document or subdocument

| Name             | Description        | Schema   |
|------------------|--------------------|----------|
| level optional   | Validation level   | string   |
| message optional | Validation message | string   |
| path optional    | Validation path    | string   |

## ValidationResultDto

Validation status of a document or subdocument

| Name              | Description         | Schema                          |
|-------------------|---------------------|---------------------------------|
| messages optional | Validation messages | < ValidationMessageD to > array |
| status optional   | Validation status   | enum (valid, invalid)           |

## VersionDto

SED Version details

| Name          | Description                           | Schema             |
|---------------|---------------------------------------|--------------------|
| date optional | The date that the version was created | string (date-time) |

| Name          | Description                                     | Schema       |
|---------------|-------------------------------------------------|--------------|
| id optional   | The id of the Version                           | string       |
| user optional | The user related to the creation of the version | UserGroupDto |

## VocabularyDetailedRevisedDto

Polymorphism : Composition

| Name              | Description                                                                                                                                | Schema                                     |
|-------------------|--------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------|
| concepts optional | The Concepts of the Vocabulary: AuditCategoryTypes AuditEventTypes ResourceStatusTypes each with a name and possibly some other properties | < string, ConceptDetailedRevi sedDto > map |
| id optional       | The id of the Vocabulary                                                                                                                   | string                                     |

## VocabularyDto

Abstract type for vocabulary object

| Name        | Description              | Schema   |
|-------------|--------------------------|----------|
| id optional | The id of the Vocabulary | string   |

## VocabularyStringDto

Polymorphism : Composition

| Name              | Description                                                                                 | Schema               |
|-------------------|---------------------------------------------------------------------------------------------|----------------------|
| concepts optional | The Concepts of the Vocabulary: en, fr, each with a name and possibly some other properties | < string, string map |
| id optional       | The id of the Vocabulary                                                                    | string               |

## X500Principal

| Name             | Schema                  |
|------------------|-------------------------|
| encoded optional | < string (byte) > array |
| name optional    | string                  |

## X509Certificate

| Name                              | Schema                     |
|-----------------------------------|----------------------------|
| basicConstraints optional         | integer (int32)            |
| criticalExtensionOIDs optional    | < string > array           |
| encoded optional                  | < string (byte) > array    |
| extendedKeyUsage optional         | < string > array           |
| issuerAlternativeNames optional   | < < object > array > array |
| issuerDN optional                 | Principal                  |
| issuerUniqueID optional           | < boolean > array          |
| issuerX500Principal optional      | X500Principal              |
| keyUsage optional                 | < boolean > array          |
| nonCriticalExtensionOIDs optional | < string > array           |
| notAfter optional                 | string (date-time)         |

| Name                             | Schema                     |
|----------------------------------|----------------------------|
| notBefore optional               | string (date-time)         |
| publicKey optional               | PublicKey                  |
| serialNumber optional            | integer                    |
| sigAlgName optional              | string                     |
| sigAlgOID optional               | string                     |
| sigAlgParams optional            | < string (byte) > array    |
| signature optional               | < string (byte) > array    |
| subjectAlternativeNames optional | < < object > array > array |
| subjectDN optional               | Principal                  |
| subjectUniqueID optional         | < boolean > array          |
| subjectX500Principal optional    | X500Principal              |
| tbscertificate optional          | < string (byte) > array    |
| type optional                    | string                     |
| version optional                 | integer (int32)            |