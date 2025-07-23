Bisogna imparare a conoscere le forme del riutilizzo, i vantaggi e svantaggi e soprattutto perché i "pattern" (modelli) sono esempi perfetti di riutilizzo.
L'ingegneria del software ci insegna che la conoscenza si struttura nel tempo e tutte le cose che abbiamo imparato ci serviranno per poterle riutilizzare o comunque essere più consapevoli di tutti i rischi e problemi che possiamo incontrare. 

**Riutilizzare qualcosa di noto può aumentare la qualità, migliorare la produttività e ridurre il rischio.** 
Tutto può essere riutilizzato ma serve equilibrio, usare un modulo standard ti fa risparmiare tempo ma se ho bisogno di qualcosa di specifico rischio di perdere flessibilità.

Riusare non significa solo evitare la ripetizione.  Significa **apprendere dall’esperienza passata**, **fare tesoro del lavoro già fatto** e **costruire sulle spalle dei giganti**.
Ogni forma di riuso ci fa risparmiare tempo e riduce il rischio di errori, ma **richiede organizzazione, consapevolezza e adattamento.**

**Il riutilizzo non riguarda solo il codice, ma è una strategia applicabile a qualsiasi artefatto del software.**
- riutilizzo dei requisiti 
- riutilizzo delle soluzioni architetturali
- riutilizzo delle soluzioni di progettazione
- riutilizzo del codice
- riutilizzo dei processi/metodi
### Rischi del riutilizzo 
- **Rischio di qualità**
  Potrei pensare di riutilizzare ad esempio una libreria o un tool già fatto in un altro progetto, ma magari contiene bug nascosti, non è documentata o è troppo ottimale rispetto al mio progetto minimale, il che lo andrebbe ad appesantire.
- **Rischio di inadeguatezza**
  Considerare se ciò che sto riutilizzando copre tutti i tuoi requisiti. Magari manca qualcosa, e riadattarla forza il progetto iniziale.
- **Rischio del fornitore**
  Se ti basi su software di terzi potresti trovarti in difficoltà se il fornitore cambia rotta (sviluppa funzionalità che non ti servono), o smette di aggiornare il prodotto. 
- **Perdita di flessibilità**
  Se usi componenti esterni sei legato alle decisioni altrui e se qualcosa non va non puoi correggere o modificare da solo.

Presi tutti questi rischi uno potrebbe pensare che i rischi sono maggiori rispetto al guadagno, ma in realtà **la scelta è individuale e si basa su tanti fattori**, come il tempo disponibile, il budget, l'importanza del controllo...
	- Se decido di **Comprare e riutilizzare** una componente già fatta perdo meno tempo a sviluppare e correggere bug (si da per scontato che la componente sia corretta), ma **rischio la qualità, minore controllo...**
	  Scrivere un codice riutilizzabile costa molto di più (ma ti salva tempo dopo), perché richiede una maggiore pulizia, più test, più documentazione, repository comuni e standard per gestire le versioni.
	  Molti non riutilizzano proprio per questo motivo, oltre al fatto che pensano che scrivendo da soli il proprio codice lo "comprendono" meglio.
	- Se decido di **Ispirarmi ma svilupparla da solo** sicuramente riesco ad adattarla meglio ai miei requisiti e sono certo della qualità del mio programma, ma allo stesso tempo **ho molto più lavoro, più tempo e magari errori miei.**

### Imparare a riutilizzare
Nel tempo **l'ingegneria del software si è evoluta non tanto da diventare zero, ma da accumulare soluzioni riutilizzabili** al punto tale da ridurre dell'oltre il 25% l'anno il tempo di sviluppare determinati programmi.
Non è necessario "inventare" ogni volta soluzioni nuove, conviene piuttosto basarsi su cose già scritte ed esperienze consolidate. In questo modo in teoria andiamo a **ridurre il rischio** **se riesco a riutilizzare qualcosa di affidabile**.
Fino agli anni 90' il riutilizzo era inteso solo come riutilizzo del codice, poi con la nascita del **[[Design Pattern]]** il riutilizzo è stato applicato anche ai requisiti, al design, all'architettura. 
Un **Pattern** è una coppia/problema che si può riutilizzare in molti contesti diversi, non ci dice cosa fare, ma ci da una forma di pensiero.

#### Pattern ricorrenti
Tutti i giorni utilizziamo senza pensarci dei pattern ricorrenti, concetti, semplicissimi ma potenti che stanno alla base della comprensione del design:
1. **Astrazione** --> ignorare i dettagli inutili
   fondamentale per ridurre la complessità e migliorarne la leggibilità.
2. **Strutturazione** --> rendere qualcosa di complesso più comprensibile, attribuendo ruoli espliciti alle sue parti.
   se divido un sistema in blocchi sarà più facile capirlo, modificarlo, estenderlo. 
3. **Modularizzazione** --> divide il software in parti indipendenti, ciascuna con una responsabilità ben definita. Ti permette di modificare un modulo senza toccare gli altri, testarlo da solo.
4. **Località** --> le modifiche dovrebbero rimanere localizzate. Ovvero cambiando qualcosa in una parte del codice, questo non deve creare effetti a catena su altre parti.
5. **Consistenza** --> le parti simili devono essere trattate in modo simile.
6. **Adeguatezza** --> tutto deve essere adattato allo scopo. "Non posso costruire un missile per portare una lettera".

La riusabilità è il principio che racchiude tutti gli altri. **Se applico tutti questi principi allora sto costruendo un software che può essere riutilizzato da chiunque.**

#### Anti-pattern
Gli anti-pattern sono soluzioni cattive che si presentano ripetutamente nella pratica, poiché sono molto diffusi e all'inizio possono sembrare delle buone idee. 
Esempi pratici:
- **Analysis Paralysis** --> analizzare all'infinito senza mai partire
- **Death by Planning** --> passare mesi a pianificare senza sapere se quei piani funzioneranno
- **Reinvent the Wheel** --> ignorare soluzioni esistenti facendo tutto da soli, spesso peggio
- **Golden Hammer** --> usare sempre la stessa soluzione, anche quando non è adatta
- **Dead End** --> modificare troppo un componente esterno al punto tale da non poterlo più aggiornare
- **Bleeding Edge** --> usare tecnologie troppo nuove non ancora stabili
- **Dumm Halten** --> isolare i programmatori dagli utenti rischia di non far capire loro cosa è importante sviluppare
- **Design by Committee** --> troppe persone che vogliono decidere l'architettura con opinioni diverse e nessuna guida