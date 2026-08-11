# D&D REALISTIC MASTER — MEMORIA PERSISTENTE E STATO

> Nota del framework pubblico: progettato per il regolamento revisionato 5e / 5.5e e per un utilizzo compatibile con SRD 5.2.1. Questo file definisce procedure operative per il DM IA e non sostituisce i regolamenti ufficiali.

## SCOPO
Definisce come usare il repository GitHub della campagna come memoria persistente e autorevole.

## 1. FONTE AUTOREVOLE
Quando GitHub è disponibile, i file vivi del repository hanno precedenza sulla memoria informale della chat per lo stato persistente.

## 2. DOCUMENTI VIVI
- `campagna/PG.md`: scheda e risorse del personaggio.
- `campagna/STATO_CAMPAGNA.md`: luogo, data, ora, condizioni generali, stato del mondo e note operative.
- `campagna/NPC_CAMPAGNA.md`: NPC rilevanti e relazioni.
- `campagna/QUEST.md`: missioni, obiettivi, scadenze e stato.
- `campagna/CRONOLOGIA.md`: eventi significativi già avvenuti in ordine temporale.
- `dm/SEGRETI_DM.md`: verità e segreti non automaticamente conoscibili dal giocatore.
- `dm/FAZIONI_INTERNE.md`: stato interno completo delle fazioni.
- `dm/EVENTI_PENDENTI.md`: conseguenze, fronti e scadenze ancora in evoluzione.

## 3. LETTURA INIZIALE
All'inizio di una sessione o quando riprendi una campagna, consulta almeno `campagna/PG.md` e `campagna/STATO_CAMPAGNA.md`; consulta gli altri file pertinenti alla scena.

## 4. NON INVENTARE STATO
Se un dato persistente manca, non inventarlo come se fosse già stabilito. Chiedilo solo se indispensabile; altrimenti lascia il campo sconosciuto fino a quando emergerà nel gioco.

## 5. AGGIORNAMENTO IMMEDIATO
Dopo cambiamenti significativi aggiorna il file interessato senza attendere la fine della sessione: HP, condizioni, risorse, inventario, denaro, slot, equipaggiamento, luogo, tempo, quest, NPC, morte o altri cambiamenti persistenti.

## 6. LETTURA PRIMA DELLA SCRITTURA
Quando il valore corrente è necessario per evitare conflitti, leggi il file prima di modificarlo.

## 7. SCRITTURA MIRATA
Modifica soltanto i dati realmente cambiati. Non riscrivere interi file se una modifica mirata è sufficiente.

## 8. VERSIONAMENTO
Ogni modifica persistente deve essere salvata nel repository con un commit descrittivo. Non fare commit per ogni singolo tiro; raggruppa modifiche strettamente correlate quando appropriato.

## 9. NESSUNA FALSA CONFERMA
Non dichiarare mai che un salvataggio è riuscito se l'operazione GitHub non ha restituito successo.

## 10. ERRORE DI SCRITTURA
Se GitHub non è disponibile o una scrittura fallisce, continua il gioco mantenendo temporaneamente lo stato nella conversazione e comunica chiaramente che il dato non è stato persistito.

## 11. COERENZA
Se repository e chat divergono, verifica quale dato è più recente. Non sovrascrivere automaticamente un file più recente con memoria vecchia.

## 12. CRONOLOGIA
Aggiungi a `campagna/CRONOLOGIA.md` solo eventi rilevanti per continuità, mondo, relazioni, quest, conseguenze o storia del PG.

## 13. NPC
`campagna/NPC_CAMPAGNA.md` deve registrare solo personaggi che possono realisticamente tornare o influenzare il mondo. Per ciascuno conserva fatti, conoscenze e relazione rilevanti.

## 14. QUEST
Per ogni quest conserva: titolo, stato, origine, obiettivo noto, eventuale scadenza, soggetti coinvolti, informazioni note e conseguenze rilevanti.

## 15. STATO_CAMPAGNA
Mantieni: data/ora del mondo, posizione del PG, situazione corrente, eventi globali attivi, fazioni o minacce in movimento, condizioni ambientali rilevanti e ultimo punto di ripresa.

## 16. PG
Mantieni dati regolamentari, HP, risorse, condizioni, equipaggiamento, inventario, denaro, capacità limitate e informazioni necessarie alla risoluzione del gioco.

## 17. SEGRETI DEL DM
Non inserire nei file visibili al giocatore segreti che rovinerebbero la campagna. Usa `dm/SEGRETI_DM.md`, `dm/FAZIONI_INTERNE.md` e `dm/EVENTI_PENDENTI.md` per informazioni non automaticamente conoscibili dal PG.

## 18. VERSIONI E DUPLICATI
Usa sempre lo stesso file vivo quando esiste. Git è la cronologia delle versioni: non creare copie tipo `PG_v2.md`, `QUEST_finale.md` o simili.

## 19. REGOLE STATICHE
`rules/01`–`rules/09` sono documenti di riferimento. Non modificarli durante il gioco salvo esplicita richiesta del proprietario.

## 20. PRIORITÀ DI SALVATAGGIO
Priorità alta: HP, morte, condizioni, slot, consumabili, denaro importante, inventario, luogo, data/ora, quest cambiate.
Priorità media: reputazione, nuove conoscenze, NPC, conseguenze pendenti.
Priorità bassa: dettagli puramente descrittivi senza effetto futuro.

## 21. CONTROLLO FINALE
Prima di chiudere una sessione verifica se esistono cambiamenti persistenti non ancora registrati e salvali.

## 22. REGOLA FINALE
La continuità della campagna non deve dipendere dalla memoria volatile della conversazione. Il repository GitHub è il registro persistente, versionato e verificabile della realtà di gioco.