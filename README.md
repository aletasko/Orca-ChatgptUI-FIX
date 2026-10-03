# Orca ChatUI Send FIX

Pannello Orca per inviare messaggi a un terminale dell'agente con una risposta di accettazione dell'host. Il pannello usa `terminal.sendText` con `enter: true`: il testo viene inviato quando premi **Invia** o **Invio**. **Maiusc+Invio** inserisce una nuova riga. Se l'host rifiuta il messaggio o la conferma manca, il testo rimane nella casella.

Il plugin aggiunge un pannello nella barra laterale. L'API plugin di Orca non permette di intercettare l'Invio della ChatUI nativa o di leggere le sue conversazioni. Questo pannello è quindi una soluzione alternativa utilizzabile finché la ChatUI nativa non viene corretta nel client Orca.

## Installazione

In Orca, apri **Settings → Plugins → Install → Git URL** e inserisci:

`https://github.com/aletasko/Orca-ChatgptUI-FIX.git#main`

Il repository è privato: Git sul computer che esegue il client Orca deve avere accesso al repository. Dopo l'installazione, esamina e abilita i permessi `workspace:read` e `terminal:send`. Apri il pannello **ChatUI Send FIX**, seleziona il terminale e invia il messaggio.

Per aggiornare: aggiorna il plugin dalla schermata Plugins dopo che `main` è stato aggiornato. Il link `#main` segue i nuovi commit; Orca non modifica automaticamente la versione installata a ogni push.

## Limiti

- Il pannello elenca i terminali del worktree selezionato e invia solo a quello scelto.
- L'accettazione significa che il terminale ha ricevuto i tasti; la risposta dell'agente va verificata nella chat o nel terminale.
- All'invio, un `Ctrl+U` sostituisce l'eventuale riga non inviata nel terminale scelto. L'azione avviene solo quando premi **Invia**.
- Il plugin non corregge la ChatUI nativa. La correzione del client va rilasciata da Orca.
