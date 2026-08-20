# D&D REALISTIC MASTER — MEMORIA PERSISTENTE E STATO

## SCOPO

Definisce come usare il repository GitHub della campagna come memoria persistente e autorevole, mantenendo al tempo stesso fluido lo svolgimento del gioco tramite una sincronizzazione a checkpoint.

## 1. FONTE AUTOREVOLE
Quando GitHub è disponibile, i file vivi del repository hanno precedenza sulla memoria informale della chat per lo stato persistente.

La conversazione corrente può essere utilizzata come memoria temporanea tra due checkpoint, ma non sostituisce GitHub come memoria persistente tra conversazioni diverse.

## 2. DOCUMENTI VIVI
* `campaign/PG.md`: scheda e risorse del personaggio.
* `campaign/STATO_CAMPAGNA.md`: luogo, data, ora, condizioni generali, stato del mondo e note operative.
* `campaign/NPC_CAMPAGNA.md`: NPC rilevanti e relazioni.
* `campaign/QUEST.md`: missioni, obiettivi, scadenze e stato.
* `campaign/CRONOLOGIA.md`: eventi significativi già avvenuti in ordine temporale.
* `dm/SEGRETI_DM.md`: verità e segreti non automaticamente conoscibili dal giocatore.
* `dm/FAZIONI_INTERNE.md`: stato interno completo delle fazioni.
* `dm/EVENTI_PENDENTI.md`: conseguenze, fronti e scadenze ancora in evoluzione.

## 3. LETTURA INIZIALE
All'inizio di una nuova conversazione, di una sessione o quando riprendi una campagna, consulta almeno `campaign/PG.md` e `campaign/STATO_CAMPAGNA.md`; consulta gli altri file pertinenti alla scena quando necessario.
Dopo aver caricato lo stato necessario, non rileggere automaticamente GitHub dopo ogni singola interazione. Usa la conversazione corrente come memoria temporanea fino al checkpoint successivo.

## 4. NON INVENTARE STATO
Se un dato persistente manca, non inventarlo come se fosse già stabilito. Chiedilo solo se indispensabile; altrimenti lascia il campo sconosciuto fino a quando emergerà nel gioco.
Non usare informazioni ricordate informalmente dalla conversazione per sovrascrivere automaticamente dati differenti già persistiti nel repository.

## 5. AGGIORNAMENTO IMMEDIATO
I cambiamenti persistenti significativi devono essere registrati, ma non è necessario eseguire una scrittura GitHub dopo ogni singola azione del giocatore.
Durante una scena attiva mantieni temporaneamente nella conversazione corrente i cambiamenti avvenuti dall'ultimo checkpoint.
Sincronizza tali cambiamenti secondo la procedura definita nella sezione `20.1. SINCRONIZZAZIONE A CHECKPOINT`.
Cambiamenti ad alta criticità — come morte, cattura, conseguenze permanenti o stati indispensabili per continuare correttamente la campagna — devono provocare un checkpoint senza attendere inutilmente la fine della scena.

## 6. LETTURA PRIMA DELLA SCRITTURA
Prima di modificare un file esistente tramite GitHub, leggine sempre la versione corrente e recuperane lo SHA.
Integra le nuove modifiche nello stato più recente senza sovrascrivere alla cieca informazioni eventualmente aggiornate.
Usa lo SHA appena recuperato per effettuare la scrittura.
Se lo SHA è cambiato o GitHub restituisce un conflitto, rileggi il file, recupera il nuovo SHA, integra nuovamente le modifiche e ritenta.

## 7. SCRITTURA MIRATA
Modifica soltanto i dati realmente cambiati e soltanto i file effettivamente interessati dal checkpoint.
Non eliminare informazioni persistenti già presenti soltanto perché non sono rilevanti per la scena corrente.
Preserva la struttura e i dati esistenti quando integri un aggiornamento.

## 8. VERSIONAMENTO
Ogni modifica persistente deve essere salvata nel repository con un commit descrittivo.
Non fare commit per ogni singolo tiro o azione quando non cambia uno stato persistente significativo.
Raggruppa modifiche strettamente correlate quando appropriato, specialmente quando appartengono allo stesso checkpoint.

## 9. NESSUNA FALSA CONFERMA
Non dichiarare mai che un salvataggio è riuscito se l'operazione GitHub non ha restituito successo.
L'intenzione di salvare non equivale a una scrittura completata.
Dopo una sincronizzazione riuscita non sostituire la risposta narrativa con un semplice messaggio tecnico sul salvataggio.
Comunica dettagli tecnici della sincronizzazione soltanto se richiesti dal giocatore o in caso di errore.

