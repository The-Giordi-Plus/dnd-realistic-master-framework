# Architettura

Il framework separa tre responsabilità.

## 1. Regole operative statiche

I file in `regole/` definiscono il comportamento permanente del Dungeon Master IA e vengono caricati nel Custom GPT come Knowledge.

## 2. Stato dinamico della campagna

Lo stato vivo viene salvato in un repository GitHub privato separato.

File canonici della campagna:

- `campagna/PG.md`
- `campagna/STATO_CAMPAGNA.md`
- `campagna/NPC_CAMPAGNA.md`
- `campagna/QUEST.md`
- `campagna/CRONOLOGIA.md`

File interni del DM:

- `dm/SEGRETI_DM.md`
- `dm/FAZIONI_INTERNE.md`
- `dm/EVENTI_PENDENTI.md`

La cronologia Git fornisce versionamento e possibilità di rollback. La memoria della chat non viene mai considerata l'unica fonte autorevole dello stato persistente.

## 3. Casualità e strumenti

Quando disponibile, Code Interpreter / Data Analysis viene utilizzato per generare i risultati casuali dei dadi.

Il modello decide quando è necessario un tiro e quali regole applicare; lo strumento RNG determina il risultato.

## Flusso di una sessione

1. Il GPT legge `PG.md` e `STATO_CAMPAGNA.md`.
2. Consulta gli altri file soltanto quando pertinenti.
3. Risolve il gioco applicando Instructions, regole, stato persistente e RNG.
4. Quando cambia uno stato persistente, legge il file e lo SHA correnti.
5. Aggiorna il file tramite GitHub API.
6. GitHub registra la modifica in un commit.

## Principio fondamentale

Il repository privato della campagna rappresenta la memoria persistente verificabile; il repository pubblico del framework contiene soltanto motore, modelli e documentazione.
