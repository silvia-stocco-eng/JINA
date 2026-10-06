---
unique-name: eessi-rina-sql-db-schema-physical-data-model-rev02
display-name: EESSI   RINA   SQL DB Schema   Physical Data Model   rev02
category: GENERAL
tags: ec
---

**EESSI – RINA**

**Database Schema**

***Physical Data Model***

**Document Control Information**

| **Document Control** | Value |
| --- | --- |
| **Project Title** | Electronic Exchange of Social Security Information (EESSI) |
| **Document Name** | EESSI - RINA – SQL DB Schema – Physical Data Model |
| **Document Category** | Data Architecture |
| **Revision** | rev02 |
| **Published with Component Version** | RINA 6.2.18 |
| **Last Publication Date** **Project Milestone** | 17/12/2021 EESSI-2020 HF8 |
| **Document Status** | Final |
| **Sensitivity (TLP)** **Distribution terms** | Traffic Light Protocol (TLP) = “GREEN” The distribution of this document is done strictly in line with the Traffic Light Protocol (TLP) established by the European Commission's note AC 790/15 REV for the EESSI project documentation. In line with the note AC 790/15 REV, this document is labelled as TLP = “Green”. Therefore, it can be circulated widely within the EESSI community. However, the document or the information herein may not be published or posted on the Internet, nor released outside of the EESSI community. |
| **Connected/Embedded Files** | None |
| **Authors** | European Commission, DG EMPL A4, EESSI ARCH/RINA |
| **Revised by** | European Commission, DG EMPL A4, EESSI QA/QC |
| **Approved by** | European Commission, DG EMPL A4, EESSI PMO |

**Document history**

| **Project Milestone** | **Date** | **Changes/Corrections** **Description** |
| --- | --- | --- |
| **EESSI-2020** **RINA 6.2.1** | 18/12/2020 | Initial Document |
| **EESSI-2020 HF1** **rev01** **RINA 6.2.3** | 12/03/2021 | Improvements to support the Data Migration process |
| **EESSI-2020 HF8** **rev02** **RINA 6.2.18** | 17/12/2021 | The following changes on DB Tables have been performed: - Update the column “NET_LOCATION_IP” of the Table “AUDIT_EVENT” - Update the column “REASON” of the Table “NOTIFICATION” - Add the column “ORIG_CREATED_AT” of the table “DOCUMENT_BVERSION” |
|  | 17/12/2021 | The following changes on DB indices have been performed: - Add the “ACTION_TAG__ACTION_UNQ” to column “FK_ACTION_SID” of the Table “ACTION_TAG” - Add the “CASE_SUBJECT_ORG__ORG_IDX” to column “FK_ORG_SID” of the Table “CASE_SUBJEXT_ORG” |
|  | 17/12/2021 | Replace the definitions of the Views: - “V_AUDIT_SEARCH” - “V_ORGANISATION_SEARCH” - “V_CASE_SEARCH” |

**Table of Contents**

I Introduction 20

I.1 Description 20

II Full model description 21

II.1 Diagram EESSII RINA physical diagram 21

II.2 List of tables 21

II.2.1 Table action 23

II.2.1.1 Card of table action 23

II.2.1.2 Check constraint name of the table action 23

II.2.1.3 List of incoming references of the table action 24

II.2.1.4 List of outgoing references of the table action 24

II.2.1.5 List of diagrams containing the table action 24

II.2.1.6 List of columns of the table action 24

II.2.1.7 List of keys of the table action 27

II.2.1.8 List of indexes of the table action 27

II.2.2 Table action_tag 27

II.2.2.1 Card of table action_tag 27

II.2.2.2 Check constraint name of the table action_tag 27

II.2.2.3 List of outgoing references of the table action_tag 27

II.2.2.4 List of diagrams containing the table action_tag 28

II.2.2.5 List of columns of the table action_tag 28

II.2.2.6 List of keys of the table action_tag 28

II.2.2.7 List of indexes of the table action_tag 28

II.2.3 Table activity 28

II.2.3.1 Card of table activity 28

II.2.3.2 Check constraint name of the table activity 29

II.2.3.3 List of incoming references of the table activity 29

II.2.3.4 List of outgoing references of the table activity 29

II.2.3.5 List of diagrams containing the table activity 29

II.2.3.6 List of columns of the table activity 29

II.2.3.7 List of keys of the table activity 30

II.2.3.8 List of indexes of the table activity 30

II.2.4 Table admin_notification_type 30

II.2.4.1 Card of table admin_notification_type 30

II.2.4.2 Check constraint name of the table admin_notification_type 30

II.2.4.3 List of diagrams containing the table admin_notification_type 30

II.2.4.4 List of columns of the table admin_notification_type 30

II.2.4.5 List of keys of the table admin_notification_type 31

II.2.4.6 List of indexes of the table admin_notification_type 31

II.2.5 Table archiving_volume 31

II.2.5.1 Card of table archiving_volume 31

II.2.5.2 Check constraint name of the table archiving_volume 31

II.2.5.3 List of diagrams containing the table archiving_volume 32

II.2.5.4 List of columns of the table archiving_volume 32

II.2.5.5 List of keys of the table archiving_volume 32

II.2.5.6 List of indexes of the table archiving_volume 32

II.2.6 Table ass_pol_ass_pol_target 32

II.2.6.1 Card of table ass_pol_ass_pol_target 32

II.2.6.2 Check constraint name of the table ass_pol_ass_pol_target 32

II.2.6.3 List of outgoing references of the table ass_pol_ass_pol_target 32

II.2.6.4 List of diagrams containing the table ass_pol_ass_pol_target 33

II.2.6.5 List of columns of the table ass_pol_ass_pol_target 33

II.2.7 Table assigned_buc 33

II.2.7.1 Card of table assigned_buc 33

II.2.7.2 Check constraint name of the table assigned_buc 33

II.2.7.3 List of outgoing references of the table assigned_buc 33

II.2.7.4 List of diagrams containing the table assigned_buc 33

II.2.7.5 List of columns of the table assigned_buc 33

II.2.7.6 List of keys of the table assigned_buc 34

II.2.7.7 List of indexes of the table assigned_buc 34

II.2.8 Table assignment 34

II.2.8.1 Card of table assignment 34

II.2.8.2 Check constraint name of the table assignment 34

II.2.8.3 List of incoming references of the table assignment 35

II.2.8.4 List of outgoing references of the table assignment 35

II.2.8.5 List of diagrams containing the table assignment 35

II.2.8.6 List of columns of the table assignment 35

II.2.8.7 List of keys of the table assignment 35

II.2.8.8 List of indexes of the table assignment 35

II.2.9 Table assignment_group 35

II.2.9.1 Card of table assignment_group 35

II.2.9.2 Check constraint name of the table assignment_group 36

II.2.9.3 List of outgoing references of the table assignment_group 36

II.2.9.4 List of diagrams containing the table assignment_group 36

II.2.9.5 List of columns of the table assignment_group 36

II.2.9.6 List of indexes of the table assignment_group 36

II.2.10 Table assignment_policy 36

II.2.10.1 Card of table assignment_policy 36

II.2.10.2 Check constraint name of the table assignment_policy 36

II.2.10.3 List of incoming references of the table assignment_policy 36

II.2.10.4 List of outgoing references of the table assignment_policy 37

II.2.10.5 List of diagrams containing the table assignment_policy 37

II.2.10.6 List of columns of the table assignment_policy 37

II.2.10.7 List of keys of the table assignment_policy 38

II.2.10.8 List of indexes of the table assignment_policy 38

II.2.11 Table assignment_policy_policy 38

II.2.11.1 Card of table assignment_policy_policy 38

II.2.11.2 Check constraint name of the table assignment_policy_policy 38

II.2.11.3 List of outgoing references of the table assignment_policy_policy 38

II.2.11.4 List of diagrams containing the table assignment_policy_policy 38

II.2.11.5 List of columns of the table assignment_policy_policy 38

II.2.12 Table assignment_policy_rule 39

II.2.12.1 Card of table assignment_policy_rule 39

II.2.12.2 Check constraint name of the table assignment_policy_rule 39

II.2.12.3 List of incoming references of the table assignment_policy_rule 39

II.2.12.4 List of outgoing references of the table assignment_policy_rule 39

II.2.12.5 List of diagrams containing the table assignment_policy_rule 39

II.2.12.6 List of columns of the table assignment_policy_rule 39

II.2.12.7 List of keys of the table assignment_policy_rule 40

II.2.12.8 List of indexes of the table assignment_policy_rule 40

II.2.13 Table assignment_policy_target 40

II.2.13.1 Card of table assignment_policy_target 40

II.2.13.2 Check constraint name of the table assignment_policy_target 40

II.2.13.3 List of incoming references of the table assignment_policy_target 41

II.2.13.4 List of outgoing references of the table assignment_policy_target 41

II.2.13.5 List of diagrams containing the table assignment_policy_target 41

II.2.13.6 List of columns of the table assignment_policy_target 41

II.2.13.7 List of keys of the table assignment_policy_target 41

II.2.13.8 List of indexes of the table assignment_policy_target 41

II.2.14 Table assignment_request 41

II.2.14.1 Card of table assignment_request 41

II.2.14.2 Check constraint name of the table assignment_request 42

II.2.14.3 List of outgoing references of the table assignment_request 42

II.2.14.4 List of diagrams containing the table assignment_request 42

II.2.14.5 List of columns of the table assignment_request 42

II.2.14.6 List of keys of the table assignment_request 42

II.2.14.7 List of indexes of the table assignment_request 42

II.2.15 Table assignment_user 43

II.2.15.1 Card of table assignment_user 43

II.2.15.2 Check constraint name of the table assignment_user 43

II.2.15.3 List of outgoing references of the table assignment_user 43

II.2.15.4 List of diagrams containing the table assignment_user 43

II.2.15.5 List of columns of the table assignment_user 43

II.2.15.6 List of indexes of the table assignment_user 43

II.2.16 Table audit_event 43

II.2.16.1 Card of table audit_event 43

II.2.16.2 Check constraint name of the table audit_event 44

II.2.16.3 List of incoming references of the table audit_event 44

II.2.16.4 List of diagrams containing the table audit_event 44

II.2.16.5 List of columns of the table audit_event 44

II.2.16.6 List of keys of the table audit_event 48

II.2.16.7 List of indexes of the table audit_event 48

II.2.17 Table audit_object 48

II.2.17.1 Card of table audit_object 48

II.2.17.2 Check constraint name of the table audit_object 48

II.2.17.3 List of outgoing references of the table audit_object 48

II.2.17.4 List of views of the table audit_object 48

II.2.17.5 List of diagrams containing the table audit_object 49

II.2.17.6 List of columns of the table audit_object 49

II.2.17.7 List of keys of the table audit_object 49

II.2.17.8 List of indexes of the table audit_object 50

II.2.18 Table audit_participant 50

II.2.18.1 Card of table audit_participant 50

II.2.18.2 Check constraint name of the table audit_participant 50

II.2.18.3 List of outgoing references of the table audit_participant 50

II.2.18.4 List of diagrams containing the table audit_participant 50

II.2.18.5 List of columns of the table audit_participant 50

II.2.18.6 List of keys of the table audit_participant 51

II.2.18.7 List of indexes of the table audit_participant 51

II.2.19 Table business_exception 51

II.2.19.1 Card of table business_exception 51

II.2.19.2 Check constraint name of the table business_exception 51

II.2.19.3 List of outgoing references of the table business_exception 51

II.2.19.4 List of views of the table business_exception 51

II.2.19.5 List of diagrams containing the table business_exception 51

II.2.19.6 List of columns of the table business_exception 51

II.2.19.7 List of keys of the table business_exception 52

II.2.19.8 List of indexes of the table business_exception 52

II.2.20 Table business_exception_settings 52

II.2.20.1 Card of table business_exception_settings 52

II.2.20.2 Check constraint name of the table business_exception_settings 52

II.2.20.3 List of diagrams containing the table business_exception_settings 52

II.2.20.4 List of columns of the table business_exception_settings 52

II.2.20.5 List of keys of the table business_exception_settings 53

II.2.20.6 List of indexes of the table business_exception_settings 53

II.2.21 Table business_key 53

II.2.21.1 Card of table business_key 53

II.2.21.2 Check constraint name of the table business_key 53

II.2.21.3 List of diagrams containing the table business_key 53

II.2.21.4 List of columns of the table business_key 53

II.2.21.5 List of keys of the table business_key 53

II.2.21.6 List of indexes of the table business_key 54

II.2.22 Table case_attachment 54

II.2.22.1 Card of table case_attachment 54

II.2.22.2 Check constraint name of the table case_attachment 54

II.2.22.3 List of outgoing references of the table case_attachment 54

II.2.22.4 List of diagrams containing the table case_attachment 54

II.2.22.5 List of columns of the table case_attachment 54

II.2.22.6 List of keys of the table case_attachment 55

II.2.22.7 List of indexes of the table case_attachment 55

II.2.23 Table case_comment 56

II.2.23.1 Card of table case_comment 56

II.2.23.2 Check constraint name of the table case_comment 56

II.2.23.3 List of outgoing references of the table case_comment 56

II.2.23.4 List of diagrams containing the table case_comment 56

II.2.23.5 List of columns of the table case_comment 56

II.2.23.6 List of keys of the table case_comment 56

II.2.23.7 List of indexes of the table case_comment 57

II.2.24 Table case_participant 57

II.2.24.1 Card of table case_participant 57

II.2.24.2 Check constraint name of the table case_participant 57

II.2.24.3 List of outgoing references of the table case_participant 57

II.2.24.4 List of diagrams containing the table case_participant 57

II.2.24.5 List of columns of the table case_participant 57

II.2.24.6 List of keys of the table case_participant 57

II.2.24.7 List of indexes of the table case_participant 58

II.2.25 Table case_prefill 58

II.2.25.1 Card of table case_prefill 58

II.2.25.2 Check constraint name of the table case_prefill 58

II.2.25.3 List of outgoing references of the table case_prefill 58

II.2.25.4 List of diagrams containing the table case_prefill 58

II.2.25.5 List of columns of the table case_prefill 58

II.2.25.6 List of keys of the table case_prefill 59

II.2.25.7 List of indexes of the table case_prefill 59

II.2.26 Table case_property 59

II.2.26.1 Card of table case_property 59

II.2.26.2 Check constraint name of the table case_property 59

II.2.26.3 List of outgoing references of the table case_property 59

II.2.26.4 List of diagrams containing the table case_property 59

II.2.26.5 List of columns of the table case_property 59

II.2.26.6 List of keys of the table case_property 60

II.2.26.7 List of indexes of the table case_property 60

II.2.27 Table case_subject_org 60

II.2.27.1 Card of table case_subject_org 60

II.2.27.2 Check constraint name of the table case_subject_org 60

II.2.27.3 List of outgoing references of the table case_subject_org 60

II.2.27.4 List of diagrams containing the table case_subject_org 60

II.2.27.5 List of columns of the table case_subject_org 60

II.2.27.6 List of indexes of the table case_subject_org 60

II.2.28 Table check_bucket 61

II.2.28.1 Card of table check_bucket 61

II.2.28.2 Check constraint name of the table check_bucket 61

II.2.28.3 List of incoming references of the table check_bucket 61

II.2.28.4 List of diagrams containing the table check_bucket 61

II.2.28.5 List of columns of the table check_bucket 61

II.2.28.6 List of keys of the table check_bucket 61

II.2.28.7 List of indexes of the table check_bucket 61

II.2.29 Table check_definition 62

II.2.29.1 Card of table check_definition 62

II.2.29.2 Check constraint name of the table check_definition 62

II.2.29.3 List of incoming references of the table check_definition 62

II.2.29.4 List of diagrams containing the table check_definition 62

II.2.29.5 List of columns of the table check_definition 62

II.2.29.6 List of keys of the table check_definition 62

II.2.29.7 List of indexes of the table check_definition 62

II.2.30 Table check_instance 63

II.2.30.1 Card of table check_instance 63

II.2.30.2 Check constraint name of the table check_instance 63

II.2.30.3 List of outgoing references of the table check_instance 63

II.2.30.4 List of diagrams containing the table check_instance 63

II.2.30.5 List of columns of the table check_instance 63

II.2.30.6 List of keys of the table check_instance 63

II.2.30.7 List of indexes of the table check_instance 64

II.2.31 Table cluster_node 64

II.2.31.1 Card of table cluster_node 64

II.2.31.2 Check constraint name of the table cluster_node 64

II.2.31.3 List of diagrams containing the table cluster_node 64

II.2.31.4 List of columns of the table cluster_node 64

II.2.31.5 List of keys of the table cluster_node 64

II.2.31.6 List of indexes of the table cluster_node 64

II.2.32 Table conv_participant 65

II.2.32.1 Card of table conv_participant 65

II.2.32.2 Check constraint name of the table conv_participant 65

II.2.32.3 List of outgoing references of the table conv_participant 65

II.2.32.4 List of diagrams containing the table conv_participant 65

II.2.32.5 List of columns of the table conv_participant 65

II.2.32.6 List of keys of the table conv_participant 65

II.2.32.7 List of indexes of the table conv_participant 65

II.2.33 Table doc_bversion_attachment 66

II.2.33.1 Card of table doc_bversion_attachment 66

II.2.33.2 Check constraint name of the table doc_bversion_attachment 66

II.2.33.3 List of outgoing references of the table doc_bversion_attachment 66

II.2.33.4 List of diagrams containing the table doc_bversion_attachment 66

II.2.33.5 List of columns of the table doc_bversion_attachment 66

II.2.33.6 List of indexes of the table doc_bversion_attachment 66

II.2.34 Table doc_bversion_subdoc_bversion 66

II.2.34.1 Card of table doc_bversion_subdoc_bversion 66

II.2.34.2 Check constraint name of the table doc_bversion_subdoc_bversion 67

II.2.34.3 List of outgoing references of the table doc_bversion_subdoc_bversion 67

II.2.34.4 List of diagrams containing the table doc_bversion_subdoc_bversion 67

II.2.34.5 List of columns of the table doc_bversion_subdoc_bversion 67

II.2.34.6 List of indexes of the table doc_bversion_subdoc_bversion 67

II.2.35 Table document 67

II.2.35.1 Card of table document 67

II.2.35.2 Check constraint name of the table document 67

II.2.35.3 List of incoming references of the table document 67

II.2.35.4 List of outgoing references of the table document 68

II.2.35.5 List of diagrams containing the table document 68

II.2.35.6 List of columns of the table document 68

II.2.35.7 List of keys of the table document 70

II.2.35.8 List of indexes of the table document 70

II.2.36 Table document_attachment 71

II.2.36.1 Card of table document_attachment 71

II.2.36.2 Check constraint name of the table document_attachment 71

II.2.36.3 List of incoming references of the table document_attachment 71

II.2.36.4 List of outgoing references of the table document_attachment 71

II.2.36.5 List of diagrams containing the table document_attachment 71

II.2.36.6 List of columns of the table document_attachment 71

II.2.36.7 List of keys of the table document_attachment 72

II.2.36.8 List of indexes of the table document_attachment 72

II.2.37 Table document_bversion 73

II.2.37.1 Card of table document_bversion 73

II.2.37.2 Check constraint name of the table document_bversion 73

II.2.37.3 List of incoming references of the table document_bversion 73

II.2.37.4 List of outgoing references of the table document_bversion 73

II.2.37.5 List of diagrams containing the table document_bversion 73

II.2.37.6 List of columns of the table document_bversion 73

II.2.37.7 List of keys of the table document_bversion 74

II.2.37.8 List of indexes of the table document_bversion 74

II.2.38 Table document_comment 74

II.2.38.1 Card of table document_comment 74

II.2.38.2 Check constraint name of the table document_comment 74

II.2.38.3 List of outgoing references of the table document_comment 74

II.2.38.4 List of diagrams containing the table document_comment 74

II.2.38.5 List of columns of the table document_comment 75

II.2.38.6 List of keys of the table document_comment 75

II.2.38.7 List of indexes of the table document_comment 75

II.2.39 Table document_content 75

II.2.39.1 Card of table document_content 75

II.2.39.2 Check constraint name of the table document_content 75

II.2.39.3 List of incoming references of the table document_content 76

II.2.39.4 List of outgoing references of the table document_content 76

II.2.39.5 List of diagrams containing the table document_content 76

II.2.39.6 List of columns of the table document_content 76

II.2.39.7 List of keys of the table document_content 76

II.2.39.8 List of indexes of the table document_content 76

II.2.40 Table document_conversation 76

II.2.40.1 Card of table document_conversation 76

II.2.40.2 Check constraint name of the table document_conversation 77

II.2.40.3 List of incoming references of the table document_conversation 77

II.2.40.4 List of outgoing references of the table document_conversation 77

II.2.40.5 List of diagrams containing the table document_conversation 77

II.2.40.6 List of columns of the table document_conversation 77

II.2.40.7 List of keys of the table document_conversation 77

II.2.40.8 List of indexes of the table document_conversation 77

II.2.41 Table document_history 78

II.2.41.1 Card of table document_history 78

II.2.41.2 Check constraint name of the table document_history 78

II.2.41.3 List of outgoing references of the table document_history 78

II.2.41.4 List of diagrams containing the table document_history 78

II.2.41.5 List of columns of the table document_history 78

II.2.41.6 List of keys of the table document_history 80

II.2.41.7 List of indexes of the table document_history 80

II.2.42 Table document_thumbnail 80

II.2.42.1 Card of table document_thumbnail 80

II.2.42.2 Check constraint name of the table document_thumbnail 80

II.2.42.3 List of outgoing references of the table document_thumbnail 80

II.2.42.4 List of diagrams containing the table document_thumbnail 80

II.2.42.5 List of columns of the table document_thumbnail 80

II.2.42.6 List of keys of the table document_thumbnail 81

II.2.42.7 List of indexes of the table document_thumbnail 81

II.2.43 Table document_type 82

II.2.43.1 Card of table document_type 82

II.2.43.2 Check constraint name of the table document_type 82

II.2.43.3 List of incoming references of the table document_type 82

II.2.43.4 List of outgoing references of the table document_type 82

II.2.43.5 List of diagrams containing the table document_type 82

II.2.43.6 List of columns of the table document_type 82

II.2.43.7 List of keys of the table document_type 82

II.2.43.8 List of indexes of the table document_type 83

II.2.44 Table document_type_version 83

II.2.44.1 Card of table document_type_version 83

II.2.44.2 Check constraint name of the table document_type_version 83

II.2.44.3 List of incoming references of the table document_type_version 83

II.2.44.4 List of outgoing references of the table document_type_version 83

II.2.44.5 List of diagrams containing the table document_type_version 83

II.2.44.6 List of columns of the table document_type_version 83

II.2.44.7 List of keys of the table document_type_version 84

II.2.44.8 List of indexes of the table document_type_version 84

II.2.45 Table field 84

II.2.45.1 Card of table field 84

II.2.45.2 Check constraint name of the table field 84

II.2.45.3 List of outgoing references of the table field 84

II.2.45.4 List of diagrams containing the table field 84

II.2.45.5 List of columns of the table field 84

II.2.45.6 List of keys of the table field 85

II.2.45.7 List of indexes of the table field 85

II.2.46 Table field_chooser 85

II.2.46.1 Card of table field_chooser 85

II.2.46.2 Check constraint name of the table field_chooser 85

II.2.46.3 List of incoming references of the table field_chooser 85

II.2.46.4 List of outgoing references of the table field_chooser 85

II.2.46.5 List of diagrams containing the table field_chooser 85

II.2.46.6 List of columns of the table field_chooser 86

II.2.46.7 List of keys of the table field_chooser 86

II.2.46.8 List of indexes of the table field_chooser 86

II.2.47 Table global_param 86

II.2.47.1 Card of table global_param 86

II.2.47.2 Check constraint name of the table global_param 86

II.2.47.3 List of outgoing references of the table global_param 86

II.2.47.4 List of diagrams containing the table global_param 86

II.2.47.5 List of columns of the table global_param 87

II.2.47.6 List of keys of the table global_param 87

II.2.47.7 List of indexes of the table global_param 87

II.2.48 Table global_param_group 87

II.2.48.1 Card of table global_param_group 87

II.2.48.2 Check constraint name of the table global_param_group 87

II.2.48.3 List of incoming references of the table global_param_group 87

II.2.48.4 List of diagrams containing the table global_param_group 87

II.2.48.5 List of columns of the table global_param_group 88

II.2.48.6 List of keys of the table global_param_group 88

II.2.48.7 List of indexes of the table global_param_group 88

II.2.49 Table iam_group 88

II.2.49.1 Card of table iam_group 88

II.2.49.2 Check constraint name of the table iam_group 89

II.2.49.3 List of incoming references of the table iam_group 89

II.2.49.4 List of outgoing references of the table iam_group 89

II.2.49.5 List of diagrams containing the table iam_group 89

II.2.49.6 List of columns of the table iam_group 89

II.2.49.7 List of keys of the table iam_group 90

II.2.49.8 List of indexes of the table iam_group 90

II.2.50 Table iam_origin 90

II.2.50.1 Card of table iam_origin 90

II.2.50.2 Check constraint name of the table iam_origin 90

II.2.50.3 List of incoming references of the table iam_origin 90

II.2.50.4 List of diagrams containing the table iam_origin 90

II.2.50.5 List of columns of the table iam_origin 91

II.2.50.6 List of keys of the table iam_origin 91

II.2.50.7 List of indexes of the table iam_origin 91

II.2.51 Table iam_user 91

II.2.51.1 Card of table iam_user 91

II.2.51.2 Check constraint name of the table iam_user 91

II.2.51.3 List of incoming references of the table iam_user 91

II.2.51.4 List of outgoing references of the table iam_user 91

II.2.51.5 List of diagrams containing the table iam_user 92

II.2.51.6 List of columns of the table iam_user 92

II.2.51.7 List of keys of the table iam_user 93

II.2.51.8 List of indexes of the table iam_user 93

II.2.52 Table iam_user_group 93

II.2.52.1 Card of table iam_user_group 93

II.2.52.2 Check constraint name of the table iam_user_group 93

II.2.52.3 List of outgoing references of the table iam_user_group 93

II.2.52.4 List of diagrams containing the table iam_user_group 93

II.2.52.5 List of columns of the table iam_user_group 93

II.2.52.6 List of keys of the table iam_user_group 94

II.2.52.7 List of indexes of the table iam_user_group 94

II.2.53 Table nie_event 94

II.2.53.1 Card of table nie_event 94

II.2.53.2 Check constraint name of the table nie_event 94

II.2.53.3 List of outgoing references of the table nie_event 94

II.2.53.4 List of diagrams containing the table nie_event 94

II.2.53.5 List of columns of the table nie_event 94

II.2.53.6 List of keys of the table nie_event 95

II.2.53.7 List of indexes of the table nie_event 95

II.2.54 Table nie_listener 96

II.2.54.1 Card of table nie_listener 96

II.2.54.2 Check constraint name of the table nie_listener 96

II.2.54.3 List of outgoing references of the table nie_listener 96

II.2.54.4 List of diagrams containing the table nie_listener 96

II.2.54.5 List of columns of the table nie_listener 96

II.2.54.6 List of keys of the table nie_listener 96

II.2.54.7 List of indexes of the table nie_listener 96

II.2.55 Table nie_subscriber 97

II.2.55.1 Card of table nie_subscriber 97

II.2.55.2 Check constraint name of the table nie_subscriber 97

II.2.55.3 List of outgoing references of the table nie_subscriber 97

II.2.55.4 List of diagrams containing the table nie_subscriber 97

II.2.55.5 List of columns of the table nie_subscriber 97

II.2.55.6 List of keys of the table nie_subscriber 97

II.2.55.7 List of indexes of the table nie_subscriber 98

II.2.56 Table nie_subscription 98

II.2.56.1 Card of table nie_subscription 98

II.2.56.2 Check constraint name of the table nie_subscription 98

II.2.56.3 List of incoming references of the table nie_subscription 98

II.2.56.4 List of diagrams containing the table nie_subscription 98

II.2.56.5 List of columns of the table nie_subscription 98

II.2.56.6 List of keys of the table nie_subscription 99

II.2.56.7 List of indexes of the table nie_subscription 99

II.2.57 Table notification 99

II.2.57.1 Card of table notification 99

II.2.57.2 Check constraint name of the table notification 99

II.2.57.3 List of incoming references of the table notification 99

II.2.57.4 List of outgoing references of the table notification 99

II.2.57.5 List of diagrams containing the table notification 99

II.2.57.6 List of columns of the table notification 99

II.2.57.7 List of keys of the table notification 100

II.2.57.8 List of indexes of the table notification 100

II.2.58 Table notification_alarm 101

II.2.58.1 Card of table notification_alarm 101

II.2.58.2 Check constraint name of the table notification_alarm 101

II.2.58.3 List of outgoing references of the table notification_alarm 101

II.2.58.4 List of diagrams containing the table notification_alarm 101

II.2.58.5 List of columns of the table notification_alarm 101

II.2.58.6 List of keys of the table notification_alarm 102

II.2.58.7 List of indexes of the table notification_alarm 102

II.2.59 Table notification_user 102

II.2.59.1 Card of table notification_user 102

II.2.59.2 Check constraint name of the table notification_user 102

II.2.59.3 List of outgoing references of the table notification_user 102

II.2.59.4 List of diagrams containing the table notification_user 102

II.2.59.5 List of columns of the table notification_user 102

II.2.59.6 List of indexes of the table notification_user 103

II.2.60 Table org_contact_method 103

II.2.60.1 Card of table org_contact_method 103

II.2.60.2 Check constraint name of the table org_contact_method 103

II.2.60.3 List of outgoing references of the table org_contact_method 103

II.2.60.4 List of diagrams containing the table org_contact_method 103

II.2.60.5 List of columns of the table org_contact_method 103

II.2.60.6 List of keys of the table org_contact_method 103

II.2.60.7 List of indexes of the table org_contact_method 103

II.2.61 Table organisation 104

II.2.61.1 Card of table organisation 104

II.2.61.2 Check constraint name of the table organisation 104

II.2.61.3 List of incoming references of the table organisation 104

II.2.61.4 List of diagrams containing the table organisation 104

II.2.61.5 List of columns of the table organisation 104

II.2.61.6 List of keys of the table organisation 106

II.2.61.7 List of indexes of the table organisation 106

II.2.62 Table pending_attachment 107

II.2.62.1 Card of table pending_attachment 107

II.2.62.2 Check constraint name of the table pending_attachment 107

II.2.62.3 List of outgoing references of the table pending_attachment 107

II.2.62.4 List of diagrams containing the table pending_attachment 107

II.2.62.5 List of columns of the table pending_attachment 107

II.2.62.6 List of keys of the table pending_attachment 108

II.2.62.7 List of indexes of the table pending_attachment 108

II.2.63 Table pending_message 108

II.2.63.1 Card of table pending_message 108

II.2.63.2 Check constraint name of the table pending_message 108

II.2.63.3 List of incoming references of the table pending_message 108

II.2.63.4 List of outgoing references of the table pending_message 109

II.2.63.5 List of diagrams containing the table pending_message 109

II.2.63.6 List of columns of the table pending_message 109

II.2.63.7 List of keys of the table pending_message 110

II.2.63.8 List of indexes of the table pending_message 110

II.2.64 Table pending_signature 110

II.2.64.1 Card of table pending_signature 110

II.2.64.2 Check constraint name of the table pending_signature 110

II.2.64.3 List of diagrams containing the table pending_signature 110

II.2.64.4 List of columns of the table pending_signature 110

II.2.64.5 List of keys of the table pending_signature 111

II.2.64.6 List of indexes of the table pending_signature 111

II.2.65 Table pending_status 111

II.2.65.1 Card of table pending_status 111

II.2.65.2 Check constraint name of the table pending_status 111

II.2.65.3 List of diagrams containing the table pending_status 111

II.2.65.4 List of columns of the table pending_status 111

II.2.65.5 List of keys of the table pending_status 112

II.2.65.6 List of indexes of the table pending_status 112

II.2.66 Table policy 112

II.2.66.1 Card of table policy 112

II.2.66.2 Check constraint name of the table policy 112

II.2.66.3 List of outgoing references of the table policy 112

II.2.66.4 List of diagrams containing the table policy 112

II.2.66.5 List of columns of the table policy 113

II.2.66.6 List of keys of the table policy 113

II.2.66.7 List of indexes of the table policy 113

II.2.67 Table process_def 113

II.2.67.1 Card of table process_def 113

II.2.67.2 Check constraint name of the table process_def 113

II.2.67.3 List of incoming references of the table process_def 114

II.2.67.4 List of outgoing references of the table process_def 114

II.2.67.5 List of views of the table process_def 114

II.2.67.6 List of diagrams containing the table process_def 114

II.2.67.7 List of columns of the table process_def 114

II.2.67.8 List of keys of the table process_def 114

II.2.67.9 List of indexes of the table process_def 114

II.2.68 Table process_def_version 115

II.2.68.1 Card of table process_def_version 115

II.2.68.2 Check constraint name of the table process_def_version 115

II.2.68.3 List of incoming references of the table process_def_version 115

II.2.68.4 List of outgoing references of the table process_def_version 115

II.2.68.5 List of views of the table process_def_version 115

II.2.68.6 List of diagrams containing the table process_def_version 115

II.2.68.7 List of columns of the table process_def_version 115

II.2.68.8 List of keys of the table process_def_version 116

II.2.68.9 List of indexes of the table process_def_version 116

II.2.69 Table resource 116

II.2.69.1 Card of table resource 116

II.2.69.2 Check constraint name of the table resource 116

II.2.69.3 List of diagrams containing the table resource 116

II.2.69.4 List of columns of the table resource 116

II.2.69.5 List of keys of the table resource 117

II.2.69.6 List of indexes of the table resource 117

II.2.70 Table rina_case 118

II.2.70.1 Card of table rina_case 118

II.2.70.2 Check constraint name of the table rina_case 118

II.2.70.3 List of incoming references of the table rina_case 118

II.2.70.4 List of outgoing references of the table rina_case 118

II.2.70.5 List of views of the table rina_case 118

II.2.70.6 List of diagrams containing the table rina_case 118

II.2.70.7 List of columns of the table rina_case 118

II.2.70.8 List of keys of the table rina_case 120

II.2.70.9 List of indexes of the table rina_case 120

II.2.71 Table role 120

II.2.71.1 Card of table role 120

II.2.71.2 Check constraint name of the table role 120

II.2.71.3 List of incoming references of the table role 120

II.2.71.4 List of diagrams containing the table role 120

II.2.71.5 List of columns of the table role 120

II.2.71.6 List of keys of the table role 121

II.2.71.7 List of indexes of the table role 121

II.2.72 Table rule_country 121

II.2.72.1 Card of table rule_country 121

II.2.72.2 Check constraint name of the table rule_country 121

II.2.72.3 List of outgoing references of the table rule_country 121

II.2.72.4 List of diagrams containing the table rule_country 121

II.2.72.5 List of columns of the table rule_country 121

II.2.72.6 List of keys of the table rule_country 122

II.2.72.7 List of indexes of the table rule_country 122

II.2.73 Table rule_creator_group 122

II.2.73.1 Card of table rule_creator_group 122

II.2.73.2 Check constraint name of the table rule_creator_group 123

II.2.73.3 List of outgoing references of the table rule_creator_group 123

II.2.73.4 List of diagrams containing the table rule_creator_group 123

II.2.73.5 List of columns of the table rule_creator_group 123

II.2.73.6 List of indexes of the table rule_creator_group 123

II.2.74 Table rule_creator_user 123

II.2.74.1 Card of table rule_creator_user 123

II.2.74.2 Check constraint name of the table rule_creator_user 123

II.2.74.3 List of outgoing references of the table rule_creator_user 124

II.2.74.4 List of diagrams containing the table rule_creator_user 124

II.2.74.5 List of columns of the table rule_creator_user 124

II.2.74.6 List of indexes of the table rule_creator_user 124

II.2.75 Table rule_group 124

II.2.75.1 Card of table rule_group 124

II.2.75.2 Check constraint name of the table rule_group 124

II.2.75.3 List of outgoing references of the table rule_group 124

II.2.75.4 List of diagrams containing the table rule_group 125

II.2.75.5 List of columns of the table rule_group 125

II.2.75.6 List of indexes of the table rule_group 125