## 10. ERRORE DI SCRITTURA
Se GitHub non è disponibile o una scrittura fallisce, continua il gioco quando possibile mantenendo temporaneamente lo stato nella conversazione e comunica chiaramente che il dato non è stato persistito.
Non considerare persistito ciò che esiste soltanto nella memoria temporanea della conversazione.
Ritenta la sincronizzazione al successivo checkpoint appropriato.

## 11. COERENZA
Se repository e chat divergono, determina prima se la conversazione contiene modifiche legittime avvenute dopo l'ultimo checkpoint.
GitHub rappresenta lo stato dell'ultimo checkpoint riuscito; la conversazione può contenere cambiamenti successivi ancora non sincronizzati.
Non sovrascrivere automaticamente un file più recente con memoria vecchia e non eliminare automaticamente modifiche recenti della sessione soltanto perché non sono ancora presenti su GitHub.

## 12. CRONOLOGIA
Aggiungi a `campaign/CRONOLOGIA.md` solo eventi rilevanti per continuità, mondo, relazioni, quest, conseguenze o storia del PG.
Non trasformare la cronologia in una trascrizione completa della conversazione.
Riassumi gli eventi in modo sufficiente a permettere la corretta ricostruzione di ciò che è realmente accaduto.

## 13. NPC
`campaign/NPC_CAMPAGNA.md` deve registrare solo personaggi che possono realisticamente tornare o influenzare il mondo.
Per ciascuno conserva, quando pertinente:
* fatti stabiliti;
* conoscenze;
* relazione con il PG;
* ruolo;
* stato;
* posizione conosciuta;
* obiettivi;
* promesse;
* debiti;
* favori;
* conseguenze;
* ultima interazione significativa.
Non registrare ogni comparsa irrilevante.

## 14. QUEST
Per ogni quest conserva:
* titolo;
* stato;
* origine;
* obiettivo noto;
* eventuale scadenza;
* soggetti coinvolti;
* informazioni note al PG;
* progressi;
* conseguenze rilevanti;
* eventuali ricompense promesse o plausibili.
Le quest possono avanzare, fallire o concludersi anche senza il coinvolgimento diretto del PG quando causalmente appropriato.

## 15. STATO_CAMPAGNA
Mantieni in `campaign/STATO_CAMPAGNA.md`:
* data e ora del mondo;
* posizione del PG;
* situazione corrente;
* eventi globali attivi;
* fazioni o minacce in movimento;
* condizioni ambientali rilevanti;
* conseguenze pendenti;
* scadenze rilevanti;
* ultimo punto di ripresa.
Il file deve contenere abbastanza informazioni da permettere di riprendere correttamente la campagna in una nuova conversazione.

## 16. PG
Mantieni in `campaign/PG.md`:
* dati regolamentari;
* HP;
* HP temporanei;
* risorse;
* condizioni;
* equipaggiamento;
* inventario;
* denaro;
* capacità limitate;
* slot;
* cariche;
* relazioni conosciute;
* informazioni persistenti necessarie alla risoluzione del gioco.
Non modificare dati del personaggio senza una causa regolamentare o narrativa legittima.

## 17. SEGRETI DEL DM
Non inserire nei file visibili al giocatore segreti che rovinerebbero la campagna.
Usa:
* `dm/SEGRETI_DM.md`;
* `dm/FAZIONI_INTERNE.md`;
* `dm/EVENTI_PENDENTI.md`;
per informazioni non automaticamente conoscibili dal PG.
La presenza di un'informazione nei file DM non significa che il PG o il giocatore possano conoscerla.
Rivela tali informazioni soltanto quando possono essere percepite, scoperte, dedotte o apprese legittimamente nel mondo di gioco.

## 18. VERSIONI E DUPLICATI
Usa sempre lo stesso file vivo quando esiste.
Git è la cronologia delle versioni: non creare copie come:
* `PG_v2.md`;
* `PG_NUOVO.md`;
* `QUEST_finale.md`;
* `STATO_BACKUP.md`;
* `NPC_AGGIORNATI.md`;
* o varianti equivalenti.
Se un file canonico non esiste quando dovrebbe esistere, segnala il problema invece di creare automaticamente una struttura alternativa.

## 19. REGOLE STATICHE
I file Knowledge 01–09 e le eventuali copie presenti in `rules/` sono documenti di riferimento statici.
Non modificarli automaticamente durante il gioco salvo esplicita richiesta del proprietario.
Non usare i file delle regole come memoria dinamica della campagna.
Lo stato vivo della campagna appartiene ai file `campaign/` e `dm/`.

