---
unique-name: jina-rn-nie-group-eessi-6261-6255-2490-8840-fa-v10
display-name: JINA RN NIE Group: EESSI-6261, EESSI-6255, EESSI-2490, EESSI-8840 (Functional Analysis) V1.0
category: GENERAL
description: Analisi funzionale del NIE Group comprendente i ticket JIRA EESSI-2490 (identity propagation), EESSI-6255 (document ID/version in NIE notifications), EESSI-6261 (robust NIE implementation), EESSI-8840 (UI feedback during NIE exchange). Struttura: AS-IS, TO-BE, Riepilogo Modifiche, Casi d'uso, Punti Aperti vs documenti EY. Fonte primaria: ticket JIRA originali.
tags: cret
---

# NIE Group: EESSI – 6261, EESSI – 6255, EESSI – 2490, EESSI – 8840
## *(Functional Analysis)*

**TGC Engineering Ingegneria Informatica**
**CIG 9623953142**

---

| Date: [DA DEFINIRE] | Doc. Version: 1.0 | Status: Draft |

---

### Document Control Information

| Settings | Value |
|---|---|
| **Document Title** | NIE Group: EESSI – 6261, EESSI – 6255, EESSI – 2490, EESSI – 8840 (Functional Analysis) |
| **Project Id** | CIG 9623953142 |
| **Document Authors** | [DA DEFINIRE] |
| **Project Owner** | Barbara Ingrosso (PO) |
| **Project Manager** | Milko Anselmi (PM) |
| **Doc. Version** | 1.0 |
| **Sensitivity** | Reserved |
| **Date** | [DA DEFINIRE] |

**Document Approver(s) and Reviewer(s):**

| Name | Role | Action | Date |
|---|---|---|---|
| [DA DEFINIRE] | | \<Approve / Review\> | |
| [DA DEFINIRE] | | \<Approve / Review\> | |

**Document history:**

| Revision | Date | Created by | Short Description of Changes |
|---|---|---|---|
| 1.0 | [DA DEFINIRE] | [DA DEFINIRE] | First draft |

---

## Sommario

1. Introduction
   - 1.1 General Overview
   - 1.2 Scope
   - 1.3 Glossary of Terms
   - 1.4 CR Overview
2. NIE Group – AS-IS
3. NIE Group – TO-BE
   - 3.1 Riepilogo delle Modifiche
4. Casi d'uso
5. Verifiche da effettuare
6. References and Related Documents
7. Punti Aperti

---

## 1. Introduction

### 1.1 General Overview

The Join Implementation of a National Applications (JINA) is a web-based software application for the electronic management and exchange of social security cases across competent institutions of the participant countries. Currently managed by *Jump-RINA* to ensure the evolution of the EESSI project (Electronic Exchange of Social Security Information).

### 1.2 Scope

Il presente documento ha natura dinamica ed è soggetto ad aggiornamenti e approfondimenti durante tutto il ciclo di vita del progetto. I contenuti riportati nel documento descrivono il comportamento attuale (AS-IS) e le indicazioni funzionali sul comportamento futuro (TO-BE) secondo quanto richiesto dai ticket JIRA **EESSI-2490, EESSI-6255, EESSI-6261 ed EESSI-8840**, raggruppati sotto il tema **NIE Group**, per il CDM [DA DEFINIRE] ed eventuali impatti sull'applicativo JINA.

Tutti e quattro i ticket riguardano la componente **RINA** e l'interfaccia **NIE (National Information Exchange)**.

### 1.3 Glossary of Terms

| Term/Acronym | Definition |
|---|---|
| RINA | Reference Implementation of National Applications |
| CDM | Common Data Model |
| CR | Change Request |
| SED | Structured Electronic Document |
| BUC | Business Use Case |
| CO | Case Owner |
| CP | Counterparty |
| NIE | National Information Exchange (interface) |
| NA | National Application |
| API | Application Programming Interface |
| NAV | Norwegian Labour and Welfare Administration |
| CAK | [DA DEFINIRE] – reporter ticket EESSI-6261 (Netherlands) |

### 1.4 CR Overview

