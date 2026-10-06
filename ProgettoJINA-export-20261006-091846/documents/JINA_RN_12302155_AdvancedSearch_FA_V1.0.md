---
unique-name: JINA_RN_12302155_AdvancedSearch_FA_V1.0
display-name: JINA RN:12302155 — Notification Centre Advanced Search (Functional Analysis) V1.0
category: CR
description: Analisi funzionale della CR RN:12302155 — Potenziamento del Notification Centre con Ricerca Avanzata: nuove colonne tabella, filtri per periodo/BUC/Tipo Evento/SED, persistenza filtri in sessione, export Excel. Struttura: AS-IS, TO-BE, Riepilogo modifiche FE/BE, Casi d'uso, Verifiche.
tags: eng
---

# JINA RN:12302155 — Notification Centre Advanced Search (Functional Analysis)

**TGC Engineering Ingegneria Informatica**

*RN:12302155 — Notification Centre Advanced Search (Functional Analysis)*

**CIG 9623953142**

---

| Date: Giugno 2026 | Doc. Version: 1.0 |
| --- | --- |

---

**Document Control Information**

| Settings | Value |
| --- | --- |
| **Document Title:** | JINA RN:12302155 — Notification Centre Advanced Search (Functional Analysis) |
| **Project Id:** | CIG 9623953142 |
| **Document Authors:** | TGC Analyst Team |
| **Project Owner:** | Barbara Ingrosso (PO) |
| **Project Manager:** | Milko Anselmi (PM) |
| **Doc. Version:** | 1.0 |
| **Sensitivity:** | Reserved |
| **Date:** | Giugno 2026 |

**Document Approver(s) and Reviewer(s):**

NOTE: All Approvers are required. Records of each approver must be maintained. All Reviewers in the list are considered required unless explicitly listed as Optional.

| Name | Role | Action | Date |
| --- | --- | --- | --- |
|  |  | *&lt;Approve / Review&gt;* |  |
|  |  | *&lt;Approve / Review&gt;* |  |
|  |  | *&lt;Approve / Review&gt;* |  |

**Document history:**

The Document Author is authorized to make the following types of changes to the document without requiring that the document be re-approved:

- Editorial, formatting, and spelling
- Clarification

Changes to this document are summarized in the following table in reverse chronological order (latest version first).

| Revision | Date | Created by | Short Description of Changes |
| --- | --- | --- | --- |
| 1.0 | Giugno 2026 | TGC Analyst Team | Prima emissione analisi funzionale |

**Configuration Management: Document Location**

The latest version of this controlled document is stored in: *EESSIGateway*

---

## Sommario

