Un requisito è una condizione necessaria a un utente o sistema per risolvere un problema o raggiungere un obiettivo. **È qualcosa che il sistema deve fare** e deve essere espresso in modo chiaro, comprensibile e verificabile. 
**Se i requisiti sono sbagliati, il sistema sarà inutile, anche se il sistema funziona perfettamente.**
Se non riesci a descriverlo chiaramente, allora il requisito non è chiaro.
## Requisiti funzionali Vs non funzionali
- **Requisiti funzionali** --> descrivono **Cosa fa il sistema**
  → casi d’uso + tabelle + logica
  "Il medico può creare una ricetta"
- **Requisiti non funzionali** --> descrivono **Come deve comportarsi**
  → scenari qualitativi
  "Il sistema deve essere funzionante il 99,99% del tempo"
## Come si raccolgono i requisiti

| Fasi               | Cosa si fa                                                          | Tecniche principali                                                     |
| ------------------ | ------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| 1.**Elicitazione** | Si **raccolgono** le esigenze da stakeholder e utenti               | Interviste, osservazioni, scenari, workshop, ecc.                       |
| 2.**Analisi**      | Si **capisce, struttura, chiarisce** quello che è stato raccolto    | Ordinamento carte, modelli, gerarchie di obiettivi, conflitti, priorità |
| 3.**Specifica**    | Si **scrivono i requisiti in modo chiaro** e preciso                | Casi d’uso testuali, requisiti formali, diagrammi UML                   |
| 4.**Validazione**  | Si **controlla con gli stakeholder** se tutto è corretto e completo | Prototipi, walkthrough, simulazioni, checklist, test di accettazione    |

**Ogni analisi dei requisiti deve saper rispondere a 4 domande fondamentali all'interno della documentazione:**
	 **Chi** ha interesse nel sistema, **Perché** lo vogliono? **Cosa** deve fare? Quali **vincoli** dobbiamo rispettare?

**I requisiti NON sono solo l'elenco delle funzioni disponibili.**
Ci sono molti problemi che girano intorno alla raccolta dei requisiti, poiché **talvolta questi possono essere ambigui, nascosti, dati per scontati, o possiamo incontrare clienti che non sanno cosa vogliono o cambiano continuamente idea.** Devono essere chiari, verificabili, rilevanti e tracciabili.

Per evitare qualsiasi tipo di problematica **è necessario saper fare chiarezza**, attraverso interviste, questionari, prototipi, scenari d'uso (raccontano in maniera narrativa come l'utente interagisce con il sistema osservandolo) e documentazione. **Si usano più tecniche insieme.**

Es:
	"Il sistema deve essere intuitivo e facile da usare" NON è un buon requisito, troppo vago.
	"L'85% degli utenti deve riuscire a completare l'operazione in meno di 1 minuto" questa è migliore

### Tecniche per scoprire i requisiti
- **Introspezione**
  L'ingegnere del software **riflette da solo su cosa potrebbe servire**. Nonostante sia una pratica semplicissima e spesso utilizzata inconsciamente, **rischia di proiettare i nostri pensieri sugli utenti.**
- **Osservazione partecipante**
  L'osservatore partecipa attivamente alla realtà che vuole studiare. **Trascorre tempo reale con gli utenti imparando dall'interno come funziona il loro lavoro**. Rileva dei dettagli invisibili, ma richiede molto tempo oltre che focus sull'obiettivo.
- **Interviste**
  Interviste semi strutturate con **domande a risposta aperta** possono raccogliere molte informazioni qualitative, opinioni e motivazioni, ma allo stesso tempo sono difficili da analizzare e non rilevano comportamenti automatici o abitudini.
- **Questionari**
  **Mandare domande scritte a molte persone**. È economico ma si rischia di perdere contesto, oltre che ottenere spesso risposte ambigue e troppo semplici. Non spiegano il perché dietro le risposte.
- **Tecniche di elicitazione di gruppo**
  Come **gruppi di discussione**. Si riesce ad avere una maggiore interazione tra le persone e di conseguenza nascono più punti di vista, ma serve un moderatore esperto.
