# D&D Realistic Master Framework

Framework aperto e utilizzabile interamente da browser per creare un Dungeon Master IA persistente e realistico per il regolamento revisionato 5e / 5.5e.

## Obiettivi principali

- stato persistente della campagna salvato in un repository GitHub privato;
- dadi generati tramite uno strumento RNG, non scelti linguisticamente dal modello;
- nessuna plot armor e nessuna manipolazione dei risultati;
- NPC, fazioni, quest, scadenze ed eventi del mondo autonomi;
- separazione rigorosa tra conoscenza del DM, degli NPC, del PG e del giocatore;
- cronologia Git per versionamento e rollback dello stato della campagna;
- separazione tra file visibili al giocatore e file interni del DM;
- configurazione di riferimento senza installazioni locali.

## Stato del progetto

**v0.1 pre-alpha.**

Questo repository contiene soltanto il framework riutilizzabile. Le singole campagne devono vivere in repository privati separati creati a partire dai modelli inclusi.

## Struttura

- `regole/` — procedure operative statiche del Dungeon Master IA;
- `modelli/campagna/` — modelli vuoti per lo stato persistente della campagna;
- `modelli/dm/` — modelli vuoti per lo stato interno e segreto del DM;
- `gpt/ISTRUZIONI.md` — modello generico delle Instructions del Custom GPT;
- `gpt/AZIONE_GITHUB_OPENAPI.yaml` — schema dell'Action GitHub;
- `documentazione/` — installazione, architettura, sicurezza e note di rilascio.

## Sicurezza

Non pubblicare mai Personal Access Token GitHub, API key, file `.env`, credenziali, segreti della campagna o dati personali dei giocatori.

Ogni utente dovrebbe creare un **repository privato separato per la propria campagna** e un token GitHub fine-grained limitato esclusivamente a quel repository e ai soli permessi necessari.

## Compatibilità D&D / SRD

Il progetto è pensato per il regolamento revisionato 5e / 5.5e e usa **SRD 5.2.1** come base pubblica di compatibilità.

Non redistribuisce Player's Handbook, Dungeon Master's Guide, Monster Manual o altro contenuto non incluso nell'SRD applicabile.

Consulta `AVVISO.md` e `LICENZA.md`.

## Licenze

Il repository utilizza licenze separate:

- codice e configurazioni tecniche: MIT;
- regole operative, modelli e documentazione: CC BY 4.0.

Consulta `LICENZA.md` per la mappatura dei file.

## Avvio rapido

1. Crea un repository GitHub **privato** per la tua campagna.
2. Copia `modelli/campagna/` in `campaign/`.
3. Copia `modelli/dm/` in `dm/`.
4. Crea un Custom GPT.
5. Carica i nove file presenti in `regole/` come Knowledge.
6. Copia `gpt/ISTRUZIONI.md` nelle Instructions del GPT.
7. Configura un token GitHub fine-grained limitato al repository della campagna.
8. Configura l'Action usando `gpt/AZIONE_GITHUB_OPENAPI.yaml`.
9. Attiva Code Interpreter / Data Analysis.
10. Verifica lettura, scrittura e RNG prima di iniziare la campagna.

La procedura completa è in `documentazione/INSTALLAZIONE.md`.
