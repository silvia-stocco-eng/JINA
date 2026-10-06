---
unique-name: jinarn11625596notification-caseautomaticallyclosed
display-name: JINA RN 11625596 Notification Case automatically closed cannot be marked as read    V1.1
category: GENERAL
description: The Join Implementation of a National Applications (JINA) is a web-based
tags: eng
---

![A person typing on a computer Description automatically
generated](./immagini/media/image1.jpg){width="8.265917541557306in"\
height="11.739943132108486in"}

![](./immagini/media/image2.emf){width="1.8736111111111111in"\
height="2.4652777777777777in"}

![](./immagini/media/image3.png){width="0.6909722222222222in"\
height="0.2222222222222222in"}

![](./immagini/media/image4.png){width="0.9902777777777778in"\
height="0.22152777777777777in"}

![Immagine che contiene logo Descrizione
generata
automaticamente](./immagini/media/image5.png){width="0.2423611111111111in"\
height="0.2423611111111111in"}

![Immagine che contiene testo Descrizione
generata
automaticamente](./immagini/media/image6.png){width="0.9715277777777778in"\
height="0.2423611111111111in"}

![](./immagini/media/image8.svg){width="1.3221128608923884in"\
height="0.3472758092738408in"}

![Immagine che contiene Carattere, logo, schermata, Elementi grafici Il
contenuto generato dallIA potrebbe non essere
corretto.](./immagini/media/image9.png){width="0.9569444444444445in"\
height="1.086111111111111in"}

**TGC Engineering Ingegneria Informatica**

*RN:11625596-- Notification\
"Case automatically closed" cannot be marked as read​ (Functional\
Analysis)*

**CIG 9623953142**

(CIG 9623953142)

---

Date: 12 Doc.\
Dicembre 2025 Version:\
1.1

---

---

**Document Control Information**

---

**Settings** **Value**

---

**Document Title:** *RN:11625596-- Notification\
"Case automatically closed" cannot be marked as read​\
(Functional Analysis)*

**Project Id:** CIG 9623953142

**Document Authors:** Stocco Silvia

**Project Owner:** Barbara Ingrosso (PO)

**Project Manager:** Milko Anselmi (PM)

**Doc. Version:** 1.1

**Sensitivity:** Reserved

## **Date:** 12 Dicember 2025

**Document Approver(s) and Reviewer(s):**

NOTE: All Approvers are required. Records of each approver must be\
maintained. All Reviewers in the list are considered required unless\
explicitly listed as Optional.

---

**Name** **Role** **Action** **Date**

---

```
                                  *\<Approve /      
                                  Review\>*         

                                  *\<Approve /      
                                  Review\>*         

                                  *\<Approve /      
                                  Review\>*         
```

---

**Document history:**

The Document Author is authorized to make the following types of changes\
to the document without requiring that the document be re-approved:

- Editorial, formatting, and spelling

- Clarification

To request a change to this document, contact the Document Author or\
Owner.

Changes to this document are summarized in the following table in\
reverse chronological order -(latest version first).

---

**Revision** **Date** **Created by** **Short Description of Changes**

---

1.0 12/12/2025 Silvia Stocco Prima stesura

1.1 30/03/2026 Silvia Stocco Aggiornati gli stati di notifica\
nell'AS-IS

---

**Configuration Management: Document Location**

The latest version of this controlled document is stored in: *link*

Sommario

