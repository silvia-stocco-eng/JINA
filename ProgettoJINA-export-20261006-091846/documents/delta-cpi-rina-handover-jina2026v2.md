---
unique-name: delta-cpi-rina-handover-jina2026v2
display-name: Delta_CPI_RINA_handover_JINA2026v2
category: GENERAL_DRAFT
description: Delta/gap-analysis report between swagger.json (EESSI RINA REST API Interface CPI) and the reference document EESSI - RINA - Case Processing Interface (CPI) - rev03. Report only, not an updated CPI document.
---

# Delta CPI RINA – Handover JINA2026v2

## Document Control

| Field | Value |
| --- | --- |
| Document Name | Delta_CPI_RINA_handover_JINA2026v2 |
| Purpose | Delta report between the `swagger.json` REST API definition and the reference document "EESSI - RINA - Case Processing Interface (CPI) - rev03" |
| Reference source #1 | DocMind document `eessi-rina-case-processing-interface-cpi-rev03` (id 345) |
| Reference source #2 | `swagger.json` (OpenAPI/Swagger 2.0), title "EESSI RINA REST API Interface (CPI)", provided by user, 146 paths / 184 operations |
| Status | DRAFT |
| Type | Delta / gap-analysis report only — **not** the updated CPI document |
| Generated On | 2026-07-23 |

## 1. Methodology

1. `swagger.json` was parsed to extract all path templates and HTTP operations (146 paths, 184 operations across 33 controller tags).
2. The DocMind document "EESSI - RINA - Case Processing Interface (CPI) - rev03" was retrieved in full and scanned for every explicit REST endpoint mention (URL path + HTTP method), found in:
   - the main body (Authentication, CAS, APListener sections), and
   - **ANNEX – "Differences of CPI Implementation between RINA 5.x (EESSI 2019) and 6.x (EESSI 2020)"** (Tables 3 to 18), which is the only part of rev03 listing concrete endpoints, grouped per controller.
3. Each endpoint explicitly named in rev03 was normalized (path parameters `<x>`/`{x}` treated as equivalent) and matched against the swagger operations by HTTP method + path.
4. Any swagger operation with no corresponding explicit mention in rev03 was classified as "not covered by rev03".

## 2. Important limitation (must be read before using this report)

**rev03 is a Solution/Application Architecture document, not the exhaustive API reference.** Section 7 of rev03 states explicitly:

> "The reference documentation is located in a separate document ('EESSI - RINA - Case Processing Interface (CPI) - Reference'), which is generated from the code and contains the exact description of the REST calls for each resource."

That separate, code-generated reference document was **not provided** and was **not used** in this analysis (per instructions, only rev03 and `swagger.json` were used — nothing was assumed or invented beyond their content). Consequently:

- The ~30 endpoints matched below are the **only ones explicitly named in rev03** (mainly the RINA 5.x→6.x annex, plus a handful of examples in the main text).
- The remaining **154 of 184 swagger operations** are simply **outside the scope of what rev03 documents** (rev03 never claimed to describe them) — they should **not** be read as "new/undocumented" APIs in an absolute sense, only as "not confirmed/covered by rev03".
- 3 endpoint mentions in rev03 were not found in swagger.json; some due to legacy pre-6.x naming superseded by newer paths (already reconciled below), one is a genuine open point requiring manual confirmation against the original (garbled PDF-to-text conversion affected some multi-row tables in the annex).

## 3. Endpoints confirmed present in both rev03 and swagger.json (30)

| HTTP | Path (swagger) | rev03 source / method name |
| --- | --- | --- |
| POST | /user-auth | authenticateUser – Authentication Controller (Table 16) |
| POST | /message/received | onReceivedMessage – ApListener Controller (Table 15) |
| POST | /message/signature-update | onMessageSignatureUpdate – ApListener Controller (Table 15) |
| POST | /message/status-update | onMessageStatusUpdate – ApListener Controller (Table 15) |
| GET | /ApplicationProfile | example, §3.5 CORS Filtering |
| GET | /Cases/{caseId}/Documents/{id} | example, §3.8 HTTP Error codes |
| GET | /Cases/{caseId}/Documents/{documentId}/Details | retrieveDocumentDetails – Document Controller (Table 3) |
| PUT | /Cases/{caseId}/Actions/{actionId}/Document | submitDocument – Document Controller (Table 3) |
| PUT | /Cases/{caseId}/Documents/{documentId}/Subdocuments/{subdocumentId} | updateSubdocument – Document Controller (Table 3) |
| GET | /Cases/{caseId}/Documents/{documentId}/Batch | exportSubdocuments – Document Controller (Table 3) |
| GET | /Cases/{id} | getCase – Cases Controller (Table 4) |
| GET | /Cases/ByBusinessId/{businessId} | getCaseByBusinessId – Cases Controller (Table 4) |
| GET | /Cases/ByInternationalId/{internationalId} | getCaseByInternationalId – Cases Controller (Table 4) |
| PUT | /Cases/{caseId}/Assignment | assignCase – Cases Controller (Table 4) |
| POST | /Cases/{caseId}/Assignment/Actions | executeCaseAssignmentAction – Cases Controller (Table 4) |
| GET | /Cases | searchCases – Cases Controller (Table 4) |
| GET | /Activities/AllActivities | getActivitiesForUser – Activity Controller (Table 5) |
| POST | /Activities/Activity | createActivity – Activity Controller (Table 5) |
| POST | /ApplicationProfile/IAMSettings/LdapSynchronization/{institutionId} | synchronizeLdap – ApplicationProfile Controller (Table 6) |
| DELETE | /Identity/Group/{groupId} | deleteGroup – Groups Controller (Table 7) |
| POST | /Keystores/UpdateBusinessAliasPassword | updateBusinessAliasPassword – Keystore Controller (Table 8) |
| GET | /Notifications | retrieveNotificationsDetails – Notifications Controller (Table 10) |
| GET | /Resources | getResources – ResourceAdmin Controller (Table 11) |
| PUT | /Resources/{resourceId} | updateResources – ResourceAdmin Controller (Table 11) |
| PUT | /Identity/User/{userId} | updateUser – Users Controller (Table 14) |
| POST | /Identity/Registration | registerUser – Users Controller (Table 14) |
| GET | /organisations | searchOrganisations – Organisation Controller (Table 17) |
| GET | /organisations/searchByParams | searchOrganisationsByParam – Organisation Controller (Table 17) |
| GET | /organisations/{id} | getOrganisationByIdAndCountry – Organisation Controller (Table 17) |
| GET | /Forms/Translations, /Forms/Metadata | getTranslations / getSedMetadata – PortalForms Controller (Table 18) |