- **Usare il feedback degli utenti**
  Tramite forum, interviste, dati di uso reali. Rappresenta il mondo reale ma c'è il rischio di fraintendere le richieste, oltre che la possibilità di incontrare clienti poco esperti che danno suggerimenti inutili. 
- **Sviluppo iterativo (Agile)**
  Si costruisce una prima versione semplice, si testa con l'utente, si impara e si adatta. Per poi ripetere.
- **Ordinamento delle carte**
  Si scrivono concetti su carte, poi l'esperto le raggruppa e spiega. Ottimo per comprendere le strutture mentali dell'esperto e tirare fuori la conoscenza. Non mostra come funziona davvero un sistema però.
- **Gerarchie di obiettivi**
  **Rappresentare perché il sistema viene costruito.** Si parte degli obiettivi principali e li si approfondisce. Può diventare complesso vago e superficiale, ma è ideale per progetti con molti interessi diversi.
- **Scenari**
  È una sequenza di azioni che rappresentano una **singola interazione** **tra uno o più attori e il sistema**. È un esempio lineare e specifico di comportamento, privo di varianti o gestioni di errore, che si concentra su ciò che accade dall’esterno del sistema, senza descrivere la logica interna.
  Possono essere positivi (il comportamento desiderato) e negativi (ciò che non deve accadere).
  Utile perché gli utenti li capiscono facilmente e sono alla base dei casi d'uso UML.

## Come si rappresentano i requisiti funzionali già scoperti
Dopo aver raccolto i requisiti con tante tecniche diverse, possiamo utilizzare altrettante tecniche diverse per rappresentarle, scelte in base alle nostre necessità. 
Ogni metodo ha un ruolo diverso. Abbiamo scenari dettagliati, diagrammi UML, tabelle, glossari, notazioni informali e formali, oltre che i casi d'uso. 

**Casi d'Uso**
Non è un requisito funzionale ma un metodo per descriverli.
Un caso d'uso è una **descrizione testuale di sequenze di azioni(più scenari)** che il sistema compie, ovvero del **comportamento** atteso di un sistema a seguito di un'interazione con un utente o un altro attore esterno. 
Ci interessa **COSA fa e non come.** È una visione funzionale e non tecnica.

Serve per descrivere e **verificare la comprensione dei i requisiti attesi dall'utente** per un'analisi iniziale, per questo deve essere semplice e comprensibile.
Poi valida l'architettura e verifica il sistema.