II.2.76 Table rule_organisation 125

II.2.76.1 Card of table rule_organisation 125

II.2.76.2 Check constraint name of the table rule_organisation 125

II.2.76.3 List of outgoing references of the table rule_organisation 125

II.2.76.4 List of diagrams containing the table rule_organisation 125

II.2.76.5 List of columns of the table rule_organisation 125

II.2.76.6 List of indexes of the table rule_organisation 126

II.2.77 Table rule_process 126

II.2.77.1 Card of table rule_process 126

II.2.77.2 Check constraint name of the table rule_process 126

II.2.77.3 List of outgoing references of the table rule_process 126

II.2.77.4 List of diagrams containing the table rule_process 126

II.2.77.5 List of columns of the table rule_process 126

II.2.77.6 List of indexes of the table rule_process 126

II.2.78 Table rule_role 127

II.2.78.1 Card of table rule_role 127

II.2.78.2 Check constraint name of the table rule_role 127

II.2.78.3 List of outgoing references of the table rule_role 127

II.2.78.4 List of diagrams containing the table rule_role 127

II.2.78.5 List of columns of the table rule_role 127

II.2.78.6 List of indexes of the table rule_role 127

II.2.79 Table rule_sector 128

II.2.79.1 Card of table rule_sector 128

II.2.79.2 Check constraint name of the table rule_sector 128

II.2.79.3 List of outgoing references of the table rule_sector 128

II.2.79.4 List of diagrams containing the table rule_sector 128

II.2.79.5 List of columns of the table rule_sector 128

II.2.79.6 List of indexes of the table rule_sector 128

II.2.80 Table rule_user 128

II.2.80.1 Card of table rule_user 128

II.2.80.2 Check constraint name of the table rule_user 129

II.2.80.3 List of outgoing references of the table rule_user 129

II.2.80.4 List of diagrams containing the table rule_user 129

II.2.80.5 List of columns of the table rule_user 129

II.2.80.6 List of indexes of the table rule_user 129

II.2.81 Table search_def_group 129

II.2.81.1 Card of table search_def_group 129

II.2.81.2 Check constraint name of the table search_def_group 129

II.2.81.3 List of outgoing references of the table search_def_group 129

II.2.81.4 List of diagrams containing the table search_def_group 130

II.2.81.5 List of columns of the table search_def_group 130

II.2.81.6 List of indexes of the table search_def_group 130

II.2.82 Table search_def_org 130

II.2.82.1 Card of table search_def_org 130

II.2.82.2 Check constraint name of the table search_def_org 130

II.2.82.3 List of outgoing references of the table search_def_org 130

II.2.82.4 List of diagrams containing the table search_def_org 130

II.2.82.5 List of columns of the table search_def_org 131

II.2.82.6 List of indexes of the table search_def_org 131

II.2.83 Table search_def_proc_def 131

II.2.83.1 Card of table search_def_proc_def 131

II.2.83.2 Check constraint name of the table search_def_proc_def 131

II.2.83.3 List of outgoing references of the table search_def_proc_def 131

II.2.83.4 List of diagrams containing the table search_def_proc_def 131

II.2.83.5 List of columns of the table search_def_proc_def 131

II.2.83.6 List of indexes of the table search_def_proc_def 132

II.2.84 Table search_def_user 132

II.2.84.1 Card of table search_def_user 132

II.2.84.2 Check constraint name of the table search_def_user 132

II.2.84.3 List of outgoing references of the table search_def_user 132

II.2.84.4 List of diagrams containing the table search_def_user 132

II.2.84.5 List of columns of the table search_def_user 132

II.2.84.6 List of indexes of the table search_def_user 132

II.2.85 Table search_definition 133

II.2.85.1 Card of table search_definition 133

II.2.85.2 Check constraint name of the table search_definition 133

II.2.85.3 List of incoming references of the table search_definition 133

II.2.85.4 List of outgoing references of the table search_definition 133

II.2.85.5 List of diagrams containing the table search_definition 133

II.2.85.6 List of columns of the table search_definition 133

II.2.85.7 List of keys of the table search_definition 134

II.2.85.8 List of indexes of the table search_definition 134

II.2.86 Table sector 134

II.2.86.1 Card of table sector 134

II.2.86.2 Check constraint name of the table sector 134

II.2.86.3 List of incoming references of the table sector 134

II.2.86.4 List of diagrams containing the table sector 134

II.2.86.5 List of columns of the table sector 134

II.2.86.6 List of keys of the table sector 135

II.2.86.7 List of indexes of the table sector 135

II.2.87 Table signature 135

II.2.87.1 Card of table signature 135

II.2.87.2 Check constraint name of the table signature 135

II.2.87.3 List of outgoing references of the table signature 135

II.2.87.4 List of diagrams containing the table signature 135

II.2.87.5 List of columns of the table signature 135

II.2.87.6 List of keys of the table signature 136

II.2.87.7 List of indexes of the table signature 136

II.2.88 Table subdoc_bversion_attachment 136

II.2.88.1 Card of table subdoc_bversion_attachment 136

II.2.88.2 Check constraint name of the table subdoc_bversion_attachment 136

II.2.88.3 List of outgoing references of the table subdoc_bversion_attachment 136

II.2.88.4 List of diagrams containing the table subdoc_bversion_attachment 136

II.2.88.5 List of columns of the table subdoc_bversion_attachment 136

II.2.88.6 List of indexes of the table subdoc_bversion_attachment 137

II.2.89 Table subdocument 137

II.2.89.1 Card of table subdocument 137

II.2.89.2 Check constraint name of the table subdocument 137

II.2.89.3 List of incoming references of the table subdocument 137

II.2.89.4 List of outgoing references of the table subdocument 137

II.2.89.5 List of views of the table subdocument 137

II.2.89.6 List of diagrams containing the table subdocument 137

II.2.89.7 List of columns of the table subdocument 138

II.2.89.8 List of keys of the table subdocument 138

II.2.89.9 List of indexes of the table subdocument 138

II.2.90 Table subdocument_attachment 139

II.2.90.1 Card of table subdocument_attachment 139

II.2.90.2 Check constraint name of the table subdocument_attachment 139

II.2.90.3 List of incoming references of the table subdocument_attachment 139

II.2.90.4 List of outgoing references of the table subdocument_attachment 139

II.2.90.5 List of diagrams containing the table subdocument_attachment 139

II.2.90.6 List of columns of the table subdocument_attachment 139

II.2.90.7 List of keys of the table subdocument_attachment 140

II.2.90.8 List of indexes of the table subdocument_attachment 140

II.2.91 Table subdocument_bversion 141

II.2.91.1 Card of table subdocument_bversion 141

II.2.91.2 Check constraint name of the table subdocument_bversion 141

II.2.91.3 List of incoming references of the table subdocument_bversion 141

II.2.91.4 List of outgoing references of the table subdocument_bversion 141

II.2.91.5 List of diagrams containing the table subdocument_bversion 141

II.2.91.6 List of columns of the table subdocument_bversion 141

II.2.91.7 List of keys of the table subdocument_bversion 142

II.2.91.8 List of indexes of the table subdocument_bversion 142

II.2.92 Table subdocument_content 142

II.2.92.1 Card of table subdocument_content 142

II.2.92.2 Check constraint name of the table subdocument_content 142

II.2.92.3 List of incoming references of the table subdocument_content 142

II.2.92.4 List of outgoing references of the table subdocument_content 143

II.2.92.5 List of diagrams containing the table subdocument_content 143

II.2.92.6 List of columns of the table subdocument_content 143

II.2.92.7 List of keys of the table subdocument_content 143

II.2.92.8 List of indexes of the table subdocument_content 143

II.2.93 Table subdocument_history 143

II.2.93.1 Card of table subdocument_history 143

II.2.93.2 Check constraint name of the table subdocument_history 143

II.2.93.3 List of outgoing references of the table subdocument_history 143

II.2.93.4 List of diagrams containing the table subdocument_history 144

II.2.93.5 List of columns of the table subdocument_history 144

II.2.93.6 List of keys of the table subdocument_history 144

II.2.93.7 List of indexes of the table subdocument_history 144

II.2.94 Table subdocument_prefill 145

II.2.94.1 Card of table subdocument_prefill 145

II.2.94.2 Check constraint name of the table subdocument_prefill 145

II.2.94.3 List of outgoing references of the table subdocument_prefill 145

II.2.94.4 List of diagrams containing the table subdocument_prefill 145

II.2.94.5 List of columns of the table subdocument_prefill 145

II.2.94.6 List of keys of the table subdocument_prefill 145

II.2.94.7 List of indexes of the table subdocument_prefill 145

II.2.95 Table supported_language 146

II.2.95.1 Card of table supported_language 146

II.2.95.2 Check constraint name of the table supported_language 146

II.2.95.3 List of diagrams containing the table supported_language 146

II.2.95.4 List of columns of the table supported_language 146

II.2.95.5 List of keys of the table supported_language 146

II.2.95.6 List of indexes of the table supported_language 146

II.2.96 Table tenant 146

II.2.96.1 Card of table tenant 146

II.2.96.2 Check constraint name of the table tenant 146

II.2.96.3 List of incoming references of the table tenant 147

II.2.96.4 List of outgoing references of the table tenant 147

II.2.96.5 List of diagrams containing the table tenant 147

II.2.96.6 List of columns of the table tenant 147

II.2.96.7 List of keys of the table tenant 148

II.2.96.8 List of indexes of the table tenant 148

II.2.97 Table tenant_param 148

II.2.97.1 Card of table tenant_param 148

II.2.97.2 Check constraint name of the table tenant_param 148

II.2.97.3 List of outgoing references of the table tenant_param 148

II.2.97.4 List of diagrams containing the table tenant_param 148

II.2.97.5 List of columns of the table tenant_param 148

II.2.97.6 List of keys of the table tenant_param 149

II.2.97.7 List of indexes of the table tenant_param 149

II.2.98 Table tenant_param_group 149

II.2.98.1 Card of table tenant_param_group 149

II.2.98.2 Check constraint name of the table tenant_param_group 149

II.2.98.3 List of incoming references of the table tenant_param_group 149

II.2.98.4 List of outgoing references of the table tenant_param_group 149

II.2.98.5 List of diagrams containing the table tenant_param_group 149

II.2.98.6 List of columns of the table tenant_param_group 149

II.2.98.7 List of keys of the table tenant_param_group 150

II.2.98.8 List of indexes of the table tenant_param_group 150

II.2.99 Table translation 151

II.2.99.1 Card of table translation 151

II.2.99.2 Check constraint name of the table translation 151

II.2.99.3 List of diagrams containing the table translation 151

II.2.99.4 List of columns of the table translation 151

II.2.99.5 List of keys of the table translation 152

II.2.99.6 List of indexes of the table translation 152

II.2.100 Table transposition 152

II.2.100.1 Card of table transposition 152

II.2.100.2 Check constraint name of the table transposition 152

II.2.100.3 List of outgoing references of the table transposition 152

II.2.100.4 List of diagrams containing the table transposition 152

II.2.100.5 List of columns of the table transposition 152

II.2.100.6 List of keys of the table transposition 153

II.2.100.7 List of indexes of the table transposition 153

II.2.101 Table user_message 153

II.2.101.1 Card of table user_message 153

II.2.101.2 Check constraint name of the table user_message 153

II.2.101.3 List of incoming references of the table user_message 153

II.2.101.4 List of outgoing references of the table user_message 153

II.2.101.5 List of diagrams containing the table user_message 153

II.2.101.6 List of columns of the table user_message 154

II.2.101.7 List of keys of the table user_message 154

II.2.101.8 List of indexes of the table user_message 154

II.2.102 Table user_message_response 155

II.2.102.1 Card of table user_message_response 155

II.2.102.2 Check constraint name of the table user_message_response 155

II.2.102.3 List of outgoing references of the table user_message_response 155

II.2.102.4 List of diagrams containing the table user_message_response 155

II.2.102.5 List of columns of the table user_message_response 155

II.2.102.6 List of keys of the table user_message_response 155

II.2.102.7 List of indexes of the table user_message_response 156

II.2.103 Table user_profile 156

II.2.103.1 Card of table user_profile 156

II.2.103.2 Check constraint name of the table user_profile 156

II.2.103.3 List of outgoing references of the table user_profile 156

II.2.103.4 List of diagrams containing the table user_profile 156

II.2.103.5 List of columns of the table user_profile 156

II.2.103.6 List of keys of the table user_profile 158

II.2.103.7 List of indexes of the table user_profile 158

II.2.104 Table vocabulary 159

II.2.104.1 Card of table vocabulary 159

II.2.104.2 Check constraint name of the table vocabulary 159

II.2.104.3 List of outgoing references of the table vocabulary 159

II.2.104.4 List of diagrams containing the table vocabulary 159

II.2.104.5 List of columns of the table vocabulary 159

II.2.104.6 List of keys of the table vocabulary 159

II.2.104.7 List of indexes of the table vocabulary 160

II.2.105 Table vocabulary_type 160

II.2.105.1 Card of table vocabulary_type 160

II.2.105.2 Check constraint name of the table vocabulary_type 160

II.2.105.3 List of incoming references of the table vocabulary_type 160

II.2.105.4 List of diagrams containing the table vocabulary_type 160

II.2.105.5 List of columns of the table vocabulary_type 160

II.2.105.6 List of keys of the table vocabulary_type 163

II.2.105.7 List of indexes of the table vocabulary_type 163

II.3 List of references 163

II.4 List of views 168

II.4.1 View v_audit_search 168

II.4.1.1 Card of view v_audit_search 168

II.4.1.2 SQL query of the view v_audit_search 168

II.4.1.3 List of tables of the view v_audit_search 169

II.4.1.4 List of diagrams containing the view v_audit_search 169

II.4.1.5 List of columns of the view v_audit_search 169

II.4.2 View v_business_ex_search 169

II.4.2.1 Card of view v_business_ex_search 169

II.4.2.2 SQL query of the view v_business_ex_search 169

II.4.2.3 List of tables of the view v_business_ex_search 170

II.4.2.4 List of diagrams containing the view v_business_ex_search 170

II.4.2.5 List of columns of the view v_business_ex_search 170

II.4.3 View v_case_search 170

II.4.3.1 Card of view v_case_search 170

II.4.3.2 SQL query of the view v_case_search 171

II.4.3.3 List of tables of the view v_case_search 171

II.4.3.4 List of diagrams containing the view v_case_search 171

II.4.3.5 List of columns of the view v_case_search 171

II.4.4 View v_iam_user_search 171

II.4.4.1 Card of view v_iam_user_search 171

II.4.4.2 SQL query of the view v_iam_user_search 171

II.4.4.3 List of diagrams containing the view v_iam_user_search 172

II.4.4.4 List of columns of the view v_iam_user_search 172

II.4.5 View v_organisation_search 172

II.4.5.1 Card of view v_organisation_search 172

II.4.5.2 SQL query of the view v_organisation_search 172

II.4.5.3 List of diagrams containing the view v_organisation_search 173

II.4.5.4 List of columns of the view v_organisation_search 173

II.4.6 View v_subdocuments_search 173

II.4.6.1 Card of view v_subdocuments_search 173

II.4.6.2 SQL query of the view v_subdocuments_search 173

II.4.6.3 List of tables of the view v_subdocuments_search 174

II.4.6.4 List of diagrams containing the view v_subdocuments_search 174

II.4.6.5 List of columns of the view v_subdocuments_search 174

II.5 List of sequences 174

## 1 Introduction

### 1.1 Description

This document provides the schema of the RINA DB. All the tables are listed. For each table all the the fields and their attributes are presented. Furthermore, the keys, constraints, indices and references related to each table are provided. Finally, the views contained in the schema are presented.

The nomenclature for the naming is based in using '\_' for separating different words for all field and table names. For references and indices, the naming might include double '\_' for concatenating two tables. References are named always from using the child table name concatenated with the parent table name. The same holds for indices associated with these references.

## 2 Full model description

### 2.1 Diagram EESSII RINA physical diagram

### 2.2 List of tables

| *Code* |
| --- |
| ACTION |
| ACTION_TAG |
| ACTIVITY |
| ADMIN_NOTIFICATION_TYPE |
| ARCHIVING_VOLUME |
| ASS_POL_ASS_POL_TARGET |
| ASSIGNED_BUC |
| ASSIGNMENT |
| ASSIGNMENT_GROUP |
| ASSIGNMENT_POLICY |
| ASSIGNMENT_POLICY_POLICY |
| ASSIGNMENT_POLICY_RULE |
| ASSIGNMENT_POLICY_TARGET |
| ASSIGNMENT_REQUEST |
| ASSIGNMENT_USER |
| AUDIT_EVENT |
| AUDIT_OBJECT |
| AUDIT_PARTICIPANT |
| BUSINESS_EXCEPTION |
| BUSINESS_EXCEPTION_SETTINGS |
| BUSINESS_KEY |
| CASE_ATTACHMENT |
| CASE_COMMENT |
| CASE_PARTICIPANT |
| CASE_PREFILL |
| CASE_PROPERTY |
| CASE_SUBJECT_ORG |
| CHECK_BUCKET |
| CHECK_DEFINITION |
| CHECK_INSTANCE |
| CLUSTER_NODE |
| CONV_PARTICIPANT |
| DOC_BVERSION_ATTACHMENT |
| DOC_BVERSION_SUBDOC_BVERSION |
| DOCUMENT |
| DOCUMENT_ATTACHMENT |
| DOCUMENT_BVERSION |
| DOCUMENT_COMMENT |
| DOCUMENT_CONTENT |
| DOCUMENT_CONVERSATION |
| DOCUMENT_HISTORY |
| DOCUMENT_THUMBNAIL |
| DOCUMENT_TYPE |
| DOCUMENT_TYPE_VERSION |
| FIELD |
| FIELD_CHOOSER |
| GLOBAL_PARAM |
| GLOBAL_PARAM_GROUP |
| IAM_GROUP |
| IAM_ORIGIN |
| IAM_USER |
| IAM_USER_GROUP |
| NIE_EVENT |
| NIE_LISTENER |
| NIE_SUBSCRIBER |
| NIE_SUBSCRIPTION |
| NOTIFICATION |
| NOTIFICATION_ALARM |
| NOTIFICATION_USER |
| ORG_CONTACT_METHOD |
| ORGANISATION |
| PENDING_ATTACHMENT |
| PENDING_MESSAGE |
| PENDING_SIGNATURE |
| PENDING_STATUS |
| POLICY |
| PROCESS_DEF |
| PROCESS_DEF_VERSION |
| RESOURCE |
| RINA_CASE |
| ROLE |
| RULE_COUNTRY |
| RULE_CREATOR_GROUP |
| RULE_CREATOR_USER |
| RULE_GROUP |
| RULE_ORGANISATION |
| RULE_PROCESS |
| RULE_ROLE |
| RULE_SECTOR |
| RULE_USER |
| SEARCH_DEF_GROUP |
| SEARCH_DEF_ORG |
| SEARCH_DEF_PROC_DEF |
| SEARCH_DEF_USER |
| SEARCH_DEFINITION |
| SECTOR |
| SIGNATURE |
| SUBDOC_BVERSION_ATTACHMENT |
| SUBDOCUMENT |
| SUBDOCUMENT_ATTACHMENT |
| SUBDOCUMENT_BVERSION |
| SUBDOCUMENT_CONTENT |
| SUBDOCUMENT_HISTORY |
| SUBDOCUMENT_PREFILL |
| SUPPORTED_LANGUAGE |
| TENANT |
| TENANT_PARAM |
| TENANT_PARAM_GROUP |
| TRANSLATION |
| TRANSPOSITION |
| USER_MESSAGE |
| USER_MESSAGE_RESPONSE |
| USER_PROFILE |
| VOCABULARY |
| VOCABULARY_TYPE |

2.2.1 Table action

2.2.1.1 Card of table action

| Code | ACTION |
| --- | --- |
| Comment | Available Action of a specific Case Instance or Document |

2.2.1.2 Check constraint name of the table action

CKT_ACTION

2.2.1.3 List of incoming references of the table action

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| FK_ACTION_TAG__ACTION | action_tag | fk_action_sid |

2.2.1.4 List of outgoing references of the table action

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_ACTION__CASE | rina_case | fk_case_sid |
| FK_ACTION__DOC_TYPE_VER | document_type_version | fk_doc_type_version_sid |
| FK_ACTION__DOCUMENT | document | fk_document_sid |
| FK_ACTION__P_DOCUMENT | document | fk_parent_document_sid |

2.2.1.5 List of diagrams containing the table action

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.1.6 List of columns of the table action

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('action_seq') | The surrogate key |
| VERSION | INT4 | X | 1 | The version of the action.The system version. It is automatically increased by Hibernate each time the row is updated. |
| FK_CASE_SID | INT8 |  |  | Foreign key that links the action to the case table. |
| FK_DOCUMENT_SID | INT8 |  |  | Foreign key that links the Action to the Document table |
| FK_PARENT_DOCUMENT_SID | INT8 |  |  |  |
| FK_DOC_TYPE_VERSION_SID | INT8 |  |  | Foreign key to document_type_version table |
| ID | VARCHAR(255) | X |  | The id of the Action. |
| NAME | VARCHAR(255) |  |  | The action name. |
| STATUS | VARCHAR(30) | X | 'NEW' | The action status.Possible values(active, suspended, cancelled, executed). |
| ACTOR | VARCHAR(30) |  |  | The action actor. Possible values( SUPERVISOR, AUTHORIZED_CLERK UNAUTHORIZED_CLERK, AUDITOR,VIEWER, MEDICAL, VIP, EVERYONE) |
| OPERATION_TYPE | VARCHAR(30) |  |  | The action operation type. Possible values: CREATE("Create"), UPDATE("Update"), SEND("Send"), DELETE("Delete"), SUBDOCUMENT("Subdocument"), CREATE_LETTER("CreateLetter"), READ("Read"), CLOSE("Close"), REOPEN("Reopen"), DELETE_CASE("DeleteCase"), LOCAL_CLOSE("LocalClose"), LOCAL_REOPEN("LocalReopen"), ARCHIVE_CASE("ArchiveCase"), BACKUP_CASE("BackupCase"), RESTORE_CASE("RestoreCase"), SEND_PARTICIPANTS("SendParticipants"), SELECT_PARTICIPANTS("SelectParticipants"), READ_PARTICIPANTS("ReadParticipants"), UPDATE_PARTICIPANTS("UpdateParticipants"), ADD_ATTACHMENT("Attachment_Added"), //old, not used by UI REQUEST_APPROVAL("Request_Approval"), ADD_SUBDOCUMENT("Add_Subdocument"), UPDATE_SUBDOCUMENT("Update_Subdocument"), REMOVE_SUBDOCUMENT("Remove_Subdocument"), IMPORT_SUBDOCUMENT("Import_Subdocuments"), //new, not used by UI, internal to CPI and BUC-engine CREATE_CASE("CreateCase"), REMOVE_ATTACHMENT("Attachment_Removed"), //new, not used by UI, not used by CPI, internal to BUC-engine only. FORWARD_CASE("ForwardCase"), CREATE_CHILD("CreateChild"), CREATE_REPLY("CreateReply"), CANCEL("Cancel"), CANCEL_RECEIVE("CancelReceive"), RECEIVE("Receive"), RECEIVE_UPDATE("ReceiveUpdate"), RECEIVE_REPLY("ReceiveReply"); |
| DISPLAY_IN_DOCUMENT_ID | VARCHAR(255) |  |  | The display in document id. |
| DISPLAY_NAME | VARCHAR(255) |  |  | The display name. |
| DISPLAY_TYPE | VARCHAR(50) |  |  | The display type. |
| TEMPLATE_VERSION | VARCHAR(10) |  |  | The template version. |
| TEMPLATE | VARCHAR(255) |  |  | The template. |
| IS_CASE_RELATED | BOOL | X | false | The is case related flag. |
| IS_DOCUMENT_RELATED | BOOL | X | false | The is document related flag. |
| IS_BULK | BOOL | X | false | The is bulk flag. |
| HAS_BUSINESS_VALIDATION | BOOL | X | false | The has business validation flag. |
| REQUIRES_VALID_DOCUMENT | BOOL | X | false | The requires valid document flag. |
| CAN_CLOSE | BOOL | X | false | The can close flag. |
| AVAILABLE_FROM | TIMESTAMP WITH TIME ZONE |  |  | The available from date of the action. |
| CREATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | Date & Time of Creation |
| UPDATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | Date & time of last update |

2.2.1.7 List of keys of the table action

| Code | Primary |
| --- | --- |
| ACTION_PK | X |

2.2.1.8 List of indexes of the table action

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| ACTION_IDX | X | X |  | action |
| ACTION__CASE_IDX |  |  | X | action |
| ACTION__DOCUMENT_IDX |  |  | X | action |
| ACTION__DOC_TYPE_VER_IDX |  |  | X | action |
| ACTION__ID_UNQ | X |  |  | action |
| ACTION__P_DOCUMENT_IDX |  |  | X | action |

2.2.2 Table action_tag

2.2.2.1 Card of table action_tag

| Code | ACTION_TAG |
| --- | --- |
| Comment |  |

2.2.2.2 Check constraint name of the table action_tag

CKT_ACTION_TAG

2.2.2.3 List of outgoing references of the table action_tag

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_ACTION_TAG__ACTION | action | fk_action_sid |

2.2.2.4 List of diagrams containing the table action_tag

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.2.5 List of columns of the table action_tag

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X |  | The surrogate key. |
| FK_ACTION_SID | INT8 | X |  | Foreign key that links the ACTION_TAG to the ACTION table. |
| TYPE | VARCHAR(30) | X |  | The action tag type. Possible values: ADMIN("admin"), SECTORIAL("sectorial"); |
| CATEGORY | VARCHAR(30) | X |  | The action tag category. Possible values: CASE_ACTIONS("Case Actions"), DOCUMENTS("Documents"), HORIZONTAL_DOCUMENTS("Horizontal Documents"), PARTICIPANTS("Participants"); |

2.2.2.6 List of keys of the table action_tag

| Code | Primary |
| --- | --- |
| ACTION_TAG_PK | X |

2.2.2.7 List of indexes of the table action_tag

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| ACTION_TAG_IDX | X | X |  | action_tag |
| ACTION_TAG__ACTION_UNQ | X |  | X | action_tag |

2.2.3 Table activity

2.2.3.1 Card of table activity

| Code | ACTIVITY |
| --- | --- |
| Comment |  |

2.2.3.2 Check constraint name of the table activity

CKT_ACTIVITY

2.2.3.3 List of incoming references of the table activity

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| FK_ACTIVITY__PARENT | activity | fk_parent_sid |

2.2.3.4 List of outgoing references of the table activity

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_ACTIVITY__CASE | rina_case | fk_case_sid |
| FK_ACTIVITY__PARENT | activity | fk_parent_sid |

2.2.3.5 List of diagrams containing the table activity

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.3.6 List of columns of the table activity

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('activity_seq') | The surrogate key. |
| VERSION | INT4 | X | 1 | The system version. It is automatically increased by Hibernate each time the row is updated. |
| FK_CASE_SID | INT8 | X |  | Foreign key that links the activity to the case table. |
| FK_PARENT_SID | INT8 |  |  | Foreign key that links the activity to it's own parent. |
| ID | VARCHAR(255) | X |  | The id of the Activity. |
| TITLE | VARCHAR(255) |  |  | The title of the activity. |
| MESSAGE | TEXT |  |  | The activity message. |
| START_DATE | TIMESTAMP WITH TIME ZONE |  |  | The start date of the activity. |
| IS_DELETED | BOOL | X | false | The is deleted flag. |
| IS_REPEATING | BOOL | X | false | The is repeating flag. |
| COLOUR | VARCHAR(50) |  |  | The color of the activity. Possible values: BLUE("Blue"), RED("Red"), GREEN("Green"), ORANGE("ORANGE"), PURPLE("purple"); |
| DAY_INTERVAL | INT8 |  |  | The day interval. |
| OCCURENCES | INT8 |  |  | The number of occurences. |
| CREATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | Date & Time of Creation. |
| UPDATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | Date & Time of Update. |
| CREATED_BY | VARCHAR(255) | X | '0' | The person that created the activity. |
| UPDATED_BY | VARCHAR(255) | X | '0' | The person that last updated the activity. |

2.2.3.7 List of keys of the table activity

| Code | Primary |
| --- | --- |
| ACTIVITY_PK | X |

2.2.3.8 List of indexes of the table activity

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| ACTIVITY_IDX | X | X |  | activity |
| ACTIVITY__CASE_IDX |  |  | X | activity |
| ACTIVITY__PARENT_IDX |  |  | X | activity |
| ACTIVITY__ID_UNQ | X |  |  | activity |

2.2.4 Table admin_notification_type

2.2.4.1 Card of table admin_notification_type

| Code | ADMIN_NOTIFICATION_TYPE |
| --- | --- |
| Comment | AdminNotificationType details |

2.2.4.2 Check constraint name of the table admin_notification_type

CKT_ADMIN_NOTIFICATION_TYPE

2.2.4.3 List of diagrams containing the table admin_notification_type

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.4.4 List of columns of the table admin_notification_type

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('admin_notification_type_seq') | The surrogate key. |
| VERSION | INT4 | X | 1 | The system version. It is automatically increased by Hibernate each time the row is updated. |
| NOTIFICATION_TYPE | VARCHAR(255) | X |  | The notification Type of the AdminNotificationType |
| NOTIFICATION_NAME | VARCHAR(255) | X |  | The notifications name. |
| IS_FOR_ADMIN | BOOL |  |  | Value of Notification Centre for Admin checkbox |
| IS_FOR_CLERK | BOOL |  |  | Value of the Notification Centre for Clerk checkbox |
| IS_BE | BOOL |  |  | Flag to activate the Notification Centre for Business Exception |
| SHOW_FOR_ADMIN | BOOL |  |  | Flag to activate the Notification Centre for Admin checkbox |
| SHOW_FOR_CLERK | BOOL |  |  | Flag to activate the Notification Centre for Clerk checkbox |
| GENERATE_NIE_EVENT | BOOL |  |  | Value of Notification Centre for nie event checkbox |
| RETENTION_PERIOD | INT8 |  |  | The retention period of the AdminNotificationType |
| NOTIFICATION_PERIOD | INT8 |  |  | The notification period of the AdminNotificationType |

2.2.4.5 List of keys of the table admin_notification_type

| Code | Primary |
| --- | --- |
| ADMIN_NOTIFICATION_TYPE_PK | X |

2.2.4.6 List of indexes of the table admin_notification_type

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| ADMIN_NOTIFICATION_TYPE_IDX | X | X |  | admin_notification_type |
| ADMIN_NOTIF_TYPE_TYPE_UNQ | X |  |  | admin_notification_type |
| ADMIN_NOTIF_TYPE_NAME_UNQ | X |  |  | admin_notification_type |

2.2.5 Table archiving_volume

2.2.5.1 Card of table archiving_volume

| Code | ARCHIVING_VOLUME |
| --- | --- |
| Comment | Archiving volume details |

2.2.5.2 Check constraint name of the table archiving_volume

CKT_ARCHIVING_VOLUME

2.2.5.3 List of diagrams containing the table archiving_volume

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.5.4 List of columns of the table archiving_volume

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('archiving_volume_seq') | the surrogate key |
| ARCHIVING_VOLUME_ID | VARCHAR(255) | X |  | Volume identifier |
| ARCHIVING_VOLUME | VARCHAR(255) |  |  | Volume name |
| ACHIVING_MIN_SPACE_THRESHOLD | INT4 |  |  | The minimum space threshold per volume for the archiving process (in MB) |
| PHYSICAL_LOCATIONS | TEXT | X |  | The physical locations attached to volumes |

2.2.5.5 List of keys of the table archiving_volume

| Code | Primary |
| --- | --- |
| ARCHIVING_REPO_PK | X |

2.2.5.6 List of indexes of the table archiving_volume

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| ARCHIVING_IDX | X | X |  | archiving_volume |
| ARCHIVING__VOLUME_ID_UNQ | X |  |  | archiving_volume |

2.2.6 Table ass_pol_ass_pol_target

2.2.6.1 Card of table ass_pol_ass_pol_target

| Code | ASS_POL_ASS_POL_TARGET |
| --- | --- |
| Comment | Many-to-many association between assignment policies and targets |

2.2.6.2 Check constraint name of the table ass_pol_ass_pol_target

CKT_ASS_POL_ASS_POL_TARGET

2.2.6.3 List of outgoing references of the table ass_pol_ass_pol_target

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_AS_PL_TGT__AS_PL_ASS_PL_TGT | assignment_policy_target | fk_target_sid |
| FK_ASS_POL__ASS_POL_ASS_POL_TGT | assignment_policy | fk_policy_sid |

2.2.6.4 List of diagrams containing the table ass_pol_ass_pol_target

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.6.5 List of columns of the table ass_pol_ass_pol_target

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| FK_POLICY_SID | INT8 | X |  | foreign key to assignment policy table |
| FK_TARGET_SID | INT8 | X |  | foreign_key to assignment policy target table |

2.2.7 Table assigned_buc

2.2.7.1 Card of table assigned_buc

| Code | ASSIGNED_BUC |
| --- | --- |
| Comment | The BUC assigned to each case |

2.2.7.2 Check constraint name of the table assigned_buc

CKT_ASSIGNED_BUC

2.2.7.3 List of outgoing references of the table assigned_buc

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_ASSIGNED_BUC__ORG | organisation | fk_org_sid |
| FK_ASSIGNED_BUC__PROCESS_DEF | process_def | fk_process_def_sid |

2.2.7.4 List of diagrams containing the table assigned_buc

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.7.5 List of columns of the table assigned_buc

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('assigned_buc_seq') | The surrogate key |
| VERSION | INT4 | X | 1 | The system version. It is automatically increased by Hibernate each time the row is updated. |
| FK_ORG_SID | INT8 | X |  | Foreign key to organisation table |
| FK_PROCESS_DEF_SID | INT8 | X |  | foreign key to Process Definition table |
| APPLICATION_ROLE | VARCHAR(2) | X |  | The Application Role. Possible values: PO("CaseOwner"), CP("CounterParty"); |
| IS_EESSI_READY | BOOL |  |  | Is ready for usage in EESSI |
| VALIDITY_START_DATE | TIMESTAMP WITH TIME ZONE |  |  | Start day of the validity |
| VALIDITY_END_DATE | TIMESTAMP WITH TIME ZONE |  |  | End day of the validity |
| CREATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | The time that the BUC was first inserted into the DB |
| UPDATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | The last time that the BUC was updated |
| CREATED_BY | VARCHAR(255) | X | '0' | The person that created the asigned buc. |
| UPDATED_BY | VARCHAR(255) | X | '0' | The person that last updated the assigned buc. |

2.2.7.6 List of keys of the table assigned_buc

| Code | Primary |
| --- | --- |
| ASSIGNED_BUC_PK | X |

2.2.7.7 List of indexes of the table assigned_buc

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| ASSIGNED_BUC_IDX | X | X |  | assigned_buc |
| ASSIGNED_BUC__ORG_IDX |  |  | X | assigned_buc |
| ASSIGNED_BUC__PROCESS_DEF_IDX |  |  | X | assigned_buc |
| ASS_BUC__PROC_DEF_ORG_ROLE_UNQ | X |  |  | assigned_buc |

2.2.8 Table assignment

2.2.8.1 Card of table assignment

| Code | ASSIGNMENT |
| --- | --- |
| Comment | A many-to-many relation table for indicating the association between cases and roles. The table contains a surrogate key and it is not a typical many-to-many table in order to directly access each association since it is used by other many-to-many associations. |

2.2.8.2 Check constraint name of the table assignment

CKT_ASSIGNMENT

2.2.8.3 List of incoming references of the table assignment

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| FK_ASSIGN_GROUP__ASSIGN | assignment_group | fk_assignment_sid |
| FK_ASSIGN_USER__ASSIGN | assignment_user | fk_assignment_sid |

2.2.8.4 List of outgoing references of the table assignment

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_ASSIGN__CASE | rina_case | fk_case_sid |
| FK_ASSIGN__ROLE | role | fk_role_sid |