[1 Introduction](#introduction)

[1.1 General Overview](#general-overview)

[1.2 Scope](#scope)

[1.3 Glossary of Terms](#glossary-of-terms)

[1.4 CR Overview](#cr-overview)

[2 Notification Centre — AS-IS](#notification-centre--as-is)

[3 Notification Centre Advanced Search — TO-BE](#notification-centre-advanced-search--to-be)

[3.1 Riepilogo delle modifiche](#riepilogo-delle-modifiche)

[4 Casi d'uso](#casi-duso)

[5 Verifiche da effettuare](#verifiche-da-effettuare)

[6 References and Related Documents](#references-and-related-documents)

---

# Introduction

## General Overview

The Join Implementation of a National Applications (JINA) is a web-based software application for the electronic management and exchange of social security cases across competent institutions of the participant countries. Currently managed by *Jump-RINA* to ensure the evolution of the EESSI project (Electronic Exchange of Social Security Information).

## Scope

Il presente documento ha natura dinamica ed è soggetto ad aggiornamenti e approfondimenti durante tutto il ciclo di vita del progetto. I contenuti riportati nel documento descrivono il comportamento attuale (AS-IS) e le indicazioni funzionali sul comportamento futuro (TO-BE) secondo quanto richiesto dalla **RN:12302155** per il **Slot 8**, con eventuali impatti sull'applicativo JINA.

Il documento costituisce il riferimento funzionale per il team di sviluppo ai fini dell'implementazione delle modifiche richieste dalla CR RN:12302155, che prevede il potenziamento del Notification Centre mediante l'introduzione di una funzionalità di Ricerca Avanzata, l'aggiunta di nuove colonne nella tabella delle notifiche, la persistenza dei filtri di ricerca nella sessione utente e la possibilità di esportare i risultati in formato Excel.

## Glossary of Terms

| Term/Acronym | Definition |
| --- | --- |
| RINA | Reference Implementation of National Applications |
| JINA | Join Implementation of National Applications |
| EESSI | Electronic Exchange of Social Security Information |
| CDM | Common Data Model |
| CR | Change Request |
| SED | Structured Electronic Document |
| BUC | Business Use Case |
| CO | Case Owner |
| CP | Counterparty |
| FE | Frontend |
| BE | Backend |
| Notification Centre | Modulo dell'applicativo JINA che raccoglie tutte le notifiche relative ai casi dell'utente |
| Starter SED | Primo SED che ha dato avvio a un caso (caso in cui il tipo evento è relativo a un Case) |
| List Box ceccabile | Elemento di interfaccia a lista con selezione singola (un solo valore selezionabile per volta) |
| Local Case ID | Identificativo locale del caso assegnato dal sistema |

## CR Overview

**CR number**: RN:12302155

**Title**: Notification Centre — Advanced Search

**Slot**: 8

**Elementi impattati**: User Portal — Notification Centre (visualizzazione tabella, filtri di ricerca, navigazione, export)

---

# Notification Centre — AS-IS

Attualmente il Notification Centre di JINA fornisce agli utenti una vista tabellare delle notifiche ricevute. La pagina presenta le notifiche in ordine cronologico con un numero limitato di colonne e funzionalità di ricerca di base.

Le **limitazioni attuali** sono le seguenti:

1. **Colonne mancanti**: la tabella delle notifiche mostra informazioni limitate, prive di dettagli chiave quali:

   - Origine BUC (serie)
   - Numero BUC
   - Tipo Evento
   - SED name/number
   - Local Case ID
   - Cognome e Nome dell'assistito

2. **Assenza di Ricerca Avanzata**: non è disponibile una funzionalità di ricerca avanzata che consenta di filtrare le notifiche per periodo, tipo di evento, SED o serie BUC. Questo rende difficoltoso e dispendioso in termini di tempo il reperimento di notifiche specifiche.

3. **Assenza di export**: non è possibile esportare i dati del Notification Centre in formato Excel per analisi o reportistica.

4. **Perdita dei filtri alla navigazione**: quando l'utente naviga fuori dal Notification Centre (ad esempio aprendo un caso) e vi ritorna, i filtri di ricerca eventualmente applicati vengono persi, costringendo l'utente a reimpostarli.

---

# Notification Centre Advanced Search — TO-BE

Con l'implementazione della CR RN:12302155, il Notification Centre viene arricchito con le seguenti nuove funzionalità:

- **A** — Nuove colonne nella tabella delle notifiche
- **B** — Maschera di Ricerca Avanzata con filtri per periodo, Serie BUC, Tipo Evento e SED
- **C** — Persistenza dei filtri di ricerca nella sessione utente (navigazione con back)
- **D** — Export dei risultati in formato Excel (.xlsx), generato lato BE

---

### A — Nuove colonne nella tabella del Notification Centre

La tabella del Notification Centre viene estesa con le seguenti colonne aggiuntive:

| Colonna | Descrizione | Note |
| --- | --- | --- |
| **Tipo Evento** | Codice/etichetta dell'evento che ha generato la notifica | Valorizzato con i valori della Lista Tipo Evento |
| **BUC di origine** | Codice completo del BUC (es. H_BUC_01, R_BUC_07) | Valorizzato con i valori della Lista BUC |
| **Numero BUC** | Numero identificativo del BUC | Valore numerico |
| **ID** (Local Case ID) | Identificativo locale del caso | Stringa identificativa univoca |
| **Serie BUC di origine** | Lettera/sigla della serie BUC (es. H, R, U) | Derivata dal BUC di origine |
| **Tipo** | Descrizione in italiano del tipo di evento | Testo descrittivo localizzato |
| **SED** | Codice SED associato alla notifica | Se il Tipo Evento è relativo a un Case, mostrare unicamente lo starter SED del caso ⚠️ *\[TBD: definire i criteri per determinare quando un Tipo Evento è "related to a Case" — da concordare con il team di sviluppo BE\]* |
| **Cognome/Nome** | Cognome e nome dell'assistito | Può essere vuoto in alcuni casi |
| **Azioni** | Menu azioni sulla notifica (es. "Visualizza") | Colonna già esistente |

---

### B — Maschera di Ricerca Avanzata

Viene implementata una maschera di Ricerca Avanzata accessibile dal Notification Centre. I campi della maschera sono i seguenti:

| Campo | Tipo | Obbligatorietà | Note |
| --- | --- | --- | --- |
| **Periodo Dal** | Date picker | **Obbligatorio** | Data di inizio del periodo di ricerca |
| **Periodo Al** | Date picker | **Obbligatorio** | Data di fine del periodo di ricerca |
| **Serie BUC** | List Box ceccabile (selezione singola) | Facoltativo (\*) | Vedi lista valori sotto |
| **Tipo Evento** | List Box ceccabile (selezione singola) | Facoltativo (\*) | Vedi lista valori sotto |
| **SED** | List Box ceccabile (selezione singola) | Facoltativo (\*) | Vedi lista valori sotto |

> **(\*) Regola di obbligatorietà condizionale**: almeno uno tra i campi *Serie BUC*, *Tipo Evento* e *SED* deve essere valorizzato. Non è necessario compilarli tutti e tre contemporaneamente (es. è valido compilare solo *Tipo Evento* e *SED* senza specificare la *Serie BUC*).

> **⚠️ TBD — Range temporale massimo**: l'ampiezza massima del periodo Dal/Al è da definirsi in base ai limiti tecnici (volumi dati).

> **Nota su Serie BUC**: è possibile selezionare un valore specifico (es. *R_BUC_07*) oppure un valore parziale di serie (es. *R_BUC*, *P_BUC*) per includere tutti i BUC di quella famiglia senza specificare il numero.

Lista valori — Serie BUC

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| H_BUC_07 | H_BUC_08 | H_BUC_09 | H_BUC_10 | M_BUC_01 |
| M_BUC_02 | M_BUC_03a | M_BUC_03b | AD_BUC_01 | AD_BUC_02 |
| AD_BUC_03 | AD_BUC_04 | AD_BUC_05 | AD_BUC_06 | AD_BUC_07 |
| AD_BUC_08 | AD_BUC_09 | AD_BUC_10 | AD_BUC_11 | AD_BUC_12 |
| P_BUC_01 | P_BUC_02 | P_BUC_03 | P_BUC_04 | P_BUC_05 |
| P_BUC_06 | P_BUC_07 | P_BUC_08 | P_BUC_09 | P_BUC_10 |
| UB_BUC_01 | UB_BUC_02 | UB_BUC_03 | UB_BUC_04 | FB_BUC_01 |
| FB_BUC_02 | FB_BUC_03 | FB_BUC_04 | S_BUC_12 | S_BUC_14 |
| S_BUC_14a | S_BUC_14b | S_BUC_24 | R_BUC_01 | R_BUC_02 |
| R_BUC_03 | R_BUC_04 | R_BUC_05 | R_BUC_06 | R_BUC_07 |
| LA_BUC_01 | LA_BUC_02 | LA_BUC_03 | LA_BUC_04 | LA_BUC_05 |
| LA_BUC_06 |  |  |  |  |

Lista valori — Tipo Evento

|  |  |
| --- | --- |
| A duplicate message arrived | A duplicate SED (update) has arrived |
| A New Case Arrived | A New SED Arrived |
| A wrong SED (update) has arrived | Aggiornamento SED senza creare |
| Causa sconosciuta | È arrivato un SED aggiornato |
| Eccezione nell'archiviazione del caso | Eccezione nell'assegnazione del caso |
| Firma business non valida | Il tuo allarme è scaduto |
| Mancato recapito del SED | Pratica assegnata |
| Pratica chiusa | Pratica chiusa automaticamente |
| Pratica disassegnata | Pratica inoltrata |
| Pratica mancante | Pratica rimossa |
| Problema nell'archiviazione del caso | Richiesta di assegnazione della pratica |
| Richiesta di assegnazione della pratica accolta | Richiesta di assegnazione della pratica respinta |
| SED della pratica automaticamente inviati a nuovo partecipante | SED in sequenza errata |
| SED non corrispondente alla pratica | SED recapitato |
| Si richiede approvazione per l'invio del SED | Verifica antimalware allegato fallita |

Lista valori — SED

|  |  |  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| A003 | A004 | A005 | A006 | A007 | A008 | A009 | A010 | A012 |
| F001 | F002 | F003 | F004 | F016 | F017 | F022 | F023 | F026 |
| F027 | H001 | H002 | H003 | H005 | H006 | H061 | H065 | H066 |
| H070 | H120 | H121 | M052 | M053 | P2000 | P2100 | P2200 | P3000_IT |
| P3000_DE | P4000 | P5000 | P6000 | P7000 | P8000 | P9000 | P10000 | P11000 |
| P12000 | P15000 | R001 | R002 | R010 | R012 | R014 | R015 | R017 |
| R018 | R025 | R029 | S040 | S041 | S048 | S055 | U001 | U001CB |
| U002 | U003 | U004 | U005 | U006 | U007 | U009 | U010 | U012 |
| U013 | U017 | U018 | X001 | X002 | X003 | X005 | X006 | X007 |
| X008 | X009 | X010 | X011 | X012 | X013 | X050 | X100 | NULL |

---

### C — Persistenza dei filtri di ricerca nella sessione

La funzionalità di navigazione viene implementata tramite **persistenza dei parametri di ricerca nella sessione utente**, in analogia con quanto già adottato in altri casi d'uso dell'applicativo JINA.

**Comportamento atteso:**

- Quando l'utente naviga fuori dal Notification Centre (es. apertura di un caso tramite l'azione "Visualizza") e successivamente torna indietro (back), il sistema ripristina automaticamente i filtri di ricerca precedentemente applicati.
- I risultati della ricerca vengono visualizzati nello stato in cui si trovavano prima della navigazione.

> **Nota**: non è prevista l'apertura del caso in una nuova finestra. La voce "Open in a new window" indicata nel TO-BE del CR non viene implementata; la gestione del ritorno al Notification Centre avviene esclusivamente tramite persistenza in sessione.

---

### D — Export Excel

L'utente può esportare i risultati della ricerca avanzata in un file **Excel (.xlsx)**. La generazione del file avviene **lato BE**.

**Comportamento atteso:**

- Un pulsante/link "Esportazione in Excel" è disponibile nella pagina dei risultati della ricerca avanzata.
- Il file .xlsx generato contiene tutte le righe corrispondenti ai filtri applicati, con le stesse colonne della tabella visualizzata a schermo.
- L'export è disponibile solo a seguito di una ricerca avanzata (con i filtri obbligatori valorizzati).

---

## Riepilogo delle modifiche

Di seguito l'elenco delle modifiche da implementare, suddivise per area (FE / BE):

### Modifiche FE

| \# | Modifica | Descrizione |
| --- | --- | --- |
| FE-01 | **Visualizzazione tabella — nuovi dati** | Aggiungere alla tabella del Notification Centre le colonne: *Tipo Evento*, *BUC di origine*, *Numero BUC*, *ID (Local Case ID)*, *Serie BUC di origine*, *Tipo*, *SED*, *Cognome/Nome*. La colonna *Azioni* rimane esistente. |
| FE-02 | **Nuovi filtri di ricerca** | Implementare la maschera di Ricerca Avanzata con i campi: *Periodo Dal* (obbligatorio), *Periodo Al* (obbligatorio), *Serie BUC* (List Box, selezione singola, facoltativo), *Tipo Evento* (List Box, selezione singola, facoltativo), *SED* (List Box, selezione singola, facoltativo). Gestire la validazione: periodi obbligatori; almeno uno tra Serie BUC, Tipo Evento e SED deve essere compilato. |
| FE-03 | **Navigazione con persistenza filtri** | Implementare la persistenza dei parametri di ricerca nella sessione utente. Al ritorno al Notification Centre (back), ripristinare automaticamente i filtri applicati e i risultati. |
| FE-04 | **Export Excel** | Aggiungere pulsante "Esportazione in Excel" nella pagina dei risultati. Gestire il download del file .xlsx generato dal BE. |

### Modifiche BE

| \# | Modifica | Descrizione |
| --- | --- | --- |
| BE-01 | **Ricerca avanzata** | Implementare l'endpoint per la ricerca avanzata nel Notification Centre. I parametri di input sono: *dataDal* (obbligatorio), *dataAl* (obbligatorio), *serieBUC* (facoltativo), *tipoEvento* (facoltativo), *sed* (facoltativo). Almeno uno dei tre parametri facoltativi deve essere presente. |
| BE-02 | **Lista BUC** | Implementare l'endpoint che restituisce la lista delle Serie BUC disponibili (vedi lista valori — Serie BUC). |
| BE-03 | **Lista Tipo Evento** | Implementare l'endpoint che restituisce la lista dei Tipi Evento disponibili (vedi lista valori — Tipo Evento). |
| BE-04 | **Lista SED** | Implementare l'endpoint che restituisce la lista dei codici SED disponibili (vedi lista valori — SED). |
| BE-05 | **Generazione Excel** | Implementare il servizio di generazione del file .xlsx con i dati risultanti dalla ricerca avanzata. Il file include tutte le colonne della tabella TO-BE. |

---

# Casi d'uso

Lo scopo di questo capitolo è descrivere i percorsi funzionali principali introdotti dalla CR RN:12302155.

---

### UC1 — Ricerca Avanzata nel Notification Centre

**Attore**: Utente JINA autenticato

**Precondizioni**: L'utente ha effettuato l'accesso ed è sulla pagina del Notification Centre.

**Flusso principale**:

1. Il sistema visualizza la tabella delle notifiche con le nuove colonne (Tipo Evento, BUC di origine, Numero BUC, ID, Serie BUC di origine, Tipo, SED, Cognome/Nome, Azioni).
2. L'utente apre la maschera di Ricerca Avanzata.
3. L'utente compila i campi obbligatori: *Periodo Dal* e *Periodo Al*.
4. L'utente seleziona almeno uno tra: *Serie BUC*, *Tipo Evento*, *SED* (selezione singola da List Box).
5. L'utente avvia la ricerca.
6. Il BE esegue la query con i filtri forniti.
7. Il sistema visualizza i risultati filtrati nella tabella.

**Flusso alternativo — Errore di validazione**:

- Se *Periodo Dal* o *Periodo Al* non sono compilati → il sistema mostra un messaggio di errore: *"Il periodo di ricerca (Dal/Al) è obbligatorio"*.
- Se nessun campo tra *Serie BUC*, *Tipo Evento* e *SED* è compilato → il sistema mostra un messaggio di errore: *"Compilare almeno uno tra: Serie BUC, Tipo Evento, SED"*.

---

### UC2 — Export Excel dei risultati

**Attore**: Utente JINA autenticato

**Precondizioni**: UC1 completato — una ricerca avanzata è stata eseguita e i risultati sono visualizzati.

**Flusso principale**:

1. L'utente clicca sul pulsante "Esportazione in Excel".
2. Il FE invia la richiesta al BE con i parametri di ricerca correnti.
3. Il BE genera il file .xlsx con i dati dei risultati.
4. Il sistema avvia il download del file nel browser dell'utente.

---

### UC3 — Navigazione con persistenza dei filtri

**Attore**: Utente JINA autenticato

**Precondizioni**: UC1 completato — una ricerca avanzata è attiva con filtri applicati e risultati visualizzati.

**Flusso principale**:

1. L'utente clicca sull'azione "Visualizza" su una notifica per aprire il caso corrispondente.
2. Il sistema salva nella sessione utente i parametri di ricerca correnti (Periodo Dal/Al, Serie BUC, Tipo Evento, SED).
3. L'utente visualizza il dettaglio del caso.
4. L'utente torna al Notification Centre (azione "back" / navigazione indietro).
5. Il sistema ripristina automaticamente i filtri salvati in sessione e visualizza i risultati precedentemente ottenuti.

---

# Verifiche da effettuare

Lo scopo di questo capitolo è indicare i percorsi di verifica da eseguire al completamento dello sviluppo, sulla base degli scenari di riferimento dell'allegato *"JINA Centro Notifiche — Ricerca Avanzata"*.

---

### VERIFICA 1 — Ricerca per Tipo Evento + SED (DEMO1)

**Parametri di ricerca**:

| Campo | Valore |
| --- | --- |
| Periodo Dal | \[data valorizzata\] |
| Periodo Al | \[data valorizzata\] |
| Serie BUC | *(non valorizzato)* |
| Tipo Evento | A New SED Arrived |
| SED | X009 |

**Esito atteso — Tabella risultati**:

La tabella visualizza solo le notifiche con Tipo Evento = *A New SED Arrived* e SED = *X009*, con tutte le nuove colonne popolate. Esempio di righe attese:

| Tipo Evento | BUC di origine | Numero BUC | ID | Data | Serie BUC di origine | Tipo | SED | Cognome/Nome | Azioni |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| A New SED Arrived | H_BUC_01 | 1731790 | 3e2bb2bcf1c8... | \[data\] | H | È arrivato un nuovo Promemoria | X009 | Massimo Cavallaro | Visualizza |
| A New SED Arrived | R_BUC_07 | 1657980 | c5cc41f83198... | \[data\] | R | È arrivato un nuovo Promemoria | X009 |  | Visualizza |

**Verifica Export**: il file .xlsx scaricato contiene le stesse righe filtrate con le medesime colonne.

---

### VERIFICA 2 — Ricerca per Serie BUC + Tipo Evento senza SED (DEMO2)

**Parametri di ricerca**:

| Campo | Valore |
| --- | --- |
| Periodo Dal | \[data valorizzata\] |
| Periodo Al | \[data valorizzata\] |
| Serie BUC | R_BUC_07 |
| Tipo Evento | A New Case Arrived |
| SED | *(non valorizzato)* |

**Esito atteso — Tabella risultati**:

La tabella visualizza solo le notifiche relative a BUC = *R_BUC_07* con Tipo Evento = *A New Case Arrived*. Poiché il tipo evento è relativo a un Case, la colonna SED riporta lo **starter SED** del caso. Esempio di riga attesa:

| Tipo Evento | BUC di origine | Numero BUC | ID | Data | Serie BUC di origine | Tipo | SED | Cognome/Nome | Azioni |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| A New Case Arrived | R_BUC_07 | 1234 | aabbcc | \[data\] | R | \[label evento\] | R_017 |  | Visualizza |

**Verifica Export**: il file .xlsx scaricato contiene le stesse righe filtrate.

---

### VERIFICA 3 — Validazione obbligatorietà campi

| Caso | Azione | Esito atteso |
| --- | --- | --- |
| 3a | Avviare la ricerca senza compilare nessun campo | Messaggio di errore su Periodo Dal/Al e su almeno un campo opzionale |
| 3b | Compilare Tipo Evento ma non Periodo Dal | Messaggio di errore: Periodo obbligatorio |
| 3c | Compilare Periodo Dal/Al ma nessun campo opzionale | Messaggio di errore: compilare almeno uno tra Serie BUC, Tipo Evento, SED |
| 3d | Compilare tutti i campi obbligatori e almeno un opzionale | Ricerca eseguita correttamente |

---

### VERIFICA 4 — Persistenza dei filtri alla navigazione

**Procedura**:

1. Eseguire una ricerca avanzata con parametri valorizzati (es. Tipo Evento = *A New SED Arrived*).
2. Dai risultati, cliccare su "Visualizza" su una notifica per aprire il caso.
3. Tornare al Notification Centre tramite "back".
4. Verificare che i filtri siano ripristinati e i risultati visualizzati corrispondano a quelli precedenti.

**Esito atteso**: i filtri di ricerca sono automaticamente ripristinati; la tabella mostra gli stessi risultati filtrati precedenti alla navigazione, senza necessità di reinserire i parametri.

---

# References and Related Documents

| \# | Reference or Related Document | Source or Link/Location |
| --- | --- | --- |
| 1 | JINA-CRs RN:12302155 v1.1 — Notification Centre Advanced Search | EESSIGateway / Docmind: jina-crsrn123021551v11 |
| 2 | JINA Centro Notifiche — Ricerca Avanzata (Allegato) | Docmind: jina-centro-notifiche-ricerca-avanzata |
| 3 | JINA2026 UserManual V1.0 | Docmind: jina2026usermanualv10 |
