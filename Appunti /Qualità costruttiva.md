È quella parte della qualità che si costruisce **durante lo sviluppo**, progettando bene processi, regole e ambienti di lavoro, in modo da **prevenire** gli errori invece che cercarli dopo.

>La qualità costruttiva lavora sia per migliorare la qualità interna che esterna, si divide dunque in **gestione del processo** (secondo cui avere un buon processo, ovvero un buon modo di produrre il software, permette di conseguenza un buon prodotto finale) **gestione del progetto**(singolo software)[[Project Management]].

La qualità costruttiva **non si ottiene solo con strumenti**, ma anche con:
- **Formazione**
- **Cultura aziendale**
- **Collaborazione**
- **Responsabilità condivisa**

Il processo va **monitorato e migliorato continuamente**, anche grazie a metriche, analisi dei rischi, e comunicazione efficace.
Ci sono due approcci per gestire la qualità costruttiva
- **Tradizionale.   (Waterfall)**
  garantisce la qualità tramite il controllo. Si avranno dunque ruoli ben definiti, poco spazio a cambiamenti, documentazione formale. Sia andrà in ordine: analisi → design → implementazione → test
- **Agile.   (Scrum, XP)** 
  garantisce la qualità tramite la collaborazione.
  Si ha una comunicazione continua, team autogestiti con cambiamenti accettati.
  
### Strumenti per la qualità costruttiva
Si utilizzano **Framework e modelli** per garantire che il processo di sviluppo sia di qualità.

**CMMI** (Capability Maturity Model Integration) 
È un **modello a 5 livelli** di maturità del processo software. Si parte dal primo livello più "caotico" fino al livello 5 con "ottimizzazione continua". 
Ci insegna che **la qualità non è solo tecnica ma anche organizzazione del lavoro**, che nel primo livello anche un buon programmatore farà fatica, mentre nell'ultimo anche team normali ottengono grandi risultati.
Rende il lavoro **prevedibile**, aiuta a capire cosa migliorare e **migliora l'organizzazione**, ma allo stesso tempo bisogna fare attenzione e **utilizzarlo con prudenza, perché potrebbe diventare una macchina burocratica che sopprime la creatività**.

Nel primo livello tutto dipende dalle singole persone, non c'è una documentazione o un processo definito.
Nel secondo iniziamo ad fissare degli obiettivi, scadenze e responsabilità.
Nel terzo (primo livello "industriale" ) tutti i team seguono lo stesso modello di sviluppo. 
Nel quarto si raccolgono dati sui tempi, difetti e qualità, facendo addirittura previsioni con numeri. 
Nel quinto l'azienda analizza continuamente i propri dati e i team collaborano tra loro. 

**ISO 9000** 
È lo **standard internazionale** per la gestione della qualità. È un insieme di standard internazionali che definiscono come si dovrebbe organizzare un'azienda (qualsiasi non solo in informatica).
Focalizzato su documentazione, processi controllati e miglioramento continuo.
**È focalizzata sulle regole dell'organizzazione non sul prodotto**, **dice come organizzarsi e non come programmare o testare** 

Se un'azienda segue questo standard, un'ente valuta i processi e può fornire una certificazione ISO 9001 valida per 3 anni. Ogni anno ci sono però controlli per mantenere il certificato.

