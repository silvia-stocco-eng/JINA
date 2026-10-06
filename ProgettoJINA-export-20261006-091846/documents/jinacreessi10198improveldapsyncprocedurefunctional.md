---
unique-name: jinacreessi10198improveldapsyncprocedurefunctional
display-name: JINA CR EESSI 10198 Improve LDAP Sync Procedure Functional Analysis v0.2
category: GENERAL
description: Analisi funzionale EESSI 10198 aggiornata con i chiarimenti del cliente su configurazioni da preservare, comportamento atteso, matching LDAP, utenti deleted, logging e coerenza Portal/API.
tags: eng
---

**TGC Engineering Ingegneria Informatica**

*EESSI:10198 -- Miglioramento della procedura di LDAP Sync (Analisi Funzionale)*

**CIG 9623953142**

(CIG 9623953142)

---

Data: 08 September 2026  
Doc. Version: 0.2

---

**Informazioni di Controllo del Documento**

---

**Impostazioni** | **Valore**
--- | ---
**Titolo del documento:** | *EESSI:10198 -- Miglioramento della procedura di LDAP Sync (Analisi Funzionale)*
**Id progetto:** | CIG 9623953142
**Autori del documento:** | Bozza Copilot basata sulla documentazione di progetto
**Responsabile di progetto:** | Barbara Ingrosso (PO)
**Project Manager:** | Milko Anselmi (PM)
**Versione documento:** | 0.2
**Sensibilita':** | Riservato

## **Data:** 08 September 2026

**Approvatori e revisori del documento:**

NOTA: tutti gli approvatori sono obbligatori. Le registrazioni di ciascun approvatore devono essere mantenute. Tutti i revisori presenti nell'elenco sono considerati obbligatori salvo esplicita indicazione contraria.

---

**Nome** | **Ruolo** | **Azione** | **Data**
--- | --- | --- | ---
| | | *<Approva / Revisiona>* | |
| | | *<Approva / Revisiona>* | |
| | | *<Approva / Revisiona>* | |

---

**Storico del documento:**

L'autore del documento e' autorizzato ad apportare le seguenti modifiche senza richiedere una nuova approvazione del documento:

- modifiche editoriali, di formattazione e ortografiche
- chiarimenti

Per richiedere una modifica a questo documento, contattare l'autore o il proprietario del documento.