2.2.8.5 List of diagrams containing the table assignment

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.8.6 List of columns of the table assignment

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('assignment_seq') | The surrogate key |
| ID | VARCHAR(255) |  |  | The id of the assignement. |
| FK_CASE_SID | INT8 | X |  | Foreign key to the Case table |
| FK_ROLE_SID | INT8 | X |  | Foreign key to the Role table |

2.2.8.7 List of keys of the table assignment

| Code | Primary |
| --- | --- |
| ASSIGNMENT_PK | X |

2.2.8.8 List of indexes of the table assignment

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| ASSIGNMENT_IDX | X | X |  | assignment |
| ASSIGN__CASE_IDX |  |  | X | assignment |
| ASSIGN__ROLE_IDX |  |  | X | assignment |
| ASSIGN_CASE_ROLE_UNQ | X |  |  | assignment |
| ASSIGN_ID_UNQ | X |  |  | assignment |

2.2.9 Table assignment_group

2.2.9.1 Card of table assignment_group

| Code | ASSIGNMENT_GROUP |
| --- | --- |
| Comment | Many-to-many association between assignments and groups (iam_group table) |

2.2.9.2 Check constraint name of the table assignment_group

CKT_ASSIGNMENT_GROUP

2.2.9.3 List of outgoing references of the table assignment_group

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_ASSIGN_GROUP__ASSIGN | assignment | fk_assignment_sid |
| FK_ASSIGN_GROUP__GROUP | iam_group | fk_group_sid |

2.2.9.4 List of diagrams containing the table assignment_group

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.9.5 List of columns of the table assignment_group

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| FK_ASSIGNMENT_SID | INT8 | X |  | Foreign key to assignment table |
| FK_GROUP_SID | INT8 | X |  | Foreign key to iam_group table |

2.2.9.6 List of indexes of the table assignment_group

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| ASSIGN_GROUP__ASSIGN_IDX |  |  | X | assignment_group |
| ASSIGN_GROUP__GROUP_IDX |  |  | X | assignment_group |

2.2.10 Table assignment_policy

2.2.10.1 Card of table assignment_policy

| Code | ASSIGNMENT_POLICY |
| --- | --- |
| Comment | Assignment Policy details table. |

2.2.10.2 Check constraint name of the table assignment_policy

CKT_ASSIGNMENT_POLICY

2.2.10.3 List of incoming references of the table assignment_policy

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| FK_ASS_POL__ASS_POL_ASS_POL_TGT | ass_pol_ass_pol_target | fk_policy_sid |
| FK_ASSIGN_POL_RULE___ASSIGN_POL | assignment_policy_rule | fk_assignment_policy_sid |
| FK_ASSIGNMENT_POL__CHILD | assignment_policy_policy | fk_policy_child_sid |
| FK_ASSIGNMENT_POL__PARENT | assignment_policy_policy | fk_policy_parent_sid |

2.2.10.4 List of outgoing references of the table assignment_policy

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_ASSIGNMENT_POL__TENANT | tenant | fk_tenant_sid |

2.2.10.5 List of diagrams containing the table assignment_policy

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.10.6 List of columns of the table assignment_policy

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('assignment_policy_seq') | The surrogate key |
| VERSION | INT4 | X | 1 | The system version. It is automatically increased by Hibernate each time the row is updated. |
| FK_TENANT_SID | INT8 | X |  | Foreign key to the Tenant table |
| ID | VARCHAR(255) | X |  | The old ES id |
| NAME | VARCHAR(255) | X |  | The name of the Policy |
| DESCRIPTION | VARCHAR(255) |  |  | The policy description |
| COLOR | VARCHAR(255) |  |  | The color of the policy |
| TYPE | VARCHAR(20) | X |  | The type of this policy. Possible values: POLICY, GROUP, CREATOR; |
| APPLICATION_ROLE | VARCHAR(2) |  |  | Application Role PO or CP |
| CREATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | The time that the policy was first inserted into the DB |
| UPDATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | The last time that the policy was updated |
| CREATED_BY | VARCHAR(255) | X | '0' | The person that created the record. |
| UPDATED_BY | VARCHAR(255) | X | '0' | The person that last updated the record. |

2.2.10.7 List of keys of the table assignment_policy

| Code | Primary |
| --- | --- |
| PK_ASSIGNMENT_POLICY | X |

2.2.10.8 List of indexes of the table assignment_policy

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| ASSIGNMENT_POL_IDX | X | X |  | assignment_policy |
| ASSIGNMENT_POL__TENANT_IDX |  |  | X | assignment_policy |
| ASSIGNMENT_POL_ID_UNQ | X |  |  | assignment_policy |
| ASSIGNMENT_POL_NAME_UNQ | X |  |  | assignment_policy |

2.2.11 Table assignment_policy_policy

2.2.11.1 Card of table assignment_policy_policy

| Code | ASSIGNMENT_POLICY_POLICY |
| --- | --- |
| Comment | Many-to-many association between assignment policies parents and children |

2.2.11.2 Check constraint name of the table assignment_policy_policy

CKT_ASSIGNMENT_POLICY_POLICY

2.2.11.3 List of outgoing references of the table assignment_policy_policy

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_ASSIGNMENT_POL__CHILD | assignment_policy | fk_policy_child_sid |
| FK_ASSIGNMENT_POL__PARENT | assignment_policy | fk_policy_parent_sid |

2.2.11.4 List of diagrams containing the table assignment_policy_policy

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.11.5 List of columns of the table assignment_policy_policy

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| FK_POLICY_PARENT_SID | INT8 | X |  | foreign key to assignment policy parents |
| FK_POLICY_CHILD_SID | INT8 | X |  | foreign_key to assignment policy children |

2.2.12 Table assignment_policy_rule

2.2.12.1 Card of table assignment_policy_rule

| Code | ASSIGNMENT_POLICY_RULE |
| --- | --- |
| Comment | Assignment Policy Rule details |

2.2.12.2 Check constraint name of the table assignment_policy_rule

CKT_ASSIGNMENT_POLICY_RULE

2.2.12.3 List of incoming references of the table assignment_policy_rule

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| FK_RULE_COUN__ASSIGN_POL_RULE | rule_country | fk_rule_sid |
| FK_RULE_CREATOR_GROUP__RULE | rule_creator_group | fk_rule_sid |
| FK_RULE_CREATOR_USER__RULE | rule_creator_user | fk_rule_sid |
| FK_RULE_GROUP__RULE | rule_group | fk_rule_sid |
| FK_RULE_ORG__RULE | rule_organisation | fk_rule_sid |
| FK_RULE_PROCESS__RULE | rule_process | fk_rule_sid |
| FK_RULE_ROLE__RULE | rule_role | fk_rule_sid |
| FK_RULE_SECTOR__ASSIGN_POL_RUL | rule_sector | fk_rule_sid |
| FK_RULE_USER__ASSIGN_POL_RULE | rule_user | fk_rule_sid |

2.2.12.4 List of outgoing references of the table assignment_policy_rule

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_ASSIGN_POL_RULE___ASSIGN_POL | assignment_policy | fk_assignment_policy_sid |

2.2.12.5 List of diagrams containing the table assignment_policy_rule

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.12.6 List of columns of the table assignment_policy_rule

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('assignment_policy_rule_seq') | The surrogate key |
| ID | VARCHAR(255) | X |  | The id of the assignment policy rule. |
| VERSION | INT4 | X | 1 | The system version. It is automatically increased by Hibernate each time the row is updated. |
| FK_ASSIGNMENT_POLICY_SID | INT8 | X |  | Foreign key to assignment policy table |
| NAME | VARCHAR(255) |  |  | The name of this rule |
| POSITION_NO | INT4 | X | 1 | The position number. |
| CONDITION_PARTICIPANT_ROLE | VARCHAR(2) |  |  | The condition that must be met by a case instance for this rule to apply.Possible values: PO("CaseOwner"), CP("CounterParty"); |
| CONDITION_SUBJECT_ADDRESS | VARCHAR(255) |  |  | The condition that must be met by a case instance for this rule to apply |
| ASSIGN_TO_CREATOR_USER | BOOL | X | false | The asign to creator user field. |
| ASSIGN_TO_CREATOR_BRANCH | BOOL | X | false | The asign to creator branch field. |
| CREATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | The time that the rule was first inserted into the DB |
| UPDATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | The last time that the rule was updated |
| CREATED_BY | VARCHAR(255) | X | 'system' | The person that created the record. |
| UPDATED_BY | VARCHAR(255) | X | 'system' | The person that last updated the record. |

2.2.12.7 List of keys of the table assignment_policy_rule

| Code | Primary |
| --- | --- |
| PK_ASSIGNMENT_POLICY_RULE | X |

2.2.12.8 List of indexes of the table assignment_policy_rule

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| ASSIGN_POL_RULE_IDX | X | X |  | assignment_policy_rule |
| ASSIGN_POL_RULE_NAME_UNQ | X |  |  | assignment_policy_rule |
| ASSIGN_POL_RULE__ASSIGN_POL_IDX |  |  | X | assignment_policy_rule |
| ASSIGN_POL_RULE_ID_UNQ | X |  |  | assignment_policy_rule |

2.2.13 Table assignment_policy_target

2.2.13.1 Card of table assignment_policy_target

| Code | ASSIGNMENT_POLICY_TARGET |
| --- | --- |
| Comment | Assignment Policy Target details |

2.2.13.2 Check constraint name of the table assignment_policy_target

CKT_ASSIGNMENT_POLICY_TARGET

2.2.13.3 List of incoming references of the table assignment_policy_target

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| FK_AS_PL_TGT__AS_PL_ASS_PL_TGT | ass_pol_ass_pol_target | fk_target_sid |

2.2.13.4 List of outgoing references of the table assignment_policy_target

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_ASS_POL_TRGT__TENANT | tenant | fk_tenant_sid |

2.2.13.5 List of diagrams containing the table assignment_policy_target

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.13.6 List of columns of the table assignment_policy_target

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('assignment_policy_target_seq') | The surrogate key |
| FK_TENANT_SID | INT8 | X |  | Foreign key that links the asignment policy target to the tennant table. |
| TARGET | VARCHAR(255) | X |  | assignment policy target ID |
| STORAGE_ID | VARCHAR(255) | X |  | The storage id. |

2.2.13.7 List of keys of the table assignment_policy_target

| Code | Primary |
| --- | --- |
| ASSIGNMENT_POLICY_TARGET_PK | X |

2.2.13.8 List of indexes of the table assignment_policy_target

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| ASSIGNMENT_POLICY_TARGET_IDX | X | X |  | assignment_policy_target |
| ASSIGN_POL__TENANT_IDX |  |  | X | assignment_policy_target |
| ASSIGN_POL_TARGET__UNQ | X |  |  | assignment_policy_target |

2.2.14 Table assignment_request

2.2.14.1 Card of table assignment_request

| Code | ASSIGNMENT_REQUEST |
| --- | --- |
| Comment | A many-to-many relation table for indicating the association between cases and roles. The table contains a surrogate key and it is not a typical many-to-many table in order to directly access each association since it is used by other many-to-many associations. |

2.2.14.2 Check constraint name of the table assignment_request

CKT_ASSIGNMENT_REQUEST

2.2.14.3 List of outgoing references of the table assignment_request

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_ASSIGN_REQUEST__CASE | rina_case | fk_case_sid |
| FK_ASSIGN_REQUEST__NOTIF | notification | fk_notification_sid |
| FK_ASSIGN_REQUEST__ROLE | role | fk_role_sid |

2.2.14.4 List of diagrams containing the table assignment_request

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.14.5 List of columns of the table assignment_request

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('assignment_request_seq') | The surrogate key |
| FK_CASE_SID | INT8 | X |  | Foreign key to the Case table |
| FK_ROLE_SID | INT8 | X |  | Foreign key to the Role table |
| FK_NOTIFICATION_SID | INT8 | X |  | Foreign key that links the asignment request to the notification table. |
| ID | VARCHAR(255) |  |  | The id of the assignement request. |
| STATUS | VARCHAR(20) | X | 'PENDING' | The status of the assignement request. Possible values: PENDING, ACCEPTED, REJECTED, COMPLETED; |

2.2.14.6 List of keys of the table assignment_request

| Code | Primary |
| --- | --- |
| ASSIGNMENT_REQUEST_PK | X |

2.2.14.7 List of indexes of the table assignment_request

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| ASSIGNMENT_REQUEST_IDX | X | X |  | assignment_request |
| ASSIGN_REQUEST__CASE_IDX |  |  | X | assignment_request |
| ASSIGN_REQUEST__ROLE_IDX |  |  | X | assignment_request |
| ASSIGN_REQUEST__NOTIF_IDX |  |  | X | assignment_request |
| ASSIGN_REQ_CASE_ROLE_UNQ | X |  |  | assignment_request |

2.2.15 Table assignment_user

2.2.15.1 Card of table assignment_user

| Code | ASSIGNMENT_USER |
| --- | --- |
| Comment | Many-to-many association between assignments and users (iam_user table) |

2.2.15.2 Check constraint name of the table assignment_user

CKT_ASSIGNMENT_USER

2.2.15.3 List of outgoing references of the table assignment_user

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_ASSIGN_USER__ASSIGN | assignment | fk_assignment_sid |
| FK_ASSIGN_USER__USER | iam_user | fk_user_sid |

2.2.15.4 List of diagrams containing the table assignment_user

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.15.5 List of columns of the table assignment_user

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| FK_ASSIGNMENT_SID | INT8 | X |  | Foreign key to assignment policy table |
| FK_USER_SID | INT8 | X |  | Foreign key to iam_group table |

2.2.15.6 List of indexes of the table assignment_user

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| ASSIGN_USER__ASSIGN_IDX |  |  | X | assignment_user |
| ASSIGN_USER__USER_IDX |  |  | X | assignment_user |

2.2.16 Table audit_event

2.2.16.1 Card of table audit_event

| Code | AUDIT_EVENT |
| --- | --- |
| Comment | Table that hold information about the AUDIT's events. |

2.2.16.2 Check constraint name of the table audit_event

CKT_AUDIT_EVENT

2.2.16.3 List of incoming references of the table audit_event

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| FK_AUDIT_OBJECT__AUDIT_EVENT | audit_object | fk_audit_event_sid |
| FK_AUDIT_PART__AUDIT_EVENT | audit_participant | fk_audit_event_sid |

2.2.16.4 List of diagrams containing the table audit_event

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.16.5 List of columns of the table audit_event

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('audit_event_seq') | The surrogate key |
| ID | VARCHAR(100) | X |  | The id of the audit. |
| TENANT_ID | VARCHAR(255) |  |  | The id of the tenant |
| ACTION_TYPE | VARCHAR(50) | X |  | The action type of the audit. Possible values: CREATE("cre"), UPDATE("upd"), READ("re"), DELETE("del"), EXECUTE("exec"); |
| USERNAME | VARCHAR(255) |  |  | The username of the audited user |
| NET_LOCATION_MACHINE | VARCHAR(255) |  |  | The net location of the machine. |
| NET_LOCATION_IP | TEXT |  |  | The net location ip. |
| EVENT_TYPE | VARCHAR(100) | X |  | The event type. Possible values: /\* ATTACHMENTS */ SUBMIT_ATTACHMENT_ON_CASE, DELETE_ATTACHMENT_ON_CASE, RETRIEVE_ATTACHMENT_ON_CASE, SUBMIT_ATTACHMENT_ON_DOCUMENT, RETRIEVE_ATTACHMENT_ON_DOCUMENT, DELETE_ATTACHMENT_ON_DOCUMENT, /* CASES */ SEARCH_CASES_BY_SEARCH_DEFINITION_AND_OR_FREE_TEXT RETRIEVE_CASE_BY_ID RETRIEVE_CASE_BY_BUSINESS_ID RETRIEVE_CASE_BY_INTERNATIONAL_ID RETRIEVE_CASE_ID_BY_INTERNATIONAL_ID CREATE_NEW_CASE ASSIGN_CASE UPDATE_CASE_SENSITIVE SET_CASE_METADATA RETRIEVE_CASE_HASHCODE_BY_ID RETRIEVE_CASE_ASSIGNMENTS ARCHIVE_UNARCHIVE_CASE /* COMMENTS */ SUBMIT_COMMENT_ON_CASE DELETE_COMMENT_ON_CASE SUBMIT_COMMENT_ON_DOCUMENT DELETE_COMMENT_ON_DOCUMENT /* DOCUMENTS */ RETRIEVE_INITIAL_DOCUMENT SUBMIT_DOCUMENT RETRIEVE_DOCUMENT RETRIEVE_THUMBNAIL CREATE_DOCUMENT UPDATE_DOCUMENT DELETE_DOCUMENT SEND_DOCUMENT IMPORT_BATCH EXPORT_BATCH /* LOG IN/OUT */ LOG_IN LOG_OUT /* NOTIFICATIONS */ RETRIEVE_NOTIFICATIONS_DETAILS RETRIEVE_NOTIFICATIONS_CONSOLIDATED_SUMMARY RETRIEVE_NOTIFICATION_SUMMARY RETRIEVE_NOTIFICATION_TIME_SLOTS UPDATE_NOTIFICATION /* SEARCH DEFINITIONS */ CREATE_SEARCH_DEFINITION UPDATE_SEARCH_DEFINITION DELETE_SEARCH_DEFINITION /* USER PROFILE */ UPDATE_USER_PROFILE UPDATE_APPLICATION_PROFILE /* USER GROUP */ CREATE_USER_GROUP UPDATE_USER_GROUP DELETE_USER_GROUP CHANGE_AUTHORIZATION_POLICY /* BUSINESS MESSAGE */ SEND_BUSINESS_MESSAGE NOTIFY_ABOUT_RECEIVED_BUSINESS_MESSAGE NOTIFY_ABOUT_STATUS_UPDATE /* TECHNICAL MESSAGE */ SEND_TECHNICAL_MESSAGE RECEIVE_TECHNICAL_MESSAGE /* APPLICATION */ APPLICATION_START APPLICATION_END /* ALARM */ SET_ALARM CLEAR_ALARM /* CASE ASSIGNMENT ACTION\*/ EXECUTE_CASE_ASSIGNMENT_ACTION |
| CATEGORY_TYPE | VARCHAR(20) | X |  | The category type of the audit event. Possible values: MESSAGING("mess"), SECURITY("sec"), BUSINESS("bus"); |
| COMPONENT_TYPE | VARCHAR(20) | X |  | The component type. Possible values: ATTACHMENTS("attch"), CASES("cas"), COMMENTS("cmt"), DOCUMENTS("doc"), NOTIFICATIONS("notf"), SEARCH_DEFINITIONS("srch"), SECURITY("sec"), ADMINISTRATION("admin"), BUSINESS_MESSAGING("bmsg"), TECHNICAL_MESSAGING("tmsg"); |
| OUTCOME_TYPE | VARCHAR(20) | X |  | The outcome type of the audit event. Possible values: SUCCESS("succ"), ERROR("err"), UNAUTHORIZED("rjct"); |
| OUTCOME_DETAILS | TEXT |  |  | The outcome details of the audit event. |
| CREATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | Date & Time of Creation. |
| UPDATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | Date & time of last update. |
| CREATED_BY | VARCHAR(255) | X | '0' | The person that created the record. |
| UPDATED_BY | VARCHAR(255) | X | '0' | The person that last updated the record. |

2.2.16.6 List of keys of the table audit_event

| Code | Primary |
| --- | --- |
| AUDIT_EVENT_PK | X |

2.2.16.7 List of indexes of the table audit_event

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| AUDIT_EVENT_IDX | X | X |  | audit_event |

2.2.17 Table audit_object

2.2.17.1 Card of table audit_object

| Code | AUDIT_OBJECT |
| --- | --- |
| Comment | Table that hold information about the AUDITed objects. |

2.2.17.2 Check constraint name of the table audit_object

CKT_AUDIT_OBJECT

2.2.17.3 List of outgoing references of the table audit_object

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_AUDIT_OBJECT__AUDIT_EVENT | audit_event | fk_audit_event_sid |

2.2.17.4 List of views of the table audit_object

| Code |
| --- |
| V_AUDIT_SEARCH |

2.2.17.5 List of diagrams containing the table audit_object

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.17.6 List of columns of the table audit_object

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('audit_object_seq') | The surrogate key |
| FK_AUDIT_EVENT_SID | INT8 | X |  | Foreign key to the audit event table. |
| ID | VARCHAR(100) |  |  | The id of the audit object. |
| AUDIT_OBJECT_TYPE | VARCHAR(20) | X |  | The audit object type. Possible values: ATTACHMENT("attch"), ACTION("act"), CASE("cas"), COMMENT("cmt"), DOCUMENT("doc"), SUBDOCUMENT("sdoc"), NOTIFICATION("notf"), ALARM("alrm"), SEARCH_DEFINITION("srch"), USER_GROUP("usgr"), USER_PROFILE("uspr"), APPLICATION_PROFILE("appr"), CREDENTIAL("cred"), POLICY("poly"), BUSINESS_MESSAGE("bmsg"), TECHNICAL_MESSAGE("tmsg"), BUSINESS_ACK("ackm"), BUSINESS_ERROR("errm"); |
| DETAILS | TEXT |  |  | The audit object details. |

2.2.17.7 List of keys of the table audit_object

| Code | Primary |
| --- | --- |
| AUDIT_OBJECT_PK | X |

2.2.17.8 List of indexes of the table audit_object

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| AUDIT_OBJECT_IDX | X | X |  | audit_object |
| AUDIT_OBJECT__AUDIT_EVENT_IDX |  |  | X | audit_object |

2.2.18 Table audit_participant

2.2.18.1 Card of table audit_participant

| Code | AUDIT_PARTICIPANT |
| --- | --- |
| Comment | Table that hold information about the AUDITed participants. |

2.2.18.2 Check constraint name of the table audit_participant

CKT_AUDIT_PARTICIPANT

2.2.18.3 List of outgoing references of the table audit_participant

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_AUDIT_PART__AUDIT_EVENT | audit_event | fk_audit_event_sid |

2.2.18.4 List of diagrams containing the table audit_participant

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.18.5 List of columns of the table audit_participant

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('audit_participant_seq') | The surrogate key |
| FK_AUDIT_EVENT_SID | INT8 | X |  | Foreign key to the audit event table. |
| ID | TEXT |  |  | The audit participant id. |
| PARTICIPANT_TYPE | VARCHAR(20) | X |  | The participant type. Possible values: PERSON("per"), ORGANISATION("org"); |
| PARTICIPANT_ROLE | VARCHAR(20) | X |  | The participant role of the audit participant. Poosible values: SENDER("sndr"), RECEIVER("rcvr"), SUBJECT("subj"); |

2.2.18.6 List of keys of the table audit_participant

| Code | Primary |
| --- | --- |
| AUDIT_PARTICIPANT_PK | X |

2.2.18.7 List of indexes of the table audit_participant

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| AUDIT_PARTICIPANTT_IDX | X | X |  | audit_participant |
| AUDIT_OBJECT__AUDIT_PART_IDX |  |  | X | audit_participant |

2.2.19 Table business_exception

2.2.19.1 Card of table business_exception

| Code | BUSINESS_EXCEPTION |
| --- | --- |
| Comment | Table that holds information about the Business Exception |

2.2.19.2 Check constraint name of the table business_exception

CKT_BUSINESS_EXCEPTION

2.2.19.3 List of outgoing references of the table business_exception

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_BUSINESS_EXC__DOC | document | fk_doc_sid |
| FK_BUSINESS_EXC__PEND_MSG | pending_message | fk_pend_msg_sid |

2.2.19.4 List of views of the table business_exception

| Code |
| --- |
| V_BUSINESS_EX_SEARCH |

2.2.19.5 List of diagrams containing the table business_exception

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.19.6 List of columns of the table business_exception

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('business_exception_seq') | The surrogate key |
| FK_DOC_SID | INT8 | X |  | Foreign key that links the Business Exception to the document table |
| FK_PEND_MSG_SID | INT8 | X |  | Foreign key that links the Business Exception to the pending message table |
| ID | VARCHAR(255) | X |  | The id of the Business Exception |
| DATE | TIMESTAMP WITH TIME ZONE | X | now() |  |
| REASON | VARCHAR(255) |  |  | The reason of the business exception. |

2.2.19.7 List of keys of the table business_exception

| Code | Primary |
| --- | --- |
| BUSINESS_EXCEPTION_PK | X |

2.2.19.8 List of indexes of the table business_exception

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| BUS_EXC_IDX | X | X |  | business_exception |
| BUS_EXC__DOC_IDX |  |  | X | business_exception |
| BUS_EXC__PEND_MSG_IDX |  |  | X | business_exception |
| BUS_EXC__ID_UNQ | X |  |  | business_exception |

2.2.20 Table business_exception_settings

2.2.20.1 Card of table business_exception_settings

| Code | BUSINESS_EXCEPTION_SETTINGS |
| --- | --- |
| Comment | Business Exception Settings |

2.2.20.2 Check constraint name of the table business_exception_settings

CKT_BUSINESS_EXCEPTION_SETTING

2.2.20.3 List of diagrams containing the table business_exception_settings

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.20.4 List of columns of the table business_exception_settings

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('business_exception_settings_seq') | The surrogate key |
| CAUSE | VARCHAR(255) | X |  | The source/cause of the business error |
| SETTING | INT4 | X |  | The setting fot the business exception |

2.2.20.5 List of keys of the table business_exception_settings

| Code | Primary |
| --- | --- |
| BUSINESS_EXCEPTIONS_SETTINGS_PK | X |

2.2.20.6 List of indexes of the table business_exception_settings

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| BUSINESS_EXCEPTION_SETTINGS_IDX | X | X |  | business_exception_settings |
| BUS_EXCEPTION_SET_CAUSE_UNQ | X |  |  | business_exception_settings |

2.2.21 Table business_key

2.2.21.1 Card of table business_key

| Code | BUSINESS_KEY |
| --- | --- |
| Comment | The business key aliases of the application available to tenants. The keys are located in the associeted keystore. |

2.2.21.2 Check constraint name of the table business_key

CKT_BUSINESS_KEY

2.2.21.3 List of diagrams containing the table business_key

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.21.4 List of columns of the table business_key

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('business_key_seq') | The surrogate key |
| ALIAS | VARCHAR(255) | X |  | The alias of the business key |
| PASSWORD | VARCHAR(255) | X |  | The password of the business key |

2.2.21.5 List of keys of the table business_key

| Code | Primary |
| --- | --- |
| BUSINESS_KEY_PK | X |

2.2.21.6 List of indexes of the table business_key

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| BUSINESS_KEY_IDX | X | X |  | business_key |
| BUSINESS_KEY_ALIAS_UNQ | X |  |  | business_key |

2.2.22 Table case_attachment

2.2.22.1 Card of table case_attachment

| Code | CASE_ATTACHMENT |
| --- | --- |
| Comment | The attachments associated to a specific case |

2.2.22.2 Check constraint name of the table case_attachment

CKT_CASE_ATTACHMENT

2.2.22.3 List of outgoing references of the table case_attachment

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_CASE_ATTACH__CASE | rina_case | fk_case_sid |

2.2.22.4 List of diagrams containing the table case_attachment

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.22.5 List of columns of the table case_attachment

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('case_attachment_seq') | The surrogate key |
| VERSION | INT4 | X | 1 | The system version. It is automatically increased by Hibernate each time the row is updated. |
| FK_CASE_SID | INT8 | X |  | Foreign key to the rina_case table |
| MIME_TYPE | VARCHAR(50) | X |  | The mime type. Possible values: APP_PDF APP_MSWORD APP_MSEXCEL APP_MSPOWERPOINT APP_OPENXML_DOC APP_OPENXML_SPREADSHEET APP_OPENXML_PRESENTATION APP_XML APP_ZIP APP_GZIP IMG_JPEG IMG_PNG IMG_TIFF TXT_RTF TXT_XML // Mimetypes NOT included in the SBDH XSD definition APP_X_ZIP APP_OCTET_STREAM APP_X_ZIP_COMPRESSED |
| ID | VARCHAR(255) | X |  | The id of the case attachment. |
| NAME | VARCHAR(255) |  |  | The name of the case attachment. |
| FILENAME | VARCHAR(1024) |  |  | The directory path where the assignment is stored |
| PATHNAME | VARCHAR(1024) | X |  | The pathname of the attachment. |
| IS_MEDICAL | BOOL | X | false | The is medical flag. |
| IS_ACTIVE | BOOL | X | true | The is active flag. |
| CREATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | Date & Time of Creation. |
| UPDATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | Date & time of last update. |
| CREATED_BY | VARCHAR(255) | X | '0' | The person that created the record. |
| UPDATED_BY | VARCHAR(255) | X | '0' | The person that last updated the record. |

2.2.22.6 List of keys of the table case_attachment

| Code | Primary |
| --- | --- |
| CASE_ATTACHEMENT_PK | X |

2.2.22.7 List of indexes of the table case_attachment

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| CASE_ATTACHEMENT_IDX | X | X |  | case_attachment |
| CASE_ATTACHMENT_ID_UNQ | X |  |  | case_attachment |
| CASE_ATTACHMENT__CASE_IDX |  |  | X | case_attachment |

2.2.23 Table case_comment

2.2.23.1 Card of table case_comment

| Code | CASE_COMMENT |
| --- | --- |
| Comment | The comments associated to a specific case |

2.2.23.2 Check constraint name of the table case_comment

CKT_CASE_COMMENT

2.2.23.3 List of outgoing references of the table case_comment

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_COMMENT__CASE | rina_case | fk_case_sid |

2.2.23.4 List of diagrams containing the table case_comment

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.23.5 List of columns of the table case_comment

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('case_comment_seq') | The surrogate key |
| VERSION | INT4 | X | 1 | The system version. It is automatically increased by Hibernate each time the row is updated. |
| FK_CASE_SID | INT8 | X |  | Foreign key to the rina_case table |
| ID | VARCHAR(255) | X |  | The id of the case comment. |
| TEXT | TEXT | X |  | The comment |
| CREATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | Date & Time the entity was created |
| UPDATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | Date & Time the entity was last updated |
| CREATED_BY | VARCHAR(255) | X | '0' | The person that created the record. |
| UPDATED_BY | VARCHAR(255) | X | '0' | The person that last updated the record. |

2.2.23.6 List of keys of the table case_comment

| Code | Primary |
| --- | --- |
| CASE_COMMENT_PK | X |

2.2.23.7 List of indexes of the table case_comment

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| CASE_COMMENT_IDX | X | X |  | case_comment |
| CASE_COMMENT__CASE_IDX |  |  | X | case_comment |
| CASE_COMMENT_ID_UNQ | X |  |  | case_comment |

2.2.24 Table case_participant

2.2.24.1 Card of table case_participant

| Code | CASE_PARTICIPANT |
| --- | --- |
| Comment | Table that holds infomation about the Participating Institution in a conversation or case instance |

2.2.24.2 Check constraint name of the table case_participant

CKT_CASE_PARTICIPANT

2.2.24.3 List of outgoing references of the table case_participant

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_CASE_PARTICIPANT__CASE | rina_case | fk_case_sid |
| FK_CASE_PARTICIPANT__ORG | organisation | fk_org_sid |

2.2.24.4 List of diagrams containing the table case_participant

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.24.5 List of columns of the table case_participant

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('case_participant_seq') | The surrogate key |
| FK_CASE_SID | INT8 | X |  | Foreign key associated to the associated case. |
| FK_ORG_SID | INT8 | X |  | foreign key to organisation |
| CASE_PARTICIPANT_ROLE | VARCHAR(2) | X |  | The role of the participant in in a conversation or in a case |

2.2.24.6 List of keys of the table case_participant

| Code | Primary |
| --- | --- |
| CASE_PARTICIPANT_PK | X |

2.2.24.7 List of indexes of the table case_participant

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| CASE_PARTICIPANT_IDX | X | X |  | case_participant |
| CASE_PARTICIPANT__CASE_IDX |  |  | X | case_participant |
| CASE_PARTICIPANT__ORG_IDX |  |  | X | case_participant |

2.2.25 Table case_prefill

2.2.25.1 Card of table case_prefill

| Code | CASE_PREFILL |
| --- | --- |
| Comment | The prefill data associated to a specific case |

2.2.25.2 Check constraint name of the table case_prefill

CKT_CASE_PREFILL

2.2.25.3 List of outgoing references of the table case_prefill

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_CASE_PREFILL__RINA_CASE | rina_case | fk_case_sid |

2.2.25.4 List of diagrams containing the table case_prefill

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.25.5 List of columns of the table case_prefill

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('case_prefill_seq') | The surrogate key |
| FK_CASE_SID | INT8 | X |  | Foreign key to the rina_case table |
| PREFILL_GROUP | VARCHAR(20) | X | PREFILL | The prefill group. Possible values: SUBJECT, PREFILL, SEARCH_METADATA; |
| KEY | VARCHAR(1024) | X |  | The key of the case prefill. |
| VALUE | TEXT | X |  | The directory path where the assignment is stored |

2.2.25.6 List of keys of the table case_prefill

| Code | Primary |
| --- | --- |
| CASE_PREFILL_PK | X |

2.2.25.7 List of indexes of the table case_prefill

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| CASE_PREFILL_IDX | X | X |  | case_prefill |
| CASE_PREFILL__CASE_IDX |  |  | X | case_prefill |
| CASE_PREFILL__GROUP_IDX |  |  |  | case_prefill |
| CASE_PREFILL__KEY_UNQ | X |  |  | case_prefill |

2.2.26 Table case_property

2.2.26.1 Card of table case_property

| Code | CASE_PROPERTY |
| --- | --- |
| Comment | The properties associated to a specific case |

2.2.26.2 Check constraint name of the table case_property

CKT_CASE_PROPERTY

2.2.26.3 List of outgoing references of the table case_property

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_CASE_PROPERTY__CASE | rina_case | fk_case_sid |

2.2.26.4 List of diagrams containing the table case_property

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.26.5 List of columns of the table case_property

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('case_property_seq') | The surrogate key |
| FK_CASE_SID | INT8 | X |  | Foreign key to the rina_case table |
| KEY | VARCHAR(30) | X |  | The key of the case property. |
| VALUE | VARCHAR(255) | X |  | The directory path where the assignment is stored |

2.2.26.6 List of keys of the table case_property

| Code | Primary |
| --- | --- |
| CASE_PROPERTY_PK | X |

2.2.26.7 List of indexes of the table case_property

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| CASE_PROPERTY_IDX | X | X |  | case_property |
| CASE_PROPERTY__CASE_IDX |  |  | X | case_property |
| CASE_PROPERTY__KEY_UNQ | X |  |  | case_property |

2.2.27 Table case_subject_org

2.2.27.1 Card of table case_subject_org

| Code | CASE_SUBJECT_ORG |
| --- | --- |
| Comment |  |

2.2.27.2 Check constraint name of the table case_subject_org

CKT_CASE_SUBJECT_ORG

2.2.27.3 List of outgoing references of the table case_subject_org

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_CASE_SUBJECT_ORG__CASE | rina_case | fk_case_sid |
| FK_CASE_SUBJECT_ORG__ORG | organisation | fk_org_sid |

2.2.27.4 List of diagrams containing the table case_subject_org

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.27.5 List of columns of the table case_subject_org

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| FK_CASE_SID | INT8 | X |  | Foreign key to the rina case table. |
| FK_ORG_SID | INT8 | X |  | Fk to the organisation table. |

2.2.27.6 List of indexes of the table case_subject_org

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| CASE_SUBJECT_ORG__ORG_IDX |  |  | X | case_subject_org |
| CASE_SUBJECT_ORG__CASE_IDX |  |  | X | case_subject_org |

2.2.28 Table check_bucket

2.2.28.1 Card of table check_bucket

| Code | CHECK_BUCKET |
| --- | --- |
| Comment | Table that holds a list of check buckets |

2.2.28.2 Check constraint name of the table check_bucket

CKT_CHECK_BUCKET

2.2.28.3 List of incoming references of the table check_bucket

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| FK_CHECK_INSTANCE__CHECK_BUCKET | check_instance | fk_check_bucket_sid |

2.2.28.4 List of diagrams containing the table check_bucket

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.28.5 List of columns of the table check_bucket

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('check_bucket_seq') | The surrogate key |
| ID | VARCHAR(255) | X |  | The id of the check bucket. |
| START_DATE | TIMESTAMP WITH TIME ZONE | X |  | The start date. |

2.2.28.6 List of keys of the table check_bucket

