---
unique-name: rina2020bucengineprocessesd2morning
display-name: RINA 2020 BUC engine  processes D2morning
category: GENERAL
tags: ec
---

<!-- image -->

## EESSI RINA training for developers

RINA 2020 BUC engine &amp; processes Day 2 - Morning March 2021

## RINA 2020 BUC engine &amp; processes

<!-- image -->

<!-- image -->

## Table of Content

- Chap1: Introduction (key concepts around BUCs and BUC Engine)
- Chap2: BUC Engine (from BonitaBPM to XML/JAVA technology)
- Chap3: XML structure of BUC processes (intro + afternoon session)
- Chap4: Full example (afternoon session)

<!-- image -->

## Foreword

## Session focused on understanding:

➢ BUC Engine / Process concepts

➢ BUC Process XML structure

Main goal is to Understand the XML structure of a BUC process

BUC Engine technical details of JAVA implementation discussed in following training session

<!-- image -->

(from developer's viewpoint)

## Chapter 1 - Introduction

- Place of BUC Engine in RINA (reminder)
- Different kinds of BUCs
- Sectorial BUCs, Horizontal BUCs, Administrative BUCs
- More specific features of BUCs
- How to go from BUC requirements to BUC process implementation
- Inputs needed for BUC technical implementation / process
- Notions of Stateless and Stateful validations

<!-- image -->

## BUC Engine in RINA (reminder)

<!-- image -->

RINA = "Reference Implementation of National Application"

Layers: Portal, CPS, BMS, TMS

## Institution's choice between:

- Full use of RINA (RINA full stack)
- Partial use of RINA (integrated with own additional development)
- No use of RINA (own National Application)

## BUC Engine in RINA

- Part of CPS (Case Processing Services): module responsible for managing cases, processing BUCs
- Recently migrated from BonitaSoft BonitaBPM to XML/JAVA technology

<!-- image -->

## Kinds of BUCs - Sectorial, 9 sectors

- AWOD: Accidents at Work and Other Diseases (ex. AW\_BUC\_05)
- FB: Family Benefits (ex. FB\_BUC\_01)
- LA: Legislation Applicable (ex. LA\_BUC\_03)
- P: Pension (ex. P\_BUC\_01)
- R: Recovery (ex. R\_BUC\_01)
- S: Sickness (ex. S\_BUC\_01)
- UB: Unemployment Benefits (ex. UB\_BUC\_04)
- M: Miscellaneous (ex. M\_BUC\_01)
- H: Horizontal (ex. H\_BUC\_01)
- → Sectorial BUCs are defined in specification documents

<!-- image -->

## Kinds of BUCs - Sectorial, example

Example: Pension business case « P\_BUC\_01 »

Case Owner (CO), multiple Counterparties (CPs)

- Scenario

During his life a European citizen worked in UK, Belgium and France.

He is now resident in Spain (retired) and is requesting his pension in Madrid (INSS institution).

- Flow

CO (INSS, Madrid) creates a case P\_BUC\_01.

CO chooses CPs (in UK, BE and FR), fills and sends the starter SED (P2000) with Spanish resident's data. CPs receive P2000.

Together all CO and CPs cases share the same international CaseId and exchange additional SEDs (P6000… P7000) to solve the case.

<!-- image -->

## Kinds of BUCs - Horizontal

- May be used as main process (see sectorial horizontal BUCs, ex. H\_BUC\_01)
- May be used as subprocess (ex. H\_BUC\_01\_sub):
- Cannot be used alone, must be integrated in a main process
- Often: same functionalities as main process
- There are exceptions:

## Differences?

- admins may differ (ex. H\_BUC\_01 main process has Reminder, subprocess has not)
- flows may differ (ex. 3 main processes: H\_BUC\_02a, H\_BUC\_02b, H\_BUC\_02c, but only 1 subprocess H\_BUC\_02\_sub)
- → Also defined in specification documents

<!-- image -->

## Kinds of BUCs - Administrative(case / SED level)

| Document name                  | Document type   | Level   | Specification document   |
|--------------------------------|-----------------|---------|--------------------------|
| Close case                     | X001            | Case    | AD_BUC_01                |
| Request for Reopen             | X002            | Case    | AD_BUC_02                |
| Individual decision for Reopen | X003            | Case    | AD_BUC_02                |
| Final Decision for Reopen      | X004            | Case    | AD_BUC_02                |
| Add Participants               | X005            | Case    | AD_BUC_03                |
| Remove Participants            | X006            | Case    | AD_BUC_04                |
| Forward case                   | X007            | Case    | AD_BUC_05                |
| Reminder                       | X009            | Case    | AD_BUC_07                |
| Reply to Reminder              | X010            | Case    | AD_BUC_07                |
| Business exception             | X050            | Case    | AD_BUC_11                |
| Change participants            | X100            | Case    | AD_BUC_12                |
| Update                         |                 | SED     | AD_BUC_10                |
| Invalidate                     | X008            | SED     | AD_BUC_06                |
| Reject                         | X011            | SED     | AD_BUC_09                |
| Clarify                        | X012            | SED     | AD_BUC_08                |
| Reply To Clarify               | X013            | SED     | AD_BUC_08                |

<!-- image -->

## BUC more specific features

- Bilateral / Multilateral

BUC with one or more counterparties

Ex: bilateral: R\_BUC\_03, multilateral: P\_BUC\_01

- Single-starter / Multi-starter

BUC with one or more possible starter SEDs

Ex: single-starter: P\_BUC\_01, multi-starter: UB\_BUC\_01

- Non-Batch / Batch

BUC without / with one or more bulk SEDs (containing subdocuments)

Ex: non-batch: P\_BUC\_01, batch: UB\_BUC\_04

<!-- image -->

## BUCs - Summary view (reminder)

<!-- image -->

Core Business Process-Instantiable process handling a specificbusiness scenario

Sub Process-Reusable process part that is used by a core process or another subprocess

<!-- image -->

## Input for RINA implementation

- EESSI model artefacts (used by all institutions):
- Process definitions (English text and BPM diagrams)
- SBDH and SED xsd (constraints on messages containing SEDs)
- Transaction files xsd (constraints on exchanges)
- Transposition files (description of prefilling of SED field values per BUC)
- In addition: RINA artefacts
- Html forms (used in Portal to render SEDs)
- Json (initial document contents used for default, transposition and NIE prefilling)

<!-- image -->

## Input for BUC flow implementation

In order to be able to build the BUC flow technical implementation (flow of actions), developers need:

- FLOW definition =
- o BUC specification (text and BPM diagrams) elements of attention: BUC description, SEDs included, participants, special requirements, main scenario/branches, restriction of attachments, request/reply pattern between SEDs...
- o Used to build the flow of actions
- SED definitions =
- o Transaction / SED xsd's (structure of SEDs together with constraints on datatype and cardinality)
- o Used to test the content of SEDs in order to decide on business flow, such as invoking of BUC branches

<!-- image -->

## Input to DEV - Note on Transposition files

- Set of rules describing the way SED values are prefilled at SED creation
- End user not obliged to fill same data many times in different SEDs (for example: first name, last name, age, birth place, address…)
- Not part of BUC Engine as such
- Specifications not implemented completely (historically RINA as a demo, specifications came late)
- (Conditions in flow can be based on SED prefilled values)

<!-- image -->

## Stateless vs Stateful validation

Coming to BUC engine…

Developing a technical BUC process implies finding a way to compute and validate

- the next allowed actions at every step of the flow
- in order to respect the requirements (definition of BUC)
- → Notions of

Stateless validation

vs

Stateful validation

<!-- image -->

## Stateless validation (by BMP)

- Managed through BMP (Business Message Protocol) - reminder

Minimum standard that National Applications must follow to produce business messages that can be accepted as valid transactions within the EESSI domain.

Specification defining constraints between key aspects of BUC, SBDH (Standard Business Document Header) and SED

- Technology used = xsd based on XML v1.0

Transaction files, including validation of messages (constraints on datatypes and mandatory fields)

```
Example:
```

P\_BUC\_01-4.2-CaseOwner-Counterparty-Start-P2000-4.2.xsd

P\_BUC\_01-4.2-CaseOwner-Counterparty-New-P7000-4.2.xsd

- BUT not enough to validate messages completely (their order!)

Example: how to enforce that P7000 cannot be sent before P2000 (order) ?

Need of Stateful validation!

<!-- image -->

## Stateful validation (by BUC Engine)

- Stateful validation =

'is this message allowed at this step of the flow?'

- o Case "state" (position in the flow) is used to compute the next allowed actions/messages
- o Stateful services performed by CPS
- o BUC Engine stores information about case "state' (including SED states too)
- o BUC Engine enforces the respect of BUC definition
- Technology used:
- o PAST: BonitaSoft BonitaBPM: state defined by token distribution in the (BPM) flow
- o CURRENT: XML technology: direct description of next actions by language in XML

<!-- image -->

## Chapter 2 - BUC Engine

From PAST engine (BonitaBPM) to CURRENT engine (XML/JAVA)

- PAST = BonitaSoft BonitaBPM process definitions
- CURRENT = XML process definitions

(encoding of Main SEDs, Administrative SEDs, Transitions to next actions)

- Advantages, drawbacks

<!-- image -->

## BUC Engine - Past BonitaBPM technology

Main scenario

<!-- image -->

<!-- image -->

## BUC Engine with BonitaBPM

- Description of process (BPMN diagram) = .proc file
- Compiled deliverable = .bar file
- BUC engine = BonitaBPM software, interprets the .bar file on server (plays flow, manages state, derives next actions)

<!-- image -->

## BUC Engine with BonitaBPM (cont'd)

## Management of sectorial SEDs

- Through Call Activities (BPM subprocesses)

Main call activities: DOCUMENT\_MANAGER: managing SEDs + admins at sending side, DOCUMENT\_READER: managing SEDs + admins at receiving side. ex.

P2000, P6000 are sent within DOCUMENT\_MANAGER and received within DOCUMENT\_READER call activities

## Management of administrative SEDs

- Through Call Activity parameters (of DOCUMENT\_MANAGER and DOCUMENT\_READER)
- ex. Invalidate (X008) on P2000 is defined as a parameter (hasCancel) of the DOCUMENT\_MANAGER call activity
- Through specific Call Activities (Common, Reminder, AddRemoveForward...)

ex. Reminder call activity manages the Reminder (X009) and Reply To Reminder (X010) admin SEDs

<!-- image -->

## BUC Engine with BonitaBPM(cont'd)

- Defining the next allowed actions
- o Through flow &amp; transition links, conditional flows (use of groovy scripts)
- o Through subprocess parameters (ex. hasCancel for invalidate)
- Set of tokens define the internal state, that drive the next actions
- Drawbacks
- State is hardly controllable in BonitaSoft BonitaBPM
- (in the Community edition - free version - no control on tokens)
- ex. a business loop in the process requires coming back to a given state
- → actions hard to instantiate → lack of flexibility
- No correct scalability, average performance

<!-- image -->

## BUC Engine - Current XML technology

<!-- image -->

- Introduced to solve BonitaBPM drawbacks
- BUC Engine written in JAVA
- BUC Engine based on hierarchical rules

(Usage of customization through overridden methods)

- Flexibility
- Performance
- Scalability

<!-- image -->

## BUC Engine based on XML

- Description of process = .xml file
- Compiled deliverable = .jar file
- BUC engine = JAVA, interprets and executes the .jar file on server

<!-- image -->

## BUC Engine based on XML(cont'd)

## Management of sectorial SEDs

- Through documents (tag &lt;document&gt;)
- ex. P2000, P6000

## Management of administrative SEDs

- ·
- ·
- Through documents (tag &lt;document&gt;) ex. X001, X005, X006, X007, X009, X010
- Through document parameters (tag &lt;parameter&gt; associated to documents)
- ex. Reject (hasReject), invalidate (hasCancel), clarify (hasClarify), update (hasMultipleVersions)

<!-- image -->

## BUC Engine based on XML(cont'd)

- Defining / Deriving / Computing the next allowed actions
- o Through document parameters

(tag &lt;parameter&gt; ex. action 'invalidate' allowed after action 'send P2000' is performed)

- o Through trigger handlers

(ex. Action 'create P6000' available after action 'send P2000' is performed)

```
<creationActionTrigger>: trigger to create an action <removeActionTrigger>: trigger to remove an action <suspendActionTrigger>: trigger to suspend an action <reactivateActionTrigger>: trigger to reactivate an action
```

<!-- image -->

- ·

## BUC Engine based on XML(cont'd)

- Next actions controllable through trigger parameters (JAVA, set of parameters could be easily extended)

## · Dummy example

```
<document type="P9000"> <triggers> <createActionTrigger onAction="DOC_SEND" onParentDocumentType="P8000" onResult="SUCCESS" onCondition="XYZ" actionType="DOC_CREATE" documentType="X001" delay="5d"/> </triggers> </document>
```

## Flexibility:

- Extendable (java)
- Controllable flow through custom trigger/action handlers (overriding behaviour of the base action classes)
- Use of conditions

<!-- image -->

## BUC Engine based on XML(cont'd)

- Custom handlers - example in UB\_BUC\_04
- Conditions - example in AW\_BUC\_01a

Implementation details in next training session on BUC Engine

<!-- image -->

## BUC Engine based on XML(cont'd)

- Testing Framework
- Developed to test BUC xml files
- Script example
- Implementation details in next training session on BUC Engine

<!-- image -->

## Chapter (3) - XML structure

- Case and documents
- o Details on Case parameters (isML, removeMeOnly)
- o Details on Document parameters (isStarter, allowsAttachments, isBulk, hasReject, hasClarify, hasCancel, hasParticipantSelection, isML, recreateAfterDeletion…)
- o Details on Trigger Handlers (createActionTrigger, RemoveActionTrigger, SuspendActionTrigger, ReactivateActionTrigger, Custom Action Trigger)
- Dummy example

<!-- image -->

## BUC Process - XML Structure

## Process XML file composed of:

- o Case context = set of case parameters
- o Case body = list of documents
- document parameters
- document triggers
- Examples: pages 11, 12 of RINA - BUC Technical specifications

<!-- image -->

## BUC Process - XML Structure (cont'd)

## Details on Case parameters:

pages 19, 20 of RINA - BUC Technical specifications

## Details on Document parameters:

pages 21 to 28 of RINA - BUC Technical specifications

| isML                | removeMeOnly (for CPs)   |
|---------------------|--------------------------|
| isStarter           | recreateAfterSend        |
| hasCancel           | recreateAfterCancel      |
| hasMultipleVersions | recreateAfterDeletion    |
| hasClarify          | hasParticipantSelection  |
| hasReject           | isML                     |
| isBulk              | canBeSentWithoutBulk     |
| allowsAttachments   |                          |

<!-- image -->

## BUC Process - XML Structure (cont'd)

## Details on trigger handlers:

pages 13 to 18 of RINA - BUC Technical specifications

| createActionTrigger      | suspendActionTrigger     |
|--------------------------|--------------------------|
| removeActionTrigger      | reactivateActionTrigger  |
| (custom Action Trigger ) | (custom Action Trigger ) |

<!-- image -->

## Chapter (4) - Full example

## Pension BUC - P\_BUC\_01

- Initial requirements (BUC specifications)
- Presentation of complete XML solution
- Testing Framework (runs test scripts) - page 67 of BUC Technical implementation

<!-- image -->

## References

- EESSI - System Architecture Overview
- EESSI 2020 - RINA - Architecture Overview
- EESSI 2020 - RINA - Business Use Case Engine Architecture
- EESSI 2020 - RINA - BUC Technical Specifications

<!-- image -->

## Thank you

<!-- image -->

© European Union 1995 - 2021

Unless otherwise noted the reuse of this presentation is authorised under the CC BY 4.0 license. For any use or reproduction of elements that are not owned by the EU, permission may need to be sought directly from the respective right holders.

<!-- image -->