Include gli attori, le condizioni, gli obiettivi e più scenari con possibilità di estensioni (alternative, ed errori che rappresentano altri percorsi dentro lo stesso caso d'uso).

### Principi per la scrittura di buoni casi d’uso.
**"visione del prodotto"**: Cosa rende ottimo un caso d’uso al **termine della sua realizzazione**
	1. chiarire gli obiettivi dell'attore e **non citare come funziona il sistema internamente** ("Effettuare un pagamento" e non "Aggiorna database transazioni")
	2. verificare se la sequenza degli scenari è corretta, inserendo solo ciò che accade direttamente tra sistema e attore senza aggiungere dettagli tecnici
	3. verificare che il flusso sia scorrevole e gestire bene anche le alternative

 **"visione del processo"**: Come si scrive effettivamente un buon caso d’uso? 
	1. bisogna **definire prima un attore principale e il suo obiettivo** tramite un linguaggio semplice e non tecnico e solo poi si passa allo scenario principale etc.
	2. bisogna evitare strutture tecniche o pseudo-codice poiché l**e frasi devono essere capite anche da persone non tecniche come il cliente.** 
	3. prende in considerazioni **eventuali varianti ed errori**
	4. bisogna strutturare il tutto partendo dal punto di vista dell'utente di come questo interagisce con il sistema per evitare passaggi inutili per la comunicazione
	.
	Come si scrive un caso d'uso
	1 **Attore principale + obiettivo**  → Chiarisce chi fa cosa, e perché.
	2 **Scenario principale**  → Cosa succede se tutto va bene
	3 **Scenari alternativi**  → Varianti, problemi, eccezioni
	4 **Espansioni**  → Come si gestiscono quelle varianti

### Diagramma dei casi d'uso UML
Un diagramma dei casi d'uso è una **rappresentazione grafica delle varie relazioni tra gli** **attori e i casi d'uso**, senza descriverne i dettagli dell'interazione.
Mentre il caso d'uso abbiamo detto che è un testo che descrive in dettaglio l'interazione tra l'**attore e il sistema**.

Vantaggi: 
	essendo un grafico è più intuitivo capire le varie funzionalità e gli attori coinvolti.
Svantaggi:
	mostrando solo attori, casi e relazioni non descrive poi il comportamento del sistema. Di conseguenza **se non è accompagnato dai casi d'uso testuali è insufficiente per l'analisi dei requisiti.**

#### Elementi di un diagramma dei casi d'uso
1.  **Attore**
   È un'entità esterna al sistema che interagisce con esso per raggiungere un obiettivo. Non è per forza una persona fisica ma una un **ruolo che qualcuno o qualcosa svolge rispetto al sistema**. Nei diagrammi viene rappresentato con la figura dell'omino.

Il nome dell'attore **identifica un ruolo funzionale, non una persona specifica**. Infatti, se un cliente riceve solo un'email automatica, non fa nulla con il sistema dunque non è attore.
   Es:
	_Caso d'uso:_ "Acquisto prodotto"
	_→ Attore principale:_ acquirente (obiettivo: acquistare)
	_Caso d'uso_: "Registra dati in un gestionale"
	_→ Attore_ principale: impiegato 

2.  **System Boundary** ovvero un rettangolo che racchiude tutti i casi d'uso del sistema per distinguerli da ciò che è esterno al sistema. 

3. Relazione **<< include >>** indica che un caso d'uso contiene **sempre** un altro caso d'uso come parte del suo flusso principale. é simile ad una chiamata a funzione nel codice.
		Es: "effettua ordine" include --> "seleziona metodo di pagamento".

4. relazione **<< extend >>** che mostra varianti e scenari esterni al flusso principale. Come funzionalità opzionali o condizionali seguite **solo in determinati casi**.
		Es: "Visualizza cronologia ordine" <-- estende "visualizza dettagli ordine" (attenzione alla freccia è messa apposta al contrario)
		qui visualizza dettagli ordine viene aperto solo se l'attore vuole visualizzare la cronologia.

5. **Generalizzazione** rappresenta ereditarietà tra attori o casi d'uso, si usa per specializzare ruoli o funzionalità.

# Esempio progetto personale
_**a) Scrivi un caso d’uso basato su una delle tue specifiche dell’esercizio 4-2. 
Scegline uno non banale, cioè: il suo scenario di successo dovrebbe comprendere più di tre passaggi e almeno una estensione**._

| Use Case                       | Start a Pomodoro Session<br>History: Created 15/05/2025 - Author: [hv]                                                                                                                                                                                                                                                                                                                          |
| ------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Description                    | The user starts a timed Pomodoro session to perform focused work. A session usually last 25 min and may be linked to a task. The timer runs until completion and alerts the user when the session ends.<br>Sources: [Pomodoro Technique - Cirillo 2006]                                                                                                                                         |
| Actors                         | User(primary)<br>Application Timer Module<br>Notification System                                                                                                                                                                                                                                                                                                                                |
| Assumptions<br>(preconditions) | The system is already running. <br>The timer is not already active.<br>Session timing and notification mechanisms are reliable.                                                                                                                                                                                                                                                                 |
| Steps<br>(man scen)            | 1. User opens the Pomodoro app.<br>2. The system displays the timer interface and available tasks list.<br>3. User optionally selects a task.<br>4. User presses the "Start" button.<br>5. Timer countdown is shown on screen starts with the defined     duration(25 min).<br>6. At the end of the session, when the timer reaches zero, the system notifies the user with sound and/or popup. |
| Variations <br>(extensions)    | #3: No task selected -> The session starts without a linked task.<br>#4: Timer fails to start due to internal error -> System shows error and allows retry.<br>#5: Notifications are muted -> Only a visual notification is shown.                                                                                                                                                              |
| Issues                         | What happens if the user misses the notification at the end of the Pomodoro session?Should the timer automatically start the next phase  or wait explicit user confirmation?                                                                                                                                                                                                                    |

  