| CR | Title | Reporter Country | Affects Version | Severity | Priority |
|---|---|---|---|---|---|
| EESSI-2490 | Support for identity propagation (security context) from the NIE interface | Norway | RINA 5.0.3 | Major | Major |
| EESSI-6255 | Add document ID and version number for notification events related to documents | Czech Republic | RINA 5.4.1 | Major | Major |
| EESSI-6261 | CAK: Create more robust NIE implementation | Netherlands | RINA 5.4.3 | **Critical** | Major |
| EESSI-8840 | Exchanging information using NIE settings in RINA | Greece | RINA 2020 | Major | Major |

**Slot:** [DA DEFINIRE]

**Elementi impattati:** NIE interface, RINA UI, National Applications (NA)

> ⚠️ *Nota*: tutti i ticket hanno status **CLOSED** su JIRA (risolti a Dicembre 2025). Fix Version = None per tutti. La Commissione Europea ha comunicato che queste CR non vengono implementate centralmente ma sono **handover agli Stati Membri**.
> *(Source: commenti JIRA EESSI-2490, EESSI-6255, EESSI-6261, EESSI-8840 – RADUCANU Elena, Jul 2022)*

---

## 2. NIE Group – AS-IS

### 2.1 EESSI-2490 – Identity Propagation (Norway – NAV)

NAV ha sviluppato una propria applicazione che espone le API necessarie per gestire gli eventi NIE relativi a casi e documenti (eventi *RestCase* e *RestDocument*). NAV non utilizza l'applicazione di riferimento RINIE.

Attualmente queste API non dispongono di un layer di autorizzazione: non esiste alcun meccanismo che verifichi l'identità del clerk che ha eseguito l'azione in RINA quando un evento viene inviato all'API. Di conseguenza, utenti non autorizzati potrebbero potenzialmente invocare le API e accedere alle informazioni sensibili sui casi e documenti.

> *Source: JIRA EESSI-2490 – Description (05/Feb/18)*

---

### 2.2 EESSI-6255 – Missing document ID/version in NIE notification events (Czech Republic)

Le National Applications ricevono eventi di notifica NIE "SED Delivered" e "SED Failed to be Delivered". Il payload di questi eventi **non contiene il document ID né il version number**: include unicamente il tipo documento (es. H001).

Quando in un caso esistono più versioni di un documento o più documenti dello stesso tipo, non è possibile identificare in modo sicuro a quale documento specifico si riferisce l'evento.

> *Source: JIRA EESSI-6255 – Description + Current Situation field: "The notification events related to documents (e.g. document delivered) do not contain the document ID and document version. As a result the notifications cannot be safely linked with the right document/version."*

---

### 2.3 EESSI-6261 – NIE not robust: lost notifications (Netherlands – CAK)

L'interfaccia NIE viene utilizzata per trasmettere i SED ricevuti alle National Applications. Quando una notifica fallisce, si genera un errore di sistema (Java exception) e la notifica **non viene ritentata né loggata**.

Come risultato, si riscontrano dati di produzione inconsistenti e incompleti nelle National Applications. Gli amministratori non hanno alcuna possibilità di riconoscere, processare, correggere o rinviare manualmente le notifiche fallite.

> *Source: JIRA EESSI-6261 – Description + Current Situation: "Failure of NIE events resulting in lost messages at business level. Rights of citizens are at stake when messages can be lost."*

---

### 2.4 EESSI-8840 – No UI feedback during NIE data exchange (Greece)