| Code | Primary |
| --- | --- |
| CHECK_DEF_PK | X |

2.2.28.7 List of indexes of the table check_bucket

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| CHECK_BUCKET_IDX | X | X |  | check_bucket |
| CHECK_BUCKET_ID_IDX | X |  |  | check_bucket |

2.2.29 Table check_definition

2.2.29.1 Card of table check_definition

| Code | CHECK_DEFINITION |
| --- | --- |
| Comment | Table that holds a list of checks |

2.2.29.2 Check constraint name of the table check_definition

CKT_CHECK_DEFINITION

2.2.29.3 List of incoming references of the table check_definition

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| FK_CHECK_INSTANCE__CHECK_DEF | check_instance | fk_check_definition_sid |

2.2.29.4 List of diagrams containing the table check_definition

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.29.5 List of columns of the table check_definition

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('check_definition_seq') | The surrogate key |
| ID | VARCHAR(255) | X |  | The id of the check definition. |
| CHECK_CATEGORY | VARCHAR(255) | X |  | The check category. |
| NAME | VARCHAR(255) | X |  | The name of the check definition. |
| DESCRIPTION | VARCHAR(255) |  |  | The check definition description. |
| PROPERTIES | VARCHAR(4000) |  |  | The check definition properties. |
| IS_VALID | BOOL | X |  | The is valid flag. |

2.2.29.6 List of keys of the table check_definition

| Code | Primary |
| --- | --- |
| CHECK_DEF_PK | X |

2.2.29.7 List of indexes of the table check_definition

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| CHECK_DEF_IDX | X | X |  | check_definition |
| CHECK_DEF_ID_IDX | X |  |  | check_definition |

2.2.30 Table check_instance

2.2.30.1 Card of table check_instance

| Code | CHECK_INSTANCE |
| --- | --- |
| Comment | Table that holds a list of checks instance details |

2.2.30.2 Check constraint name of the table check_instance

CKT_CHECK_INSTANCE

2.2.30.3 List of outgoing references of the table check_instance

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_CHECK_INSTANCE__CHECK_BUCKET | check_bucket | fk_check_bucket_sid |
| FK_CHECK_INSTANCE__CHECK_DEF | check_definition | fk_check_definition_sid |

2.2.30.4 List of diagrams containing the table check_instance

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.30.5 List of columns of the table check_instance

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('check_instance_seq') | The surrogate key |
| FK_CHECK_DEFINITION_SID | INT8 | X |  | Foreign key to the check definition table. |
| FK_CHECK_BUCKET_SID | INT8 | X |  | Foreign key to the check bucket table. |
| ID | VARCHAR(255) | X |  | The id of the check instance. |
| NAME | VARCHAR(255) |  |  | The name of the check instance. |
| START_DATE | TIMESTAMP WITH TIME ZONE | X |  | The start date of the check instance. |
| END_DATE | TIMESTAMP WITH TIME ZONE |  |  | The end date. |
| STATUS | VARCHAR(255) | X |  | The status. |
| MESSAGE | VARCHAR(4000) |  |  | The check instance message. |

2.2.30.6 List of keys of the table check_instance

| Code | Primary |
| --- | --- |
| CHECK_DEF_PK | X |

2.2.30.7 List of indexes of the table check_instance

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| CHECK_INSTANCE_IDX | X | X |  | check_instance |
| CHECK_INSTANCE_ID_IDX | X |  |  | check_instance |
| CHECK_INSTANCE__CHECK_DEF_IDX |  |  | X | check_instance |
| CHECK_INSTANCE__CHECK_BUC_IDX |  |  | X | check_instance |

2.2.31 Table cluster_node

2.2.31.1 Card of table cluster_node

| Code | CLUSTER_NODE |
| --- | --- |
| Comment | The cluster nodes of the system |

2.2.31.2 Check constraint name of the table cluster_node

CKT_CLUSTER_NODE

2.2.31.3 List of diagrams containing the table cluster_node

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.31.4 List of columns of the table cluster_node

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('cluster_node_seq') | The surrogate key |
| NAME | VARCHAR(255) | X |  | The name of the node |
| PMODE_PATH | VARCHAR(255) | X |  | The directory path where the pmodes of the node are located |

2.2.31.5 List of keys of the table cluster_node

| Code | Primary |
| --- | --- |
| CLUSTER_NODE_PK | X |

2.2.31.6 List of indexes of the table cluster_node

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| CLUSTER_NODE_IDX | X | X |  | cluster_node |
| CLUSTER_NODE_NAME_UNQ | X |  |  | cluster_node |

2.2.32 Table conv_participant

2.2.32.1 Card of table conv_participant

| Code | CONV_PARTICIPANT |
| --- | --- |
| Comment | Table that holds infomation about the Participating Institution in a conversation or case instance |

2.2.32.2 Check constraint name of the table conv_participant

CKT_CONV_PARTICIPANT

2.2.32.3 List of outgoing references of the table conv_participant

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_CONV_PARTICIPANT__CONV | document_conversation | fk_conv_sid |
| FK_CONV_PARTICIPANT__ORG | organisation | fk_org_sid |

2.2.32.4 List of diagrams containing the table conv_participant

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.32.5 List of columns of the table conv_participant

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('conv_participant_seq') | The surrogate key |
| FK_CONV_SID | INT8 | X |  | Foreign key associated to the associated case. |
| FK_ORG_SID | INT8 | X |  | foreign key to organisation |
| CONV_PARTICIPANT_ROLE | VARCHAR(11) | X |  | The role of the participant in in a conversation or in a case |

2.2.32.6 List of keys of the table conv_participant

| Code | Primary |
| --- | --- |
| CONV_PARTICIPANT_PK | X |

2.2.32.7 List of indexes of the table conv_participant

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| CONV_PARTICIPANT_IDX | X | X |  | conv_participant |
| CONV_PARTICIPANT__CONV_IDX |  |  | X | conv_participant |
| CONV_PARTICIPANT__ORG_IDX |  |  | X | conv_participant |

2.2.33 Table doc_bversion_attachment

2.2.33.1 Card of table doc_bversion_attachment

| Code | DOC_BVERSION_ATTACHMENT |
| --- | --- |
| Comment | Many-to-many association between document_history entries and document_attachment entries |

2.2.33.2 Check constraint name of the table doc_bversion_attachment

CKT_DOC_BVERSION_ATTACHMENT

2.2.33.3 List of outgoing references of the table doc_bversion_attachment

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_DOC_BVERSION_ATT__DOC_ATT | document_attachment | fk_doc_attachment_sid |
| FK_DOC_BVERSION_ATT__DOC_BVERS | document_bversion | fk_doc_bversion_sid |

2.2.33.4 List of diagrams containing the table doc_bversion_attachment

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.33.5 List of columns of the table doc_bversion_attachment

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| FK_DOC_BVERSION_SID | INT8 | X |  | The surrogate key |
| FK_DOC_ATTACHMENT_SID | INT8 | X |  | Foreign key to document_attachment table |

2.2.33.6 List of indexes of the table doc_bversion_attachment

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| DOC_BVERSION_ATT__DOC_BVERS_IDX |  |  | X | doc_bversion_attachment |
| DOC_BVERSION_ATT__DOC_ATT_IDX |  |  | X | doc_bversion_attachment |

2.2.34 Table doc_bversion_subdoc_bversion

2.2.34.1 Card of table doc_bversion_subdoc_bversion

| Code | DOC_BVERSION_SUBDOC_BVERSION |
| --- | --- |
| Comment | Many-to-many association between document_bversion entries and subdocument_bversion entries |

2.2.34.2 Check constraint name of the table doc_bversion_subdoc_bversion

CKT_DOC_BVERSION_SUBDOC_BVERSI

2.2.34.3 List of outgoing references of the table doc_bversion_subdoc_bversion

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_DOC_BV_SUBDOC_BV__DOC_BV | document_bversion | fk_doc_bversion_sid |
| FK_DOC_BV_SUBDOC_BV__SUBDOC_BV | subdocument_bversion | fk_subdoc_bversion_sid |

2.2.34.4 List of diagrams containing the table doc_bversion_subdoc_bversion

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.34.5 List of columns of the table doc_bversion_subdoc_bversion

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| FK_DOC_BVERSION_SID | INT8 | X |  | The surrogate key |
| FK_SUBDOC_BVERSION_SID | INT8 | X |  | Foreign key to document_attachment table |

2.2.34.6 List of indexes of the table doc_bversion_subdoc_bversion

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| DOC_BV_SUBDOC_BV__DOC_BV_IDX |  |  | X | doc_bversion_subdoc_bversion |
| DOC_BV_SUBDOC_BV__SUBDOC_BV_IDX |  |  | X | doc_bversion_subdoc_bversion |

2.2.35 Table document

2.2.35.1 Card of table document

| Code | DOCUMENT |
| --- | --- |
| Comment | Document details |

2.2.35.2 Check constraint name of the table document

CKT_DOCUMENT

2.2.35.3 List of incoming references of the table document

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| FK_ACTION__DOCUMENT | action | fk_document_sid |
| FK_ACTION__P_DOCUMENT | action | fk_parent_document_sid |
| FK_BUSINESS_EXC__DOC | business_exception | fk_doc_sid |
| FK_DOC_ATTACH__DOC | document_attachment | fk_doc_sid |
| FK_DOC_BVERSION__DOC | document_bversion | fk_doc_sid |
| FK_DOC_COMMENT__DOC | document_comment | fk_doc_sid |
| FK_DOC_CONTENT__DOC | document_content | fk_doc_sid |
| FK_DOC_CONV__DOC | document_conversation | fk_doc_sid |
| FK_DOC_HIS__DOC | document_history | fk_doc_sid |
| FK_DOCUMENT__PARENT | document | fk_parent_sid |
| FK_NOTIFICATION__DOCUMENT | notification | fk_document_sid |
| FK_SUBDOC__DOC | subdocument | fk_document_sid |

2.2.35.4 List of outgoing references of the table document

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_DOC__DOC_BVERSION | document_bversion | fk_doc_bversion_sid |
| FK_DOC__DOC_TYPE_VERSION | document_type_version | fk_doc_type_version_sid |
| FK_DOCUMENT__CASE | rina_case | fk_case_sid |
| FK_DOCUMENT__PARENT | document | fk_parent_sid |

2.2.35.5 List of diagrams containing the table document

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.35.6 List of columns of the table document

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('document_seq') | The surrogate key |
| VERSION | INT4 | X | 1 | The system version. It is automatically increased by Hibernate each time the row is updated. |
| FK_CASE_SID | INT8 |  |  | Foreign key to the rina_case table |
| FK_DOC_TYPE_VERSION_SID | INT8 | X |  | Foreign key to document_type_version table |
| FK_PARENT_SID | INT8 |  |  | The fk to the parent of the document. |
| FK_DOC_BVERSION_SID | INT8 |  |  | The content of the document |
| ID | VARCHAR(255) | X |  | Id of the document |
| NAME | VARCHAR(255) |  |  | The name of the document. |
| DISPLAY_NAME | VARCHAR(255) |  |  | The display name of the Document |
| STATUS | VARCHAR(20) |  |  | The status of the Document. Possible values: NEW("new"), EMPTY("empty"), ACTIVE("active"), SENT("sent"), CANCELLED("cancelled"), RECEIVED("received"); |
| INTERNAL_ID | VARCHAR(255) |  |  | The internal id. |
| DM_PROCESS_ID | INT8 |  |  | The process id of the document manager |
| SUB_PROCESS_ID | INT8 |  |  | The subprocess id |
| READ_TEMPLATE | VARCHAR(255) |  |  | Template for reading the document |
| CREATE_TEMPLATE | VARCHAR(255) |  |  | Template for creating the document |
| DIRECTION | VARCHAR(255) |  |  | The direction of the Document. Possible values: IN, OUT |
| MIME_TYPE | VARCHAR(50) |  |  | The mime type of the document. |
| DOC_ORDER | INT4 | X | 1 | The order of the document |
| TO_SENDER_ONLY | BOOL | X | false | TRUE If the document is only to sender |
| IS_ADMIN | BOOL | X | false | TRUE If this is an admin document |
| IS_BULK | BOOL | X | false | Whether or not the document is a Bulk(Batch) Document |
| IS_DUMMY_DOCUMENT | BOOL | X | false | True if the document is just a dummy. |
| IS_FIRST_DOCUMENT | BOOL | X | false | TRUE if this is the first document |
| IS_MLC | BOOL | X | false | TRUE if this is MLC document |
| IS_STARTER | BOOL | X | false | If document already sent |
| IS_SEND_EXECUTED | BOOL | X | false | TRUE If document already sent |
| IS_REPLY | BOOL | X | false | The is reply flag. |
| IS_VALID | BOOL | X | true | The is valid flag. |
| VALIDATION_ERRORS | TEXT |  |  | The validation errors flag. |
| HAS_REPLY_CLARIFY | BOOL | X | false | TRUE if it has reply clarify |
| HAS_REJECT | BOOL | X | false | TRUE if it has reject |
| HAS_LETTER | BOOL | X | false | TRUE if it has letter |
| HAS_CLARIFY | BOOL | X | false | TRUE if it has clarify |
| HAS_CANCEL | BOOL | X | false | TRUE if it has cancel |
| HAS_BUSINESS_VALIDATION | BOOL | X | false | Requires any business side validation before any action. Default is false. |
| HAS_MULTIPLE_VERSIONS | BOOL | X | false | TRUE if the document has multiple versions |
| SELECT_PARTICIPANTS | BOOL | X | false | TRUE If select participant |
| ALLOWS_ATTACHMENTS | BOOL | X | false | The document allows having attachments. Default is false. |
| CAN_BE_SENT_WITHOUT_CHILD | BOOL | X | false | True if the document can be sent without any children. |
| COUNTER | INT4 | X | 1 | The counter value of the document. |
| BUSINESS_REFERENCE_MANAGER | TEXT |  |  | Keeps information in JSON format of subdocuments business references for bulk documents |
| RECEIVED_AT | TIMESTAMP WITH TIME ZONE |  |  | The date when the document was received. |
| ORIG_CREATED_AT | TIMESTAMP WITH TIME ZONE |  |  | Keeps the original date when document was created by sender |
| ORIG_UPDATED_AT | TIMESTAMP WITH TIME ZONE |  |  | Keeps the original date when document was updated by sender |
| CREATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | The time that the document was first inserted into the DB |
| UPDATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | The last time that the document was updated |
| CREATED_BY | VARCHAR(255) | X | '0' | The person that created the record. |
| UPDATED_BY | VARCHAR(255) | X | '0' | The person that last updated the record. |
| RANDOM_STRING | VARCHAR(255) | X | 'A1' | Random string for unicity in the document. |

2.2.35.7 List of keys of the table document

| Code | Primary |
| --- | --- |
| DOCUMENT_PK | X |

2.2.35.8 List of indexes of the table document

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| DOC_IDX | X | X |  | document |
| DOC_CASE_IDX |  |  | X | document |
| DOC__DOC_TYPE_VERSION_IDX |  |  | X | document |
| DOC__DOC_BVERSION_IDX |  |  | X | document |
| DOC_ID_UNQ | X |  |  | document |

2.2.36 Table document_attachment

2.2.36.1 Card of table document_attachment

| Code | DOCUMENT_ATTACHMENT |
| --- | --- |
| Comment | The attachments associated to a specific document |

2.2.36.2 Check constraint name of the table document_attachment

CKT_DOCUMENT_ATTACHMENT

2.2.36.3 List of incoming references of the table document_attachment

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| FK_DOC_BVERSION_ATT__DOC_ATT | doc_bversion_attachment | fk_doc_attachment_sid |

2.2.36.4 List of outgoing references of the table document_attachment

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_DOC_ATTACH__DOC | document | fk_doc_sid |

2.2.36.5 List of diagrams containing the table document_attachment

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.36.6 List of columns of the table document_attachment

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('doc_attachment_seq') | The surrogate key |
| VERSION | INT4 | X | 1 | The system version. It is automatically increased by Hibernate each time the row is updated. |
| FK_DOC_SID | INT8 | X |  | Foreign key to the document table. |
| MIME_TYPE | VARCHAR(50) | X |  | The mime type of the document attachment. Possible values: APP_PDF APP_MSWORD APP_MSEXCEL APP_MSPOWERPOINT APP_OPENXML_DOC APP_OPENXML_SPREADSHEET APP_OPENXML_PRESENTATION APP_XML APP_ZIP APP_GZIP IMG_JPEG IMG_PNG IMG_TIFF TXT_RTF TXT_XML // Mimetypes NOT included in the SBDH XSD definition APP_X_ZIP APP_OCTET_STREAM APP_X_ZIP_COMPRESSED |
| ID | VARCHAR(255) | X |  | The document attachment id. |
| NAME | VARCHAR(255) |  |  | The name of the attachement. |
| FILENAME | VARCHAR(1024) |  |  | The directory path where the assignment is stored |
| PATHNAME | VARCHAR(1024) | X |  | The complete pathname to retrieve the attachment. |
| IS_MEDICAL | BOOL | X | false | The is medical flag. |
| IS_ACTIVE | BOOL | X | true | The status of the attachemnt (false it has been deleted) |
| CREATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | Date & Time of Creation. |
| UPDATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | Date & time of last update. |
| CREATED_BY | VARCHAR(255) | X | '0' | The person that created the record. |
| UPDATED_BY | VARCHAR(255) | X | '0' | The person that last updated the record. |

2.2.36.7 List of keys of the table document_attachment

| Code | Primary |
| --- | --- |
| DOC_ATTACHEMENT_PK | X |

2.2.36.8 List of indexes of the table document_attachment

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| DOC_ATTACHEMENT_IDX | X | X |  | document_attachment |
| DOC_ATTACHMENT_ID_UNQ | X |  |  | document_attachment |
| DOC_ATTACHMENT__DOC_IDX |  |  | X | document_attachment |

2.2.37 Table document_bversion

2.2.37.1 Card of table document_bversion

| Code | DOCUMENT_BVERSION |
| --- | --- |
| Comment | The business version associated to a specific document |

2.2.37.2 Check constraint name of the table document_bversion

CKT_DOCUMENT_BVERSION

2.2.37.3 List of incoming references of the table document_bversion

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| FK_DOC__DOC_BVERSION | document | fk_doc_bversion_sid |
| FK_DOC_BV_SUBDOC_BV__DOC_BV | doc_bversion_subdoc_bversion | fk_doc_bversion_sid |
| FK_DOC_BVERSION_ATT__DOC_BVERS | doc_bversion_attachment | fk_doc_bversion_sid |
| FK_DOC_CONV__DOC_BVERSION | document_conversation | fk_doc_bversion_sid |
| FK_DOC_HIS__DOC_BVERSION | document_history | fk_doc_bversion_sid |
| FK_DOC_THUMB__DOC_BVER | document_thumbnail | fk_doc_bversion_sid |

2.2.37.4 List of outgoing references of the table document_bversion

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_DOC_BVERSION__DOC | document | fk_doc_sid |
| FK_DOC_BVERSION__DOC_CONTENT | document_content | fk_doc_content_sid |

2.2.37.5 List of diagrams containing the table document_bversion

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.37.6 List of columns of the table document_bversion

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('document_bversion_seq') | The surrogate key |
| FK_DOC_SID | INT8 | X |  | Foreign key to the document table. |
| FK_DOC_CONTENT_SID | INT8 |  |  | Foreign key to the document content table. |
| ID | INT4 | X | 1 | The id of the document bversion. |
| VERSION | INT4 | X | 1 | The system version. It is automatically increased by Hibernate each time the row is updated. |
| ORIG_CREATED_AT | TIMESTAMP WITH TIME ZONE |  |  |  |
| CREATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | The time that the document bversion was first inserted into the DB |
| UPDATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | The last time that the document bversion was updated |
| CREATED_BY | VARCHAR(255) | X | '0' | The person that created the record. |
| UPDATED_BY | VARCHAR(255) | X | '0' | The person that last updated the record. |

2.2.37.7 List of keys of the table document_bversion

| Code | Primary |
| --- | --- |
| DOCUMENT_BVERSION_PK | X |

2.2.37.8 List of indexes of the table document_bversion

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| DOCUMENT_BVERSION_IDX | X | X |  | document_bversion |
| DOC_BVERSION__DOC_CONTENT_IDX |  |  | X | document_bversion |
| DOC_BVERSION__DOC_IDX |  |  | X | document_bversion |
| DOC_BVERSION_UNQ | X |  |  | document_bversion |

2.2.38 Table document_comment

2.2.38.1 Card of table document_comment

| Code | DOCUMENT_COMMENT |
| --- | --- |
| Comment | The comments associated to a specific document |

2.2.38.2 Check constraint name of the table document_comment

CKT_DOCUMENT_COMMENT

2.2.38.3 List of outgoing references of the table document_comment

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_DOC_COMMENT__DOC | document | fk_doc_sid |

2.2.38.4 List of diagrams containing the table document_comment

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.38.5 List of columns of the table document_comment

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('doc_comment_seq') | The surrogate key |
| VERSION | INT4 | X | 1 | The system version. It is automatically increased by Hibernate each time the row is updated. |
| FK_DOC_SID | INT8 | X |  | Foreign key to the document table |
| ID | VARCHAR(255) | X |  | The id of the document content. |
| TEXT | TEXT | X |  | The comment |
| CREATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | Date & Time the entity was created |
| UPDATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | Date & Time the entity was last updated |
| CREATED_BY | VARCHAR(255) | X | '0' | The person/process that created the record. |
| UPDATED_BY | VARCHAR(255) | X | '0' | The person/process that last updated the record. |

2.2.38.6 List of keys of the table document_comment

| Code | Primary |
| --- | --- |
| DOC_COMMENT_PK | X |

2.2.38.7 List of indexes of the table document_comment

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| DOC_COMMENT_IDX | X | X |  | document_comment |
| DOC_COMMENT__DOC_IDX |  |  | X | document_comment |
| DOC_COMMENT_ID_UNQ | X |  |  | document_comment |

2.2.39 Table document_content

2.2.39.1 Card of table document_content

| Code | DOCUMENT_CONTENT |
| --- | --- |
| Comment | The content associated to a specific document |

2.2.39.2 Check constraint name of the table document_content

CKT_DOCUMENT_CONTENT

2.2.39.3 List of incoming references of the table document_content

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| FK_DOC_BVERSION__DOC_CONTENT | document_bversion | fk_doc_content_sid |

2.2.39.4 List of outgoing references of the table document_content

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_DOC_CONTENT__DOC | document | fk_doc_sid |

2.2.39.5 List of diagrams containing the table document_content

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.39.6 List of columns of the table document_content

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('document_content_seq') | The surrogate key |
| FK_DOC_SID | INT8 | X |  | Foreign key to the document table. |
| CONTENT | TEXT | X |  | The content of the document. |
| IS_ACTIVE | BOOL | X | true | The is active flag of the document content. |

2.2.39.7 List of keys of the table document_content

| Code | Primary |
| --- | --- |
| DOC_CONTENT_PK | X |

2.2.39.8 List of indexes of the table document_content

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| DOC_CONTENT_IDX | X | X |  | document_content |
| DOC_CONTENT__DOC_IDX |  |  | X | document_content |

2.2.40 Table document_conversation

2.2.40.1 Card of table document_conversation

| Code | DOCUMENT_CONVERSATION |
| --- | --- |
| Comment | The attachments associated to a specific document |

2.2.40.2 Check constraint name of the table document_conversation

CKT_DOCUMENT_CONVERSATION

2.2.40.3 List of incoming references of the table document_conversation

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| FK_CONV_PARTICIPANT__CONV | conv_participant | fk_conv_sid |
| FK_USER_MSG__DOC_CONV | user_message | fk_doc_conv_sid |

2.2.40.4 List of outgoing references of the table document_conversation

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_DOC_CONV__DOC | document | fk_doc_sid |
| FK_DOC_CONV__DOC_BVERSION | document_bversion | fk_doc_bversion_sid |

2.2.40.5 List of diagrams containing the table document_conversation

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.40.6 List of columns of the table document_conversation

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('doc_conversation_seq') | The surrogate key |
| FK_DOC_SID | INT8 | X |  | Foreign key to the document table. |
| FK_DOC_BVERSION_SID | INT8 |  |  | Foreign key to the document_bversion table. |
| ID | VARCHAR(255) | X |  | The id of the document conversation. |
| DATE | TIMESTAMP WITH TIME ZONE |  |  | Date & Time of Creation. |
| RECEIVED_AT | TIMESTAMP WITH TIME ZONE |  |  | Date & Time when the conversation was received. |

2.2.40.7 List of keys of the table document_conversation

| Code | Primary |
| --- | --- |
| DOC_CONVERSATION_PK | X |

2.2.40.8 List of indexes of the table document_conversation

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| DOC_CONVERSATION_IDX | X | X |  | document_conversation |
| DOC_CONV__DOC_BVERSION_IDX |  |  | X | document_conversation |
| DOC_CONV__DOC_IDX |  |  | X | document_conversation |
| DOC_CONV_ID_UNQ | X |  |  | document_conversation |

2.2.41 Table document_history

2.2.41.1 Card of table document_history

| Code | DOCUMENT_HISTORY |
| --- | --- |
| Comment | The history of the document |

2.2.41.2 Check constraint name of the table document_history

CKT_DOCUMENT_HISTORY

2.2.41.3 List of outgoing references of the table document_history

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_DOC_HIS__CASE | rina_case | fk_case_sid |
| FK_DOC_HIS__DOC | document | fk_doc_sid |
| FK_DOC_HIS__DOC_BVERSION | document_bversion | fk_doc_bversion_sid |
| FK_DOC_HIS__DOC_TYPE_VERSION | document_type_version | fk_doc_type_version_sid |

2.2.41.4 List of diagrams containing the table document_history

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.41.5 List of columns of the table document_history

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('document_history_seq') | The surrogate key |
| FK_DOC_SID | INT8 | X |  | Foreign key to the document table |
| FK_CASE_SID | INT8 |  |  | Foreign key to the rina_case table |
| FK_DOC_TYPE_VERSION_SID | INT8 | X |  | Foreign key to the document type version table. |
| FK_DOC_BVERSION_SID | INT8 |  |  | Foreign key to the doc_bversion table. |
| VERSION | INT4 | X |  | The system version of the correspospnding document. The value is set to that of the current entry of the document after the last update. |
| ID | VARCHAR(255) | X |  | the id of the document |
| NAME | VARCHAR(255) |  |  | The name of the document history. |
| DISPLAY_NAME | VARCHAR(255) |  |  | The display name of the Document |
| STATUS | VARCHAR(20) |  |  | The status of the Document. Possible values: NEW("new"), EMPTY("empty"), ACTIVE("active"), SENT("sent"), CANCELLED("cancelled"), RECEIVED("received"); |
| BUSINESS_VERSION_ID | VARCHAR(255) |  |  | The business version id value. |
| INTERNAL_ID | VARCHAR(255) |  |  | The internal id. |
| DM_PROCESS_ID | INT8 |  |  | The process id of the document manager |
| SUB_PROCESS_ID | INT8 |  |  | The subprocess id |
| CREATE_TEMPLATE | VARCHAR(255) |  |  | Template for creating the document |
| DIRECTION | VARCHAR(255) |  |  | The direction of the Document |
| MIME_TYPE | VARCHAR(255) |  |  | The mime type. |
| DOC_ORDER | INT4 |  |  | The order of the document |
| TO_SENDER_ONLY | BOOL |  |  | TRUE If the document is only to sender |
| IS_ADMIN | BOOL |  |  | TRUE If this is an admin document |
| IS_BULK | BOOL |  |  | Whether or not the document is a Bulk(Batch) Document |
| IS_DUMMY_DOCUMENT | BOOL | X | false | True if the document is just a dummy. |
| IS_FIRST_DOCUMENT | BOOL |  |  | TRUE if this is the first document |
| IS_MLC | BOOL |  |  | TRUE if this is MLC document |
| IS_STARTER | BOOL |  |  | If document already sent |
| IS_SEND_EXECUTED | BOOL |  |  | TRUE If document already sent |
| HAS_REPLY_CLARIFY | BOOL |  |  | TRUE if it has reply clarify |
| HAS_REJECT | BOOL |  |  | TRUE if it has reject |
| HAS_LETTER | BOOL |  |  | TRUE if it has letter |
| HAS_CLARIFY | BOOL |  |  | TRUE if it has clarify |
| HAS_CANCEL | BOOL |  |  | TRUE if it has cancel |
| HAS_BUSINESS_VALIDATION | BOOL | X | false | Requires any business side validation before any action. Default is false. |
| HAS_MULTIPLE_VERSIONS | BOOL |  |  | TRUE if the document has multiple versions |
| SELECT_PARTICIPANTS | BOOL |  |  | TRUE If select participant |
| ALLOWS_ATTACHMENTS | BOOL | X | false | The document allows having attachments. Default is false. |
| CAN_BE_SENT_WITHOUT_CHILD | BOOL |  |  | True if the document can be sent without any children. |
| UPDATED_AT | TIMESTAMP WITH TIME ZONE | X |  | The time that the document was updated |
| UPDATED_BY | VARCHAR(255) | X |  | The person/process that last updated the record. |

2.2.41.6 List of keys of the table document_history

| Code | Primary |
| --- | --- |
| DOC_HIS_PK | X |

2.2.41.7 List of indexes of the table document_history

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| DOC_HIS_IDX | X | X |  | document_history |
| DOC_HIS_DOC_SID_VERSION_UNQ | X |  |  | document_history |
| DOC_HIS__DOC_IDX |  |  | X | document_history |
| DOC_HIS__DOC_TYPE_VERSION_IDX |  |  | X | document_history |
| DOC_HIS__DOC_BVERSION_IDX |  |  | X | document_history |

2.2.42 Table document_thumbnail

2.2.42.1 Card of table document_thumbnail

| Code | DOCUMENT_THUMBNAIL |
| --- | --- |
| Comment | Many-to-one association between document_bversion entries and document_thmbnail entries |

2.2.42.2 Check constraint name of the table document_thumbnail

CKT_DOCUMENT_THUMBNAIL

2.2.42.3 List of outgoing references of the table document_thumbnail

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_DOC_THUMB__DOC_BVER | document_bversion | fk_doc_bversion_sid |

2.2.42.4 List of diagrams containing the table document_thumbnail

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.42.5 List of columns of the table document_thumbnail

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('doc_thumbnail_seq') | The surrogate key |
| FK_DOC_BVERSION_SID | INT8 | X |  | Foreign key to the doc_bversion table. |
| LANG | VARCHAR(2) | X |  | The language of the document thumbnail. Possible values: bg, cs, da, de, en, el, es, et, fi, fr, hr, hu, it, lt, lv, mt, nl, no, pl, pt, ro, sk, sl, sv. |
| CONTENT | TEXT | X |  | The content of the thumbnail for the document. |

2.2.42.6 List of keys of the table document_thumbnail

| Code | Primary |
| --- | --- |
| DOC_THUMBNAIL_PK | X |

2.2.42.7 List of indexes of the table document_thumbnail

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| DOC_THUMBNAIL_IDX | X | X |  | document_thumbnail |
| DOC_THUMB__DOC_BVER_IDX |  |  | X | document_thumbnail |

2.2.43 Table document_type

2.2.43.1 Card of table document_type

| Code | DOCUMENT_TYPE |
| --- | --- |
| Comment | The type of document |

2.2.43.2 Check constraint name of the table document_type

CKT_DOCUMENT_TYPE

2.2.43.3 List of incoming references of the table document_type

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| FK_DOC_TYPE__DOC_TYPE_VERSION | document_type_version | fk_doc_type_sid |
| FK_NIE_EVENT__DOC_TYPE | nie_event | fk_doc_type_sid |
| FK_NOTIF__DOC_TYPE | notification | fk_document_type_sid |
| FK_SUBSCRBR__DOC_TYPE | nie_subscriber | fk_document_type_sid |

2.2.43.4 List of outgoing references of the table document_type

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_DOC_TYPE__PROC_DEF_VERSION | process_def_version | fk_proc_def_version_sid |

2.2.43.5 List of diagrams containing the table document_type

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.43.6 List of columns of the table document_type

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('doc_type_seq') | The surrogate key |
| FK_PROC_DEF_VERSION_SID | INT8 |  |  | Foreign key that links the Case to the process definition's version table |
| TYPE | VARCHAR(255) | X |  | The type of document |
| NAME | VARCHAR(255) |  |  | The name of the document type. |

2.2.43.7 List of keys of the table document_type

| Code | Primary |
| --- | --- |
| DOC_TYPE_PK | X |

2.2.43.8 List of indexes of the table document_type

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| DOC_TYPE_IDX | X | X |  | document_type |
| DOC_TYPE_TYPE_UNQ | X |  |  | document_type |
| DOC_TYPE__PROC_DEF_VERSION_IDX |  |  | X | document_type |

2.2.44 Table document_type_version

2.2.44.1 Card of table document_type_version

| Code | DOCUMENT_TYPE_VERSION |
| --- | --- |
| Comment | The version of the document type |

2.2.44.2 Check constraint name of the table document_type_version

CKT_DOCUMENT_TYPE_VERSION

2.2.44.3 List of incoming references of the table document_type_version

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| FK_ACTION__DOC_TYPE_VER | action | fk_doc_type_version_sid |
| FK_DOC__DOC_TYPE_VERSION | document | fk_doc_type_version_sid |
| FK_DOC_HIS__DOC_TYPE_VERSION | document_history | fk_doc_type_version_sid |
| FK_TRANSPOS__DOC_TYPE_VERSION | transposition | fk_doc_type_version_sid |

2.2.44.4 List of outgoing references of the table document_type_version

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_DOC_TYPE__DOC_TYPE_VERSION | document_type | fk_doc_type_sid |

2.2.44.5 List of diagrams containing the table document_type_version

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.44.6 List of columns of the table document_type_version

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('doc_type_version_seq') | The surrogate key |
| FK_DOC_TYPE_SID | INT8 | X |  | Foreign key to document_type table |
| BVERSION | VARCHAR(10) | X |  | The bversion value for the document type version. |
| DEFAULT_DOC_CONTENT | TEXT |  |  | The default document content |
| METADATA | TEXT |  |  | The metadata of the document type version. |

2.2.44.7 List of keys of the table document_type_version

| Code | Primary |
| --- | --- |
| DOC_TYPE_VERSION_PK | X |

2.2.44.8 List of indexes of the table document_type_version

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| DOC_TYPE_VERSION_IDX | X | X |  | document_type_version |
| DOC_TYPE_TYPE_VERSION_UNQ | X |  |  | document_type_version |

2.2.45 Table field

2.2.45.1 Card of table field

| Code | FIELD |
| --- | --- |
| Comment | Fields to be shown in Case Search Results |

2.2.45.2 Check constraint name of the table field

CKT_FIELD

2.2.45.3 List of outgoing references of the table field

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_FIELD__FIELD_CHOOSER | field_chooser | fk_field_chooser_sid |

2.2.45.4 List of diagrams containing the table field

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.45.5 List of columns of the table field

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('field_seq') | The surogate key. |
| FK_FIELD_CHOOSER_SID | INT8 | X |  | Foreign key to the field_chooser table |
| ID | VARCHAR(255) | X |  | The id of the field. |
| NAME | VARCHAR(255) | X |  | The name of the field |
| TYPE | VARCHAR(50) |  |  | The type of the field. Possible values: Long, Integer, Double, null. |
| SORT | VARCHAR(60) | X | 'none' | The direction that the values of the Field will be sorted Can be either 'ASCENDING', 'DESCENDING' or 'NONE' |
| SHOW | BOOL | X | false | The flag to determine if the Field is to be shown or not |

2.2.45.6 List of keys of the table field

| Code | Primary |
| --- | --- |
| PK_FIELD | X |

2.2.45.7 List of indexes of the table field

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| FIELD_IDX | X | X |  | field |
| FIIELD__FIELD_CHOOSER_IDX |  |  | X | field |
| FIELD_FIELD_CHOOSER_NAME_UNQ | X |  |  | field |

2.2.46 Table field_chooser

2.2.46.1 Card of table field_chooser

| Code | FIELD_CHOOSER |
| --- | --- |
| Comment | Table for associating with the list of Fields to be shown in Case Search Results |

2.2.46.2 Check constraint name of the table field_chooser

