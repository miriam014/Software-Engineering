Serve per **esprimere vincoli** (regole logiche) **all'interno dei modelli UML**, **definendo precondizioni, postcondizioni e invarianti**. Utilizzato nella fase di design. [[Design pattern]]]
Ad esempio in UML posso sempre esprimere le regole tra elementi solo tramite le frecce, mentre grazie a OCL possiamo anche rappresentare condizioni come : "_Un torneo non può avere due match sovrapposti_"  o "_Un giocatore deve essere registrato prima di partecipare_"...

**Utile non solo per avere un'idea più chiara del nostro sistema, ma anche per trovare errori presenti già nei modelli UML.**
In Java è possibile simulare il comportamento di OCL con Javadoc (con tag tipo @pre, @post) oppure con assert standard.

### Regole
##### Invariant 
Un invariante è una condizione che **deve essere SEMPRE vera** per un oggetto di una classe, **dopo ogni operazione pubblica** 

Ad esempio: ogni torneo deve avere un numero massimo di giocatori maggiore di zero

	context Tournament inv:
		maxNumPlayers > 0
##### Precondition
Una precondizione è **una regola che deve essere vera PRIMA di eseguire un metodo.**
Ad esempio: prima di accettare un giocatore, verifica che non sia già stato accettato

	context Tournament::acceptPlayer(p) pre:
		not isPlayerAccepted(p)
##### Postcondition
Una postcondizione è una regola che **deve essere vera DOPO** che un metodo è stato eseguito.

Ad esempio: Dopo aver accettato il giocatore, deve **risultare accettato** nel sistema.

	context Tournament::acceptPlayer(p) post:
		isPlayerAccepted(p)

### Operatori e Quantificatori
Per riferirci al valore di un attributo PRIMA che il metodo venga eseguito utilizziamo l'**operatore @pre** idem per gli altri. Ad esempio, il numero dei giocatori prima di accettare il nuovo giocatore sarà ripreso con  getNumPlayers@pre.  **Si utilizza solo per confrontare il valore di qualcosa PRIMA e DOPO l'esecuzione**

Il quantificatore **forALL** dice che **tutti gli elementi** devono rispettare una certa condizione. 
Ad esempio: *tutti i match devono iniziare dopo l'inizio del torneo e finire prima della fine*, verrà rappresentata con:

	context Tournament inv:: 
	matches->forAll ( m | m.start.after(self.start) and m.and.before(self.end))

Il quantificatore **exists** dice che **almeno un elemento** deve soddisfare una condizione.
Ad esempio: *almeno un match deve iniziare il giorno stesso dell'inizio del torneo*

	context Tournament inv:
		matches->exists ( m | m.start.equals(self.start))

### Esercizi
##### a) Riscrivi i vincoli forniti in OCL in linguaggio naturale
- context task inv c1: score>0 
  Ogni attività deve avere sempre punteggio maggiore di 0

- context Student inv c2: solution->size() = exam.tasks->size()
  ogni studente deve aver consegnato tante soluzioni quante le task presenti nell'esame

- context exam inv c3:
	`participant->forAll (t |`
		`t.passed implies t.solutions->exists (l |`
			`l.points > 0 and l.task.exam = self`
		`)`
	`)`
	per ogni partecipante all'esame si vuole che per poter passare l'esame, il numero di soluzioni mandate devono essere almeno >0 e ottenere punti >0 e essere riferimento alle dell'esame stesso e non un altro


##### b) Scrivere OCL corretto
- In ogni esame c'è almeno un task con 1 punto
	`context Esam inv :` 
		`self.task->exist ( t | t.point = 1)`

- Un post-esame non può avere un altro post-esame
	 `context Esam inv:` 
		`self.postExamin->isEmpty() or` 
		`self.postExamin. postExamin->isEmpty()` 

- Dopo che un esame è stato completato, lo stato deve passare da "attivo" "completato"
	`context Esam post:`
		`status = "completato" and status@pre = "attivo"`