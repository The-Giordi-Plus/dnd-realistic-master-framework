````md
# Installazione — Pre-alpha

La configurazione di riferimento funziona interamente da browser. Non è necessario installare Git o VS Code sul PC se si utilizzano GitHub e, facoltativamente, GitHub Codespaces.

## Requisiti

Prima di iniziare servono:

- un account GitHub;
- accesso alla creazione di un Custom GPT;
- supporto alle Custom Actions;
- Code Interpreter / Data Analysis disponibile nel Custom GPT;
- questo repository pubblico del framework.

## 1. Crea un repository privato per la campagna

Crea su GitHub un nuovo repository **privato**.

Esempio:

`mia-campagna-dnd`

Non usare il repository pubblico del framework come repository della campagna reale.

Nel nuovo repository crea questa struttura:

```text
campagna/
dm/
````

Copia:

```text
modelli/campagna/ → campagna/
modelli/dm/       → dm/
```

Alla fine il repository privato deve contenere almeno:

```text
campagna/
├── PG.md
├── STATO_CAMPAGNA.md
├── NPC_CAMPAGNA.md
├── QUEST.md
└── CRONOLOGIA.md

dm/
├── SEGRETI_DM.md
├── FAZIONI_INTERNE.md
└── EVENTI_PENDENTI.md
```

Esegui un commit e verifica che i file siano presenti nel branch `main`.

## 2. Crea il Custom GPT

Crea un nuovo Custom GPT.

Nel campo Knowledge carica i nove file presenti nella cartella:

```text
regole/
```

Carica:

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

Apri:

```text
gpt/ISTRUZIONI.md
```

e copia il contenuto nel campo Instructions del Custom GPT.

Sostituisci:

```text
TUO_USERNAME_GITHUB
TUO_REPOSITORY_CAMPAGNA
```

con i dati reali del repository privato.

Esempio:

```text
TUO_USERNAME_GITHUB
→ mario-rossi

TUO_REPOSITORY_CAMPAGNA
→ mia-campagna-dnd
```

Attiva:

```text
Code Interpreter / Data Analysis
```

## 3. Crea il token GitHub

Su GitHub vai in:

```text
Settings
→ Developer settings
→ Personal access tokens
→ Fine-grained tokens
→ Generate new token
```

Configurazione consigliata:

```text
Resource owner:
il tuo account GitHub

Repository access:
Only select repositories

Repository:
il repository privato della campagna
```

In `Repository permissions` imposta:

```text
Contents → Read and write
```

Non concedere permessi aggiuntivi non necessari.

È consigliata una scadenza del token.

Genera il token e copialo subito.

**Non inserire mai il token nei file del repository e non pubblicarlo.**

## 4. Configura l'autenticazione dell'Action

Nel Custom GPT apri:

```text
Configura
→ Azioni
→ Crea nuova azione
```

Nella sezione Autenticazione imposta:

```text
Tipo:
Chiave API

Tipo autenticazione:
Bearer
```

Nel campo della chiave inserisci il Personal Access Token GitHub.

Il token deve rimanere soltanto nel campo segreto dell'Action.

## 5. Configura lo schema OpenAPI

Apri:

```text
gpt/AZIONE_GITHUB_OPENAPI.yaml
```

Sostituisci:

```text
TUO_USERNAME_GITHUB
TUO_REPOSITORY_CAMPAGNA
```

con i dati reali del repository privato.

Copia poi l'intero contenuto nel campo Schema della Custom Action.

Al termine devono risultare disponibili almeno queste due operazioni:

```text
readCampaignFile
writeCampaignFile
```

## 6. Test di lettura

Prima di modificare qualunque file, verifica soltanto la lettura.

Prompt consigliato:

```text
Leggi campagna/PG.md e campagna/STATO_CAMPAGNA.md dal branch main usando readCampaignFile.
Non modificare nulla.
Dimmi soltanto se entrambi sono stati letti correttamente.
```

Entrambi i file devono essere recuperati dal branch `main`.

Se ricevi `404 Not Found`, controlla:

* nome utente GitHub;
* nome repository;
* branch `main`;
* percorso del file;
* repository selezionato nel fine-grained token;
* permesso `Contents: Read and write`;
* token configurato correttamente come Bearer.

## 7. Test di scrittura

Esegui una modifica controllata e reversibile.

Prima il GPT deve:

1. leggere il file;
2. ottenere lo SHA corrente;
3. modificare il contenuto;
4. usare `writeCampaignFile`;
5. ricevere conferma positiva da GitHub.

Verifica su GitHub:

* nuovo commit;
* nuovo SHA del file;
* contenuto effettivamente aggiornato.

Rimuovi poi eventuali dati inseriti esclusivamente per il test.

Non considerare il test riuscito soltanto perché il GPT afferma di aver salvato: deve esistere realmente il commit GitHub.

## 8. Test del generatore di dadi

Prompt consigliato:

```text
Esegui 20 tiri indipendenti di d20 usando Code Interpreter / Data Analysis come RNG.
Non scegliere linguisticamente i risultati.
Mostrami i risultati nell'ordine generato e la somma totale.
Non modificare alcun file GitHub.
```

Verifica che Code Interpreter / Data Analysis venga realmente utilizzato.

## 9. Test della memoria persistente

Chiudi la conversazione di test e aprine una nuova con lo stesso Custom GPT.

Chiedi:

```text
Leggi campagna/PG.md e campagna/STATO_CAMPAGNA.md e dimmi qual è lo stato persistente corrente della campagna.
```

Il GPT deve recuperare i dati dal repository e non affidarsi alla memoria della conversazione precedente.

## 10. Controllo finale

Prima di iniziare una campagna reale verifica:

* Knowledge caricati;
* Instructions configurate;
* Code Interpreter / Data Analysis attivo;
* Action GitHub configurata;
* token limitato al repository corretto;
* `readCampaignFile` funzionante;
* `writeCampaignFile` funzionante;
* commit GitHub realmente creati;
* RNG tramite strumento funzionante;
* ripresa dello stato da una nuova conversazione riuscita.

Solo dopo questi test inizializza PG, ambientazione e campagna.

## Sicurezza

Non pubblicare mai:

* Personal Access Token;
* API key;
* file `.env`;
* credenziali;
* repository privato della campagna se contiene segreti del DM;
* dati personali non necessari.

Per ulteriori dettagli consulta:

```text
documentazione/SICUREZZA.md
```

````

Poi salva e fai:

```bash
git add documentazione/INSTALLAZIONE.md
git commit -m "docs: espande guida di installazione"
git push
````
