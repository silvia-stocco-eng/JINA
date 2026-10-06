---
unique-name: dbschemajina2026v2
display-name: DB schema JINA2026v2
category: GENERAL_DRAFT
description: Draft physical data model for PostgreSQL schema rina extracted from DBMind connection JINATEST. Section 2.5 Sequences updated with pg_attrdef verification results for subdocument_history, action_tag and search_definition SID columns provided by the user on 2026-07-27.
---

**JINA**

**Database Schema**

***Physical Data Model***


**Document Control Information**

| **Document Control** | Value |
| --- | --- |
| **Document Name** | DB schema JINA2026v2 |
| **Schema** | rina |
| **Database Type** | PostgreSQL |
| **DBMind Connection ID** | JINATEST |
| **Source URL** | jdbc:postgresql://10.72.122.68:5432/rina |
| **Generated On** | 2026-07-22 |
| **Document Status** | DRAFT |

**Table of Contents**

- [1 Introduction](#1-introduction)
- [2 Full model description](#2-full-model-description)
  - [2.1 Diagram DB schema JINA2026v2 physical diagram](#21-diagram-db-schema-jina2026v2-physical-diagram)
  - [2.2 List of tables](#22-list-of-tables)
  - [2.3 Views and materialized views](#23-views-and-materialized-views)
  - [2.4 Functions](#24-functions)
  - [2.5 Sequences](#25-sequences)

## 1 Introduction

### 1.1 Description

This document describes the physical data model of the PostgreSQL schema `rina` exposed by DBMind connection `JINATEST`. It documents 105 base tables, 7 standard views discovered through schema inspection, 2 additional materialized views found in `pg_catalog`, and 13 functions in the target schema. The structure follows the reference Physical Data Model template already stored in DocMind, adapted to the metadata that could be extracted automatically from PostgreSQL catalogs.

## 2 Full model description

### 2.1 Diagram DB schema JINA2026v2 physical diagram

```mermaid
erDiagram
    ACTION {
        bigint SID
        int VERSION
        bigint FK_CASE_SID
    }
    ACTION_TAG {
        bigint SID
        bigint FK_ACTION_SID
        string TYPE
    }
    ACTIVITY {
        bigint SID
        int VERSION
        bigint FK_CASE_SID
    }
    ADMIN_NOTIFICATION_TYPE {
        bigint SID
        int VERSION
        string NOTIFICATION_TYPE
    }
    ARCHIVING_VOLUME {
        bigint SID
        string ARCHIVING_VOLUME_ID
        string ARCHIVING_VOLUME
    }
    ASS_POL_ASS_POL_TARGET {
        bigint FK_POLICY_SID
        bigint FK_TARGET_SID
    }
    ASSIGNED_BUC {
        bigint SID
        int VERSION
        bigint FK_ORG_SID
    }
    ASSIGNMENT {
        bigint SID
        string ID
        bigint FK_CASE_SID
    }
    ASSIGNMENT_GROUP {
        bigint FK_ASSIGNMENT_SID
        bigint FK_GROUP_SID
    }
    ASSIGNMENT_POLICY {
        bigint SID
        int VERSION
        bigint FK_TENANT_SID
    }
    ASSIGNMENT_POLICY_POLICY {
        bigint FK_POLICY_PARENT_SID
        bigint FK_POLICY_CHILD_SID
    }
    ASSIGNMENT_POLICY_RULE {
        bigint SID
        string ID
        int VERSION
    }
    ASSIGNMENT_POLICY_TARGET {
        bigint SID
        bigint FK_TENANT_SID
        string TARGET
    }
    ASSIGNMENT_REQUEST {
        bigint SID
        bigint FK_CASE_SID
        bigint FK_ROLE_SID
    }
    ASSIGNMENT_USER {
        bigint FK_ASSIGNMENT_SID
        bigint FK_USER_SID
    }
    AUDIT_EVENT {
        bigint SID
        string ID
        string TENANT_ID
    }
    AUDIT_OBJECT {
        bigint SID
        bigint FK_AUDIT_EVENT_SID
        string ID
    }
    AUDIT_PARTICIPANT {
        bigint SID
        bigint FK_AUDIT_EVENT_SID
        string ID
    }
    BUSINESS_EXCEPTION {
        bigint SID
        bigint FK_DOC_SID
        bigint FK_PEND_MSG_SID
    }
    BUSINESS_EXCEPTION_SETTINGS {
        bigint SID
        string CAUSE
        int SETTING
    }
    BUSINESS_KEY {
        bigint SID
        string ALIAS
        string PASSWORD
    }
    CASE_ATTACHMENT {
        bigint SID
        int VERSION
        bigint FK_CASE_SID
    }
    CASE_COMMENT {
        bigint SID
        int VERSION
        bigint FK_CASE_SID
    }
    CASE_PARTICIPANT {
        bigint SID
        bigint FK_CASE_SID
        bigint FK_ORG_SID
    }
    CASE_PREFILL {
        bigint SID
        bigint FK_CASE_SID
        string PREFILL_GROUP
    }
    CASE_PROPERTY {
        bigint SID
        bigint FK_CASE_SID
        string KEY
    }
    CASE_SUBJECT_ORG {
        bigint FK_CASE_SID
        bigint FK_ORG_SID
    }
    CHECK_BUCKET {
        bigint SID
        string ID
        timestamp START_DATE
    }
    CHECK_DEFINITION {
        bigint SID
        string ID
        string CHECK_CATEGORY
    }
    CHECK_INSTANCE {
        bigint SID
        bigint FK_CHECK_DEFINITION_SID
        bigint FK_CHECK_BUCKET_SID
    }
    CLUSTER_NODE {
        bigint SID
        string NAME
        string PMODE_PATH
    }
    CONV_PARTICIPANT {
        bigint SID
        bigint FK_CONV_SID
        bigint FK_ORG_SID
    }
    DOC_BVERSION_ATTACHMENT {
        bigint FK_DOC_BVERSION_SID
        bigint FK_DOC_ATTACHMENT_SID
    }
    DOC_BVERSION_SUBDOC_BVERSION {
        bigint FK_DOC_BVERSION_SID
        bigint FK_SUBDOC_BVERSION_SID
    }
    DOCUMENT {
        bigint SID
        int VERSION
        bigint FK_CASE_SID
    }
    DOCUMENT_ATTACHMENT {
        bigint SID
        int VERSION
        bigint FK_DOC_SID
    }
    DOCUMENT_BVERSION {
        bigint SID
        bigint FK_DOC_SID
        bigint FK_DOC_CONTENT_SID
    }
    DOCUMENT_COMMENT {
        bigint SID
        int VERSION
        bigint FK_DOC_SID
    }
    DOCUMENT_CONTENT {
        bigint SID
        bigint FK_DOC_SID
        string CONTENT
    }
    DOCUMENT_CONVERSATION {
        bigint SID
        bigint FK_DOC_SID
        bigint FK_DOC_BVERSION_SID
    }
    DOCUMENT_HISTORY {
        bigint SID
        bigint FK_DOC_SID
        bigint FK_CASE_SID
    }
    DOCUMENT_THUMBNAIL {
        bigint SID
        bigint FK_DOC_BVERSION_SID
        string LANG
    }
    DOCUMENT_TYPE {
        bigint SID
        bigint FK_PROC_DEF_VERSION_SID
        string TYPE
    }
    DOCUMENT_TYPE_VERSION {
        bigint SID
        bigint FK_DOC_TYPE_SID
        string BVERSION
    }
    FIELD {
        bigint SID
        bigint FK_FIELD_CHOOSER_SID
        string ID
    }
    FIELD_CHOOSER {
        bigint SID
        bigint FK_USER_SID
        bigint FK_PROCESS_DEF_SID
    }
    GLOBAL_PARAM {
        bigint SID
        bigint FK_GLOBAL_PARAM_GROUP_SID
        string KEY
    }
    GLOBAL_PARAM_GROUP {
        bigint SID
        int VERSION
        string NAME
    }
    IAM_GROUP {
        bigint SID
        int VERSION
        bigint FK_ORIGIN_SID
    }
    IAM_ORIGIN {
        bigint SID
        string NAME
        string DESCRIPTION
    }
    IAM_USER {
        bigint SID
        int VERSION
        bigint FK_ORIGIN_SID
    }
    IAM_USER_GROUP {
        bigint SID
        bigint FK_USER_SID
        bigint FK_GROUP_SID
    }
    NIE_EVENT {
        bigint SID
        bigint FK_PROCESS_DEF_VERSION_SID
        bigint FK_DOC_TYPE_SID
    }
    NIE_LISTENER {
        bigint SID
        bigint FK_NIE_SUBSCRIPTION_SID
        string ID
    }
    NIE_SUBSCRIBER {
        bigint SID
        bigint FK_NIE_SUBSCRIPTION_SID
        bigint FK_PROCESS_DEF_VERSION_SID
    }
    NIE_SUBSCRIPTION {
        bigint SID
        string SUBSCRIPTION_NAME
        string ID
    }
    NOTIFICATION {
        bigint SID
        string ID
        int VERSION
    }
    NOTIFICATION_ALARM {
        bigint SID
        string ID
        bigint FK_CASE_SID
    }
    NOTIFICATION_USER {
        bigint FK_NOTIFICATION_SID
        bigint FK_USER_SID
    }
    ORG_CONTACT_METHOD {
        bigint SID
        bigint FK_ORG_SID
        string TYPE
    }
    ORGANISATION {
        bigint SID
        int VERSION
        string ID
    }
    PENDING_ATTACHMENT {
        bigint SID
        bigint FK_PEND_MSG_SID
        string MIME_TYPE
    }
    PENDING_MESSAGE {
        bigint SID
        string ID
        bigint FK_RECEIVER_ORG_SID
    }
    PENDING_SIGNATURE {
        bigint SID
        string ID
        string DIRECTION
    }
    PENDING_STATUS {
        bigint SID
        string ID
        string DIRECTION
    }
    POLICY {
        bigint SID
        bigint FK_TENANT_SID
        bigint FK_SECTOR_SID
    }
    PROCESS_DEF {
        bigint SID
        bigint FK_SECTOR_SID
        string ID
    }
    PROCESS_DEF_VERSION {
        bigint SID
        bigint FK_PROC_DEF_SID
        string BVERSION
    }
    RESOURCE {
        bigint SID
        string ID
        int VERSION
    }
    RINA_CASE {
        bigint SID
        int VERSION
        bigint FK_TENANT_SID
    }
    ROLE {
        bigint SID
        string NAME
    }
    RULE_COUNTRY {
        bigint SID
        bigint FK_RULE_SID
        string COUNTRY_CODE
    }
    RULE_CREATOR_GROUP {
        bigint FK_RULE_SID
        bigint FK_GROUP_SID
    }
    RULE_CREATOR_USER {
        bigint FK_RULE_SID
        bigint FK_USER_SID
    }
    RULE_GROUP {
        bigint FK_RULE_SID
        bigint FK_GROUP_SID
    }
    RULE_ORGANISATION {
        bigint FK_RULE_SID
        bigint FK_ORG_SID
    }
    RULE_PROCESS {
        bigint FK_RULE_SID
        bigint FK_PROCESS_SID
    }
    RULE_ROLE {
        bigint FK_RULE_SID
        bigint FK_ROLE_SID
    }
    RULE_SECTOR {
        bigint FK_RULE_SID
        bigint FK_SECTOR_SID
    }
    RULE_USER {
        bigint FK_RULE_SID
        bigint FK_USER_SID
    }
    SEARCH_DEF_GROUP {
        bigint FK_SEARCH_DEFINITION_SID
        bigint FK_IAM_GROUP_SID
    }
    SEARCH_DEF_ORG {
        bigint FK_SEARCH_DEFINITION_SID
        bigint FK_ORGANISATION_SID
    }
    SEARCH_DEF_PROC_DEF {
        bigint FK_SEARCH_DEFINITION_SID
        bigint FK_PROCESS_DEFINITION_SID
    }
    SEARCH_DEF_USER {
        bigint FK_IAM_USER_SID
        bigint FK_SEARCH_DEFINITION_SID
    }
    SEARCH_DEFINITION {
        bigint SID
        bigint FK_IAM_USER_SID
        string ID
    }
    SECTOR {
        bigint SID
        string NAME
    }
    SIGNATURE {
        bigint SID
        string ID
        bigint FK_MESSAGE_SID
    }
    SUBDOC_BVERSION_ATTACHMENT {
        bigint FK_SUBDOC_ATTACHMENT_SID
        bigint FK_SUBDOC_BVERSION_SID
    }
    SUBDOCUMENT {
        bigint SID
        int VERSION
        bigint FK_CASE_SID
    }
    SUBDOCUMENT_ATTACHMENT {
        bigint SID
        int VERSION
        bigint FK_SUBDOC_SID
    }
    SUBDOCUMENT_BVERSION {
        bigint SID
        bigint FK_SUBDOC_SID
        bigint FK_SUBDOC_CONTENT_SID
    }
    SUBDOCUMENT_CONTENT {
        bigint SID
        bigint FK_SUBDOC_SID
        string CONTENT
    }
    SUBDOCUMENT_HISTORY {
        bigint SID
        bigint FK_SUBDOC_SID
        bigint FK_DOC_SID
    }
    SUBDOCUMENT_PREFILL {
        bigint SID
        bigint FK_SUBDOC_SID
        string PREFILL_GROUP
    }
    SUPPORTED_LANGUAGE {
        bigint SID
        string LANG
    }
    TENANT {
        bigint SID
        int VERSION
        bigint FK_ORG_SID
    }
    TENANT_PARAM {
        bigint SID
        bigint FK_TENANT_SID
        bigint FK_TENANT_PARAM_GROUP_SID
    }
    TENANT_PARAM_GROUP {
        bigint SID
        int VERSION
        bigint FK_TENANT_SID
    }
    TRANSLATION {
        bigint SID
        string LANG
        string CONTENT
    }
    TRANSPOSITION {
        bigint SID
        bigint FK_PROC_DEF_VERSION_SID
        bigint FK_DOC_TYPE_VERSION_SID
    }
    USER_MESSAGE {
        bigint SID
        bigint FK_SENDER_SID
        bigint FK_RECEIVER_SID
    }
    USER_MESSAGE_RESPONSE {
        bigint SID
        bigint FK_MESSAGE_SID
        string ID
    }
    USER_PROFILE {
        bigint SID
        int VERSION
        bigint FK_USER_SID
    }
    VOCABULARY {
        bigint SID
        bigint FK_VOCABULARY_TYPE_SID
        string CODE
    }
    VOCABULARY_TYPE {
        bigint SID
        string TYPE
    }
    RINA_CASE ||--o{ ACTION : "fk_action__case"
    DOCUMENT_TYPE_VERSION ||--o{ ACTION : "fk_action__doc_type_ver"
    DOCUMENT ||--o{ ACTION : "fk_action__document"
    DOCUMENT ||--o{ ACTION : "fk_action__p_document"
    ACTION ||--o{ ACTION_TAG : "fk_action_tag__action"
    RINA_CASE ||--o{ ACTIVITY : "fk_activity__case"
    ACTIVITY ||--o{ ACTIVITY : "fk_activity__parent"
    ASSIGNMENT_POLICY_TARGET ||--o{ ASS_POL_ASS_POL_TARGET : "fk_as_pl_tgt__as_pl_ass_pl_tgt"
    ASSIGNMENT_POLICY ||--o{ ASS_POL_ASS_POL_TARGET : "fk_ass_pol__ass_pol_ass_pol_tgt"
    ORGANISATION ||--o{ ASSIGNED_BUC : "fk_assigned_buc__org"
    PROCESS_DEF ||--o{ ASSIGNED_BUC : "fk_assigned_buc__process_def"
    RINA_CASE ||--o{ ASSIGNMENT : "fk_assign__case"
    ROLE ||--o{ ASSIGNMENT : "fk_assign__role"
    ASSIGNMENT ||--o{ ASSIGNMENT_GROUP : "fk_assign_group__assign"
    IAM_GROUP ||--o{ ASSIGNMENT_GROUP : "fk_assign_group__group"
    TENANT ||--o{ ASSIGNMENT_POLICY : "fk_assignment_pol__tenant"
    ASSIGNMENT_POLICY ||--o{ ASSIGNMENT_POLICY_POLICY : "fk_assignment_pol__child"
    ASSIGNMENT_POLICY ||--o{ ASSIGNMENT_POLICY_POLICY : "fk_assignment_pol__parent"
    ASSIGNMENT_POLICY ||--o{ ASSIGNMENT_POLICY_RULE : "fk_assign_pol_rule___assign_pol"
    TENANT ||--o{ ASSIGNMENT_POLICY_TARGET : "fk_ass_pol_trgt__tenant"
    RINA_CASE ||--o{ ASSIGNMENT_REQUEST : "fk_assign_request__case"
    NOTIFICATION ||--o{ ASSIGNMENT_REQUEST : "fk_assign_request__notif"
    ROLE ||--o{ ASSIGNMENT_REQUEST : "fk_assign_request__role"
    ASSIGNMENT ||--o{ ASSIGNMENT_USER : "fk_assign_user__assign"
    IAM_USER ||--o{ ASSIGNMENT_USER : "fk_assign_user__user"
    AUDIT_EVENT ||--o{ AUDIT_OBJECT : "fk_audit_object__audit_event"
    AUDIT_EVENT ||--o{ AUDIT_PARTICIPANT : "fk_audit_part__audit_event"
    DOCUMENT ||--o{ BUSINESS_EXCEPTION : "fk_business_exc__doc"
    PENDING_MESSAGE ||--o{ BUSINESS_EXCEPTION : "fk_business_exc__pend_msg"
    RINA_CASE ||--o{ CASE_ATTACHMENT : "fk_case_attach__case"
    RINA_CASE ||--o{ CASE_COMMENT : "fk_comment__case"
    RINA_CASE ||--o{ CASE_PARTICIPANT : "fk_case_participant__case"
    ORGANISATION ||--o{ CASE_PARTICIPANT : "fk_case_participant__org"
    RINA_CASE ||--o{ CASE_PREFILL : "fk_case_prefill__rina_case"
    RINA_CASE ||--o{ CASE_PROPERTY : "fk_case_property__case"
    RINA_CASE ||--o{ CASE_SUBJECT_ORG : "fk_case_subject_org__case"
    ORGANISATION ||--o{ CASE_SUBJECT_ORG : "fk_case_subject_org__org"
    CHECK_BUCKET ||--o{ CHECK_INSTANCE : "fk_check_instance__check_bucket"
    CHECK_DEFINITION ||--o{ CHECK_INSTANCE : "fk_check_instance__check_def"
    DOCUMENT_CONVERSATION ||--o{ CONV_PARTICIPANT : "fk_conv_participant__conv"
    ORGANISATION ||--o{ CONV_PARTICIPANT : "fk_conv_participant__org"
    DOCUMENT_ATTACHMENT ||--o{ DOC_BVERSION_ATTACHMENT : "fk_doc_bversion_att__doc_att"
    DOCUMENT_BVERSION ||--o{ DOC_BVERSION_ATTACHMENT : "fk_doc_bversion_att__doc_bvers"
    DOCUMENT_BVERSION ||--o{ DOC_BVERSION_SUBDOC_BVERSION : "fk_doc_bv_subdoc_bv__doc_bv"
    SUBDOCUMENT_BVERSION ||--o{ DOC_BVERSION_SUBDOC_BVERSION : "fk_doc_bv_subdoc_bv__subdoc_bv"
    DOCUMENT_BVERSION ||--o{ DOCUMENT : "fk_doc__doc_bversion"
    DOCUMENT_TYPE_VERSION ||--o{ DOCUMENT : "fk_doc__doc_type_version"
    RINA_CASE ||--o{ DOCUMENT : "fk_document__case"
    DOCUMENT ||--o{ DOCUMENT : "fk_document__parent"
    DOCUMENT ||--o{ DOCUMENT_ATTACHMENT : "fk_doc_attach__doc"
    DOCUMENT ||--o{ DOCUMENT_BVERSION : "fk_doc_bversion__doc"
    DOCUMENT_CONTENT ||--o{ DOCUMENT_BVERSION : "fk_doc_bversion__doc_content"
    DOCUMENT ||--o{ DOCUMENT_COMMENT : "fk_doc_comment__doc"
    DOCUMENT ||--o{ DOCUMENT_CONTENT : "fk_doc_content__doc"
    DOCUMENT ||--o{ DOCUMENT_CONVERSATION : "fk_doc_conv__doc"
    DOCUMENT_BVERSION ||--o{ DOCUMENT_CONVERSATION : "fk_doc_conv__doc_bversion"
    RINA_CASE ||--o{ DOCUMENT_HISTORY : "fk_doc_his__case"
    DOCUMENT ||--o{ DOCUMENT_HISTORY : "fk_doc_his__doc"
    DOCUMENT_BVERSION ||--o{ DOCUMENT_HISTORY : "fk_doc_his__doc_bversion"
    DOCUMENT_TYPE_VERSION ||--o{ DOCUMENT_HISTORY : "fk_doc_his__doc_type_version"
    DOCUMENT_BVERSION ||--o{ DOCUMENT_THUMBNAIL : "fk_doc_thumb__doc_bver"
    PROCESS_DEF_VERSION ||--o{ DOCUMENT_TYPE : "fk_doc_type__proc_def_version"
    DOCUMENT_TYPE ||--o{ DOCUMENT_TYPE_VERSION : "fk_doc_type__doc_type_version"
    FIELD_CHOOSER ||--o{ FIELD : "fk_field__field_chooser"
    PROCESS_DEF ||--o{ FIELD_CHOOSER : "fk_field_chooser__process_def"
    IAM_USER ||--o{ FIELD_CHOOSER : "fk_field_chooser__user"
    GLOBAL_PARAM_GROUP ||--o{ GLOBAL_PARAM : "fk_glbl_param__glbl_param_grp"
    IAM_ORIGIN ||--o{ IAM_GROUP : "fk_group__origin"
    IAM_GROUP ||--o{ IAM_GROUP : "fk_iam_group__iam_group"
    TENANT ||--o{ IAM_GROUP : "fk_iam_group__tenant"
    TENANT ||--o{ IAM_USER : "fk_iam_user__tenant"
    IAM_ORIGIN ||--o{ IAM_USER : "fk_origin__user"
    IAM_GROUP ||--o{ IAM_USER_GROUP : "fk_iam_usergroup__group"
    IAM_USER ||--o{ IAM_USER_GROUP : "fk_iam_usergroup__user"
    ROLE ||--o{ IAM_USER_GROUP : "fk_user_group__role"
    DOCUMENT_TYPE ||--o{ NIE_EVENT : "fk_nie_event__doc_type"
    PROCESS_DEF_VERSION ||--o{ NIE_EVENT : "fk_nie_event__proc_def_version"
    NIE_SUBSCRIPTION ||--o{ NIE_LISTENER : "fk_listener__subscription"
    DOCUMENT_TYPE ||--o{ NIE_SUBSCRIBER : "fk_nie_subs_fk_subscr_document"
    PROCESS_DEF_VERSION ||--o{ NIE_SUBSCRIBER : "fk_subscrbr__process_def_ver"
    NIE_SUBSCRIPTION ||--o{ NIE_SUBSCRIBER : "fk_subscriber__subscription"
    DOCUMENT_TYPE ||--o{ NOTIFICATION : "fk_notif__doc_type"
    IAM_USER ||--o{ NOTIFICATION : "fk_notif__iam_user"
    ORGANISATION ||--o{ NOTIFICATION : "fk_notifica_fk_notifi_organisa"
    DOCUMENT ||--o{ NOTIFICATION : "fk_notification__document"
    RINA_CASE ||--o{ NOTIFICATION : "fk_notification__rina_case"
    ORGANISATION ||--o{ NOTIFICATION : "fk_notification_sdr__org"
    RINA_CASE ||--o{ NOTIFICATION_ALARM : "fk_notif_alarm__case"
    NOTIFICATION ||--o{ NOTIFICATION_USER : "fk_notif_user__notif"
    IAM_USER ||--o{ NOTIFICATION_USER : "fk_notif_user__user"
    ORGANISATION ||--o{ ORG_CONTACT_METHOD : "fk_org_contact_method__org"
    PENDING_MESSAGE ||--o{ PENDING_ATTACHMENT : "fk_pend_attach__pend_msg"
    RINA_CASE ||--o{ PENDING_MESSAGE : "fk_pend_msg__case"
    PROCESS_DEF_VERSION ||--o{ PENDING_MESSAGE : "fk_pend_msg__proc_def_ver"
    ORGANISATION ||--o{ PENDING_MESSAGE : "fk_pend_msg_rec__organisation"
    ORGANISATION ||--o{ PENDING_MESSAGE : "fk_pend_msg_sdr__organisation"
    PROCESS_DEF ||--o{ POLICY : "fk_policy__process_def"
    SECTOR ||--o{ POLICY : "fk_policy__sector"
    TENANT ||--o{ POLICY : "fk_policy__tenant"
    SECTOR ||--o{ PROCESS_DEF : "fk_process_def__sector"
    PROCESS_DEF ||--o{ PROCESS_DEF_VERSION : "fk_proc_def__proc_def_version"
    PROCESS_DEF_VERSION ||--o{ RINA_CASE : "fk_case__proc_def_version"
    TENANT ||--o{ RINA_CASE : "fk_case__tenant"
    ASSIGNMENT_POLICY_RULE ||--o{ RULE_COUNTRY : "fk_rule_coun__assign_pol_rule"
    IAM_GROUP ||--o{ RULE_CREATOR_GROUP : "fk_rule_creator_group__group"
    ASSIGNMENT_POLICY_RULE ||--o{ RULE_CREATOR_GROUP : "fk_rule_creator_group__rule"
    ASSIGNMENT_POLICY_RULE ||--o{ RULE_CREATOR_USER : "fk_rule_creator_user__rule"
    IAM_USER ||--o{ RULE_CREATOR_USER : "fk_rule_creator_user__user"
    IAM_GROUP ||--o{ RULE_GROUP : "fk_rule_group__group"
    ASSIGNMENT_POLICY_RULE ||--o{ RULE_GROUP : "fk_rule_group__rule"
    ORGANISATION ||--o{ RULE_ORGANISATION : "fk_rule_org__org"
    ASSIGNMENT_POLICY_RULE ||--o{ RULE_ORGANISATION : "fk_rule_org__rule"
    PROCESS_DEF ||--o{ RULE_PROCESS : "fk_rule_process__process"
    ASSIGNMENT_POLICY_RULE ||--o{ RULE_PROCESS : "fk_rule_process__rule"
    ROLE ||--o{ RULE_ROLE : "fk_rule_role__role"
    ASSIGNMENT_POLICY_RULE ||--o{ RULE_ROLE : "fk_rule_role__rule"
    ASSIGNMENT_POLICY_RULE ||--o{ RULE_SECTOR : "fk_rule_sector__assign_pol_rul"
    SECTOR ||--o{ RULE_SECTOR : "fk_rule_sector__sector"
    ASSIGNMENT_POLICY_RULE ||--o{ RULE_USER : "fk_rule_user__assign_pol_rule"
    IAM_USER ||--o{ RULE_USER : "fk_rule_user__user"
    IAM_GROUP ||--o{ SEARCH_DEF_GROUP : "fk_search_def_group__group"
    SEARCH_DEFINITION ||--o{ SEARCH_DEF_GROUP : "fk_search_def_group__search_def"
    ORGANISATION ||--o{ SEARCH_DEF_ORG : "fk_search_def_org__org"
    SEARCH_DEFINITION ||--o{ SEARCH_DEF_ORG : "fk_search_def_org__search_def"
    PROCESS_DEF ||--o{ SEARCH_DEF_PROC_DEF : "fk_srch_def_proc_def__proc_def"
    SEARCH_DEFINITION ||--o{ SEARCH_DEF_PROC_DEF : "fk_srch_def_proc_def__srch_def"
    SEARCH_DEFINITION ||--o{ SEARCH_DEF_USER : "fk_search_def_user__search_def"
    IAM_USER ||--o{ SEARCH_DEF_USER : "fk_search_def_user__user"
    IAM_USER ||--o{ SEARCH_DEFINITION : "fk_search_d_fk_iam_us_iam_user"
    USER_MESSAGE ||--o{ SIGNATURE : "fk_signature__message"
    SUBDOCUMENT_ATTACHMENT ||--o{ SUBDOC_BVERSION_ATTACHMENT : "fk_subdoc_bver_att__subdoc_att"
    SUBDOCUMENT_BVERSION ||--o{ SUBDOC_BVERSION_ATTACHMENT : "fk_subdoc_bver_att__subdoc_bver"
    DOCUMENT ||--o{ SUBDOCUMENT : "fk_subdoc__doc"
    RINA_CASE ||--o{ SUBDOCUMENT : "fk_subdoc__rina_case"
    SUBDOCUMENT_BVERSION ||--o{ SUBDOCUMENT : "fk_subdoc__subdoc_bversion"
    SUBDOCUMENT ||--o{ SUBDOCUMENT_ATTACHMENT : "fk_subdoc_attach__subdoc"
    SUBDOCUMENT_CONTENT ||--o{ SUBDOCUMENT_BVERSION : "fk_subdoc_bver__subdoc_content"
    SUBDOCUMENT ||--o{ SUBDOCUMENT_BVERSION : "fk_subdoc_bversion__subdoc"
    SUBDOCUMENT ||--o{ SUBDOCUMENT_CONTENT : "fk_subdoc_content_subdoc"
    SUBDOCUMENT ||--o{ SUBDOCUMENT_HISTORY : "fk_subdoc_his__subdoc"
    SUBDOCUMENT_BVERSION ||--o{ SUBDOCUMENT_HISTORY : "fk_subdoc_his__subdoc_bversion"
    SUBDOCUMENT ||--o{ SUBDOCUMENT_PREFILL : "fk_subdoc_prefill__subdoc"
    ORGANISATION ||--o{ TENANT : "fk_tenant__organisation"
    TENANT ||--o{ TENANT_PARAM : "fk_tenant_param__tenant"
    TENANT_PARAM_GROUP ||--o{ TENANT_PARAM : "tenant_param__tenant_param_grp"
    TENANT ||--o{ TENANT_PARAM_GROUP : "fk_tenant_param_group___tenant"
    DOCUMENT_TYPE_VERSION ||--o{ TRANSPOSITION : "fk_transpos__doc_type_version"
    PROCESS_DEF_VERSION ||--o{ TRANSPOSITION : "fk_transpos__proc_def_version"
    DOCUMENT_CONVERSATION ||--o{ USER_MESSAGE : "fk_user_msg__doc_conv"
    ORGANISATION ||--o{ USER_MESSAGE : "fk_user_msg__receiver"
    ORGANISATION ||--o{ USER_MESSAGE : "fk_user_msg__sender"
    USER_MESSAGE ||--o{ USER_MESSAGE_RESPONSE : "fk_usr_msg_res__usr_msg"
    PROCESS_DEF ||--o{ USER_PROFILE : "fk_user_profile__process_def"
    IAM_USER ||--o{ USER_PROFILE : "fk_user_profile__user"
    VOCABULARY_TYPE ||--o{ VOCABULARY : "fk_voc_type__voc"
```

### 2.2 List of tables

| Code | Comment |
| --- | --- |
| ACTION | Available Action of a specific Case Instance or Document |
| ACTION_TAG |  |
| ACTIVITY |  |
| ADMIN_NOTIFICATION_TYPE | AdminNotificationType details |
| ARCHIVING_VOLUME | Archiving volume details |
| ASS_POL_ASS_POL_TARGET | Many-to-many association between assignment policies and targets |
| ASSIGNED_BUC | The BUC assigned to each case |
| ASSIGNMENT | A many-to-many relation table for indicating the association between cases and roles. The table contains a surrogate key and it is not a typical many-to-many table in order to directly access each association since it is used by other many-to-many associations. |
| ASSIGNMENT_GROUP | Many-to-many association between assignments and groups (iam_group table) |
| ASSIGNMENT_POLICY | Assignment Policy details table. |
| ASSIGNMENT_POLICY_POLICY | Many-to-many association between assignment policies parents and children |
| ASSIGNMENT_POLICY_RULE | Assignment Policy Rule details |
| ASSIGNMENT_POLICY_TARGET | Assignment Policy Target details |
| ASSIGNMENT_REQUEST | A many-to-many relation table for indicating the association between cases and roles. The table contains a surrogate key and it is not a typical many-to-many table in order to directly access each association since it is used by other many-to-many associations. |
| ASSIGNMENT_USER | Many-to-many association between assignments and users (iam_user table) |
| AUDIT_EVENT | Table that hold information about the AUDIT's events. |
| AUDIT_OBJECT | Table that hold information about the AUDITed objects. |
| AUDIT_PARTICIPANT | Table that hold information about the AUDITed participants. |
| BUSINESS_EXCEPTION | Table that holds information about the Business Exception |
| BUSINESS_EXCEPTION_SETTINGS | Business Exception Settings |
| BUSINESS_KEY | The business key aliases of the application available to tenants. The keys are located in the associeted keystore. |
| CASE_ATTACHMENT | The attachments associated to a specific case |
| CASE_COMMENT | The comments associated to a specific case |
| CASE_PARTICIPANT | Table that holds infomation about the Participating Institution in a conversation or case instance |
| CASE_PREFILL | The prefill data  associated to a specific case |
| CASE_PROPERTY | The properties  associated to a specific case |
| CASE_SUBJECT_ORG |  |
| CHECK_BUCKET | Table that holds a list of check buckets |
| CHECK_DEFINITION | Table that holds a list of checks |
| CHECK_INSTANCE | Table that holds a list of checks instance details |
| CLUSTER_NODE | The cluster nodes of the system |
| CONV_PARTICIPANT | Table that holds infomation about the Participating Institution in a conversation or case instance |
| DOC_BVERSION_ATTACHMENT | Many-to-many association between document_history entries and document_attachment entries |
| DOC_BVERSION_SUBDOC_BVERSION | Many-to-many association between document_bversion entries and subdocument_bversion entries |
| DOCUMENT | Document details |
| DOCUMENT_ATTACHMENT | The attachments associated to a specific document |
| DOCUMENT_BVERSION | The business version associated to a specific document |
| DOCUMENT_COMMENT | The comments associated to a specific document |
| DOCUMENT_CONTENT | The content associated to a specific document |
| DOCUMENT_CONVERSATION | The attachments associated to a specific document |
| DOCUMENT_HISTORY | The history of the document |
| DOCUMENT_THUMBNAIL | Many-to-one association between document_bversion entries and document_thmbnail entries |
| DOCUMENT_TYPE | The type of document |
| DOCUMENT_TYPE_VERSION | The version of the document type |
| FIELD | Fields to be shown in Case Search Results |
| FIELD_CHOOSER | Table for associating with  the list of Fields to be shown in Case Search Results |
| GLOBAL_PARAM | The global application parameters. |
| GLOBAL_PARAM_GROUP | Table that holds a group of global_application_parameters, with version for optimistic locking and auditing properties. |
| IAM_GROUP | Group Details |
| IAM_ORIGIN | Origin details (Used for LDAP purposes) |
| IAM_USER | User details |
| IAM_USER_GROUP | Many-to-many association between users (iam_user table) and groups (iam_group table) |
| NIE_EVENT | Table that hold information about the NIE's events. |
| NIE_LISTENER | Table that holds NIE's listeners |
| NIE_SUBSCRIBER | Table that holds NIE subscriber |
| NIE_SUBSCRIPTION | Table that hold information about the NIE's event subscription. |
| NOTIFICATION | The table that holds the notifications. |
| NOTIFICATION_ALARM | The table that holds the notification alarms. |
| NOTIFICATION_USER | Many-to-many association between notifications and users (iam_user table). It defines the user responsible parties. |
| ORG_CONTACT_METHOD | Tables that holds information on the organisations'contact methods |
| ORGANISATION | Table that holds infomation about the Organisation |
| PENDING_ATTACHMENT | Table that holds information about the attachment of the pending_messages |
| PENDING_MESSAGE | Table that holds information about the Pending Message |
| PENDING_SIGNATURE | Table that holds information about the Pending Signature |
| PENDING_STATUS | Table that holds information about the Pending Status |
| POLICY | Archiving policy details |
| PROCESS_DEF | Table that holds information about the process definiyion. |
| PROCESS_DEF_VERSION | Table that holds information about the business version of the process definition |
| RESOURCE | Resource inventory |
| RINA_CASE | Table that holds information about the Case |
| ROLE | The roles (Supervisor, Authorised, NonAuthorised, Auditor, Viewer, Medical, VIP) |
| RULE_COUNTRY | Table that holds information about the Country associated with an assignment_ policy_rule's po |
| RULE_CREATOR_GROUP | Many to many table that links Rules and their coresponding groups for creator |
| RULE_CREATOR_USER | Many to many table that links Rules and their coresponding users  for creator |
| RULE_GROUP | Many to many table that links Rules and their coresponding groups |
| RULE_ORGANISATION | Many to many table that links Rules and their coresponding organisations |
| RULE_PROCESS | Many to many table that links Rules and their coresponding processes |
| RULE_ROLE | Table that holds information about roles associated with an assigment policy rule |
| RULE_SECTOR | Many to many table that links Rules and their coresponding sectors |
| RULE_USER | Many to many table that links the Rules to its Users |
| SEARCH_DEF_GROUP | The search definition group table. |
| SEARCH_DEF_ORG | Many-to-many association between search_definition and organisation table. |
| SEARCH_DEF_PROC_DEF | Many-to-many association between search_definition and process_definition table. |
| SEARCH_DEF_USER | Many-to-many association between search_definition and user group table. |
| SEARCH_DEFINITION | The search definition table. |
| SECTOR | Table that holds information about the Sector |
| SIGNATURE | Table that holds information about the User Message Signature  |
| SUBDOC_BVERSION_ATTACHMENT | Many to many table that links subdoc bversions to their attachments |
| SUBDOCUMENT | The subdocument table. |
| SUBDOCUMENT_ATTACHMENT | Table that holds information about the attachment of the subdocument |
| SUBDOCUMENT_BVERSION | The business version associated to a specific subdocument |
| SUBDOCUMENT_CONTENT | The content associated to a specific subdocument |
| SUBDOCUMENT_HISTORY | The history of the subdocument table. |
| SUBDOCUMENT_PREFILL | The prefill data  associated to a specific subdocument |
| SUPPORTED_LANGUAGE | Table that holds the language code |
| TENANT | Table that holds information about the Tenant |
| TENANT_PARAM | Parameters assosiated with a tenant |
| TENANT_PARAM_GROUP | Table that holds a group of global_application_params, with version for optimistic locking and auditing properties. |
| TRANSLATION | Table that holds the transation per language |
| TRANSPOSITION | The transposition json, pertinent to a specific document type |
| USER_MESSAGE | The user message associated to a specific conversation  |
| USER_MESSAGE_RESPONSE | Table that holds information about the user message response (ack / error) |
| USER_PROFILE | The table that holds the user profile. |
| VOCABULARY | Table that holds vocabularies related to a vocabulary_type |
| VOCABULARY_TYPE | Table that holds a list of vocabulary types |

2.2.1 Table action

2.2.1.1 Card of table action

| Code | Value |
| --- | --- |
| Code | ACTION |
| Comment | Available Action of a specific Case Instance or Document |

2.2.1.2 List of incoming references of the table action

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| fk_action_tag__action | action_tag | fk_action_sid |

2.2.1.3 List of outgoing references of the table action

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_action__case | rina_case | fk_case_sid | sid |
| fk_action__doc_type_ver | document_type_version | fk_doc_type_version_sid | sid |
| fk_action__document | document | fk_document_sid | sid |
| fk_action__p_document | document | fk_parent_document_sid | sid |

2.2.1.4 List of columns of the table action

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.action_seq'::regclass) | The surrogate key |
| VERSION | integer | X | 1 | The version of the action.The system version. It is automatically increased by Hibernate each time the row is updated. |
| FK_CASE_SID | bigint |  |  | Foreign key that links the action to the case table. |
| FK_DOCUMENT_SID | bigint |  |  | Foreign key that links the Action to the Document table |
| FK_PARENT_DOCUMENT_SID | bigint |  |  |  |
| FK_DOC_TYPE_VERSION_SID | bigint |  |  | Foreign key to document_type_version table |
| ID | character varying(255) | X |  | The id of the Action. |
| NAME | character varying(255) |  |  | The action name. |
| STATUS | character varying(30) | X | 'NEW'::character varying | The action status.Possible values(active, suspended, cancelled, executed). |
| ACTOR | character varying(30) |  |  | The action actor. Possible values( SUPERVISOR,  AUTHORIZED_CLERK <br>    UNAUTHORIZED_CLERK, AUDITOR,VIEWER, MEDICAL, VIP, EVERYONE) |
| OPERATION_TYPE | character varying(30) |  |  | The action operation type. Possible values: <br>    CREATE("Create"), <br>    UPDATE("Update"), <br>    SEND("Send"), <br>    DELETE("Delete"), <br>    SUBDOCUMENT("Subdocument"), <br> <br>    CREATE_LETTER("CreateLetter"), <br>    READ("Read"), <br>    CLOSE("Close"), <br>    REOPEN("Reopen"), <br>    DELETE_CASE("DeleteCase"), <br>    LOCAL_CLOSE("LocalClose"), <br>    LOCAL_REOPEN("LocalReopen"), <br>    ARCHIVE_CASE("ArchiveCase"), <br>    BACKUP_CASE("BackupCase"), <br>    RESTORE_CASE("RestoreCase"), <br>    SEND_PARTICIPANTS("SendParticipants"), <br>    SELECT_PARTICIPANTS("SelectParticipants"), <br>    READ_PARTICIPANTS("ReadParticipants"), <br>    UPDATE_PARTICIPANTS("UpdateParticipants"), <br>    ADD_ATTACHMENT("Attachment_Added"), //old, not used by UI <br>    REQUEST_APPROVAL("Request_Approval"), <br>    ADD_SUBDOCUMENT("Add_Subdocument"), <br>    UPDATE_SUBDOCUMENT("Update_Subdocument"), <br>    REMOVE_SUBDOCUMENT("Remove_Subdocument"), <br>    IMPORT_SUBDOCUMENT("Import_Subdocuments"), <br> <br>    //new, not used by UI, internal to CPI and BUC-engine <br>    CREATE_CASE("CreateCase"), <br>    REMOVE_ATTACHMENT("Attachment_Removed"), <br> <br>    //new, not used by UI, not used by CPI, internal to BUC-engine only. <br>    FORWARD_CASE("ForwardCase"), <br>    CREATE_CHILD("CreateChild"), <br>    CREATE_REPLY("CreateReply"), <br>    CANCEL("Cancel"), <br>    CANCEL_RECEIVE("CancelReceive"), <br>    RECEIVE("Receive"), <br>    RECEIVE_UPDATE("ReceiveUpdate"), <br>    RECEIVE_REPLY("ReceiveReply"); |
| DISPLAY_IN_DOCUMENT_ID | character varying(255) |  |  | The display in document id. |
| DISPLAY_NAME | character varying(255) |  |  | The display name. |
| DISPLAY_TYPE | character varying(50) |  |  | The display type. |
| TEMPLATE_VERSION | character varying(10) |  |  | The template version. |
| TEMPLATE | character varying(255) |  |  | The template. |
| IS_CASE_RELATED | boolean | X | false | The is case related flag. |
| IS_DOCUMENT_RELATED | boolean | X | false | The is document related flag. |
| IS_BULK | boolean | X | false | The is bulk flag. |
| HAS_BUSINESS_VALIDATION | boolean | X | false | The has business validation flag. |
| REQUIRES_VALID_DOCUMENT | boolean | X | false | The requires valid document flag. |
| CAN_CLOSE | boolean | X | false | The can close flag. |
| AVAILABLE_FROM | timestamp with time zone |  |  | The available from date of the action. |
| CREATED_AT | timestamp with time zone | X | '2024-06-03 16:57:25.134246+00'::timestamp with time zone | Date & Time of Creation |
| UPDATED_AT | timestamp with time zone | X | '2024-06-03 16:57:25.134246+00'::timestamp with time zone | Date & time of last update |

2.2.1.5 List of keys of the table action

| Code | Columns | Primary |
| --- | --- | --- |
| pk_action | sid | X |

2.2.1.6 List of indexes of the table action

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| action__case_idx |  |  | CREATE INDEX action__case_idx ON rina.action USING btree (fk_case_sid) |
| action__doc_type_ver_idx |  |  | CREATE INDEX action__doc_type_ver_idx ON rina.action USING btree (fk_doc_type_version_sid) |
| action__document_idx |  |  | CREATE INDEX action__document_idx ON rina.action USING btree (fk_document_sid) |
| action__id_unq | X |  | CREATE UNIQUE INDEX action__id_unq ON rina.action USING btree (id) |
| action__p_document_idx |  |  | CREATE INDEX action__p_document_idx ON rina.action USING btree (fk_parent_document_sid) |
| action_idx | X |  | CREATE UNIQUE INDEX action_idx ON rina.action USING btree (sid) |
| pk_action | X | X | CREATE UNIQUE INDEX pk_action ON rina.action USING btree (sid) |

2.2.1.7 Other constraints of the table action

_None._

2.2.2 Table action_tag

2.2.2.1 Card of table action_tag

| Code | Value |
| --- | --- |
| Code | ACTION_TAG |
| Comment |  |

2.2.2.2 List of incoming references of the table action_tag

_None._

2.2.2.3 List of outgoing references of the table action_tag

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_action_tag__action | action | fk_action_sid | sid |

2.2.2.4 List of columns of the table action_tag

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X |  | The surrogate key. |
| FK_ACTION_SID | bigint | X |  | Foreign key that links the ACTION_TAG  to the ACTION  table. |
| TYPE | character varying(30) | X |  | The action tag type. Possible values: <br>  ADMIN("admin"), <br>  SECTORIAL("sectorial"); |
| CATEGORY | character varying(30) | X |  | The action tag category. Possible values: <br>    CASE_ACTIONS("Case Actions"), <br>    DOCUMENTS("Documents"), <br>    HORIZONTAL_DOCUMENTS("Horizontal Documents"), <br>    PARTICIPANTS("Participants"); |

2.2.2.5 List of keys of the table action_tag

| Code | Columns | Primary |
| --- | --- | --- |
| pk_action_tag | sid | X |

2.2.2.6 List of indexes of the table action_tag

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| action_tag__action_unq | X |  | CREATE UNIQUE INDEX action_tag__action_unq ON rina.action_tag USING btree (fk_action_sid) |
| action_tag_idx | X |  | CREATE UNIQUE INDEX action_tag_idx ON rina.action_tag USING btree (sid) |
| pk_action_tag | X | X | CREATE UNIQUE INDEX pk_action_tag ON rina.action_tag USING btree (sid) |

2.2.2.7 Other constraints of the table action_tag

_None._

2.2.3 Table activity

2.2.3.1 Card of table activity

| Code | Value |
| --- | --- |
| Code | ACTIVITY |
| Comment |  |

2.2.3.2 List of incoming references of the table activity

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| fk_activity__parent | activity | fk_parent_sid |

2.2.3.3 List of outgoing references of the table activity

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_activity__case | rina_case | fk_case_sid | sid |
| fk_activity__parent | activity | fk_parent_sid | sid |

2.2.3.4 List of columns of the table activity

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.activity_seq'::regclass) | The surrogate key. |
| VERSION | integer | X | 1 | The system version. It is automatically increased by Hibernate each time the row is updated. |
| FK_CASE_SID | bigint | X |  | Foreign key that links the activity  to the case table. |
| FK_PARENT_SID | bigint |  |  | Foreign key that links the activity to it's own parent. |
| ID | character varying(255) | X |  | The id of the Activity. |
| TITLE | character varying(255) |  |  | The title of the activity. |
| MESSAGE | text |  |  | The activity message. |
| START_DATE | timestamp with time zone |  |  | The start date of the activity. |
| IS_DELETED | boolean | X | false | The is deleted flag. |
| IS_REPEATING | boolean | X | false | The is repeating flag. |
| COLOUR | character varying(50) |  |  | The color of the activity. Possible values: <br> BLUE("Blue"), RED("Red"), GREEN("Green"), ORANGE("ORANGE"), PURPLE("purple"); |
| DAY_INTERVAL | bigint |  |  | The day interval. |
| OCCURENCES | bigint |  |  | The number of occurences. |
| CREATED_AT | timestamp with time zone | X | '2024-06-03 16:57:25.371187+00'::timestamp with time zone | Date & Time of Creation. |
| UPDATED_AT | timestamp with time zone | X | '2024-06-03 16:57:25.371187+00'::timestamp with time zone | Date & Time of Update. |
| CREATED_BY | character varying(255) | X | '0'::character varying | The person that created the activity. |
| UPDATED_BY | character varying(255) | X | '0'::character varying | The person that last updated the activity. |

2.2.3.5 List of keys of the table activity

| Code | Columns | Primary |
| --- | --- | --- |
| pk_activity | sid | X |

2.2.3.6 List of indexes of the table activity

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| activity__case_idx |  |  | CREATE INDEX activity__case_idx ON rina.activity USING btree (fk_case_sid) |
| activity__id_unq | X |  | CREATE UNIQUE INDEX activity__id_unq ON rina.activity USING btree (id) |
| activity__parent_idx |  |  | CREATE INDEX activity__parent_idx ON rina.activity USING btree (fk_parent_sid) |
| activity_idx | X |  | CREATE UNIQUE INDEX activity_idx ON rina.activity USING btree (sid) |
| pk_activity | X | X | CREATE UNIQUE INDEX pk_activity ON rina.activity USING btree (sid) |

2.2.3.7 Other constraints of the table activity

_None._

2.2.4 Table admin_notification_type

2.2.4.1 Card of table admin_notification_type

| Code | Value |
| --- | --- |
| Code | ADMIN_NOTIFICATION_TYPE |
| Comment | AdminNotificationType details |

2.2.4.2 List of incoming references of the table admin_notification_type

_None._

2.2.4.3 List of outgoing references of the table admin_notification_type

_None._

2.2.4.4 List of columns of the table admin_notification_type

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.admin_notification_type_seq'::regclass) | The surrogate key. |
| VERSION | integer | X | 1 | The system version. It is automatically increased by Hibernate each time the row is updated. |
| NOTIFICATION_TYPE | character varying(255) | X |  | The notification Type of the AdminNotificationType |
| NOTIFICATION_NAME | character varying(255) | X |  | The notifications name. |
| IS_FOR_ADMIN | boolean |  |  | Value of Notification Centre for Admin checkbox |
| IS_FOR_CLERK | boolean |  |  | Value of the Notification Centre for Clerk checkbox |
| IS_BE | boolean |  |  | Flag to activate the Notification Centre for Business Exception |
| SHOW_FOR_ADMIN | boolean |  |  | Flag to activate the Notification Centre for Admin checkbox |
| SHOW_FOR_CLERK | boolean |  |  | Flag to activate the Notification Centre for Clerk checkbox |
| GENERATE_NIE_EVENT | boolean |  |  | Value of Notification Centre for nie event checkbox |
| RETENTION_PERIOD | bigint |  |  | The retention period of the AdminNotificationType |
| NOTIFICATION_PERIOD | bigint |  |  | The notification period of the AdminNotificationType |

2.2.4.5 List of keys of the table admin_notification_type

| Code | Columns | Primary |
| --- | --- | --- |
| pk_admin_notification_type | sid | X |

2.2.4.6 List of indexes of the table admin_notification_type

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| admin_notif_type_name_unq | X |  | CREATE UNIQUE INDEX admin_notif_type_name_unq ON rina.admin_notification_type USING btree (notification_name) |
| admin_notif_type_type_unq | X |  | CREATE UNIQUE INDEX admin_notif_type_type_unq ON rina.admin_notification_type USING btree (notification_type) |
| admin_notification_type_idx | X |  | CREATE UNIQUE INDEX admin_notification_type_idx ON rina.admin_notification_type USING btree (sid) |
| pk_admin_notification_type | X | X | CREATE UNIQUE INDEX pk_admin_notification_type ON rina.admin_notification_type USING btree (sid) |

2.2.4.7 Other constraints of the table admin_notification_type

_None._

2.2.5 Table archiving_volume

2.2.5.1 Card of table archiving_volume

| Code | Value |
| --- | --- |
| Code | ARCHIVING_VOLUME |
| Comment | Archiving volume details |

2.2.5.2 List of incoming references of the table archiving_volume

_None._

2.2.5.3 List of outgoing references of the table archiving_volume

_None._

2.2.5.4 List of columns of the table archiving_volume

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.archiving_volume_seq'::regclass) | the surrogate key |
| ARCHIVING_VOLUME_ID | character varying(255) | X |  | Volume identifier |
| ARCHIVING_VOLUME | character varying(255) |  |  | Volume name |
| ACHIVING_MIN_SPACE_THRESHOLD | integer |  |  | The minimum space threshold per volume for the archiving process (in MB) |
| PHYSICAL_LOCATIONS | text | X |  | The physical locations attached to volumes |

2.2.5.5 List of keys of the table archiving_volume

| Code | Columns | Primary |
| --- | --- | --- |
| pk_archiving_volume | sid | X |

2.2.5.6 List of indexes of the table archiving_volume

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| archiving__volume_id_unq | X |  | CREATE UNIQUE INDEX archiving__volume_id_unq ON rina.archiving_volume USING btree (archiving_volume_id) |
| archiving_idx | X |  | CREATE UNIQUE INDEX archiving_idx ON rina.archiving_volume USING btree (sid) |
| pk_archiving_volume | X | X | CREATE UNIQUE INDEX pk_archiving_volume ON rina.archiving_volume USING btree (sid) |

2.2.5.7 Other constraints of the table archiving_volume

_None._

2.2.6 Table ass_pol_ass_pol_target

2.2.6.1 Card of table ass_pol_ass_pol_target

| Code | Value |
| --- | --- |
| Code | ASS_POL_ASS_POL_TARGET |
| Comment | Many-to-many association between assignment policies and targets |

2.2.6.2 List of incoming references of the table ass_pol_ass_pol_target

_None._

2.2.6.3 List of outgoing references of the table ass_pol_ass_pol_target

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_as_pl_tgt__as_pl_ass_pl_tgt | assignment_policy_target | fk_target_sid | sid |
| fk_ass_pol__ass_pol_ass_pol_tgt | assignment_policy | fk_policy_sid | sid |

2.2.6.4 List of columns of the table ass_pol_ass_pol_target

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| FK_POLICY_SID | bigint | X |  | foreign key to assignment policy table |
| FK_TARGET_SID | bigint | X |  | foreign_key to assignment policy target table |

2.2.6.5 List of keys of the table ass_pol_ass_pol_target

_None._

2.2.6.6 List of indexes of the table ass_pol_ass_pol_target

_None._

2.2.6.7 Other constraints of the table ass_pol_ass_pol_target

_None._

2.2.7 Table assigned_buc

2.2.7.1 Card of table assigned_buc

| Code | Value |
| --- | --- |
| Code | ASSIGNED_BUC |
| Comment | The BUC assigned to each case |

2.2.7.2 List of incoming references of the table assigned_buc

_None._

2.2.7.3 List of outgoing references of the table assigned_buc

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_assigned_buc__org | organisation | fk_org_sid | sid |
| fk_assigned_buc__process_def | process_def | fk_process_def_sid | sid |

2.2.7.4 List of columns of the table assigned_buc

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.assigned_buc_seq'::regclass) | The surrogate key |
| VERSION | integer | X | 1 | The system version. It is automatically increased by Hibernate each time the row is updated. |
| FK_ORG_SID | bigint | X |  | Foreign key to organisation table |
| FK_PROCESS_DEF_SID | bigint | X |  | foreign key to Process Definition table |
| APPLICATION_ROLE | character varying(2) | X |  | The Application Role. Possible values: <br>  PO("CaseOwner"), <br>   CP("CounterParty"); |
| IS_EESSI_READY | boolean |  |  | Is ready for usage in EESSI |
| VALIDITY_START_DATE | timestamp with time zone |  |  | Start day of the validity |
| VALIDITY_END_DATE | timestamp with time zone |  |  | End day of the validity |
| CREATED_AT | timestamp with time zone | X | '2024-06-03 16:57:25.492488+00'::timestamp with time zone | The time that the BUC was first inserted into the DB |
| UPDATED_AT | timestamp with time zone | X | '2024-06-03 16:57:25.492488+00'::timestamp with time zone | The last time that the BUC was updated |
| CREATED_BY | character varying(255) | X | '0'::character varying | The person that created the asigned buc. |
| UPDATED_BY | character varying(255) | X | '0'::character varying | The person that last updated the assigned buc. |
| UNAVAILABLE_COMPETENCE_INDICATOR | boolean |  |  | Flag indicating if the competence for this assigned BUC is currently explicitly marked as unavailable. |
| COMPETENCE_STATUS | integer |  |  | Numeric representation of the competence status. 0=To Be Activated, 1=Active, 2=To Be Deactivated, 3=Phasing Out, 4=Deactivated. |
| IS_SELECTABLE_FOR_NEW_CASE | boolean |  |  | Computed business rule flag: Indicates if this institution/competence combination can be selected from a list when initializing a new case. |
| CAN_CREATE_NEW_CASE | boolean |  |  | Computed business rule flag: Indicates if the institution is authorized to actually create and start a new case for this BUC. |
| CAN_FORWARD_CASE | boolean |  |  | Computed business rule flag: Indicates if the institution is allowed to forward this existing case to another participant. |
| CAN_RECEIVE_FORWARDED_CASE | boolean |  |  | Computed business rule flag: Indicates if the institution is in a valid state to receive a case forwarded by another participant. |
| CAN_CREATE_SED | boolean |  |  | Computed business rule flag: Indicates if the institution can create a new Structured Electronic Document (SED) within the context of this BUC. |
| CAN_SEND_SED | boolean |  |  | Computed business rule flag: Indicates if the institution is currently permitted to transmit SEDs over the network for this BUC. |
| CAN_RECEIVE_SED | boolean |  |  | Computed business rule flag: Indicates if the institution is currently permitted to receive incoming SEDs for this BUC. |

2.2.7.5 List of keys of the table assigned_buc

| Code | Columns | Primary |
| --- | --- | --- |
| pk_assigned_buc | sid | X |

2.2.7.6 List of indexes of the table assigned_buc

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| ass_buc__proc_def_org_role_unq | X |  | CREATE UNIQUE INDEX ass_buc__proc_def_org_role_unq ON rina.assigned_buc USING btree (fk_org_sid, fk_process_def_sid, application_role) |
| assigned_buc__org_idx |  |  | CREATE INDEX assigned_buc__org_idx ON rina.assigned_buc USING btree (fk_org_sid) |
| assigned_buc__process_def_idx |  |  | CREATE INDEX assigned_buc__process_def_idx ON rina.assigned_buc USING btree (fk_process_def_sid) |
| assigned_buc_idx | X |  | CREATE UNIQUE INDEX assigned_buc_idx ON rina.assigned_buc USING btree (sid) |
| pk_assigned_buc | X | X | CREATE UNIQUE INDEX pk_assigned_buc ON rina.assigned_buc USING btree (sid) |

2.2.7.7 Other constraints of the table assigned_buc

_None._

2.2.8 Table assignment

2.2.8.1 Card of table assignment

| Code | Value |
| --- | --- |
| Code | ASSIGNMENT |
| Comment | A many-to-many relation table for indicating the association between cases and roles. The table contains a surrogate key and it is not a typical many-to-many table in order to directly access each association since it is used by other many-to-many associations. |

2.2.8.2 List of incoming references of the table assignment

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| fk_assign_group__assign | assignment_group | fk_assignment_sid |
| fk_assign_user__assign | assignment_user | fk_assignment_sid |

2.2.8.3 List of outgoing references of the table assignment

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_assign__case | rina_case | fk_case_sid | sid |
| fk_assign__role | role | fk_role_sid | sid |

2.2.8.4 List of columns of the table assignment

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.assignment_seq'::regclass) | The surrogate key |
| ID | character varying(255) |  |  | The id of the assignement. |
| FK_CASE_SID | bigint | X |  | Foreign key to the Case table |
| FK_ROLE_SID | bigint | X |  | Foreign key to the Role table |

2.2.8.5 List of keys of the table assignment

| Code | Columns | Primary |
| --- | --- | --- |
| pk_assignment | sid | X |

2.2.8.6 List of indexes of the table assignment

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| assign__case_idx |  |  | CREATE INDEX assign__case_idx ON rina.assignment USING btree (fk_case_sid) |
| assign__role_idx |  |  | CREATE INDEX assign__role_idx ON rina.assignment USING btree (fk_role_sid) |
| assign_case_role_unq | X |  | CREATE UNIQUE INDEX assign_case_role_unq ON rina.assignment USING btree (fk_role_sid, fk_case_sid) |
| assign_id_unq | X |  | CREATE UNIQUE INDEX assign_id_unq ON rina.assignment USING btree (id) |
| assignment_idx | X |  | CREATE UNIQUE INDEX assignment_idx ON rina.assignment USING btree (sid) |
| pk_assignment | X | X | CREATE UNIQUE INDEX pk_assignment ON rina.assignment USING btree (sid) |

2.2.8.7 Other constraints of the table assignment

_None._

2.2.9 Table assignment_group

2.2.9.1 Card of table assignment_group

| Code | Value |
| --- | --- |
| Code | ASSIGNMENT_GROUP |
| Comment | Many-to-many association between assignments and groups (iam_group table) |

2.2.9.2 List of incoming references of the table assignment_group

_None._

2.2.9.3 List of outgoing references of the table assignment_group

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_assign_group__assign | assignment | fk_assignment_sid | sid |
| fk_assign_group__group | iam_group | fk_group_sid | sid |

2.2.9.4 List of columns of the table assignment_group

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| FK_ASSIGNMENT_SID | bigint | X |  | Foreign key to assignment table |
| FK_GROUP_SID | bigint | X |  | Foreign key to iam_group table |

2.2.9.5 List of keys of the table assignment_group

_None._

2.2.9.6 List of indexes of the table assignment_group

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| assign_group__assign_idx |  |  | CREATE INDEX assign_group__assign_idx ON rina.assignment_group USING btree (fk_assignment_sid) |
| assign_group__group_idx |  |  | CREATE INDEX assign_group__group_idx ON rina.assignment_group USING btree (fk_group_sid) |

2.2.9.7 Other constraints of the table assignment_group

_None._

2.2.10 Table assignment_policy

2.2.10.1 Card of table assignment_policy

| Code | Value |
| --- | --- |
| Code | ASSIGNMENT_POLICY |
| Comment | Assignment Policy details table. |

2.2.10.2 List of incoming references of the table assignment_policy

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| fk_ass_pol__ass_pol_ass_pol_tgt | ass_pol_ass_pol_target | fk_policy_sid |
| fk_assignment_pol__child | assignment_policy_policy | fk_policy_child_sid |
| fk_assignment_pol__parent | assignment_policy_policy | fk_policy_parent_sid |
| fk_assign_pol_rule___assign_pol | assignment_policy_rule | fk_assignment_policy_sid |

2.2.10.3 List of outgoing references of the table assignment_policy

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_assignment_pol__tenant | tenant | fk_tenant_sid | sid |

2.2.10.4 List of columns of the table assignment_policy

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.assignment_policy_seq'::regclass) | The surrogate key |
| VERSION | integer | X | 1 | The system version. It is automatically increased by Hibernate each time the row is updated. |
| FK_TENANT_SID | bigint | X |  | Foreign key to the Tenant table |
| ID | character varying(255) | X |  | The old ES  id |
| NAME | character varying(255) | X |  | The name of the Policy |
| DESCRIPTION | character varying(255) |  |  | The policy description |
| COLOR | character varying(255) |  |  | The color of the policy |
| TYPE | character varying(20) | X |  | The type of this policy. Possible values: <br> POLICY, GROUP, CREATOR; |
| APPLICATION_ROLE | character varying(2) |  |  | Application Role PO or CP  |
| CREATED_AT | timestamp with time zone | X | '2024-06-03 16:57:25.612032+00'::timestamp with time zone | The time that the policy  was first inserted into the DB |
| UPDATED_AT | timestamp with time zone | X | '2024-06-03 16:57:25.612032+00'::timestamp with time zone | The last time that the policy was updated |
| CREATED_BY | character varying(255) | X | '0'::character varying | The person that created the record. |
| UPDATED_BY | character varying(255) | X | '0'::character varying | The person that last updated the record. |

2.2.10.5 List of keys of the table assignment_policy

| Code | Columns | Primary |
| --- | --- | --- |
| pk_assignment_policy | sid | X |

2.2.10.6 List of indexes of the table assignment_policy

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| assignment_pol__tenant_idx |  |  | CREATE INDEX assignment_pol__tenant_idx ON rina.assignment_policy USING btree (fk_tenant_sid) |
| assignment_pol_id_unq | X |  | CREATE UNIQUE INDEX assignment_pol_id_unq ON rina.assignment_policy USING btree (id) |
| assignment_pol_idx | X |  | CREATE UNIQUE INDEX assignment_pol_idx ON rina.assignment_policy USING btree (sid) |
| assignment_pol_name_unq | X |  | CREATE UNIQUE INDEX assignment_pol_name_unq ON rina.assignment_policy USING btree (name, fk_tenant_sid) |
| pk_assignment_policy | X | X | CREATE UNIQUE INDEX pk_assignment_policy ON rina.assignment_policy USING btree (sid) |

2.2.10.7 Other constraints of the table assignment_policy

_None._

2.2.11 Table assignment_policy_policy

2.2.11.1 Card of table assignment_policy_policy

| Code | Value |
| --- | --- |
| Code | ASSIGNMENT_POLICY_POLICY |
| Comment | Many-to-many association between assignment policies parents and children |

2.2.11.2 List of incoming references of the table assignment_policy_policy

_None._

2.2.11.3 List of outgoing references of the table assignment_policy_policy

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_assignment_pol__child | assignment_policy | fk_policy_child_sid | sid |
| fk_assignment_pol__parent | assignment_policy | fk_policy_parent_sid | sid |

2.2.11.4 List of columns of the table assignment_policy_policy

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| FK_POLICY_PARENT_SID | bigint | X |  | foreign key to assignment policy parents |
| FK_POLICY_CHILD_SID | bigint | X |  | foreign_key to assignment policy children |

2.2.11.5 List of keys of the table assignment_policy_policy

_None._

2.2.11.6 List of indexes of the table assignment_policy_policy

_None._

2.2.11.7 Other constraints of the table assignment_policy_policy

_None._

2.2.12 Table assignment_policy_rule

2.2.12.1 Card of table assignment_policy_rule

| Code | Value |
| --- | --- |
| Code | ASSIGNMENT_POLICY_RULE |
| Comment | Assignment Policy Rule details |

2.2.12.2 List of incoming references of the table assignment_policy_rule

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| fk_rule_coun__assign_pol_rule | rule_country | fk_rule_sid |
| fk_rule_creator_group__rule | rule_creator_group | fk_rule_sid |
| fk_rule_creator_user__rule | rule_creator_user | fk_rule_sid |
| fk_rule_group__rule | rule_group | fk_rule_sid |
| fk_rule_org__rule | rule_organisation | fk_rule_sid |
| fk_rule_process__rule | rule_process | fk_rule_sid |
| fk_rule_role__rule | rule_role | fk_rule_sid |
| fk_rule_sector__assign_pol_rul | rule_sector | fk_rule_sid |
| fk_rule_user__assign_pol_rule | rule_user | fk_rule_sid |

2.2.12.3 List of outgoing references of the table assignment_policy_rule

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_assign_pol_rule___assign_pol | assignment_policy | fk_assignment_policy_sid | sid |

2.2.12.4 List of columns of the table assignment_policy_rule

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.assignment_policy_rule_seq'::regclass) | The surrogate key |
| ID | character varying(255) | X |  | The id of the assignment policy rule. |
| VERSION | integer | X | 1 | The system version. It is automatically increased by Hibernate each time the row is updated. |
| FK_ASSIGNMENT_POLICY_SID | bigint | X |  | Foreign key to assignment policy table |
| NAME | character varying(255) |  |  | The name of this rule |
| POSITION_NO | integer | X | 1 | The position number. |
| CONDITION_PARTICIPANT_ROLE | character varying(2) |  |  | The condition that must be met by a case instance for this rule to apply.Possible values:  <br>    PO("CaseOwner"), <br>    CP("CounterParty"); |
| CONDITION_SUBJECT_ADDRESS | character varying(255) |  |  | The condition that must be met by a case instance for this rule to apply |
| ASSIGN_TO_CREATOR_USER | boolean | X | false | The asign to creator user field. |
| ASSIGN_TO_CREATOR_BRANCH | boolean | X | false | The asign to creator branch field. |
| CREATED_AT | timestamp with time zone | X | '2024-06-03 16:57:25.667684+00'::timestamp with time zone | The time that the rule was first inserted into the DB |
| UPDATED_AT | timestamp with time zone | X | '2024-06-03 16:57:25.667684+00'::timestamp with time zone | The last time that the rule was updated |
| CREATED_BY | character varying(255) | X | 'system'::character varying | The person that created the record. |
| UPDATED_BY | character varying(255) | X | 'system'::character varying | The person that last updated the record. |

2.2.12.5 List of keys of the table assignment_policy_rule

| Code | Columns | Primary |
| --- | --- | --- |
| pk_assignment_policy_rule | sid | X |

2.2.12.6 List of indexes of the table assignment_policy_rule

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| assign_pol_rule__assign_pol_idx |  |  | CREATE INDEX assign_pol_rule__assign_pol_idx ON rina.assignment_policy_rule USING btree (fk_assignment_policy_sid) |
| assign_pol_rule_id_unq | X |  | CREATE UNIQUE INDEX assign_pol_rule_id_unq ON rina.assignment_policy_rule USING btree (id) |
| assign_pol_rule_idx | X |  | CREATE UNIQUE INDEX assign_pol_rule_idx ON rina.assignment_policy_rule USING btree (sid) |
| assign_pol_rule_name_unq | X |  | CREATE UNIQUE INDEX assign_pol_rule_name_unq ON rina.assignment_policy_rule USING btree (name) |
| pk_assignment_policy_rule | X | X | CREATE UNIQUE INDEX pk_assignment_policy_rule ON rina.assignment_policy_rule USING btree (sid) |

2.2.12.7 Other constraints of the table assignment_policy_rule

_None._

2.2.13 Table assignment_policy_target

2.2.13.1 Card of table assignment_policy_target

| Code | Value |
| --- | --- |
| Code | ASSIGNMENT_POLICY_TARGET |
| Comment | Assignment Policy Target details |

2.2.13.2 List of incoming references of the table assignment_policy_target

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| fk_as_pl_tgt__as_pl_ass_pl_tgt | ass_pol_ass_pol_target | fk_target_sid |

2.2.13.3 List of outgoing references of the table assignment_policy_target

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_ass_pol_trgt__tenant | tenant | fk_tenant_sid | sid |

2.2.13.4 List of columns of the table assignment_policy_target

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.assignment_policy_target_seq'::regclass) | The surrogate key |
| FK_TENANT_SID | bigint | X |  | Foreign key that links the  asignment policy target to the tennant table. |
| TARGET | character varying(255) | X |  | assignment policy target ID |
| STORAGE_ID | character varying(255) | X |  | The storage id. |

2.2.13.5 List of keys of the table assignment_policy_target

| Code | Columns | Primary |
| --- | --- | --- |
| pk_assignment_policy_target | sid | X |

2.2.13.6 List of indexes of the table assignment_policy_target

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| assign_pol__tenant_idx |  |  | CREATE INDEX assign_pol__tenant_idx ON rina.assignment_policy_target USING btree (fk_tenant_sid) |
| assign_pol_target__unq | X |  | CREATE UNIQUE INDEX assign_pol_target__unq ON rina.assignment_policy_target USING btree (fk_tenant_sid, target) |
| assignment_policy_target_idx | X |  | CREATE UNIQUE INDEX assignment_policy_target_idx ON rina.assignment_policy_target USING btree (sid) |
| pk_assignment_policy_target | X | X | CREATE UNIQUE INDEX pk_assignment_policy_target ON rina.assignment_policy_target USING btree (sid) |

2.2.13.7 Other constraints of the table assignment_policy_target

_None._

2.2.14 Table assignment_request

2.2.14.1 Card of table assignment_request

| Code | Value |
| --- | --- |
| Code | ASSIGNMENT_REQUEST |
| Comment | A many-to-many relation table for indicating the association between cases and roles. The table contains a surrogate key and it is not a typical many-to-many table in order to directly access each association since it is used by other many-to-many associations. |

2.2.14.2 List of incoming references of the table assignment_request

_None._

2.2.14.3 List of outgoing references of the table assignment_request

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_assign_request__case | rina_case | fk_case_sid | sid |
| fk_assign_request__notif | notification | fk_notification_sid | sid |
| fk_assign_request__role | role | fk_role_sid | sid |

2.2.14.4 List of columns of the table assignment_request

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.assignment_request_seq'::regclass) | The surrogate key |
| FK_CASE_SID | bigint | X |  | Foreign key to the Case table |
| FK_ROLE_SID | bigint | X |  | Foreign key to the Role table |
| FK_NOTIFICATION_SID | bigint | X |  | Foreign key that links the asignment request to the notification table. |
| ID | character varying(255) |  |  | The id of the assignement request. |
| STATUS | character varying(20) | X | 'PENDING'::character varying | The status of the assignement request. Possible values: <br>  PENDING, ACCEPTED, REJECTED, COMPLETED; |

2.2.14.5 List of keys of the table assignment_request

| Code | Columns | Primary |
| --- | --- | --- |
| pk_assignment_request | sid | X |

2.2.14.6 List of indexes of the table assignment_request

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| assign_req_case_role_unq | X |  | CREATE UNIQUE INDEX assign_req_case_role_unq ON rina.assignment_request USING btree (fk_role_sid, fk_case_sid, fk_notification_sid) |
| assign_request__case_idx |  |  | CREATE INDEX assign_request__case_idx ON rina.assignment_request USING btree (fk_case_sid) |
| assign_request__notif_idx |  |  | CREATE INDEX assign_request__notif_idx ON rina.assignment_request USING btree (fk_notification_sid) |
| assign_request__role_idx |  |  | CREATE INDEX assign_request__role_idx ON rina.assignment_request USING btree (fk_role_sid) |
| assignment_request_idx | X |  | CREATE UNIQUE INDEX assignment_request_idx ON rina.assignment_request USING btree (sid) |
| pk_assignment_request | X | X | CREATE UNIQUE INDEX pk_assignment_request ON rina.assignment_request USING btree (sid) |

2.2.14.7 Other constraints of the table assignment_request

_None._

2.2.15 Table assignment_user

2.2.15.1 Card of table assignment_user

| Code | Value |
| --- | --- |
| Code | ASSIGNMENT_USER |
| Comment | Many-to-many association between assignments and users (iam_user table) |

2.2.15.2 List of incoming references of the table assignment_user

_None._

2.2.15.3 List of outgoing references of the table assignment_user

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_assign_user__assign | assignment | fk_assignment_sid | sid |
| fk_assign_user__user | iam_user | fk_user_sid | sid |

2.2.15.4 List of columns of the table assignment_user

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| FK_ASSIGNMENT_SID | bigint | X |  | Foreign key to assignment policy table |
| FK_USER_SID | bigint | X |  | Foreign key to iam_group table |

2.2.15.5 List of keys of the table assignment_user

_None._

2.2.15.6 List of indexes of the table assignment_user

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| assign_user__assign_idx |  |  | CREATE INDEX assign_user__assign_idx ON rina.assignment_user USING btree (fk_assignment_sid) |
| assign_user__user_idx |  |  | CREATE INDEX assign_user__user_idx ON rina.assignment_user USING btree (fk_user_sid) |

2.2.15.7 Other constraints of the table assignment_user

_None._

2.2.16 Table audit_event

2.2.16.1 Card of table audit_event

| Code | Value |
| --- | --- |
| Code | AUDIT_EVENT |
| Comment | Table that hold information about the AUDIT's events. |

2.2.16.2 List of incoming references of the table audit_event

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| fk_audit_object__audit_event | audit_object | fk_audit_event_sid |
| fk_audit_part__audit_event | audit_participant | fk_audit_event_sid |

2.2.16.3 List of outgoing references of the table audit_event

_None._

2.2.16.4 List of columns of the table audit_event

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.audit_event_seq'::regclass) | The surrogate key |
| ID | character varying(100) | X |  | The id of the audit. |
| TENANT_ID | character varying(255) |  |  | The id of the tenant |
| ACTION_TYPE | character varying(50) | X |  | The action type of the audit. Possible values: <br>    CREATE("cre"), <br>    UPDATE("upd"), <br>    READ("re"), <br>    DELETE("del"), <br>    EXECUTE("exec"); |
| USERNAME | character varying(255) |  |  | The username of the audited user |
| NET_LOCATION_MACHINE | character varying(255) |  |  | The net location of the machine. |
| NET_LOCATION_IP | text |  |  | The net location ip. |
| EVENT_TYPE | character varying(100) | X |  | The event type. Possible values: <br> /* ATTACHMENTS */ <br>    SUBMIT_ATTACHMENT_ON_CASE, <br>    DELETE_ATTACHMENT_ON_CASE, <br>    RETRIEVE_ATTACHMENT_ON_CASE, <br>    SUBMIT_ATTACHMENT_ON_DOCUMENT, <br>    RETRIEVE_ATTACHMENT_ON_DOCUMENT, <br>    DELETE_ATTACHMENT_ON_DOCUMENT, <br> <br>    /* CASES */ <br>    SEARCH_CASES_BY_SEARCH_DEFINITION_AND_OR_FREE_TEXT <br>    RETRIEVE_CASE_BY_ID <br>    RETRIEVE_CASE_BY_BUSINESS_ID <br>    RETRIEVE_CASE_BY_INTERNATIONAL_ID <br>    RETRIEVE_CASE_ID_BY_INTERNATIONAL_ID <br>    CREATE_NEW_CASE <br>    ASSIGN_CASE <br>    UPDATE_CASE_SENSITIVE <br>    SET_CASE_METADATA <br>    RETRIEVE_CASE_HASHCODE_BY_ID <br>    RETRIEVE_CASE_ASSIGNMENTS <br>    ARCHIVE_UNARCHIVE_CASE <br> <br>    /* COMMENTS */ <br>    SUBMIT_COMMENT_ON_CASE <br>    DELETE_COMMENT_ON_CASE <br>    SUBMIT_COMMENT_ON_DOCUMENT <br>    DELETE_COMMENT_ON_DOCUMENT <br> <br>    /* DOCUMENTS */ <br>    RETRIEVE_INITIAL_DOCUMENT <br>    SUBMIT_DOCUMENT <br>    RETRIEVE_DOCUMENT <br>    RETRIEVE_THUMBNAIL <br>    CREATE_DOCUMENT <br>    UPDATE_DOCUMENT <br>    DELETE_DOCUMENT <br>    SEND_DOCUMENT <br>    IMPORT_BATCH <br>    EXPORT_BATCH <br> <br>    /* LOG IN/OUT */ <br>    LOG_IN <br>    LOG_OUT <br> <br>    /* NOTIFICATIONS */ <br>    RETRIEVE_NOTIFICATIONS_DETAILS <br>    RETRIEVE_NOTIFICATIONS_CONSOLIDATED_SUMMARY <br>    RETRIEVE_NOTIFICATION_SUMMARY <br>    RETRIEVE_NOTIFICATION_TIME_SLOTS <br>    UPDATE_NOTIFICATION <br> <br>    /* SEARCH DEFINITIONS */ <br>    CREATE_SEARCH_DEFINITION <br>    UPDATE_SEARCH_DEFINITION <br>    DELETE_SEARCH_DEFINITION <br> <br>    /* USER PROFILE */ <br>    UPDATE_USER_PROFILE <br>    UPDATE_APPLICATION_PROFILE <br> <br>    /* USER GROUP */ <br>    CREATE_USER_GROUP <br>    UPDATE_USER_GROUP <br>    DELETE_USER_GROUP <br>    CHANGE_AUTHORIZATION_POLICY <br> <br>    /* BUSINESS MESSAGE */ <br>    SEND_BUSINESS_MESSAGE <br>    NOTIFY_ABOUT_RECEIVED_BUSINESS_MESSAGE <br>    NOTIFY_ABOUT_STATUS_UPDATE <br> <br>    /* TECHNICAL MESSAGE */ <br>    SEND_TECHNICAL_MESSAGE <br>    RECEIVE_TECHNICAL_MESSAGE <br> <br>    /* APPLICATION */ <br>    APPLICATION_START <br>    APPLICATION_END <br> <br>    /* ALARM */ <br>    SET_ALARM <br>    CLEAR_ALARM <br>     <br>    /* CASE ASSIGNMENT ACTION*/ <br>    EXECUTE_CASE_ASSIGNMENT_ACTION |
| CATEGORY_TYPE | character varying(20) | X |  | The category type of the audit event. Possible values: <br>    MESSAGING("mess"), <br>    SECURITY("sec"), <br>    BUSINESS("bus"); |
| COMPONENT_TYPE | character varying(20) | X |  | The component type. Possible values: <br>    ATTACHMENTS("attch"), <br>    CASES("cas"), <br>    COMMENTS("cmt"), <br>    DOCUMENTS("doc"), <br>    NOTIFICATIONS("notf"), <br>    SEARCH_DEFINITIONS("srch"), <br>    SECURITY("sec"), <br>    ADMINISTRATION("admin"), <br>    BUSINESS_MESSAGING("bmsg"), <br>    TECHNICAL_MESSAGING("tmsg"); |
| OUTCOME_TYPE | character varying(20) | X |  | The outcome type of the audit event. Possible values: <br>    SUCCESS("succ"), <br>    ERROR("err"), <br>    UNAUTHORIZED("rjct"); |
| OUTCOME_DETAILS | text |  |  | The outcome details of the audit event. |
| CREATED_AT | timestamp with time zone | X | '2024-06-03 16:57:25.828705+00'::timestamp with time zone | Date & Time of Creation. |
| UPDATED_AT | timestamp with time zone | X | '2024-06-03 16:57:25.828705+00'::timestamp with time zone | Date & time of last update. |
| CREATED_BY | character varying(255) | X | '0'::character varying | The person that created the record. |
| UPDATED_BY | character varying(255) | X | '0'::character varying | The person that last updated the record. |

2.2.16.5 List of keys of the table audit_event

| Code | Columns | Primary |
| --- | --- | --- |
| pk_audit_event | sid | X |

2.2.16.6 List of indexes of the table audit_event

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| audit_event_idx | X |  | CREATE UNIQUE INDEX audit_event_idx ON rina.audit_event USING btree (sid) |
| pk_audit_event | X | X | CREATE UNIQUE INDEX pk_audit_event ON rina.audit_event USING btree (sid) |

2.2.16.7 Other constraints of the table audit_event

_None._

2.2.17 Table audit_object

2.2.17.1 Card of table audit_object

| Code | Value |
| --- | --- |
| Code | AUDIT_OBJECT |
| Comment | Table that hold information about the AUDITed objects. |

2.2.17.2 List of incoming references of the table audit_object

_None._

2.2.17.3 List of outgoing references of the table audit_object

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_audit_object__audit_event | audit_event | fk_audit_event_sid | sid |

2.2.17.4 List of columns of the table audit_object

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.audit_object_seq'::regclass) | The surrogate key |
| FK_AUDIT_EVENT_SID | bigint | X |  | Foreign key to the  audit event table. |
| ID | character varying(100) |  |  | The id of the audit object. |
| AUDIT_OBJECT_TYPE | character varying(20) | X |  | The audit object type. Possible values:  <br>    ATTACHMENT("attch"), <br>    ACTION("act"), <br>    CASE("cas"), <br>    COMMENT("cmt"), <br>    DOCUMENT("doc"), <br>    SUBDOCUMENT("sdoc"), <br>    NOTIFICATION("notf"), <br>    ALARM("alrm"), <br>    SEARCH_DEFINITION("srch"), <br>    USER_GROUP("usgr"), <br>    USER_PROFILE("uspr"), <br>    APPLICATION_PROFILE("appr"), <br>    CREDENTIAL("cred"), <br>    POLICY("poly"), <br>    BUSINESS_MESSAGE("bmsg"), <br>    TECHNICAL_MESSAGE("tmsg"), <br>    BUSINESS_ACK("ackm"), <br>    BUSINESS_ERROR("errm"); |
| DETAILS | text |  |  | The audit object details. |

2.2.17.5 List of keys of the table audit_object

| Code | Columns | Primary |
| --- | --- | --- |
| pk_audit_object | sid | X |

2.2.17.6 List of indexes of the table audit_object

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| audit_object__audit_event_idx |  |  | CREATE INDEX audit_object__audit_event_idx ON rina.audit_object USING btree (fk_audit_event_sid) |
| audit_object_idx | X |  | CREATE UNIQUE INDEX audit_object_idx ON rina.audit_object USING btree (sid) |
| pk_audit_object | X | X | CREATE UNIQUE INDEX pk_audit_object ON rina.audit_object USING btree (sid) |

2.2.17.7 Other constraints of the table audit_object

_None._

2.2.18 Table audit_participant

2.2.18.1 Card of table audit_participant

| Code | Value |
| --- | --- |
| Code | AUDIT_PARTICIPANT |
| Comment | Table that hold information about the AUDITed participants. |

2.2.18.2 List of incoming references of the table audit_participant

_None._

2.2.18.3 List of outgoing references of the table audit_participant

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_audit_part__audit_event | audit_event | fk_audit_event_sid | sid |

2.2.18.4 List of columns of the table audit_participant

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.audit_participant_seq'::regclass) | The surrogate key |
| FK_AUDIT_EVENT_SID | bigint | X |  | Foreign key to the audit event table. |
| ID | text |  |  | The audit participant id. |
| PARTICIPANT_TYPE | character varying(20) | X |  | The participant type. Possible values: <br> PERSON("per"), <br>  ORGANISATION("org"); |
| PARTICIPANT_ROLE | character varying(20) | X |  | The participant role of the audit participant. Poosible values: <br>    SENDER("sndr"), <br>    RECEIVER("rcvr"), <br>    SUBJECT("subj"); |

2.2.18.5 List of keys of the table audit_participant

| Code | Columns | Primary |
| --- | --- | --- |
| pk_audit_participant | sid | X |

2.2.18.6 List of indexes of the table audit_participant

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| audit_object__audit_part_idx |  |  | CREATE INDEX audit_object__audit_part_idx ON rina.audit_participant USING btree (fk_audit_event_sid) |
| audit_participantt_idx | X |  | CREATE UNIQUE INDEX audit_participantt_idx ON rina.audit_participant USING btree (sid) |
| pk_audit_participant | X | X | CREATE UNIQUE INDEX pk_audit_participant ON rina.audit_participant USING btree (sid) |

2.2.18.7 Other constraints of the table audit_participant

_None._

2.2.19 Table business_exception

2.2.19.1 Card of table business_exception

| Code | Value |
| --- | --- |
| Code | BUSINESS_EXCEPTION |
| Comment | Table that holds information about the Business Exception |

2.2.19.2 List of incoming references of the table business_exception

_None._

2.2.19.3 List of outgoing references of the table business_exception

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_business_exc__doc | document | fk_doc_sid | sid |
| fk_business_exc__pend_msg | pending_message | fk_pend_msg_sid | sid |

2.2.19.4 List of columns of the table business_exception

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.business_exception_seq'::regclass) | The surrogate key |
| FK_DOC_SID | bigint | X |  | Foreign key that links the Business Exception to the document  table |
| FK_PEND_MSG_SID | bigint | X |  | Foreign key that links the Business Exception to the pending message table |
| ID | character varying(255) | X |  | The id of the Business Exception |
| DATE | timestamp with time zone | X | '2024-06-03 16:57:25.94567+00'::timestamp with time zone |  |
| REASON | character varying(255) |  |  | The reason of the business exception. |

2.2.19.5 List of keys of the table business_exception

| Code | Columns | Primary |
| --- | --- | --- |
| pk_business_exception | sid | X |

2.2.19.6 List of indexes of the table business_exception

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| bus_exc__doc_idx |  |  | CREATE INDEX bus_exc__doc_idx ON rina.business_exception USING btree (fk_doc_sid) |
| bus_exc__id_unq | X |  | CREATE UNIQUE INDEX bus_exc__id_unq ON rina.business_exception USING btree (id) |
| bus_exc__pend_msg_idx |  |  | CREATE INDEX bus_exc__pend_msg_idx ON rina.business_exception USING btree (fk_pend_msg_sid) |
| bus_exc_idx | X |  | CREATE UNIQUE INDEX bus_exc_idx ON rina.business_exception USING btree (sid) |
| pk_business_exception | X | X | CREATE UNIQUE INDEX pk_business_exception ON rina.business_exception USING btree (sid) |

2.2.19.7 Other constraints of the table business_exception

_None._

2.2.20 Table business_exception_settings

2.2.20.1 Card of table business_exception_settings

| Code | Value |
| --- | --- |
| Code | BUSINESS_EXCEPTION_SETTINGS |
| Comment | Business Exception Settings |

2.2.20.2 List of incoming references of the table business_exception_settings

_None._

2.2.20.3 List of outgoing references of the table business_exception_settings

_None._

2.2.20.4 List of columns of the table business_exception_settings

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.business_exception_settings_seq'::regclass) | The surrogate key |
| CAUSE | character varying(255) | X |  | The source/cause of the business error |
| SETTING | integer | X |  | The setting fot the business exception |

2.2.20.5 List of keys of the table business_exception_settings

| Code | Columns | Primary |
| --- | --- | --- |
| pk_business_exception_settings | sid | X |

2.2.20.6 List of indexes of the table business_exception_settings

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| bus_exception_set_cause_unq | X |  | CREATE UNIQUE INDEX bus_exception_set_cause_unq ON rina.business_exception_settings USING btree (cause) |
| business_exception_settings_idx | X |  | CREATE UNIQUE INDEX business_exception_settings_idx ON rina.business_exception_settings USING btree (sid) |
| pk_business_exception_settings | X | X | CREATE UNIQUE INDEX pk_business_exception_settings ON rina.business_exception_settings USING btree (sid) |

2.2.20.7 Other constraints of the table business_exception_settings

_None._

2.2.21 Table business_key

2.2.21.1 Card of table business_key

| Code | Value |
| --- | --- |
| Code | BUSINESS_KEY |
| Comment | The business key aliases of the application available to tenants. The keys are located in the associeted keystore. |

2.2.21.2 List of incoming references of the table business_key

_None._

2.2.21.3 List of outgoing references of the table business_key

_None._

2.2.21.4 List of columns of the table business_key

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.business_key_seq'::regclass) | The surrogate key |
| ALIAS | character varying(255) | X |  | The alias of the business key |
| PASSWORD | character varying(255) | X |  | The password of the business key |

2.2.21.5 List of keys of the table business_key

| Code | Columns | Primary |
| --- | --- | --- |
| pk_business_key | sid | X |

2.2.21.6 List of indexes of the table business_key

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| business_key_alias_unq | X |  | CREATE UNIQUE INDEX business_key_alias_unq ON rina.business_key USING btree (alias) |
| business_key_idx | X |  | CREATE UNIQUE INDEX business_key_idx ON rina.business_key USING btree (sid) |
| pk_business_key | X | X | CREATE UNIQUE INDEX pk_business_key ON rina.business_key USING btree (sid) |

2.2.21.7 Other constraints of the table business_key

_None._

2.2.22 Table case_attachment

2.2.22.1 Card of table case_attachment

| Code | Value |
| --- | --- |
| Code | CASE_ATTACHMENT |
| Comment | The attachments associated to a specific case |

2.2.22.2 List of incoming references of the table case_attachment

_None._

2.2.22.3 List of outgoing references of the table case_attachment

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_case_attach__case | rina_case | fk_case_sid | sid |

2.2.22.4 List of columns of the table case_attachment

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.case_attachment_seq'::regclass) | The surrogate key |
| VERSION | integer | X | 1 | The system version. It is automatically increased by Hibernate each time the row is updated. |
| FK_CASE_SID | bigint | X |  | Foreign key to the rina_case table |
| MIME_TYPE | character varying(50) | X |  | The mime type. Possible values: <br>    APP_PDF <br>    APP_MSWORD <br>    APP_MSEXCEL <br>    APP_MSPOWERPOINT <br>    APP_OPENXML_DOC <br>    APP_OPENXML_SPREADSHEET <br>    APP_OPENXML_PRESENTATION <br>    APP_XML <br>    APP_ZIP <br>    APP_GZIP <br>    IMG_JPEG <br>    IMG_PNG <br>    IMG_TIFF <br>    TXT_RTF <br>    TXT_XML <br> <br>    // Mimetypes NOT included in the SBDH XSD definition <br>    APP_X_ZIP <br>    APP_OCTET_STREAM <br>    APP_X_ZIP_COMPRESSED |
| ID | character varying(255) | X |  | The id of the case attachment. |
| NAME | character varying(255) |  |  | The name of the case attachment. |
| FILENAME | character varying(1024) |  |  | The directory path where the assignment is stored |
| PATHNAME | character varying(1024) | X |  | The pathname of the attachment. |
| IS_MEDICAL | boolean | X | false | The is medical flag. |
| IS_ACTIVE | boolean | X | true | The is active flag. |
| CREATED_AT | timestamp with time zone | X | '2024-06-03 16:57:26.087456+00'::timestamp with time zone | Date & Time of Creation. |
| UPDATED_AT | timestamp with time zone | X | '2024-06-03 16:57:26.087456+00'::timestamp with time zone | Date & time of last update. |
| CREATED_BY | character varying(255) | X | '0'::character varying | The person that created the record. |
| UPDATED_BY | character varying(255) | X | '0'::character varying | The person that last updated the record. |

2.2.22.5 List of keys of the table case_attachment

| Code | Columns | Primary |
| --- | --- | --- |
| pk_case_attachment | sid | X |

2.2.22.6 List of indexes of the table case_attachment

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| case_attachement_idx | X |  | CREATE UNIQUE INDEX case_attachement_idx ON rina.case_attachment USING btree (sid) |
| case_attachment__case_idx |  |  | CREATE INDEX case_attachment__case_idx ON rina.case_attachment USING btree (fk_case_sid) |
| case_attachment_id_unq | X |  | CREATE UNIQUE INDEX case_attachment_id_unq ON rina.case_attachment USING btree (id, fk_case_sid) |
| pk_case_attachment | X | X | CREATE UNIQUE INDEX pk_case_attachment ON rina.case_attachment USING btree (sid) |

2.2.22.7 Other constraints of the table case_attachment

_None._

2.2.23 Table case_comment

2.2.23.1 Card of table case_comment

| Code | Value |
| --- | --- |
| Code | CASE_COMMENT |
| Comment | The comments associated to a specific case |

2.2.23.2 List of incoming references of the table case_comment

_None._

2.2.23.3 List of outgoing references of the table case_comment

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_comment__case | rina_case | fk_case_sid | sid |

2.2.23.4 List of columns of the table case_comment

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.case_comment_seq'::regclass) | The surrogate key |
| VERSION | integer | X | 1 | The system version. It is automatically increased by Hibernate each time the row is updated. |
| FK_CASE_SID | bigint | X |  | Foreign key to the rina_case table |
| ID | character varying(255) | X |  | The id of the case comment. |
| TEXT | text | X |  | The comment |
| CREATED_AT | timestamp with time zone | X | '2024-06-03 16:57:26.161446+00'::timestamp with time zone | Date & Time the entity was created |
| UPDATED_AT | timestamp with time zone | X | '2024-06-03 16:57:26.161446+00'::timestamp with time zone | Date & Time the entity was last updated |
| CREATED_BY | character varying(255) | X | '0'::character varying | The person that created the record. |
| UPDATED_BY | character varying(255) | X | '0'::character varying | The person that last updated the record. |

2.2.23.5 List of keys of the table case_comment

| Code | Columns | Primary |
| --- | --- | --- |
| pk_case_comment | sid | X |

2.2.23.6 List of indexes of the table case_comment

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| case_comment__case_idx |  |  | CREATE INDEX case_comment__case_idx ON rina.case_comment USING btree (fk_case_sid) |
| case_comment_id_unq | X |  | CREATE UNIQUE INDEX case_comment_id_unq ON rina.case_comment USING btree (id) |
| case_comment_idx | X |  | CREATE UNIQUE INDEX case_comment_idx ON rina.case_comment USING btree (sid) |
| pk_case_comment | X | X | CREATE UNIQUE INDEX pk_case_comment ON rina.case_comment USING btree (sid) |

2.2.23.7 Other constraints of the table case_comment

_None._

2.2.24 Table case_participant

2.2.24.1 Card of table case_participant

| Code | Value |
| --- | --- |
| Code | CASE_PARTICIPANT |
| Comment | Table that holds infomation about the Participating Institution in a conversation or case instance |

2.2.24.2 List of incoming references of the table case_participant

_None._

2.2.24.3 List of outgoing references of the table case_participant

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_case_participant__case | rina_case | fk_case_sid | sid |
| fk_case_participant__org | organisation | fk_org_sid | sid |

2.2.24.4 List of columns of the table case_participant

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.case_participant_seq'::regclass) | The surrogate key |
| FK_CASE_SID | bigint | X |  | Foreign key associated to the associated case. |
| FK_ORG_SID | bigint | X |  | foreign key to organisation |
| CASE_PARTICIPANT_ROLE | character varying(2) | X |  | The role of the participant in in a conversation or in a case |

2.2.24.5 List of keys of the table case_participant

| Code | Columns | Primary |
| --- | --- | --- |
| pk_case_participant | sid | X |

2.2.24.6 List of indexes of the table case_participant

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| case_participant__case_idx |  |  | CREATE INDEX case_participant__case_idx ON rina.case_participant USING btree (fk_case_sid) |
| case_participant__org_idx |  |  | CREATE INDEX case_participant__org_idx ON rina.case_participant USING btree (fk_org_sid) |
| case_participant_idx | X |  | CREATE UNIQUE INDEX case_participant_idx ON rina.case_participant USING btree (sid) |
| pk_case_participant | X | X | CREATE UNIQUE INDEX pk_case_participant ON rina.case_participant USING btree (sid) |

2.2.24.7 Other constraints of the table case_participant

_None._

2.2.25 Table case_prefill

2.2.25.1 Card of table case_prefill

| Code | Value |
| --- | --- |
| Code | CASE_PREFILL |
| Comment | The prefill data  associated to a specific case |

2.2.25.2 List of incoming references of the table case_prefill

_None._

2.2.25.3 List of outgoing references of the table case_prefill

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_case_prefill__rina_case | rina_case | fk_case_sid | sid |

2.2.25.4 List of columns of the table case_prefill

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.case_prefill_seq'::regclass) | The surrogate key |
| FK_CASE_SID | bigint | X |  | Foreign key to the rina_case table |
| PREFILL_GROUP | character varying(20) | X | 'PREFILL'::character varying | The prefill group. Possible values: <br>    SUBJECT, <br>    PREFILL, <br>    SEARCH_METADATA; |
| KEY | character varying(1024) | X |  | The key of the case prefill. |
| VALUE | text | X |  | The directory path where the assignment is stored |

2.2.25.5 List of keys of the table case_prefill

| Code | Columns | Primary |
| --- | --- | --- |
| pk_case_prefill | sid | X |

2.2.25.6 List of indexes of the table case_prefill

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| case_prefill__case_idx |  |  | CREATE INDEX case_prefill__case_idx ON rina.case_prefill USING btree (fk_case_sid) |
| case_prefill__group_idx |  |  | CREATE INDEX case_prefill__group_idx ON rina.case_prefill USING btree (prefill_group) |
| case_prefill__key_unq | X |  | CREATE UNIQUE INDEX case_prefill__key_unq ON rina.case_prefill USING btree (fk_case_sid, prefill_group, key) |
| case_prefill_idx | X |  | CREATE UNIQUE INDEX case_prefill_idx ON rina.case_prefill USING btree (sid) |
| pk_case_prefill | X | X | CREATE UNIQUE INDEX pk_case_prefill ON rina.case_prefill USING btree (sid) |

2.2.25.7 Other constraints of the table case_prefill

_None._

2.2.26 Table case_property

2.2.26.1 Card of table case_property

| Code | Value |
| --- | --- |
| Code | CASE_PROPERTY |
| Comment | The properties  associated to a specific case |

2.2.26.2 List of incoming references of the table case_property

_None._

2.2.26.3 List of outgoing references of the table case_property

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_case_property__case | rina_case | fk_case_sid | sid |

2.2.26.4 List of columns of the table case_property

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.case_property_seq'::regclass) | The surrogate key |
| FK_CASE_SID | bigint | X |  | Foreign key to the rina_case table |
| KEY | character varying(30) | X |  | The key of the case property. |
| VALUE | character varying(255) | X |  | The directory path where the assignment is stored |

2.2.26.5 List of keys of the table case_property

| Code | Columns | Primary |
| --- | --- | --- |
| pk_case_property | sid | X |

2.2.26.6 List of indexes of the table case_property

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| case_property__case_idx |  |  | CREATE INDEX case_property__case_idx ON rina.case_property USING btree (fk_case_sid) |
| case_property__key_unq | X |  | CREATE UNIQUE INDEX case_property__key_unq ON rina.case_property USING btree (fk_case_sid, key) |
| case_property_idx | X |  | CREATE UNIQUE INDEX case_property_idx ON rina.case_property USING btree (sid) |
| pk_case_property | X | X | CREATE UNIQUE INDEX pk_case_property ON rina.case_property USING btree (sid) |

2.2.26.7 Other constraints of the table case_property

_None._

2.2.27 Table case_subject_org

2.2.27.1 Card of table case_subject_org

| Code | Value |
| --- | --- |
| Code | CASE_SUBJECT_ORG |
| Comment |  |

2.2.27.2 List of incoming references of the table case_subject_org

_None._

2.2.27.3 List of outgoing references of the table case_subject_org

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_case_subject_org__case | rina_case | fk_case_sid | sid |
| fk_case_subject_org__org | organisation | fk_org_sid | sid |

2.2.27.4 List of columns of the table case_subject_org

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| FK_CASE_SID | bigint | X |  | Foreign key to the  rina case table. |
| FK_ORG_SID | bigint | X |  | Fk to the organisation table. |

2.2.27.5 List of keys of the table case_subject_org

_None._

2.2.27.6 List of indexes of the table case_subject_org

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| case_subject_org__case_idx |  |  | CREATE INDEX case_subject_org__case_idx ON rina.case_subject_org USING btree (fk_case_sid) |
| case_subject_org__org_idx |  |  | CREATE INDEX case_subject_org__org_idx ON rina.case_subject_org USING btree (fk_org_sid) |

2.2.27.7 Other constraints of the table case_subject_org

_None._

2.2.28 Table check_bucket

2.2.28.1 Card of table check_bucket

| Code | Value |
| --- | --- |
| Code | CHECK_BUCKET |
| Comment | Table that holds a list of check buckets |

2.2.28.2 List of incoming references of the table check_bucket

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| fk_check_instance__check_bucket | check_instance | fk_check_bucket_sid |

2.2.28.3 List of outgoing references of the table check_bucket

_None._

2.2.28.4 List of columns of the table check_bucket

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.check_bucket_seq'::regclass) | The surrogate key |
| ID | character varying(255) | X |  | The id of the check bucket. |
| START_DATE | timestamp with time zone | X |  | The start date. |

2.2.28.5 List of keys of the table check_bucket

| Code | Columns | Primary |
| --- | --- | --- |
| pk_check_bucket | sid | X |

2.2.28.6 List of indexes of the table check_bucket

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| check_bucket_id_idx | X |  | CREATE UNIQUE INDEX check_bucket_id_idx ON rina.check_bucket USING btree (id) |
| check_bucket_idx | X |  | CREATE UNIQUE INDEX check_bucket_idx ON rina.check_bucket USING btree (sid) |
| pk_check_bucket | X | X | CREATE UNIQUE INDEX pk_check_bucket ON rina.check_bucket USING btree (sid) |

2.2.28.7 Other constraints of the table check_bucket

_None._

2.2.29 Table check_definition

2.2.29.1 Card of table check_definition

| Code | Value |
| --- | --- |
| Code | CHECK_DEFINITION |
| Comment | Table that holds a list of checks |

2.2.29.2 List of incoming references of the table check_definition

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| fk_check_instance__check_def | check_instance | fk_check_definition_sid |

2.2.29.3 List of outgoing references of the table check_definition

_None._

2.2.29.4 List of columns of the table check_definition

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.check_definition_seq'::regclass) | The surrogate key |
| ID | character varying(255) | X |  | The id of the check definition. |
| CHECK_CATEGORY | character varying(255) | X |  | The check category. |
| NAME | character varying(255) | X |  | The name of the check definition. |
| DESCRIPTION | character varying(255) |  |  | The check definition description. |
| PROPERTIES | character varying(4000) |  |  | The check definition properties. |
| IS_VALID | boolean | X |  | The is valid flag. |

2.2.29.5 List of keys of the table check_definition

| Code | Columns | Primary |
| --- | --- | --- |
| pk_check_definition | sid | X |

2.2.29.6 List of indexes of the table check_definition

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| check_def_id_idx | X |  | CREATE UNIQUE INDEX check_def_id_idx ON rina.check_definition USING btree (id) |
| check_def_idx | X |  | CREATE UNIQUE INDEX check_def_idx ON rina.check_definition USING btree (sid) |
| pk_check_definition | X | X | CREATE UNIQUE INDEX pk_check_definition ON rina.check_definition USING btree (sid) |

2.2.29.7 Other constraints of the table check_definition

_None._

2.2.30 Table check_instance

2.2.30.1 Card of table check_instance

| Code | Value |
| --- | --- |
| Code | CHECK_INSTANCE |
| Comment | Table that holds a list of checks instance details |

2.2.30.2 List of incoming references of the table check_instance

_None._

2.2.30.3 List of outgoing references of the table check_instance

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_check_instance__check_bucket | check_bucket | fk_check_bucket_sid | sid |
| fk_check_instance__check_def | check_definition | fk_check_definition_sid | sid |

2.2.30.4 List of columns of the table check_instance

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.check_instance_seq'::regclass) | The surrogate key |
| FK_CHECK_DEFINITION_SID | bigint | X |  | Foreign key to the check definition table. |
| FK_CHECK_BUCKET_SID | bigint | X |  | Foreign key to the check bucket table. |
| ID | character varying(255) | X |  | The id of the check instance. |
| NAME | character varying(255) |  |  | The name of the check instance. |
| START_DATE | timestamp with time zone | X |  | The start date of the check instance. |
| END_DATE | timestamp with time zone |  |  | The end date. |
| STATUS | character varying(255) | X |  | The status. |
| MESSAGE | character varying(4000) |  |  | The check instance message. |

2.2.30.5 List of keys of the table check_instance

| Code | Columns | Primary |
| --- | --- | --- |
| pk_check_instance | sid | X |

2.2.30.6 List of indexes of the table check_instance

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| check_instance__check_buc_idx |  |  | CREATE INDEX check_instance__check_buc_idx ON rina.check_instance USING btree (fk_check_bucket_sid) |
| check_instance__check_def_idx |  |  | CREATE INDEX check_instance__check_def_idx ON rina.check_instance USING btree (fk_check_definition_sid) |
| check_instance_id_idx | X |  | CREATE UNIQUE INDEX check_instance_id_idx ON rina.check_instance USING btree (id) |
| check_instance_idx | X |  | CREATE UNIQUE INDEX check_instance_idx ON rina.check_instance USING btree (sid) |
| pk_check_instance | X | X | CREATE UNIQUE INDEX pk_check_instance ON rina.check_instance USING btree (sid) |

2.2.30.7 Other constraints of the table check_instance

_None._

2.2.31 Table cluster_node

2.2.31.1 Card of table cluster_node

| Code | Value |
| --- | --- |
| Code | CLUSTER_NODE |
| Comment | The cluster nodes of the system |

2.2.31.2 List of incoming references of the table cluster_node

_None._

2.2.31.3 List of outgoing references of the table cluster_node

_None._

2.2.31.4 List of columns of the table cluster_node

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.cluster_node_seq'::regclass) | The surrogate key |
| NAME | character varying(255) | X |  | The name of the node |
| PMODE_PATH | character varying(255) | X |  | The directory path where the pmodes of the node are located |

2.2.31.5 List of keys of the table cluster_node

| Code | Columns | Primary |
| --- | --- | --- |
| pk_cluster_node | sid | X |

2.2.31.6 List of indexes of the table cluster_node

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| cluster_node_idx | X |  | CREATE UNIQUE INDEX cluster_node_idx ON rina.cluster_node USING btree (sid) |
| cluster_node_name_unq | X |  | CREATE UNIQUE INDEX cluster_node_name_unq ON rina.cluster_node USING btree (name) |
| pk_cluster_node | X | X | CREATE UNIQUE INDEX pk_cluster_node ON rina.cluster_node USING btree (sid) |

2.2.31.7 Other constraints of the table cluster_node

_None._

2.2.32 Table conv_participant

2.2.32.1 Card of table conv_participant

| Code | Value |
| --- | --- |
| Code | CONV_PARTICIPANT |
| Comment | Table that holds infomation about the Participating Institution in a conversation or case instance |

2.2.32.2 List of incoming references of the table conv_participant

_None._

2.2.32.3 List of outgoing references of the table conv_participant

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_conv_participant__conv | document_conversation | fk_conv_sid | sid |
| fk_conv_participant__org | organisation | fk_org_sid | sid |

2.2.32.4 List of columns of the table conv_participant

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.conv_participant_seq'::regclass) | The surrogate key |
| FK_CONV_SID | bigint | X |  | Foreign key associated to the associated case. |
| FK_ORG_SID | bigint | X |  | foreign key to organisation |
| CONV_PARTICIPANT_ROLE | character varying(11) | X |  | The role of the participant in in a conversation or in a case |

2.2.32.5 List of keys of the table conv_participant

| Code | Columns | Primary |
| --- | --- | --- |
| pk_conv_participant | sid | X |

2.2.32.6 List of indexes of the table conv_participant

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| conv_participant__conv_idx |  |  | CREATE INDEX conv_participant__conv_idx ON rina.conv_participant USING btree (fk_conv_sid) |
| conv_participant__org_idx |  |  | CREATE INDEX conv_participant__org_idx ON rina.conv_participant USING btree (fk_org_sid) |
| conv_participant_idx | X |  | CREATE UNIQUE INDEX conv_participant_idx ON rina.conv_participant USING btree (sid) |
| pk_conv_participant | X | X | CREATE UNIQUE INDEX pk_conv_participant ON rina.conv_participant USING btree (sid) |

2.2.32.7 Other constraints of the table conv_participant

_None._

2.2.33 Table doc_bversion_attachment

2.2.33.1 Card of table doc_bversion_attachment

| Code | Value |
| --- | --- |
| Code | DOC_BVERSION_ATTACHMENT |
| Comment | Many-to-many association between document_history entries and document_attachment entries |

2.2.33.2 List of incoming references of the table doc_bversion_attachment

_None._

2.2.33.3 List of outgoing references of the table doc_bversion_attachment

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_doc_bversion_att__doc_att | document_attachment | fk_doc_attachment_sid | sid |
| fk_doc_bversion_att__doc_bvers | document_bversion | fk_doc_bversion_sid | sid |

2.2.33.4 List of columns of the table doc_bversion_attachment

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| FK_DOC_BVERSION_SID | bigint | X |  | The surrogate key |
| FK_DOC_ATTACHMENT_SID | bigint | X |  | Foreign key to document_attachment table |

2.2.33.5 List of keys of the table doc_bversion_attachment

_None._

2.2.33.6 List of indexes of the table doc_bversion_attachment

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| doc_bversion_att__doc_att_idx |  |  | CREATE INDEX doc_bversion_att__doc_att_idx ON rina.doc_bversion_attachment USING btree (fk_doc_attachment_sid) |
| doc_bversion_att__doc_bvers_idx |  |  | CREATE INDEX doc_bversion_att__doc_bvers_idx ON rina.doc_bversion_attachment USING btree (fk_doc_bversion_sid) |

2.2.33.7 Other constraints of the table doc_bversion_attachment

_None._

2.2.34 Table doc_bversion_subdoc_bversion

2.2.34.1 Card of table doc_bversion_subdoc_bversion

| Code | Value |
| --- | --- |
| Code | DOC_BVERSION_SUBDOC_BVERSION |
| Comment | Many-to-many association between document_bversion entries and subdocument_bversion entries |

2.2.34.2 List of incoming references of the table doc_bversion_subdoc_bversion

_None._

2.2.34.3 List of outgoing references of the table doc_bversion_subdoc_bversion

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_doc_bv_subdoc_bv__doc_bv | document_bversion | fk_doc_bversion_sid | sid |
| fk_doc_bv_subdoc_bv__subdoc_bv | subdocument_bversion | fk_subdoc_bversion_sid | sid |

2.2.34.4 List of columns of the table doc_bversion_subdoc_bversion

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| FK_DOC_BVERSION_SID | bigint | X |  | The surrogate key |
| FK_SUBDOC_BVERSION_SID | bigint | X |  | Foreign key to document_attachment table |

2.2.34.5 List of keys of the table doc_bversion_subdoc_bversion

_None._

2.2.34.6 List of indexes of the table doc_bversion_subdoc_bversion

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| doc_bv_subdoc_bv__doc_bv_idx |  |  | CREATE INDEX doc_bv_subdoc_bv__doc_bv_idx ON rina.doc_bversion_subdoc_bversion USING btree (fk_doc_bversion_sid) |
| doc_bv_subdoc_bv__subdoc_bv_idx |  |  | CREATE INDEX doc_bv_subdoc_bv__subdoc_bv_idx ON rina.doc_bversion_subdoc_bversion USING btree (fk_subdoc_bversion_sid) |

2.2.34.7 Other constraints of the table doc_bversion_subdoc_bversion

_None._

2.2.35 Table document

2.2.35.1 Card of table document

| Code | Value |
| --- | --- |
| Code | DOCUMENT |
| Comment | Document details |

2.2.35.2 List of incoming references of the table document

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| fk_action__document | action | fk_document_sid |
| fk_action__p_document | action | fk_parent_document_sid |
| fk_business_exc__doc | business_exception | fk_doc_sid |
| fk_document__parent | document | fk_parent_sid |
| fk_doc_attach__doc | document_attachment | fk_doc_sid |
| fk_doc_bversion__doc | document_bversion | fk_doc_sid |
| fk_doc_comment__doc | document_comment | fk_doc_sid |
| fk_doc_content__doc | document_content | fk_doc_sid |
| fk_doc_conv__doc | document_conversation | fk_doc_sid |
| fk_doc_his__doc | document_history | fk_doc_sid |
| fk_notification__document | notification | fk_document_sid |
| fk_subdoc__doc | subdocument | fk_document_sid |

2.2.35.3 List of outgoing references of the table document

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_doc__doc_bversion | document_bversion | fk_doc_bversion_sid | sid |
| fk_doc__doc_type_version | document_type_version | fk_doc_type_version_sid | sid |
| fk_document__case | rina_case | fk_case_sid | sid |
| fk_document__parent | document | fk_parent_sid | sid |

2.2.35.4 List of columns of the table document

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.document_seq'::regclass) | The surrogate key |
| VERSION | integer | X | 1 | The system version. It is automatically increased by Hibernate each time the row is updated. |
| FK_CASE_SID | bigint |  |  | Foreign key to the rina_case table |
| FK_DOC_TYPE_VERSION_SID | bigint | X |  | Foreign key to document_type_version table |
| FK_PARENT_SID | bigint |  |  | The fk to the parent of the document. |
| FK_DOC_BVERSION_SID | bigint |  |  | The content of the document |
| ID | character varying(255) | X |  | Id of the document |
| NAME | character varying(255) |  |  | The name of the document. |
| DISPLAY_NAME | character varying(255) |  |  | The display name of the Document |
| STATUS | character varying(20) |  |  | The status of the Document. Possible values: <br>NEW("new"), <br>EMPTY("empty"), <br>ACTIVE("active"), <br>SENT("sent"), <br>CANCELLED("cancelled"), <br>RECEIVED("received"); |
| INTERNAL_ID | character varying(255) |  |  | The internal id. |
| DM_PROCESS_ID | bigint |  |  | The process id of the document manager |
| SUB_PROCESS_ID | bigint |  |  | The subprocess id |
| READ_TEMPLATE | character varying(255) |  |  | Template for reading the document |
| CREATE_TEMPLATE | character varying(255) |  |  | Template for creating the document |
| DIRECTION | character varying(255) |  |  | The direction of the Document. Possible values: <br>IN, <br>OUT <br> |
| MIME_TYPE | character varying(50) |  |  | The mime type of the document. |
| DOC_ORDER | integer | X | 1 | The order of the document |
| TO_SENDER_ONLY | boolean | X | false | TRUE If the document is only to sender |
| IS_ADMIN | boolean | X | false | TRUE If this is an admin document |
| IS_BULK | boolean | X | false | Whether or not the document is a Bulk(Batch) Document |
| IS_DUMMY_DOCUMENT | boolean | X | false | True if the document is just a dummy. |
| IS_FIRST_DOCUMENT | boolean | X | false | TRUE if this is the first document |
| IS_MLC | boolean | X | false | TRUE if this is MLC document |
| IS_STARTER | boolean | X | false | If document already sent |
| IS_SEND_EXECUTED | boolean | X | false | TRUE If document already sent |
| IS_REPLY | boolean | X | false | The is reply flag. |
| IS_VALID | boolean | X | true | The is valid flag. |
| VALIDATION_ERRORS | text |  |  | The validation errors flag. |
| HAS_REPLY_CLARIFY | boolean | X | false | TRUE if it has reply clarify |
| HAS_REJECT | boolean | X | false | TRUE if it has reject |
| HAS_LETTER | boolean | X | false | TRUE if it has letter |
| HAS_CLARIFY | boolean | X | false | TRUE if it has clarify |
| HAS_CANCEL | boolean | X | false | TRUE if it has cancel |
| HAS_BUSINESS_VALIDATION | boolean | X | false | Requires any business side validation before any action. Default is false. |
| HAS_MULTIPLE_VERSIONS | boolean | X | false | TRUE if the document has multiple versions |
| SELECT_PARTICIPANTS | boolean | X | false | TRUE If select participant |
| ALLOWS_ATTACHMENTS | boolean | X | false | The document allows having attachments. Default is false. |
| CAN_BE_SENT_WITHOUT_CHILD | boolean | X | false | True if the document can be sent without any children. |
| COUNTER | integer | X | 1 | The counter value of the document. |
| BUSINESS_REFERENCE_MANAGER | text |  |  | Keeps information in JSON format of subdocuments business references for bulk documents |
| RECEIVED_AT | timestamp with time zone |  |  | The date when the document was received. |
| ORIG_CREATED_AT | timestamp with time zone |  |  | Keeps the original date when document was created by sender |
| ORIG_UPDATED_AT | timestamp with time zone |  |  | Keeps the original date when document was updated by sender |
| CREATED_AT | timestamp with time zone | X | '2024-06-03 16:57:26.460564+00'::timestamp with time zone | The time that the document  was first inserted into the DB |
| UPDATED_AT | timestamp with time zone | X | '2024-06-03 16:57:26.460564+00'::timestamp with time zone | The last time that the document  was updated |
| CREATED_BY | character varying(255) | X | '0'::character varying | The person that created the record. |
| UPDATED_BY | character varying(255) | X | '0'::character varying | The person that last updated the record. |
| RANDOM_STRING | character varying(255) | X | 'A1'::character varying | Random string for unicity in the document. |

2.2.35.5 List of keys of the table document

| Code | Columns | Primary |
| --- | --- | --- |
| pk_document | sid | X |

2.2.35.6 List of indexes of the table document

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| doc__doc_bversion_idx |  |  | CREATE INDEX doc__doc_bversion_idx ON rina.document USING btree (fk_doc_bversion_sid) |
| doc__doc_type_version_idx |  |  | CREATE INDEX doc__doc_type_version_idx ON rina.document USING btree (fk_doc_type_version_sid) |
| doc_case_idx |  |  | CREATE INDEX doc_case_idx ON rina.document USING btree (fk_case_sid) |
| doc_id_unq | X |  | CREATE UNIQUE INDEX doc_id_unq ON rina.document USING btree (fk_case_sid, id) |
| doc_idx | X |  | CREATE UNIQUE INDEX doc_idx ON rina.document USING btree (sid) |
| pk_document | X | X | CREATE UNIQUE INDEX pk_document ON rina.document USING btree (sid) |

2.2.35.7 Other constraints of the table document

_None._

2.2.36 Table document_attachment

2.2.36.1 Card of table document_attachment

| Code | Value |
| --- | --- |
| Code | DOCUMENT_ATTACHMENT |
| Comment | The attachments associated to a specific document |

2.2.36.2 List of incoming references of the table document_attachment

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| fk_doc_bversion_att__doc_att | doc_bversion_attachment | fk_doc_attachment_sid |

2.2.36.3 List of outgoing references of the table document_attachment

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_doc_attach__doc | document | fk_doc_sid | sid |

2.2.36.4 List of columns of the table document_attachment

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.doc_attachment_seq'::regclass) | The surrogate key |
| VERSION | integer | X | 1 | The system version. It is automatically increased by Hibernate each time the row is updated. |
| FK_DOC_SID | bigint | X |  | Foreign key to the document table. |
| MIME_TYPE | character varying(50) | X |  | The mime type of the document attachment. Possible values: <br>    APP_PDF <br>    APP_MSWORD <br>    APP_MSEXCEL <br>    APP_MSPOWERPOINT <br>    APP_OPENXML_DOC <br>    APP_OPENXML_SPREADSHEET <br>    APP_OPENXML_PRESENTATION <br>    APP_XML <br>    APP_ZIP <br>    APP_GZIP <br>    IMG_JPEG <br>    IMG_PNG <br>    IMG_TIFF <br>    TXT_RTF <br>    TXT_XML <br> <br>    // Mimetypes NOT included in the SBDH XSD definition <br>    APP_X_ZIP <br>    APP_OCTET_STREAM <br>    APP_X_ZIP_COMPRESSED |
| ID | character varying(255) | X |  | The document attachment id. |
| NAME | character varying(255) |  |  | The name of the attachement. |
| FILENAME | character varying(1024) |  |  | The directory path where the assignment is stored |
| PATHNAME | character varying(1024) | X |  | The complete pathname to retrieve the attachment. |
| IS_MEDICAL | boolean | X | false | The is medical flag. |
| IS_ACTIVE | boolean | X | true | The status of the attachemnt (false it has been deleted) |
| CREATED_AT | timestamp with time zone | X | '2024-06-03 16:57:26.547803+00'::timestamp with time zone | Date & Time of Creation. |
| UPDATED_AT | timestamp with time zone | X | '2024-06-03 16:57:26.547803+00'::timestamp with time zone | Date & time of last update. |
| CREATED_BY | character varying(255) | X | '0'::character varying | The person that created the record. |
| UPDATED_BY | character varying(255) | X | '0'::character varying | The person that last updated the record. |

2.2.36.5 List of keys of the table document_attachment

| Code | Columns | Primary |
| --- | --- | --- |
| pk_document_attachment | sid | X |

2.2.36.6 List of indexes of the table document_attachment

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| doc_attachement_idx | X |  | CREATE UNIQUE INDEX doc_attachement_idx ON rina.document_attachment USING btree (sid) |
| doc_attachment__doc_idx |  |  | CREATE INDEX doc_attachment__doc_idx ON rina.document_attachment USING btree (fk_doc_sid) |
| doc_attachment_id_unq | X |  | CREATE UNIQUE INDEX doc_attachment_id_unq ON rina.document_attachment USING btree (id, fk_doc_sid) |
| pk_document_attachment | X | X | CREATE UNIQUE INDEX pk_document_attachment ON rina.document_attachment USING btree (sid) |

2.2.36.7 Other constraints of the table document_attachment

_None._

2.2.37 Table document_bversion

2.2.37.1 Card of table document_bversion

| Code | Value |
| --- | --- |
| Code | DOCUMENT_BVERSION |
| Comment | The business version associated to a specific document |

2.2.37.2 List of incoming references of the table document_bversion

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| fk_doc_bversion_att__doc_bvers | doc_bversion_attachment | fk_doc_bversion_sid |
| fk_doc_bv_subdoc_bv__doc_bv | doc_bversion_subdoc_bversion | fk_doc_bversion_sid |
| fk_doc__doc_bversion | document | fk_doc_bversion_sid |
| fk_doc_conv__doc_bversion | document_conversation | fk_doc_bversion_sid |
| fk_doc_his__doc_bversion | document_history | fk_doc_bversion_sid |
| fk_doc_thumb__doc_bver | document_thumbnail | fk_doc_bversion_sid |

2.2.37.3 List of outgoing references of the table document_bversion

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_doc_bversion__doc | document | fk_doc_sid | sid |
| fk_doc_bversion__doc_content | document_content | fk_doc_content_sid | sid |

2.2.37.4 List of columns of the table document_bversion

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.document_bversion_seq'::regclass) | The surrogate key |
| FK_DOC_SID | bigint | X |  | Foreign key to the document table. |
| FK_DOC_CONTENT_SID | bigint |  |  | Foreign key to the document content table. |
| ID | integer | X | 1 | The id of the document bversion. |
| VERSION | integer | X | 1 | The system version. It is automatically increased by Hibernate each time the row is updated. |
| CREATED_AT | timestamp with time zone | X | '2024-06-03 16:57:26.58299+00'::timestamp with time zone | The time that the document bversion was first inserted into the DB |
| UPDATED_AT | timestamp with time zone | X | '2024-06-03 16:57:26.58299+00'::timestamp with time zone | The last time that the document bversion was updated |
| CREATED_BY | character varying(255) | X | '0'::character varying | The person that created the record. |
| UPDATED_BY | character varying(255) | X | '0'::character varying | The person that last updated the record. |
| ORIG_CREATED_AT | timestamp with time zone |  |  |  |

2.2.37.5 List of keys of the table document_bversion

| Code | Columns | Primary |
| --- | --- | --- |
| pk_document_bversion | sid | X |

2.2.37.6 List of indexes of the table document_bversion

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| doc_bversion__doc_content_idx |  |  | CREATE INDEX doc_bversion__doc_content_idx ON rina.document_bversion USING btree (fk_doc_content_sid) |
| doc_bversion__doc_idx |  |  | CREATE INDEX doc_bversion__doc_idx ON rina.document_bversion USING btree (fk_doc_sid) |
| doc_bversion_unq | X |  | CREATE UNIQUE INDEX doc_bversion_unq ON rina.document_bversion USING btree (fk_doc_sid, id) |
| document_bversion_idx | X |  | CREATE UNIQUE INDEX document_bversion_idx ON rina.document_bversion USING btree (sid) |
| pk_document_bversion | X | X | CREATE UNIQUE INDEX pk_document_bversion ON rina.document_bversion USING btree (sid) |

2.2.37.7 Other constraints of the table document_bversion

_None._

2.2.38 Table document_comment

2.2.38.1 Card of table document_comment

| Code | Value |
| --- | --- |
| Code | DOCUMENT_COMMENT |
| Comment | The comments associated to a specific document |

2.2.38.2 List of incoming references of the table document_comment

_None._

2.2.38.3 List of outgoing references of the table document_comment

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_doc_comment__doc | document | fk_doc_sid | sid |

2.2.38.4 List of columns of the table document_comment

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.doc_comment_seq'::regclass) | The surrogate key |
| VERSION | integer | X | 1 | The system version. It is automatically increased by Hibernate each time the row is updated. |
| FK_DOC_SID | bigint | X |  | Foreign key to the document table |
| ID | character varying(255) | X |  | The id of the document content. |
| TEXT | text | X |  | The comment |
| CREATED_AT | timestamp with time zone | X | '2024-06-03 16:57:26.636525+00'::timestamp with time zone | Date & Time the entity was created |
| UPDATED_AT | timestamp with time zone | X | '2024-06-03 16:57:26.636525+00'::timestamp with time zone | Date & Time the entity was last updated |
| CREATED_BY | character varying(255) | X | '0'::character varying | The person/process that created the record. |
| UPDATED_BY | character varying(255) | X | '0'::character varying | The person/process that last updated the record. |

2.2.38.5 List of keys of the table document_comment

| Code | Columns | Primary |
| --- | --- | --- |
| pk_document_comment | sid | X |

2.2.38.6 List of indexes of the table document_comment

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| doc_comment__doc_idx |  |  | CREATE INDEX doc_comment__doc_idx ON rina.document_comment USING btree (fk_doc_sid) |
| doc_comment_id_unq | X |  | CREATE UNIQUE INDEX doc_comment_id_unq ON rina.document_comment USING btree (id) |
| doc_comment_idx | X |  | CREATE UNIQUE INDEX doc_comment_idx ON rina.document_comment USING btree (sid) |
| pk_document_comment | X | X | CREATE UNIQUE INDEX pk_document_comment ON rina.document_comment USING btree (sid) |

2.2.38.7 Other constraints of the table document_comment

_None._

2.2.39 Table document_content

2.2.39.1 Card of table document_content

| Code | Value |
| --- | --- |
| Code | DOCUMENT_CONTENT |
| Comment | The content associated to a specific document |

2.2.39.2 List of incoming references of the table document_content

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| fk_doc_bversion__doc_content | document_bversion | fk_doc_content_sid |

2.2.39.3 List of outgoing references of the table document_content

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_doc_content__doc | document | fk_doc_sid | sid |

2.2.39.4 List of columns of the table document_content

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.document_content_seq'::regclass) | The surrogate key |
| FK_DOC_SID | bigint | X |  | Foreign key to the document table. |
| CONTENT | text | X |  | The content of the document. |
| IS_ACTIVE | boolean | X | true | The is active flag of the document content. |

2.2.39.5 List of keys of the table document_content

| Code | Columns | Primary |
| --- | --- | --- |
| pk_document_content | sid | X |

2.2.39.6 List of indexes of the table document_content

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| doc_content__doc_idx |  |  | CREATE INDEX doc_content__doc_idx ON rina.document_content USING btree (fk_doc_sid) |
| doc_content_idx | X |  | CREATE UNIQUE INDEX doc_content_idx ON rina.document_content USING btree (sid) |
| pk_document_content | X | X | CREATE UNIQUE INDEX pk_document_content ON rina.document_content USING btree (sid) |

2.2.39.7 Other constraints of the table document_content

_None._

2.2.40 Table document_conversation

2.2.40.1 Card of table document_conversation

| Code | Value |
| --- | --- |
| Code | DOCUMENT_CONVERSATION |
| Comment | The attachments associated to a specific document |

2.2.40.2 List of incoming references of the table document_conversation

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| fk_conv_participant__conv | conv_participant | fk_conv_sid |
| fk_user_msg__doc_conv | user_message | fk_doc_conv_sid |

2.2.40.3 List of outgoing references of the table document_conversation

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_doc_conv__doc | document | fk_doc_sid | sid |
| fk_doc_conv__doc_bversion | document_bversion | fk_doc_bversion_sid | sid |

2.2.40.4 List of columns of the table document_conversation

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.doc_conversation_seq'::regclass) | The surrogate key |
| FK_DOC_SID | bigint | X |  | Foreign key to the document table. |
| FK_DOC_BVERSION_SID | bigint |  |  | Foreign key to the document_bversion table. |
| ID | character varying(255) | X |  | The id of the document conversation. |
| DATE | timestamp with time zone |  |  | Date & Time of Creation. |
| RECEIVED_AT | timestamp with time zone |  |  | Date & Time when the conversation was received. |

2.2.40.5 List of keys of the table document_conversation

| Code | Columns | Primary |
| --- | --- | --- |
| pk_document_conversation | sid | X |

2.2.40.6 List of indexes of the table document_conversation

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| doc_conv__doc_bversion_idx |  |  | CREATE INDEX doc_conv__doc_bversion_idx ON rina.document_conversation USING btree (fk_doc_bversion_sid) |
| doc_conv__doc_idx |  |  | CREATE INDEX doc_conv__doc_idx ON rina.document_conversation USING btree (fk_doc_sid) |
| doc_conv_id_unq | X |  | CREATE UNIQUE INDEX doc_conv_id_unq ON rina.document_conversation USING btree (id) |
| doc_conversation_idx | X |  | CREATE UNIQUE INDEX doc_conversation_idx ON rina.document_conversation USING btree (sid) |
| pk_document_conversation | X | X | CREATE UNIQUE INDEX pk_document_conversation ON rina.document_conversation USING btree (sid) |

2.2.40.7 Other constraints of the table document_conversation

_None._

2.2.41 Table document_history

2.2.41.1 Card of table document_history

| Code | Value |
| --- | --- |
| Code | DOCUMENT_HISTORY |
| Comment | The history of the document |

2.2.41.2 List of incoming references of the table document_history

_None._

2.2.41.3 List of outgoing references of the table document_history

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_doc_his__case | rina_case | fk_case_sid | sid |
| fk_doc_his__doc | document | fk_doc_sid | sid |
| fk_doc_his__doc_bversion | document_bversion | fk_doc_bversion_sid | sid |
| fk_doc_his__doc_type_version | document_type_version | fk_doc_type_version_sid | sid |

2.2.41.4 List of columns of the table document_history

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.document_history_seq'::regclass) | The surrogate key |
| FK_DOC_SID | bigint | X |  | Foreign key to the document table |
| FK_CASE_SID | bigint |  |  | Foreign key to the rina_case table |
| FK_DOC_TYPE_VERSION_SID | bigint | X |  | Foreign key to the document type version table. |
| FK_DOC_BVERSION_SID | bigint |  |  | Foreign key to the doc_bversion table. |
| VERSION | integer | X |  | The system version of the correspospnding document. The value is set to that of the current entry of the document after the last update. |
| ID | character varying(255) | X |  | the id of the document |
| NAME | character varying(255) |  |  | The name of the document history. |
| DISPLAY_NAME | character varying(255) |  |  | The display name of the Document |
| STATUS | character varying(20) |  |  | The status of the Document. Possible values: <br>    NEW("new"), <br>    EMPTY("empty"), <br>    ACTIVE("active"), <br>    SENT("sent"), <br>    CANCELLED("cancelled"), <br>    RECEIVED("received"); |
| BUSINESS_VERSION_ID | character varying(255) |  |  | The business version id value. |
| INTERNAL_ID | character varying(255) |  |  | The internal id. |
| DM_PROCESS_ID | bigint |  |  | The process id of the document manager |
| SUB_PROCESS_ID | bigint |  |  | The subprocess id |
| CREATE_TEMPLATE | character varying(255) |  |  | Template for creating the document |
| DIRECTION | character varying(255) |  |  | The direction of the Document |
| MIME_TYPE | character varying(255) |  |  | The mime type. |
| DOC_ORDER | integer |  |  | The order of the document |
| TO_SENDER_ONLY | boolean |  |  | TRUE If the document is only to sender |
| IS_ADMIN | boolean |  |  | TRUE If this is an admin document |
| IS_BULK | boolean |  |  | Whether or not the document is a Bulk(Batch) Document |
| IS_DUMMY_DOCUMENT | boolean | X | false | True if the document is just a dummy. |
| IS_FIRST_DOCUMENT | boolean |  |  | TRUE if this is the first document |
| IS_MLC | boolean |  |  | TRUE if this is MLC document |
| IS_STARTER | boolean |  |  | If document already sent |
| IS_SEND_EXECUTED | boolean |  |  | TRUE If document already sent |
| HAS_REPLY_CLARIFY | boolean |  |  | TRUE if it has reply clarify |
| HAS_REJECT | boolean |  |  | TRUE if it has reject |
| HAS_LETTER | boolean |  |  | TRUE if it has letter |
| HAS_CLARIFY | boolean |  |  | TRUE if it has clarify |
| HAS_CANCEL | boolean |  |  | TRUE if it has cancel |
| HAS_BUSINESS_VALIDATION | boolean | X | false | Requires any business side validation before any action. Default is false. |
| HAS_MULTIPLE_VERSIONS | boolean |  |  | TRUE if the document has multiple versions |
| SELECT_PARTICIPANTS | boolean |  |  | TRUE If select participant |
| ALLOWS_ATTACHMENTS | boolean | X | false | The document allows having attachments. Default is false. |
| CAN_BE_SENT_WITHOUT_CHILD | boolean |  |  | True if the document can be sent without any children. |
| UPDATED_AT | timestamp with time zone | X |  | The time that the document was updated |
| UPDATED_BY | character varying(255) | X |  | The person/process that last updated the record. |

2.2.41.5 List of keys of the table document_history

| Code | Columns | Primary |
| --- | --- | --- |
| pk_document_history | sid | X |

2.2.41.6 List of indexes of the table document_history

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| doc_his__doc_bversion_idx |  |  | CREATE INDEX doc_his__doc_bversion_idx ON rina.document_history USING btree (fk_doc_bversion_sid) |
| doc_his__doc_idx |  |  | CREATE INDEX doc_his__doc_idx ON rina.document_history USING btree (fk_doc_sid) |
| doc_his__doc_type_version_idx |  |  | CREATE INDEX doc_his__doc_type_version_idx ON rina.document_history USING btree (fk_doc_type_version_sid) |
| doc_his_doc_sid_version_unq | X |  | CREATE UNIQUE INDEX doc_his_doc_sid_version_unq ON rina.document_history USING btree (fk_doc_sid, version) |
| doc_his_idx | X |  | CREATE UNIQUE INDEX doc_his_idx ON rina.document_history USING btree (sid) |
| pk_document_history | X | X | CREATE UNIQUE INDEX pk_document_history ON rina.document_history USING btree (sid) |

2.2.41.7 Other constraints of the table document_history

_None._

2.2.42 Table document_thumbnail

2.2.42.1 Card of table document_thumbnail

| Code | Value |
| --- | --- |
| Code | DOCUMENT_THUMBNAIL |
| Comment | Many-to-one association between document_bversion entries and document_thmbnail entries |

2.2.42.2 List of incoming references of the table document_thumbnail

_None._

2.2.42.3 List of outgoing references of the table document_thumbnail

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_doc_thumb__doc_bver | document_bversion | fk_doc_bversion_sid | sid |

2.2.42.4 List of columns of the table document_thumbnail

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.doc_thumbnail_seq'::regclass) | The surrogate key |
| FK_DOC_BVERSION_SID | bigint | X |  | Foreign key to the doc_bversion table. |
| LANG | character varying(2) | X |  | The language of the document thumbnail. Possible values: <br>    bg, <br>    cs, <br>    da, <br>    de, <br>    en, <br>    el, <br>    es, <br>    et, <br>    fi, <br>    fr, <br>    hr, <br>    hu, <br>    it, <br>    lt, <br>    lv, <br>    mt, <br>    nl, <br>    no, <br>    pl, <br>    pt, <br>    ro, <br>    sk, <br>    sl, <br>    sv. |
| CONTENT | text | X |  | The content of the thumbnail for the document. |

2.2.42.5 List of keys of the table document_thumbnail

| Code | Columns | Primary |
| --- | --- | --- |
| pk_document_thumbnail | sid | X |

2.2.42.6 List of indexes of the table document_thumbnail

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| doc_thumb__doc_bver_idx |  |  | CREATE INDEX doc_thumb__doc_bver_idx ON rina.document_thumbnail USING btree (fk_doc_bversion_sid) |
| doc_thumbnail_idx | X |  | CREATE UNIQUE INDEX doc_thumbnail_idx ON rina.document_thumbnail USING btree (sid) |
| pk_document_thumbnail | X | X | CREATE UNIQUE INDEX pk_document_thumbnail ON rina.document_thumbnail USING btree (sid) |

2.2.42.7 Other constraints of the table document_thumbnail

_None._

2.2.43 Table document_type

2.2.43.1 Card of table document_type

| Code | Value |
| --- | --- |
| Code | DOCUMENT_TYPE |
| Comment | The type of document |

2.2.43.2 List of incoming references of the table document_type

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| fk_doc_type__doc_type_version | document_type_version | fk_doc_type_sid |
| fk_nie_event__doc_type | nie_event | fk_doc_type_sid |
| fk_nie_subs_fk_subscr_document | nie_subscriber | fk_document_type_sid |
| fk_notif__doc_type | notification | fk_document_type_sid |

2.2.43.3 List of outgoing references of the table document_type

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_doc_type__proc_def_version | process_def_version | fk_proc_def_version_sid | sid |

2.2.43.4 List of columns of the table document_type

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.doc_type_seq'::regclass) | The surrogate key |
| FK_PROC_DEF_VERSION_SID | bigint |  |  | Foreign key that links the Case to the process definition's version  table |
| TYPE | character varying(255) | X |  | The type of document |
| NAME | character varying(255) |  |  | The name of the document type. |

2.2.43.5 List of keys of the table document_type

| Code | Columns | Primary |
| --- | --- | --- |
| pk_document_type | sid | X |

2.2.43.6 List of indexes of the table document_type

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| doc_type__proc_def_version_idx |  |  | CREATE INDEX doc_type__proc_def_version_idx ON rina.document_type USING btree (fk_proc_def_version_sid) |
| doc_type_idx | X |  | CREATE UNIQUE INDEX doc_type_idx ON rina.document_type USING btree (sid) |
| doc_type_type_unq | X |  | CREATE UNIQUE INDEX doc_type_type_unq ON rina.document_type USING btree (type) |
| pk_document_type | X | X | CREATE UNIQUE INDEX pk_document_type ON rina.document_type USING btree (sid) |

2.2.43.7 Other constraints of the table document_type

_None._

2.2.44 Table document_type_version

2.2.44.1 Card of table document_type_version

| Code | Value |
| --- | --- |
| Code | DOCUMENT_TYPE_VERSION |
| Comment | The version of the document type |

2.2.44.2 List of incoming references of the table document_type_version

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| fk_action__doc_type_ver | action | fk_doc_type_version_sid |
| fk_doc__doc_type_version | document | fk_doc_type_version_sid |
| fk_doc_his__doc_type_version | document_history | fk_doc_type_version_sid |
| fk_transpos__doc_type_version | transposition | fk_doc_type_version_sid |

2.2.44.3 List of outgoing references of the table document_type_version

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_doc_type__doc_type_version | document_type | fk_doc_type_sid | sid |

2.2.44.4 List of columns of the table document_type_version

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.doc_type_version_seq'::regclass) | The surrogate key |
| FK_DOC_TYPE_SID | bigint | X |  | Foreign key to document_type table |
| BVERSION | character varying(10) | X |  | The bversion value for the document type version. |
| DEFAULT_DOC_CONTENT | text |  |  | The default document content |
| METADATA | text |  |  | The metadata of the document type version. |

2.2.44.5 List of keys of the table document_type_version

| Code | Columns | Primary |
| --- | --- | --- |
| pk_document_type_version | sid | X |

2.2.44.6 List of indexes of the table document_type_version

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| doc_type_type_version_unq | X |  | CREATE UNIQUE INDEX doc_type_type_version_unq ON rina.document_type_version USING btree (fk_doc_type_sid, bversion) |
| doc_type_version_idx | X |  | CREATE UNIQUE INDEX doc_type_version_idx ON rina.document_type_version USING btree (sid) |
| pk_document_type_version | X | X | CREATE UNIQUE INDEX pk_document_type_version ON rina.document_type_version USING btree (sid) |

2.2.44.7 Other constraints of the table document_type_version

_None._

2.2.45 Table field

2.2.45.1 Card of table field

| Code | Value |
| --- | --- |
| Code | FIELD |
| Comment | Fields to be shown in Case Search Results |

2.2.45.2 List of incoming references of the table field

_None._

2.2.45.3 List of outgoing references of the table field

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_field__field_chooser | field_chooser | fk_field_chooser_sid | sid |

2.2.45.4 List of columns of the table field

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.field_seq'::regclass) | The surogate key. |
| FK_FIELD_CHOOSER_SID | bigint | X |  | Foreign key to the field_chooser table |
| ID | character varying(255) | X |  | The id of the field. |
| NAME | character varying(255) | X |  | The name of the field |
| TYPE | character varying(50) |  |  | The type of the field. Possible values: Long, Integer, Double, null. |
| SORT | character varying(60) | X | 'none'::character varying | The direction that the values of the Field will be sorted Can be either 'ASCENDING', 'DESCENDING' or 'NONE' |
| SHOW | boolean | X | false | The flag to determine if the Field is to be shown or not |

2.2.45.5 List of keys of the table field

| Code | Columns | Primary |
| --- | --- | --- |
| pk_field | sid | X |

2.2.45.6 List of indexes of the table field

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| field_field_chooser_name_unq | X |  | CREATE UNIQUE INDEX field_field_chooser_name_unq ON rina.field USING btree (name, fk_field_chooser_sid) |
| field_idx | X |  | CREATE UNIQUE INDEX field_idx ON rina.field USING btree (sid) |
| fiield__field_chooser_idx |  |  | CREATE INDEX fiield__field_chooser_idx ON rina.field USING btree (fk_field_chooser_sid) |
| pk_field | X | X | CREATE UNIQUE INDEX pk_field ON rina.field USING btree (sid) |

2.2.45.7 Other constraints of the table field

_None._

2.2.46 Table field_chooser

2.2.46.1 Card of table field_chooser

| Code | Value |
| --- | --- |
| Code | FIELD_CHOOSER |
| Comment | Table for associating with  the list of Fields to be shown in Case Search Results |

2.2.46.2 List of incoming references of the table field_chooser

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| fk_field__field_chooser | field | fk_field_chooser_sid |

2.2.46.3 List of outgoing references of the table field_chooser

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_field_chooser__process_def | process_def | fk_process_def_sid | sid |
| fk_field_chooser__user | iam_user | fk_user_sid | sid |

2.2.46.4 List of columns of the table field_chooser

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.field_chooser_seq'::regclass) | The surrogate key |
| FK_USER_SID | bigint | X |  | Foreign key to the iam_user table |
| FK_PROCESS_DEF_SID | bigint | X |  | Foreign key to the process_definition table |

2.2.46.5 List of keys of the table field_chooser

| Code | Columns | Primary |
| --- | --- | --- |
| pk_field_chooser | sid | X |

2.2.46.6 List of indexes of the table field_chooser

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| chooser__process_def_idx |  |  | CREATE INDEX chooser__process_def_idx ON rina.field_chooser USING btree (fk_process_def_sid) |
| chooser__user_idx |  |  | CREATE INDEX chooser__user_idx ON rina.field_chooser USING btree (fk_user_sid) |
| chooser_idx | X |  | CREATE UNIQUE INDEX chooser_idx ON rina.field_chooser USING btree (sid) |
| chooser_user_process_def_unq | X |  | CREATE UNIQUE INDEX chooser_user_process_def_unq ON rina.field_chooser USING btree (fk_user_sid, fk_process_def_sid) |
| pk_field_chooser | X | X | CREATE UNIQUE INDEX pk_field_chooser ON rina.field_chooser USING btree (sid) |

2.2.46.7 Other constraints of the table field_chooser

_None._

2.2.47 Table global_param

2.2.47.1 Card of table global_param

| Code | Value |
| --- | --- |
| Code | GLOBAL_PARAM |
| Comment | The global application parameters. |

2.2.47.2 List of incoming references of the table global_param

_None._

2.2.47.3 List of outgoing references of the table global_param

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_glbl_param__glbl_param_grp | global_param_group | fk_global_param_group_sid | sid |

2.2.47.4 List of columns of the table global_param

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.global_param_seq'::regclass) | The surrogate key |
| FK_GLOBAL_PARAM_GROUP_SID | bigint |  |  | Foreign key to the global param group table. |
| KEY | character varying(255) | X |  | The key of the parameter |
| VALUE | character varying(255) |  |  | the value of the parameter |

2.2.47.5 List of keys of the table global_param

| Code | Columns | Primary |
| --- | --- | --- |
| pk_global_param | sid | X |

2.2.47.6 List of indexes of the table global_param

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| glbl_prm__glbl_prm_grp_idx |  |  | CREATE INDEX glbl_prm__glbl_prm_grp_idx ON rina.global_param USING btree (fk_global_param_group_sid) |
| global_param_idx | X |  | CREATE UNIQUE INDEX global_param_idx ON rina.global_param USING btree (sid) |
| global_param_key_unq | X |  | CREATE UNIQUE INDEX global_param_key_unq ON rina.global_param USING btree (key) |
| pk_global_param | X | X | CREATE UNIQUE INDEX pk_global_param ON rina.global_param USING btree (sid) |

2.2.47.7 Other constraints of the table global_param

_None._

2.2.48 Table global_param_group

2.2.48.1 Card of table global_param_group

| Code | Value |
| --- | --- |
| Code | GLOBAL_PARAM_GROUP |
| Comment | Table that holds a group of global_application_parameters, with version for optimistic locking and auditing properties. |

2.2.48.2 List of incoming references of the table global_param_group

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| fk_glbl_param__glbl_param_grp | global_param | fk_global_param_group_sid |

2.2.48.3 List of outgoing references of the table global_param_group

_None._

2.2.48.4 List of columns of the table global_param_group

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.global_param_group_seq'::regclass) | The surrogate key |
| VERSION | integer | X | 1 | The system version. It is automatically increased by Hibernate each time the row is updated. |
| NAME | character varying(255) | X |  | The name of the global param group. Possible values: <br>TEST. |
| CREATED_AT | timestamp with time zone | X | '2024-06-03 16:57:27.054567+00'::timestamp with time zone | Date & Time by whom the tenant was created |
| UPDATED_AT | timestamp with time zone | X | '2024-06-03 16:57:27.054567+00'::timestamp with time zone | Date & Time the tenant's details was updated |
| CREATED_BY | character varying(255) | X | '0'::character varying | The person/process that created the record. |
| UPDATED_BY | character varying(255) | X | '0'::character varying | The person/process that last updated the record. |
| RANDOM_STRING | character varying(255) | X | 'A1'::character varying | Random string saved for the global param group. |

2.2.48.5 List of keys of the table global_param_group

| Code | Columns | Primary |
| --- | --- | --- |
| pk_global_param_group | sid | X |

2.2.48.6 List of indexes of the table global_param_group

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| global_param_group_idx | X |  | CREATE UNIQUE INDEX global_param_group_idx ON rina.global_param_group USING btree (sid) |
| global_param_group_name_unq | X |  | CREATE UNIQUE INDEX global_param_group_name_unq ON rina.global_param_group USING btree (name) |
| pk_global_param_group | X | X | CREATE UNIQUE INDEX pk_global_param_group ON rina.global_param_group USING btree (sid) |

2.2.48.7 Other constraints of the table global_param_group

_None._

2.2.49 Table iam_group

2.2.49.1 Card of table iam_group

| Code | Value |
| --- | --- |
| Code | IAM_GROUP |
| Comment | Group Details |

2.2.49.2 List of incoming references of the table iam_group

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| fk_assign_group__group | assignment_group | fk_group_sid |
| fk_iam_group__iam_group | iam_group | fk_parent_sid |
| fk_iam_usergroup__group | iam_user_group | fk_group_sid |
| fk_rule_creator_group__group | rule_creator_group | fk_group_sid |
| fk_rule_group__group | rule_group | fk_group_sid |
| fk_search_def_group__group | search_def_group | fk_iam_group_sid |

2.2.49.3 List of outgoing references of the table iam_group

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_group__origin | iam_origin | fk_origin_sid | sid |
| fk_iam_group__iam_group | iam_group | fk_parent_sid | sid |
| fk_iam_group__tenant | tenant | fk_tenant_sid | sid |

2.2.49.4 List of columns of the table iam_group

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.iam_group_seq'::regclass) | the surrogate key |
| VERSION | integer | X | 1 | The system version. It is automatically increased by Hibernate each time the row is updated. |
| FK_ORIGIN_SID | bigint |  |  | Foreign key to the origin table |
| FK_TENANT_SID | bigint | X |  | Foreign key to the tenant table |
| FK_PARENT_SID | bigint |  |  | Foreign key to parent entry of the iam_group table |
| NAME | character varying(255) | X |  | The name of the group |
| ID | character varying(255) | X |  | The id. |
| DISPLAY_NAME | character varying(255) | X |  | The display name of the Group |
| PARENT_PATH | character varying(1024) |  |  | The path to the parent. |
| DESCRIPTION | character varying(255) |  |  | The description of the Group |
| IS_DELETED | boolean | X | false | Flag indicating if this group is deleted |
| IS_ORGANISATION_UNIT | boolean | X | true | The is organisation unit flag. |
| CREATED_AT | timestamp with time zone | X | '2024-06-03 16:57:27.078061+00'::timestamp with time zone | The time that the group was first inserted into the DB |
| UPDATED_AT | timestamp with time zone | X | '2024-06-03 16:57:27.078061+00'::timestamp with time zone | The last time that the group  was updated |
| CREATED_BY | character varying(255) | X | '0'::character varying | The person/process that created the record. |
| UPDATED_BY | character varying(255) | X | '0'::character varying | The person/process that last updated the record. |

2.2.49.5 List of keys of the table iam_group

| Code | Columns | Primary |
| --- | --- | --- |
| pk_iam_group | sid | X |

2.2.49.6 List of indexes of the table iam_group

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| group__origin_idx |  |  | CREATE INDEX group__origin_idx ON rina.iam_group USING btree (fk_origin_sid) |
| group__tenant_idx |  |  | CREATE INDEX group__tenant_idx ON rina.iam_group USING btree (fk_tenant_sid) |
| group_id_unq | X |  | CREATE UNIQUE INDEX group_id_unq ON rina.iam_group USING btree (id) |
| group_idx | X |  | CREATE UNIQUE INDEX group_idx ON rina.iam_group USING btree (sid) |
| group_name_unq | X |  | CREATE UNIQUE INDEX group_name_unq ON rina.iam_group USING btree (name, fk_tenant_sid, parent_path) WHERE (is_deleted IS FALSE) |
| group_name_with_null_parent_unq | X |  | CREATE UNIQUE INDEX group_name_with_null_parent_unq ON rina.iam_group USING btree (name, fk_tenant_sid) WHERE ((parent_path IS NULL) AND (is_deleted IS FALSE)) |
| pk_iam_group | X | X | CREATE UNIQUE INDEX pk_iam_group ON rina.iam_group USING btree (sid) |

2.2.49.7 Other constraints of the table iam_group

_None._

2.2.50 Table iam_origin

2.2.50.1 Card of table iam_origin

| Code | Value |
| --- | --- |
| Code | IAM_ORIGIN |
| Comment | Origin details (Used for LDAP purposes) |

2.2.50.2 List of incoming references of the table iam_origin

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| fk_group__origin | iam_group | fk_origin_sid |
| fk_origin__user | iam_user | fk_origin_sid |

2.2.50.3 List of outgoing references of the table iam_origin

_None._

2.2.50.4 List of columns of the table iam_origin

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.iam_origin_seq'::regclass) | The surrogate key |
| NAME | character varying(255) | X |  | The name of the origin |
| DESCRIPTION | character varying(255) |  |  | Description of origin |

2.2.50.5 List of keys of the table iam_origin

| Code | Columns | Primary |
| --- | --- | --- |
| pk_user_origin | sid | X |

2.2.50.6 List of indexes of the table iam_origin

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| origin_idx | X |  | CREATE UNIQUE INDEX origin_idx ON rina.iam_origin USING btree (sid) |
| origin_name_unq | X |  | CREATE UNIQUE INDEX origin_name_unq ON rina.iam_origin USING btree (name) |
| pk_user_origin | X | X | CREATE UNIQUE INDEX pk_user_origin ON rina.iam_origin USING btree (sid) |

2.2.50.7 Other constraints of the table iam_origin

_None._

2.2.51 Table iam_user

2.2.51.1 Card of table iam_user

| Code | Value |
| --- | --- |
| Code | IAM_USER |
| Comment | User details |

2.2.51.2 List of incoming references of the table iam_user

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| fk_assign_user__user | assignment_user | fk_user_sid |
| fk_field_chooser__user | field_chooser | fk_user_sid |
| fk_iam_usergroup__user | iam_user_group | fk_user_sid |
| fk_notif__iam_user | notification | fk_creator_sid |
| fk_notif_user__user | notification_user | fk_user_sid |
| fk_rule_creator_user__user | rule_creator_user | fk_user_sid |
| fk_rule_user__user | rule_user | fk_user_sid |
| fk_search_def_user__user | search_def_user | fk_iam_user_sid |
| fk_search_d_fk_iam_us_iam_user | search_definition | fk_iam_user_sid |
| fk_user_profile__user | user_profile | fk_user_sid |

2.2.51.3 List of outgoing references of the table iam_user

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_iam_user__tenant | tenant | fk_tenant_sid | sid |
| fk_origin__user | iam_origin | fk_origin_sid | sid |

2.2.51.4 List of columns of the table iam_user

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.iam_user_seq'::regclass) | The surrogate key |
| VERSION | integer | X | 1 | The system version. It is automatically increased by Hibernate each time the row is updated. |
| FK_ORIGIN_SID | bigint |  |  | Foreign key to the origin table |
| FK_TENANT_SID | bigint |  |  | Foreign key to the tenant table |
| USERNAME | character varying(255) | X |  | The username of the User |
| ID | character varying(255) | X |  | The id of the iam user. |
| FIRST_NAME | character varying(255) | X |  | The first name of the User |
| LAST_NAME | character varying(255) | X |  | The last name of the User |
| MIDDLE_NAMES | character varying(255) |  |  | The middle names of the User |
| PHONE_NUMBER | character varying(255) |  |  |  |
| EMAIL | character varying(255) |  |  | The email address of the User |
| KEYSTORE_ALIAS | character varying(1024) |  |  |  |
| PASSWORD | character varying(255) |  |  | The password of the User |
| SALT | character varying(255) | X | 'salt'::character varying | Salt field used for encrypting the password |
| IS_SYSTEM | boolean | X | false | The is system flag. |
| IS_ENABLED | boolean | X | true | True is the user is enabled |
| IS_DELETED | boolean | X | false | Flag indicating if this user is deleted |
| IS_ADMIN | boolean | X | false | Flag indicating if this user is an administrator |
| CREATED_AT | timestamp with time zone | X | '2024-06-03 16:57:27.212685+00'::timestamp with time zone | The time that the user was first inserted into the DB |
| UPDATED_AT | timestamp with time zone | X | '2024-06-03 16:57:27.212685+00'::timestamp with time zone | The last time that the user was updated |
| CREATED_BY | character varying(255) | X | '0'::character varying | The person/process that created the record. |
| UPDATED_BY | character varying(255) | X | '0'::character varying | The person/process that last updated the record. |

2.2.51.5 List of keys of the table iam_user

| Code | Columns | Primary |
| --- | --- | --- |
| pk_iam_user | sid | X |

2.2.51.6 List of indexes of the table iam_user

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| pk_iam_user | X | X | CREATE UNIQUE INDEX pk_iam_user ON rina.iam_user USING btree (sid) |
| user__origin_idx |  |  | CREATE INDEX user__origin_idx ON rina.iam_user USING btree (fk_origin_sid) |
| user__tenant_idx |  |  | CREATE INDEX user__tenant_idx ON rina.iam_user USING btree (fk_tenant_sid) |
| user_id_unq | X |  | CREATE UNIQUE INDEX user_id_unq ON rina.iam_user USING btree (id) |
| user_idx | X |  | CREATE UNIQUE INDEX user_idx ON rina.iam_user USING btree (sid) |
| user_username_unq | X |  | CREATE UNIQUE INDEX user_username_unq ON rina.iam_user USING btree (username) WHERE (is_deleted IS FALSE) |

2.2.51.7 Other constraints of the table iam_user

_None._

2.2.52 Table iam_user_group

2.2.52.1 Card of table iam_user_group

| Code | Value |
| --- | --- |
| Code | IAM_USER_GROUP |
| Comment | Many-to-many association between users (iam_user table) and groups (iam_group table) |

2.2.52.2 List of incoming references of the table iam_user_group

_None._

2.2.52.3 List of outgoing references of the table iam_user_group

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_iam_usergroup__group | iam_group | fk_group_sid | sid |
| fk_iam_usergroup__user | iam_user | fk_user_sid | sid |
| fk_user_group__role | role | fk_role_sid | sid |

2.2.52.4 List of columns of the table iam_user_group

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.iam_user_group_seq'::regclass) | The surrogate key |
| FK_USER_SID | bigint | X |  | Foreign key to the iam_user table |
| FK_GROUP_SID | bigint | X |  | Foreign key to the iam_group table |
| FK_ROLE_SID | bigint |  |  | Foreign key to role table |

2.2.52.5 List of keys of the table iam_user_group

| Code | Columns | Primary |
| --- | --- | --- |
| pk_iam_user_group | sid | X |

2.2.52.6 List of indexes of the table iam_user_group

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| pk_iam_user_group | X | X | CREATE UNIQUE INDEX pk_iam_user_group ON rina.iam_user_group USING btree (sid) |
| user_group__group_idx |  |  | CREATE INDEX user_group__group_idx ON rina.iam_user_group USING btree (fk_group_sid) |
| user_group__role_idx |  |  | CREATE INDEX user_group__role_idx ON rina.iam_user_group USING btree (fk_role_sid) |
| user_group__user_idx |  |  | CREATE INDEX user_group__user_idx ON rina.iam_user_group USING btree (fk_user_sid) |
| user_group_idx | X |  | CREATE UNIQUE INDEX user_group_idx ON rina.iam_user_group USING btree (sid) |

2.2.52.7 Other constraints of the table iam_user_group

_None._

2.2.53 Table nie_event

2.2.53.1 Card of table nie_event

| Code | Value |
| --- | --- |
| Code | NIE_EVENT |
| Comment | Table that hold information about the NIE's events. |

2.2.53.2 List of incoming references of the table nie_event

_None._

2.2.53.3 List of outgoing references of the table nie_event

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_nie_event__doc_type | document_type | fk_doc_type_sid | sid |
| fk_nie_event__proc_def_version | process_def_version | fk_process_def_version_sid | sid |

2.2.53.4 List of columns of the table nie_event

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.nie_event_seq'::regclass) | The surrogate key |
| FK_PROCESS_DEF_VERSION_SID | bigint |  |  | Foreign key to the process def version table. |
| FK_DOC_TYPE_SID | bigint |  |  | Foreign key to document_type_version table |
| EVENT_TYPE | character varying(255) | X |  | The name of the subscription  |
| STATUS | character varying(20) | X | 'NEW'::character varying | The status of the nie event. Possible values: <br> NEW, <br>  PROCESSING, <br>  RETRY, <br>  CANCELED; |
| RETRIES | integer | X | 0 | The nr of retries. |
| USER_ID | character varying(255) |  |  | The id of the user. |
| PID | character varying(255) |  |  | The process identification value. |
| PAYLOAD | text | X |  | The payload of the nie event. |
| CREATED_AT | timestamp with time zone | X | '2024-06-03 16:57:27.32432+00'::timestamp with time zone | Date & Time of Creation. |
| UPDATED_AT | timestamp with time zone | X | '2024-06-03 16:57:27.32432+00'::timestamp with time zone | Date & time of last update. |
| NEXT_ATTEMPT_AT | timestamp with time zone |  |  | The next date when the event is schedulled. |
| HTTP_ERROR_CODE | integer |  |  | The http error code of the nie event that failed. |
| ERROR_MESSAGE | text |  |  | The error message of the nie event that failed. |

2.2.53.5 List of keys of the table nie_event

| Code | Columns | Primary |
| --- | --- | --- |
| pk_nie_event | sid | X |

2.2.53.6 List of indexes of the table nie_event

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| nie_event__doc_type_idx |  |  | CREATE INDEX nie_event__doc_type_idx ON rina.nie_event USING btree (fk_doc_type_sid) |
| nie_event__proc_def_version_idx |  |  | CREATE INDEX nie_event__proc_def_version_idx ON rina.nie_event USING btree (fk_process_def_version_sid) |
| nie_event__status_idx |  |  | CREATE INDEX nie_event__status_idx ON rina.nie_event USING btree (status) |
| nie_event__status_next_att_idx |  |  | CREATE INDEX nie_event__status_next_att_idx ON rina.nie_event USING btree (status, next_attempt_at) |
| nie_event__status_pid_idx |  |  | CREATE INDEX nie_event__status_pid_idx ON rina.nie_event USING btree (status, pid) |
| nie_event__status_updated_idx |  |  | CREATE INDEX nie_event__status_updated_idx ON rina.nie_event USING btree (status, updated_at) |
| nie_event_idx | X |  | CREATE UNIQUE INDEX nie_event_idx ON rina.nie_event USING btree (sid) |
| pk_nie_event | X | X | CREATE UNIQUE INDEX pk_nie_event ON rina.nie_event USING btree (sid) |

2.2.53.7 Other constraints of the table nie_event

_None._

2.2.54 Table nie_listener

2.2.54.1 Card of table nie_listener

| Code | Value |
| --- | --- |
| Code | NIE_LISTENER |
| Comment | Table that holds NIE's listeners |

2.2.54.2 List of incoming references of the table nie_listener

_None._

2.2.54.3 List of outgoing references of the table nie_listener

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_listener__subscription | nie_subscription | fk_nie_subscription_sid | sid |

2.2.54.4 List of columns of the table nie_listener

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.nie_listener_seq'::regclass) | The surrogate key |
| FK_NIE_SUBSCRIPTION_SID | bigint | X |  | Foreign key to the table nie_event_subscription |
| ID | character varying(255) | X |  | The id of the nie listener |
| URL | character varying(1024) | X |  | The listener |
| LABEL | character varying(255) |  |  | The label of the listener |

2.2.54.5 List of keys of the table nie_listener

| Code | Columns | Primary |
| --- | --- | --- |
| pk_nie_listener | sid | X |

2.2.54.6 List of indexes of the table nie_listener

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| nie_listener_idx | X |  | CREATE UNIQUE INDEX nie_listener_idx ON rina.nie_listener USING btree (sid) |
| nie_listener_subscription_idx |  |  | CREATE INDEX nie_listener_subscription_idx ON rina.nie_listener USING btree (fk_nie_subscription_sid) |
| pk_nie_listener | X | X | CREATE UNIQUE INDEX pk_nie_listener ON rina.nie_listener USING btree (sid) |

2.2.54.7 Other constraints of the table nie_listener

_None._

2.2.55 Table nie_subscriber

2.2.55.1 Card of table nie_subscriber

| Code | Value |
| --- | --- |
| Code | NIE_SUBSCRIBER |
| Comment | Table that holds NIE subscriber |

2.2.55.2 List of incoming references of the table nie_subscriber

_None._

2.2.55.3 List of outgoing references of the table nie_subscriber

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_nie_subs_fk_subscr_document | document_type | fk_document_type_sid | sid |
| fk_subscrbr__process_def_ver | process_def_version | fk_process_def_version_sid | sid |
| fk_subscriber__subscription | nie_subscription | fk_nie_subscription_sid | sid |

2.2.55.4 List of columns of the table nie_subscriber

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.nie_subscriber_seq'::regclass) | The surrogate key |
| FK_NIE_SUBSCRIPTION_SID | bigint | X |  | Foreign key to the table nie_event_subscription  |
| FK_PROCESS_DEF_VERSION_SID | bigint |  |  | Foreign key to the process def version table. |
| FK_DOCUMENT_TYPE_SID | bigint |  |  | Foreign key to the document type table. |
| ID | character varying(255) | X |  | The id of NIE subscriber |

2.2.55.5 List of keys of the table nie_subscriber

| Code | Columns | Primary |
| --- | --- | --- |
| pk_nie_subscriber | sid | X |

2.2.55.6 List of indexes of the table nie_subscriber

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| nie_subscriber_idx | X |  | CREATE UNIQUE INDEX nie_subscriber_idx ON rina.nie_subscriber USING btree (sid) |
| pk_nie_subscriber | X | X | CREATE UNIQUE INDEX pk_nie_subscriber ON rina.nie_subscriber USING btree (sid) |
| subscriber_document_type_unq | X |  | CREATE UNIQUE INDEX subscriber_document_type_unq ON rina.nie_subscriber USING btree (fk_document_type_sid) WHERE (fk_document_type_sid IS NOT NULL) |
| subscriber_proc_def_version_unq | X |  | CREATE UNIQUE INDEX subscriber_proc_def_version_unq ON rina.nie_subscriber USING btree (fk_process_def_version_sid) WHERE (fk_process_def_version_sid IS NOT NULL) |
| subscriber_subscription_idx |  |  | CREATE INDEX subscriber_subscription_idx ON rina.nie_subscriber USING btree (fk_nie_subscription_sid) |

2.2.55.7 Other constraints of the table nie_subscriber

_None._

2.2.56 Table nie_subscription

2.2.56.1 Card of table nie_subscription

| Code | Value |
| --- | --- |
| Code | NIE_SUBSCRIPTION |
| Comment | Table that hold information about the NIE's event subscription. |

2.2.56.2 List of incoming references of the table nie_subscription

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| fk_listener__subscription | nie_listener | fk_nie_subscription_sid |
| fk_subscriber__subscription | nie_subscriber | fk_nie_subscription_sid |

2.2.56.3 List of outgoing references of the table nie_subscription

_None._

2.2.56.4 List of columns of the table nie_subscription

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.nie_subscription_seq'::regclass) | The surrogate key |
| SUBSCRIPTION_NAME | character varying(255) | X |  | The name of the subscription  |
| ID | character varying(255) | X |  | The old id |
| IS_CASE | boolean |  |  | Flag that indicate if is a subscription of a cases or of a documents; when true is a cases and false is documents |

2.2.56.5 List of keys of the table nie_subscription

| Code | Columns | Primary |
| --- | --- | --- |
| pk_nie_subscription | sid | X |

2.2.56.6 List of indexes of the table nie_subscription

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| nie_subscription_idx | X |  | CREATE UNIQUE INDEX nie_subscription_idx ON rina.nie_subscription USING btree (sid) |
| pk_nie_subscription | X | X | CREATE UNIQUE INDEX pk_nie_subscription ON rina.nie_subscription USING btree (sid) |
| subscription_name_unq | X |  | CREATE UNIQUE INDEX subscription_name_unq ON rina.nie_subscription USING btree (subscription_name) |

2.2.56.7 Other constraints of the table nie_subscription

_None._

2.2.57 Table notification

2.2.57.1 Card of table notification

| Code | Value |
| --- | --- |
| Code | NOTIFICATION |
| Comment | The table that holds the notifications. |

2.2.57.2 List of incoming references of the table notification

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| fk_assign_request__notif | assignment_request | fk_notification_sid |
| fk_notif_user__notif | notification_user | fk_notification_sid |

2.2.57.3 List of outgoing references of the table notification

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_notif__doc_type | document_type | fk_document_type_sid | sid |
| fk_notif__iam_user | iam_user | fk_creator_sid | sid |
| fk_notifica_fk_notifi_organisa | organisation | fk_receiver_org_sid | sid |
| fk_notification__document | document | fk_document_sid | sid |
| fk_notification__rina_case | rina_case | fk_case_sid | sid |
| fk_notification_sdr__org | organisation | fk_sender_org_sid | sid |

2.2.57.4 List of columns of the table notification

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.notification_seq'::regclass) | The surrogate key |
| ID | character varying(255) | X |  | The id of the Notification |
| VERSION | integer | X | 1 | The system version. It is automatically increased by Hibernate each time the row is updated. |
| FK_CASE_SID | bigint |  |  | Foreign key to rina_case table |
| FK_DOCUMENT_SID | bigint |  |  | Foreign key to document table |
| FK_DOCUMENT_TYPE_SID | bigint |  |  | Foreign key to document type table |
| FK_SENDER_ORG_SID | bigint |  |  | The sender of the notification. |
| FK_RECEIVER_ORG_SID | bigint |  |  | The receiver of the notification. |
| FK_CREATOR_SID | bigint | X | 0 | The creator of the notification. |
| CATEGORY | character varying(255) |  |  | The category of the notification |
| SEVERITY | character varying(255) |  |  | The type of severity (e.g. warning, error, information) |
| TYPE | character varying(255) |  |  | The type of the notification (e.g. new message arrived) |
| STATUS | character varying(255) |  |  | The status of the notification |
| SOURCE_TYPE | character varying(255) |  |  | The source of the notification (messaging, business, other) |
| IS_READ | boolean |  |  | Is the notification read? |
| REASON | text |  |  | The reason of the Notification |
| FAILURE_CODE | character varying(255) |  |  | The code of the error in case of failure |
| FAILURE_DESCRIPTION | text |  |  | The description of the error in case of failure |
| DUE_DATE | timestamp with time zone |  |  | The due date of the notification |
| CREATED_AT | timestamp with time zone | X | '2024-06-03 16:57:27.471284+00'::timestamp with time zone | The time that the notification  was first inserted into the DB |
| UPDATED_AT | timestamp with time zone | X | '2024-06-03 16:57:27.471284+00'::timestamp with time zone | The last time that the notification  was updated |

2.2.57.5 List of keys of the table notification

| Code | Columns | Primary |
| --- | --- | --- |
| pk_notification | sid | X |

2.2.57.6 List of indexes of the table notification

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| notifation_idx | X |  | CREATE UNIQUE INDEX notifation_idx ON rina.notification USING btree (sid) |
| notification__created_at_idx |  |  | CREATE INDEX notification__created_at_idx ON rina.notification USING btree (created_at) |
| notification__creator_idx |  |  | CREATE INDEX notification__creator_idx ON rina.notification USING btree (fk_creator_sid) |
| notification__doc_type_idx |  |  | CREATE INDEX notification__doc_type_idx ON rina.notification USING btree (fk_document_type_sid) |
| notification__document_idx |  |  | CREATE INDEX notification__document_idx ON rina.notification USING btree (fk_document_sid) |
| notification__rina_case_idx |  |  | CREATE INDEX notification__rina_case_idx ON rina.notification USING btree (fk_case_sid) |
| pk_notification | X | X | CREATE UNIQUE INDEX pk_notification ON rina.notification USING btree (sid) |

2.2.57.7 Other constraints of the table notification

_None._

2.2.58 Table notification_alarm

2.2.58.1 Card of table notification_alarm

| Code | Value |
| --- | --- |
| Code | NOTIFICATION_ALARM |
| Comment | The table that holds the notification alarms. |

2.2.58.2 List of incoming references of the table notification_alarm

_None._

2.2.58.3 List of outgoing references of the table notification_alarm

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_notif_alarm__case | rina_case | fk_case_sid | sid |

2.2.58.4 List of columns of the table notification_alarm

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.notification_alarm_seq'::regclass) | The surrogate key |
| ID | character varying(255) | X |  | The id of the Signature |
| FK_CASE_SID | bigint | X |  | Foreign key that links the Notification alarm to the rina_case  table |
| DATE | timestamp with time zone |  | '2024-06-03 16:57:27.533732+00'::timestamp with time zone | The date of the alarm. |
| DESCRIPTION | character varying(255) |  |  | The description of the notification alarm. |
| CREATED_AT | timestamp with time zone | X | '2024-06-03 16:57:27.533732+00'::timestamp with time zone | Date & Time of Creation. |
| UPDATED_AT | timestamp with time zone | X | '2024-06-03 16:57:27.533732+00'::timestamp with time zone | Date & time of last update. |
| CREATED_BY | character varying(255) | X | '0'::character varying | The person/process that created the record. |
| UPDATED_BY | character varying(255) | X | '0'::character varying | The person/process that last updated the record. |

2.2.58.5 List of keys of the table notification_alarm

| Code | Columns | Primary |
| --- | --- | --- |
| pk_notification_alarm | sid | X |

2.2.58.6 List of indexes of the table notification_alarm

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| notif_alarm__id_unq | X |  | CREATE UNIQUE INDEX notif_alarm__id_unq ON rina.notification_alarm USING btree (id) |
| notif_alarm_case_sid_idx |  |  | CREATE INDEX notif_alarm_case_sid_idx ON rina.notification_alarm USING btree (fk_case_sid) |
| notification_alarm_idx | X |  | CREATE UNIQUE INDEX notification_alarm_idx ON rina.notification_alarm USING btree (sid) |
| pk_notification_alarm | X | X | CREATE UNIQUE INDEX pk_notification_alarm ON rina.notification_alarm USING btree (sid) |

2.2.58.7 Other constraints of the table notification_alarm

_None._

2.2.59 Table notification_user

2.2.59.1 Card of table notification_user

| Code | Value |
| --- | --- |
| Code | NOTIFICATION_USER |
| Comment | Many-to-many association between notifications and users (iam_user table). It defines the user responsible parties. |

2.2.59.2 List of incoming references of the table notification_user

_None._

2.2.59.3 List of outgoing references of the table notification_user

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_notif_user__notif | notification | fk_notification_sid | sid |
| fk_notif_user__user | iam_user | fk_user_sid | sid |

2.2.59.4 List of columns of the table notification_user

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| FK_NOTIFICATION_SID | bigint | X |  | Foreign key to notification table |
| FK_USER_SID | bigint | X |  | Foreign key to iam_user table |

2.2.59.5 List of keys of the table notification_user

_None._

2.2.59.6 List of indexes of the table notification_user

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| notif_user__notif_idx |  |  | CREATE INDEX notif_user__notif_idx ON rina.notification_user USING btree (fk_notification_sid) |
| notif_user__user_idx |  |  | CREATE INDEX notif_user__user_idx ON rina.notification_user USING btree (fk_user_sid) |

2.2.59.7 Other constraints of the table notification_user

_None._

2.2.60 Table org_contact_method

2.2.60.1 Card of table org_contact_method

| Code | Value |
| --- | --- |
| Code | ORG_CONTACT_METHOD |
| Comment | Tables that holds information on the organisations'contact methods |

2.2.60.2 List of incoming references of the table org_contact_method

_None._

2.2.60.3 List of outgoing references of the table org_contact_method

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_org_contact_method__org | organisation | fk_org_sid | sid |

2.2.60.4 List of columns of the table org_contact_method

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.org_contact_method_seq'::regclass) | The surrogate key. |
| FK_ORG_SID | bigint | X |  | Foreign key to the organisation table. |
| TYPE | character varying(255) | X |  | The type of the org contact method. |
| VALUE | character varying(255) | X |  | The value of the org contact method. |

2.2.60.5 List of keys of the table org_contact_method

| Code | Columns | Primary |
| --- | --- | --- |
| pk_org_contact_method | sid | X |

2.2.60.6 List of indexes of the table org_contact_method

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| org_contact_method__org_idx |  |  | CREATE INDEX org_contact_method__org_idx ON rina.org_contact_method USING btree (fk_org_sid) |
| org_contact_method_type_unq | X |  | CREATE UNIQUE INDEX org_contact_method_type_unq ON rina.org_contact_method USING btree (fk_org_sid, type) |
| org_contact_methods_idx | X |  | CREATE UNIQUE INDEX org_contact_methods_idx ON rina.org_contact_method USING btree (sid) |
| pk_org_contact_method | X | X | CREATE UNIQUE INDEX pk_org_contact_method ON rina.org_contact_method USING btree (sid) |

2.2.60.7 Other constraints of the table org_contact_method

_None._

2.2.61 Table organisation

2.2.61.1 Card of table organisation

| Code | Value |
| --- | --- |
| Code | ORGANISATION |
| Comment | Table that holds infomation about the Organisation |

2.2.61.2 List of incoming references of the table organisation

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| fk_assigned_buc__org | assigned_buc | fk_org_sid |
| fk_case_participant__org | case_participant | fk_org_sid |
| fk_case_subject_org__org | case_subject_org | fk_org_sid |
| fk_conv_participant__org | conv_participant | fk_org_sid |
| fk_notifica_fk_notifi_organisa | notification | fk_receiver_org_sid |
| fk_notification_sdr__org | notification | fk_sender_org_sid |
| fk_org_contact_method__org | org_contact_method | fk_org_sid |
| fk_pend_msg_rec__organisation | pending_message | fk_receiver_org_sid |
| fk_pend_msg_sdr__organisation | pending_message | fk_sender_org_sid |
| fk_rule_org__org | rule_organisation | fk_org_sid |
| fk_search_def_org__org | search_def_org | fk_organisation_sid |
| fk_tenant__organisation | tenant | fk_org_sid |
| fk_user_msg__receiver | user_message | fk_receiver_sid |
| fk_user_msg__sender | user_message | fk_sender_sid |

2.2.61.3 List of outgoing references of the table organisation

_None._

2.2.61.4 List of columns of the table organisation

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.organisation_seq'::regclass) | The surrogate key |
| VERSION | integer | X | 1 | The system version. It is automatically increased by Hibernate each time the row is updated. |
| ID | character varying(50) | X |  | The id of the Entity |
| COUNTRY_CODE | character varying(2) | X |  | The country code of the country that the Organisation/Institution belongs to". Possible values: <br>    AT, <br>    BE, <br>    BG, <br>    CH, <br>    CY, <br>    CZ, <br>    DE, <br>    DK, <br>    EE, <br>    EL, <br>    ES, <br>    FI, <br>    FR, <br>    HR, <br>    HU, <br>    IS, <br>    IE, <br>    IT, <br>    LV, <br>    LI, <br>    LT, <br>    LU, <br>    MT, <br>    NL, <br>    NO, <br>    PL, <br>    PT, <br>    RO, <br>    SE, <br>    SI, <br>    SK, <br>    UK; |
| NAME | character varying(255) |  |  | The name of the organisation. |
| ACRONYM | character varying(255) |  |  | The organisation acronim. |
| LOCATION | character varying(255) |  |  | The geographical location of the Organisation/Institution |
| REGISTRY_NUMBER | character varying(255) |  |  | The registry number of the Organisation/Institution |
| ACTIVE_SINCE | timestamp with time zone |  |  | The date that the Organisation/Institution is active since |
| ACTIVE_UNTIL | timestamp with time zone |  |  | The date that the Organisation/Institution is active until |
| IS_ENABLED | boolean | X | true | The is enabled flag. |
| AP_ID | character varying(255) |  |  | The Id of the Access Point |
| AP_NAME | character varying(255) |  |  | The name of the Access Point |
| AP_COUNTRY_CODE | character varying(255) |  |  | The country code of the Access Point |
| AP_PROTOCOL | character varying(255) |  |  | The protocol of the Access Point |
| AP_TECHNICAL_PROTOCOL | character varying(255) |  |  | The technical protocol of the Access Point |
| AP_IP | character varying(255) |  |  | The IP of the Access Point |
| AP_PORT | integer |  |  | The port of the Access Point |
| AP_OUTBOX_SERVICE | character varying(255) |  |  | The outbox Service URL of the Access Point |
| AP_TECHNICAL_OUTBOX_SERVICE | character varying(255) |  |  | The technical outbox Service URL of the Access Point |
| AP_INBOX_SERVICE | character varying(255) |  |  | The inbox Service URL of the Access Point |
| AP_TECHNICAL_INBOX_SERVICE | character varying(255) |  |  | The technical inbox Service URL of the Access Point |
| AP_TECHNICAL_CHANNEL | character varying(255) |  |  | The system channel used for pulling, this is the last part of the system MPC |
| AP_CHANNEL | character varying(255) |  |  | The business channel used for pulling, this is the last part of the business MPC |
| ADDRESS_STREET | character varying(255) |  |  | The street of the Address details |
| ADDRESS_TOWN | character varying(255) |  |  | The town of the Address details |
| ADDRESS_POSTAL_CODE | character varying(255) |  |  | The postal code of the Address details |
| ADDRESS_REGION | character varying(255) |  |  | The region of the Address details |
| ADDRESS_COUNTRY | character varying(255) |  |  | The country of the Address details |
| CREATED_AT | timestamp with time zone | X | '2024-06-03 16:57:27.582302+00'::timestamp with time zone | Date & Time of creation |
| UPDATED_AT | timestamp with time zone | X | '2024-06-03 16:57:27.582302+00'::timestamp with time zone | Date & Time of the last update |
| INSTITUTION_STATUS | integer |  |  | Institution status from IRDATA |

2.2.61.5 List of keys of the table organisation

| Code | Columns | Primary |
| --- | --- | --- |
| pk_organisation | sid | X |

2.2.61.6 List of indexes of the table organisation

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| organisation_id_unq | X |  | CREATE UNIQUE INDEX organisation_id_unq ON rina.organisation USING btree (id) |
| organisation_idx | X |  | CREATE UNIQUE INDEX organisation_idx ON rina.organisation USING btree (sid) |
| pk_organisation | X | X | CREATE UNIQUE INDEX pk_organisation ON rina.organisation USING btree (sid) |

2.2.61.7 Other constraints of the table organisation

_None._

2.2.62 Table pending_attachment

2.2.62.1 Card of table pending_attachment

| Code | Value |
| --- | --- |
| Code | PENDING_ATTACHMENT |
| Comment | Table that holds information about the attachment of the pending_messages |

2.2.62.2 List of incoming references of the table pending_attachment

_None._

2.2.62.3 List of outgoing references of the table pending_attachment

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_pend_attach__pend_msg | pending_message | fk_pend_msg_sid | sid |

2.2.62.4 List of columns of the table pending_attachment

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.pending_message_seq'::regclass) | The surrogate key |
| FK_PEND_MSG_SID | bigint | X |  | Foreign key that points to the subdocument table |
| MIME_TYPE | character varying(50) | X |  | The mime type of the pending attachment. Possible values: <br>    APP_PDF <br>    APP_MSWORD <br>    APP_MSEXCEL <br>    APP_MSPOWERPOINT <br>    APP_OPENXML_DOC <br>    APP_OPENXML_SPREADSHEET <br>    APP_OPENXML_PRESENTATION <br>    APP_XML <br>    APP_ZIP <br>    APP_GZIP <br>    IMG_JPEG <br>    IMG_PNG <br>    IMG_TIFF <br>    TXT_RTF <br>    TXT_XML <br> <br>    // Mimetypes NOT included in the SBDH XSD definition <br>    APP_X_ZIP <br>    APP_OCTET_STREAM <br>    APP_X_ZIP_COMPRESSED |
| ID | character varying(255) | X |  | The id of the pending attachment. |
| FILENAME | character varying(1024) |  |  | The directory path where the assignment is stored |
| IS_MEDICAL | boolean | X | false | The is medical flag. |
| SECTION_REFERENCE | character varying(1024) |  |  | Section refference value. |
| PATHNAME | character varying(1024) | X |  | The complete pathname from where to retrieve the pending attachment. |

2.2.62.5 List of keys of the table pending_attachment

| Code | Columns | Primary |
| --- | --- | --- |
| pk_pending_attachment | sid | X |

2.2.62.6 List of indexes of the table pending_attachment

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| pend_attachment_idx | X |  | CREATE UNIQUE INDEX pend_attachment_idx ON rina.pending_attachment USING btree (sid) |
| pk_pending_attachment | X | X | CREATE UNIQUE INDEX pk_pending_attachment ON rina.pending_attachment USING btree (sid) |

2.2.62.7 Other constraints of the table pending_attachment

_None._

2.2.63 Table pending_message

2.2.63.1 Card of table pending_message

| Code | Value |
| --- | --- |
| Code | PENDING_MESSAGE |
| Comment | Table that holds information about the Pending Message |

2.2.63.2 List of incoming references of the table pending_message

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| fk_business_exc__pend_msg | business_exception | fk_pend_msg_sid |
| fk_pend_attach__pend_msg | pending_attachment | fk_pend_msg_sid |

2.2.63.3 List of outgoing references of the table pending_message

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_pend_msg__case | rina_case | fk_case_sid | sid |
| fk_pend_msg__proc_def_ver | process_def_version | fk_proc_def_version_sid | sid |
| fk_pend_msg_rec__organisation | organisation | fk_receiver_org_sid | sid |
| fk_pend_msg_sdr__organisation | organisation | fk_sender_org_sid | sid |

2.2.63.4 List of columns of the table pending_message

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.pending_message_seq'::regclass) | The surrogate key |
| ID | character varying(255) | X |  | The id of the Pending Message |
| FK_RECEIVER_ORG_SID | bigint |  |  | Foreign key that links the Pending Message to the receiver's organisation table |
| FK_SENDER_ORG_SID | bigint |  |  | Foreign key that links the Pending Message to the sender's organisation table |
| FK_CASE_SID | bigint |  |  | Foreign key that links the Pending Message to the process definition's version  table |
| FK_PROC_DEF_VERSION_SID | bigint |  |  | Foreign key that links the Pending Message to the process definition's version  table |
| SBDH | text | X |  | The SDBH value. |
| CONTENT_LOCATION | character varying(255) |  |  | The location of the content for the pending message. |
| ACTION_TYPE | character varying(255) |  |  | Action type of the Pending Message |
| INTERNATIONAL_CASE_ID | character varying(255) |  |  | International case ID |
| IS_PROTECTED_PERSON | boolean | X | false | The is protected person flag. |
| SHOULD_NOTIFY | boolean | X | false | The should notify flag. |
| IS_PROCESSED | boolean | X | false | The is protected flag. |
| IS_SELECTED | boolean |  |  | The is selected flag. |
| IS_FILTERED_OUT | boolean |  |  | The is filtered out  flag. |
| IS_EXPANDED | boolean |  |  | The is processed flag. |
| PROBLEM | character varying(255) |  |  | The problem of the peding message. |
| CAUSE | character varying(255) |  |  | The cause that triggered the creation of the pending message. |
| DATE | timestamp with time zone | X | '2024-06-03 16:57:27.674883+00'::timestamp with time zone | The date the peding message happend/was created, |

2.2.63.5 List of keys of the table pending_message

| Code | Columns | Primary |
| --- | --- | --- |
| pk_pending_message | sid | X |

2.2.63.6 List of indexes of the table pending_message

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| pend_msg__case_idx |  |  | CREATE INDEX pend_msg__case_idx ON rina.pending_message USING btree (fk_case_sid) |
| pend_msg__id_unq | X |  | CREATE UNIQUE INDEX pend_msg__id_unq ON rina.pending_message USING btree (id) |
| pend_msg__proc_def_ver_idx |  |  | CREATE INDEX pend_msg__proc_def_ver_idx ON rina.pending_message USING btree (fk_proc_def_version_sid) |
| pend_msg__processed_idx |  |  | CREATE INDEX pend_msg__processed_idx ON rina.pending_message USING btree (is_processed) |
| pend_msg__receiver_idx |  |  | CREATE INDEX pend_msg__receiver_idx ON rina.pending_message USING btree (fk_receiver_org_sid) |
| pend_msg__sender_idx |  |  | CREATE INDEX pend_msg__sender_idx ON rina.pending_message USING btree (fk_sender_org_sid) |
| pend_msg_idx | X |  | CREATE UNIQUE INDEX pend_msg_idx ON rina.pending_message USING btree (sid) |
| pk_pending_message | X | X | CREATE UNIQUE INDEX pk_pending_message ON rina.pending_message USING btree (sid) |

2.2.63.7 Other constraints of the table pending_message

_None._

2.2.64 Table pending_signature

2.2.64.1 Card of table pending_signature

| Code | Value |
| --- | --- |
| Code | PENDING_SIGNATURE |
| Comment | Table that holds information about the Pending Signature |

2.2.64.2 List of incoming references of the table pending_signature

_None._

2.2.64.3 List of outgoing references of the table pending_signature

_None._

2.2.64.4 List of columns of the table pending_signature

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.pending_signature_seq'::regclass) | The surrogate key |
| ID | character varying(255) | X |  | Id of pending message |
| DIRECTION | character varying(11) | X |  | Direction of pending message |
| SED_SIGNATURE | text | X |  | Pending Signature of SED |
| TARGET_SED_ID | character varying(255) | X |  | Id of target SED |
| LAST_UPDATE | timestamp with time zone |  |  | Date & time of last update. |

2.2.64.5 List of keys of the table pending_signature

| Code | Columns | Primary |
| --- | --- | --- |
| pk_pending_signature | sid | X |

2.2.64.6 List of indexes of the table pending_signature

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| pend_sign_idx | X |  | CREATE UNIQUE INDEX pend_sign_idx ON rina.pending_signature USING btree (sid) |
| pend_sign_unq_idx | X |  | CREATE UNIQUE INDEX pend_sign_unq_idx ON rina.pending_signature USING btree (id, direction) |
| pk_pending_signature | X | X | CREATE UNIQUE INDEX pk_pending_signature ON rina.pending_signature USING btree (sid) |

2.2.64.7 Other constraints of the table pending_signature

_None._

2.2.65 Table pending_status

2.2.65.1 Card of table pending_status

| Code | Value |
| --- | --- |
| Code | PENDING_STATUS |
| Comment | Table that holds information about the Pending Status |

2.2.65.2 List of incoming references of the table pending_status

_None._

2.2.65.3 List of outgoing references of the table pending_status

_None._

2.2.65.4 List of columns of the table pending_status

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.pending_status_seq'::regclass) | The surrogate key |
| ID | character varying(255) | X |  | The id of the pending status. |
| DIRECTION | character varying(11) | X |  | Direction of the Pending Status. Possible values:  <br>IN("IN"), <br>OUT("OUT"); |
| STATUS | character varying(255) | X |  | Status of the Pending Status. Possible values: <br>    SENT("sent"), <br>    DELIVERED("delivered"), <br>    ERROR("error"), <br>    RESENT("resent"); |
| TARGET_MESSAGE_ID | character varying(255) | X |  | The target message id of the pending status. |
| LAST_UPDATE | timestamp with time zone |  |  | Date & time of last update. |
| ERROR_DESCRIPTION | text |  |  | The description of the error of the pending message. |

2.2.65.5 List of keys of the table pending_status

| Code | Columns | Primary |
| --- | --- | --- |
| pk_pending_status | sid | X |

2.2.65.6 List of indexes of the table pending_status

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| pend_status_idx | X |  | CREATE UNIQUE INDEX pend_status_idx ON rina.pending_status USING btree (sid) |
| pend_status_unq_idx | X |  | CREATE UNIQUE INDEX pend_status_unq_idx ON rina.pending_status USING btree (id, direction) |
| pk_pending_status | X | X | CREATE UNIQUE INDEX pk_pending_status ON rina.pending_status USING btree (sid) |

2.2.65.7 Other constraints of the table pending_status

_None._

2.2.66 Table policy

2.2.66.1 Card of table policy

| Code | Value |
| --- | --- |
| Code | POLICY |
| Comment | Archiving policy details |

2.2.66.2 List of incoming references of the table policy

_None._

2.2.66.3 List of outgoing references of the table policy

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_policy__process_def | process_def | fk_process_def_sid | sid |
| fk_policy__sector | sector | fk_sector_sid | sid |
| fk_policy__tenant | tenant | fk_tenant_sid | sid |

2.2.66.4 List of columns of the table policy

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.policy_seq'::regclass) | The surrogate key |
| FK_TENANT_SID | bigint |  |  | Foreign key to the Tenant table |
| FK_SECTOR_SID | bigint |  |  | Foreign key to the Sector table |
| FK_PROCESS_DEF_SID | bigint |  |  | Foreign key to the process def table. |
| ID | character varying(255) |  |  | The id of the policy. |
| APPLICATION_ROLE | character varying(2) |  |  | The Application Role. Possible values: <br>  PO("CaseOwner"), <br>  CP("CounterParty"); |
| POLICY_TYPE | character varying(50) | X |  | The policy type. |
| POLICY | integer | X |  | The archiving timer used by archiving process. Closed or forwarded cases will be archived after the specified timer (number of days – e.g.7 days a week, 365 days a year, etc. ) |

2.2.66.5 List of keys of the table policy

| Code | Columns | Primary |
| --- | --- | --- |
| pk_policy | sid | X |

2.2.66.6 List of indexes of the table policy

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| pk_policy | X | X | CREATE UNIQUE INDEX pk_policy ON rina.policy USING btree (sid) |
| policy__buc_idx |  |  | CREATE INDEX policy__buc_idx ON rina.policy USING btree (fk_process_def_sid) |
| policy__sector_idx |  |  | CREATE INDEX policy__sector_idx ON rina.policy USING btree (fk_sector_sid) |
| policy__tenant_idx |  |  | CREATE INDEX policy__tenant_idx ON rina.policy USING btree (fk_tenant_sid) |
| policy_id_unq | X |  | CREATE UNIQUE INDEX policy_id_unq ON rina.policy USING btree (id) WHERE (id IS NOT NULL) |
| policy_idx | X |  | CREATE UNIQUE INDEX policy_idx ON rina.policy USING btree (sid) |

2.2.66.7 Other constraints of the table policy

_None._

2.2.67 Table process_def

2.2.67.1 Card of table process_def

| Code | Value |
| --- | --- |
| Code | PROCESS_DEF |
| Comment | Table that holds information about the process definiyion. |

2.2.67.2 List of incoming references of the table process_def

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| fk_assigned_buc__process_def | assigned_buc | fk_process_def_sid |
| fk_field_chooser__process_def | field_chooser | fk_process_def_sid |
| fk_policy__process_def | policy | fk_process_def_sid |
| fk_proc_def__proc_def_version | process_def_version | fk_proc_def_sid |
| fk_rule_process__process | rule_process | fk_process_sid |
| fk_srch_def_proc_def__proc_def | search_def_proc_def | fk_process_definition_sid |
| fk_user_profile__process_def | user_profile | fk_proc_def_sid |

2.2.67.3 List of outgoing references of the table process_def

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_process_def__sector | sector | fk_sector_sid | sid |

2.2.67.4 List of columns of the table process_def

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.process_def_seq'::regclass) | The surrogate key. |
| FK_SECTOR_SID | bigint | X |  | Foreign key to the Sector table. |
| ID | character varying(255) | X |  | The id of the process def. |
| NAME | character varying(255) | X |  | The name of the process definition. |
| IS_REIMBURSEMENT | boolean |  | false |  |

2.2.67.5 List of keys of the table process_def

| Code | Columns | Primary |
| --- | --- | --- |
| pk_process_def | sid | X |

2.2.67.6 List of indexes of the table process_def

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| pk_process_def | X | X | CREATE UNIQUE INDEX pk_process_def ON rina.process_def USING btree (sid) |
| process_def__id_unq | X |  | CREATE UNIQUE INDEX process_def__id_unq ON rina.process_def USING btree (id) |
| process_def_idx | X |  | CREATE UNIQUE INDEX process_def_idx ON rina.process_def USING btree (sid) |
| process_def_name_unq | X |  | CREATE UNIQUE INDEX process_def_name_unq ON rina.process_def USING btree (name) |

2.2.67.7 Other constraints of the table process_def

_None._

2.2.68 Table process_def_version

2.2.68.1 Card of table process_def_version

| Code | Value |
| --- | --- |
| Code | PROCESS_DEF_VERSION |
| Comment | Table that holds information about the business version of the process definition |

2.2.68.2 List of incoming references of the table process_def_version

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| fk_doc_type__proc_def_version | document_type | fk_proc_def_version_sid |
| fk_nie_event__proc_def_version | nie_event | fk_process_def_version_sid |
| fk_subscrbr__process_def_ver | nie_subscriber | fk_process_def_version_sid |
| fk_pend_msg__proc_def_ver | pending_message | fk_proc_def_version_sid |
| fk_case__proc_def_version | rina_case | fk_proc_def_version_sid |
| fk_transpos__proc_def_version | transposition | fk_proc_def_version_sid |

2.2.68.3 List of outgoing references of the table process_def_version

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_proc_def__proc_def_version | process_def | fk_proc_def_sid | sid |

2.2.68.4 List of columns of the table process_def_version

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.process_def_version_seq'::regclass) | The surrogate key |
| FK_PROC_DEF_SID | bigint | X |  | Foreign key to the process_def table  |
| BVERSION | character varying(10) | X |  | The version of the ProcessDefinition. |
| ACTIVE_FROM | timestamp with time zone |  |  | Timestamp since the process definition version should be active from |
| ACTIVE_TO | timestamp with time zone |  |  | The date and time untill the process definition is active. |

2.2.68.5 List of keys of the table process_def_version

| Code | Columns | Primary |
| --- | --- | --- |
| pk_process_def_version | sid | X |

2.2.68.6 List of indexes of the table process_def_version

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| pk_process_def_version | X | X | CREATE UNIQUE INDEX pk_process_def_version ON rina.process_def_version USING btree (sid) |
| proc_def__proc_def_version_idx |  |  | CREATE INDEX proc_def__proc_def_version_idx ON rina.process_def_version USING btree (fk_proc_def_sid) |
| process_def_version_idx | X |  | CREATE UNIQUE INDEX process_def_version_idx ON rina.process_def_version USING btree (sid) |
| process_def_version_version_unq | X |  | CREATE UNIQUE INDEX process_def_version_version_unq ON rina.process_def_version USING btree (bversion, fk_proc_def_sid) |

2.2.68.7 Other constraints of the table process_def_version

_None._

2.2.69 Table resource

2.2.69.1 Card of table resource

| Code | Value |
| --- | --- |
| Code | RESOURCE |
| Comment | Resource inventory |

2.2.69.2 List of incoming references of the table resource

_None._

2.2.69.3 List of outgoing references of the table resource

_None._

2.2.69.4 List of columns of the table resource

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.resource_seq'::regclass) | The surrogate key |
| ID | character varying(255) | X |  | The id of the resource. |
| VERSION | integer | X | 1 | The system version. It is automatically increased by Hibernate each time the row is updated. |
| STORAGE_ID | character varying(255) | X |  | Storage id |
| TYPE | character varying(20) | X |  | The type of this resource. Possible values: <br>    organisation,  <br>    vocabulary,  <br>    initialdoc,  <br>    process,  <br>    sbdh,  <br>    sed,  <br>    transaction,  <br>    form,  <br>    report,  <br>    APPLICATION, <br>    letterTemplate, <br>    localization |
| BVERSION | character varying(35) | X |  | Business version |
| DATE | timestamp with time zone |  |  | The computed date of the resource |
| TAG | character varying(255) | X |  | The tag of the resource |
| CREATED_AT | timestamp with time zone | X | '2024-06-03 16:57:27.951193+00'::timestamp with time zone | The time that the resource  was first inserted into the DB |
| UPDATED_AT | timestamp with time zone | X | '2024-06-03 16:57:27.951193+00'::timestamp with time zone | The last time that the resource was updated |
| CREATED_BY | character varying(255) | X | '0'::character varying | The person/process that created the record. |
| UPDATED_BY | character varying(255) | X | '0'::character varying | The person/process that last updated the record. |

2.2.69.5 List of keys of the table resource

| Code | Columns | Primary |
| --- | --- | --- |
| pk_resource | sid | X |

2.2.69.6 List of indexes of the table resource

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| pk_resource | X | X | CREATE UNIQUE INDEX pk_resource ON rina.resource USING btree (sid) |
| resource_idx | X |  | CREATE UNIQUE INDEX resource_idx ON rina.resource USING btree (sid) |
| resource_storage_id_idx | X |  | CREATE UNIQUE INDEX resource_storage_id_idx ON rina.resource USING btree (storage_id, type) |
| resource_type_idx |  |  | CREATE INDEX resource_type_idx ON rina.resource USING btree (type) |

2.2.69.7 Other constraints of the table resource

_None._

2.2.70 Table rina_case

2.2.70.1 Card of table rina_case

| Code | Value |
| --- | --- |
| Code | RINA_CASE |
| Comment | Table that holds information about the Case |

2.2.70.2 List of incoming references of the table rina_case

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| fk_action__case | action | fk_case_sid |
| fk_activity__case | activity | fk_case_sid |
| fk_assign__case | assignment | fk_case_sid |
| fk_assign_request__case | assignment_request | fk_case_sid |
| fk_case_attach__case | case_attachment | fk_case_sid |
| fk_comment__case | case_comment | fk_case_sid |
| fk_case_participant__case | case_participant | fk_case_sid |
| fk_case_prefill__rina_case | case_prefill | fk_case_sid |
| fk_case_property__case | case_property | fk_case_sid |
| fk_case_subject_org__case | case_subject_org | fk_case_sid |
| fk_document__case | document | fk_case_sid |
| fk_doc_his__case | document_history | fk_case_sid |
| fk_notification__rina_case | notification | fk_case_sid |
| fk_notif_alarm__case | notification_alarm | fk_case_sid |
| fk_pend_msg__case | pending_message | fk_case_sid |
| fk_subdoc__rina_case | subdocument | fk_case_sid |

2.2.70.3 List of outgoing references of the table rina_case

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_case__proc_def_version | process_def_version | fk_proc_def_version_sid | sid |
| fk_case__tenant | tenant | fk_tenant_sid | sid |

2.2.70.4 List of columns of the table rina_case

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.case_seq'::regclass) | The surrogate key |
| VERSION | integer | X | 1 | The system version. It is automatically increased by Hibernate each time the row is updated. |
| FK_TENANT_SID | bigint | X |  | Foreign key that links the Case to the Tenant table |
| FK_PROC_DEF_VERSION_SID | bigint | X |  | Foreign key that links the Case to the process definition's version  table |
| FK_STARTER_DOC_TYPE_SID | bigint |  |  | This is the foreign key to the document type for the stater document. |
| ID | character varying(255) | X |  | The id of the Case |
| APPLICATION_ROLE | character varying(2) | X |  | The Application Role. Possible values: <br>  PO("CaseOwner"), <br>  CP("CounterParty"); |
| INTERNATIONAL_ID | character varying(255) |  |  | International correlation Id of the Case |
| BUSINESS_ID | text |  |  | Business Id of the Case |
| STATUS | character varying(10) | X | 'open'::character varying | The current status of the Case. Possible values: <br>    OPEN("open"), <br>    CLOSED("closed"), <br>    ACTIVE("active"), <br>    REMOVED("removed"), <br>    ARCHIVED("archived"), <br>    FORWARD("forward") |
| COUNTER | integer | X | 0 | The counter. |
| IS_SENSITIVE | boolean | X | false | The sensitivity status of the Case |
| IS_SENSITIVE_COMMITED | boolean | X | false | The is sensitive commited flag. |
| IS_MLC | boolean |  |  | The is MLC flag. |
| HAS_VALID_STARTER | boolean |  |  | The has valid starter flag. |
| REMOVE_ME_ONLY | boolean |  |  | The remove me only flag. |
| IS_STARTER_SENT | boolean |  |  | The is starter sent flag. |
| IMPORTANCE | integer | X | 0 | The importance of the case. |
| CRITICALITY | integer | X | 0 | The criticality of the case. |
| STORE_LOCATION_OF_ARCHIVE | character varying(1024) |  |  | The location of the stored archive. |
| CREATED_AT | timestamp with time zone | X | '2024-06-03 16:57:27.994461+00'::timestamp with time zone | Date & Time of Creation |
| UPDATED_AT | timestamp with time zone | X | '2024-06-03 16:57:27.994461+00'::timestamp with time zone | Date & time of last update |
| CREATED_BY | character varying(255) | X | '0'::character varying | The person/process that created the record. |
| UPDATED_BY | character varying(255) | X | '0'::character varying | The person/process that last updated the record. |
| RANDOM_STRING | character varying(255) | X | 'A1'::character varying | Random string for the case. |

2.2.70.5 List of keys of the table rina_case

| Code | Columns | Primary |
| --- | --- | --- |
| pk_rina_case | sid | X |

2.2.70.6 List of indexes of the table rina_case

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| case__created_at_idx |  |  | CREATE INDEX case__created_at_idx ON rina.rina_case USING btree (created_at) |
| case__proc_def_version_idx |  |  | CREATE INDEX case__proc_def_version_idx ON rina.rina_case USING btree (fk_proc_def_version_sid) |
| case__status_idx |  |  | CREATE INDEX case__status_idx ON rina.rina_case USING btree (status) |
| case__tenant_idx |  |  | CREATE INDEX case__tenant_idx ON rina.rina_case USING btree (fk_tenant_sid) |
| case__updated_at_idx |  |  | CREATE INDEX case__updated_at_idx ON rina.rina_case USING btree (updated_at DESC NULLS LAST) |
| case_id_unq | X |  | CREATE UNIQUE INDEX case_id_unq ON rina.rina_case USING btree (id) |
| case_idx | X |  | CREATE UNIQUE INDEX case_idx ON rina.rina_case USING btree (sid) |
| pk_rina_case | X | X | CREATE UNIQUE INDEX pk_rina_case ON rina.rina_case USING btree (sid) |

2.2.70.7 Other constraints of the table rina_case

_None._

2.2.71 Table role

2.2.71.1 Card of table role

| Code | Value |
| --- | --- |
| Code | ROLE |
| Comment | The roles (Supervisor, Authorised, NonAuthorised, Auditor, Viewer, Medical, VIP) |

2.2.71.2 List of incoming references of the table role

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| fk_assign__role | assignment | fk_role_sid |
| fk_assign_request__role | assignment_request | fk_role_sid |
| fk_user_group__role | iam_user_group | fk_role_sid |
| fk_rule_role__role | rule_role | fk_role_sid |

2.2.71.3 List of outgoing references of the table role

_None._

2.2.71.4 List of columns of the table role

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.role_seq'::regclass) | the surrogate key |
| NAME | character varying(20) | X |  | The role name |

2.2.71.5 List of keys of the table role

| Code | Columns | Primary |
| --- | --- | --- |
| pk_role | sid | X |

2.2.71.6 List of indexes of the table role

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| pk_role | X | X | CREATE UNIQUE INDEX pk_role ON rina.role USING btree (sid) |
| role_idx | X |  | CREATE UNIQUE INDEX role_idx ON rina.role USING btree (sid) |
| role_name_unq | X |  | CREATE UNIQUE INDEX role_name_unq ON rina.role USING btree (name) |

2.2.71.7 Other constraints of the table role

_None._

2.2.72 Table rule_country

2.2.72.1 Card of table rule_country

| Code | Value |
| --- | --- |
| Code | RULE_COUNTRY |
| Comment | Table that holds information about the Country associated with an assignment_ policy_rule's po |

2.2.72.2 List of incoming references of the table rule_country

_None._

2.2.72.3 List of outgoing references of the table rule_country

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_rule_coun__assign_pol_rule | assignment_policy_rule | fk_rule_sid | sid |

2.2.72.4 List of columns of the table rule_country

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.rule_country_seq'::regclass) | The surrogate key |
| FK_RULE_SID | bigint | X |  | Foreign key to assignment_policy_rule table |
| COUNTRY_CODE | character varying(2) | X |  | The country code. Possible values: <br>    AT, <br>    BE, <br>    BG, <br>    CH, <br>    CY, <br>    CZ, <br>    DE, <br>    DK, <br>    EE, <br>    EL, <br>    ES, <br>    FI, <br>    FR, <br>    HR, <br>    HU, <br>    IS, <br>    IE, <br>    IT, <br>    LV, <br>    LI, <br>    LT, <br>    LU, <br>    MT, <br>    NL, <br>    NO, <br>    PL, <br>    PT, <br>    RO, <br>    SE, <br>    SI, <br>    SK, <br>    UK; |

2.2.72.5 List of keys of the table rule_country

| Code | Columns | Primary |
| --- | --- | --- |
| pk_rule_country | sid | X |

2.2.72.6 List of indexes of the table rule_country

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| pk_rule_country | X | X | CREATE UNIQUE INDEX pk_rule_country ON rina.rule_country USING btree (sid) |
| rule_coun__assign_pol_rule_idx |  |  | CREATE INDEX rule_coun__assign_pol_rule_idx ON rina.rule_country USING btree (fk_rule_sid) |
| rule_country_idx | X |  | CREATE UNIQUE INDEX rule_country_idx ON rina.rule_country USING btree (sid) |
| rule_country_unq | X |  | CREATE UNIQUE INDEX rule_country_unq ON rina.rule_country USING btree (fk_rule_sid, country_code) |

2.2.72.7 Other constraints of the table rule_country

_None._

2.2.73 Table rule_creator_group

2.2.73.1 Card of table rule_creator_group

| Code | Value |
| --- | --- |
| Code | RULE_CREATOR_GROUP |
| Comment | Many to many table that links Rules and their coresponding groups for creator |

2.2.73.2 List of incoming references of the table rule_creator_group

_None._

2.2.73.3 List of outgoing references of the table rule_creator_group

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_rule_creator_group__group | iam_group | fk_group_sid | sid |
| fk_rule_creator_group__rule | assignment_policy_rule | fk_rule_sid | sid |

2.2.73.4 List of columns of the table rule_creator_group

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| FK_RULE_SID | bigint | X |  | Linked record field that mapped to the Rule table |
| FK_GROUP_SID | bigint | X |  | Linked record field that mapped to the Group table |

2.2.73.5 List of keys of the table rule_creator_group

_None._

2.2.73.6 List of indexes of the table rule_creator_group

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| rule_creator_group__group_idx |  |  | CREATE INDEX rule_creator_group__group_idx ON rina.rule_creator_group USING btree (fk_group_sid) |
| rule_creator_group__rule_idx |  |  | CREATE INDEX rule_creator_group__rule_idx ON rina.rule_creator_group USING btree (fk_rule_sid) |
| rule_creator_group__unq | X |  | CREATE UNIQUE INDEX rule_creator_group__unq ON rina.rule_creator_group USING btree (fk_rule_sid, fk_group_sid) |

2.2.73.7 Other constraints of the table rule_creator_group

_None._

2.2.74 Table rule_creator_user

2.2.74.1 Card of table rule_creator_user

| Code | Value |
| --- | --- |
| Code | RULE_CREATOR_USER |
| Comment | Many to many table that links Rules and their coresponding users  for creator |

2.2.74.2 List of incoming references of the table rule_creator_user

_None._

2.2.74.3 List of outgoing references of the table rule_creator_user

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_rule_creator_user__rule | assignment_policy_rule | fk_rule_sid | sid |
| fk_rule_creator_user__user | iam_user | fk_user_sid | sid |

2.2.74.4 List of columns of the table rule_creator_user

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| FK_RULE_SID | bigint | X |  | Linked record field that mapped to the Rule table |
| FK_USER_SID | bigint | X |  | Linked record field that mapped to the Group table |

2.2.74.5 List of keys of the table rule_creator_user

_None._

2.2.74.6 List of indexes of the table rule_creator_user

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| rule_creator_user__rule_idx |  |  | CREATE INDEX rule_creator_user__rule_idx ON rina.rule_creator_user USING btree (fk_rule_sid) |
| rule_creator_user__user_idx |  |  | CREATE INDEX rule_creator_user__user_idx ON rina.rule_creator_user USING btree (fk_user_sid) |
| rule_creator_user_unq | X |  | CREATE UNIQUE INDEX rule_creator_user_unq ON rina.rule_creator_user USING btree (fk_rule_sid, fk_user_sid) |

2.2.74.7 Other constraints of the table rule_creator_user

_None._

2.2.75 Table rule_group

2.2.75.1 Card of table rule_group

| Code | Value |
| --- | --- |
| Code | RULE_GROUP |
| Comment | Many to many table that links Rules and their coresponding groups |

2.2.75.2 List of incoming references of the table rule_group

_None._

2.2.75.3 List of outgoing references of the table rule_group

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_rule_group__group | iam_group | fk_group_sid | sid |
| fk_rule_group__rule | assignment_policy_rule | fk_rule_sid | sid |

2.2.75.4 List of columns of the table rule_group

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| FK_RULE_SID | bigint | X |  | Linked record field that mapped to the Rule table |
| FK_GROUP_SID | bigint | X |  | Linked record field that mapped to the Group table |

2.2.75.5 List of keys of the table rule_group

_None._

2.2.75.6 List of indexes of the table rule_group

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| rule_group__group_idx |  |  | CREATE INDEX rule_group__group_idx ON rina.rule_group USING btree (fk_group_sid) |
| rule_group__rule_idx |  |  | CREATE INDEX rule_group__rule_idx ON rina.rule_group USING btree (fk_rule_sid) |
| rule_group__unq | X |  | CREATE UNIQUE INDEX rule_group__unq ON rina.rule_group USING btree (fk_rule_sid, fk_group_sid) |

2.2.75.7 Other constraints of the table rule_group

_None._

2.2.76 Table rule_organisation

2.2.76.1 Card of table rule_organisation

| Code | Value |
| --- | --- |
| Code | RULE_ORGANISATION |
| Comment | Many to many table that links Rules and their coresponding organisations |

2.2.76.2 List of incoming references of the table rule_organisation

_None._

2.2.76.3 List of outgoing references of the table rule_organisation

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_rule_org__org | organisation | fk_org_sid | sid |
| fk_rule_org__rule | assignment_policy_rule | fk_rule_sid | sid |

2.2.76.4 List of columns of the table rule_organisation

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| FK_RULE_SID | bigint | X |  | Foreign key to assignment_policy_rule table |
| FK_ORG_SID | bigint | X |  | Foreign key to organisation table |

2.2.76.5 List of keys of the table rule_organisation

_None._

2.2.76.6 List of indexes of the table rule_organisation

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| rule_org__org_idx |  |  | CREATE INDEX rule_org__org_idx ON rina.rule_organisation USING btree (fk_org_sid) |
| rule_org__rule_idx |  |  | CREATE INDEX rule_org__rule_idx ON rina.rule_organisation USING btree (fk_rule_sid) |
| rule_org_unq | X |  | CREATE UNIQUE INDEX rule_org_unq ON rina.rule_organisation USING btree (fk_rule_sid, fk_org_sid) |

2.2.76.7 Other constraints of the table rule_organisation

_None._

2.2.77 Table rule_process

2.2.77.1 Card of table rule_process

| Code | Value |
| --- | --- |
| Code | RULE_PROCESS |
| Comment | Many to many table that links Rules and their coresponding processes |

2.2.77.2 List of incoming references of the table rule_process

_None._

2.2.77.3 List of outgoing references of the table rule_process

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_rule_process__process | process_def | fk_process_sid | sid |
| fk_rule_process__rule | assignment_policy_rule | fk_rule_sid | sid |

2.2.77.4 List of columns of the table rule_process

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| FK_RULE_SID | bigint | X |  | Foreign key pointing to theRule table |
| FK_PROCESS_SID | bigint | X |  | Foreign key to the process_def table |

2.2.77.5 List of keys of the table rule_process

_None._

2.2.77.6 List of indexes of the table rule_process

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| rule_process__process_idx |  |  | CREATE INDEX rule_process__process_idx ON rina.rule_process USING btree (fk_process_sid) |
| rule_process__rule_idx |  |  | CREATE INDEX rule_process__rule_idx ON rina.rule_process USING btree (fk_rule_sid) |
| rule_process_unq | X |  | CREATE UNIQUE INDEX rule_process_unq ON rina.rule_process USING btree (fk_rule_sid, fk_process_sid) |

2.2.77.7 Other constraints of the table rule_process

_None._

2.2.78 Table rule_role

2.2.78.1 Card of table rule_role

| Code | Value |
| --- | --- |
| Code | RULE_ROLE |
| Comment | Table that holds information about roles associated with an assigment policy rule |

2.2.78.2 List of incoming references of the table rule_role

_None._

2.2.78.3 List of outgoing references of the table rule_role

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_rule_role__role | role | fk_role_sid | sid |
| fk_rule_role__rule | assignment_policy_rule | fk_rule_sid | sid |

2.2.78.4 List of columns of the table rule_role

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| FK_RULE_SID | bigint | X |  | Foreign key to assignment_policy_rule Table |
| FK_ROLE_SID | bigint | X |  | the surrogate key |

2.2.78.5 List of keys of the table rule_role

_None._

2.2.78.6 List of indexes of the table rule_role

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| rule_role__role_idx |  |  | CREATE INDEX rule_role__role_idx ON rina.rule_role USING btree (fk_role_sid) |
| rule_role__rule_idx |  |  | CREATE INDEX rule_role__rule_idx ON rina.rule_role USING btree (fk_rule_sid) |
| rule_role_unq | X |  | CREATE UNIQUE INDEX rule_role_unq ON rina.rule_role USING btree (fk_rule_sid, fk_role_sid) |

2.2.78.7 Other constraints of the table rule_role

_None._

2.2.79 Table rule_sector

2.2.79.1 Card of table rule_sector

| Code | Value |
| --- | --- |
| Code | RULE_SECTOR |
| Comment | Many to many table that links Rules and their coresponding sectors |

2.2.79.2 List of incoming references of the table rule_sector

_None._

2.2.79.3 List of outgoing references of the table rule_sector

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_rule_sector__assign_pol_rul | assignment_policy_rule | fk_rule_sid | sid |
| fk_rule_sector__sector | sector | fk_sector_sid | sid |

2.2.79.4 List of columns of the table rule_sector

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| FK_RULE_SID | bigint | X |  | Foreign key to assignment_policy_rule table |
| FK_SECTOR_SID | bigint | X |  | Foreign key to sector table |

2.2.79.5 List of keys of the table rule_sector

_None._

2.2.79.6 List of indexes of the table rule_sector

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| rule_sector__assign_pol_r_idx |  |  | CREATE INDEX rule_sector__assign_pol_r_idx ON rina.rule_sector USING btree (fk_rule_sid) |
| rule_sector__sector_idx |  |  | CREATE INDEX rule_sector__sector_idx ON rina.rule_sector USING btree (fk_sector_sid) |
| rule_sector_unq | X |  | CREATE UNIQUE INDEX rule_sector_unq ON rina.rule_sector USING btree (fk_rule_sid, fk_sector_sid) |

2.2.79.7 Other constraints of the table rule_sector

_None._

2.2.80 Table rule_user

2.2.80.1 Card of table rule_user

| Code | Value |
| --- | --- |
| Code | RULE_USER |
| Comment | Many to many table that links the Rules to its Users |

2.2.80.2 List of incoming references of the table rule_user

_None._

2.2.80.3 List of outgoing references of the table rule_user

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_rule_user__assign_pol_rule | assignment_policy_rule | fk_rule_sid | sid |
| fk_rule_user__user | iam_user | fk_user_sid | sid |

2.2.80.4 List of columns of the table rule_user

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| FK_RULE_SID | bigint | X |  | Linked record field that mapped to the Rule table |
| FK_USER_SID | bigint | X |  | Linked record field that mapped to User Table |

2.2.80.5 List of keys of the table rule_user

_None._

2.2.80.6 List of indexes of the table rule_user

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| rule_user__rule_idx |  |  | CREATE INDEX rule_user__rule_idx ON rina.rule_user USING btree (fk_rule_sid) |
| rule_user__user_idx |  |  | CREATE INDEX rule_user__user_idx ON rina.rule_user USING btree (fk_user_sid) |
| rule_user_unq | X |  | CREATE UNIQUE INDEX rule_user_unq ON rina.rule_user USING btree (fk_rule_sid, fk_user_sid) |

2.2.80.7 Other constraints of the table rule_user

_None._

2.2.81 Table search_def_group

2.2.81.1 Card of table search_def_group

| Code | Value |
| --- | --- |
| Code | SEARCH_DEF_GROUP |
| Comment | The search definition group table. |

2.2.81.2 List of incoming references of the table search_def_group

_None._

2.2.81.3 List of outgoing references of the table search_def_group

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_search_def_group__group | iam_group | fk_iam_group_sid | sid |
| fk_search_def_group__search_def | search_definition | fk_search_definition_sid | sid |

2.2.81.4 List of columns of the table search_def_group

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| FK_SEARCH_DEFINITION_SID | bigint |  |  | Foreign key to the search definition table |
| FK_IAM_GROUP_SID | bigint |  |  | Foreign key to the iam group table |

2.2.81.5 List of keys of the table search_def_group

_None._

2.2.81.6 List of indexes of the table search_def_group

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| search_def_group__group_idx |  |  | CREATE INDEX search_def_group__group_idx ON rina.search_def_group USING btree (fk_iam_group_sid) |
| srch_def_group__search_def_idx |  |  | CREATE INDEX srch_def_group__search_def_idx ON rina.search_def_group USING btree (fk_search_definition_sid) |

2.2.81.7 Other constraints of the table search_def_group

_None._

2.2.82 Table search_def_org

2.2.82.1 Card of table search_def_org

| Code | Value |
| --- | --- |
| Code | SEARCH_DEF_ORG |
| Comment | Many-to-many association between search_definition and organisation table. |

2.2.82.2 List of incoming references of the table search_def_org

_None._

2.2.82.3 List of outgoing references of the table search_def_org

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_search_def_org__org | organisation | fk_organisation_sid | sid |
| fk_search_def_org__search_def | search_definition | fk_search_definition_sid | sid |

2.2.82.4 List of columns of the table search_def_org

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| FK_SEARCH_DEFINITION_SID | bigint | X |  | Foreign key to the search definition table. |
| FK_ORGANISATION_SID | bigint | X |  | Foreign key to the organisation table. |

2.2.82.5 List of keys of the table search_def_org

_None._

2.2.82.6 List of indexes of the table search_def_org

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| search_def__org_idx |  |  | CREATE INDEX search_def__org_idx ON rina.search_def_org USING btree (fk_organisation_sid) |
| search_def__search_def_idx |  |  | CREATE INDEX search_def__search_def_idx ON rina.search_def_org USING btree (fk_search_definition_sid) |

2.2.82.7 Other constraints of the table search_def_org

_None._

2.2.83 Table search_def_proc_def

2.2.83.1 Card of table search_def_proc_def

| Code | Value |
| --- | --- |
| Code | SEARCH_DEF_PROC_DEF |
| Comment | Many-to-many association between search_definition and process_definition table. |

2.2.83.2 List of incoming references of the table search_def_proc_def

_None._

2.2.83.3 List of outgoing references of the table search_def_proc_def

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_srch_def_proc_def__proc_def | process_def | fk_process_definition_sid | sid |
| fk_srch_def_proc_def__srch_def | search_definition | fk_search_definition_sid | sid |

2.2.83.4 List of columns of the table search_def_proc_def

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| FK_SEARCH_DEFINITION_SID | bigint | X |  | Foreign key to the search definition table. |
| FK_PROCESS_DEFINITION_SID | bigint | X |  | Foreign key to the process definition table. |

2.2.83.5 List of keys of the table search_def_proc_def

_None._

2.2.83.6 List of indexes of the table search_def_proc_def

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| srch_def_proc_def__proc_def_idx |  |  | CREATE INDEX srch_def_proc_def__proc_def_idx ON rina.search_def_proc_def USING btree (fk_process_definition_sid) |
| srch_def_proc_def__srch_def_idx |  |  | CREATE INDEX srch_def_proc_def__srch_def_idx ON rina.search_def_proc_def USING btree (fk_search_definition_sid) |

2.2.83.7 Other constraints of the table search_def_proc_def

_None._

2.2.84 Table search_def_user

2.2.84.1 Card of table search_def_user

| Code | Value |
| --- | --- |
| Code | SEARCH_DEF_USER |
| Comment | Many-to-many association between search_definition and user group table. |

2.2.84.2 List of incoming references of the table search_def_user

_None._

2.2.84.3 List of outgoing references of the table search_def_user

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_search_def_user__search_def | search_definition | fk_search_definition_sid | sid |
| fk_search_def_user__user | iam_user | fk_iam_user_sid | sid |

2.2.84.4 List of columns of the table search_def_user

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| FK_IAM_USER_SID | bigint | X |  | Foreign key to the iam user table. |
| FK_SEARCH_DEFINITION_SID | bigint | X |  | Foreign key to the search definition table. |

2.2.84.5 List of keys of the table search_def_user

_None._

2.2.84.6 List of indexes of the table search_def_user

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| search_def_user__search_def_idx |  |  | CREATE INDEX search_def_user__search_def_idx ON rina.search_def_user USING btree (fk_search_definition_sid) |
| search_def_user__user_idx |  |  | CREATE INDEX search_def_user__user_idx ON rina.search_def_user USING btree (fk_iam_user_sid) |

2.2.84.7 Other constraints of the table search_def_user

_None._

2.2.85 Table search_definition

2.2.85.1 Card of table search_definition

| Code | Value |
| --- | --- |
| Code | SEARCH_DEFINITION |
| Comment | The search definition table. |

2.2.85.2 List of incoming references of the table search_definition

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| fk_search_def_group__search_def | search_def_group | fk_search_definition_sid |
| fk_search_def_org__search_def | search_def_org | fk_search_definition_sid |
| fk_srch_def_proc_def__srch_def | search_def_proc_def | fk_search_definition_sid |
| fk_search_def_user__search_def | search_def_user | fk_search_definition_sid |

2.2.85.3 List of outgoing references of the table search_definition

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_search_d_fk_iam_us_iam_user | iam_user | fk_iam_user_sid | sid |

2.2.85.4 List of columns of the table search_definition

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X |  | The surrogate key. |
| FK_IAM_USER_SID | bigint | X |  | Foreign key to the iam user table. |
| ID | character varying(255) | X |  | The id of the search definition. |
| NAME | character varying(255) | X |  | The name of the search definition. |
| COLOR | character varying(255) |  |  | The color of the search definition. |
| TIME_INTERVAL_TYPE | character varying(50) |  |  | The selected time interval of the search definition. |
| IMPORTANCES | text |  |  | The importances saved for the specific search definition. |
| CRITICALITIES | text |  |  | The criticalities saved for the specific search definition. |
| STATUSES | character varying(100) |  |  | The statuses saved for the specific search definition. |
| START_DATE | timestamp with time zone |  |  | The start date of the search definition for retrieving the desired custom interval. |
| END_DATE | timestamp with time zone |  |  | The end date of the search definition for retrieving the desired custom interval. |

2.2.85.5 List of keys of the table search_definition

| Code | Columns | Primary |
| --- | --- | --- |
| pk_search_definition | sid | X |

2.2.85.6 List of indexes of the table search_definition

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| pk_search_definition | X | X | CREATE UNIQUE INDEX pk_search_definition ON rina.search_definition USING btree (sid) |
| search_def__iam_user_fk |  |  | CREATE INDEX search_def__iam_user_fk ON rina.search_definition USING btree (fk_iam_user_sid) |
| search_def_id_unq | X |  | CREATE UNIQUE INDEX search_def_id_unq ON rina.search_definition USING btree (id) |
| search_def_idx | X |  | CREATE UNIQUE INDEX search_def_idx ON rina.search_definition USING btree (sid) |

2.2.85.7 Other constraints of the table search_definition

_None._

2.2.86 Table sector

2.2.86.1 Card of table sector

| Code | Value |
| --- | --- |
| Code | SECTOR |
| Comment | Table that holds information about the Sector |

2.2.86.2 List of incoming references of the table sector

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| fk_policy__sector | policy | fk_sector_sid |
| fk_process_def__sector | process_def | fk_sector_sid |
| fk_rule_sector__sector | rule_sector | fk_sector_sid |

2.2.86.3 List of outgoing references of the table sector

_None._

2.2.86.4 List of columns of the table sector

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.sector_seq'::regclass) | The surrogate key |
| NAME | character varying(50) | X |  | The name of the sector |

2.2.86.5 List of keys of the table sector

| Code | Columns | Primary |
| --- | --- | --- |
| pk_sector | sid | X |

2.2.86.6 List of indexes of the table sector

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| pk_sector | X | X | CREATE UNIQUE INDEX pk_sector ON rina.sector USING btree (sid) |
| sector_idx | X |  | CREATE UNIQUE INDEX sector_idx ON rina.sector USING btree (sid) |
| sector_unq | X |  | CREATE UNIQUE INDEX sector_unq ON rina.sector USING btree (name) |

2.2.86.7 Other constraints of the table sector

_None._

2.2.87 Table signature

2.2.87.1 Card of table signature

| Code | Value |
| --- | --- |
| Code | SIGNATURE |
| Comment | Table that holds information about the User Message Signature  |

2.2.87.2 List of incoming references of the table signature

_None._

2.2.87.3 List of outgoing references of the table signature

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_signature__message | user_message | fk_message_sid | sid |

2.2.87.4 List of columns of the table signature

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.signature_seq'::regclass) | The surrogate key |
| ID | character varying(255) | X |  | The id of the Signature |
| FK_MESSAGE_SID | bigint | X |  | Foreign key that links the Signature to the user message  table |
| SED_SIGNATURE | text |  |  | The sed signature. |
| LAST_UPDATE | timestamp with time zone |  | '2024-06-03 16:57:28.384354+00'::timestamp with time zone | Date & time of last update. |

2.2.87.5 List of keys of the table signature

| Code | Columns | Primary |
| --- | --- | --- |
| pk_signature | sid | X |

2.2.87.6 List of indexes of the table signature

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| message_sid_idx |  |  | CREATE INDEX message_sid_idx ON rina.signature USING btree (fk_message_sid) |
| pk_signature | X | X | CREATE UNIQUE INDEX pk_signature ON rina.signature USING btree (sid) |
| signature_idx | X |  | CREATE UNIQUE INDEX signature_idx ON rina.signature USING btree (sid) |

2.2.87.7 Other constraints of the table signature

_None._

2.2.88 Table subdoc_bversion_attachment

2.2.88.1 Card of table subdoc_bversion_attachment

| Code | Value |
| --- | --- |
| Code | SUBDOC_BVERSION_ATTACHMENT |
| Comment | Many to many table that links subdoc bversions to their attachments |

2.2.88.2 List of incoming references of the table subdoc_bversion_attachment

_None._

2.2.88.3 List of outgoing references of the table subdoc_bversion_attachment

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_subdoc_bver_att__subdoc_att | subdocument_attachment | fk_subdoc_attachment_sid | sid |
| fk_subdoc_bver_att__subdoc_bver | subdocument_bversion | fk_subdoc_bversion_sid | sid |

2.2.88.4 List of columns of the table subdoc_bversion_attachment

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| FK_SUBDOC_ATTACHMENT_SID | bigint | X |  | Linked record field that mapped to the attachments |
| FK_SUBDOC_BVERSION_SID | bigint | X |  | The surrogate key |

2.2.88.5 List of keys of the table subdoc_bversion_attachment

_None._

2.2.88.6 List of indexes of the table subdoc_bversion_attachment

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| subdoc_his_att__doc_att_idx |  |  | CREATE INDEX subdoc_his_att__doc_att_idx ON rina.subdoc_bversion_attachment USING btree (fk_subdoc_attachment_sid) |
| subdoc_his_attach__doc_his_idx |  |  | CREATE INDEX subdoc_his_attach__doc_his_idx ON rina.subdoc_bversion_attachment USING btree (fk_subdoc_bversion_sid) |

2.2.88.7 Other constraints of the table subdoc_bversion_attachment

_None._

2.2.89 Table subdocument

2.2.89.1 Card of table subdocument

| Code | Value |
| --- | --- |
| Code | SUBDOCUMENT |
| Comment | The subdocument table. |

2.2.89.2 List of incoming references of the table subdocument

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| fk_subdoc_attach__subdoc | subdocument_attachment | fk_subdoc_sid |
| fk_subdoc_bversion__subdoc | subdocument_bversion | fk_subdoc_sid |
| fk_subdoc_content_subdoc | subdocument_content | fk_subdoc_sid |
| fk_subdoc_his__subdoc | subdocument_history | fk_subdoc_sid |
| fk_subdoc_prefill__subdoc | subdocument_prefill | fk_subdoc_sid |

2.2.89.3 List of outgoing references of the table subdocument

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_subdoc__doc | document | fk_document_sid | sid |
| fk_subdoc__rina_case | rina_case | fk_case_sid | sid |
| fk_subdoc__subdoc_bversion | subdocument_bversion | fk_subdoc_bversion_sid | sid |

2.2.89.4 List of columns of the table subdocument

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.subdocument_seq'::regclass) | The surrogate key |
| VERSION | integer | X | 1 | The system version. It is automatically increased by Hibernate each time the row is updated. |
| FK_CASE_SID | bigint | X |  | Foreign key that points to the Case table |
| FK_DOCUMENT_SID | bigint | X |  | Foreign key that points to the Document table |
| FK_SUBDOC_BVERSION_SID | bigint |  |  | The content of the document |
| ID | character varying(255) | X |  | The id of the subdocument. |
| NAME | character varying(255) |  |  | The name of the subdocument. |
| NO | bigint |  |  | The number of the subdocument. |
| BUSINESS_REFERENCE | character varying(255) |  |  | The business refference of the subdocument. |
| IS_VALID | boolean | X | true | The is valid flag. |
| IS_ACTIVE | boolean | X | true | The is active flag. |
| VALIDATION_ERRORS | text |  |  | The validation errors occured for this subdocument. |
| CREATED_AT | timestamp with time zone | X | '2024-06-03 16:57:28.40673+00'::timestamp with time zone | Date & Time the entity was created |
| UPDATED_AT | timestamp with time zone | X | '2024-06-03 16:57:28.40673+00'::timestamp with time zone | Date & Time entity was updated |
| CREATED_BY | character varying(255) | X | '0'::character varying | The person/process that created the record. |
| UPDATED_BY | character varying(255) | X | '0'::character varying | The person/process that last updated the record. |
| RANDOM_STRING | character varying(255) | X | 'A1'::character varying | Random string created for the subdocument. |

2.2.89.5 List of keys of the table subdocument

| Code | Columns | Primary |
| --- | --- | --- |
| pk_subdocument | sid | X |

2.2.89.6 List of indexes of the table subdocument

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| pk_subdocument | X | X | CREATE UNIQUE INDEX pk_subdocument ON rina.subdocument USING btree (sid) |
| subdoc__b_ref_idx |  |  | CREATE INDEX subdoc__b_ref_idx ON rina.subdocument USING btree (fk_case_sid, business_reference, is_active) |
| subdoc__case_idx |  |  | CREATE INDEX subdoc__case_idx ON rina.subdocument USING btree (fk_case_sid) |
| subdoc__doc_idx |  |  | CREATE INDEX subdoc__doc_idx ON rina.subdocument USING btree (fk_document_sid) |
| subdoc__subdoc_bversion_idx |  |  | CREATE INDEX subdoc__subdoc_bversion_idx ON rina.subdocument USING btree (fk_subdoc_bversion_sid) |
| subdoc_id_unq | X |  | CREATE UNIQUE INDEX subdoc_id_unq ON rina.subdocument USING btree (fk_case_sid, id, fk_document_sid, is_active) |
| subdocument_idx | X |  | CREATE UNIQUE INDEX subdocument_idx ON rina.subdocument USING btree (sid) |

2.2.89.7 Other constraints of the table subdocument

_None._

2.2.90 Table subdocument_attachment

2.2.90.1 Card of table subdocument_attachment

| Code | Value |
| --- | --- |
| Code | SUBDOCUMENT_ATTACHMENT |
| Comment | Table that holds information about the attachment of the subdocument |

2.2.90.2 List of incoming references of the table subdocument_attachment

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| fk_subdoc_bver_att__subdoc_att | subdoc_bversion_attachment | fk_subdoc_attachment_sid |

2.2.90.3 List of outgoing references of the table subdocument_attachment

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_subdoc_attach__subdoc | subdocument | fk_subdoc_sid | sid |

2.2.90.4 List of columns of the table subdocument_attachment

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.subdoc_attachment_seq'::regclass) | The surrogate key |
| VERSION | integer | X | 1 | The version. |
| FK_SUBDOC_SID | bigint | X |  | Foreign key that points to the subdocument table |
| MIME_TYPE | character varying(50) | X |  | The mime type of the attachment for the subdocument. Possible values: <br>    APP_PDF <br>    APP_MSWORD <br>    APP_MSEXCEL <br>    APP_MSPOWERPOINT <br>    APP_OPENXML_DOC <br>    APP_OPENXML_SPREADSHEET <br>    APP_OPENXML_PRESENTATION <br>    APP_XML <br>    APP_ZIP <br>    APP_GZIP <br>    IMG_JPEG <br>    IMG_PNG <br>    IMG_TIFF <br>    TXT_RTF <br>    TXT_XML <br> <br>    // Mimetypes NOT included in the SBDH XSD definition <br>    APP_X_ZIP <br>    APP_OCTET_STREAM <br>    APP_X_ZIP_COMPRESSED |
| ID | character varying(255) | X |  | The id of the attachment for the subdocument. |
| NAME | character varying(255) |  |  | The name of the attachment for the subdocument. |
| FILENAME | character varying(1024) |  |  | The directory path where the assignment is stored |
| PATHNAME | character varying(1024) | X |  | The complet path of the attachment for the subdocument. |
| IS_MEDICAL | boolean | X | false | The is medical flag. |
| IS_ACTIVE | boolean | X | true | Status of the subdocument |
| CREATED_AT | timestamp with time zone | X | '2024-06-03 16:57:28.453936+00'::timestamp with time zone | Date & Time of Creation. |
| UPDATED_AT | timestamp with time zone | X | '2024-06-03 16:57:28.453936+00'::timestamp with time zone | Date & time of last update. |
| CREATED_BY | character varying(255) | X | '0'::character varying | The person/process that created the record. |
| UPDATED_BY | character varying(255) | X | '0'::character varying | The person/process that last updated the record. |

2.2.90.5 List of keys of the table subdocument_attachment

| Code | Columns | Primary |
| --- | --- | --- |
| pk_subdocument_attachment | sid | X |

2.2.90.6 List of indexes of the table subdocument_attachment

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| pk_subdocument_attachment | X | X | CREATE UNIQUE INDEX pk_subdocument_attachment ON rina.subdocument_attachment USING btree (sid) |
| subdoc_att__subdoc_idx |  |  | CREATE INDEX subdoc_att__subdoc_idx ON rina.subdocument_attachment USING btree (fk_subdoc_sid) |
| subdoc_attachement_idx | X |  | CREATE UNIQUE INDEX subdoc_attachement_idx ON rina.subdocument_attachment USING btree (sid) |
| subdoc_attachment_id_unq | X |  | CREATE UNIQUE INDEX subdoc_attachment_id_unq ON rina.subdocument_attachment USING btree (id, fk_subdoc_sid) |

2.2.90.7 Other constraints of the table subdocument_attachment

_None._

2.2.91 Table subdocument_bversion

2.2.91.1 Card of table subdocument_bversion

| Code | Value |
| --- | --- |
| Code | SUBDOCUMENT_BVERSION |
| Comment | The business version associated to a specific subdocument |

2.2.91.2 List of incoming references of the table subdocument_bversion

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| fk_doc_bv_subdoc_bv__subdoc_bv | doc_bversion_subdoc_bversion | fk_subdoc_bversion_sid |
| fk_subdoc_bver_att__subdoc_bver | subdoc_bversion_attachment | fk_subdoc_bversion_sid |
| fk_subdoc__subdoc_bversion | subdocument | fk_subdoc_bversion_sid |
| fk_subdoc_his__subdoc_bversion | subdocument_history | fk_subdoc_bversion_sid |

2.2.91.3 List of outgoing references of the table subdocument_bversion

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_subdoc_bver__subdoc_content | subdocument_content | fk_subdoc_content_sid | sid |
| fk_subdoc_bversion__subdoc | subdocument | fk_subdoc_sid | sid |

2.2.91.4 List of columns of the table subdocument_bversion

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.subdocument_bversion_seq'::regclass) | The surrogate key |
| FK_SUBDOC_SID | bigint | X |  | Foreign key to the subdocument table. |
| FK_SUBDOC_CONTENT_SID | bigint |  |  | Foreign key to the subdocument content table. |
| ID | integer | X | 1 | The id of the subdocument bversion. |
| IS_ACTIVE | boolean | X | true | The is active flag. |
| VERSION | integer | X | 1 | The system version. It is automatically increased by Hibernate each time the row is updated. |
| CREATED_AT | timestamp with time zone | X | '2024-06-03 16:57:28.489268+00'::timestamp with time zone | The time that the subdocument bversion was first inserted into the DB |
| UPDATED_AT | timestamp with time zone | X | '2024-06-03 16:57:28.489268+00'::timestamp with time zone | The last time that the subdocument bversion was updated |
| CREATED_BY | character varying(255) | X | '0'::character varying | The person/process that created the record. |
| UPDATED_BY | character varying(255) | X | '0'::character varying | The person/process that last updated the record. |

2.2.91.5 List of keys of the table subdocument_bversion

| Code | Columns | Primary |
| --- | --- | --- |
| pk_subdocument_bversion | sid | X |

2.2.91.6 List of indexes of the table subdocument_bversion

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| pk_subdocument_bversion | X | X | CREATE UNIQUE INDEX pk_subdocument_bversion ON rina.subdocument_bversion USING btree (sid) |
| subdoc_bver__subdoc_content_idx |  |  | CREATE INDEX subdoc_bver__subdoc_content_idx ON rina.subdocument_bversion USING btree (fk_subdoc_content_sid) |
| subdoc_bversion__subdoc_idx |  |  | CREATE INDEX subdoc_bversion__subdoc_idx ON rina.subdocument_bversion USING btree (fk_subdoc_sid) |
| subdoc_bversion_unq | X |  | CREATE UNIQUE INDEX subdoc_bversion_unq ON rina.subdocument_bversion USING btree (fk_subdoc_sid, id) |
| subdocument_bversion_idx | X |  | CREATE UNIQUE INDEX subdocument_bversion_idx ON rina.subdocument_bversion USING btree (sid) |

2.2.91.7 Other constraints of the table subdocument_bversion

_None._

2.2.92 Table subdocument_content

2.2.92.1 Card of table subdocument_content

| Code | Value |
| --- | --- |
| Code | SUBDOCUMENT_CONTENT |
| Comment | The content associated to a specific subdocument |

2.2.92.2 List of incoming references of the table subdocument_content

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| fk_subdoc_bver__subdoc_content | subdocument_bversion | fk_subdoc_content_sid |

2.2.92.3 List of outgoing references of the table subdocument_content

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_subdoc_content_subdoc | subdocument | fk_subdoc_sid | sid |

2.2.92.4 List of columns of the table subdocument_content

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.subdocument_content_seq'::regclass) | The surrogate key |
| FK_SUBDOC_SID | bigint | X |  | Foreign key to the subdocument table. |
| CONTENT | text | X |  | The content of the subdocument. |
| IS_ACTIVE | boolean | X | true | The is active flag. |

2.2.92.5 List of keys of the table subdocument_content

| Code | Columns | Primary |
| --- | --- | --- |
| pk_subdocument_content | sid | X |

2.2.92.6 List of indexes of the table subdocument_content

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| pk_subdocument_content | X | X | CREATE UNIQUE INDEX pk_subdocument_content ON rina.subdocument_content USING btree (sid) |
| subdoc_content_idx | X |  | CREATE UNIQUE INDEX subdoc_content_idx ON rina.subdocument_content USING btree (sid) |

2.2.92.7 Other constraints of the table subdocument_content

_None._

2.2.93 Table subdocument_history

2.2.93.1 Card of table subdocument_history

| Code | Value |
| --- | --- |
| Code | SUBDOCUMENT_HISTORY |
| Comment | The history of the subdocument table. |

2.2.93.2 List of incoming references of the table subdocument_history

_None._

2.2.93.3 List of outgoing references of the table subdocument_history

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_subdoc_his__subdoc | subdocument | fk_subdoc_sid | sid |
| fk_subdoc_his__subdoc_bversion | subdocument_bversion | fk_subdoc_bversion_sid | sid |

2.2.93.4 List of columns of the table subdocument_history

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.subdocument_seq'::regclass) | The surrogate key |
| FK_SUBDOC_SID | bigint | X |  | Foreign key that points to subdocument table |
| FK_DOC_SID | bigint | X |  | Foreign key that points to document table |
| FK_CASE_SID | bigint | X |  | Foreign key that points to case table |
| FK_SUBDOC_BVERSION_SID | bigint |  |  | The content of the document |
| VERSION | integer | X |  | The actual version |
| ID | character varying(255) | X |  | The id of the subdocument history |
| NAME | character varying(255) |  |  | The id of the history of the subdocument. |
| UPDATED_AT | timestamp with time zone | X |  | Date & Time the history was updated |
| UPDATED_BY | character varying(255) | X |  | The person/process that last updated the record. |

2.2.93.5 List of keys of the table subdocument_history

| Code | Columns | Primary |
| --- | --- | --- |
| pk_subdocument_history | sid | X |

2.2.93.6 List of indexes of the table subdocument_history

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| pk_subdocument_history | X | X | CREATE UNIQUE INDEX pk_subdocument_history ON rina.subdocument_history USING btree (sid) |
| sobdoc_his__sobdoc_bversion_idx |  |  | CREATE INDEX sobdoc_his__sobdoc_bversion_idx ON rina.subdocument_history USING btree (fk_subdoc_bversion_sid) |
| subdoc_his__subdoc_idx |  |  | CREATE INDEX subdoc_his__subdoc_idx ON rina.subdocument_history USING btree (fk_subdoc_sid) |
| subdoc_his_idx | X |  | CREATE UNIQUE INDEX subdoc_his_idx ON rina.subdocument_history USING btree (sid) |
| subdoc_his_sid_version_unq | X |  | CREATE UNIQUE INDEX subdoc_his_sid_version_unq ON rina.subdocument_history USING btree (fk_subdoc_sid, version) |

2.2.93.7 Other constraints of the table subdocument_history

_None._

2.2.94 Table subdocument_prefill

2.2.94.1 Card of table subdocument_prefill

| Code | Value |
| --- | --- |
| Code | SUBDOCUMENT_PREFILL |
| Comment | The prefill data  associated to a specific subdocument |

2.2.94.2 List of incoming references of the table subdocument_prefill

_None._

2.2.94.3 List of outgoing references of the table subdocument_prefill

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_subdoc_prefill__subdoc | subdocument | fk_subdoc_sid | sid |

2.2.94.4 List of columns of the table subdocument_prefill

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.subdoc_prefill_seq'::regclass) | The surrogate key |
| FK_SUBDOC_SID | bigint | X |  | Foreign key to the subdocument table |
| PREFILL_GROUP | character varying(20) | X | 'PREFILL'::character varying | The prefill group value of the subdocument. Possible values: <br>    SUBJECT, <br>    PREFILL, <br>    SEARCH_METADATA; |
| KEY | character varying(1024) | X |  | The key for the prefill of the subdocument. |
| VALUE | text | X |  | The value for the prefill of the subdocument. |

2.2.94.5 List of keys of the table subdocument_prefill

| Code | Columns | Primary |
| --- | --- | --- |
| pk_subdocument_prefill | sid | X |

2.2.94.6 List of indexes of the table subdocument_prefill

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| pk_subdocument_prefill | X | X | CREATE UNIQUE INDEX pk_subdocument_prefill ON rina.subdocument_prefill USING btree (sid) |
| subdoc_prefill__group_idx |  |  | CREATE INDEX subdoc_prefill__group_idx ON rina.subdocument_prefill USING btree (prefill_group) |
| subdoc_prefill__key_unq | X |  | CREATE UNIQUE INDEX subdoc_prefill__key_unq ON rina.subdocument_prefill USING btree (fk_subdoc_sid, prefill_group, key) |
| subdoc_prefill__subdoc_idx |  |  | CREATE INDEX subdoc_prefill__subdoc_idx ON rina.subdocument_prefill USING btree (fk_subdoc_sid) |
| subdoc_prefill_idx | X |  | CREATE UNIQUE INDEX subdoc_prefill_idx ON rina.subdocument_prefill USING btree (sid) |

2.2.94.7 Other constraints of the table subdocument_prefill

_None._

2.2.95 Table supported_language

2.2.95.1 Card of table supported_language

| Code | Value |
| --- | --- |
| Code | SUPPORTED_LANGUAGE |
| Comment | Table that holds the language code |

2.2.95.2 List of incoming references of the table supported_language

_None._

2.2.95.3 List of outgoing references of the table supported_language

_None._

2.2.95.4 List of columns of the table supported_language

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.supported_language_seq'::regclass) | The surrogate key |
| LANG | character varying(2) | X |  | The language code |

2.2.95.5 List of keys of the table supported_language

| Code | Columns | Primary |
| --- | --- | --- |
| pk_supported_language | sid | X |

2.2.95.6 List of indexes of the table supported_language

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| pk_supported_language | X | X | CREATE UNIQUE INDEX pk_supported_language ON rina.supported_language USING btree (sid) |
| supported_language_idx | X |  | CREATE UNIQUE INDEX supported_language_idx ON rina.supported_language USING btree (sid) |
| supported_language_lang_unq | X |  | CREATE UNIQUE INDEX supported_language_lang_unq ON rina.supported_language USING btree (lang) |

2.2.95.7 Other constraints of the table supported_language

_None._

2.2.96 Table tenant

2.2.96.1 Card of table tenant

| Code | Value |
| --- | --- |
| Code | TENANT |
| Comment | Table that holds information about the Tenant |

2.2.96.2 List of incoming references of the table tenant

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| fk_assignment_pol__tenant | assignment_policy | fk_tenant_sid |
| fk_ass_pol_trgt__tenant | assignment_policy_target | fk_tenant_sid |
| fk_iam_group__tenant | iam_group | fk_tenant_sid |
| fk_iam_user__tenant | iam_user | fk_tenant_sid |
| fk_policy__tenant | policy | fk_tenant_sid |
| fk_case__tenant | rina_case | fk_tenant_sid |
| fk_tenant_param__tenant | tenant_param | fk_tenant_sid |
| fk_tenant_param_group___tenant | tenant_param_group | fk_tenant_sid |

2.2.96.3 List of outgoing references of the table tenant

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_tenant__organisation | organisation | fk_org_sid | sid |

2.2.96.4 List of columns of the table tenant

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.tenant_seq'::regclass) | The surrogate key |
| VERSION | integer | X | 1 | The system version. It is automatically increased by Hibernate each time the row is updated. |
| FK_ORG_SID | bigint | X |  | Foreign key to the organisation table. |
| ID | character varying(255) | X |  | The id of the tenant |
| IS_ENABLED | boolean | X | true | Use to check if enable or not |
| IS_DEFAULT | boolean | X | false | Use to check if it is default tenant or not |
| INCOMING_MSG_RELATIVE_PATH | character varying(255) |  |  | The ralative path od the incoming message |
| CREATED_AT | timestamp with time zone | X | '2024-06-03 16:57:28.756522+00'::timestamp with time zone | Date & Time by whom the tenant was created |
| UPDATED_AT | timestamp with time zone | X | '2024-06-03 16:57:28.756522+00'::timestamp with time zone | Date & Time the tenant's details was updated |

2.2.96.5 List of keys of the table tenant

| Code | Columns | Primary |
| --- | --- | --- |
| pk_tenant | sid | X |

2.2.96.6 List of indexes of the table tenant

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| pk_tenant | X | X | CREATE UNIQUE INDEX pk_tenant ON rina.tenant USING btree (sid) |
| tenant__org_idx | X |  | CREATE UNIQUE INDEX tenant__org_idx ON rina.tenant USING btree (fk_org_sid) |
| tenant_id_unq | X |  | CREATE UNIQUE INDEX tenant_id_unq ON rina.tenant USING btree (id) |
| tenant_idx | X |  | CREATE UNIQUE INDEX tenant_idx ON rina.tenant USING btree (sid) |

2.2.96.7 Other constraints of the table tenant

_None._

2.2.97 Table tenant_param

2.2.97.1 Card of table tenant_param

| Code | Value |
| --- | --- |
| Code | TENANT_PARAM |
| Comment | Parameters assosiated with a tenant |

2.2.97.2 List of incoming references of the table tenant_param

_None._

2.2.97.3 List of outgoing references of the table tenant_param

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_tenant_param__tenant | tenant | fk_tenant_sid | sid |
| tenant_param__tenant_param_grp | tenant_param_group | fk_tenant_param_group_sid | sid |

2.2.97.4 List of columns of the table tenant_param

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.tenant_param_seq'::regclass) | The surrogate key |
| FK_TENANT_SID | bigint | X |  | Foreign key to the tenant table. |
| FK_TENANT_PARAM_GROUP_SID | bigint |  |  | Foreign key to the tenant param group table. |
| KEY | character varying(255) | X |  | The key of the parameter |
| VALUE | character varying(255) | X |  | The value of the parameter |

2.2.97.5 List of keys of the table tenant_param

| Code | Columns | Primary |
| --- | --- | --- |
| pk_tenant_param | sid | X |

2.2.97.6 List of indexes of the table tenant_param

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| pk_tenant_param | X | X | CREATE UNIQUE INDEX pk_tenant_param ON rina.tenant_param USING btree (sid) |
| tenant_param__tenant_idx |  |  | CREATE INDEX tenant_param__tenant_idx ON rina.tenant_param USING btree (fk_tenant_sid) |
| tenant_param_idx | X |  | CREATE UNIQUE INDEX tenant_param_idx ON rina.tenant_param USING btree (sid) |
| tenant_param_key_unq | X |  | CREATE UNIQUE INDEX tenant_param_key_unq ON rina.tenant_param USING btree (fk_tenant_sid, key) |
| tenant_prm__tenant_prm_grp_idx |  |  | CREATE INDEX tenant_prm__tenant_prm_grp_idx ON rina.tenant_param USING btree (fk_tenant_param_group_sid) |

2.2.97.7 Other constraints of the table tenant_param

_None._

2.2.98 Table tenant_param_group

2.2.98.1 Card of table tenant_param_group

| Code | Value |
| --- | --- |
| Code | TENANT_PARAM_GROUP |
| Comment | Table that holds a group of global_application_params, with version for optimistic locking and auditing properties. |

2.2.98.2 List of incoming references of the table tenant_param_group

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| tenant_param__tenant_param_grp | tenant_param | fk_tenant_param_group_sid |

2.2.98.3 List of outgoing references of the table tenant_param_group

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_tenant_param_group___tenant | tenant | fk_tenant_sid | sid |

2.2.98.4 List of columns of the table tenant_param_group

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.tenant_param_group_seq'::regclass) | The surrogate key |
| VERSION | integer | X | 1 | The system version. It is automatically increased by Hibernate each time the row is updated. |
| FK_TENANT_SID | bigint | X |  | Foreign key to the tenant table. |
| NAME | character varying(255) | X |  | The name of the tennant param group. Possible values: <br>    CASE_COUNTER_SETTINGS, <br>    LDAP_CONNECTION_SETTINGS, <br>    LDAP_USER_PARAMETERS_MAPPING, <br>    LDAP_GROUP_PARAMETERS_MAPPING, <br>    MESSAGE_SETTINGS_PARAMETERS_MAPPING; |
| CREATED_AT | timestamp with time zone | X | '2024-06-03 16:57:28.842016+00'::timestamp with time zone | Date & Time by whom the tenant was created |
| UPDATED_AT | timestamp with time zone | X | '2024-06-03 16:57:28.842016+00'::timestamp with time zone | Date & Time the tenant's details was updated |
| CREATED_BY | character varying(255) | X | '0'::character varying | The person/process that created the record. |
| UPDATED_BY | character varying(255) | X | '0'::character varying | The person/process that last updated the record. |
| RANDOM_STRING | character varying(255) | X | 'A1'::character varying | Random string created for the tenant param group. |

2.2.98.5 List of keys of the table tenant_param_group

| Code | Columns | Primary |
| --- | --- | --- |
| pk_tenant_param_group | sid | X |

2.2.98.6 List of indexes of the table tenant_param_group

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| pk_tenant_param_group | X | X | CREATE UNIQUE INDEX pk_tenant_param_group ON rina.tenant_param_group USING btree (sid) |
| tenant_param_group__tenant_idx |  |  | CREATE INDEX tenant_param_group__tenant_idx ON rina.tenant_param_group USING btree (fk_tenant_sid) |
| tenant_param_group_idx | X |  | CREATE UNIQUE INDEX tenant_param_group_idx ON rina.tenant_param_group USING btree (sid) |
| tenant_param_group_name_unq | X |  | CREATE UNIQUE INDEX tenant_param_group_name_unq ON rina.tenant_param_group USING btree (fk_tenant_sid, name) |

2.2.98.7 Other constraints of the table tenant_param_group

_None._

2.2.99 Table translation

2.2.99.1 Card of table translation

| Code | Value |
| --- | --- |
| Code | TRANSLATION |
| Comment | Table that holds the transation per language |

2.2.99.2 List of incoming references of the table translation

_None._

2.2.99.3 List of outgoing references of the table translation

_None._

2.2.99.4 List of columns of the table translation

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.translation_seq'::regclass) | The surrogate key |
| LANG | character varying(2) | X |  | The language code. Possible values: <br>    bg, <br>    cs, <br>    da, <br>    de, <br>    en, <br>    el, <br>    es, <br>    et, <br>    fi, <br>    fr, <br>    hr, <br>    hu, <br>    it, <br>    lt, <br>    lv, <br>    mt, <br>    nl, <br>    no, <br>    pl, <br>    pt, <br>    ro, <br>    sk, <br>    sl, <br>    sv, |
| CONTENT | text | X |  | The content of the translation. |

2.2.99.5 List of keys of the table translation

| Code | Columns | Primary |
| --- | --- | --- |
| pk_translation | sid | X |

2.2.99.6 List of indexes of the table translation

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| pk_translation | X | X | CREATE UNIQUE INDEX pk_translation ON rina.translation USING btree (sid) |
| translation_idx | X |  | CREATE UNIQUE INDEX translation_idx ON rina.translation USING btree (sid) |
| translation_lang_unq | X |  | CREATE UNIQUE INDEX translation_lang_unq ON rina.translation USING btree (lang) |

2.2.99.7 Other constraints of the table translation

_None._

2.2.100 Table transposition

2.2.100.1 Card of table transposition

| Code | Value |
| --- | --- |
| Code | TRANSPOSITION |
| Comment | The transposition json, pertinent to a specific document type |

2.2.100.2 List of incoming references of the table transposition

_None._

2.2.100.3 List of outgoing references of the table transposition

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_transpos__doc_type_version | document_type_version | fk_doc_type_version_sid | sid |
| fk_transpos__proc_def_version | process_def_version | fk_proc_def_version_sid | sid |

2.2.100.4 List of columns of the table transposition

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.transposition_seq'::regclass) | The surrogate key |
| FK_PROC_DEF_VERSION_SID | bigint | X |  | Foreign key that links the Case to the process definition's version  table |
| FK_DOC_TYPE_VERSION_SID | bigint | X |  | Foreign key to document_type table |
| APPLICATION_ROLE | character varying(2) | X |  | The Application Role. Possible values: <br>    PO("CaseOwner"), <br>    CP("CounterParty"); |
| JSON | text | X |  | The json of the transposition. |

2.2.100.5 List of keys of the table transposition

| Code | Columns | Primary |
| --- | --- | --- |
| pk_transposition | sid | X |

2.2.100.6 List of indexes of the table transposition

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| pk_transposition | X | X | CREATE UNIQUE INDEX pk_transposition ON rina.transposition USING btree (sid) |
| transpos__doc_type_version_idx |  |  | CREATE INDEX transpos__doc_type_version_idx ON rina.transposition USING btree (fk_doc_type_version_sid) |
| transpos__proc_def_version_idx |  |  | CREATE INDEX transpos__proc_def_version_idx ON rina.transposition USING btree (fk_proc_def_version_sid) |
| transposition_idx | X |  | CREATE UNIQUE INDEX transposition_idx ON rina.transposition USING btree (sid) |
| transposition_unq | X |  | CREATE UNIQUE INDEX transposition_unq ON rina.transposition USING btree (fk_proc_def_version_sid, fk_doc_type_version_sid, application_role) |

2.2.100.7 Other constraints of the table transposition

_None._

2.2.101 Table user_message

2.2.101.1 Card of table user_message

| Code | Value |
| --- | --- |
| Code | USER_MESSAGE |
| Comment | The user message associated to a specific conversation  |

2.2.101.2 List of incoming references of the table user_message

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| fk_signature__message | signature | fk_message_sid |
| fk_usr_msg_res__usr_msg | user_message_response | fk_message_sid |

2.2.101.3 List of outgoing references of the table user_message

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_user_msg__doc_conv | document_conversation | fk_doc_conv_sid | sid |
| fk_user_msg__receiver | organisation | fk_receiver_sid | sid |
| fk_user_msg__sender | organisation | fk_sender_sid | sid |

2.2.101.4 List of columns of the table user_message

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.user_msg_seq'::regclass) | The surrogate key |
| FK_SENDER_SID | bigint | X |  | Foreign key to the user table. |
| FK_RECEIVER_SID | bigint | X |  | Foreign key to the user table. |
| FK_DOC_CONV_SID | bigint | X |  | Foreign key to the document conversation table. |
| ID | character varying(255) | X |  | The id of the user message. |
| DIRECTION | character varying(15) | X |  | The direction of the user message. Possible values: <br>IN("IN"), <br>OUT("OUT"); |
| ACTION | character varying(15) | X |  | The action of the user message. Possible values: <br>    START("Start"), <br>    NEW("New"), <br>    UPDATE("Update"), <br>    START_FORWARD("StartForward"), <br>    NEW_FORWARD("NewForward"); |
| SBDH | text | X |  | The sdbh of the user message. |
| STATUS | character varying(50) |  |  | The status of the user message. Possible values: <br>    SENT("sent"), <br>    DELIVERED("delivered"), <br>    ERROR("error"), <br>    RESENT("resent"); |
| LAST_UPDATE | timestamp with time zone |  |  | Date & time of last update. |

2.2.101.5 List of keys of the table user_message

| Code | Columns | Primary |
| --- | --- | --- |
| pk_user_message | sid | X |

2.2.101.6 List of indexes of the table user_message

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| pk_user_message | X | X | CREATE UNIQUE INDEX pk_user_message ON rina.user_message USING btree (sid) |
| user_msg__receiver_idx |  |  | CREATE INDEX user_msg__receiver_idx ON rina.user_message USING btree (fk_receiver_sid) |
| user_msg__sender_idx |  |  | CREATE INDEX user_msg__sender_idx ON rina.user_message USING btree (fk_sender_sid) |
| user_msg_id_sent_unq | X |  | CREATE UNIQUE INDEX user_msg_id_sent_unq ON rina.user_message USING btree (id, fk_doc_conv_sid) |
| user_msg_idx | X |  | CREATE UNIQUE INDEX user_msg_idx ON rina.user_message USING btree (sid) |

2.2.101.7 Other constraints of the table user_message

_None._

2.2.102 Table user_message_response

2.2.102.1 Card of table user_message_response

| Code | Value |
| --- | --- |
| Code | USER_MESSAGE_RESPONSE |
| Comment | Table that holds information about the user message response (ack / error) |

2.2.102.2 List of incoming references of the table user_message_response

_None._

2.2.102.3 List of outgoing references of the table user_message_response

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_usr_msg_res__usr_msg | user_message | fk_message_sid | sid |

2.2.102.4 List of columns of the table user_message_response

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.user_message_response_seq'::regclass) | The surrogate key |
| FK_MESSAGE_SID | bigint | X |  | Foreign key that links the User message Response to the user message  table |
| ID | character varying(255) | X |  | The id of the user message response. |
| TYPE | character varying(6) | X |  | The type of the user message response. Possible values: <br>USERMESSAGE("usermessage"), <br>ACK("ACK"), <br>ERROR("ERROR"); |
| DESCRIPTION | text |  |  | The description of  the user message response. |
| LAST_UPDATE | timestamp with time zone |  |  | Date & time of last update. |

2.2.102.5 List of keys of the table user_message_response

| Code | Columns | Primary |
| --- | --- | --- |
| pk_user_message_response | sid | X |

2.2.102.6 List of indexes of the table user_message_response

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| pk_user_message_response | X | X | CREATE UNIQUE INDEX pk_user_message_response ON rina.user_message_response USING btree (sid) |
| user_message_resp_idx | X |  | CREATE UNIQUE INDEX user_message_resp_idx ON rina.user_message_response USING btree (sid) |
| user_message_resp_msg_idx |  |  | CREATE INDEX user_message_resp_msg_idx ON rina.user_message_response USING btree (fk_message_sid) |

2.2.102.7 Other constraints of the table user_message_response

_None._

2.2.103 Table user_profile

2.2.103.1 Card of table user_profile

| Code | Value |
| --- | --- |
| Code | USER_PROFILE |
| Comment | The table that holds the user profile. |

2.2.103.2 List of incoming references of the table user_profile

_None._

2.2.103.3 List of outgoing references of the table user_profile

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_user_profile__process_def | process_def | fk_proc_def_sid | sid |
| fk_user_profile__user | iam_user | fk_user_sid | sid |

2.2.103.4 List of columns of the table user_profile

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.user_profile_seq'::regclass) | The surrogate key |
| VERSION | integer | X | 1 | The system version. It is automatically increased by Hibernate each time the row is updated. <br> |
| FK_USER_SID | bigint | X |  | Foreign Key to User table |
| FK_PROC_DEF_SID | bigint |  |  | Foreign key to the process definition table. |
| LANG | character varying(2) |  |  | The language of the profile for the user. Possible values: <br>    bg, <br>    cs, <br>    da, <br>    de, <br>    en, <br>    el, <br>    es, <br>    et, <br>    fi, <br>    fr, <br>    hr, <br>    hu, <br>    it, <br>    lt, <br>    lv, <br>    mt, <br>    nl, <br>    no, <br>    pl, <br>    pt, <br>    ro, <br>    sk, <br>    sl, <br>    sv, |
| ALARM_AUTO_SET_DAYS | integer |  |  | The alarm auto set days flag. |
| ALARM_AUTO_SET_ON_SEND | boolean |  |  | The alarm auto set on send flag. |
| DOCUMENT_DSPLAY_MODE | character varying(255) |  |  | The display mode of the document for that profile |
| DOCUMENT_SORTBY | character varying(255) |  |  | how is  the document sort by for that profile |
| DOCUMENT_SHOWFLAGS | boolean |  |  | flag to show document or not for that profile |
| FILTER_ACTION_TYPE | character varying(10) |  |  | The filter action type of profile |
| CLASSIC_GROUP_BY_MONTH | boolean |  |  | Use to flag if it is a classic group by month or not |
| CLASSIC_SHOW_PREVIEW | boolean |  |  | Use to flag if it is a classic group by month or not |
| TIMELINE_DISPLAY_THUMBNAILS | boolean |  |  | Use to flag how to display  thumbnails or not |
| TIMELINE_DISPLAY_MODE | character varying(20) |  |  | holda the display mode |
| LOCALE_LANG | character varying(2) |  |  | holds the local language for that profile. Possible values: <br>    bg, <br>    cs, <br>    da, <br>    de, <br>    en, <br>    el, <br>    es, <br>    et, <br>    fi, <br>    fr, <br>    hr, <br>    hu, <br>    it, <br>    lt, <br>    lv, <br>    mt, <br>    nl, <br>    no, <br>    pl, <br>    pt, <br>    ro, <br>    sk, <br>    sl, <br>    sv, |
| LOCALE_NUMBER_FORMAT | character varying(20) |  |  | holds the locale number format for that profile |
| LOCALE_DATE_FORMAT | character varying(20) |  |  | The format of the locale for the date. |
| LOCALE_TIME_FORMAT | character varying(20) |  |  | holds the local time format for that profile |
| LOCALE_CURRENCY | character varying(3) |  |  | holds the local currency format for that profile |
| LOCALE_TIMEZONE | character varying(3) |  |  | holds the local time zone for that profile |
| CREATED_AT | timestamp with time zone | X | '2024-06-03 16:57:29.069979+00'::timestamp with time zone | Date & Time the User Profile was created |
| UPDATED_AT | timestamp with time zone | X | '2024-06-03 16:57:29.069979+00'::timestamp with time zone | Date & Time the User Profile was updated |
| CREATED_BY | character varying(255) | X | '0'::character varying | The person/process that created the record. |
| UPDATED_BY | character varying(255) | X | '0'::character varying | The person/process that last updated the record. |

2.2.103.5 List of keys of the table user_profile

| Code | Columns | Primary |
| --- | --- | --- |
| pk_user_profile | sid | X |

2.2.103.6 List of indexes of the table user_profile

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| pk_user_profile | X | X | CREATE UNIQUE INDEX pk_user_profile ON rina.user_profile USING btree (sid) |
| user_profile_iam_user_unq | X |  | CREATE UNIQUE INDEX user_profile_iam_user_unq ON rina.user_profile USING btree (fk_user_sid) |
| user_profile_idx | X |  | CREATE UNIQUE INDEX user_profile_idx ON rina.user_profile USING btree (sid) |

2.2.103.7 Other constraints of the table user_profile

_None._

2.2.104 Table vocabulary

2.2.104.1 Card of table vocabulary

| Code | Value |
| --- | --- |
| Code | VOCABULARY |
| Comment | Table that holds vocabularies related to a vocabulary_type |

2.2.104.2 List of incoming references of the table vocabulary

_None._

2.2.104.3 List of outgoing references of the table vocabulary

| Code | Parent Table | Foreign Key Columns | Referenced Columns |
| --- | --- | --- | --- |
| fk_voc_type__voc | vocabulary_type | fk_vocabulary_type_sid | sid |

2.2.104.4 List of columns of the table vocabulary

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.vocabulary_seq'::regclass) | The surrogate key |
| FK_VOCABULARY_TYPE_SID | bigint | X |  | foreign key to the vocabulary_type table |
| CODE | character varying(255) |  |  | The code of the concept |
| NAME | character varying(255) |  |  | the name of the concept |
| COLOR | character varying(30) |  |  | The color that the concept is depicted |
| ALT_COLOR | character varying(30) |  |  | The alternative color that the concept is depicted |
| ICON | character varying(100) |  |  | the icon used for the concept |
| TEMPLATE | character varying(255) |  |  | the template used for the concept |
| DESCRIPTION | character varying(255) |  |  | the description of the concept |
| SEVERITY | character varying(20) |  |  | the severity of the concept |
| VALUE | character varying(20) |  |  | The value of the vocabulary record. |

2.2.104.5 List of keys of the table vocabulary

| Code | Columns | Primary |
| --- | --- | --- |
| pk_vocabulary | sid | X |

2.2.104.6 List of indexes of the table vocabulary

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| pk_vocabulary | X | X | CREATE UNIQUE INDEX pk_vocabulary ON rina.vocabulary USING btree (sid) |
| voc_type__voc_idx |  |  | CREATE INDEX voc_type__voc_idx ON rina.vocabulary USING btree (fk_vocabulary_type_sid) |
| voc_voc_type__code | X |  | CREATE UNIQUE INDEX voc_voc_type__code ON rina.vocabulary USING btree (code, fk_vocabulary_type_sid) |
| vocabulary_idx | X |  | CREATE UNIQUE INDEX vocabulary_idx ON rina.vocabulary USING btree (sid) |

2.2.104.7 Other constraints of the table vocabulary

_None._

2.2.105 Table vocabulary_type

2.2.105.1 Card of table vocabulary_type

| Code | Value |
| --- | --- |
| Code | VOCABULARY_TYPE |
| Comment | Table that holds a list of vocabulary types |

2.2.105.2 List of incoming references of the table vocabulary_type

| Code | Child Table | Foreign Key Columns |
| --- | --- | --- |
| fk_voc_type__voc | vocabulary | fk_vocabulary_type_sid |

2.2.105.3 List of outgoing references of the table vocabulary_type

_None._

2.2.105.4 List of columns of the table vocabulary_type

| Code | Data Type | Mandatory | Default Value | Comment |
| --- | --- | --- | --- | --- |
| SID | bigint | X | nextval('rina.vocabulary_type_seq'::regclass) | The surrogate key |
| TYPE | character varying(255) | X |  | The type of the vocabulary. Possible values: <br>    NOTIFICATION_SEVERITIES("NotificationSeverities"), <br>    IMPORTANCE("importance"), <br>    COLORS("colors"), <br>    DOCUMENT_STATUSES("documentstatuses"), <br>    NOTIFICATION_TYPES("notificationtypes"), <br>    NOTIFICATION_READ_STATUSES("NotificationReadStatuses"), <br>    SUPPORT_TICKET_TYPES("supportTicketTypes"), <br>    AUDIT_ACTION_TYPES("AuditActionTypes"), <br>    AUDITED_OBJECT_TYPES("AuditedObjectTypes"), <br>    AUDIT_COMPONENT_TYPES("AuditComponentTypes"), <br>    AUDIT_CATEGORY_TYPES("AuditCategoryTypes"), <br>    AUDIT_EVENT_TYPES("AuditEventTypes"), <br>    TECHNICAL_LOG_LEVELS("TechnicalLogLevels"), <br>    RESOURCE_TYPES("ResourceTypes"), <br>    RESOURCES_STATUS_TYPES("ResourceStatusTypes"), <br>    BMP_VALIDATION_MODES("BMPValidationModes"), <br>    X002_REASONS_FOR_REQUEST("X002ReasonsForRequest"), <br>    YES1NO2("Yes1No2"), <br>    LANGUAGES("Languages"), <br>    COUNTRIES("Countries"), <br>    NUMBER_FORMATS("NumberFormats"), <br>    DATE_FORMATS("DateFormats"), <br>    TIME_FORMATS("TimeFormats"), <br>    CURRENCIES("Currencies"), <br>    TIMEZONES("TimeZones"), <br>    BEXCEPTION_TYPES("bexceptiontypes"), <br>    BUSINESS_EXCEPTION_TYPES("BusinessExceptionTypes"), <br>    CRITICALITY("criticality"), <br>    CASESTATUSES("casestatuses"), <br>    TIME_INTERVALS("timeIntervals"), <br>    SUPPORT_TICKET_PRIORITIES("supportTicketPriorities"), <br>    AUDIT_OUTCOME_TYPES("AuditOutcomeTypes"), <br>    AUDIT_PARTICIPANT_TYPES("AuditParticipantTypes"), <br>    AUDIT_PARTICIPANT_ROLES("AuditParticipantRoles"), <br>    SED_VALIDATION_MODES("SEDValidationModes"), <br>    X001_REASONS_FOR_CLOSING("X001ReasonsForClosing"), <br>    X004_DECISIONS("X004Decisions"),     <br>    X009_URGENCY("X009Urgency"), <br>    NOTIFICATION_STATUSES("NotificationStatuses"), <br>    RESOURCE_CHANGE_TYPES("ResourceChangeTypes"), <br>    X001_CLOSE_TYPES("X001CloseTypes"), <br>    AUTHENTICATION_CHANNELS("AuthenticationChannels"), <br>    TECHNICAL_LOG_TYPES("TechnicalLogTypes"); |

2.2.105.5 List of keys of the table vocabulary_type

| Code | Columns | Primary |
| --- | --- | --- |
| pk_vocabulary_type | sid | X |

2.2.105.6 List of indexes of the table vocabulary_type

| Code | Unique | Primary | Definition |
| --- | --- | --- | --- |
| pk_vocabulary_type | X | X | CREATE UNIQUE INDEX pk_vocabulary_type ON rina.vocabulary_type USING btree (sid) |
| vocabulary_type_idx | X |  | CREATE UNIQUE INDEX vocabulary_type_idx ON rina.vocabulary_type USING btree (sid) |
| vocabulary_type_type_unq | X |  | CREATE UNIQUE INDEX vocabulary_type_type_unq ON rina.vocabulary_type USING btree (type) |

2.2.105.7 Other constraints of the table vocabulary_type

_None._

### 2.3 Views and materialized views

2.3.1 View v_audit_search

| Attribute | Value |
| --- | --- |
| Name | v_audit_search |
| Type | view |
| Comment | The view responsible for allowing the audit search to work using specific keywords indexed and added here, using Postgress TsVector search functionality. |

```sql
SELECT audit_sid,
    audit_id,
    username,
    net_location_machine,
    net_location_ip,
    outcome_type,
    outcome_details,
    audit_obj_details,
    to_tsvector((((((((((((((audit_sid || ' '::text) || audit_id::text) || ' '::text) || username::text) || ' '::text) || net_location_machine::text) || ' '::text) || net_location_ip) || ' '::text) || outcome_type::text) || ' '::text) || outcome_details) || ' '::text) || audit_obj_details) AS tsvector
   FROM ( SELECT ae.sid AS audit_sid,
            COALESCE(ae.id, ''::character varying) AS audit_id,
            COALESCE(ae.created_by, ''::character varying) AS username,
            COALESCE(ae.net_location_machine, ''::character varying) AS net_location_machine,
            COALESCE(ae.net_location_ip, ''::text) AS net_location_ip,
            COALESCE(ae.outcome_type, ''::character varying) AS outcome_type,
            COALESCE(ae.outcome_details, ''::text) AS outcome_details,
            COALESCE(ae.created_by, ''::character varying) AS created_by,
            COALESCE(ao.details, ''::text) AS audit_obj_details
           FROM rina.audit_event ae
             LEFT JOIN rina.audit_object ao ON ae.sid = ao.fk_audit_event_sid) result;
```

2.3.2 View v_business_ex_search

| Attribute | Value |
| --- | --- |
| Name | v_business_ex_search |
| Type | view |
| Comment | The view responsible for allowing the business exeptions and pending messages search to work using specific keywords indexed and added here, using Postgress TsVector search functionality. |

```sql
SELECT business_ex_sid,
    pend_msg_sid,
    business_ex_id,
    reason,
    pend_msg_id,
    sbdh,
    content_location,
    action_type,
    international_case_id,
    is_protected_person,
    should_notify,
    is_processed,
    problem,
    cause,
    to_tsvector((((((((((((((((((((((business_ex_id::text || ' '::text) || reason::text) || ' '::text) || pend_msg_id::text) || ' '::text) || sbdh) || ' '::text) || content_location::text) || ' '::text) || action_type::text) || ' '::text) || international_case_id::text) || ' '::text) || is_protected_person) || ' '::text) || should_notify) || ' '::text) || is_processed) || ' '::text) || problem::text) || ' '::text) || cause::text) AS tsvector
   FROM ( SELECT be.sid AS business_ex_sid,
            pm.sid AS pend_msg_sid,
            COALESCE(be.id, ''::character varying) AS business_ex_id,
            COALESCE(be.reason, ''::character varying) AS reason,
            COALESCE(pm.id, ''::character varying) AS pend_msg_id,
            COALESCE(pm.sbdh, ''::text) AS sbdh,
            COALESCE(pm.content_location, ''::character varying) AS content_location,
            pm.is_protected_person,
            COALESCE(pm.action_type, ''::character varying) AS action_type,
            COALESCE(pm.international_case_id, ''::character varying) AS international_case_id,
            pm.should_notify,
            pm.is_processed,
            COALESCE(pm.problem, ''::character varying) AS problem,
            COALESCE(pm.cause, ''::character varying) AS cause
           FROM rina.pending_message pm
             LEFT JOIN rina.business_exception be ON pm.sid = be.fk_pend_msg_sid) result;
```

2.3.3 View v_case_search

| Attribute | Value |
| --- | --- |
| Name | v_case_search |
| Type | view |
| Comment | The view responsible for allowing the cases search to work using specific keywords indexed and added here, using Postgress TsVector search functionality. |

```sql
SELECT vcs.fk_case_sid,
    vcs.case_id,
    vcs.case_int_id,
    vcs.case_status,
    vcs.buc_type,
    vcs.buc_name,
    vcs.case_agg_search,
    vcs.tsvector
   FROM rina.v_case_search_mat vcs
  WHERE NOT (EXISTS ( SELECT vcs.fk_case_sid
           FROM rina.v_case_search_last24h l24h
          WHERE vcs.fk_case_sid = l24h.fk_case_sid))
UNION
 SELECT v_case_search_last24h.fk_case_sid,
    v_case_search_last24h.case_id,
    v_case_search_last24h.case_int_id,
    v_case_search_last24h.case_status,
    v_case_search_last24h.buc_type,
    v_case_search_last24h.buc_name,
    v_case_search_last24h.case_agg_search,
    v_case_search_last24h.tsvector
   FROM rina.v_case_search_last24h;
```

2.3.4 View v_case_search_last24h

| Attribute | Value |
| --- | --- |
| Name | v_case_search_last24h |
| Type | view |
| Comment |  |

```sql
SELECT rc.sid AS fk_case_sid,
    rc.id AS case_id,
    rc.international_id AS case_int_id,
    rc.status AS case_status,
    pd.id AS buc_type,
    pd.name AS buc_name,
    COALESCE(pivot.agg_preffils, ''::text) AS case_agg_search,
    to_tsvector((((((((((rc.id::text || ' '::text) || COALESCE(pivot.agg_preffils, ''::text)) || ' '::text) || rc.status::text) || ' '::text) || pd.id::text) || ' '::text) || pd.name::text) || ' '::text) || rc.international_id::text) AS tsvector
   FROM rina.rina_case rc
     JOIN rina.process_def_version pdv ON rc.fk_proc_def_version_sid = pdv.sid
     JOIN rina.process_def pd ON pdv.fk_proc_def_sid = pd.sid
     LEFT JOIN ( SELECT cp.fk_case_sid,
            string_agg(cp.value, ' '::text) AS agg_preffils
           FROM rina.case_prefill cp
          WHERE cp.prefill_group::text = 'SEARCH_METADATA'::text
          GROUP BY cp.fk_case_sid) pivot ON rc.sid = pivot.fk_case_sid
  WHERE rc.updated_at > (now() - '1 day'::interval);
```

2.3.5 Materialized View v_case_search_mat

| Attribute | Value |
| --- | --- |
| Name | v_case_search_mat |
| Type | materialized view |
| Comment |  |

```sql
SELECT rc.sid AS fk_case_sid,
    rc.id AS case_id,
    rc.international_id AS case_int_id,
    rc.status AS case_status,
    pd.id AS buc_type,
    pd.name AS buc_name,
    COALESCE(pivot.agg_preffils, ''::text) AS case_agg_search,
    to_tsvector((((((((((rc.id::text || ' '::text) || COALESCE(pivot.agg_preffils, ''::text)) || ' '::text) || rc.status::text) || ' '::text) || pd.id::text) || ' '::text) || pd.name::text) || ' '::text) || rc.international_id::text) AS tsvector
   FROM rina.rina_case rc
     JOIN rina.process_def_version pdv ON rc.fk_proc_def_version_sid = pdv.sid
     JOIN rina.process_def pd ON pdv.fk_proc_def_sid = pd.sid
     LEFT JOIN ( SELECT cp.fk_case_sid,
            string_agg(cp.value, ' '::text) AS agg_preffils
           FROM rina.case_prefill cp
          WHERE cp.prefill_group::text = 'SEARCH_METADATA'::text
          GROUP BY cp.fk_case_sid) pivot ON rc.sid = pivot.fk_case_sid;
```

2.3.6 View v_iam_user_search

| Attribute | Value |
| --- | --- |
| Name | v_iam_user_search |
| Type | view |
| Comment | The view responsible for allowing the iam user search to work using specific keywords indexed and added here, using Postgress TsVector search functionality. |

```sql
SELECT user_sid,
    username,
    first_name,
    last_name,
    middle_names,
    email,
    phone_number,
    to_tsvector((((((((((((user_sid || ' '::text) || username::text) || ' '::text) || first_name::text) || ' '::text) || last_name::text) || ' '::text) || middle_names::text) || ' '::text) || email::text) || ' '::text) || phone_number::text) AS tsvector
   FROM ( SELECT u.sid AS user_sid,
            COALESCE(u.username, ''::character varying) AS username,
            COALESCE(u.first_name, ''::character varying) AS first_name,
            COALESCE(u.last_name, ''::character varying) AS last_name,
            COALESCE(u.middle_names, ''::character varying) AS middle_names,
            COALESCE(u.email, ''::character varying) AS email,
            COALESCE(u.phone_number, ''::character varying) AS phone_number
           FROM rina.iam_user u) result;
```

2.3.7 Materialized View v_org_search_mat

| Attribute | Value |
| --- | --- |
| Name | v_org_search_mat |
| Type | materialized view |
| Comment |  |

```sql
SELECT sid,
    digit_id,
    org_id_code,
    org_id,
    org_name,
    acronym,
    ap_id,
    ap_name,
    to_tsvector((((((((((((((sid || ' '::text) || digit_id) || ' '::text) || org_id_code) || ' '::text) || org_id::text) || ' '::text) || org_name::text) || ' '::text) || acronym::text) || ' '::text) || ap_id::text) || ' '::text) || ap_name::text) AS tsvector
   FROM ( SELECT o.sid,
            ( SELECT regexp_replace(COALESCE(o.id, ''::character varying)::text, '[^0-9]+'::text, ''::text, 'g'::text) AS digit_id) AS digit_id,
            ( SELECT regexp_replace(COALESCE(o.id, ''::character varying)::text, '[^0-9A-Za-z]'::text, ''::text) AS org_id_code) AS org_id_code,
            o.id AS org_id,
            COALESCE(o.name, ''::character varying) AS org_name,
            COALESCE(o.acronym, ''::character varying) AS acronym,
            COALESCE(o.ap_id, ''::character varying) AS ap_id,
            COALESCE(o.ap_name, ''::character varying) AS ap_name
           FROM rina.organisation o) result;
```

2.3.8 View v_organisation_search

| Attribute | Value |
| --- | --- |
| Name | v_organisation_search |
| Type | view |
| Comment | The view responsible for allowing the organisation search to work using specific keywords indexed and added here, using Postgress TsVector search functionality. |

```sql
SELECT sid,
    digit_id,
    org_id_code,
    org_id,
    org_name,
    acronym,
    ap_id,
    ap_name,
    to_tsvector((((((((((((((sid || ' '::text) || digit_id) || ' '::text) || org_id_code) || ' '::text) || org_id::text) || ' '::text) || org_name::text) || ' '::text) || acronym::text) || ' '::text) || ap_id::text) || ' '::text) || ap_name::text) AS tsvector
   FROM ( SELECT o.sid,
            ( SELECT regexp_replace(COALESCE(o.id, ''::character varying)::text, '[^0-9]+'::text, ''::text, 'g'::text) AS digit_id) AS digit_id,
            ( SELECT regexp_replace(COALESCE(o.id, ''::character varying)::text, '[^0-9A-Za-z]'::text, ''::text) AS org_id_code) AS org_id_code,
            o.id AS org_id,
            COALESCE(o.name, ''::character varying) AS org_name,
            COALESCE(o.acronym, ''::character varying) AS acronym,
            COALESCE(o.ap_id, ''::character varying) AS ap_id,
            COALESCE(o.ap_name, ''::character varying) AS ap_name
           FROM rina.organisation o) result;
```

2.3.9 View v_subdocuments_search

| Attribute | Value |
| --- | --- |
| Name | v_subdocuments_search |
| Type | view |
| Comment | The view responsible for allowing the subdocuments search to work using specific keywords indexed and added here, using Postgress TsVector search functionality. |

```sql
SELECT case_sid,
    subdoc_sid,
    field_1,
    field_2,
    field_3,
    field_4,
    to_tsvector((((((((((case_sid || ' '::text) || subdoc_sid) || ' '::text) || field_1) || ' '::text) || field_2) || ' '::text) || field_3) || ' '::text) || field_4) AS tsvector
   FROM ( SELECT pivot.fk_subdoc_sid AS subdoc_sid,
            COALESCE(pivot.field_1, ''::text) AS field_1,
            COALESCE(pivot.field_2, ''::text) AS field_2,
            COALESCE(pivot.field_3, ''::text) AS field_3,
            COALESCE(pivot.field_4, ''::text) AS field_4,
            rc.sid AS case_sid
           FROM rina.crosstab('select sp.fk_subdoc_sid, sp.key, sp.value 
			  from rina.subdocument_prefill sp
			  where sp.prefill_group=''SEARCH_METADATA'' ORDER BY 1,2'::text) pivot(fk_subdoc_sid bigint, field_1 text, field_2 text, field_3 text, field_4 text)
             JOIN rina.subdocument sd ON sd.sid = pivot.fk_subdoc_sid
             JOIN rina.rina_case rc ON rc.sid = sd.fk_case_sid) result;
```

### 2.4 Functions

| Name | Arguments | Return Type | Description |
| --- | --- | --- | --- |
| connectby | text, text, text, text, integer | SETOF record |  |
| connectby | text, text, text, text, integer, text | SETOF record |  |
| connectby | text, text, text, text, text, integer | SETOF record |  |
| connectby | text, text, text, text, text, integer, text | SETOF record |  |
| crosstab | text | SETOF record |  |
| crosstab | text, integer | SETOF record |  |
| crosstab | text, text | SETOF record |  |
| crosstab2 | text | SETOF rina.tablefunc_crosstab_2 |  |
| crosstab3 | text | SETOF rina.tablefunc_crosstab_3 |  |
| crosstab4 | text | SETOF rina.tablefunc_crosstab_4 |  |
| normal_rand | integer, double precision, double precision | SETOF double precision |  |
| refreshcasesearchmview |  | void |  |
| refreshorgsearchmview |  | void |  |

### 2.5 Sequences

Sequences below were identified from the `nextval(...)` default expressions of the surrogate `SID` columns documented in section 2.2, since the DBMind extraction did not capture sequences as standalone catalog objects (unlike Functions, section 2.4). As a result, generation attributes (Increment, Min Value, Max Value, Start Value, Cache Size) could not be populated and should be retrieved with a direct query against `pg_catalog.pg_sequences` on schema `rina`.

| Code | Schema | Data Type | Owned By | Comment |
| --- | --- | --- | --- | --- |
| action_seq | rina | bigint | action.sid | Not available (not extracted from pg_sequences by DBMind) |
| activity_seq | rina | bigint | activity.sid | Not available (not extracted from pg_sequences by DBMind) |
| admin_notification_type_seq | rina | bigint | admin_notification_type.sid | Not available (not extracted from pg_sequences by DBMind) |
| archiving_volume_seq | rina | bigint | archiving_volume.sid | Not available (not extracted from pg_sequences by DBMind) |
| assigned_buc_seq | rina | bigint | assigned_buc.sid | Not available (not extracted from pg_sequences by DBMind) |
| assignment_policy_rule_seq | rina | bigint | assignment_policy_rule.sid | Not available (not extracted from pg_sequences by DBMind) |
| assignment_policy_seq | rina | bigint | assignment_policy.sid | Not available (not extracted from pg_sequences by DBMind) |
| assignment_policy_target_seq | rina | bigint | assignment_policy_target.sid | Not available (not extracted from pg_sequences by DBMind) |
| assignment_request_seq | rina | bigint | assignment_request.sid | Not available (not extracted from pg_sequences by DBMind) |
| assignment_seq | rina | bigint | assignment.sid | Not available (not extracted from pg_sequences by DBMind) |
| audit_event_seq | rina | bigint | audit_event.sid | Not available (not extracted from pg_sequences by DBMind) |
| audit_object_seq | rina | bigint | audit_object.sid | Not available (not extracted from pg_sequences by DBMind) |
| audit_participant_seq | rina | bigint | audit_participant.sid | Not available (not extracted from pg_sequences by DBMind) |
| business_exception_seq | rina | bigint | business_exception.sid | Not available (not extracted from pg_sequences by DBMind) |
| business_exception_settings_seq | rina | bigint | business_exception_settings.sid | Not available (not extracted from pg_sequences by DBMind) |
| business_key_seq | rina | bigint | business_key.sid | Not available (not extracted from pg_sequences by DBMind) |
| case_attachment_seq | rina | bigint | case_attachment.sid | Not available (not extracted from pg_sequences by DBMind) |
| case_comment_seq | rina | bigint | case_comment.sid | Not available (not extracted from pg_sequences by DBMind) |
| case_participant_seq | rina | bigint | case_participant.sid | Not available (not extracted from pg_sequences by DBMind) |
| case_prefill_seq | rina | bigint | case_prefill.sid | Not available (not extracted from pg_sequences by DBMind) |
| case_property_seq | rina | bigint | case_property.sid | Not available (not extracted from pg_sequences by DBMind) |
| case_seq | rina | bigint | rina_case.sid | Not available (not extracted from pg_sequences by DBMind) |
| check_bucket_seq | rina | bigint | check_bucket.sid | Not available (not extracted from pg_sequences by DBMind) |
| check_definition_seq | rina | bigint | check_definition.sid | Not available (not extracted from pg_sequences by DBMind) |
| check_instance_seq | rina | bigint | check_instance.sid | Not available (not extracted from pg_sequences by DBMind) |
| cluster_node_seq | rina | bigint | cluster_node.sid | Not available (not extracted from pg_sequences by DBMind) |
| conv_participant_seq | rina | bigint | conv_participant.sid | Not available (not extracted from pg_sequences by DBMind) |
| doc_attachment_seq | rina | bigint | document_attachment.sid | Not available (not extracted from pg_sequences by DBMind) |
| doc_comment_seq | rina | bigint | document_comment.sid | Not available (not extracted from pg_sequences by DBMind) |
| doc_conversation_seq | rina | bigint | document_conversation.sid | Not available (not extracted from pg_sequences by DBMind) |
| doc_thumbnail_seq | rina | bigint | document_thumbnail.sid | Not available (not extracted from pg_sequences by DBMind) |
| doc_type_seq | rina | bigint | document_type.sid | Not available (not extracted from pg_sequences by DBMind) |
| doc_type_version_seq | rina | bigint | document_type_version.sid | Not available (not extracted from pg_sequences by DBMind) |
| document_bversion_seq | rina | bigint | document_bversion.sid | Not available (not extracted from pg_sequences by DBMind) |
| document_content_seq | rina | bigint | document_content.sid | Not available (not extracted from pg_sequences by DBMind) |
| document_history_seq | rina | bigint | document_history.sid | Not available (not extracted from pg_sequences by DBMind) |
| document_seq | rina | bigint | document.sid | Not available (not extracted from pg_sequences by DBMind) |
| field_chooser_seq | rina | bigint | field_chooser.sid | Not available (not extracted from pg_sequences by DBMind) |
| field_seq | rina | bigint | field.sid | Not available (not extracted from pg_sequences by DBMind) |
| global_param_group_seq | rina | bigint | global_param_group.sid | Not available (not extracted from pg_sequences by DBMind) |
| global_param_seq | rina | bigint | global_param.sid | Not available (not extracted from pg_sequences by DBMind) |
| iam_group_seq | rina | bigint | iam_group.sid | Not available (not extracted from pg_sequences by DBMind) |
| iam_origin_seq | rina | bigint | iam_origin.sid | Not available (not extracted from pg_sequences by DBMind) |
| iam_user_group_seq | rina | bigint | iam_user_group.sid | Not available (not extracted from pg_sequences by DBMind) |
| iam_user_seq | rina | bigint | iam_user.sid | Not available (not extracted from pg_sequences by DBMind) |
| nie_event_seq | rina | bigint | nie_event.sid | Not available (not extracted from pg_sequences by DBMind) |
| nie_listener_seq | rina | bigint | nie_listener.sid | Not available (not extracted from pg_sequences by DBMind) |
| nie_subscriber_seq | rina | bigint | nie_subscriber.sid | Not available (not extracted from pg_sequences by DBMind) |
| nie_subscription_seq | rina | bigint | nie_subscription.sid | Not available (not extracted from pg_sequences by DBMind) |
| notification_alarm_seq | rina | bigint | notification_alarm.sid | Not available (not extracted from pg_sequences by DBMind) |
| notification_seq | rina | bigint | notification.sid | Not available (not extracted from pg_sequences by DBMind) |
| org_contact_method_seq | rina | bigint | org_contact_method.sid | Not available (not extracted from pg_sequences by DBMind) |
| organisation_seq | rina | bigint | organisation.sid | Not available (not extracted from pg_sequences by DBMind) |
| pending_message_seq | rina | bigint | pending_attachment.sid, pending_message.sid | Not available (not extracted from pg_sequences by DBMind) |
| pending_signature_seq | rina | bigint | pending_signature.sid | Not available (not extracted from pg_sequences by DBMind) |
| pending_status_seq | rina | bigint | pending_status.sid | Not available (not extracted from pg_sequences by DBMind) |
| policy_seq | rina | bigint | policy.sid | Not available (not extracted from pg_sequences by DBMind) |
| process_def_seq | rina | bigint | process_def.sid | Not available (not extracted from pg_sequences by DBMind) |
| process_def_version_seq | rina | bigint | process_def_version.sid | Not available (not extracted from pg_sequences by DBMind) |
| resource_seq | rina | bigint | resource.sid | Not available (not extracted from pg_sequences by DBMind) |
| role_seq | rina | bigint | role.sid | Not available (not extracted from pg_sequences by DBMind) |
| rule_country_seq | rina | bigint | rule_country.sid | Not available (not extracted from pg_sequences by DBMind) |
| sector_seq | rina | bigint | sector.sid | Not available (not extracted from pg_sequences by DBMind) |
| signature_seq | rina | bigint | signature.sid | Not available (not extracted from pg_sequences by DBMind) |
| subdoc_attachment_seq | rina | bigint | subdocument_attachment.sid | Not available (not extracted from pg_sequences by DBMind) |
| subdoc_prefill_seq | rina | bigint | subdocument_prefill.sid | Not available (not extracted from pg_sequences by DBMind) |
| subdocument_bversion_seq | rina | bigint | subdocument_bversion.sid | Not available (not extracted from pg_sequences by DBMind) |
| subdocument_content_seq | rina | bigint | subdocument_content.sid | Not available (not extracted from pg_sequences by DBMind) |
| subdocument_seq | rina | bigint | subdocument.sid, subdocument_history.sid | Confirmed via direct query on pg_attrdef (2026-07-27): subdocument_history.sid also defaults to nextval('subdocument_seq'::regclass) |
| supported_language_seq | rina | bigint | supported_language.sid | Not available (not extracted from pg_sequences by DBMind) |
| tenant_param_group_seq | rina | bigint | tenant_param_group.sid | Not available (not extracted from pg_sequences by DBMind) |
| tenant_param_seq | rina | bigint | tenant_param.sid | Not available (not extracted from pg_sequences by DBMind) |
| tenant_seq | rina | bigint | tenant.sid | Not available (not extracted from pg_sequences by DBMind) |
| translation_seq | rina | bigint | translation.sid | Not available (not extracted from pg_sequences by DBMind) |
| transposition_seq | rina | bigint | transposition.sid | Not available (not extracted from pg_sequences by DBMind) |
| user_message_response_seq | rina | bigint | user_message_response.sid | Not available (not extracted from pg_sequences by DBMind) |
| user_msg_seq | rina | bigint | user_message.sid | Not available (not extracted from pg_sequences by DBMind) |
| user_profile_seq | rina | bigint | user_profile.sid | Not available (not extracted from pg_sequences by DBMind) |
| vocabulary_seq | rina | bigint | vocabulary.sid | Not available (not extracted from pg_sequences by DBMind) |
| vocabulary_type_seq | rina | bigint | vocabulary_type.sid | Not available (not extracted from pg_sequences by DBMind) |

Verification performed on 2026-07-27 against `pg_attrdef` on schema `rina` for the tables `action_tag`, `search_definition` and `subdocument_history`, whose `SID` column showed no `Default Value` in section 2.2. The query returned a single row: `subdocument_history.sid` defaults to `nextval('subdocument_seq'::regclass)`, confirming it shares the sequence with `subdocument`. No default expression was returned for `action_tag.sid` or `search_definition.sid`, confirming that in the JINA2026v2 database these two columns are genuinely not backed by a sequence-based column default (unlike their counterparts in the EESSI rev02 reference model), consistent with the 80 sequences documented above.