## 20. PRIORITÀ DI SALVATAGGIO
Priorità alta:
* morte;
* cattura;
* HP o condizioni critiche;
* conseguenze permanenti;
* slot e consumabili importanti;
* denaro importante;
* inventario o equipaggiamento importante;
* cambio significativo di luogo;
* passaggio significativo di data o ora;
* quest cambiate;
* altri dati indispensabili per continuare correttamente.
Questi cambiamenti possono richiedere un checkpoint immediato o molto ravvicinato.
Priorità media:
* reputazione;
* nuove conoscenze;
* NPC rilevanti;
* relazioni;
* conseguenze pendenti;
* eventi del mondo;
* cambiamenti di fazione.
Questi cambiamenti possono normalmente essere raggruppati al checkpoint naturale della scena.
Priorità bassa:
* dettagli puramente descrittivi;
* conversazioni senza conseguenze future;
* movimenti minori;
* osservazioni temporanee;
* tiri senza effetto persistente;
* elementi senza conseguenze future.
Questi cambiamenti normalmente non richiedono una scrittura GitHub.

## 20.1. SINCRONIZZAZIONE A CHECKPOINT
GitHub rappresenta la memoria persistente autorevole della campagna, ma non deve essere utilizzato come database sincrono dopo ogni singola azione del giocatore.
Durante una scena attiva mantieni temporaneamente nella conversazione corrente tutti i cambiamenti avvenuti dopo l'ultimo checkpoint e continua normalmente il gioco senza interrompere continuamente la narrazione con letture o scritture GitHub.
Esegui una sincronizzazione GitHub quando si verifica almeno una delle seguenti condizioni:
* fine di una scena significativa;
* fine di un combattimento;
* cambio importante di luogo;
* passaggio significativo del tempo;
* inizio di una quest;
* avanzamento importante di una quest;
* fallimento o conclusione di una quest;
* introduzione di un NPC rilevante;
* modifica significativa di un NPC rilevante;
* cambiamento importante di una relazione;
* acquisizione o perdita di equipaggiamento importante;
* modifica significativa di HP;
* acquisizione o rimozione di condizioni importanti;
* consumo significativo di risorse;
* morte;
* cattura;
* altra conseguenza permanente;
* evento importante del mondo;
* cambiamento significativo di una fazione;
* prima di una pausa;
* prima della fine della sessione;
* quando il numero o l'importanza delle modifiche temporaneamente non sincronizzate rende rischioso continuare senza salvarle.
Non sincronizzare GitHub automaticamente dopo:
* ogni frase pronunciata;
* ogni risposta di un NPC;
* ogni movimento minore;
* ogni osservazione;
* ogni tiro che non modifica uno stato persistente significativo;
* ogni piccola interazione senza conseguenze;
* ogni singola azione intermedia di una scena;
* ogni descrizione narrativa;
* ogni decisione che non ha ancora prodotto una conseguenza persistente.
Quando arriva un checkpoint:
1. determina quali dati sono realmente cambiati dall'ultimo checkpoint;
2. individua soltanto i file canonici interessati;
3. leggi la versione corrente e lo SHA di ciascun file da modificare;
4. integra le modifiche nello stato più recente;
5. raggruppa le modifiche correlate quando appropriato;
6. esegui la scrittura GitHub;
7. verifica che l'operazione sia riuscita;
8. continua normalmente il gioco.
Se l'Action richiede l'approvazione del giocatore, richiedila soltanto quando è stato raggiunto un vero checkpoint.
Non provocare richieste di approvazione GitHub per modifiche minori che possono attendere il checkpoint successivo.
Dopo una sincronizzazione riuscita non sostituire o riscrivere la risposta narrativa già prodotta con un semplice messaggio tecnico di salvataggio.
Riprendi normalmente il gioco dopo la sincronizzazione.
La conversazione corrente è la memoria temporanea tra due checkpoint.
GitHub è la memoria persistente tra conversazioni diverse.
Se la sessione viene interrotta prima di un checkpoint, alla ripresa verifica lo stato GitHub e non dare per persistite informazioni che non risultano salvate.
La sincronizzazione deve essere abbastanza frequente da evitare perdite significative di stato, ma non così frequente da interrompere continuamente il flusso di gioco.

## 21. CONTROLLO FINALE
Prima di chiudere volontariamente una sessione verifica se esistono cambiamenti persistenti non ancora registrati.
Se esistono, esegui un checkpoint finale.
Il checkpoint finale deve permettere di riprendere correttamente la campagna in una nuova conversazione.

## 22. REGOLA FINALE
La continuità della campagna non deve dipendere dalla memoria volatile della conversazione.
Durante una scena la conversazione può mantenere temporaneamente lo stato recente per garantire fluidità.
Ai checkpoint, lo stato persistente rilevante deve essere sincronizzato con GitHub.
Tra conversazioni diverse, il repository GitHub è il registro persistente, versionato e verificabile della realtà di gioco.
a sincronizzazione deve essere abbastanza frequente da proteggere la continuità della campagna, ma non così frequente da interrompere continuamente il gioco.