L'applicazione RINA è configurata per scambiare informazioni con le National Applications tramite le impostazioni NIE. L'esportazione da RINA verso le NA funziona correttamente (la creazione di un nuovo SED triggerizza correttamente l'evento).

Tuttavia, quando la NA invia informazioni aggiornate a RINA tramite NIE callback, **l'interfaccia utente di RINA non informa l'operatore** che è in corso una comunicazione: nessuna icona loader o indicatore visivo è mostrato. Una volta che le informazioni sono restituite e aggiornate in RINA, l'operatore deve **chiudere e riaprire il SED** per vedere le modifiche.

> *Source: JIRA EESSI-8840 – Description (29/Apr/21): "The user of RINA is not informed about this communication and sees no visual loader icon. After the info is returned and updated in RINA, the user needs to close and reopen the SED in order to see the info."*

---

## 3. NIE Group – TO-BE

### 3.1 EESSI-2490 – Identity Propagation

NAV richiede un sistema in cui **l'identità del clerk che ha eseguito un'azione in RINA venga propagata e verificata** quando un evento viene inviato all'API di NAV. L'API deve autenticare e autorizzare le richieste in base all'identità del clerk, garantendo che solo i soggetti con le autorizzazioni appropriate possano accedere alle informazioni.

La soluzione deve essere compatibile con l'ecosistema tecnologico esistente di NAV, inclusa la piattaforma Bonita.

> *Source: JIRA EESSI-2490 – Description: "implement a system where the identity of the clerk who performed an action in RINA is carried over and verified when an event is sent to the API [...] within the constraints of their current technological ecosystem, including the Bonita platform."*

---

### 3.2 EESSI-6255 – Document ID and version in NIE notification events

Il **document ID e il version number** devono essere aggiunti al payload degli eventi di notifica NIE relativi ai documenti (es. "SED Delivered", "SED Failed to be Delivered").

I SED state change notifications devono essere riclassificati nella categoria **"Document Events"**.

> *Source: JIRA EESSI-6255 – Desired Situation: "To add the document ID and version number into notifications events related to documents. The National Application would need at least document ID and version in the payload. Also, the document related events should be moved into 'document events' category."*

> ⚠️ **Nota stato implementazione**: Secondo il commento JIRA (RADUCANU Elena, 12/Jul/22): *"This CR was partially implemented – the document ID is present, the version is missing."* Il requisito sul **version number è ancora aperto**.

---

### 3.3 EESSI-6261 – Robust NIE with reliable delivery and error handling

Il **requisito minimo** è che le notifiche NIE fallite vengano **almeno loggiate**. La soluzione preferita è un **meccanismo di retry automatico** per le notifiche non consegnate.

L'implementazione deve essere effettuata il prima possibile, preferibilmente come **hotfix**.

> *Source: JIRA EESSI-6261 – Description: "Minimal requirement is that failed notifications are at least logged [...] this should be implemented as soon as possible, preferably as a hotfix." + Desired Situation: "Robust implementation of NIE with reliable delivery and error handling."*

---

### 3.4 EESSI-8840 – UI feedback and live SED update during NIE exchange

Quando una NA invia informazioni aggiornate a RINA tramite NIE callback, l'interfaccia RINA deve:
1. **Informare l'operatore** che è in corso una comunicazione con una National Application (es. indicatore visivo / loader icon)
2. **Aggiornare la vista del SED in tempo reale**, senza richiedere all'operatore di chiudere e riaprire il documento

> *Source: JIRA EESSI-8840 – Description*

---

### 3.5 Riepilogo delle Modifiche

| # | Ticket | Componente | Modifica richiesta |
|---|---|---|---|
| 1 | EESSI-2490 | NIE / NA (NAV) | Implementare autenticazione/autorizzazione sulle API NIE di NAV con propagazione dell'identità del clerk da RINA |
| 2 | EESSI-6255 | NIE | Aggiungere document ID e version number nel payload degli eventi di notifica NIE relativi a documenti |
| 3 | EESSI-6255 | NIE | Riclassificare i SED state change notifications nella categoria "Document Events" |
| 4 | EESSI-6261 | NIE | Logging minimo delle notifiche fallite; preferibilmente meccanismo di retry automatico |
| 5 | EESSI-8840 | RINA UI / NIE | Mostrare indicatore visivo durante comunicazioni NIE in corso; aggiornare la vista SED in real-time senza chiusura/riapertura |

---

## 4. Casi d'uso

### 4.1 EESSI-2490 – Secure API access via identity propagation

**Scenario:** Un clerk esegue un'azione in RINA che genera un evento NIE verso le API di NAV.

**AS-IS:** L'evento viene inviato all'API di NAV senza verifica dell'identità del clerk. Qualsiasi chiamante può invocare le API.

**TO-BE:** L'evento include il contesto di sicurezza del clerk. L'API di NAV verifica che il chiamante sia autorizzato prima di processare l'evento.

---

### 4.2 EESSI-6255 – Identify correct document from NIE notification

**Scenario:** Una NA riceve un evento "SED Delivered" o "SED Failed to be Delivered" per un caso con più versioni dello stesso documento.

**AS-IS:** Il payload contiene solo il tipo documento (es. H001). Non è possibile identificare quale versione specifica è oggetto dell'evento.

**TO-BE:** Il payload contiene document ID e version number. La NA identifica univocamente il documento oggetto dell'evento. L'evento è visibile nella categoria "Document Events".

---

### 4.3 EESSI-6261 – Handling failed NIE notification

**Scenario:** Una notifica NIE verso una NA fallisce durante la consegna.

**AS-IS:** Si genera una Java exception. La notifica non viene ritentata né loggata. I dati nella NA risultano incompleti/inconsistenti.

**TO-BE (minimo):** La notifica fallita viene loggata.
**TO-BE (preferred):** Il sistema ritenta automaticamente la consegna fino al successo.

---

### 4.4 EESSI-8840 – Real-time UI update during NIE exchange

**Scenario:** Un operatore RINA ha aperto un SED. La NA invia informazioni aggiornate a RINA tramite NIE callback.

**AS-IS:** L'operatore non vede indicazioni della comunicazione in corso. Deve chiudere e riaprire il SED per vedere le modifiche.

**TO-BE:** L'interfaccia RINA mostra un indicatore visivo della comunicazione in corso. Le modifiche sono riflesse automaticamente nel SED aperto.

---

## 5. Verifiche da effettuare

[DA DEFINIRE]

---

## 6. References and Related Documents

| # | Reference or Related Document | Source or Link/Location |
|---|---|---|
| 1 | EESSI-2490: Support for identity propagation (security context) from the NIE interface | https://citnet.tech.ec.europa.eu/CITnet/jira/browse/EESSI-2490 |
| 2 | EESSI-6255: Add document ID and version number for notification events related to documents | https://citnet.tech.ec.europa.eu/CITnet/jira/browse/EESSI-6255 |
| 3 | EESSI-6261: CAK: Create more robust NIE implementation | https://citnet.tech.ec.europa.eu/CITnet/jira/browse/EESSI-6261 |
| 4 | EESSI-8840: Exchanging information using NIE settings in RINA | https://citnet.tech.ec.europa.eu/CITnet/jira/browse/EESSI-8840 |
| 5 | EESSI-2461: RINA CAS with token (JWT, OIDC, SAML) | https://citnet.tech.ec.europa.eu/CITnet/jira/browse/EESSI-2461 |
| 6 | EESSI-2491: Support for token based authentication | https://citnet.tech.ec.europa.eu/CITnet/jira/browse/EESSI-2491 |
| 7 | EESSI-5694: Notification events related to documents | https://citnet.tech.ec.europa.eu/CITnet/jira/browse/EESSI-5694 |
| 8 | EESSI-6334: CAK: Logging in NieClientImpl | https://citnet.tech.ec.europa.eu/CITnet/jira/browse/EESSI-6334 |

---

## 7. Punti Aperti

Differenze rilevate tra i documenti JIRA (fonte primaria) e i documenti EY presenti in KB:

| # | Ticket | Differenza | Impatto |
|---|---|---|---|
| 1 | EESSI-6255 | CR **parzialmente implementata** (document ID presente, version number mancante – commento JIRA 12/Jul/22). I documenti EY non menzionano questo stato. | ⚠️ Richiede verifica se il version number è ancora da implementare in JINA |
| 2 | EESSI-6261 | I doc EY introducono il requisito di una **dashboard** per il monitoraggio delle notifiche da parte degli amministratori. Il JIRA originale richiede unicamente logging minimo ("failed notifications are at least logged"). | ⚠️ Dashboard non è nel perimetro JIRA. Da decidere se includerla nello scope |
| 3 | EESSI-8840 | I doc EY aggiungono requisiti di **Operational Efficiency**, **Data Accuracy and Timeliness** e **Strategic Alignment** non presenti nella JIRA originale, che descrive esclusivamente il problema UI (loader + ricaricamento SED). | ℹ️ Requisiti ampliati rispetto all'originale, da confermare con il cliente |
| 4 | EESSI-2490 | I doc EY indicano esplicitamente l'approccio **token-based** ("API consumers will adjust their procedures to include the new authentication token"). Il JIRA non specifica la soluzione tecnica, chiedendo solo di valutare cosa è possibile fare. | ℹ️ Soluzione tecnica [DA DEFINIRE] secondo JIRA |
| 5 | Tutti | I doc EY non riportano che tutti i ticket sono **CLOSED** su JIRA (Dic 2025) e che la CE non li implementerà centralmente (handover agli Stati Membri). | ℹ️ Da chiarire l'impatto sul perimetro di implementazione JINA |