CKT_FIELD_CHOOSER

2.2.46.3 List of incoming references of the table field_chooser

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| FK_FIELD__FIELD_CHOOSER | field | fk_field_chooser_sid |

2.2.46.4 List of outgoing references of the table field_chooser

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_FIELD_CHOOSER__PROCESS_DEF | process_def | FK_PROCESS_DEF_SID |
| FK_FIELD_CHOOSER__USER | iam_user | FK_USER_SID |

2.2.46.5 List of diagrams containing the table field_chooser

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.46.6 List of columns of the table field_chooser

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('field_chooser_seq') | The surrogate key |
| FK_USER_SID | INT8 | X |  | Foreign key to the iam_user table |
| FK_PROCESS_DEF_SID | INT8 | X |  | Foreign key to the process_definition table |

2.2.46.7 List of keys of the table field_chooser

| Code | Primary |
| --- | --- |
| PK_FIELD_CHOOSER | X |

2.2.46.8 List of indexes of the table field_chooser

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| CHOOSER_IDX | X | X |  | field_chooser |
| CHOOSER__PROCESS_DEF_IDX |  |  | X | field_chooser |
| CHOOSER__USER_IDX |  |  | X | field_chooser |
| CHOOSER_USER_PROCESS_DEF_UNQ | X |  |  | field_chooser |

2.2.47 Table global_param

2.2.47.1 Card of table global_param

| Code | GLOBAL_PARAM |
| --- | --- |
| Comment | The global application parameters. |

2.2.47.2 Check constraint name of the table global_param

CKT_GLOBAL_PARAM

2.2.47.3 List of outgoing references of the table global_param

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_GLBL_PARAM__GLBL_PARAM_GRP | global_param_group | fk_global_param_group_sid |

2.2.47.4 List of diagrams containing the table global_param

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.47.5 List of columns of the table global_param

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('global_param_seq') | The surrogate key |
| FK_GLOBAL_PARAM_GROUP_SID | INT8 |  |  | Foreign key to the global param group table. |
| KEY | VARCHAR(255) | X |  | The key of the parameter |
| VALUE | VARCHAR(255) |  |  | the value of the parameter |

2.2.47.6 List of keys of the table global_param

| Code | Primary |
| --- | --- |
| GLOBAL_PARAM_PK | X |

2.2.47.7 List of indexes of the table global_param

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| GLOBAL_PARAM_IDX | X | X |  | global_param |
| GLOBAL_PARAM_KEY_UNQ | X |  |  | global_param |
| GLBL_PRM__GLBL_PRM_GRP_IDX |  |  | X | global_param |

2.2.48 Table global_param_group

2.2.48.1 Card of table global_param_group

| Code | GLOBAL_PARAM_GROUP |
| --- | --- |
| Comment | Table that holds a group of global_application_parameters, with version for optimistic locking and auditing properties. |

2.2.48.2 Check constraint name of the table global_param_group

CKT_GLOBAL_PARAM_GROUP

2.2.48.3 List of incoming references of the table global_param_group

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| FK_GLBL_PARAM__GLBL_PARAM_GRP | global_param | fk_global_param_group_sid |

2.2.48.4 List of diagrams containing the table global_param_group

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.48.5 List of columns of the table global_param_group

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('global_param_group_seq') | The surrogate key |
| VERSION | INT4 | X | 1 | The system version. It is automatically increased by Hibernate each time the row is updated. |
| NAME | VARCHAR(255) | X |  | The name of the global param group. Possible values: TEST. |
| CREATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | Date & Time by whom the tenant was created |
| UPDATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | Date & Time the tenant's details was updated |
| CREATED_BY | VARCHAR(255) | X | '0' | The person/process that created the record. |
| UPDATED_BY | VARCHAR(255) | X | '0' | The person/process that last updated the record. |
| RANDOM_STRING | VARCHAR(255) | X | 'A1' | Random string saved for the global param group. |

2.2.48.6 List of keys of the table global_param_group

| Code | Primary |
| --- | --- |
| GLOBAL_PARAM_GROUP_PK | X |

2.2.48.7 List of indexes of the table global_param_group

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| GLOBAL_PARAM_GROUP_IDX | X | X |  | global_param_group |
| GLOBAL_PARAM_GROUP_NAME_UNQ | X |  |  | global_param_group |

2.2.49 Table iam_group

2.2.49.1 Card of table iam_group

| Code | IAM_GROUP |
| --- | --- |
| Comment | Group Details |

2.2.49.2 Check constraint name of the table iam_group

CKT_IAM_GROUP

2.2.49.3 List of incoming references of the table iam_group

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| FK_ASSIGN_GROUP__GROUP | assignment_group | fk_group_sid |
| FK_IAM_GROUP__IAM_GROUP | iam_group | fk_parent_sid |
| FK_IAM_USERGROUP__GROUP | iam_user_group | fk_group_sid |
| FK_RULE_CREATOR_GROUP__GROUP | rule_creator_group | fk_group_sid |
| FK_RULE_GROUP__GROUP | rule_group | fk_group_sid |
| FK_SEARCH_DEF_GROUP__GROUP | search_def_group | fk_iam_group_sid |

2.2.49.4 List of outgoing references of the table iam_group

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_GROUP__ORIGIN | iam_origin | fk_origin_sid |
| FK_IAM_GROUP__IAM_GROUP | iam_group | fk_parent_sid |
| FK_IAM_GROUP__TENANT | tenant | fk_tenant_sid |

2.2.49.5 List of diagrams containing the table iam_group

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.49.6 List of columns of the table iam_group

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('iam_group_seq') | the surrogate key |
| VERSION | INT4 | X | 1 | The system version. It is automatically increased by Hibernate each time the row is updated. |
| FK_ORIGIN_SID | INT8 |  |  | Foreign key to the origin table |
| FK_TENANT_SID | INT8 | X |  | Foreign key to the tenant table |
| FK_PARENT_SID | INT8 |  |  | Foreign key to parent entry of the iam_group table |
| NAME | VARCHAR(255) | X |  | The name of the group |
| ID | VARCHAR(255) | X |  | The id. |
| DISPLAY_NAME | VARCHAR(255) | X |  | The display name of the Group |
| PARENT_PATH | VARCHAR(1024) |  |  | The path to the parent. |
| DESCRIPTION | VARCHAR(255) |  |  | The description of the Group |
| IS_DELETED | BOOL | X | false | Flag indicating if this group is deleted |
| IS_ORGANISATION_UNIT | BOOL | X | true | The is organisation unit flag. |
| CREATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | The time that the group was first inserted into the DB |
| UPDATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | The last time that the group was updated |
| CREATED_BY | VARCHAR(255) | X | '0' | The person/process that created the record. |
| UPDATED_BY | VARCHAR(255) | X | '0' | The person/process that last updated the record. |

2.2.49.7 List of keys of the table iam_group

| Code | Primary |
| --- | --- |
| PK_IAM_GROUP | X |

2.2.49.8 List of indexes of the table iam_group

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| GROUP_IDX | X | X |  | iam_group |
| GROUP__TENANT_IDX |  |  | X | iam_group |
| GROUP__ORIGIN_IDX |  |  | X | iam_group |
| GROUP_NAME_UNQ | X |  |  | iam_group |
| GROUP_NAME_WITH_NULL_PARENT_UNQ | X |  |  | iam_group |
| GROUP_ID_UNQ | X |  |  | iam_group |

2.2.50 Table iam_origin

2.2.50.1 Card of table iam_origin

| Code | IAM_ORIGIN |
| --- | --- |
| Comment | Origin details (Used for LDAP purposes) |

2.2.50.2 Check constraint name of the table iam_origin

CKT_IAM_ORIGIN

2.2.50.3 List of incoming references of the table iam_origin

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| FK_GROUP__ORIGIN | iam_group | fk_origin_sid |
| FK_ORIGIN__USER | iam_user | fk_origin_sid |

2.2.50.4 List of diagrams containing the table iam_origin

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.50.5 List of columns of the table iam_origin

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('iam_origin_seq') | The surrogate key |
| NAME | VARCHAR(255) | X |  | The name of the origin |
| DESCRIPTION | VARCHAR(255) |  |  | Description of origin |

2.2.50.6 List of keys of the table iam_origin

| Code | Primary |
| --- | --- |
| ORIGIN_PK | X |

2.2.50.7 List of indexes of the table iam_origin

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| ORIGIN_IDX | X | X |  | iam_origin |
| ORIGIN_NAME_UNQ | X |  |  | iam_origin |

2.2.51 Table iam_user

2.2.51.1 Card of table iam_user

| Code | IAM_USER |
| --- | --- |
| Comment | User details |

2.2.51.2 Check constraint name of the table iam_user

CKT_IAM_USER

2.2.51.3 List of incoming references of the table iam_user

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| FK_ASSIGN_USER__USER | assignment_user | fk_user_sid |
| FK_FIELD_CHOOSER__USER | field_chooser | FK_USER_SID |
| FK_IAM_USER__SEARCH_DEF | search_definition | fk_iam_user_sid |
| FK_IAM_USERGROUP__USER | iam_user_group | fk_user_sid |
| FK_NOTIF__IAM_USER | notification | fk_creator_sid |
| FK_NOTIF_USER__USER | notification_user | fk_user_sid |
| FK_RULE_CREATOR_USER__USER | rule_creator_user | fk_user_sid |
| FK_RULE_USER__USER | rule_user | fk_user_sid |
| FK_SEARCH_DEF_USER__USER | search_def_user | fk_iam_user_sid |
| FK_USER_PROFILE__USER | user_profile | fk_user_sid |

2.2.51.4 List of outgoing references of the table iam_user

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_IAM_USER__TENANT | tenant | fk_tenant_sid |
| FK_ORIGIN__USER | iam_origin | fk_origin_sid |

2.2.51.5 List of diagrams containing the table iam_user

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.51.6 List of columns of the table iam_user

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('iam_user_seq') | The surrogate key |
| VERSION | INT4 | X | 1 | The system version. It is automatically increased by Hibernate each time the row is updated. |
| FK_ORIGIN_SID | INT8 |  |  | Foreign key to the origin table |
| FK_TENANT_SID | INT8 |  |  | Foreign key to the tenant table |
| USERNAME | VARCHAR(255) | X |  | The username of the User |
| ID | VARCHAR(255) | X |  | The id of the iam user. |
| FIRST_NAME | VARCHAR(255) | X |  | The first name of the User |
| LAST_NAME | VARCHAR(255) | X |  | The last name of the User |
| MIDDLE_NAMES | VARCHAR(255) |  |  | The middle names of the User |
| PHONE_NUMBER | VARCHAR(255) |  |  |  |
| EMAIL | VARCHAR(255) |  |  | The email address of the User |
| KEYSTORE_ALIAS | VARCHAR(1024) |  |  |  |
| PASSWORD | VARCHAR(255) |  |  | The password of the User |
| SALT | VARCHAR(255) | X | 'salt' | Salt field used for encrypting the password |
| IS_SYSTEM | BOOL | X | false | The is system flag. |
| IS_ENABLED | BOOL | X | true | True is the user is enabled |
| IS_DELETED | BOOL | X | false | Flag indicating if this user is deleted |
| IS_ADMIN | BOOL | X | false | Flag indicating if this user is an administrator |
| CREATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | The time that the user was first inserted into the DB |
| UPDATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | The last time that the user was updated |
| CREATED_BY | VARCHAR(255) | X | '0' | The person/process that created the record. |
| UPDATED_BY | VARCHAR(255) | X | '0' | The person/process that last updated the record. |

2.2.51.7 List of keys of the table iam_user

| Code | Primary |
| --- | --- |
| PK_IAM_USER | X |

2.2.51.8 List of indexes of the table iam_user

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| USER_IDX | X | X |  | iam_user |
| USER__TENANT_IDX |  |  | X | iam_user |
| USER__ORIGIN_IDX |  |  | X | iam_user |
| USER_USERNAME_UNQ | X |  |  | iam_user |
| USER_ID_UNQ | X |  |  | iam_user |

2.2.52 Table iam_user_group

2.2.52.1 Card of table iam_user_group

| Code | IAM_USER_GROUP |
| --- | --- |
| Comment | Many-to-many association between users (iam_user table) and groups (iam_group table) |

2.2.52.2 Check constraint name of the table iam_user_group

CKT_IAM_USER_GROUP

2.2.52.3 List of outgoing references of the table iam_user_group

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_IAM_USERGROUP__GROUP | iam_group | fk_group_sid |
| FK_IAM_USERGROUP__USER | iam_user | fk_user_sid |
| FK_USER_GROUP__ROLE | role | fk_role_sid |

2.2.52.4 List of diagrams containing the table iam_user_group

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.52.5 List of columns of the table iam_user_group

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('iam_user_group_seq') | The surrogate key |
| FK_USER_SID | INT8 | X |  | Foreign key to the iam_user table |
| FK_GROUP_SID | INT8 | X |  | Foreign key to the iam_group table |
| FK_ROLE_SID | INT8 |  |  | Foreign key to role table |

2.2.52.6 List of keys of the table iam_user_group

| Code | Primary |
| --- | --- |
| USER_GROUP_PK | X |

2.2.52.7 List of indexes of the table iam_user_group

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| USER_GROUP_IDX | X | X |  | iam_user_group |
| USER_GROUP__GROUP_IDX |  |  | X | iam_user_group |
| USER_GROUP__USER_IDX |  |  | X | iam_user_group |
| USER_GROUP__ROLE_IDX |  |  | X | iam_user_group |

2.2.53 Table nie_event

2.2.53.1 Card of table nie_event

| Code | NIE_EVENT |
| --- | --- |
| Comment | Table that hold information about the NIE's events. |

2.2.53.2 Check constraint name of the table nie_event

CKT_NIE_EVENT

2.2.53.3 List of outgoing references of the table nie_event

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_NIE_EVENT__DOC_TYPE | document_type | fk_doc_type_sid |
| FK_NIE_EVENT__PROC_DEF_VERSION | process_def_version | fk_process_def_version_sid |

2.2.53.4 List of diagrams containing the table nie_event

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.53.5 List of columns of the table nie_event

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('nie_event_seq') | The surrogate key |
| FK_PROCESS_DEF_VERSION_SID | INT8 |  |  | Foreign key to the process def version table. |
| FK_DOC_TYPE_SID | INT8 |  |  | Foreign key to document_type_version table |
| EVENT_TYPE | VARCHAR(255) | X |  | The name of the subscription |
| STATUS | VARCHAR(20) | X | 'NEW' | The status of the nie event. Possible values: NEW, PROCESSING, RETRY, CANCELED; |
| RETRIES | INT4 | X | 0 | The nr of retries. |
| USER_ID | VARCHAR(255) |  |  | The id of the user. |
| PID | VARCHAR(255) |  |  | The process identification value. |
| PAYLOAD | TEXT | X |  | The payload of the nie event. |
| CREATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | Date & Time of Creation. |
| UPDATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | Date & time of last update. |
| NEXT_ATTEMPT_AT | TIMESTAMP WITH TIME ZONE |  |  | The next date when the event is schedulled. |
| HTTP_ERROR_CODE | INT4 |  |  | The http error code of the nie event that failed. |
| ERROR_MESSAGE | TEXT |  |  | The error message of the nie event that failed. |

2.2.53.6 List of keys of the table nie_event

| Code | Primary |
| --- | --- |
| NIE_EVENT_PK | X |

2.2.53.7 List of indexes of the table nie_event

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| NIE_EVENT_IDX | X | X |  | nie_event |
| NIE_EVENT__PROC_DEF_VERSION_IDX |  |  | X | nie_event |
| NIE_EVENT__DOC_TYPE_IDX |  |  | X | nie_event |
| NIE_EVENT__STATUS_IDX |  |  |  | nie_event |
| NIE_EVENT__STATUS_UPDATED_IDX |  |  |  | nie_event |
| NIE_EVENT__STATUS_NEXT_ATT_IDX |  |  |  | nie_event |
| NIE_EVENT__STATUS_PID_IDX |  |  |  | nie_event |

2.2.54 Table nie_listener

2.2.54.1 Card of table nie_listener

| Code | NIE_LISTENER |
| --- | --- |
| Comment | Table that holds NIE's listeners |

2.2.54.2 Check constraint name of the table nie_listener

CKT_NIE_LISTENER

2.2.54.3 List of outgoing references of the table nie_listener

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_LISTENER__SUBSCRIPTION | nie_subscription | fk_nie_subscription_sid |

2.2.54.4 List of diagrams containing the table nie_listener

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.54.5 List of columns of the table nie_listener

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('nie_listener_seq') | The surrogate key |
| FK_NIE_SUBSCRIPTION_SID | INT8 | X |  | Foreign key to the table nie_event_subscription |
| ID | VARCHAR(255) | X |  | The id of the nie listener |
| URL | VARCHAR(1024) | X |  | The listener |
| LABEL | VARCHAR(255) |  |  | The label of the listener |

2.2.54.6 List of keys of the table nie_listener

| Code | Primary |
| --- | --- |
| NIE_LISTENER_PK | X |

2.2.54.7 List of indexes of the table nie_listener

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| NIE_LISTENER_IDX | X | X |  | nie_listener |
| NIE_LISTENER_SUBSCRIPTION_IDX |  |  | X | nie_listener |

2.2.55 Table nie_subscriber

2.2.55.1 Card of table nie_subscriber

| Code | NIE_SUBSCRIBER |
| --- | --- |
| Comment | Table that holds NIE subscriber |

2.2.55.2 Check constraint name of the table nie_subscriber

CKT_NIE_SUBSCRIBER

2.2.55.3 List of outgoing references of the table nie_subscriber

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_SUBSCRBR__DOC_TYPE | document_type | fk_document_type_sid |
| FK_SUBSCRBR__PROCESS_DEF_VER | process_def_version | fk_process_def_version_sid |
| FK_SUBSCRIBER__SUBSCRIPTION | nie_subscription | fk_nie_subscription_sid |

2.2.55.4 List of diagrams containing the table nie_subscriber

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.55.5 List of columns of the table nie_subscriber

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('nie_subscriber_seq') | The surrogate key |
| FK_NIE_SUBSCRIPTION_SID | INT8 | X |  | Foreign key to the table nie_event_subscription |
| FK_PROCESS_DEF_VERSION_SID | INT8 |  |  | Foreign key to the process def version table. |
| FK_DOCUMENT_TYPE_SID | INT8 |  |  | Foreign key to the document type table. |
| ID | VARCHAR(255) | X |  | The id of NIE subscriber |

2.2.55.6 List of keys of the table nie_subscriber

| Code | Primary |
| --- | --- |
| NIE_SUBSCRIBER_PK | X |

2.2.55.7 List of indexes of the table nie_subscriber

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| NIE_SUBSCRIBER_IDX | X | X |  | nie_subscriber |
| SUBSCRIBER_SUBSCRIPTION_IDX |  |  | X | nie_subscriber |
| SUBSCRIBER_DOCUMENT_TYPE_UNQ | X |  |  | nie_subscriber |
| SUBSCRIBER_PROC_DEF_VERSION_UNQ | X |  |  | nie_subscriber |

2.2.56 Table nie_subscription

2.2.56.1 Card of table nie_subscription

| Code | NIE_SUBSCRIPTION |
| --- | --- |
| Comment | Table that hold information about the NIE's event subscription. |

2.2.56.2 Check constraint name of the table nie_subscription

CKT_NIE_SUBSCRIPTION

2.2.56.3 List of incoming references of the table nie_subscription

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| FK_LISTENER__SUBSCRIPTION | nie_listener | fk_nie_subscription_sid |
| FK_SUBSCRIBER__SUBSCRIPTION | nie_subscriber | fk_nie_subscription_sid |

2.2.56.4 List of diagrams containing the table nie_subscription

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.56.5 List of columns of the table nie_subscription

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('nie_subscription_seq') | The surrogate key |
| SUBSCRIPTION_NAME | VARCHAR(255) | X |  | The name of the subscription |
| ID | VARCHAR(255) | X |  | The old id |
| IS_CASE | BOOL |  |  | Flag that indicate if is a subscription of a cases or of a documents; when true is a cases and false is documents |

2.2.56.6 List of keys of the table nie_subscription

| Code | Primary |
| --- | --- |
| NIE_SUBSCRIPTION_PK | X |

2.2.56.7 List of indexes of the table nie_subscription

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| NIE_SUBSCRIPTION_IDX | X | X |  | nie_subscription |
| SUBSCRIPTION_NAME_UNQ | X |  |  | nie_subscription |

2.2.57 Table notification

2.2.57.1 Card of table notification

| Code | NOTIFICATION |
| --- | --- |
| Comment | The table that holds the notifications. |

2.2.57.2 Check constraint name of the table notification

CKT_NOTIFICATION

2.2.57.3 List of incoming references of the table notification

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| FK_ASSIGN_REQUEST__NOTIF | assignment_request | fk_notification_sid |
| FK_NOTIF_USER__NOTIF | notification_user | fk_notification_sid |

2.2.57.4 List of outgoing references of the table notification

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_NOTIF__DOC_TYPE | document_type | fk_document_type_sid |
| FK_NOTIF__IAM_USER | iam_user | fk_creator_sid |
| FK_NOTIFICATION__DOCUMENT | document | fk_document_sid |
| FK_NOTIFICATION__RINA_CASE | rina_case | fk_case_sid |
| FK_NOTIFICATION_REC__ORG | organisation | fk_receiver_org_sid |
| FK_NOTIFICATION_SDR__ORG | organisation | fk_sender_org_sid |

2.2.57.5 List of diagrams containing the table notification

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.57.6 List of columns of the table notification

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('notification_seq') | The surrogate key |
| ID | VARCHAR(255) | X |  | The id of the Notification |
| VERSION | INT4 | X | 1 | The system version. It is automatically increased by Hibernate each time the row is updated. |
| FK_CASE_SID | INT8 |  |  | Foreign key to rina_case table |
| FK_DOCUMENT_SID | INT8 |  |  | Foreign key to document table |
| FK_DOCUMENT_TYPE_SID | INT8 |  |  | Foreign key to document type table |
| FK_SENDER_ORG_SID | INT8 |  |  | The sender of the notification. |
| FK_RECEIVER_ORG_SID | INT8 |  |  | The receiver of the notification. |
| FK_CREATOR_SID | INT8 | X | 0 | The creator of the notification. |
| CATEGORY | VARCHAR(255) |  |  | The category of the notification |
| SEVERITY | VARCHAR(255) |  |  | The type of severity (e.g. warning, error, information) |
| TYPE | VARCHAR(255) |  |  | The type of the notification (e.g. new message arrived) |
| STATUS | VARCHAR(255) |  |  | The status of the notification |
| SOURCE_TYPE | VARCHAR(255) |  |  | The source of the notification (messaging, business, other) |
| IS_READ | BOOL |  |  | Is the notification read? |
| REASON | TEXT |  |  | The reason of the Notification |
| FAILURE_CODE | VARCHAR(255) |  |  | The code of the error in case of failure |
| FAILURE_DESCRIPTION | TEXT |  |  | The description of the error in case of failure |
| DUE_DATE | TIMESTAMP WITH TIME ZONE |  |  | The due date of the notification |
| CREATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | The time that the notification was first inserted into the DB |
| UPDATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | The last time that the notification was updated |

2.2.57.7 List of keys of the table notification

| Code | Primary |
| --- | --- |
| NOTIFICATION_PK | X |

2.2.57.8 List of indexes of the table notification

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| NOTIFATION_IDX | X | X |  | notification |
| NOTIFICATION__DOCUMENT_IDX |  |  | X | notification |
| NOTIFICATION__CREATOR_IDX |  |  | X | notification |
| NOTIFICATION__RINA_CASE_IDX |  |  | X | notification |
| NOTIFICATION__DOC_TYPE_IDX |  |  | X | notification |
| NOTIFICATION__CREATED_AT_IDX |  |  |  | notification |

2.2.58 Table notification_alarm

2.2.58.1 Card of table notification_alarm

| Code | NOTIFICATION_ALARM |
| --- | --- |
| Comment | The table that holds the notification alarms. |

2.2.58.2 Check constraint name of the table notification_alarm

CKT_NOTIFICATION_ALARM

2.2.58.3 List of outgoing references of the table notification_alarm

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_NOTIF_ALARM__CASE | rina_case | fk_case_sid |

2.2.58.4 List of diagrams containing the table notification_alarm

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.58.5 List of columns of the table notification_alarm

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('notification_alarm_seq') | The surrogate key |
| ID | VARCHAR(255) | X |  | The id of the Signature |
| FK_CASE_SID | INT8 | X |  | Foreign key that links the Notification alarm to the rina_case table |
| DATE | TIMESTAMP WITH TIME ZONE |  | now() | The date of the alarm. |
| DESCRIPTION | VARCHAR(255) |  |  | The description of the notification alarm. |
| CREATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | Date & Time of Creation. |
| UPDATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | Date & time of last update. |
| CREATED_BY | VARCHAR(255) | X | '0' | The person/process that created the record. |
| UPDATED_BY | VARCHAR(255) | X | '0' | The person/process that last updated the record. |

2.2.58.6 List of keys of the table notification_alarm

| Code | Primary |
| --- | --- |
| NOTIFICATION_ALARM_PK | X |

2.2.58.7 List of indexes of the table notification_alarm

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| NOTIFICATION_ALARM_IDX | X | X |  | notification_alarm |
| NOTIF_ALARM_CASE_SID_IDX |  |  | X | notification_alarm |
| NOTIF_ALARM__ID_UNQ | X |  |  | notification_alarm |

2.2.59 Table notification_user

2.2.59.1 Card of table notification_user

| Code | NOTIFICATION_USER |
| --- | --- |
| Comment | Many-to-many association between notifications and users (iam_user table). It defines the user responsible parties. |

2.2.59.2 Check constraint name of the table notification_user

CKT_NOTIFICATION_USER

2.2.59.3 List of outgoing references of the table notification_user

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_NOTIF_USER__NOTIF | notification | fk_notification_sid |
| FK_NOTIF_USER__USER | iam_user | fk_user_sid |

2.2.59.4 List of diagrams containing the table notification_user

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.59.5 List of columns of the table notification_user

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| FK_NOTIFICATION_SID | INT8 | X |  | Foreign key to notification table |
| FK_USER_SID | INT8 | X |  | Foreign key to iam_user table |

2.2.59.6 List of indexes of the table notification_user

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| NOTIF_USER__NOTIF_IDX |  |  | X | notification_user |
| NOTIF_USER__USER_IDX |  |  | X | notification_user |

2.2.60 Table org_contact_method

2.2.60.1 Card of table org_contact_method

| Code | ORG_CONTACT_METHOD |
| --- | --- |
| Comment | Tables that holds information on the organisations'contact methods |

2.2.60.2 Check constraint name of the table org_contact_method

CKT_ORG_CONTACT_METHOD

2.2.60.3 List of outgoing references of the table org_contact_method

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_ORG_CONTACT_METHOD__ORG | organisation | fk_org_sid |

2.2.60.4 List of diagrams containing the table org_contact_method

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.60.5 List of columns of the table org_contact_method

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('org_contact_method_seq') | The surrogate key. |
| FK_ORG_SID | INT8 | X |  | Foreign key to the organisation table. |
| TYPE | VARCHAR(255) | X |  | The type of the org contact method. |
| VALUE | VARCHAR(255) | X |  | The value of the org contact method. |

2.2.60.6 List of keys of the table org_contact_method

| Code | Primary |
| --- | --- |
| ORG_CONTACT_METHOD_PK | X |

2.2.60.7 List of indexes of the table org_contact_method

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| ORG_CONTACT_METHODS_IDX | X | X |  | org_contact_method |
| ORG_CONTACT_METHOD__ORG_IDX |  |  | X | org_contact_method |
| ORG_CONTACT_METHOD_TYPE_UNQ | X |  |  | org_contact_method |

2.2.61 Table organisation

2.2.61.1 Card of table organisation

| Code | ORGANISATION |
| --- | --- |
| Comment | Table that holds infomation about the Organisation |

2.2.61.2 Check constraint name of the table organisation

CKT_ORGANISATION

2.2.61.3 List of incoming references of the table organisation

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| FK_ASSIGNED_BUC__ORG | assigned_buc | fk_org_sid |
| FK_CASE_PARTICIPANT__ORG | case_participant | fk_org_sid |
| FK_CASE_SUBJECT_ORG__ORG | case_subject_org | fk_org_sid |
| FK_CONV_PARTICIPANT__ORG | conv_participant | fk_org_sid |
| FK_NOTIFICATION_REC__ORG | notification | fk_receiver_org_sid |
| FK_NOTIFICATION_SDR__ORG | notification | fk_sender_org_sid |
| FK_ORG_CONTACT_METHOD__ORG | org_contact_method | fk_org_sid |
| FK_PEND_MSG_REC__ORGANISATION | pending_message | fk_receiver_org_sid |
| FK_PEND_MSG_SDR__ORGANISATION | pending_message | fk_sender_org_sid |
| FK_RULE_ORG__ORG | rule_organisation | fk_org_sid |
| FK_SEARCH_DEF_ORG__ORG | search_def_org | fk_organisation_sid |
| FK_TENANT__ORGANISATION | tenant | fk_org_sid |
| FK_USER_MSG__RECEIVER | user_message | fk_receiver_sid |
| FK_USER_MSG__SENDER | user_message | fk_sender_sid |

2.2.61.4 List of diagrams containing the table organisation

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.61.5 List of columns of the table organisation

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('organisation_seq') | The surrogate key |
| VERSION | INT4 | X | 1 | The system version. It is automatically increased by Hibernate each time the row is updated. |
| ID | VARCHAR(50) | X |  | The id of the Entity |
| COUNTRY_CODE | VARCHAR(2) | X |  | The country code of the country that the Organisation/Institution belongs to". Possible values: AT, BE, BG, CH, CY, CZ, DE, DK, EE, EL, ES, FI, FR, HR, HU, IS, IE, IT, LV, LI, LT, LU, MT, NL, NO, PL, PT, RO, SE, SI, SK, UK; |
| NAME | VARCHAR(255) |  |  | The name of the organisation. |
| ACRONYM | VARCHAR(255) |  |  | The organisation acronim. |
| LOCATION | VARCHAR(255) |  |  | The geographical location of the Organisation/Institution |
| REGISTRY_NUMBER | VARCHAR(255) |  |  | The registry number of the Organisation/Institution |
| ACTIVE_SINCE | TIMESTAMP WITH TIME ZONE |  |  | The date that the Organisation/Institution is active since |
| ACTIVE_UNTIL | TIMESTAMP WITH TIME ZONE |  |  | The date that the Organisation/Institution is active until |
| IS_ENABLED | BOOL | X | true | The is enabled flag. |
| AP_ID | VARCHAR(255) |  |  | The Id of the Access Point |
| AP_NAME | VARCHAR(255) |  |  | The name of the Access Point |
| AP_COUNTRY_CODE | VARCHAR(255) |  |  | The country code of the Access Point |
| AP_PROTOCOL | VARCHAR(255) |  |  | The protocol of the Access Point |
| AP_TECHNICAL_PROTOCOL | VARCHAR(255) |  |  | The technical protocol of the Access Point |
| AP_IP | VARCHAR(255) |  |  | The IP of the Access Point |
| AP_PORT | INT4 |  |  | The port of the Access Point |
| AP_OUTBOX_SERVICE | VARCHAR(255) |  |  | The outbox Service URL of the Access Point |
| AP_TECHNICAL_OUTBOX_SERVICE | VARCHAR(255) |  |  | The technical outbox Service URL of the Access Point |
| AP_INBOX_SERVICE | VARCHAR(255) |  |  | The inbox Service URL of the Access Point |
| AP_TECHNICAL_INBOX_SERVICE | VARCHAR(255) |  |  | The technical inbox Service URL of the Access Point |
| AP_TECHNICAL_CHANNEL | VARCHAR(255) |  |  | The system channel used for pulling, this is the last part of the system MPC |
| AP_CHANNEL | VARCHAR(255) |  |  | The business channel used for pulling, this is the last part of the business MPC |
| ADDRESS_STREET | VARCHAR(255) |  |  | The street of the Address details |
| ADDRESS_TOWN | VARCHAR(255) |  |  | The town of the Address details |
| ADDRESS_POSTAL_CODE | VARCHAR(255) |  |  | The postal code of the Address details |
| ADDRESS_REGION | VARCHAR(255) |  |  | The region of the Address details |
| ADDRESS_COUNTRY | VARCHAR(255) |  |  | The country of the Address details |
| CREATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | Date & Time of creation |
| UPDATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | Date & Time of the last update |

2.2.61.6 List of keys of the table organisation

| Code | Primary |
| --- | --- |
| ORGANISATION_PK | X |

2.2.61.7 List of indexes of the table organisation

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| ORGANISATION_IDX | X | X |  | organisation |
| ORGANISATION_ID_UNQ | X |  |  | organisation |

2.2.62 Table pending_attachment

2.2.62.1 Card of table pending_attachment

| Code | PENDING_ATTACHMENT |
| --- | --- |
| Comment | Table that holds information about the attachment of the pending_messages |

2.2.62.2 Check constraint name of the table pending_attachment

CKT_PENDING_ATTACHMENT

2.2.62.3 List of outgoing references of the table pending_attachment

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_PEND_ATTACH__PEND_MSG | pending_message | fk_pend_msg_sid |

2.2.62.4 List of diagrams containing the table pending_attachment

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.62.5 List of columns of the table pending_attachment

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('pending_message_seq') | The surrogate key |
| FK_PEND_MSG_SID | INT8 | X |  | Foreign key that points to the subdocument table |
| MIME_TYPE | VARCHAR(50) | X |  | The mime type of the pending attachment. Possible values: APP_PDF APP_MSWORD APP_MSEXCEL APP_MSPOWERPOINT APP_OPENXML_DOC APP_OPENXML_SPREADSHEET APP_OPENXML_PRESENTATION APP_XML APP_ZIP APP_GZIP IMG_JPEG IMG_PNG IMG_TIFF TXT_RTF TXT_XML // Mimetypes NOT included in the SBDH XSD definition APP_X_ZIP APP_OCTET_STREAM APP_X_ZIP_COMPRESSED |
| ID | VARCHAR(255) | X |  | The id of the pending attachment. |
| FILENAME | VARCHAR(1024) |  |  | The directory path where the assignment is stored |
| IS_MEDICAL | BOOL | X | false | The is medical flag. |
| SECTION_REFERENCE | VARCHAR(1024) |  |  | Section refference value. |
| PATHNAME | VARCHAR(1024) | X |  | The complete pathname from where to retrieve the pending attachment. |

2.2.62.6 List of keys of the table pending_attachment

| Code | Primary |
| --- | --- |
| KEY_1 | X |

2.2.62.7 List of indexes of the table pending_attachment

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| PEND_ATTACHMENT_IDX | X | X |  | pending_attachment |

2.2.63 Table pending_message

2.2.63.1 Card of table pending_message

| Code | PENDING_MESSAGE |
| --- | --- |
| Comment | Table that holds information about the Pending Message |

2.2.63.2 Check constraint name of the table pending_message

CKT_PENDING_MESSAGE

2.2.63.3 List of incoming references of the table pending_message

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| FK_BUSINESS_EXC__PEND_MSG | business_exception | fk_pend_msg_sid |
| FK_PEND_ATTACH__PEND_MSG | pending_attachment | fk_pend_msg_sid |

2.2.63.4 List of outgoing references of the table pending_message

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_PEND_MSG__CASE | rina_case | fk_case_sid |
| FK_PEND_MSG__PROC_DEF_VER | process_def_version | fk_proc_def_version_sid |
| FK_PEND_MSG_REC__ORGANISATION | organisation | fk_receiver_org_sid |
| FK_PEND_MSG_SDR__ORGANISATION | organisation | fk_sender_org_sid |

