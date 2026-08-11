# Installazione — Pre-alpha

La configurazione di riferimento funziona interamente da browser.

## 1. Crea un repository privato per la campagna

Crea su GitHub un nuovo repository privato.

Copia:

- `modelli/campagna/` → `campagna/`
- `modelli/dm/` → `dm/`

Non usare il repository pubblico del framework come repository della tua campagna reale.

## 2. Crea il Custom GPT

Crea un nuovo Custom GPT.

Carica come Knowledge i nove file presenti nella cartella `regole/`.

Apri `gpt/ISTRUZIONI.md`, copia il contenuto nel campo Instructions e sostituisci:

- `TUO_USERNAME_GITHUB`
- `TUO_REPOSITORY_CAMPAGNA`

con i dati del tuo repository privato.

Attiva **Code Interpreter / Data Analysis**.

## 3. Crea il token GitHub

Crea un Personal Access Token fine-grained.

Configurazione consigliata:

- accesso soltanto al repository privato della campagna;
- permesso repository `Contents: Read and write`;
- nessun altro permesso non necessario.

Non inserire mai il token nei file del repository.

## 4. Configura l'autenticazione dell'Action

Nel Custom GPT:

- autenticazione: `Chiave API`;
- tipo: `Bearer`;
- chiave: il token GitHub appena creato.

## 5. Configura lo schema OpenAPI

Copia nel campo Schema il contenuto di:

`gpt/AZIONE_GITHUB_OPENAPI.yaml`

Sostituisci:

- `TUO_USERNAME_GITHUB`
- `TUO_REPOSITORY_CAMPAGNA`

## 6. Test di lettura

Verifica `readCampaignFile` leggendo almeno:

- `campagna/PG.md`
- `campagna/STATO_CAMPAGNA.md`

Entrambi devono essere recuperati dal branch `main`.

## 7. Test di scrittura

Esegui una modifica controllata su un file della campagna.

Verifica:

- lettura dello SHA corrente;
- esecuzione di `writeCampaignFile`;
- creazione di un vero commit GitHub;
- nuovo SHA del file.

Rimuovi eventuali dati inseriti esclusivamente per il test.

## 8. Test del generatore di dadi

Chiedi al GPT di generare più tiri indipendenti tramite Code Interpreter / Data Analysis.

Verifica che venga realmente utilizzato lo strumento e non una sequenza scelta linguisticamente dal modello.

## 9. Controllo finale

Prima di iniziare una campagna reale verifica:

- Knowledge caricati;
- Instructions configurate;
- Action GitHub funzionante;
- repository privato raggiungibile;
- lettura riuscita;
- scrittura riuscita;
- RNG tramite strumento riuscito.

Solo dopo questi test inizializza PG, mondo e campagna.
