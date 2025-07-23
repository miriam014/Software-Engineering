Un progetto non si sviluppa da solo, serve pianificazione, gestione dei rischi per prevenire problemi. (i problemi più difficili da prevenire sono quelli relativi alle persone, il codice si può sempre risolvere)
Fare project management vuol dire dunque **gestire** il progetto:
- definire obiettivi, coordinare persone, risolvere conflitti

 Abbiamo **due stili di project management** che sono alla base dei diversi modelli di processo e come questi si mettono in pratica. 
 1. **Planned-leitend** (pianificato e direttivo)
 Si fa un **piano dettagliato e documentato**, indicando una **responsabile con poteri decisionali** ed è sicuramente più _adatto per progetti grandi, lunghi, dove effettuare cambiamenti può essere costoso._
2. **Agil-selbstorganisierend** (agile e auto-organizzato)
C'è una **pianificazione minima**, in vista del fatto che il progetto e le **idee possono cambiare** facilmente e le decisioni vengono condivise nel team. È adatto a _piccoli team, dove il cliente coinvolto è disponibile a continui meeting._

#### Le 9 aree del project management secondo il PMI
Il **PMI (Project Management Institute)** è un'organizzazione internazionale che si occupa di standard e certificazioni per il project management. Definisce cos'è un progetto, quali sono le fasi e le aree di responsabilità. Il modello più noto è il PMBOK da cui derivano le **9 aree(attività pratiche da gestire per far si che il progetto rispetti il triangolo)**:

- scope -> controlla la **funzionalità** (cosa fa il sistema)
- tempo -> controlla la **durata**
- costi -> controlla i **costi**
- qualità -> garantisce **standard**
- risorse umane,  comunicazione, rischi, integrazione, procurement -> supportano tutto il resto
Certo è che queste sono aree indicative, poi ogni progetto può decidere se ometterne alcune o semplificarle in base alle proprie esigenze.
### Il Triangolo del PM
Alla base del project management ci sono **sempre tre fattori/vincoli in conflitto**, dove l'aumentare uno implica sacrificare un'altro. 
**Per migliorare uno devo sacrificare l'altro. Nessun progetto può massimizzare tutto contemporaneamente** È necessario dunque un equilibrio tra le 3 e il ruolo del project manager è proprio gestire questi conflitti e **capire a cosa dare la priorità rispetto alle richieste del cliente.**
Se si pensa di poter soddisfare tutto si ricade nel problema della marcia della morte.
#### Problema del Todesmarschprojekte
È un esempio molto chiaro e preciso di cosa può succedere: “**Se gestisci male un progetto** fin dall’inizio, non esistono miracoli né eroi. Esistono solo **progetti falliti** e **persone esaurite**.”