**TQM** (Total Quality Management)
È una **filosofia** di gestione aziendale non solo uno standard organizzativo dove **per ottenere la qualità bisogna dare delle responsabilità a tutti** (_non solo nel progetto software ma nell'intera azienda_). Giappone.

Applicato poi nel mondo del software, dove la qualità è indicata da un codice leggibile, ben testato e documentato, dove **già nel momento della scrittura viene pensato per chi verrà dopo**.
Non otteniamo alcun certificato o livelli da seguire, ma solo un concetto filosofico di vivere il lavoro.


# Modelli di Processo del software
I modelli di processo **descrivono come organizzare e pianificare tutte le fasi di lavoro e sviluppo di un software**. Non sono solo teoria ma sono **strategie pratiche** che ci dicono quali fasi seguire, in che ordine:
- quando analizzare i requisiti, quando progettare, quando programmare, come testare, e come gestire i cambiamenti.
**SONO LO SCHELETRO SU CUI APPLICHI LA QUALITà**

Ogni modello viene analizzato secondo domande come: 
Quando funziona bene? Quali sono i suoi limiti? È adatto a progetti piccoli, grandi..? È adatto a sviluppi interni, su commessa, o su prodotto?

**Cos'è un processo?**
È una **sequenza di attività strutturate** con ruoli precisi, fasi ordinate e obiettivi chiari. Permette di non saltare alcun passaggio e sapere bene cosa si sta facendo. 
Ad esempio ottenuto un compito farò in ordine 1.analizzo i requisiti, 2.progetto il sistema, 3.programmo, 4.testo, 5.consegno.

È fatto di **attività**(progettare, testare..), **ruoli**(sviluppatore, tester..), **artefatti**(documenti, codice, UML, test case..).


### Modelli tradizionali
#### Modello a cascata (Waterfall)
È il più classico e rigido. **Si percorrono le fasi in ordine senza tornare più indietro**
Le fasi sono:
1. Analisi
2. progettazione dettagliata
3. Implementazione
4. integrazione
5. Validazione (test finale)
6. Rilascio

	**Non è molto funzionale** perché ogni fase comunica solo tramite documenti, se nessuno li legge fallisce. In oltre il personale cambia tra le fasi quindi si perde il contesto e se non si ha ben chiaro cosa si deve fare è un problema. Per funzionare **bisognerebbe avere le idee chiare dal principio senza più cambiarle** ma è molto difficile.

Piano piano riparare i limiti della Waterfall nascono altri modelli, il più completo è quello iterativo a spirale.
#### Modello a V
È una versione più moderna del waterfall, sviluppata su incarico del governo tedesco, ha lo scopo di creare un processo preciso adattabile e controllabile soprattutto in ambito pubblico e aziendale.

**Perché si chiama Modello a V?**
La parte sinistra della V rappresenta la **definizione del sistema**(analisi, progettazione...)
La punta della V è l'**implementazione**
La parte destra rappresenta la **verifica e validazione**

**Ogni fase di sinistra ha un corrispondente test a destra**. Questo **collega il progettare e il testare**, ed è una delle forze del modello.

**È molto grande e dettagliato, ci sono 32 ruoli, 89 attività e 97 artefatti.** 
È flessibile perché è possibile selezionare solo i "moduli" di progetto adatti al tuo progetto, di cui 4 obbligatori: 
1. Gestione del progetto
2. Gestione della qualità
3. Gestione della configurazione
4. Gestione dei problemi/cambiamenti
È centrato sul prodotto dunque ogni artefatto passa da: “pianificato” → “in lavorazione” → “proposto” → “completato”.

	Quindi, se da una parte è molto vantaggioso da utilizzare per progetti molto grandi e complessi, dove ogni dettaglio deve essere formalizzato, per progetti piccoli può diventare uno svantaggio perché è molto pesante da gestire, non è immediato poiché c'è bisogno di formazione per utilizzarlo. 

#### Modelli iterativi (Spiral...)
È pensato per i _progetti complessi e ad alto rischio_. 
In ogni iterazione si fa quello che serve di più per ridurre il rischio principale in quel momento. **Si ci concentra su un rischio specifico diverso ogni volta(ad ogni iterazione) e lo si affronta tramite test, simulazioni e discussioni**

Si chiama spirale perché ogni giro della spirale è un'**iterazione che segue quattro fasi**:
1. **Pianificare** (determinare obiettivi, alternative, vincoli)
2. **Analizzare il rischio** (identificare i problemi, stimare gli impatti)
3. **Sviluppare e testare** una soluzione provvisoria
4. **Valutare i risultati** con i clienti e **decidere se continuare**.
Per poi ritornare alla fase 1 se tutto va bene con il cliente.

	Nonostante sia molto flessibile, poiché si adatta ad ogni situazione, e permette una gestione consapevole del rischio, è sconsigliato per i piccoli progetti perché è troppo pesante e richiede grande esperienza nel saper riconoscere i rischi reali. Adatto a progetti a rischio

### Modelli agili (Scrum, XP...)
Un modello agile è un modo di organizzare lo sviluppo software **basato su interazioni frequenti con il cliente, sviluppo per piccoli passi adattamento continuo e feedback rapido**. Meno formalismo e meno paura del cambiamento.
**L'obiettivo infatti è reagire rapidamente ai cambiamenti piuttosto che seguire un piano rigido fissato dall'inizio**.

In questi modelli **non si pianificano tutti i dettagli dall’inizio**, ma si danno solo **obiettivi generali**.  
Poi si pianifica di volta in volta.

Questo è l’approccio delle **metodologie agili**:
- obiettivi piccoli e frequenti
- feedback rapido
- comunicazione continua faccia a faccia
- adattabilità ai cambiamenti
- breve documentazione
- team autogestiti

	Viene utilizzato per progetti piccoli dove i requisiti non sono ancora chiari e l'ambiente come tempi e budget è in continuo cambiamento. È da evitare se il progetto è molto grande e quindi c'è bisogno di una rigorosa tracciabilità della documentazione oltre che responsabilità suddivise tra i gruppi.

#### Scrum
È un framework agile con **cicli brevi** (**Sprint** della durata di **1-4 settimane**) e **regole chiare**.
Non descrive come programmare, ma **come lavorare insieme in team**. **Non funziona in team passivi o poco coinvolti.**

**- Sprint Planning ->**  All'inizio dello **Sprint** il team _prende una lista di tutte le funzionalità richieste_ e si pianifica il lavoro. 
**- Daily Scrum  ->**     Ogni giorno si hanno delle **daily scrum**, ovvero delle riunioni di massimo 15 minuti ogni giorno in cui si parla di cosa si è fatto il giorno prima, cosa farò oggi e se ho avuto dei problemi.  
**- Sprint Review  ->**   _Si realizzano le funzionalità fino ad ottenere un incremento funzionante e testato del software._ Alla fine dello Sprint il prodotto è potenzialmente rilasciabile e lo si mostra al cliente.
**- Retrospective  ->**   Infine si la retrospective part dove si riflette su come è andata e come si può migliorare nel prossimo sprint.
#### eXtreme programming (XP)
A differenza dello Scrum, qui i**l focus è sullo sviluppo del codice** e non sulla gestione del progetto. Si ha un **relase** ogni **(1-2 settimane)** e **i test fungono un ruolo fondamentale**. **Il cliente** poi non incontra il team a scadenza fissa (come ad esempio al termine di ogni scrum), ma **è sempre presente.** 
Tutto ruota attorno al team e al customer. 

- Tutto il codice viene scritto **da due programmatori insieme**, su un solo computer. Uno scrive, l’altro osserva e suggerisce → poi si scambiano
- **Si scrivono i test prima del codice**
- Si **rilascia** una versione funzionante ogni 1-2 settimane

	Proprio per questo NON va usato quando il cliente non è disponibile in modo continuo, quando si hanno team distribuiti dove non si possono scrivere test automatici.
	
	**È sempre preferibile utilizzare i modelli agili perché è impossibile nella realtà non avere imprevisti.**
	I modelli agili infatti tengono conto dell'incertezza, sfruttano il feedback come motore di progresso e limitano i danni quando qualcosa cambia. Soprattutto per gli imprevisti dati dalle personalità umane, vedremo in seguito come anche una comunicazione agile si adatti meglio alle relazioni sociali all'interno di un progetto. [[Personalità e lavoro nei progetti software]]