2.2.63.5 List of diagrams containing the table pending_message

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.63.6 List of columns of the table pending_message

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('pending_message_seq') | The surrogate key |
| ID | VARCHAR(255) | X |  | The id of the Pending Message |
| FK_RECEIVER_ORG_SID | INT8 |  |  | Foreign key that links the Pending Message to the receiver's organisation table |
| FK_SENDER_ORG_SID | INT8 |  |  | Foreign key that links the Pending Message to the sender's organisation table |
| FK_CASE_SID | INT8 |  |  | Foreign key that links the Pending Message to the process definition's version table |
| FK_PROC_DEF_VERSION_SID | INT8 |  |  | Foreign key that links the Pending Message to the process definition's version table |
| SBDH | TEXT | X |  | The SDBH value. |
| CONTENT_LOCATION | VARCHAR(255) |  |  | The location of the content for the pending message. |
| ACTION_TYPE | VARCHAR(255) |  |  | Action type of the Pending Message |
| INTERNATIONAL_CASE_ID | VARCHAR(255) |  |  | International case ID |
| IS_PROTECTED_PERSON | BOOL | X | false | The is protected person flag. |
| SHOULD_NOTIFY | BOOL | X | false | The should notify flag. |
| IS_PROCESSED | BOOL | X | false | The is protected flag. |
| IS_SELECTED | BOOL |  |  | The is selected flag. |
| IS_FILTERED_OUT | BOOL |  |  | The is filtered out flag. |
| IS_EXPANDED | BOOL |  |  | The is processed flag. |
| PROBLEM | VARCHAR(255) |  |  | The problem of the peding message. |
| CAUSE | VARCHAR(255) |  |  | The cause that triggered the creation of the pending message. |
| DATE | TIMESTAMP WITH TIME ZONE | X | now() | The date the peding message happend/was created, |

2.2.63.7 List of keys of the table pending_message

| Code | Primary |
| --- | --- |
| PENDING_MESSAGE_PK | X |

2.2.63.8 List of indexes of the table pending_message

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| PEND_MSG_IDX | X | X |  | pending_message |
| PEND_MSG__CASE_IDX |  |  | X | pending_message |
| PEND_MSG__RECEIVER_IDX |  |  | X | pending_message |
| PEND_MSG__SENDER_IDX |  |  | X | pending_message |
| PEND_MSG__PROC_DEF_VER_IDX |  |  | X | pending_message |
| PEND_MSG__ID_UNQ | X |  |  | pending_message |
| PEND_MSG__PROCESSED_IDX |  |  |  | pending_message |

2.2.64 Table pending_signature

2.2.64.1 Card of table pending_signature

| Code | PENDING_SIGNATURE |
| --- | --- |
| Comment | Table that holds information about the Pending Signature |

2.2.64.2 Check constraint name of the table pending_signature

CKT_PENDING_SIGNATURE

2.2.64.3 List of diagrams containing the table pending_signature

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.64.4 List of columns of the table pending_signature

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('pending_signature_seq') | The surrogate key |
| ID | VARCHAR(255) | X |  | Id of pending message |
| DIRECTION | VARCHAR(11) | X |  | Direction of pending message |
| SED_SIGNATURE | TEXT | X |  | Pending Signature of SED |
| TARGET_SED_ID | VARCHAR(255) | X |  | Id of target SED |
| LAST_UPDATE | TIMESTAMP WITH TIME ZONE |  |  | Date & time of last update. |

2.2.64.5 List of keys of the table pending_signature

| Code | Primary |
| --- | --- |
| PENDING_RECEIPT_PK | X |

2.2.64.6 List of indexes of the table pending_signature

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| PEND_SIGN_IDX | X | X |  | pending_signature |
| PEND_SIGN_UNQ_IDX | X |  |  | pending_signature |

2.2.65 Table pending_status

2.2.65.1 Card of table pending_status

| Code | PENDING_STATUS |
| --- | --- |
| Comment | Table that holds information about the Pending Status |

2.2.65.2 Check constraint name of the table pending_status

CKT_PENDING_STATUS

2.2.65.3 List of diagrams containing the table pending_status

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.65.4 List of columns of the table pending_status

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('pending_status_seq') | The surrogate key |
| ID | VARCHAR(255) | X |  | The id of the pending status. |
| DIRECTION | VARCHAR(11) | X |  | Direction of the Pending Status. Possible values: IN("IN"), OUT("OUT"); |
| STATUS | VARCHAR(255) | X |  | Status of the Pending Status. Possible values: SENT("sent"), DELIVERED("delivered"), ERROR("error"), RESENT("resent"); |
| TARGET_MESSAGE_ID | VARCHAR(255) | X |  | The target message id of the pending status. |
| LAST_UPDATE | TIMESTAMP WITH TIME ZONE |  |  | Date & time of last update. |
| ERROR_DESCRIPTION | TEXT |  |  | The description of the error of the pending message. |

2.2.65.5 List of keys of the table pending_status

| Code | Primary |
| --- | --- |
| PENDING_STATUS_PK | X |

2.2.65.6 List of indexes of the table pending_status

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| PEND_STATUS_IDX | X | X |  | pending_status |
| PEND_STATUS_UNQ_IDX | X |  |  | pending_status |

2.2.66 Table policy

2.2.66.1 Card of table policy

| Code | POLICY |
| --- | --- |
| Comment | Archiving policy details |

2.2.66.2 Check constraint name of the table policy

CKT_POLICY

2.2.66.3 List of outgoing references of the table policy

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_POLICY__PROCESS_DEF | process_def | fk_process_def_sid |
| FK_POLICY__SECTOR | sector | fk_sector_sid |
| FK_POLICY__TENANT | tenant | fk_tenant_sid |

2.2.66.4 List of diagrams containing the table policy

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.66.5 List of columns of the table policy

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('policy_seq') | The surrogate key |
| FK_TENANT_SID | INT8 |  |  | Foreign key to the Tenant table |
| FK_SECTOR_SID | INT8 |  |  | Foreign key to the Sector table |
| FK_PROCESS_DEF_SID | INT8 |  |  | Foreign key to the process def table. |
| ID | VARCHAR(255) |  |  | The id of the policy. |
| APPLICATION_ROLE | VARCHAR(2) |  |  | The Application Role. Possible values: PO("CaseOwner"), CP("CounterParty"); |
| POLICY_TYPE | VARCHAR(50) | X |  | The policy type. |
| POLICY | INT4 | X |  | The archiving timer used by archiving process. Closed or forwarded cases will be archived after the specified timer (number of days – e.g.7 days a week, 365 days a year, etc. ) |

2.2.66.6 List of keys of the table policy

| Code | Primary |
| --- | --- |
| POLICY_PK | X |

2.2.66.7 List of indexes of the table policy

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| POLICY_IDX | X | X |  | policy |
| POLICY__BUC_IDX |  |  | X | policy |
| POLICY__TENANT_IDX |  |  | X | policy |
| POLICY__SECTOR_IDX |  |  | X | policy |
| POLICY_ID_UNQ | X |  |  | policy |

2.2.67 Table process_def

2.2.67.1 Card of table process_def

| Code | PROCESS_DEF |
| --- | --- |
| Comment | Table that holds information about the process definiyion. |

2.2.67.2 Check constraint name of the table process_def

CKT_PROCESS_DEF

2.2.67.3 List of incoming references of the table process_def

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| FK_ASSIGNED_BUC__PROCESS_DEF | assigned_buc | fk_process_def_sid |
| FK_FIELD_CHOOSER__PROCESS_DEF | field_chooser | FK_PROCESS_DEF_SID |
| FK_POLICY__PROCESS_DEF | policy | fk_process_def_sid |
| FK_PROC_DEF__PROC_DEF_VERSION | process_def_version | fk_proc_def_sid |
| FK_RULE_PROCESS__PROCESS | rule_process | fk_process_sid |
| FK_SRCH_DEF_PROC_DEF__PROC_DEF | search_def_proc_def | fk_process_definition_sid |
| FK_USER_PROFILE__PROCESS_DEF | user_profile | fk_proc_def_sid |

2.2.67.4 List of outgoing references of the table process_def

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_PROCESS_DEF__SECTOR | sector | fk_sector_sid |

2.2.67.5 List of views of the table process_def

| Code |
| --- |
| V_CASE_SEARCH |

2.2.67.6 List of diagrams containing the table process_def

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.67.7 List of columns of the table process_def

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('process_def_seq') | The surrogate key. |
| FK_SECTOR_SID | INT8 | X |  | Foreign key to the Sector table. |
| ID | VARCHAR(255) | X |  | The id of the process def. |
| NAME | VARCHAR(255) | X |  | The name of the process definition. |

2.2.67.8 List of keys of the table process_def

| Code | Primary |
| --- | --- |
| PROCESS_DEF_PK | X |

2.2.67.9 List of indexes of the table process_def

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| PROCESS_DEF_IDX | X | X |  | process_def |
| PROCESS_DEF_NAME_UNQ | X |  |  | process_def |
| PROCESS_DEF__ID_UNQ | X |  |  | process_def |

2.2.68 Table process_def_version

2.2.68.1 Card of table process_def_version

| Code | PROCESS_DEF_VERSION |
| --- | --- |
| Comment | Table that holds information about the business version of the process definition |

2.2.68.2 Check constraint name of the table process_def_version

CKT_PROCESS_DEF_VERSION

2.2.68.3 List of incoming references of the table process_def_version

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| FK_CASE__PROC_DEF_VERSION | rina_case | fk_proc_def_version_sid |
| FK_DOC_TYPE__PROC_DEF_VERSION | document_type | fk_proc_def_version_sid |
| FK_NIE_EVENT__PROC_DEF_VERSION | nie_event | fk_process_def_version_sid |
| FK_PEND_MSG__PROC_DEF_VER | pending_message | fk_proc_def_version_sid |
| FK_SUBSCRBR__PROCESS_DEF_VER | nie_subscriber | fk_process_def_version_sid |
| FK_TRANSPOS__PROC_DEF_VERSION | transposition | fk_proc_def_version_sid |

2.2.68.4 List of outgoing references of the table process_def_version

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_PROC_DEF__PROC_DEF_VERSION | process_def | fk_proc_def_sid |

2.2.68.5 List of views of the table process_def_version

| Code |
| --- |
| V_CASE_SEARCH |

2.2.68.6 List of diagrams containing the table process_def_version

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.68.7 List of columns of the table process_def_version

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('process_def_version_seq') | The surrogate key |
| FK_PROC_DEF_SID | INT8 | X |  | Foreign key to the process_def table |
| BVERSION | VARCHAR(10) | X |  | The version of the ProcessDefinition. |
| ACTIVE_FROM | TIMESTAMP WITH TIME ZONE |  |  | Timestamp since the process definition version should be active from |
| ACTIVE_TO | TIMESTAMP WITH TIME ZONE |  |  | The date and time untill the process definition is active. |

2.2.68.8 List of keys of the table process_def_version

| Code | Primary |
| --- | --- |
| PROCESS_DEF_VERSION_PK | X |

2.2.68.9 List of indexes of the table process_def_version

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| PROCESS_DEF_VERSION_IDX | X | X |  | process_def_version |
| PROC_DEF__PROC_DEF_VERSION_IDX |  |  | X | process_def_version |
| PROCESS_DEF_VERSION_VERSION_UNQ | X |  |  | process_def_version |

2.2.69 Table resource

2.2.69.1 Card of table resource

| Code | RESOURCE |
| --- | --- |
| Comment | Resource inventory |

2.2.69.2 Check constraint name of the table resource

CKT_RESOURCE

2.2.69.3 List of diagrams containing the table resource

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.69.4 List of columns of the table resource

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('resource_seq') | The surrogate key |
| ID | VARCHAR(255) | X |  | The id of the resource. |
| VERSION | INT4 | X | 1 | The system version. It is automatically increased by Hibernate each time the row is updated. |
| STORAGE_ID | VARCHAR(255) | X |  | Storage id |
| TYPE | VARCHAR(20) | X |  | The type of this resource. Possible values: organisation, vocabulary, initialdoc, process, sbdh, sed, transaction, form, report, APPLICATION, letterTemplate, localization |
| BVERSION | VARCHAR(35) | X |  | Business version |
| DATE | TIMESTAMP WITH TIME ZONE |  |  | The computed date of the resource |
| TAG | VARCHAR(255) | X |  | The tag of the resource |
| CREATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | The time that the resource was first inserted into the DB |
| UPDATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | The last time that the resource was updated |
| CREATED_BY | VARCHAR(255) | X | '0' | The person/process that created the record. |
| UPDATED_BY | VARCHAR(255) | X | '0' | The person/process that last updated the record. |

2.2.69.5 List of keys of the table resource

| Code | Primary |
| --- | --- |
| PK_RESOURCE | X |

2.2.69.6 List of indexes of the table resource

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| RESOURCE_STORAGE_ID_IDX | X |  |  | resource |
| RESOURCE_TYPE_IDX |  |  |  | resource |
| RESOURCE_IDX | X | X |  | resource |

2.2.70 Table rina_case

2.2.70.1 Card of table rina_case

| Code | RINA_CASE |
| --- | --- |
| Comment | Table that holds information about the Case |

2.2.70.2 Check constraint name of the table rina_case

CKT_RINA_CASE

2.2.70.3 List of incoming references of the table rina_case

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| FK_ACTION__CASE | action | fk_case_sid |
| FK_ACTIVITY__CASE | activity | fk_case_sid |
| FK_ASSIGN__CASE | assignment | fk_case_sid |
| FK_ASSIGN_REQUEST__CASE | assignment_request | fk_case_sid |
| FK_CASE_ATTACH__CASE | case_attachment | fk_case_sid |
| FK_CASE_PARTICIPANT__CASE | case_participant | fk_case_sid |
| FK_CASE_PREFILL__RINA_CASE | case_prefill | fk_case_sid |
| FK_CASE_PROPERTY__CASE | case_property | fk_case_sid |
| FK_CASE_SUBJECT_ORG__CASE | case_subject_org | fk_case_sid |
| FK_COMMENT__CASE | case_comment | fk_case_sid |
| FK_DOC_HIS__CASE | document_history | fk_case_sid |
| FK_DOCUMENT__CASE | document | fk_case_sid |
| FK_NOTIF_ALARM__CASE | notification_alarm | fk_case_sid |
| FK_NOTIFICATION__RINA_CASE | notification | fk_case_sid |
| FK_PEND_MSG__CASE | pending_message | fk_case_sid |
| FK_SUBDOC__RINA_CASE | subdocument | fk_case_sid |

2.2.70.4 List of outgoing references of the table rina_case

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_CASE__PROC_DEF_VERSION | process_def_version | fk_proc_def_version_sid |
| FK_CASE__TENANT | tenant | fk_tenant_sid |

2.2.70.5 List of views of the table rina_case

| Code |
| --- |
| V_CASE_SEARCH |
| V_SUBDOCUMENTS_SEARCH |

2.2.70.6 List of diagrams containing the table rina_case

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.70.7 List of columns of the table rina_case

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('case_seq') | The surrogate key |
| VERSION | INT4 | X | 1 | The system version. It is automatically increased by Hibernate each time the row is updated. |
| FK_TENANT_SID | INT8 | X |  | Foreign key that links the Case to the Tenant table |
| FK_PROC_DEF_VERSION_SID | INT8 | X |  | Foreign key that links the Case to the process definition's version table |
| FK_STARTER_DOC_TYPE_SID | INT8 |  |  | This is the foreign key to the document type for the stater document. |
| ID | VARCHAR(255) | X |  | The id of the Case |
| APPLICATION_ROLE | VARCHAR(2) | X |  | The Application Role. Possible values: PO("CaseOwner"), CP("CounterParty"); |
| INTERNATIONAL_ID | VARCHAR(255) |  |  | International correlation Id of the Case |
| BUSINESS_ID | TEXT |  |  | Business Id of the Case |
| STATUS | VARCHAR(10) | X | 'open' | The current status of the Case. Possible values: OPEN("open"), CLOSED("closed"), ACTIVE("active"), REMOVED("removed"), ARCHIVED("archived"), FORWARD("forward") |
| COUNTER | INT4 | X | 0 | The counter. |
| IS_SENSITIVE | BOOL | X | false | The sensitivity status of the Case |
| IS_SENSITIVE_COMMITED | BOOL | X | false | The is sensitive commited flag. |
| IS_MLC | BOOL |  |  | The is MLC flag. |
| HAS_VALID_STARTER | BOOL |  |  | The has valid starter flag. |
| REMOVE_ME_ONLY | BOOL |  |  | The remove me only flag. |
| IS_STARTER_SENT | BOOL |  |  | The is starter sent flag. |
| IMPORTANCE | INT4 | X | 0 | The importance of the case. |
| CRITICALITY | INT4 | X | 0 | The criticality of the case. |
| STORE_LOCATION_OF_ARCHIVE | VARCHAR(1024) |  |  | The location of the stored archive. |
| CREATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | Date & Time of Creation |
| UPDATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | Date & time of last update |
| CREATED_BY | VARCHAR(255) | X | '0' | The person/process that created the record. |
| UPDATED_BY | VARCHAR(255) | X | '0' | The person/process that last updated the record. |
| RANDOM_STRING | VARCHAR(255) | X | 'A1' | Random string for the case. |

2.2.70.8 List of keys of the table rina_case

| Code | Primary |
| --- | --- |
| CASE_PK | X |

2.2.70.9 List of indexes of the table rina_case

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| CASE_IDX | X | X |  | rina_case |
| CASE__TENANT_IDX |  |  | X | rina_case |
| CASE__PROC_DEF_VERSION_IDX |  |  | X | rina_case |
| CASE_ID_UNQ | X |  |  | rina_case |
| CASE__STATUS_IDX |  |  |  | rina_case |
| CASE__CREATED_AT_IDX |  |  |  | rina_case |

2.2.71 Table role

2.2.71.1 Card of table role

| Code | ROLE |
| --- | --- |
| Comment | The roles (Supervisor, Authorised, NonAuthorised, Auditor, Viewer, Medical, VIP) |

2.2.71.2 Check constraint name of the table role

CKT_ROLE

2.2.71.3 List of incoming references of the table role

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| FK_ASSIGN__ROLE | assignment | fk_role_sid |
| FK_ASSIGN_REQUEST__ROLE | assignment_request | fk_role_sid |
| FK_RULE_ROLE__ROLE | rule_role | fk_role_sid |
| FK_USER_GROUP__ROLE | iam_user_group | fk_role_sid |

2.2.71.4 List of diagrams containing the table role

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.71.5 List of columns of the table role

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('role_seq') | the surrogate key |
| NAME | VARCHAR(20) | X |  | The role name |

2.2.71.6 List of keys of the table role

| Code | Primary |
| --- | --- |
| ROLE_PK | X |

2.2.71.7 List of indexes of the table role

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| ROLE_IDX | X | X |  | role |
| ROLE_NAME_UNQ | X |  |  | role |

2.2.72 Table rule_country

2.2.72.1 Card of table rule_country

| Code | RULE_COUNTRY |
| --- | --- |
| Comment | Table that holds information about the Country associated with an assignment\_ policy_rule's po |

2.2.72.2 Check constraint name of the table rule_country

CKT_RULE_COUNTRY

2.2.72.3 List of outgoing references of the table rule_country

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_RULE_COUN__ASSIGN_POL_RULE | assignment_policy_rule | fk_rule_sid |

2.2.72.4 List of diagrams containing the table rule_country

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.72.5 List of columns of the table rule_country

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('rule_country_seq') | The surrogate key |
| FK_RULE_SID | INT8 | X |  | Foreign key to assignment_policy_rule table |
| COUNTRY_CODE | VARCHAR(2) | X |  | The country code. Possible values: AT, BE, BG, CH, CY, CZ, DE, DK, EE, EL, ES, FI, FR, HR, HU, IS, IE, IT, LV, LI, LT, LU, MT, NL, NO, PL, PT, RO, SE, SI, SK, UK; |

2.2.72.6 List of keys of the table rule_country

| Code | Primary |
| --- | --- |
| RULE_COUNTRY_PK | X |

2.2.72.7 List of indexes of the table rule_country

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| RULE_COUNTRY_IDX | X | X |  | rule_country |
| RULE_COUN__ASSIGN_POL_RULE_IDX |  |  | X | rule_country |
| RULE_COUNTRY_UNQ | X |  |  | rule_country |

2.2.73 Table rule_creator_group

2.2.73.1 Card of table rule_creator_group

| Code | RULE_CREATOR_GROUP |
| --- | --- |
| Comment | Many to many table that links Rules and their coresponding groups for creator |

2.2.73.2 Check constraint name of the table rule_creator_group

CKT_RULE_CREATOR_GROUP

2.2.73.3 List of outgoing references of the table rule_creator_group

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_RULE_CREATOR_GROUP__GROUP | iam_group | fk_group_sid |
| FK_RULE_CREATOR_GROUP__RULE | assignment_policy_rule | fk_rule_sid |

2.2.73.4 List of diagrams containing the table rule_creator_group

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.73.5 List of columns of the table rule_creator_group

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| FK_RULE_SID | INT8 | X |  | Linked record field that mapped to the Rule table |
| FK_GROUP_SID | INT8 | X |  | Linked record field that mapped to the Group table |

2.2.73.6 List of indexes of the table rule_creator_group

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| RULE_CREATOR_GROUP__RULE_IDX |  |  | X | rule_creator_group |
| RULE_CREATOR_GROUP__GROUP_IDX |  |  | X | rule_creator_group |
| RULE_CREATOR_GROUP__UNQ | X |  |  | rule_creator_group |

2.2.74 Table rule_creator_user

2.2.74.1 Card of table rule_creator_user

| Code | RULE_CREATOR_USER |
| --- | --- |
| Comment | Many to many table that links Rules and their coresponding users for creator |

2.2.74.2 Check constraint name of the table rule_creator_user

CKT_RULE_CREATOR_USER

2.2.74.3 List of outgoing references of the table rule_creator_user

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_RULE_CREATOR_USER__RULE | assignment_policy_rule | fk_rule_sid |
| FK_RULE_CREATOR_USER__USER | iam_user | fk_user_sid |

2.2.74.4 List of diagrams containing the table rule_creator_user

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.74.5 List of columns of the table rule_creator_user

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| FK_RULE_SID | INT8 | X |  | Linked record field that mapped to the Rule table |
| FK_USER_SID | INT8 | X |  | Linked record field that mapped to the Group table |

2.2.74.6 List of indexes of the table rule_creator_user

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| RULE_CREATOR_USER__RULE_IDX |  |  | X | rule_creator_user |
| RULE_CREATOR_USER__USER_IDX |  |  | X | rule_creator_user |
| RULE_CREATOR_USER_UNQ | X |  |  | rule_creator_user |

2.2.75 Table rule_group

2.2.75.1 Card of table rule_group

| Code | RULE_GROUP |
| --- | --- |
| Comment | Many to many table that links Rules and their coresponding groups |

2.2.75.2 Check constraint name of the table rule_group

CKT_RULE_GROUP

2.2.75.3 List of outgoing references of the table rule_group

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_RULE_GROUP__GROUP | iam_group | fk_group_sid |
| FK_RULE_GROUP__RULE | assignment_policy_rule | fk_rule_sid |

2.2.75.4 List of diagrams containing the table rule_group

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.75.5 List of columns of the table rule_group

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| FK_RULE_SID | INT8 | X |  | Linked record field that mapped to the Rule table |
| FK_GROUP_SID | INT8 | X |  | Linked record field that mapped to the Group table |

2.2.75.6 List of indexes of the table rule_group

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| RULE_GROUP__RULE_IDX |  |  | X | rule_group |
| RULE_GROUP__GROUP_IDX |  |  | X | rule_group |
| RULE_GROUP__UNQ | X |  |  | rule_group |

2.2.76 Table rule_organisation

2.2.76.1 Card of table rule_organisation

| Code | RULE_ORGANISATION |
| --- | --- |
| Comment | Many to many table that links Rules and their coresponding organisations |

2.2.76.2 Check constraint name of the table rule_organisation

CKT_RULE_ORGANISATION

2.2.76.3 List of outgoing references of the table rule_organisation

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_RULE_ORG__ORG | organisation | fk_org_sid |
| FK_RULE_ORG__RULE | assignment_policy_rule | fk_rule_sid |

2.2.76.4 List of diagrams containing the table rule_organisation

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.76.5 List of columns of the table rule_organisation

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| FK_RULE_SID | INT8 | X |  | Foreign key to assignment_policy_rule table |
| FK_ORG_SID | INT8 | X |  | Foreign key to organisation table |

2.2.76.6 List of indexes of the table rule_organisation

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| RULE_ORG__ORG_IDX |  |  | X | rule_organisation |
| RULE_ORG__RULE_IDX |  |  | X | rule_organisation |
| RULE_ORG_UNQ | X |  |  | rule_organisation |

2.2.77 Table rule_process

2.2.77.1 Card of table rule_process

| Code | RULE_PROCESS |
| --- | --- |
| Comment | Many to many table that links Rules and their coresponding processes |

2.2.77.2 Check constraint name of the table rule_process

CKT_RULE_PROCESS

2.2.77.3 List of outgoing references of the table rule_process

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_RULE_PROCESS__PROCESS | process_def | fk_process_sid |
| FK_RULE_PROCESS__RULE | assignment_policy_rule | fk_rule_sid |

2.2.77.4 List of diagrams containing the table rule_process

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.77.5 List of columns of the table rule_process

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| FK_RULE_SID | INT8 | X |  | Foreign key pointing to theRule table |
| FK_PROCESS_SID | INT8 | X |  | Foreign key to the process_def table |

2.2.77.6 List of indexes of the table rule_process

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| RULE_PROCESS__PROCESS_IDX |  |  | X | rule_process |
| RULE_PROCESS__RULE_IDX |  |  | X | rule_process |
| RULE_PROCESS_UNQ | X |  |  | rule_process |

2.2.78 Table rule_role

2.2.78.1 Card of table rule_role

| Code | RULE_ROLE |
| --- | --- |
| Comment | Table that holds information about roles associated with an assigment policy rule |

2.2.78.2 Check constraint name of the table rule_role

CKT_RULE_ROLE

2.2.78.3 List of outgoing references of the table rule_role

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_RULE_ROLE__ROLE | role | fk_role_sid |
| FK_RULE_ROLE__RULE | assignment_policy_rule | fk_rule_sid |

2.2.78.4 List of diagrams containing the table rule_role

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.78.5 List of columns of the table rule_role

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| FK_RULE_SID | INT8 | X |  | Foreign key to assignment_policy_rule Table |
| FK_ROLE_SID | INT8 | X |  | the surrogate key |

2.2.78.6 List of indexes of the table rule_role

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| RULE_ROLE__ROLE_IDX |  |  | X | rule_role |
| RULE_ROLE__RULE_IDX |  |  | X | rule_role |
| RULE_ROLE_UNQ | X |  |  | rule_role |

2.2.79 Table rule_sector

2.2.79.1 Card of table rule_sector

| Code | RULE_SECTOR |
| --- | --- |
| Comment | Many to many table that links Rules and their coresponding sectors |

2.2.79.2 Check constraint name of the table rule_sector

CKT_RULE_SECTOR

2.2.79.3 List of outgoing references of the table rule_sector

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_RULE_SECTOR__ASSIGN_POL_RUL | assignment_policy_rule | fk_rule_sid |
| FK_RULE_SECTOR__SECTOR | sector | fk_sector_sid |

2.2.79.4 List of diagrams containing the table rule_sector

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.79.5 List of columns of the table rule_sector

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| FK_RULE_SID | INT8 | X |  | Foreign key to assignment_policy_rule table |
| FK_SECTOR_SID | INT8 | X |  | Foreign key to sector table |

2.2.79.6 List of indexes of the table rule_sector

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| RULE_SECTOR__ASSIGN_POL_R_IDX |  |  | X | rule_sector |
| RULE_SECTOR_UNQ | X |  |  | rule_sector |
| RULE_SECTOR__SECTOR_IDX |  |  | X | rule_sector |

2.2.80 Table rule_user

2.2.80.1 Card of table rule_user

| Code | RULE_USER |
| --- | --- |
| Comment | Many to many table that links the Rules to its Users |

2.2.80.2 Check constraint name of the table rule_user

CKT_RULE_USER

2.2.80.3 List of outgoing references of the table rule_user

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_RULE_USER__ASSIGN_POL_RULE | assignment_policy_rule | fk_rule_sid |
| FK_RULE_USER__USER | iam_user | fk_user_sid |

2.2.80.4 List of diagrams containing the table rule_user

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.80.5 List of columns of the table rule_user

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| FK_RULE_SID | INT8 | X |  | Linked record field that mapped to the Rule table |
| FK_USER_SID | INT8 | X |  | Linked record field that mapped to User Table |

2.2.80.6 List of indexes of the table rule_user

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| RULE_USER__RULE_IDX |  |  | X | rule_user |
| RULE_USER__USER_IDX |  |  | X | rule_user |
| RULE_USER_UNQ | X |  |  | rule_user |

2.2.81 Table search_def_group

2.2.81.1 Card of table search_def_group

| Code | SEARCH_DEF_GROUP |
| --- | --- |
| Comment | The search definition group table. |

2.2.81.2 Check constraint name of the table search_def_group

CKT_SEARCH_DEF_GROUP

2.2.81.3 List of outgoing references of the table search_def_group

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_SEARCH_DEF_GROUP__GROUP | iam_group | fk_iam_group_sid |
| FK_SEARCH_DEF_GROUP__SEARCH_DEF | search_definition | fk_search_definition_sid |

2.2.81.4 List of diagrams containing the table search_def_group

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.81.5 List of columns of the table search_def_group

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| FK_SEARCH_DEFINITION_SID | INT8 |  |  | Foreign key to the search definition table |
| FK_IAM_GROUP_SID | INT8 |  |  | Foreign key to the iam group table |

2.2.81.6 List of indexes of the table search_def_group

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| SEARCH_DEF_GROUP__GROUP_IDX |  |  | X | search_def_group |
| SRCH_DEF_GROUP__SEARCH_DEF_IDX |  |  | X | search_def_group |

2.2.82 Table search_def_org

2.2.82.1 Card of table search_def_org

| Code | SEARCH_DEF_ORG |
| --- | --- |
| Comment | Many-to-many association between search_definition and organisation table. |

2.2.82.2 Check constraint name of the table search_def_org

CKT_SEARCH_DEF_ORG

2.2.82.3 List of outgoing references of the table search_def_org

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_SEARCH_DEF_ORG__ORG | organisation | fk_organisation_sid |
| FK_SEARCH_DEF_ORG__SEARCH_DEF | search_definition | fk_search_definition_sid |

2.2.82.4 List of diagrams containing the table search_def_org

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.82.5 List of columns of the table search_def_org

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| FK_SEARCH_DEFINITION_SID | INT8 | X |  | Foreign key to the search definition table. |
| FK_ORGANISATION_SID | INT8 | X |  | Foreign key to the organisation table. |

2.2.82.6 List of indexes of the table search_def_org

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| SEARCH_DEF__ORG_IDX |  |  | X | search_def_org |
| SEARCH_DEF__SEARCH_DEF_IDX |  |  | X | search_def_org |

2.2.83 Table search_def_proc_def

2.2.83.1 Card of table search_def_proc_def

| Code | SEARCH_DEF_PROC_DEF |
| --- | --- |
| Comment | Many-to-many association between search_definition and process_definition table. |

2.2.83.2 Check constraint name of the table search_def_proc_def

CKT_SEARCH_DEF_PROC_DEF

2.2.83.3 List of outgoing references of the table search_def_proc_def

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_SRCH_DEF_PROC_DEF__PROC_DEF | process_def | fk_process_definition_sid |
| FK_SRCH_DEF_PROC_DEF__SRCH_DEF | search_definition | fk_search_definition_sid |

2.2.83.4 List of diagrams containing the table search_def_proc_def

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.83.5 List of columns of the table search_def_proc_def

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| FK_SEARCH_DEFINITION_SID | INT8 | X |  | Foreign key to the search definition table. |
| FK_PROCESS_DEFINITION_SID | INT8 | X |  | Foreign key to the process definition table. |

2.2.83.6 List of indexes of the table search_def_proc_def

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| SRCH_DEF_PROC_DEF__SRCH_DEF_IDX |  |  | X | search_def_proc_def |
| SRCH_DEF_PROC_DEF__PROC_DEF_IDX |  |  | X | search_def_proc_def |

2.2.84 Table search_def_user

2.2.84.1 Card of table search_def_user

| Code | SEARCH_DEF_USER |
| --- | --- |
| Comment | Many-to-many association between search_definition and user group table. |

2.2.84.2 Check constraint name of the table search_def_user

CKT_SEARCH_DEF_USER

2.2.84.3 List of outgoing references of the table search_def_user

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_SEARCH_DEF_USER__SEARCH_DEF | search_definition | fk_search_definition_sid |
| FK_SEARCH_DEF_USER__USER | iam_user | fk_iam_user_sid |

2.2.84.4 List of diagrams containing the table search_def_user

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.84.5 List of columns of the table search_def_user

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| FK_IAM_USER_SID | INT8 | X |  | Foreign key to the iam user table. |
| FK_SEARCH_DEFINITION_SID | INT8 | X |  | Foreign key to the search definition table. |

2.2.84.6 List of indexes of the table search_def_user

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| SEARCH_DEF_USER__USER_IDX |  |  | X | search_def_user |
| SEARCH_DEF_USER__SEARCH_DEF_IDX |  |  | X | search_def_user |

2.2.85 Table search_definition

2.2.85.1 Card of table search_definition

| Code | SEARCH_DEFINITION |
| --- | --- |
| Comment | The search definition table. |

2.2.85.2 Check constraint name of the table search_definition

CKT_SEARCH_DEFINITION

2.2.85.3 List of incoming references of the table search_definition

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| FK_SEARCH_DEF_GROUP__SEARCH_DEF | search_def_group | fk_search_definition_sid |
| FK_SEARCH_DEF_ORG__SEARCH_DEF | search_def_org | fk_search_definition_sid |
| FK_SEARCH_DEF_USER__SEARCH_DEF | search_def_user | fk_search_definition_sid |
| FK_SRCH_DEF_PROC_DEF__SRCH_DEF | search_def_proc_def | fk_search_definition_sid |

2.2.85.4 List of outgoing references of the table search_definition

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_IAM_USER__SEARCH_DEF | iam_user | fk_iam_user_sid |

2.2.85.5 List of diagrams containing the table search_definition

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.85.6 List of columns of the table search_definition

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X |  | The surrogate key. |
| FK_IAM_USER_SID | INT8 | X |  | Foreign key to the iam user table. |
| ID | VARCHAR(255) | X |  | The id of the search definition. |
| NAME | VARCHAR(255) | X |  | The name of the search definition. |
| COLOR | VARCHAR(255) |  |  | The color of the search definition. |
| TIME_INTERVAL_TYPE | VARCHAR(50) |  |  | The selected time interval of the search definition. |
| IMPORTANCES | TEXT |  |  | The importances saved for the specific search definition. |
| CRITICALITIES | TEXT |  |  | The criticalities saved for the specific search definition. |
| STATUSES | VARCHAR(100) |  |  | The statuses saved for the specific search definition. |
| START_DATE | TIMESTAMP WITH TIME ZONE |  |  | The start date of the search definition for retrieving the desired custom interval. |
| END_DATE | TIMESTAMP WITH TIME ZONE |  |  | The end date of the search definition for retrieving the desired custom interval. |

2.2.85.7 List of keys of the table search_definition

| Code | Primary |
| --- | --- |
| SEARCH_DEFINITION_PK | X |

2.2.85.8 List of indexes of the table search_definition

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| SEARCH_DEF_IDX | X | X |  | search_definition |
| SEARCH_DEF_ID_UNQ | X |  |  | search_definition |
| SEARCH_DEF__IAM_USER_FK |  |  | X | search_definition |

2.2.86 Table sector

2.2.86.1 Card of table sector

| Code | SECTOR |
| --- | --- |
| Comment | Table that holds information about the Sector |

2.2.86.2 Check constraint name of the table sector

CKT_SECTOR

2.2.86.3 List of incoming references of the table sector

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| FK_POLICY__SECTOR | policy | fk_sector_sid |
| FK_PROCESS_DEF__SECTOR | process_def | fk_sector_sid |
| FK_RULE_SECTOR__SECTOR | rule_sector | fk_sector_sid |

2.2.86.4 List of diagrams containing the table sector

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.86.5 List of columns of the table sector

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('sector_seq') | The surrogate key |
| NAME | VARCHAR(50) | X |  | The name of the sector |

2.2.86.6 List of keys of the table sector

| Code | Primary |
| --- | --- |
| SECTOR_PK | X |

