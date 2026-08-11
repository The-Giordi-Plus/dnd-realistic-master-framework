# CHATGPT DnD REALISTICO

Framework open source per creare un Dungeon Master IA persistente, imparziale e realistico per D&D 5.5e.

L'obiettivo è superare alcuni limiti tipici delle campagne gestite esclusivamente tramite chatbot: memoria volatile, stato difficile da verificare, dadi potenzialmente scelti dal modello, NPC troppo dipendenti dal protagonista, rischio di metagaming e assenza di versionamento.

D&D Realistic Master usa invece **GitHub come memoria persistente**, **Code Interpreter / Data Analysis come RNG**, regole operative dedicate per imparzialità e causalità, e una separazione rigorosa tra conoscenza del DM, degli NPC, del PG e del giocatore.

---

## Perché esiste

Un normale chatbot può essere un ottimo narratore, ma una campagna lunga richiede molto più della sola narrazione.

Servono:

- continuità verificabile tra sessioni;
- stato persistente del personaggio e del mondo;
- casualità non scelta linguisticamente dal modello;
- NPC e fazioni con obiettivi autonomi;
- conseguenze che continuano a esistere fuori scena;
- separazione tra informazioni note e informazioni segrete;
- possibilità di controllare e ripristinare lo stato della campagna.

Questo framework nasce per fornire proprio questa infrastruttura.

---

## Principi fondamentali

### Memoria persistente su GitHub

Lo stato della campagna vive in un repository GitHub privato separato dal framework.

GitHub diventa la fonte autorevole per:

- scheda e stato del PG;
- HP, condizioni e risorse;
- inventario ed equipaggiamento;
- denaro;
- quest e scadenze;
- NPC e relazioni;
- cronologia;
- eventi del mondo;
- fazioni;
- segreti e conseguenze pendenti.

La cronologia Git permette inoltre di vedere cosa è cambiato nel tempo e, se necessario, effettuare rollback.

### Dadi generati tramite strumento

Quando Code Interpreter / Data Analysis è disponibile, il Dungeon Master lo utilizza come RNG.

Il modello decide **quando tirare** e **quale meccanica applicare**, ma non decide quale risultato ottenere.

I risultati casuali sono vincolanti.

Niente fudge.  
Niente plot armor.  
Niente reroll narrativi.

### Mondo autonomo

Il mondo non esiste soltanto in funzione del PG.

NPC, fazioni, autorità, mercanti, creature e organizzazioni possiedono:

- conoscenze limitate;
- obiettivi;
- risorse;
- relazioni;
- motivazioni;
- priorità proprie.

Quest, minacce, eventi e scadenze possono avanzare anche quando il personaggio non è presente.

### Anti-metagaming

Il framework distingue rigorosamente:

- conoscenza completa del DM;
- conoscenza dei singoli NPC;
- conoscenza del PG;
- conoscenza fuori gioco del giocatore.

Il Dungeon Master non deve rivelare statistiche, segreti, intenzioni, CD, trappole o eventi che il personaggio non può conoscere.

### Nessun bilanciamento artificiale

Il mondo non scala automaticamente con il livello del personaggio.

Possono esistere:

- creature troppo forti;
- luoghi estremamente pericolosi;
- fazioni impossibili da affrontare frontalmente;
- situazioni in cui fuggire è la scelta migliore.

Fallimento, perdita, cattura e morte sono possibili.

---

## Confronto rapido

| Approccio chatbot tradizionale | D&D Realistic Master |
|---|---|
| Memoria principalmente conversazionale | Stato persistente su GitHub |
| Stato difficile da verificare | File Markdown canonici |
| Dadi potenzialmente generati dal modello | RNG tramite Code Interpreter |
| Mondo spesso centrato sul protagonista | Mondo autonomo |
| NPC facilmente onniscienti | Conoscenza limitata per soggetto |
| Conseguenze spesso dimenticate | Persistenza strutturata |
| Nessun versionamento | Cronologia Git e rollback |
| Segreti mescolati allo stato visibile | File separati per stato DM |

---

## Architettura

Il progetto separa tre livelli.

### 1. Regole operative statiche

La cartella:

```text
regole/
```

contiene i nove moduli che definiscono il comportamento del Dungeon Master IA:

```text
01_REGOLE_MASTER.md
02_DADI_E_PROVE.md
03_COMBATTIMENTO.md
04_NPC_SOCIALE.md
05_MONDO_ECONOMIA.md
06_ESPLORAZIONE_VIAGGI.md
07_MAGIA_E_CONOSCENZA.md
08_QUEST_FAZIONI_EVENTI.md
09_MEMORIA_PERSISTENTE.md
```

Questi file vengono caricati nel Custom GPT come **Knowledge**.

### 2. Stato persistente della campagna

Ogni campagna reale utilizza un repository GitHub privato separato.

File canonici:

```text
campagna/
├── PG.md
├── STATO_CAMPAGNA.md
├── NPC_CAMPAGNA.md
├── QUEST.md
└── CRONOLOGIA.md
```

Stato interno del Dungeon Master:

```text
dm/
├── SEGRETI_DM.md
├── FAZIONI_INTERNE.md
└── EVENTI_PENDENTI.md
```

### 3. Strumenti

Il Custom GPT utilizza:

- **GitHub API** per leggere e aggiornare lo stato persistente;
- **Code Interpreter / Data Analysis** per RNG, calcoli e supporto meccanico.

---

## Struttura del repository