\[1. Introduction [- 3 -](#introduction)\](#introduction)

\[1.1 General Overview [- 3 -](#general-overview)\](#general-overview)

\[1.2 Scope [- 3 -](#scope)\](#scope)

\[1.3 Glossary of Terms [- 3 -](#glossary-of-terms)\](#glossary-of-terms)

\[1.4 CR Overview [- 3 -](#cr-overview)\](#cr-overview)

\[2. titolo- AS-IS [- 4 -](#titolo--as-is)\](#titolo--as-is)

\[3. TITOLO-TO BE [- 5 -](#titolo-to-be)\](#titolo-to-be)

\[3.1 RIEPILOGO DELLE MODIFICHE [- 5\
-](#riepilogo-delle-modifiche)\](#riepilogo-delle-modifiche)

\[4. casi d'uso [- 6 -](#casi-duso)\](#casi-duso)

\[5. References and Related Documents [- 7\
-](#references-and-related-documents)\](#references-and-related-documents)

# Introduction

## General Overview

The Join Implementation of a National Applications (JINA) is a web-based\
software application for the electronic management and exchange of\
social security cases across competent institutions of the participant\
countries. Currently managed by *Jump-RINA* to ensure the evolution of\
the EESSI project (Electronic Exchange of Social Security Information).

## Scope

Il presente documento ha natura dinamica ed è soggetto ad aggiornamenti\
e approfondimenti durante tutto il ciclo di vita del progetto. I\
contenuti riportati nel documento descrivono il comportamento

All'interno di questo documento è presente la descrizione del\
comportamento attuale (AS-IS) e le indicazioni funzionali sul\
comportamento futuro (TO-BE) secondo quanto richiesto dalla\
**RN:11625596**.

## Glossary of Terms

---

**Term/Acronym** **Definition**

---

RINA Reference Implementation of National Applications

CDM Common Data Model

CR Change request

SBDH Standard Business Document Header

SED Structure Electronic Document

BUC Business Use Case

CO Case owner

## CP Counterparty

## CR Overview

**CR number** : RN11625596

**Title**: Notification Case automatically closed cannot be marked as\
read

**Slot:** 3

**Elementi impattati**: menù notification

# titolo- AS-IS

Attualmente in JINA per determinate notifiche come ad esempio "Case\
automatically closed" o "Case SEDs Automatically Sent to New\
Participant" quando si prova a marcare la notifica come letta\
restituisce l'errore in figura:

![Immagine che contiene testo, software, numero, Carattere Il contenuto
generato dallIA potrebbe non essere
corretto.](./immagini/media/image10.png){width="5.772222222222222in"\
height="1.5972222222222223in"}

L'errore si verifica sia quando si clicca sulla freccia

![](./immagini/media/image11.png){width="0.3021259842519685in"\
height="0.3021259842519685in"} per espandere il dettaglio della\
notifica, che quando nelle action si clicca su Marks as Read

![Immagine che contiene testo, schermata, Carattere, Blu elettrico Il
contenuto generato dallIA potrebbe non essere
corretto.](./immagini/media/image12.png){width="1.906515748031496in"\
height="1.166829615048119in"}

Di seguito si riportano gli stati che si possono trovare nelle notifiche\
di JINA portal e che sono stati verificati con l'indicazione della\
corretta funzionalità per marcare la notifica come letta:

---

STATO TYPE SEVERITY FUNZIONA?

---

A new Case CASE_ARRIVED("case_arrived") WARNING SI\
Arrived

A new SED DOCUMENT_ARRIVED("document_arrived") WARNING SI\
Arrived

An Updated SED UPDATE_ARRIVED("update_arrived") WARNING SI\
Arrived

Case Assigned CASE_ASSIGNED("case_assigned") INFORMATION SI

Case CASE_AUTOMATICALLY_CLOSED("case_automatically_closed") INFORMATION NO\
Automatically\
closed

Case SEDs SED_AUTOMATICALLY_SENT("sed_automatically_sent") INFORMATION NO\
Automatically\
Sent to New\
Participant

SED Delivery DOCUMENT_DELIVERED("document_delivered") INFORMATION SI

SED Failed to DELIVERY_ERROR("delivery_error") ERROR SI\
be Delivered

## Your Alarm ALARM_EXPIRED("alarm_expired") WARNING NO\
Expired

I Type ASSIGNMENT_REQUEST ("assignment_request"),\
APPROVAL_REQUIRED("approval_required") trovo la notifica sul DB ma non\
sul portal

I type seguenti sono notifiche del portale admin:

- RECEIVING_A_SED_AFTER_CASE_REMOVED_BY_RECEIVING_AX006SED("receivingASedAfterCaseRemovedByReceivingAX006Sed"),

- RECEIVING_A_SED_IN_CASE_IN_WRONG_SEQUENCE("receivedASedInCaseInWrongSequence"),

- RECEIVING_A_SED_FOR_A_MISSING_SETID_SED_UPDATE_FOR_NON_EXISTING_SED("receivingASedForAMissingSetldSedUpdateForANonExistingSed"),

- DUPLICATE_MESSAGE("duplicate_message"),

- DUPLICATE_UPDATE("duplicate_update"),

- CASE_UNASSIGNED("case_unassigned"),

- RECEIVING_A_SED_AFTER_CASE_FORWARDED_ANOTHER_PARTICIPANT("receivingASedAfterCaseForwardedAnotherParticipant"),

- RECEIVING_A_SED_WHEN_CASE_IN_GLOBAL_CLOSED_STATUS("receivedASedWhenCaseInGlobalClosedStatus").

I type seguenti non sono stati trovati sul DB e non è stato possibile\
verificare se sono notifiche visualizzabili in JINA portal:

- ACCEPT_ASSIGNMENT_REQUEST("accept_assignment_request"),

- REJECT_ASSIGNMENT_REQUEST("reject_assignment_request"),

- CASE_UNARCHIVED("case_unarchived"),

- BUSINESS_EXCEPTION("business_exception"),

- ARCHIVING_USER_EXCEPTION("archiving_user_exception"),

- CASE_ASSIGNMENT_EXCEPTION("case_assignment_exception"),

- RECEIVING_A_SED_WITH_AN_INVALID_BUSINESS_SIG("receivingASedWithAnInvalidBusinessSignature"),

- RECEIVING_A_SED_ATTACHMENT_WHICH_FILED_ANTIMALWARE_CHECKING("receivingASedAttachmentWhichFiledAntimalwareChecking"),

- UNKNOWN_CAUSE("unknownCause"),

- WRONG_UPDATE("wrong_update");

# TITOLO-TO BE

La sistemazione del bug prevede che anche per le notifiche "Case\
automatically closed", "Your Alarm Expired" e "Case SEDs Automatically\
Sent to New Participant" sia possibile marcarla come letta.

È stato verificato che l'Id della notifica è presente nel DB, eseguendo\
la query con un Id notifica restituito nell'errore:

**SELECT** *n*.id, *iu*.id **AS** *user_id*

**FROM** notification *n*

**JOIN** notification_user *nu* **ON** *nu*.fk_notification_sid =\
*n*.sid

**JOIN** iam_user *iu* **ON** *nu*.fk_user_sid = *iu*.sid

**WHERE** *n*.id = '2bf0955ab14f4e3ba147c7534567c748'

**AND** *iu*.id = 'utente_analisi'

Non restituisce risultati, ma se si esclude "**AND** *iu*.id =\
'utente_analisi'" vengono restuiti risultati.

## 3.1 RIEPILOGO DELLE MODIFICHE

\---

# casi d'uso

Lo scopo di questo capitolo è quello di indicare i percorsi da\
effettuare per verificare il caso.

- Cliccare su Notifications

- Filtrare per tipologia "Case SEDs Automatically Sent to New\
  Participant" o "Case Automatically Closed"

- Cliccare sulla freccia

  ![](./immagini/media/image11.png){width="0.3021259842519685in"\
  height="0.3021259842519685in"} per espandere il dettaglio della\
  notifica, oppure nelle action cliccare su "Marks as Read"

> ![Immagine che contiene testo, schermata, Carattere, Blu elettrico Il
contenuto generato dallIA potrebbe non essere
corretto.](./immagini/media/image12.png){width="1.906515748031496in"\
> height="1.166829615048119in"}

- La notifica deve avere carattere normale e non essere più in\
  grassetto.

Se non esistono notifiche di quel tipo si può riprodurre il caso creando\
ad esempio un P_BUC_01:

- Scelgo un partecipante per il quale posso accedere come CP

- Invio P2000

- Dal case action creo un Forward Case e Invio l' X007 scegliendo come\
  partecipante un'istituzione per la quale riesco ad accedere su JINA\
  (Istituzione X)

- Dalle notifications trovo "Case SEDs Automatically Sent to New\
  Participant"

Oppure:

- Creo P_BUC_01

- Scelgo due partecipanti (uno per il quale posso accedere come CP)

- Invio P2000

- Attendo che il SED arrivi al partecipante CP per il quale ho l'accesso\
  a JINA

- CO elimina il partecipante CP per il quale ho l'accesso a JINA\
  inviando X006

- Accedo alle notification del partecipante CP appena eliminato

- Trovo la notifica "Case automatically closed".

# References and Related Documents

---

**#** **Reference or Related Document** **Source or Link/Location**

---

1 JINA-BUGs\_ RN_11625596.docx

---