2.2.86.7 List of indexes of the table sector

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| SECTOR_IDX | X | X |  | sector |
| SECTOR_UNQ | X |  |  | sector |

2.2.87 Table signature

2.2.87.1 Card of table signature

| Code | SIGNATURE |
| --- | --- |
| Comment | Table that holds information about the User Message Signature |

2.2.87.2 Check constraint name of the table signature

CKT_SIGNATURE

2.2.87.3 List of outgoing references of the table signature

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_SIGNATURE__MESSAGE | user_message | fk_message_sid |

2.2.87.4 List of diagrams containing the table signature

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.87.5 List of columns of the table signature

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('signature_seq') | The surrogate key |
| ID | VARCHAR(255) | X |  | The id of the Signature |
| FK_MESSAGE_SID | INT8 | X |  | Foreign key that links the Signature to the user message table |
| SED_SIGNATURE | TEXT |  |  | The sed signature. |
| LAST_UPDATE | TIMESTAMP WITH TIME ZONE |  | now() | Date & time of last update. |

2.2.87.6 List of keys of the table signature

| Code | Primary |
| --- | --- |
| SIGNATURE_PK | X |

2.2.87.7 List of indexes of the table signature

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| SIGNATURE_IDX | X | X |  | signature |
| MESSAGE_SID_IDX |  |  | X | signature |

2.2.88 Table subdoc_bversion_attachment

2.2.88.1 Card of table subdoc_bversion_attachment

| Code | SUBDOC_BVERSION_ATTACHMENT |
| --- | --- |
| Comment | Many to many table that links subdoc bversions to their attachments |

2.2.88.2 Check constraint name of the table subdoc_bversion_attachment

CKT_SUBDOC_BVERSION_ATTACHMENT

2.2.88.3 List of outgoing references of the table subdoc_bversion_attachment

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_SUBDOC_BVER_ATT__SUBDOC_ATT | subdocument_attachment | fk_subdoc_attachment_sid |
| FK_SUBDOC_BVER_ATT__SUBDOC_BVER | subdocument_bversion | fk_subdoc_bversion_sid |

2.2.88.4 List of diagrams containing the table subdoc_bversion_attachment

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.88.5 List of columns of the table subdoc_bversion_attachment

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| FK_SUBDOC_ATTACHMENT_SID | INT8 | X |  | Linked record field that mapped to the attachments |
| FK_SUBDOC_BVERSION_SID | INT8 | X |  | The surrogate key |

2.2.88.6 List of indexes of the table subdoc_bversion_attachment

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| SUBDOC_HIS_ATT__DOC_ATT_IDX |  |  | X | subdoc_bversion_attachment |
| SUBDOC_HIS_ATTACH__DOC_HIS_IDX |  |  | X | subdoc_bversion_attachment |

2.2.89 Table subdocument

2.2.89.1 Card of table subdocument

| Code | SUBDOCUMENT |
| --- | --- |
| Comment | The subdocument table. |

2.2.89.2 Check constraint name of the table subdocument

CKT_SUBDOCUMENT

2.2.89.3 List of incoming references of the table subdocument

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| FK_SUBDOC_ATTACH__SUBDOC | subdocument_attachment | fk_subdoc_sid |
| FK_SUBDOC_BVERSION__SUBDOC | subdocument_bversion | fk_subdoc_sid |
| FK_SUBDOC_CONTENT_SUBDOC | subdocument_content | fk_subdoc_sid |
| FK_SUBDOC_HIS__SUBDOC | subdocument_history | fk_subdoc_sid |
| FK_SUBDOC_PREFILL__SUBDOC | subdocument_prefill | fk_subdoc_sid |

2.2.89.4 List of outgoing references of the table subdocument

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_SUBDOC__DOC | document | fk_document_sid |
| FK_SUBDOC__RINA_CASE | rina_case | fk_case_sid |
| FK_SUBDOC__SUBDOC_BVERSION | subdocument_bversion | fk_subdoc_bversion_sid |

2.2.89.5 List of views of the table subdocument

| Code |
| --- |
| V_SUBDOCUMENTS_SEARCH |

2.2.89.6 List of diagrams containing the table subdocument

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.89.7 List of columns of the table subdocument

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('subdocument_seq') | The surrogate key |
| VERSION | INT4 | X | 1 | The system version. It is automatically increased by Hibernate each time the row is updated. |
| FK_CASE_SID | INT8 | X |  | Foreign key that points to the Case table |
| FK_DOCUMENT_SID | INT8 | X |  | Foreign key that points to the Document table |
| FK_SUBDOC_BVERSION_SID | INT8 |  |  | The content of the document |
| ID | VARCHAR(255) | X |  | The id of the subdocument. |
| NAME | VARCHAR(255) |  |  | The name of the subdocument. |
| NO | INT8 |  |  | The number of the subdocument. |
| BUSINESS_REFERENCE | VARCHAR(255) |  |  | The business refference of the subdocument. |
| IS_VALID | BOOL | X | true | The is valid flag. |
| IS_ACTIVE | BOOL | X | true | The is active flag. |
| VALIDATION_ERRORS | TEXT |  |  | The validation errors occured for this subdocument. |
| CREATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | Date & Time the entity was created |
| UPDATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | Date & Time entity was updated |
| CREATED_BY | VARCHAR(255) | X | '0' | The person/process that created the record. |
| UPDATED_BY | VARCHAR(255) | X | '0' | The person/process that last updated the record. |
| RANDOM_STRING | VARCHAR(255) | X | 'A1' | Random string created for the subdocument. |

2.2.89.8 List of keys of the table subdocument

| Code | Primary |
| --- | --- |
| SUBDOCUMENT_PK | X |

2.2.89.9 List of indexes of the table subdocument

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| SUBDOCUMENT_IDX | X | X |  | subdocument |
| SUBDOC__DOC_IDX |  |  | X | subdocument |
| SUBDOC__CASE_IDX |  |  | X | subdocument |
| SUBDOC__SUBDOC_BVERSION_IDX |  |  | X | subdocument |
| SUBDOC_ID_UNQ | X |  |  | subdocument |
| SUBDOC__B_REF_IDX |  |  |  | subdocument |

2.2.90 Table subdocument_attachment

2.2.90.1 Card of table subdocument_attachment

| Code | SUBDOCUMENT_ATTACHMENT |
| --- | --- |
| Comment | Table that holds information about the attachment of the subdocument |

2.2.90.2 Check constraint name of the table subdocument_attachment

CKT_SUBDOCUMENT_ATTACHMENT

2.2.90.3 List of incoming references of the table subdocument_attachment

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| FK_SUBDOC_BVER_ATT__SUBDOC_ATT | subdoc_bversion_attachment | fk_subdoc_attachment_sid |

2.2.90.4 List of outgoing references of the table subdocument_attachment

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_SUBDOC_ATTACH__SUBDOC | subdocument | fk_subdoc_sid |

2.2.90.5 List of diagrams containing the table subdocument_attachment

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.90.6 List of columns of the table subdocument_attachment

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('subdoc_attachment_seq') | The surrogate key |
| VERSION | INT4 | X | 1 | The version. |
| FK_SUBDOC_SID | INT8 | X |  | Foreign key that points to the subdocument table |
| MIME_TYPE | VARCHAR(50) | X |  | The mime type of the attachment for the subdocument. Possible values: APP_PDF APP_MSWORD APP_MSEXCEL APP_MSPOWERPOINT APP_OPENXML_DOC APP_OPENXML_SPREADSHEET APP_OPENXML_PRESENTATION APP_XML APP_ZIP APP_GZIP IMG_JPEG IMG_PNG IMG_TIFF TXT_RTF TXT_XML // Mimetypes NOT included in the SBDH XSD definition APP_X_ZIP APP_OCTET_STREAM APP_X_ZIP_COMPRESSED |
| ID | VARCHAR(255) | X |  | The id of the attachment for the subdocument. |
| NAME | VARCHAR(255) |  |  | The name of the attachment for the subdocument. |
| FILENAME | VARCHAR(1024) |  |  | The directory path where the assignment is stored |
| PATHNAME | VARCHAR(1024) | X |  | The complet path of the attachment for the subdocument. |
| IS_MEDICAL | BOOL | X | false | The is medical flag. |
| IS_ACTIVE | BOOL | X | true | Status of the subdocument |
| CREATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | Date & Time of Creation. |
| UPDATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | Date & time of last update. |
| CREATED_BY | VARCHAR(255) | X | '0' | The person/process that created the record. |
| UPDATED_BY | VARCHAR(255) | X | '0' | The person/process that last updated the record. |

2.2.90.7 List of keys of the table subdocument_attachment

| Code | Primary |
| --- | --- |
| SUBDOC_ATTACHEMENT_PK | X |

2.2.90.8 List of indexes of the table subdocument_attachment

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| SUBDOC_ATTACHEMENT_IDX | X | X |  | subdocument_attachment |
| SUBDOC_ATT__SUBDOC_IDX |  |  | X | subdocument_attachment |
| SUBDOC_ATTACHMENT_ID_UNQ | X |  |  | subdocument_attachment |

2.2.91 Table subdocument_bversion

2.2.91.1 Card of table subdocument_bversion

| Code | SUBDOCUMENT_BVERSION |
| --- | --- |
| Comment | The business version associated to a specific subdocument |

2.2.91.2 Check constraint name of the table subdocument_bversion

CKT_SUBDOCUMENT_BVERSION

2.2.91.3 List of incoming references of the table subdocument_bversion

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| FK_DOC_BV_SUBDOC_BV__SUBDOC_BV | doc_bversion_subdoc_bversion | fk_subdoc_bversion_sid |
| FK_SUBDOC__SUBDOC_BVERSION | subdocument | fk_subdoc_bversion_sid |
| FK_SUBDOC_BVER_ATT__SUBDOC_BVER | subdoc_bversion_attachment | fk_subdoc_bversion_sid |
| FK_SUBDOC_HIS__SUBDOC_BVERSION | subdocument_history | fk_subdoc_bversion_sid |

2.2.91.4 List of outgoing references of the table subdocument_bversion

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_SUBDOC_BVER__SUBDOC_CONTENT | subdocument_content | fk_subdoc_content_sid |
| FK_SUBDOC_BVERSION__SUBDOC | subdocument | fk_subdoc_sid |

2.2.91.5 List of diagrams containing the table subdocument_bversion

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.91.6 List of columns of the table subdocument_bversion

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('subdocument_bversion_seq') | The surrogate key |
| FK_SUBDOC_SID | INT8 | X |  | Foreign key to the subdocument table. |
| FK_SUBDOC_CONTENT_SID | INT8 |  |  | Foreign key to the subdocument content table. |
| ID | INT4 | X | 1 | The id of the subdocument bversion. |
| IS_ACTIVE | BOOL | X | true | The is active flag. |
| VERSION | INT4 | X | 1 | The system version. It is automatically increased by Hibernate each time the row is updated. |
| CREATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | The time that the subdocument bversion was first inserted into the DB |
| UPDATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | The last time that the subdocument bversion was updated |
| CREATED_BY | VARCHAR(255) | X | '0' | The person/process that created the record. |
| UPDATED_BY | VARCHAR(255) | X | '0' | The person/process that last updated the record. |

2.2.91.7 List of keys of the table subdocument_bversion

| Code | Primary |
| --- | --- |
| SUBDOCUMENT_BVERSION_PK | X |

2.2.91.8 List of indexes of the table subdocument_bversion

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| SUBDOCUMENT_BVERSION_IDX | X | X |  | subdocument_bversion |
| SUBDOC_BVERSION__SUBDOC_IDX |  |  | X | subdocument_bversion |
| SUBDOC_BVER__SUBDOC_CONTENT_IDX |  |  | X | subdocument_bversion |
| SUBDOC_BVERSION_UNQ | X |  |  | subdocument_bversion |

2.2.92 Table subdocument_content

2.2.92.1 Card of table subdocument_content

| Code | SUBDOCUMENT_CONTENT |
| --- | --- |
| Comment | The content associated to a specific subdocument |

2.2.92.2 Check constraint name of the table subdocument_content

CKT_SUBDOCUMENT_CONTENT

2.2.92.3 List of incoming references of the table subdocument_content

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| FK_SUBDOC_BVER__SUBDOC_CONTENT | subdocument_bversion | fk_subdoc_content_sid |

2.2.92.4 List of outgoing references of the table subdocument_content

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_SUBDOC_CONTENT_SUBDOC | subdocument | fk_subdoc_sid |

2.2.92.5 List of diagrams containing the table subdocument_content

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.92.6 List of columns of the table subdocument_content

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('subdocument_content_seq') | The surrogate key |
| FK_SUBDOC_SID | INT8 | X |  | Foreign key to the subdocument table. |
| CONTENT | TEXT | X |  | The content of the subdocument. |
| IS_ACTIVE | BOOL | X | true | The is active flag. |

2.2.92.7 List of keys of the table subdocument_content

| Code | Primary |
| --- | --- |
| SUBDOC_CONTENT_PK | X |

2.2.92.8 List of indexes of the table subdocument_content

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| SUBDOC_CONTENT_IDX | X | X |  | subdocument_content |

2.2.93 Table subdocument_history

2.2.93.1 Card of table subdocument_history

| Code | SUBDOCUMENT_HISTORY |
| --- | --- |
| Comment | The history of the subdocument table. |

2.2.93.2 Check constraint name of the table subdocument_history

CKT_SUBDOCUMENT_HISTORY

2.2.93.3 List of outgoing references of the table subdocument_history

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_SUBDOC_HIS__SUBDOC | subdocument | fk_subdoc_sid |
| FK_SUBDOC_HIS__SUBDOC_BVERSION | subdocument_bversion | fk_subdoc_bversion_sid |

2.2.93.4 List of diagrams containing the table subdocument_history

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.93.5 List of columns of the table subdocument_history

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('subdocument_seq') | The surrogate key |
| FK_SUBDOC_SID | INT8 | X |  | Foreign key that points to subdocument table |
| FK_DOC_SID | INT8 | X |  | Foreign key that points to document table |
| FK_CASE_SID | INT8 | X |  | Foreign key that points to case table |
| FK_SUBDOC_BVERSION_SID | INT8 |  |  | The content of the document |
| VERSION | INT4 | X |  | The actual version |
| ID | VARCHAR(255) | X |  | The id of the subdocument history |
| NAME | VARCHAR(255) |  |  | The id of the history of the subdocument. |
| UPDATED_AT | TIMESTAMP WITH TIME ZONE | X |  | Date & Time the history was updated |
| UPDATED_BY | VARCHAR(255) | X |  | The person/process that last updated the record. |

2.2.93.6 List of keys of the table subdocument_history

| Code | Primary |
| --- | --- |
| SUBDOC_HIS_PK | X |

2.2.93.7 List of indexes of the table subdocument_history

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| SUBDOC_HIS_IDX | X | X |  | subdocument_history |
| SUBDOC_HIS_SID_VERSION_UNQ | X |  |  | subdocument_history |
| SUBDOC_HIS__SUBDOC_IDX |  |  | X | subdocument_history |
| SOBDOC_HIS__SOBDOC_BVERSION_IDX |  |  | X | subdocument_history |

2.2.94 Table subdocument_prefill

2.2.94.1 Card of table subdocument_prefill

| Code | SUBDOCUMENT_PREFILL |
| --- | --- |
| Comment | The prefill data associated to a specific subdocument |

2.2.94.2 Check constraint name of the table subdocument_prefill

CKT_SUBDOCUMENT_PREFILL

2.2.94.3 List of outgoing references of the table subdocument_prefill

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_SUBDOC_PREFILL__SUBDOC | subdocument | fk_subdoc_sid |

2.2.94.4 List of diagrams containing the table subdocument_prefill

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.94.5 List of columns of the table subdocument_prefill

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('subdoc_prefill_seq') | The surrogate key |
| FK_SUBDOC_SID | INT8 | X |  | Foreign key to the subdocument table |
| PREFILL_GROUP | VARCHAR(20) | X | PREFILL | The prefill group value of the subdocument. Possible values: SUBJECT, PREFILL, SEARCH_METADATA; |
| KEY | VARCHAR(1024) | X |  | The key for the prefill of the subdocument. |
| VALUE | TEXT | X |  | The value for the prefill of the subdocument. |

2.2.94.6 List of keys of the table subdocument_prefill

| Code | Primary |
| --- | --- |
| CASE_PREFILL_PK | X |

2.2.94.7 List of indexes of the table subdocument_prefill

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| SUBDOC_PREFILL_IDX | X | X |  | subdocument_prefill |
| SUBDOC_PREFILL__SUBDOC_IDX |  |  | X | subdocument_prefill |
| SUBDOC_PREFILL__GROUP_IDX |  |  |  | subdocument_prefill |
| SUBDOC_PREFILL__KEY_UNQ | X |  |  | subdocument_prefill |

2.2.95 Table supported_language

2.2.95.1 Card of table supported_language

| Code | SUPPORTED_LANGUAGE |
| --- | --- |
| Comment | Table that holds the language code |

2.2.95.2 Check constraint name of the table supported_language

CKT_SUPPORTED_LANGUAGE

2.2.95.3 List of diagrams containing the table supported_language

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.95.4 List of columns of the table supported_language

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('supported_language_seq') | The surrogate key |
| LANG | VARCHAR(2) | X |  | The language code |

2.2.95.5 List of keys of the table supported_language

| Code | Primary |
| --- | --- |
| SUPPORTED_LANGUAGE_PK | X |

2.2.95.6 List of indexes of the table supported_language

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| SUPPORTED_LANGUAGE_IDX | X | X |  | supported_language |
| SUPPORTED_LANGUAGE_LANG_UNQ | X |  |  | supported_language |

2.2.96 Table tenant

2.2.96.1 Card of table tenant

| Code | TENANT |
| --- | --- |
| Comment | Table that holds information about the Tenant |

2.2.96.2 Check constraint name of the table tenant

CKT_TENANT

2.2.96.3 List of incoming references of the table tenant

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| FK_ASS_POL_TRGT__TENANT | assignment_policy_target | fk_tenant_sid |
| FK_ASSIGNMENT_POL__TENANT | assignment_policy | fk_tenant_sid |
| FK_CASE__TENANT | rina_case | fk_tenant_sid |
| FK_IAM_GROUP__TENANT | iam_group | fk_tenant_sid |
| FK_IAM_USER__TENANT | iam_user | fk_tenant_sid |
| FK_POLICY__TENANT | policy | fk_tenant_sid |
| FK_TENANT_PARAM__TENANT | tenant_param | fk_tenant_sid |
| FK_TENANT_PARAM_GROUP___TENANT | tenant_param_group | fk_tenant_sid |

2.2.96.4 List of outgoing references of the table tenant

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_TENANT__ORGANISATION | organisation | fk_org_sid |

2.2.96.5 List of diagrams containing the table tenant

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.96.6 List of columns of the table tenant

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('tenant_seq') | The surrogate key |
| VERSION | INT4 | X | 1 | The system version. It is automatically increased by Hibernate each time the row is updated. |
| FK_ORG_SID | INT8 | X |  | Foreign key to the organisation table. |
| ID | VARCHAR(255) | X |  | The id of the tenant |
| IS_ENABLED | BOOL | X | true | Use to check if enable or not |
| IS_DEFAULT | BOOL | X | false | Use to check if it is default tenant or not |
| INCOMING_MSG_RELATIVE_PATH | VARCHAR(255) |  |  | The ralative path od the incoming message |
| CREATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | Date & Time by whom the tenant was created |
| UPDATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | Date & Time the tenant's details was updated |

2.2.96.7 List of keys of the table tenant

| Code | Primary |
| --- | --- |
| TENANT_PK | X |

2.2.96.8 List of indexes of the table tenant

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| TENANT_IDX | X | X |  | tenant |
| TENANT__ORG_IDX | X |  | X | tenant |
| TENANT_ID_UNQ | X |  |  | tenant |

2.2.97 Table tenant_param

2.2.97.1 Card of table tenant_param

| Code | TENANT_PARAM |
| --- | --- |
| Comment | Parameters assosiated with a tenant |

2.2.97.2 Check constraint name of the table tenant_param

CKT_TENANT_PARAM

2.2.97.3 List of outgoing references of the table tenant_param

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_TENANT_PARAM__TENANT | tenant | fk_tenant_sid |
| TENANT_PARAM__TENANT_PARAM_GRP | tenant_param_group | fk_tenant_param_group_sid |

2.2.97.4 List of diagrams containing the table tenant_param

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.97.5 List of columns of the table tenant_param

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('tenant_param_seq') | The surrogate key |
| FK_TENANT_SID | INT8 | X |  | Foreign key to the tenant table. |
| FK_TENANT_PARAM_GROUP_SID | INT8 |  |  | Foreign key to the tenant param group table. |
| KEY | VARCHAR(255) | X |  | The key of the parameter |
| VALUE | VARCHAR(255) | X |  | The value of the parameter |

2.2.97.6 List of keys of the table tenant_param

| Code | Primary |
| --- | --- |
| TENANT_PARAM_PK | X |

2.2.97.7 List of indexes of the table tenant_param

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| TENANT_PARAM_IDX | X | X |  | tenant_param |
| TENANT_PARAM_KEY_UNQ | X |  |  | tenant_param |
| TENANT_PARAM__TENANT_IDX |  |  | X | tenant_param |
| TENANT_PRM__TENANT_PRM_GRP_IDX |  |  | X | tenant_param |

2.2.98 Table tenant_param_group

2.2.98.1 Card of table tenant_param_group

| Code | TENANT_PARAM_GROUP |
| --- | --- |
| Comment | Table that holds a group of global_application_params, with version for optimistic locking and auditing properties. |

2.2.98.2 Check constraint name of the table tenant_param_group

CKT_TENANT_PARAM_GROUP

2.2.98.3 List of incoming references of the table tenant_param_group

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| TENANT_PARAM__TENANT_PARAM_GRP | tenant_param | fk_tenant_param_group_sid |

2.2.98.4 List of outgoing references of the table tenant_param_group

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_TENANT_PARAM_GROUP___TENANT | tenant | fk_tenant_sid |

2.2.98.5 List of diagrams containing the table tenant_param_group

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.98.6 List of columns of the table tenant_param_group

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('tenant_param_group_seq') | The surrogate key |
| VERSION | INT4 | X | 1 | The system version. It is automatically increased by Hibernate each time the row is updated. |
| FK_TENANT_SID | INT8 | X |  | Foreign key to the tenant table. |
| NAME | VARCHAR(255) | X |  | The name of the tennant param group. Possible values: CASE_COUNTER_SETTINGS, LDAP_CONNECTION_SETTINGS, LDAP_USER_PARAMETERS_MAPPING, LDAP_GROUP_PARAMETERS_MAPPING, MESSAGE_SETTINGS_PARAMETERS_MAPPING; |
| CREATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | Date & Time by whom the tenant was created |
| UPDATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | Date & Time the tenant's details was updated |
| CREATED_BY | VARCHAR(255) | X | '0' | The person/process that created the record. |
| UPDATED_BY | VARCHAR(255) | X | '0' | The person/process that last updated the record. |
| RANDOM_STRING | VARCHAR(255) | X | 'A1' | Random string created for the tenant param group. |

2.2.98.7 List of keys of the table tenant_param_group

| Code | Primary |
| --- | --- |
| TENANT_PARAM_GROUP_PK | X |

2.2.98.8 List of indexes of the table tenant_param_group

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| TENANT_PARAM_GROUP_IDX | X | X |  | tenant_param_group |
| TENANT_PARAM_GROUP_NAME_UNQ | X |  |  | tenant_param_group |
| TENANT_PARAM_GROUP__TENANT_IDX |  |  | X | tenant_param_group |

2.2.99 Table translation

2.2.99.1 Card of table translation

| Code | TRANSLATION |
| --- | --- |
| Comment | Table that holds the transation per language |

2.2.99.2 Check constraint name of the table translation

CKT_TRANSLATION

2.2.99.3 List of diagrams containing the table translation

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.99.4 List of columns of the table translation

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('translation_seq') | The surrogate key |
| LANG | VARCHAR(2) | X |  | The language code. Possible values: bg, cs, da, de, en, el, es, et, fi, fr, hr, hu, it, lt, lv, mt, nl, no, pl, pt, ro, sk, sl, sv, |
| CONTENT | TEXT | X |  | The content of the translation. |

2.2.99.5 List of keys of the table translation

| Code | Primary |
| --- | --- |
| TRANSLATION_PK | X |

2.2.99.6 List of indexes of the table translation

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| TRANSLATION_IDX | X | X |  | translation |
| TRANSLATION_LANG_UNQ | X |  |  | translation |

2.2.100 Table transposition

2.2.100.1 Card of table transposition

| Code | TRANSPOSITION |
| --- | --- |
| Comment | The transposition json, pertinent to a specific document type |

2.2.100.2 Check constraint name of the table transposition

CKT_TRANSPOSITION

2.2.100.3 List of outgoing references of the table transposition

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_TRANSPOS__DOC_TYPE_VERSION | document_type_version | fk_doc_type_version_sid |
| FK_TRANSPOS__PROC_DEF_VERSION | process_def_version | fk_proc_def_version_sid |

2.2.100.4 List of diagrams containing the table transposition

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.100.5 List of columns of the table transposition

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('transposition_seq') | The surrogate key |
| FK_PROC_DEF_VERSION_SID | INT8 | X |  | Foreign key that links the Case to the process definition's version table |
| FK_DOC_TYPE_VERSION_SID | INT8 | X |  | Foreign key to document_type table |
| APPLICATION_ROLE | VARCHAR(2) | X |  | The Application Role. Possible values: PO("CaseOwner"), CP("CounterParty"); |
| JSON | TEXT | X |  | The json of the transposition. |

2.2.100.6 List of keys of the table transposition

| Code | Primary |
| --- | --- |
| TRANSPOSITION_PK | X |

2.2.100.7 List of indexes of the table transposition

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| TRANSPOSITION_IDX | X | X |  | transposition |
| TRANSPOS__DOC_TYPE_VERSION_IDX |  |  | X | transposition |
| TRANSPOS__PROC_DEF_VERSION_IDX |  |  | X | transposition |
| TRANSPOSITION_UNQ | X |  |  | transposition |

2.2.101 Table user_message

2.2.101.1 Card of table user_message

| Code | USER_MESSAGE |
| --- | --- |
| Comment | The user message associated to a specific conversation |

2.2.101.2 Check constraint name of the table user_message

CKT_USER_MESSAGE

2.2.101.3 List of incoming references of the table user_message

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| FK_SIGNATURE__MESSAGE | signature | fk_message_sid |
| FK_USR_MSG_RES__USR_MSG | user_message_response | fk_message_sid |

2.2.101.4 List of outgoing references of the table user_message

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_USER_MSG__DOC_CONV | document_conversation | fk_doc_conv_sid |
| FK_USER_MSG__RECEIVER | organisation | fk_receiver_sid |
| FK_USER_MSG__SENDER | organisation | fk_sender_sid |

2.2.101.5 List of diagrams containing the table user_message

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.101.6 List of columns of the table user_message

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('user_msg_seq') | The surrogate key |
| FK_SENDER_SID | INT8 | X |  | Foreign key to the user table. |
| FK_RECEIVER_SID | INT8 | X |  | Foreign key to the user table. |
| FK_DOC_CONV_SID | INT8 | X |  | Foreign key to the document conversation table. |
| ID | VARCHAR(255) | X |  | The id of the user message. |
| DIRECTION | VARCHAR(15) | X |  | The direction of the user message. Possible values: IN("IN"), OUT("OUT"); |
| ACTION | VARCHAR(15) | X |  | The action of the user message. Possible values: START("Start"), NEW("New"), UPDATE("Update"), START_FORWARD("StartForward"), NEW_FORWARD("NewForward"); |
| SBDH | TEXT | X |  | The sdbh of the user message. |
| STATUS | VARCHAR(50) |  |  | The status of the user message. Possible values: SENT("sent"), DELIVERED("delivered"), ERROR("error"), RESENT("resent"); |
| LAST_UPDATE | TIMESTAMP WITH TIME ZONE |  |  | Date & time of last update. |

2.2.101.7 List of keys of the table user_message

| Code | Primary |
| --- | --- |
| USER_MSG_PK | X |

2.2.101.8 List of indexes of the table user_message

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| USER_MSG_IDX | X | X |  | user_message |
| USER_MSG__SENDER_IDX |  |  | X | user_message |
| USER_MSG__RECEIVER_IDX |  |  | X | user_message |
| USER_MSG_ID_SENT_UNQ | X |  |  | user_message |

2.2.102 Table user_message_response

2.2.102.1 Card of table user_message_response

| Code | USER_MESSAGE_RESPONSE |
| --- | --- |
| Comment | Table that holds information about the user message response (ack / error) |

2.2.102.2 Check constraint name of the table user_message_response

CKT_USER_MESSAGE_RESPONSE

2.2.102.3 List of outgoing references of the table user_message_response

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_USR_MSG_RES__USR_MSG | user_message | fk_message_sid |

2.2.102.4 List of diagrams containing the table user_message_response

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.102.5 List of columns of the table user_message_response

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('user_message_response_seq') | The surrogate key |
| FK_MESSAGE_SID | INT8 | X |  | Foreign key that links the User message Response to the user message table |
| ID | VARCHAR(255) | X |  | The id of the user message response. |
| TYPE | VARCHAR(6) | X |  | The type of the user message response. Possible values: USERMESSAGE("usermessage"), ACK("ACK"), ERROR("ERROR"); |
| DESCRIPTION | TEXT |  |  | The description of the user message response. |
| LAST_UPDATE | TIMESTAMP WITH TIME ZONE |  |  | Date & time of last update. |

2.2.102.6 List of keys of the table user_message_response

| Code | Primary |
| --- | --- |
| USER_MESSAGE_STATUS_PK | X |

2.2.102.7 List of indexes of the table user_message_response

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| USER_MESSAGE_RESP_IDX | X | X |  | user_message_response |
| USER_MESSAGE_RESP_MSG_IDX |  |  | X | user_message_response |

2.2.103 Table user_profile

2.2.103.1 Card of table user_profile

| Code | USER_PROFILE |
| --- | --- |
| Comment | The table that holds the user profile. |

2.2.103.2 Check constraint name of the table user_profile

CKT_USER_PROFILE

2.2.103.3 List of outgoing references of the table user_profile

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_USER_PROFILE__PROCESS_DEF | process_def | fk_proc_def_sid |
| FK_USER_PROFILE__USER | iam_user | fk_user_sid |

2.2.103.4 List of diagrams containing the table user_profile

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.103.5 List of columns of the table user_profile

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('user_profile_seq') | The surrogate key |
| VERSION | INT4 | X | 1 | The system version. It is automatically increased by Hibernate each time the row is updated. |
| FK_USER_SID | INT8 | X |  | Foreign Key to User table |
| FK_PROC_DEF_SID | INT8 |  |  | Foreign key to the process definition table. |
| LANG | VARCHAR(2) |  |  | The language of the profile for the user. Possible values: bg, cs, da, de, en, el, es, et, fi, fr, hr, hu, it, lt, lv, mt, nl, no, pl, pt, ro, sk, sl, sv, |
| ALARM_AUTO_SET_DAYS | INT4 |  |  | The alarm auto set days flag. |
| ALARM_AUTO_SET_ON_SEND | BOOL |  |  | The alarm auto set on send flag. |
| DOCUMENT_DSPLAY_MODE | VARCHAR(255) |  |  | The display mode of the document for that profile |
| DOCUMENT_SORTBY | VARCHAR(255) |  |  | how is the document sort by for that profile |
| DOCUMENT_SHOWFLAGS | BOOL |  |  | flag to show document or not for that profile |
| FILTER_ACTION_TYPE | VARCHAR(10) |  |  | The filter action type of profile |
| CLASSIC_GROUP_BY_MONTH | BOOL |  |  | Use to flag if it is a classic group by month or not |
| CLASSIC_SHOW_PREVIEW | BOOL |  |  | Use to flag if it is a classic group by month or not |
| TIMELINE_DISPLAY_THUMBNAILS | BOOL |  |  | Use to flag how to display thumbnails or not |
| TIMELINE_DISPLAY_MODE | VARCHAR(20) |  |  | holda the display mode |
| LOCALE_LANG | VARCHAR(2) |  |  | holds the local language for that profile. Possible values: bg, cs, da, de, en, el, es, et, fi, fr, hr, hu, it, lt, lv, mt, nl, no, pl, pt, ro, sk, sl, sv, |
| LOCALE_NUMBER_FORMAT | VARCHAR(20) |  |  | holds the locale number format for that profile |
| LOCALE_DATE_FORMAT | VARCHAR(20) |  |  | The format of the locale for the date. |
| LOCALE_TIME_FORMAT | VARCHAR(20) |  |  | holds the local time format for that profile |
| LOCALE_CURRENCY | VARCHAR(3) |  |  | holds the local currency format for that profile |
| LOCALE_TIMEZONE | VARCHAR(3) |  |  | holds the local time zone for that profile |
| CREATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | Date & Time the User Profile was created |
| UPDATED_AT | TIMESTAMP WITH TIME ZONE | X | now() | Date & Time the User Profile was updated |
| CREATED_BY | VARCHAR(255) | X | '0' | The person/process that created the record. |
| UPDATED_BY | VARCHAR(255) | X | '0' | The person/process that last updated the record. |

2.2.103.6 List of keys of the table user_profile

| Code | Primary |
| --- | --- |
| USER_PROFILE_PK | X |

2.2.103.7 List of indexes of the table user_profile

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| USER_PROFILE_IDX | X | X |  | user_profile |
| USER_PROFILE_IAM_USER_UNQ | X |  |  | user_profile |

2.2.104 Table vocabulary

2.2.104.1 Card of table vocabulary

| Code | VOCABULARY |
| --- | --- |
| Comment | Table that holds vocabularies related to a vocabulary_type |

2.2.104.2 Check constraint name of the table vocabulary

CKT_VOCABULARY

2.2.104.3 List of outgoing references of the table vocabulary

| Code | Parent Table | Foreign Key Columns |
| --- | --- | --- |
| FK_VOC_TYPE__VOC | vocabulary_type | fk_vocabulary_type_sid |

2.2.104.4 List of diagrams containing the table vocabulary

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.104.5 List of columns of the table vocabulary

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('vocabulary_seq') | The surrogate key |
| FK_VOCABULARY_TYPE_SID | INT8 | X |  | foreign key to the vocabulary_type table |
| CODE | VARCHAR(255) |  |  | The code of the concept |
| NAME | VARCHAR(255) |  |  | the name of the concept |
| COLOR | VARCHAR(30) |  |  | The color that the concept is depicted |
| ALT_COLOR | VARCHAR(30) |  |  | The alternative color that the concept is depicted |
| ICON | VARCHAR(100) |  |  | the icon used for the concept |
| TEMPLATE | VARCHAR(255) |  |  | the template used for the concept |
| DESCRIPTION | VARCHAR(255) |  |  | the description of the concept |
| SEVERITY | VARCHAR(20) |  |  | the severity of the concept |
| VALUE | VARCHAR(20) |  |  | The value of the vocabulary record. |

2.2.104.6 List of keys of the table vocabulary

| Code | Primary |
| --- | --- |
| VOCABULARY_PK | X |

2.2.104.7 List of indexes of the table vocabulary

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| VOCABULARY_IDX | X | X |  | vocabulary |
| VOC_TYPE__VOC_IDX |  |  | X | vocabulary |
| VOC_VOC_TYPE__CODE | X |  |  | vocabulary |

2.2.105 Table vocabulary_type

2.2.105.1 Card of table vocabulary_type

| Code | VOCABULARY_TYPE |
| --- | --- |
| Comment | Table that holds a list of vocabulary types |

2.2.105.2 Check constraint name of the table vocabulary_type

CKT_VOCABULARY_TYPE

2.2.105.3 List of incoming references of the table vocabulary_type

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| FK_VOC_TYPE__VOC | vocabulary | fk_vocabulary_type_sid |

