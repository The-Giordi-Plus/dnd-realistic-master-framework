# Sicurezza

## Non pubblicare segreti

Non inserire mai in un repository pubblico:

- Personal Access Token GitHub;
- API key;
- segreti OAuth;
- file `.env`;
- credenziali;
- segreti della campagna;
- dati personali dei giocatori.

## Token GitHub consigliato

Per la configurazione di riferimento utilizza un token fine-grained:

- limitato esclusivamente al repository privato della singola campagna;
- permesso `Contents: Read and write`;
- nessun permesso aggiuntivo non necessario.

Il token deve essere inserito esclusivamente nel campo di autenticazione dell'Action del Custom GPT.

## Framework pubblico e campagna privata

Il repository del framework può essere pubblico.

Il repository della campagna reale dovrebbe rimanere privato salvo decisione esplicita del proprietario.

## Segreti del Dungeon Master

I file sotto `dm/` possono contenere informazioni che il giocatore non deve conoscere automaticamente.

Non pubblicare il repository della campagna senza aver verificato attentamente il contenuto di tali file.

## Rotazione delle credenziali

Utilizza una scadenza ragionevole per i token e rigenerali quando necessario.

Se un token viene pubblicato accidentalmente, revocalo immediatamente e creane uno nuovo.
