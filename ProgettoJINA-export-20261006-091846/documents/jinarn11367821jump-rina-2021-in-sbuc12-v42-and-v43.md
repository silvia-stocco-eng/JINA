---
unique-name: jinarn11367821jump-rina-2021-in-sbuc12-v42-and-v43
display-name: JINA RN 11367821 JUMP RINA 2021 in S BUC 12 v4.2 and v4.3 allows CaseOwner to send Reminder (X009)   V1.0 (1)
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

*RN11367821-- JUMP RINA 2021 in S_BUC_12 v4.2 and v4.3 allows\
CaseOwner to send Reminder (X009)​ (Functional Analysis)*

**CIG 9623953142**

(CIG 9623953142)

---

Date: 17 Doc.\
Dicembre 2025 Version:\
1.0

---

---

**Document Control Information**

---

**Settings** **Value**

---

**Document Title:** *RN11367821 -- JUMP RINA 2021 in S_BUC_12 v4.2\
and v4.3 allows CaseOwner to send Reminder\
(X009)​ (Functional Analysis)*

**Project Id:** CIG 9623953142

**Document Authors:**

**Project Owner:** Barbara Ingrosso (PO)

**Project Manager:** Milko Anselmi (PM)

**Doc. Version:** 1.0

**Sensitivity:** Reserved

## **Date:** 17 Dicember 2025

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
**RN:1367821**

ed eventuali impatti sull'applicativo.

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

**CR number** : RN:11367821

**Title**: JUMP RINA 2021 in S_BUC_12 v4.2 and v4.3 allows CaseOwner to\
send Reminder (X009)​

**Slot:** 3

**Elementi impattati**: transaction X009 S_BUC_12

# titolo- AS-IS

Attualmente in JINA è abilitato per il ruolo CO tra le "Case Action" il\
"Create Remander".

![Immagine che contiene testo, software, Icona del computer, Pagina Web
Il contenuto generato dallIA potrebbe non essere
corretto.](./immagini/media/image10.png){width="5.772222222222222in"\
height="2.591666666666667in"}

Inviando il SED X009 l'invio fallisce con l'errore della seguente\
immagine:

![Immagine che contiene testo, schermata, Carattere, numero Il contenuto
generato dallIA potrebbe non essere
corretto.](./immagini/media/image11.png){width="5.772222222222222in"\
height="1.05in"}

Questo accade perché non è presente la transaction\
S_BUC_12-4.4-CaseOwner-Counterparty-New-X009-4.4.xsd dato che l'azione\
non è permessa per il ruolo CO.

# TITOLO-TO BE

La modifica chiede di **disabilitare** per il ruolo **CO** del\
**S_BUC_12** dalle "**Case Action**" il "**Create reminder**" in modo\
tale che il CO non possa inviare il SED X009.

L'azione del "Create reminder" dovrà rimanere disponibile per il ruolo\
CP come già attualmente accade.

## 3.1 RIEPILOGO DELLE MODIFICHE

\-----

# casi d'uso

Lo scopo di questo capitolo è quello di indicare i percorsi da\
effettuare per verificare il caso.

**Creazione S_BUC_12:**

Il CO crea il caso S_BUC_12 e invia il SED S055

Dalla Case Action del CO dopo l'invio del sed attivatore non deve essere\
disponibile il "Create reminder"

Il CP riceve il SED S055 e dalla "Case action" deve avere disponibile il\
"Create Reminder".

# References and Related Documents

---

**#** **Reference or Related Document** **Source or Link/Location**

---

1 RN11367821 JUMP RINA 2021 in\
S_BUC_12 v4.2 and v4.3 allows\
CaseOwner to send Reminder (X009)

---