2.2.105.4 List of diagrams containing the table vocabulary_type

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.2.105.5 List of columns of the table vocabulary_type

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | INT8 | X | nextval('vocabulary_type_seq') | The surrogate key |
| TYPE | VARCHAR(255) | X |  | The type of the vocabulary. Possible values: NOTIFICATION_SEVERITIES("NotificationSeverities"), IMPORTANCE("importance"), COLORS("colors"), DOCUMENT_STATUSES("documentstatuses"), NOTIFICATION_TYPES("notificationtypes"), NOTIFICATION_READ_STATUSES("NotificationReadStatuses"), SUPPORT_TICKET_TYPES("supportTicketTypes"), AUDIT_ACTION_TYPES("AuditActionTypes"), AUDITED_OBJECT_TYPES("AuditedObjectTypes"), AUDIT_COMPONENT_TYPES("AuditComponentTypes"), AUDIT_CATEGORY_TYPES("AuditCategoryTypes"), AUDIT_EVENT_TYPES("AuditEventTypes"), TECHNICAL_LOG_LEVELS("TechnicalLogLevels"), RESOURCE_TYPES("ResourceTypes"), RESOURCES_STATUS_TYPES("ResourceStatusTypes"), BMP_VALIDATION_MODES("BMPValidationModes"), X002_REASONS_FOR_REQUEST("X002ReasonsForRequest"), YES1NO2("Yes1No2"), LANGUAGES("Languages"), COUNTRIES("Countries"), NUMBER_FORMATS("NumberFormats"), DATE_FORMATS("DateFormats"), TIME_FORMATS("TimeFormats"), CURRENCIES("Currencies"), TIMEZONES("TimeZones"), BEXCEPTION_TYPES("bexceptiontypes"), BUSINESS_EXCEPTION_TYPES("BusinessExceptionTypes"), CRITICALITY("criticality"), CASESTATUSES("casestatuses"), TIME_INTERVALS("timeIntervals"), SUPPORT_TICKET_PRIORITIES("supportTicketPriorities"), AUDIT_OUTCOME_TYPES("AuditOutcomeTypes"), AUDIT_PARTICIPANT_TYPES("AuditParticipantTypes"), AUDIT_PARTICIPANT_ROLES("AuditParticipantRoles"), SED_VALIDATION_MODES("SEDValidationModes"), X001_REASONS_FOR_CLOSING("X001ReasonsForClosing"), X004_DECISIONS("X004Decisions"), X009_URGENCY("X009Urgency"), NOTIFICATION_STATUSES("NotificationStatuses"), RESOURCE_CHANGE_TYPES("ResourceChangeTypes"), X001_CLOSE_TYPES("X001CloseTypes"), AUTHENTICATION_CHANNELS("AuthenticationChannels"), TECHNICAL_LOG_TYPES("TechnicalLogTypes"); |

2.2.105.6 List of keys of the table vocabulary_type

| Code | Primary |
| --- | --- |
| VOCABULARY_TYPE_PK | X |

2.2.105.7 List of indexes of the table vocabulary_type

| Code | Unique | Primary | Foreign Key | Table |
| --- | --- | --- | --- | --- |
| VOCABULARY_TYPE_IDX | X | X |  | vocabulary_type |
| VOCABULARY_TYPE_TYPE_UNQ | X |  |  | vocabulary_type |

### 2.3 List of references

| *Code* | *Parent Table* | *Child Table* | *Foreign Key Columns* |
| --- | --- | --- | --- |
| FK_ACTION__CASE | rina_case | action | fk_case_sid |
| FK_ACTION__DOC_TYPE_VER | document_type_version | action | fk_doc_type_version_sid |
| FK_ACTION__DOCUMENT | document | action | fk_document_sid |
| FK_ACTION__P_DOCUMENT | document | action | fk_parent_document_sid |
| FK_ACTION_TAG__ACTION | action | action_tag | fk_action_sid |
| FK_ACTIVITY__CASE | rina_case | activity | fk_case_sid |
| FK_ACTIVITY__PARENT | activity | activity | fk_parent_sid |
| FK_AS_PL_TGT__AS_PL_ASS_PL_TGT | assignment_policy_target | ass_pol_ass_pol_target | fk_target_sid |
| FK_ASS_POL__ASS_POL_ASS_POL_TGT | assignment_policy | ass_pol_ass_pol_target | fk_policy_sid |
| FK_ASS_POL_TRGT__TENANT | tenant | assignment_policy_target | fk_tenant_sid |
| FK_ASSIGN__CASE | rina_case | assignment | fk_case_sid |
| FK_ASSIGN__ROLE | role | assignment | fk_role_sid |
| FK_ASSIGN_GROUP__ASSIGN | assignment | assignment_group | fk_assignment_sid |
| FK_ASSIGN_GROUP__GROUP | iam_group | assignment_group | fk_group_sid |
| FK_ASSIGN_POL_RULE___ASSIGN_POL | assignment_policy | assignment_policy_rule | fk_assignment_policy_sid |
| FK_ASSIGN_REQUEST__CASE | rina_case | assignment_request | fk_case_sid |
| FK_ASSIGN_REQUEST__NOTIF | notification | assignment_request | fk_notification_sid |
| FK_ASSIGN_REQUEST__ROLE | role | assignment_request | fk_role_sid |
| FK_ASSIGN_USER__ASSIGN | assignment | assignment_user | fk_assignment_sid |
| FK_ASSIGN_USER__USER | iam_user | assignment_user | fk_user_sid |
| FK_ASSIGNED_BUC__ORG | organisation | assigned_buc | fk_org_sid |
| FK_ASSIGNED_BUC__PROCESS_DEF | process_def | assigned_buc | fk_process_def_sid |
| FK_ASSIGNMENT_POL__CHILD | assignment_policy | assignment_policy_policy | fk_policy_child_sid |
| FK_ASSIGNMENT_POL__PARENT | assignment_policy | assignment_policy_policy | fk_policy_parent_sid |
| FK_ASSIGNMENT_POL__TENANT | tenant | assignment_policy | fk_tenant_sid |
| FK_AUDIT_OBJECT__AUDIT_EVENT | audit_event | audit_object | fk_audit_event_sid |
| FK_AUDIT_PART__AUDIT_EVENT | audit_event | audit_participant | fk_audit_event_sid |
| FK_BUSINESS_EXC__DOC | document | business_exception | fk_doc_sid |
| FK_BUSINESS_EXC__PEND_MSG | pending_message | business_exception | fk_pend_msg_sid |
| FK_CASE__PROC_DEF_VERSION | process_def_version | rina_case | fk_proc_def_version_sid |
| FK_CASE__TENANT | tenant | rina_case | fk_tenant_sid |
| FK_CASE_ATTACH__CASE | rina_case | case_attachment | fk_case_sid |
| FK_CASE_PARTICIPANT__CASE | rina_case | case_participant | fk_case_sid |
| FK_CASE_PARTICIPANT__ORG | organisation | case_participant | fk_org_sid |
| FK_CASE_PREFILL__RINA_CASE | rina_case | case_prefill | fk_case_sid |
| FK_CASE_PROPERTY__CASE | rina_case | case_property | fk_case_sid |
| FK_CASE_SUBJECT_ORG__CASE | rina_case | case_subject_org | fk_case_sid |
| FK_CASE_SUBJECT_ORG__ORG | organisation | case_subject_org | fk_org_sid |
| FK_CHECK_INSTANCE__CHECK_BUCKET | check_bucket | check_instance | fk_check_bucket_sid |
| FK_CHECK_INSTANCE__CHECK_DEF | check_definition | check_instance | fk_check_definition_sid |
| FK_COMMENT__CASE | rina_case | case_comment | fk_case_sid |
| FK_CONV_PARTICIPANT__CONV | document_conversation | conv_participant | fk_conv_sid |
| FK_CONV_PARTICIPANT__ORG | organisation | conv_participant | fk_org_sid |
| FK_DOC__DOC_BVERSION | document_bversion | document | fk_doc_bversion_sid |
| FK_DOC__DOC_TYPE_VERSION | document_type_version | document | fk_doc_type_version_sid |
| FK_DOC_ATTACH__DOC | document | document_attachment | fk_doc_sid |
| FK_DOC_BV_SUBDOC_BV__DOC_BV | document_bversion | doc_bversion_subdoc_bversion | fk_doc_bversion_sid |
| FK_DOC_BV_SUBDOC_BV__SUBDOC_BV | subdocument_bversion | doc_bversion_subdoc_bversion | fk_subdoc_bversion_sid |
| FK_DOC_BVERSION__DOC | document | document_bversion | fk_doc_sid |
| FK_DOC_BVERSION__DOC_CONTENT | document_content | document_bversion | fk_doc_content_sid |
| FK_DOC_BVERSION_ATT__DOC_ATT | document_attachment | doc_bversion_attachment | fk_doc_attachment_sid |
| FK_DOC_BVERSION_ATT__DOC_BVERS | document_bversion | doc_bversion_attachment | fk_doc_bversion_sid |
| FK_DOC_COMMENT__DOC | document | document_comment | fk_doc_sid |
| FK_DOC_CONTENT__DOC | document | document_content | fk_doc_sid |
| FK_DOC_CONV__DOC | document | document_conversation | fk_doc_sid |
| FK_DOC_CONV__DOC_BVERSION | document_bversion | document_conversation | fk_doc_bversion_sid |
| FK_DOC_HIS__CASE | rina_case | document_history | fk_case_sid |
| FK_DOC_HIS__DOC | document | document_history | fk_doc_sid |
| FK_DOC_HIS__DOC_BVERSION | document_bversion | document_history | fk_doc_bversion_sid |
| FK_DOC_HIS__DOC_TYPE_VERSION | document_type_version | document_history | fk_doc_type_version_sid |
| FK_DOC_THUMB__DOC_BVER | document_bversion | document_thumbnail | fk_doc_bversion_sid |
| FK_DOC_TYPE__DOC_TYPE_VERSION | document_type | document_type_version | fk_doc_type_sid |
| FK_DOC_TYPE__PROC_DEF_VERSION | process_def_version | document_type | fk_proc_def_version_sid |
| FK_DOCUMENT__CASE | rina_case | document | fk_case_sid |
| FK_DOCUMENT__PARENT | document | document | fk_parent_sid |
| FK_FIELD__FIELD_CHOOSER | field_chooser | field | fk_field_chooser_sid |
| FK_FIELD_CHOOSER__PROCESS_DEF | process_def | field_chooser | FK_PROCESS_DEF_SID |
| FK_FIELD_CHOOSER__USER | iam_user | field_chooser | FK_USER_SID |
| FK_GLBL_PARAM__GLBL_PARAM_GRP | global_param_group | global_param | fk_global_param_group_sid |
| FK_GROUP__ORIGIN | iam_origin | iam_group | fk_origin_sid |
| FK_IAM_GROUP__IAM_GROUP | iam_group | iam_group | fk_parent_sid |
| FK_IAM_GROUP__TENANT | tenant | iam_group | fk_tenant_sid |
| FK_IAM_USER__SEARCH_DEF | iam_user | search_definition | fk_iam_user_sid |
| FK_IAM_USER__TENANT | tenant | iam_user | fk_tenant_sid |
| FK_IAM_USERGROUP__GROUP | iam_group | iam_user_group | fk_group_sid |
| FK_IAM_USERGROUP__USER | iam_user | iam_user_group | fk_user_sid |
| FK_LISTENER__SUBSCRIPTION | nie_subscription | nie_listener | fk_nie_subscription_sid |
| FK_NIE_EVENT__DOC_TYPE | document_type | nie_event | fk_doc_type_sid |
| FK_NIE_EVENT__PROC_DEF_VERSION | process_def_version | nie_event | fk_process_def_version_sid |
| FK_NOTIF__DOC_TYPE | document_type | notification | fk_document_type_sid |
| FK_NOTIF__IAM_USER | iam_user | notification | fk_creator_sid |
| FK_NOTIF_ALARM__CASE | rina_case | notification_alarm | fk_case_sid |
| FK_NOTIF_USER__NOTIF | notification | notification_user | fk_notification_sid |
| FK_NOTIF_USER__USER | iam_user | notification_user | fk_user_sid |
| FK_NOTIFICATION__DOCUMENT | document | notification | fk_document_sid |
| FK_NOTIFICATION__RINA_CASE | rina_case | notification | fk_case_sid |
| FK_NOTIFICATION_REC__ORG | organisation | notification | fk_receiver_org_sid |
| FK_NOTIFICATION_SDR__ORG | organisation | notification | fk_sender_org_sid |
| FK_ORG_CONTACT_METHOD__ORG | organisation | org_contact_method | fk_org_sid |
| FK_ORIGIN__USER | iam_origin | iam_user | fk_origin_sid |
| FK_PEND_ATTACH__PEND_MSG | pending_message | pending_attachment | fk_pend_msg_sid |
| FK_PEND_MSG__CASE | rina_case | pending_message | fk_case_sid |
| FK_PEND_MSG__PROC_DEF_VER | process_def_version | pending_message | fk_proc_def_version_sid |
| FK_PEND_MSG_REC__ORGANISATION | organisation | pending_message | fk_receiver_org_sid |
| FK_PEND_MSG_SDR__ORGANISATION | organisation | pending_message | fk_sender_org_sid |
| FK_POLICY__PROCESS_DEF | process_def | policy | fk_process_def_sid |
| FK_POLICY__SECTOR | sector | policy | fk_sector_sid |
| FK_POLICY__TENANT | tenant | policy | fk_tenant_sid |
| FK_PROC_DEF__PROC_DEF_VERSION | process_def | process_def_version | fk_proc_def_sid |
| FK_PROCESS_DEF__SECTOR | sector | process_def | fk_sector_sid |
| FK_RULE_COUN__ASSIGN_POL_RULE | assignment_policy_rule | rule_country | fk_rule_sid |
| FK_RULE_CREATOR_GROUP__GROUP | iam_group | rule_creator_group | fk_group_sid |
| FK_RULE_CREATOR_GROUP__RULE | assignment_policy_rule | rule_creator_group | fk_rule_sid |
| FK_RULE_CREATOR_USER__RULE | assignment_policy_rule | rule_creator_user | fk_rule_sid |
| FK_RULE_CREATOR_USER__USER | iam_user | rule_creator_user | fk_user_sid |
| FK_RULE_GROUP__GROUP | iam_group | rule_group | fk_group_sid |
| FK_RULE_GROUP__RULE | assignment_policy_rule | rule_group | fk_rule_sid |
| FK_RULE_ORG__ORG | organisation | rule_organisation | fk_org_sid |
| FK_RULE_ORG__RULE | assignment_policy_rule | rule_organisation | fk_rule_sid |
| FK_RULE_PROCESS__PROCESS | process_def | rule_process | fk_process_sid |
| FK_RULE_PROCESS__RULE | assignment_policy_rule | rule_process | fk_rule_sid |
| FK_RULE_ROLE__ROLE | role | rule_role | fk_role_sid |
| FK_RULE_ROLE__RULE | assignment_policy_rule | rule_role | fk_rule_sid |
| FK_RULE_SECTOR__ASSIGN_POL_RUL | assignment_policy_rule | rule_sector | fk_rule_sid |
| FK_RULE_SECTOR__SECTOR | sector | rule_sector | fk_sector_sid |
| FK_RULE_USER__ASSIGN_POL_RULE | assignment_policy_rule | rule_user | fk_rule_sid |
| FK_RULE_USER__USER | iam_user | rule_user | fk_user_sid |
| FK_SEARCH_DEF_GROUP__GROUP | iam_group | search_def_group | fk_iam_group_sid |
| FK_SEARCH_DEF_GROUP__SEARCH_DEF | search_definition | search_def_group | fk_search_definition_sid |
| FK_SEARCH_DEF_ORG__ORG | organisation | search_def_org | fk_organisation_sid |
| FK_SEARCH_DEF_ORG__SEARCH_DEF | search_definition | search_def_org | fk_search_definition_sid |
| FK_SEARCH_DEF_USER__SEARCH_DEF | search_definition | search_def_user | fk_search_definition_sid |
| FK_SEARCH_DEF_USER__USER | iam_user | search_def_user | fk_iam_user_sid |
| FK_SIGNATURE__MESSAGE | user_message | signature | fk_message_sid |
| FK_SRCH_DEF_PROC_DEF__PROC_DEF | process_def | search_def_proc_def | fk_process_definition_sid |
| FK_SRCH_DEF_PROC_DEF__SRCH_DEF | search_definition | search_def_proc_def | fk_search_definition_sid |
| FK_SUBDOC__DOC | document | subdocument | fk_document_sid |
| FK_SUBDOC__RINA_CASE | rina_case | subdocument | fk_case_sid |
| FK_SUBDOC__SUBDOC_BVERSION | subdocument_bversion | subdocument | fk_subdoc_bversion_sid |
| FK_SUBDOC_ATTACH__SUBDOC | subdocument | subdocument_attachment | fk_subdoc_sid |
| FK_SUBDOC_BVER__SUBDOC_CONTENT | subdocument_content | subdocument_bversion | fk_subdoc_content_sid |
| FK_SUBDOC_BVER_ATT__SUBDOC_ATT | subdocument_attachment | subdoc_bversion_attachment | fk_subdoc_attachment_sid |
| FK_SUBDOC_BVER_ATT__SUBDOC_BVER | subdocument_bversion | subdoc_bversion_attachment | fk_subdoc_bversion_sid |
| FK_SUBDOC_BVERSION__SUBDOC | subdocument | subdocument_bversion | fk_subdoc_sid |
| FK_SUBDOC_CONTENT_SUBDOC | subdocument | subdocument_content | fk_subdoc_sid |
| FK_SUBDOC_HIS__SUBDOC | subdocument | subdocument_history | fk_subdoc_sid |
| FK_SUBDOC_HIS__SUBDOC_BVERSION | subdocument_bversion | subdocument_history | fk_subdoc_bversion_sid |
| FK_SUBDOC_PREFILL__SUBDOC | subdocument | subdocument_prefill | fk_subdoc_sid |
| FK_SUBSCRBR__DOC_TYPE | document_type | nie_subscriber | fk_document_type_sid |
| FK_SUBSCRBR__PROCESS_DEF_VER | process_def_version | nie_subscriber | fk_process_def_version_sid |
| FK_SUBSCRIBER__SUBSCRIPTION | nie_subscription | nie_subscriber | fk_nie_subscription_sid |
| FK_TENANT__ORGANISATION | organisation | tenant | fk_org_sid |
| FK_TENANT_PARAM__TENANT | tenant | tenant_param | fk_tenant_sid |
| FK_TENANT_PARAM_GROUP___TENANT | tenant | tenant_param_group | fk_tenant_sid |
| FK_TRANSPOS__DOC_TYPE_VERSION | document_type_version | transposition | fk_doc_type_version_sid |
| FK_TRANSPOS__PROC_DEF_VERSION | process_def_version | transposition | fk_proc_def_version_sid |
| FK_USER_GROUP__ROLE | role | iam_user_group | fk_role_sid |
| FK_USER_MSG__DOC_CONV | document_conversation | user_message | fk_doc_conv_sid |
| FK_USER_MSG__RECEIVER | organisation | user_message | fk_receiver_sid |
| FK_USER_MSG__SENDER | organisation | user_message | fk_sender_sid |
| FK_USER_PROFILE__PROCESS_DEF | process_def | user_profile | fk_proc_def_sid |
| FK_USER_PROFILE__USER | iam_user | user_profile | fk_user_sid |
| FK_USR_MSG_RES__USR_MSG | user_message | user_message_response | fk_message_sid |
| FK_VOC_TYPE__VOC | vocabulary_type | vocabulary | fk_vocabulary_type_sid |
| TENANT_PARAM__TENANT_PARAM_GRP | tenant_param_group | tenant_param | fk_tenant_param_group_sid |

### 2.4 List of views

| *Code* |
| --- |
| V_AUDIT_SEARCH |
| V_BUSINESS_EX_SEARCH |
| V_CASE_SEARCH |
| V_IAM_USER_SEARCH |
| V_ORGANISATION_SEARCH |
| V_SUBDOCUMENTS_SEARCH |

2.4.1 View v_audit_search

2.4.1.1 Card of view v_audit_search

| Name | v_audit_search |
| --- | --- |
| Code | V_AUDIT_SEARCH |

2.4.1.2 SQL query of the view v_audit_search

SELECT

audit_sid,

audit_id,

username,

net_location_machine,

net_location_ip,

outcome_type,

outcome_details,

audit_obj_details,

to_tsvector( audit_sid || ' ' || audit_id || ' ' || username || ' ' || net_location_machine || ' ' || net_location_ip || ' ' || outcome_type || ' ' || outcome_details || ' ' || audit_obj_details) AS tsvector

FROM

(

SELECT

ae.sid AS audit_sid,

COALESCE(ae.id, '') AS audit_id,

COALESCE(ae.created_by, '') AS username,

COALESCE(ae.net_location_machine, '') AS net_location_machine,

COALESCE(ae.net_location_ip, '') AS net_location_ip,

COALESCE(ae.outcome_type, '') AS outcome_type,

COALESCE(ae.outcome_details,'') AS outcome_details,

COALESCE(ae.created_by, '') AS created_by,

COALESCE(ao.details,'') AS audit_obj_details

FROM audit_event ae

LEFT JOIN audit_object ao ON ae.sid=ao.fk_audit_event_sid

) result

;

2.4.1.3 List of tables of the view v_audit_search

| Name | Code |
| --- | --- |
| audit_object | AUDIT_OBJECT |

2.4.1.4 List of diagrams containing the view v_audit_search

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.4.1.5 List of columns of the view v_audit_search

| Name | Code | Data Type |
| --- | --- | --- |
| audit_sid | AUDIT_SID |  |
| audit_id | AUDIT_ID |  |
| username | USERNAME |  |
| NET_LOCATION_MACHINE | NET_LOCATION_MACHINE |  |
| net_location_ip | NET_LOCATION_IP |  |
| outcome_type | OUTCOME_TYPE |  |
| outcome_details | OUTCOME_DETAILS |  |
| audit_obj_details | AUDIT_OBJ_DETAILS |  |
| TSVECTOR | TSVECTOR |  |

2.4.2 View v_business_ex_search

2.4.2.1 Card of view v_business_ex_search

| Name | v_business_ex_search |
| --- | --- |
| Code | V_BUSINESS_EX_SEARCH |

2.4.2.2 SQL query of the view v_business_ex_search

SELECT business_ex_sid, pend_msg_sid, business_ex_id, reason, pend_msg_id, sbdh, content_location, action_type, international_case_id,

is_protected_person, should_notify, is_processed, problem, cause,

to_tsvector(business_ex_id || ' ' || reason || ' ' || pend_msg_id || ' ' || sbdh || ' ' || content_location || ' ' || action_type ||

' ' ||international_case_id || ' ' ||is_protected_person || ' ' || should_notify || ' ' ||is_processed ||

' ' || problem || ' ' ||cause) AS tsvector

FROM

(

SELECT be.sid AS business_ex_sid, pm.sid AS pend_msg_sid,

COALESCE(be.id, '') AS business_ex_id, COALESCE(be.reason, '') AS reason, COALESCE(pm.id, '') AS pend_msg_id,

COALESCE(pm.sbdh, '') AS sbdh, COALESCE(pm.content_location, '') AS content_location, pm.is_protected_person,

COALESCE(pm.action_type,'') AS action_type, COALESCE(pm.international_case_id, '') AS international_case_id,

pm.should_notify, pm.is_processed, COALESCE(pm.problem,'') AS problem, COALESCE(pm.cause,'') as cause

FROM pending_message pm

LEFT JOIN business_exception be ON pm.sid=be.fk_pend_msg_sid

) result

;

2.4.2.3 List of tables of the view v_business_ex_search

| Name | Code |
| --- | --- |
| business_exception | BUSINESS_EXCEPTION |

2.4.2.4 List of diagrams containing the view v_business_ex_search

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.4.2.5 List of columns of the view v_business_ex_search

| Name | Code | Data Type |
| --- | --- | --- |
| business_ex_sid | BUSINESS_EX_SID |  |
| pend_msg_sid | PEND_MSG_SID |  |
| business_ex_id | BUSINESS_EX_ID |  |
| reason | REASON | VARCHAR(255) |
| pend_msg_id | PEND_MSG_ID |  |
| sbdh | SBDH | TEXT |
| content_location | CONTENT_LOCATION | VARCHAR(255) |
| action_type | ACTION_TYPE | VARCHAR(255) |
| international_case_id | INTERNATIONAL_CASE_ID | VARCHAR(255) |
| is_protected_person | IS_PROTECTED_PERSON | BOOL |
| should_notify | SHOULD_NOTIFY | BOOL |
| is_processed | IS_PROCESSED | BOOL |
| problem | PROBLEM | VARCHAR(255) |
| cause | CAUSE | VARCHAR(255) |
| TSVECTOR | TSVECTOR |  |

2.4.3 View v_case_search

2.4.3.1 Card of view v_case_search

| Name | v_case_search |
| --- | --- |
| Code | V_CASE_SEARCH |

2.4.3.2 SQL query of the view v_case_search

SELECT rc.sid as fk_case_sid, rc.id as case_id, rc.international_id as case_int_id, rc.status as case_status, pd.id as buc_type, pd.name as buc_name,

COALESCE(agg_preffils, '') as case_agg_search,

to_tsvector(rc.id::text || ' ' || COALESCE(agg_preffils, '') || ' ' || rc.status::text || ' ' || pd.id::text || ' ' || pd.name::text || ' ' || rc.international_id::text ) as tsvector

from rina_case rc

JOIN process_def_version pdv ON rc.fk_proc_def_version_sid=pdv.sid

JOIN process_def pd ON pdv.fk_proc_def_sid=pd.sid

LEFT JOIN ( select cp.fk_case_sid, string_agg(cp.value::text, ' ') as agg_preffils

from case_prefill cp where cp.prefill_group = 'SEARCH_METADATA' group by fk_case_sid ) pivot on rc.sid = pivot.fk_case_sid;

2.4.3.3 List of tables of the view v_case_search

| Name | Code |
| --- | --- |
| process_def | PROCESS_DEF |
| process_def_version | PROCESS_DEF_VERSION |
| rina_case | RINA_CASE |

2.4.3.4 List of diagrams containing the view v_case_search

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.4.3.5 List of columns of the view v_case_search

| Name | Code | Data Type |
| --- | --- | --- |
| sid | FK_CASE_SID | INT8 |
| id | CASE_ID | VARCHAR(255) |
| international_id | CASE_INT_ID | VARCHAR(255) |
| status | CASE_STATUS | VARCHAR(10) |
| id | BUC_TYPE | VARCHAR(255) |
| name | BUC_NAME | VARCHAR(255) |
| CASE_AGG_SEARCH | CASE_AGG_SEARCH |  |
| TSVECTOR | TSVECTOR |  |

2.4.4 View v_iam_user_search

2.4.4.1 Card of view v_iam_user_search

| Name | v_iam_user_search |
| --- | --- |
| Code | V_IAM_USER_SEARCH |

2.4.4.2 SQL query of the view v_iam_user_search

SELECT user_sid, username, first_name, last_name, middle_names, email, phone_number,

to_tsvector( user_sid || ' ' || username || ' ' || first_name || ' ' || last_name || ' ' || middle_names || ' ' || email || ' ' || phone_number) AS tsvector

FROM

(

SELECT u.sid AS user_sid, COALESCE(u.username, '') AS username, COALESCE(u.first_name, '') AS first_name,

COALESCE(u.last_name, '') AS last_name, COALESCE(u.middle_names, '') AS middle_names, COALESCE(u.email, '') AS email,

COALESCE(u.phone_number, '') AS phone_number

FROM iam_user u

) result

;

2.4.4.3 List of diagrams containing the view v_iam_user_search

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.4.4.4 List of columns of the view v_iam_user_search

| Name | Code | Data Type |
| --- | --- | --- |
| user_sid | USER_SID |  |
| username | USERNAME |  |
| first_name | FIRST_NAME |  |
| last_name | LAST_NAME |  |
| middle_names | MIDDLE_NAMES |  |
| email | EMAIL |  |
| phone_number | PHONE_NUMBER |  |
| tsvector | TSVECTOR |  |

2.4.5 View v_organisation_search

2.4.5.1 Card of view v_organisation_search

| Name | v_organisation_search |
| --- | --- |
| Code | V_ORGANISATION_SEARCH |

2.4.5.2 SQL query of the view v_organisation_search

SELECT result.sid,

result.digit_id,

result.org_id,

result.org_name,

result.acronym,

result.ap_id,

result.ap_name,

to_tsvector(((((((((((result.sid || ' '::text) || digit_id::text) || result.org_id::text) || ' '::text) || result.org_name::text) || ' '::text) || result.acronym::text) || ' '::text) || result.ap_id::text) || ' '::text) || result.ap_name::text) AS tsvector

FROM ( SELECT o.sid,

(SELECT regexp_replace(COALESCE(o.id, ''::character varying), '\[^0-9\]+', '', 'g') AS digit_id),

o.id AS org_id,

COALESCE(o.name, ''::character varying) AS org_name,

COALESCE(o.acronym, ''::character varying) AS acronym,

COALESCE(o.ap_id, ''::character varying) AS ap_id,

COALESCE(o.ap_name, ''::character varying) AS ap_name

FROM rina.organisation o)

result;

2.4.5.3 List of diagrams containing the view v_organisation_search

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.4.5.4 List of columns of the view v_organisation_search

| Name | Code | Data Type |
| --- | --- | --- |
| SID | SID |  |
| DIGIT_ID | DIGIT_ID |  |
| ORG_ID | ORG_ID |  |
| ORG_NAME | ORG_NAME |  |
| ACRONYM | ACRONYM |  |
| AP_ID | AP_ID |  |
| AP_NAME | AP_NAME |  |
| TSVECTOR | TSVECTOR |  |

2.4.6 View v_subdocuments_search

2.4.6.1 Card of view v_subdocuments_search

| Name | v_subdocuments_search |
| --- | --- |
| Code | V_SUBDOCUMENTS_SEARCH |

2.4.6.2 SQL query of the view v_subdocuments_search

SELECT case_sid, subdoc_sid, field_1, field_2, field_3, field_4,

to_tsvector( case_sid || ' ' || subdoc_sid || ' ' || field_1 || ' ' || field_2 || ' ' || field_3 || ' ' || field_4 ) AS tsvector

FROM

(

SELECT pivot.fk_subdoc_sid AS subdoc_sid, COALESCE(pivot.field_1, '') AS field_1, COALESCE(pivot.field_2, '') as field_2,

COALESCE(pivot.field_3, '') as field_3, COALESCE(pivot.field_4, '') as field_4, rc.sid as case_sid

FROM crosstab( 'select sp.fk_subdoc_sid, sp.key, sp.value

from rina.subdocument_prefill sp

where sp.prefill_group=''SEARCH_METADATA'' ORDER BY 1,2')

AS pivot(fk_subdoc_sid BIGINT, field_1 TEXT, field_2 TEXT, field_3 TEXT, field_4 TEXT)

JOIN subdocument sd ON sd.sid = pivot.fk_subdoc_sid

JOIN rina_case rc ON rc.sid = sd.fk_case_sid

) result

;

2.4.6.3 List of tables of the view v_subdocuments_search

| Name | Code |
| --- | --- |
| rina_case | RINA_CASE |
| subdocument | SUBDOCUMENT |

2.4.6.4 List of diagrams containing the view v_subdocuments_search

| Name | Code |
| --- | --- |
| EESSII RINA physical diagram | EESSII_RINA_PHYSICAL_DIAGRAM |

2.4.6.5 List of columns of the view v_subdocuments_search

| Name | Code | Data Type |
| --- | --- | --- |
| case_sid | CASE_SID |  |
| subdoc_sid | SUBDOC_SID |  |
| field_1 | FIELD_1 |  |
| field_2 | FIELD_2 |  |
| field_3 | FIELD_3 |  |
| field_4 | FIELD_4 |  |
| tsvector | TSVECTOR |  |

### 2.5 List of sequences

| *Code* |
| --- |
| ACTION_SEQ |
| ACTION_TAG_SEQ |
| ACTIVITY_SEQ |
| ACTOR_SEQ |
| ADMIN_NOTIFICATION_TYPE_SEQ |
| ALLOWED_MIME_TYPE_SEQ |
| APPLICATION_PROFILE_SEQ |
| ARCHIVING_VOLUME_SEQ |
| ARCHIVING_REPOSITORY_POLICY_SEQ |
| ASSIGNED_BUC_SEQ |
| ASSIGNMENT_POLICY_RULE_SEQ |
| ASSIGNMENT_POLICY_SEQ |
| ASSIGNMENT_POLICY_TARGET_SEQ |
| ASSIGNMENT_REQUEST_SEQ |
| ASSIGNMENT_SEQ |
| AUDIT_EVENT_SEQ |
| AUDIT_OBJECT_SEQ |
| AUDIT_PARTICIPANT_SEQ |
| BUSINESS_EXCEPTION_SEQ |
| BUSINESS_EXCEPTION_SETTINGS_SEQ |
| BUSINESS_KEY_SEQ |
| CASE_ATTACHMENT_SEQ |
| CASE_COMMENT_SEQ |
| CASE_ID_SEQ |
| CASE_PARTICIPANT_SEQ |
| CASE_PREFILL_SEQ |
| CASE_PROPERTY_SEQ |
| CASE_RETENTION_POLICY_SEQ |
| CASE_SEQ |
| CHECK_BUCKET_SEQ |
| CHECK_DEFINITION_SEQ |
| CHECK_INSTANCE_SEQ |
| CLUSTER_NODE_SEQ |
| CONV_PARTICIPANT_SEQ |
| DOC_ATTACHMENT_SEQ |
| DOC_COMMENT_SEQ |
| DOC_CONVERSATION_SEQ |
| DOC_THUMBNAIL_SEQ |
| DOC_TYPE_SEQ |
| DOC_TYPE_VERSION_SEQ |
| DOCUMENT_BVERSION_SEQ |
| DOCUMENT_CONTENT_SEQ |
| DOCUMENT_HISTORY_SEQ |
| DOCUMENT_SEQ |
| FIELD_CHOOSER_SEQ |
| FIELD_SEQ |
| GLOBAL_PARAM_GROUP_SEQ |
| GLOBAL_PARAM_SEQ |
| IAM_GROUP_SEQ |
| IAM_ORIGIN_SEQ |
| IAM_SETTINGS_SEQ |
| IAM_USER_GROUP_SEQ |
| IAM_USER_SEQ |
| MESSAGING_SETTINGS_SEQ |
| MSG_RETENTION_SETTINGS_SEQ |
| NIE_EVENT_SEQ |
| NIE_LISTENER_SEQ |
| NIE_NOTIFICATION_SEQ |
| NIE_SUBSCRIBER_SEQ |
| NIE_SUBSCRIPTION_SEQ |
| NIE_SUBSCRIPTION_TYPE_SEQ |
| NOTIFICATION_ALARM_SEQ |
| NOTIFICATION_SEQ |
| ORG_CONTACT_METHOD_SEQ |
| ORGANISATION_SEQ |
| PEND_ATTACHMENT_SEQ |
| PENDING_MESSAGE_SEQ |
| PENDING_SIGNATURE_SEQ |
| PENDING_STATUS_SEQ |
| PERSON_CONTACT_METHOD_SEQ |
| PERSON_PROPERTY_SEQ |
| PERSON_SEQ |
| POLICY_SEQ |
| PROCESS_DEF_SEQ |
| PROCESS_DEF_VERSION_SEQ |
| RESOURCE_SEQ |
| ROLE_SEQ |
| RULE_COUNTRY_SEQ |
| SEARCH_DEFINITION_SEQ |
| SECTOR_SEQ |
| SIGNATURE_SEQ |
| SUBDOC_ATTACHMENT_SEQ |
| SUBDOC_COMMENT_SEQ |
| SUBDOC_PREFILL_SEQ |
| SUBDOCUMENT_BVERSION_SEQ |
| SUBDOCUMENT_CONTENT_SEQ |
| SUBDOCUMENT_HISTORY_SEQ |
| SUBDOCUMENT_SEQ |
| SUPPORTED_LANGUAGE_SEQ |
| TENANT_PARAM_GROUP_SEQ |
| TENANT_PARAM_SEQ |
| TENANT_SEQ |
| TRANSLATION_SEQ |
| TRANSPOSITION_SEQ |
| USER_MESSAGE_RESPONSE_SEQ |
| USER_MSG_SEQ |
| USER_PROFILE_SEQ |
| VOCABULARY_SEQ |
| VOCABULARY_TYPE_SEQ |