```text
CHATGPT DnD REALISTICO/
├── regole/
├── modelli/
│   ├── campagna/
│   └── dm/
├── gpt/
│   ├── ISTRUZIONI.md
│   └── AZIONE_GITHUB_OPENAPI.yaml
├── documentazione/
│   ├── ARCHITETTURA.md
│   ├── INSTALLAZIONE.md
│   ├── SICUREZZA.md
│   └── NOTE_RILASCIO.md
├── AVVISO.md
├── LICENZA.md
├── LICENZA-MIT
├── LICENZA-CC-BY-4.0.md
└── LEGGIMI.md
```

---

## Requisiti

Per utilizzare la configurazione di riferimento servono:

- un account GitHub;
- un repository GitHub privato per la campagna;
- accesso alla creazione di un Custom GPT;
- supporto alle Custom Actions;
- Code Interpreter / Data Analysis abilitato;
- un GitHub fine-grained Personal Access Token limitato al repository della campagna.

Non è necessario installare Git, VS Code o altri strumenti sul PC se si utilizza GitHub Codespaces o l'editor web.

---

## Avvio rapido

### 1. Crea il repository della campagna

Crea un nuovo repository GitHub **privato**.

Copia:

```text
modelli/campagna/ → campagna/
modelli/dm/       → dm/
```

### 2. Crea il Custom GPT

Carica i nove file presenti in:

```text
regole/
```

come Knowledge.

### 3. Inserisci le Instructions

Copia:

```text
gpt/ISTRUZIONI.md
```

nelle Instructions del Custom GPT.

Sostituisci:

```text
TUO_USERNAME_GITHUB
TUO_REPOSITORY_CAMPAGNA
```

con i dati del repository privato della tua campagna.

### 4. Attiva Code Interpreter

Abilita:

```text
Code Interpreter / Data Analysis
```

Questa capacità viene utilizzata anche come RNG.

### 5. Crea il token GitHub

Crea un fine-grained Personal Access Token:

- limitato esclusivamente al repository della campagna;
- permesso `Contents: Read and write`;
- nessun permesso aggiuntivo non necessario.

### 6. Configura l'Action GitHub

Usa:

```text
gpt/AZIONE_GITHUB_OPENAPI.yaml
```

come schema OpenAPI.

Configura l'autenticazione come:

```text
API Key → Bearer
```

e inserisci il token GitHub nel campo segreto.

### 7. Testa la lettura

Verifica che il GPT riesca a leggere:

```text
campagna/PG.md
campagna/STATO_CAMPAGNA.md
```

### 8. Testa la scrittura

Esegui una modifica controllata e verifica che GitHub produca realmente:

- nuovo SHA del file;
- commit;
- contenuto aggiornato.

### 9. Testa il RNG

Chiedi al GPT di generare più tiri di dado usando Code Interpreter / Data Analysis e verifica che lo strumento venga realmente eseguito.

### 10. Inizia la campagna

Solo dopo aver verificato lettura, scrittura e RNG inizializza PG, ambientazione e stato del mondo.

La procedura completa è disponibile in:

```text
documentazione/INSTALLAZIONE.md
```

---

## Sicurezza

Non pubblicare mai:

- Personal Access Token GitHub;
- API key;
- OAuth secret;
- file `.env`;
- credenziali;
- segreti del DM;
- dati personali dei giocatori.

Il repository del framework può essere pubblico.

Il repository della campagna dovrebbe invece rimanere privato salvo scelta esplicita del proprietario.

Consulta:

```text
documentazione/SICUREZZA.md
```

---

## Compatibilità D&D / SRD

Il framework è progettato per il regolamento revisionato **5e / 5.5e** e utilizza **SRD 5.2.1** come base pubblica di compatibilità.

Il progetto non redistribuisce:

- Player's Handbook;
- Dungeon Master's Guide;
- Monster Manual;
- Forgotten Realms;
- altro materiale Dungeons & Dragons non incluso nella licenza SRD applicabile.

Gli utenti possono naturalmente utilizzare i propri manuali legalmente acquisiti come riferimento aggiuntivo.

Consulta:

```text
AVVISO.md
```

---

## Licenze

Il progetto utilizza una struttura di licenze separata.

**MIT**

Per:

- configurazioni tecniche;
- schema OpenAPI;
- eventuale codice e script.

**Creative Commons Attribution 4.0 International**

Per:

- regole operative;
- modelli;
- documentazione;
- Instructions;
- contenuti testuali del framework.

Consulta:

```text
LICENZA.md
```

---

## Stato del progetto

**v0.1 — Pre-alpha**

La versione attuale è destinata a:

- test tecnici;
- installazioni pilota;
- revisione delle procedure;
- miglioramento della documentazione;
- validazione della persistenza su campagne reali.

Il progetto non è ancora considerato stabile.

---

## Obiettivi futuri

Tra gli sviluppi possibili:

- procedura di installazione ancora più automatizzata;
- GitHub App / OAuth al posto dei Personal Access Token manuali;
- configurazione più semplice per il GPT Store;
- test automatici dello stato della campagna;
- template multipli per diversi stili di gioco;
- supporto a più campagne;
- strumenti di audit della coerenza;
- release versionate e installabili.

---

## Contribuire

Il progetto è in fase iniziale.

Segnalazioni di bug, problemi nella documentazione, casi limite e proposte di miglioramento sono benvenuti tramite GitHub Issues.

Prima di proporre modifiche alle regole operative, considera che l'obiettivo principale del framework è mantenere:

- imparzialità;
- causalità;
- persistenza;
- autonomia del mondo;
- separazione delle conoscenze;
- casualità verificabile.

---

## Nota

D&D Realistic Master Framework è un progetto indipendente e non è sponsorizzato, approvato o affiliato a Wizards of the Coast.