Todesmarschprojekte: **progetto marcia della morte** (sin dall'inizio si sa che finirà male, ma si lavora ugualmente senza sosta e nessuno lo dice apertamente). È un progetto in cui le risorse sono la metà di quelle necessarie (tempo, personale, soldi) oppure le richieste sono il doppio. In sintesi è un progetto con **aspettative assurde**. 
Ad esempio se si deve sviluppare tutto in 3 mesi, con poco personale senza eliminare alcuna funzionalità richiesta dall'utente.

**Queste succedono in caso di promesse ingenue da parte dei venditori, ottimismo, pensieri di dover fare nottate, concorrenza eccessiva e un'eccessiva fiducia nella tecnologia.**
Fortunatamente oggi sono più rare queste situazioni grazie ad una maggiore consapevolezza ed organizzazione, ma continuano a capitare casi del genere soprattutto tra giovani.
È importante capire sin dall'inizio su cosa l'utente punta un maggiore focus e decidere di conseguenza cosa sacrificare in anticipo. Ma come capirlo? Facendo una stima dell'effort.

### Stima dell'effort 
Fare una stima nei progetti software è molto difficile perché molto spesso **l'architettura non è chiara fin dall'inizio, i requisiti possono variare e le condizioni possono essere instabili**(team inesperto, tecnologie nuove). **I progetti troppo innovativi o confusi non si possono stimare in modo affidabile.** **Per ottenere una stima più affidabile bisogna utilizzare più tecniche diverse. Queste variano anche in base alla tipologia di approccio che abbiamo.**
#### Tecniche per fare una stima nei progetti agili
1. Stima per **confronto**
	Si fa un _confronto con progetti già fatti_ e si usano come riferimento. Dipende dall'esperienza.
2. Stima da **esperti**
	si chiede agli sviluppatori o ai project manager di stimare secondo la loro esperienza. È pratica e _veloce ma può essere molto soggettiva_.
3. Stima **combinata**
	Fa la media tra le diverse stime. Riduce sicuramente l'errore individuale ma se anche gli altri sono sbagliati, si sbaglia di conseguenza.
4. Stima con **fattori di correzione**
	Si prende un progetto simile e si applicano percentuali di correzione per ogni differenza con il nuovo progetto. Modello **CoCoMo**.
5.  Stima per **scomposizione**
	si divide la richiesta in due casi: i **requisiti**, facendo una stima di ogni funzionalità separata e la **progettazione** facendo una stima dei sottoinsiemi architetturali.
	Si rischia di trascurare l'integrazione o i costi non visibili.
6. Stima con **grandezza sostitutiva**
	Se non so stimare direttamente il tipo, ma so stimare la dimensione del codice.

#### Tecniche per fare una stima nei progetti più pianificati
##### WBS (Work Breakdown Structure)  -  cosa fare?
È una struttura di scomposizione del lavoro, **ci dice cosa bisogna fare**. Significa che **prende l'intero progetto e cerca di comporlo in blocchi gestibili (task)** in modo da avere una panoramica chiara, sapere cosa stimare e poter assegnare ogni parte a qualcuno.

Si procede per livelli, dal livello più generale fino ad arrivare alle specifiche del progetto.
- nel primo livello vediamo il progetto intero ovvero cosa richiede il nostro prodotto. Es. "Sviluppo di un sistema per la gestione di spese familiari".
- nel secondo livello vediamo le fasi principali, andandole a dividere per processo o per funzionalità principali. Es. "modulo utenti, modulo spese, report".
- nel terzo livello vediamo nel dettaglio di ogni funzionalità. Es. "per il modulo utenti bisogna creare un account, login, modifica profilo..."
##### Function Points (FP)    -  quanto dura ogni attività?
È un'unità di misura delle funzionalità fornite all'utente indipendentemente dal linguaggio, dal sistema... **In base a questa unità di misura si risale al tempo necessario per svilupparle.**  È il metodo più formale e oggettivo. 

È in grado si stimare i progetti software basati su dati. Non funziona per sistemi embedded (come dispositivi elettronici), sistemi real-time e videogiochi, robotica... **Richiede esperti certificati** per poterlo applicare e potrebbe essere pesante da introdurrei in piccoli team agili.

**Ogni funzione ha un peso**, che può variare in base alla complessità. Al termine del calcolo non otteniamo i giorni di lavoro che ci vogliono ma una misura oggettiva di quanto ci voglia, che combinata con i progetti passati calcolati con lo stesso metodo è in grado di garantire una stima abbastanza precisa. 
Ad esempio "Se in passato un progetto da 120 FP(punti funzione) lo abbiamo svolto in 3 mesi allora suppongo che uno da 80 FP si può fare in 2"

Ogni tipo di funzione ha un peso in FP ovvero:

|Tipo|Esempio|Peso in FP|
|---|---|---|
|Input esterni|Form per inserire un cliente|3–6|
|Output esterni|Fattura stampabile, report PDF|4–7|
|Query|Cerca clienti → mostra risultati|3–6|
|File logici interni|Tabelle, database|7–15|
|Interfacce esterne|API, connessione a sistemi esterni|5–10|
Se ho 5 input ad esempio moltiplico il peso 4x5volte etc.
Per poter usare i punti funzione però devo necessariamente saper individuare quante e quali funzioni applico al mio progetto, ovvero fare una **scomposizione dei requisiti.**
##### Gantt   -  quando fare ogni attività?
È uno strumento visivo che **ci dice quando e per quanto tempo fare le cose.**
Su un asse orizzontale mettiamo i giorni o le settimane e su quello verticale le attività fornite dalla WBS. 
Ad ogni attività associamo la **durata prevista**, rappresentata, dal loro inizio alla loro fine, da una barra orizzontale e può essere calcolata tramite il Function Point.

Ogni attività viene rappresentata poi da un colore: 
- blu se non sono critiche e
- rosso se sono **Critical Path** (calcolate in automatico come spiegato nel prossimo paragrafo nel caso si usi un software), ovvero quelle attività che non possono ritardare, poiché il loro ritardo implica il ritardo dell'intero progetto.

Ad ogni attività associamo poi delle **risorse**(una o più persone) che se ne dovrebbe occupare, ognuna di queste ha poi una **capacità**, ovvero quanto tempo quella risorsa deve lavorare su quella determinata attività. "100% = 1 persona a tempo pieno".

Esistono dei software che restituiscono e aggiornano automaticamente il diagramma man mano che inseriamo le attività(derivanti da WBS), la durata stimata(in giorni o ore tramite i FP), le risorse assegnate, le dipendenze, i carichi di lavoro e la data di consegna finale. **Microsoft Project**, ma gli stessi concetti sono applicabili anche a  Excel. Questi restituiscono anche i costi totali calcolati come mostrato di seguito.

##### Critical Path   -  cosa non può essere in ritardo?
Il cammino critico è la sequenza di attività all'interno di un progetto che **determina la sua durata complessiva.**  Si chiama critico proprio perché anche se solo una attività è in ritardo, allora l'intero progetto lo è altrettanto.

Le attività fuori dal cammino hanno un certo **margine di ritardo** (**slack time**) che possono raggiungere senza impattare sulla data finale. Se slack = 0 allora è critica.
Lo slack, o anche float, si calcola automaticamente in base alla durata stimata di ogni attività (FP) e la struttura delle dipendenze (chi deve aspettare chi).

| Termine               | Significato                                                   |
| --------------------- | ------------------------------------------------------------- |
| **ES (Early Start)**  | Il primo giorno in cui l’attività può iniziare                |
| **EF (Early Finish)** | ES + Durata(FP)                                               |
| **LS (Late Start)**   | L’ultimo giorno in cui può iniziare **senza ritardare** nulla |
| **LF (Late Finish)**  | LS + Durata(FP)                                               |
| **Slack (o Float)**   | **LS – ES** oppure **LF – EF**                                |

##### Stima dei costi
 Come detto precedentemente i costi non hanno un ruolo principale nel nostro triangolo poiché vengono calcolati e stimati in base al tempo e le risorse.
 tempo x risorse = costi
 È importante solo per decidere il budget con il cliente, confrontare più soluzioni, valutare la fattibilità ma soprattutto scegliere le priorità (triangolo tempo – costi – qualità).

Le tecniche possono essere varie:
	**Stima esperta**: chiedi ad un esperto quanto tempo/lavoro cosa una certa attività. Si basa sull'esperienza passata ed è soggettiva.
	**Confronto con progetti simili**: Serve un repository  storico di vecchi progetti ben documentati.
	**Scomposizione top-dow**: si utilizza la suddivisione del progetto in attività fornita da WBS e si fa una stima di ogni pezzo.
	**Function Point Analysis**: Utilizza il peso di ogni funzione dato da Function Points e li si usano per convertirli in tempo o costi. Es. 100 FP se so che il mio team produce 4 FP al giorno per uomo e che 1 giorno per uomo mi costa 400$ allora farò 25x400=10.000$

Anche i costi vengono calcolati in maniera automatica dal Microsoft Project. Si possono definire anche costi fissi e variabili per risorse o server, licenze etc.

### Gestione del rischio 
Come ragiona un buon project manager per non farsi sorprendere dai problemi. **Il rischio è qualcosa che potrebbe accadere, il problema è qualcosa che è già accaduto.**
Nel processo di Project Management, la gestione del rischio non viene dopo ma accompagna tutte le fasi.

| Fase                        | Esempio                         | Collegamento con il rischio                                         |
| --------------------------- | ------------------------------- | ------------------------------------------------------------------- |
| Pianificazione (WBS, Gantt) | Definizione attività e durata   | Se una persona è sovraccarica o una dipendenza è rigida → rischio   |
| Stima dei costi             | Valutazione ore, costi, risorse | Se il budget è troppo stretto o la produttività è incerta → rischio |
| Esecuzione                  | Il lavoro inizia                | Rischi operativi (assenze, bug, richieste nuove)                    |
| Controllo e adattamento     | Monitoraggio dei tempi          | Ritardi o imprevisti che vanno gestiti                              |
**Quindi il rischio serve per prevenire i problemi, non solo a reagire.** 
	"If you don't attack the risks, the risks will attack you".

|Rischio|Probabilità|Danno|Rischio Totale|
|---|---|---|---|
|“Cliente cambia requisiti”|Alta|Medio|Alto|
Come si calcola? **Rischio = Probabilità × Gravità del danno**

Esistono tre stili per la gestione dei rischi
- **Ottimista** (il peggiore) -> si pensa che non possano esistere errori.
- **Reattivo** -> affronta problemi solo quando succedono.
- **Preventivo** -> bisogna prevedere i problemi e pianificare su come evitarli. base del Risk Management professionale.

#### Come prevenire i problemi
- Identificare i rischi
- valutare i rischi
- capire quali rischi gestire prima
- monitorare regolarmente tutti i rischi sia quelli già trovati che di nuovi **documentarli**
Sicuramente si possono scrivere dei test automatici per evitare bug, o se il fornitore ritarda fare altro etc.
**Una possibile lista potrebbe includere del personale insufficiente o incompetente, tempi o budget fuori le possibilità, funzioni sbagliate, requisiti che cambiano continuamente...**
**Nessun piano va come lo si immagina.**
Attenzione anche alle persone che fanno parte del progetto! [[Personalità e lavoro nei progetti software]]