Le modifiche a questo documento sono riepilogate nella tabella seguente in ordine cronologico inverso (versione piu' recente per prima).

---

**Revisione** | **Data** | **Creato da** | **Breve descrizione delle modifiche**
--- | --- | --- | ---
0.2 | 08/09/2026 | Copilot draft | Aggiornamento dell'analisi con i chiarimenti funzionali ricevuti dal cliente su perimetro, comportamento atteso, logging e coerenza Portal/API
0.1 | 09/06/2026 | Copilot draft | Prima stesura del documento di analisi funzionale

---

**Gestione configurazione: posizione del documento**

L'ultima versione di questo documento controllato e' salvata in: *local workspace /root/.docmind/ProgettoJINA/*

Sommario

[1. Introduzione](#1-introduzione)

[1.1 Panoramica generale](#11-panoramica-generale)

[1.2 Obiettivo del documento](#12-obiettivo-del-documento)

[1.3 Glossario dei termini](#13-glossario-dei-termini)

[1.4 Panoramica della CR](#14-panoramica-della-cr)

[2. Sincronizzazione LDAP in RINA/JINA - AS-IS](#2-sincronizzazione-ldap-in-rinajina---as-is)

[3. Miglioramento della procedura LDAP Sync - TO-BE](#3-miglioramento-della-procedura-ldap-sync---to-be)

[3.1 Riepilogo delle modifiche](#31-riepilogo-delle-modifiche)

[3.2 Chiarimenti funzionali ricevuti](#32-chiarimenti-funzionali-ricevuti)

[3.3 Punti residui da validare](#33-punti-residui-da-validare)

[4. Casi d'uso e criteri di verifica](#4-casi-duso-e-criteri-di-verifica)

[5. Riferimenti e documenti correlati](#5-riferimenti-e-documenti-correlati)

# 1. Introduzione

## 1.1 Panoramica generale

JINA (Join Implementation of National Applications) e' un'applicazione web per la gestione elettronica e lo scambio dei casi di sicurezza sociale tra le istituzioni competenti dei Paesi partecipanti. Nel contesto RINA, IAM (Identity and Access Management) mette a disposizione le funzionalita' di gestione utenti, gruppi e autenticazione, incluse le configurazioni di sincronizzazione basate su LDAP.

## 1.2 Obiettivo del documento

Il presente documento descrive il comportamento attuale (AS-IS) e il comportamento futuro atteso (TO-BE) relativo al requisito **EESSI 10198 - Miglioramento della procedura di LDAP Sync**.

L'obiettivo della richiesta e' eliminare le inefficienze operative generate dall'attuale sincronizzazione LDAP in IAM che, secondo quanto riportato nel CR, comporta la perdita delle configurazioni assegnate agli utenti gia' esistenti nel Portal, in particolare gruppi, memberships e ruoli applicativi, con conseguente necessita' di riconfigurazione manuale dopo ogni sincronizzazione.

Il documento ha finalita' di **analisi funzionale** per il gruppo di sviluppo. A seguito dei chiarimenti ricevuti dal cliente, il presente aggiornamento consolida le principali regole funzionali attese e mantiene aperti solo gli elementi che non risultano ancora confermati o che richiedono ulteriori esempi operativi.

## 1.3 Glossario dei termini

**Termine/Acronimo** | **Definizione**
--- | ---
JINA | Join Implementation of National Applications
RINA | Reference Implementation of National Applications
IAM | Identity and Access Management
LDAP | Lightweight Directory Access Protocol
AD | Active Directory
CR | Change Request
CPI | Case Processing Interface
Tenant | Ambiente logico RINA con impostazioni IAM separate
Membership | Associazione tra utente, gruppo e permessi/visibilita' applicativa

## 1.4 Panoramica della CR

**Numero CR:** EESSI 10198

**Titolo:** Miglioramento della procedura di LDAP Sync

**Priorita':** non esplicitamente indicata nel draft funzionale disponibile

**Reporter:** Portugal (come riportato nel template CR)

**Elementi impattati:** IAM, configurazione LDAP, sincronizzazione utenti e gruppi, gestione dell'assegnazione ruoli, operazioni amministrative sugli utenti esistenti

**Esigenza di business:** a ogni LDAP Sync gli utenti gia' esistenti perdono gruppi e ruoli precedentemente configurati, costringendo gli amministratori a ripristinare manualmente la configurazione. La modifica richiesta ha l'obiettivo di preservare la configurazione esistente e ridurre effort operativo e rischio di errore.

**Chiarimento di perimetro:** la presente CR e' distinta dalla **RN:11753683**, che riguarda l'impossibilita' di cancellare utenti con casi ancora assegnati e la conseguente esigenza di una funzionalita' di bulk case reassignment. **EESSI 10198** riguarda invece la preservazione della configurazione autorizzativa degli utenti gia' esistenti durante la LDAP Sync.

**Nota rilevante del CR sorgente:** lo stesso CR cita anche un use case relativo alla sincronizzazione automatica dei ruoli utente al primo login. Questo aspetto viene riportato come requisito collegato da chiarire in termini di perimetro, poiche' potrebbe rappresentare un'evoluzione funzionale ulteriore rispetto alla richiesta principale di preservazione della configurazione in fase di sincronizzazione.

# 2. Sincronizzazione LDAP in RINA/JINA - AS-IS

Secondo il CR sorgente, gli utenti del RINA Portal vengono creati tramite LDAP Sync in IAM. Ogni volta che deve essere importato un nuovo utente, la sincronizzazione viene eseguita nuovamente; tuttavia, il processo corrente causa la perdita o il reset della configurazione gia' assegnata agli utenti esistenti.

L'impatto di business descritto nel CR e' il seguente:

- gli utenti esistenti devono essere riconfigurati manualmente dopo ogni sincronizzazione;
- gli amministratori di tenant possono dover verificare un numero elevato di utenti;
- il processo e' oneroso e soggetto a errore;
- il problema e' particolarmente critico per i tenant con piu' di cento utenti.

Dalla documentazione RINA disponibile, il comportamento standard della sincronizzazione LDAP puo' essere riassunto come segue:

- IAM consente la configurazione di una connessione LDAP per tenant;
- utenti e gruppi possono essere sincronizzati da LDAP o Active Directory verso RINA;
- mapping gruppi e mapping utenti possono essere configurati nella sezione LDAP Configuration;
- la sincronizzazione e' monodirezionale, dalla sorgente LDAP verso la destinazione RINA/PostgreSQL;
- la documentazione amministrativa standard indica esplicitamente che **roles/memberships are not synchronised from LDAP** e che le memberships possono essere aggiunte successivamente manualmente o tramite CPI.

Questo significa che, nel comportamento standard di prodotto descritto dai manuali, LDAP Sync viene utilizzata principalmente per importare e aggiornare utenti e gruppi, mentre la configurazione autorizzativa non deriva completamente da LDAP.

Sulla base del CR EESSI 10198, l'implementazione attualmente adottata nel contesto target e' comunque percepita come distruttiva per gli utenti gia' configurati, poiche' dopo la sincronizzazione l'amministratore deve ripristinare la configurazione autorizzativa gia' presente prima del sync.

Il processo AS-IS puo' quindi essere descritto come segue:

1. L'amministratore accede a IAM e mantiene la configurazione LDAP del tenant.
2. L'amministratore avvia la sincronizzazione LDAP per importare nuovi utenti e/o aggiornare i dati sincronizzabili.
3. Utenti e gruppi vengono sincronizzati da LDAP verso l'applicazione.
4. Come effetto collaterale descritto nel CR, gli utenti esistenti perdono ruoli e/o configurazioni correlate ai gruppi precedentemente assegnate.
5. L'amministratore ripristina manualmente la configurazione mancante dopo la sincronizzazione.

### Problematiche funzionali osservate nell'AS-IS

- lavoro manuale ripetitivo dopo ogni sincronizzazione;
- elevato rischio di assegnare permessi incompleti o errati;
- riduzione della produttivita' degli amministratori di tenant;
- rischio di disservizi o problemi di visibilita' per gli utenti le cui memberships non vengono ripristinate correttamente.

### Note architetturali

Il CR specifica che non e' esplicitamente richiesta una modifica architetturale lato richiedente. Tuttavia, al fornitore viene demandata la valutazione degli impatti e delle eventuali modifiche necessarie per rendere operativa la soluzione. La richiesta e' quindi funzionale dal punto di vista business, ma puo' richiedere comunque interventi sulla logica di sincronizzazione, sulle regole di persistenza e/o sulla strategia di preservazione di ruoli e memberships.

# 3. Miglioramento della procedura LDAP Sync - TO-BE

Il comportamento target richiesto dal CR EESSI 10198 prevede che l'esecuzione della LDAP Sync non rimuova e non resetti la configurazione gia' assegnata agli utenti che risultano gia' presenti nel sistema prima della sincronizzazione.

La procedura di sincronizzazione deve continuare a supportare l'import di utenti e gruppi provenienti da LDAP/AD, ma deve preservare la configurazione funzionale gia' associata agli utenti esistenti all'interno dell'applicazione.

Sulla base del riscontro ricevuto dal cliente, la regola funzionale attesa e' che, se un utente esiste gia' in JINA/RINA ed e' restituito dalla LDAP Sync, tale utente **non perda alcuna configurazione autorizzativa o di permesso** gia' presente nell'applicazione.

Nel processo target:

1. L'amministratore esegue LDAP Sync per importare o aggiornare dati utente e gruppo.
2. I nuovi utenti recuperati da LDAP vengono creati nell'applicazione secondo le regole di sincronizzazione esistenti.
3. Gli utenti esistenti restano presenti nel sistema con la configurazione autorizzativa precedentemente assegnata.
4. Le eventuali attivita' manuali residue devono riguardare solo i nuovi utenti, ove necessario.
5. Gli utenti esistenti non devono piu' richiedere riconfigurazioni massive dopo la sincronizzazione.

### Principi funzionali target

- **Sincronizzazione non distruttiva per gli utenti esistenti:** la sincronizzazione non deve cancellare la configurazione preesistente degli utenti gia' noti all'applicazione.
- **Preservazione completa della configurazione autorizzativa:** per gli utenti gia' esistenti e restituiti dalla LDAP Sync devono essere preservati ruoli, gruppi, memberships e ogni altra configurazione utente o permesso gia' assegnato.
- **Supporto all'onboarding dei nuovi utenti LDAP:** i nuovi utenti provenienti da LDAP devono continuare a essere importati correttamente.
- **Aggiornabilita' limitata ai dati sincronizzabili/personali:** la sincronizzazione puo' aggiornare i dati anagrafici o personali dell'utente, ma non deve alterare la parte autorizzativa.
- **Continuita' operativa:** il processo deve diventare sostenibile anche per tenant con un numero elevato di utenti.
- **Riduzione dell'effort manuale e degli errori:** l'attivita' amministrativa post-sync deve essere minimizzata.
- **Coerenza Portal/API:** il comportamento applicato dal Portale IAM e dalle eventuali REST API di sincronizzazione deve restare allineato.

### Perimetro della configurazione da preservare

In base al riscontro ricevuto dal cliente, la configurazione da preservare comprende **tutto cio' che e' relativo alla configurazione utente e ai permessi**. Questo include almeno:

- i gruppi associati agli utenti esistenti;
- i ruoli assegnati agli utenti esistenti;
- le memberships o associazioni utente-gruppo;
- le ulteriori configurazioni autorizzative gia' presenti sul profilo utente.

Il criterio funzionale espresso dal cliente e' che, se l'utente gia' esiste in JINA/RINA ed e' restituito dalla LDAP Sync, **non deve perdere alcuna configurazione**.

### Ulteriore use case citato nel CR

Il CR sorgente include un use case secondo cui, al primo login, il sistema dovrebbe collegarsi automaticamente a LDAP, recuperare i ruoli dell'utente e assegnare piu' ruoli se presenti.

Questo requisito appare collegato ma non perfettamente allineato con il problema principale di preservazione delle configurazioni durante LDAP Sync. Inoltre, nel riscontro ricevuto il cliente ha dichiarato di **non riconoscere questo use case** e ha richiesto maggiori dettagli prima di potersi esprimere. Per tale motivo, la presente analisi lo considera un **elemento di perimetro non confermato**:

- se confermato in scope, lo sviluppo dovra' valutare un'ulteriore evoluzione relativa all'attribuzione dei ruoli al primo login;
- se non confermato, il perimetro implementativo restera' limitato alla preservazione della configurazione applicativa esistente durante la sincronizzazione.

## 3.1 Riepilogo delle modifiche

La modifica funzionale richiesta puo' essere riassunta come segue:

- revisione del comportamento della sincronizzazione LDAP in IAM per gli utenti esistenti;
- prevenzione della perdita o del reset di ruoli, gruppi, memberships e piu' in generale delle configurazioni autorizzative gia' configurate sugli utenti presenti prima del sync;
- mantenimento della capacita' standard di importare utenti e gruppi da LDAP/AD;
- utilizzo dei criteri di matching utente LDAP ↔ utente applicativo configurati nel JINA Portal, secondo le specificita' del singolo Paese/tenant;
- mantenimento del comportamento corrente per gli utenti non piu' presenti in LDAP, che devono continuare a essere marcati come deleted;
- aggiornamento consentito ai soli dati personali o sincronizzabili dell'utente, come ad esempio first name, last name, mail e phone;
- disponibilita' di log dettagliati a supporto del troubleshooting;
- garanzia di coerenza funzionale tra il comportamento del Portale IAM e quello delle REST API collegate;
- garanzia che l'intervento amministrativo post-sync sia richiesto solo per i nuovi utenti, ove necessario;
- valutazione separata del requisito relativo alla sincronizzazione automatica dei ruoli al primo login, oppure sua esplicita conferma in scope.

## 3.2 Chiarimenti funzionali ricevuti

Nel corso del confronto con il cliente sono stati chiariti i seguenti elementi funzionali:

1. La preservazione deve riguardare **tutto cio' che e' relativo alla configurazione utente e ai permessi**.
2. Un utente gia' presente in JINA/RINA deve restare **inalterato dal punto di vista autorizzativo** quando viene restituito dalla LDAP Sync.
3. Il criterio di riconciliazione tra utente LDAP e utente applicativo deve usare **quanto configurato sul JINA Portal** in base alle specificita' dell'Active Directory del singolo Paese o tenant.
4. In caso di variazioni lato LDAP per utenti gia' esistenti, la sincronizzazione puo' aggiornare i **dati personali/sincronizzabili** dell'utente, come ad esempio first name, last name, mail e phone, ma deve preservare integralmente la parte autorizzativa.
5. Per gli utenti non piu' presenti nella sorgente LDAP deve essere mantenuto il **comportamento corrente**, ossia la marcatura dell'utente come deleted.
6. Per le esigenze del cliente sono ritenuti sufficienti **log dettagliati** del processo, importanti soprattutto per il troubleshooting.
7. La logica implementata lato IAM/Admin Portal e il comportamento delle eventuali **REST API** devono restare coerenti tra loro, anche se il cliente non utilizza direttamente tali interfacce.

## 3.3 Punti residui da validare

Alla luce dei chiarimenti ricevuti, restano da validare soltanto i seguenti aspetti:

1. Se il requisito di assegnazione automatica dei ruoli al primo login sia effettivamente in scope per questo CR, considerato che il cliente non lo ha riconosciuto e ha chiesto maggiori dettagli.
2. Quale formato e quale livello di dettaglio debbano avere gli esempi concreti richiesti al cliente per la validazione dei casi d'uso.
3. Quali attributi di matching e quali campi sincronizzabili risultino effettivamente configurati nei tenant target, poiche' tale regola dipende dalla configurazione locale del JINA Portal.

# 4. Casi d'uso e criteri di verifica

Lo scopo di questo capitolo e' indicare i percorsi funzionali da verificare per confermare il corretto comportamento richiesto.

## Caso 1 - Preservazione configurazione utente esistente

**Precondizioni:**

- l'utente e' gia' presente in JINA/RINA prima della sincronizzazione;
- all'utente risultano associati almeno un gruppo e/o uno o piu' ruoli applicativi.

**Passi:**

1. L'amministratore accede alla sezione IAM del tenant.
2. L'amministratore esegue la LDAP Sync.
3. Il sistema completa la sincronizzazione.
4. L'amministratore verifica i dati dell'utente gia' presente.

**Risultato atteso:**

- l'utente resta presente nel sistema;
- gruppi, memberships, ruoli e ogni altra configurazione autorizzativa gia' assegnata non vengono persi in conseguenza della sincronizzazione;
- non e' richiesta riconfigurazione manuale dell'utente esistente.

## Caso 2 - Import nuovo utente LDAP

**Precondizioni:**

- in LDAP e' presente un nuovo utente non ancora disponibile in JINA/RINA.

**Passi:**

1. L'amministratore esegue la LDAP Sync.
2. Il sistema importa il nuovo utente secondo la configurazione IAM del tenant.
3. L'amministratore verifica la presenza del nuovo utente in applicazione.

**Risultato atteso:**

- il nuovo utente viene creato correttamente;
- l'import del nuovo utente non produce regressioni sugli utenti gia' esistenti;
- le eventuali configurazioni manuali residue si applicano solo ai nuovi utenti e non agli utenti preesistenti.

## Caso 3 - Sincronizzazione su tenant ad alta numerosita'

**Precondizioni:**

- il tenant contiene un numero elevato di utenti gia' configurati.

**Passi:**

1. L'amministratore esegue la LDAP Sync.
2. Il sistema aggiorna i dati sincronizzabili provenienti da LDAP.
3. L'amministratore esegue verifiche a campione sugli utenti esistenti.

**Risultato atteso:**

- non si verifica una perdita massiva di configurazioni;
- non e' necessario un intervento manuale sistematico post-sync;
- l'operazione e' gestibile in modo sostenibile dal punto di vista operativo.

## Caso 4 - Aggiornamento dei dati personali di un utente esistente

**Precondizioni:**

- l'utente e' gia' presente in JINA/RINA;
- all'utente risultano gia' associati ruoli, gruppi o altre configurazioni autorizzative;
- in LDAP risultano modificati uno o piu' dati personali sincronizzabili dell'utente (ad esempio nome, cognome, mail o telefono).

**Passi:**

1. L'amministratore esegue la LDAP Sync.
2. Il sistema rileva l'utente gia' esistente in base al criterio di matching configurato sul tenant.
3. Il sistema aggiorna i dati personali sincronizzabili provenienti da LDAP.
4. L'amministratore verifica i dati dell'utente e la configurazione autorizzativa associata.

**Risultato atteso:**

- i dati personali sincronizzabili dell'utente risultano aggiornati correttamente;
- ruoli, gruppi, memberships e permessi restano invariati;
- la sincronizzazione non richiede alcuna riconfigurazione autorizzativa manuale.

## Caso 5 - Utente non piu' presente in LDAP

**Precondizioni:**

- l'utente e' gia' presente in JINA/RINA;
- l'utente non viene piu' restituito dalla sorgente LDAP durante la sincronizzazione.

**Passi:**

1. L'amministratore esegue la LDAP Sync.
2. Il sistema completa la sincronizzazione senza ricevere l'utente dalla sorgente LDAP.
3. L'amministratore verifica lo stato dell'utente in applicazione.

**Risultato atteso:**

- viene mantenuto il comportamento corrente dell'applicazione;
- l'utente viene marcato come deleted;
- la gestione degli utenti non piu' presenti in LDAP resta distinta dal requisito di riassegnazione casi oggetto della RN:11753683.

# 5. Riferimenti e documenti correlati

**#** | **Riferimento o documento correlato** | **Sorgente o percorso**
--- | --- | ---
1 | JINA-CRs EESSI 10198 | /root/.docmind/ProgettoJINA/JINA-CRs_EESSI - 10198.md
2 | EESSI - RINA - Identity and Access Management (IAM) - rev02 | /root/.docmind/ProgettoJINA/EESSI - RINA - Identity and Access Management (IAM) - rev02 .md
3 | EESSI-RINA6.2.18(Portal6.2.19)-AdministrationManual | /root/.docmind/ProgettoJINA/EESSI-RINA6.2.18(Portal6.2.19)-AdministrationManual.md
4 | EESSI - RINA - Functional Specs - Administration Portal - rev03 (1) | /root/.docmind/ProgettoJINA/EESSI - RINA - Functional Specs - Administration Portal - rev03 (1).md
5 | EESSI - RINA - Case Processing Interface (CPI) - Reference - rev03 | /root/.docmind/ProgettoJINA/EESSI - RINA - Case Processing Interface (CPI) - Reference - rev03.md
6 | JINA RN 11625596 Notification Case automatically closed cannot be marked as read V1.1 | /root/.docmind/ProgettoJINA/JINA_RN_11625596_Notification Case automatically closed cannot be marked as read_ _ V1.1.md
7 | JINA RN 11367821 JUMP RINA 2021 in S_BUC_12 v4.2 and v4.3 allows CaseOwner to send Reminder (X009) V1.0 | /root/.docmind/ProgettoJINA/JINA_RN_11367821_JUMP RINA 2021 in S_BUC_12 v4.2 and v4.3 allows CaseOwner to send Reminder (X009) _ V1.0 (1).md
8 | JINA-CRs_RN:11753683_V2.0 | /root/.docmind/Stime/JINA-CRs_RN_11753683_V2.0.md
9 | Jira export EESSI-10198 | /root/.docmind/ProgettoJINA/EESSI-10198.doc
10 | Jira export EESSI-9917 | /root/.docmind/ProgettoJINA/EESSI-9917.doc