## 4. Endpoints mentioned in rev03 but NOT found (as such) in swagger.json (3 open points)

| HTTP | Path mentioned in rev03 | Note |
| --- | --- | --- |
| POST | /received | Pre-6.x legacy name mentioned only in the main text before the annex; superseded by `/message/received`, which IS present in swagger. Not a real gap. |
| POST | /signature-update | Pre-6.x legacy name; superseded by `/message/signature-update`, present in swagger. Not a real gap. |
| POST | /status-update | Pre-6.x legacy name; superseded by `/message/status-update`, present in swagger. Not a real gap. |

**Open point requiring manual verification:** the annex table row for `updateActivity` (Table 5) lists the HTTP method as "POST" against path `/Activities/Activity/<id>`, but swagger.json shows this path only with **PUT** (`updateActivityUsingPUT`) and **DELETE** (`deleteActivityUsingDELETE`), no POST. The rev03 table cells appeared merged/garbled in the PDF-to-text conversion at this point, so this discrepancy could not be reliably resolved from the text alone — recommend checking the original rev03 PDF table directly.

## 5. Swagger operations NOT covered by rev03 (154 of 184) — grouped by controller

*(These are not "missing documentation" per se — rev03 never intended to describe them; the exhaustive reference is the separate, code-generated document mentioned in rev03 §7, which was not supplied for this analysis.)*

| Controller (swagger tag) | # ops not covered |
| --- | --- |
| application-profile-controller | 21 |
| document-controller | 11 |
| attachment-controller | 12 |
| configurations-controller | 10 |
| keystore-controller | 10 |
| assignment-policies-controller | 8 |
| business-exceptions-controller | 8 |
| cases-controller | 8 |
| users-controller | 7 |
| tenant-controller | 5 |
| comment-controller | 4 |
| notifications-controller | 4 |
| search-definitions-controller | 4 |
| synchronizations-controller | 4 |
| alarms-controller | 3 |
| check-buckets-controller | 3 |
| entity-controller | 3 |
| process-definitions-controller | 3 |
| activity-controller | 2 |
| admin-notification-controller | 2 |
| audit-controller | 2 |
| check-definitions-controller | 2 |
| groups-controller | 2 |
| process-definition-fields-controller | 2 |
| resource-admin-controller | 2 |
| technical-log-controller | 2 |
| user-profile-controller | 2 |
| application-resources-controller | 1 |
| login-controller | 1 |
| sector-controller | 1 |
| upload-files-controller | 1 |
| vocabularies-controller | 1 |

Full per-endpoint listing is available on request (extracted programmatically from `swagger.json`, one row per HTTP method + path + operationId, e.g. `GET /Cases/{caseId}/Alarms [getAlarmsUsingGET]`).

## 6. Summary

| Metric | Count |
| --- | --- |
| Total swagger operations | 184 |
| Total swagger paths | 146 |
| Explicitly confirmed by rev03 | 30 |
| Mentioned in rev03, not found in swagger (legacy, reconciled) | 3 |
| Open point needing manual PDF check | 1 (updateActivity method mismatch) |
| Not covered by rev03 scope | 154 |

## 7. Recommendation for the next step (updated CPI document — not produced in this report)

Per instructions, this report stops at the delta analysis. To produce the updated CPI document, the recommended next step would be to obtain and incorporate the separate code-generated "EESSI - RINA - Case Processing Interface (CPI) - Reference" document (cited in rev03 §7), since it — not rev03 — is the authoritative 1:1 API reference; without it, any "updated CPI document" built only from rev03 + swagger.json would necessarily leave the 154 non-covered operations without functional/business context (only technical signatures from swagger).
