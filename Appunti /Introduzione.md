Il **Software** è un insieme di programmi o dati, e documenti di accompagnamento necessari o utili per il loro uso. Più tecnicamente (IEEE 1983) sono programmi informatici, procedure regole e documentazione relativi al funzionamento di un sistema informatico. **Non è solo codice.** 

l'**Ingegneria del software** è la disciplina che si occupa di fornire e usare in modo sistematico metodi e strumenti per la produzione e l’applicazione di software. 
**Il compito dell'ingegneria del software è analizzare costi e benefici, capire cosa deve fare il sistema (requisiti), capire come deve essere strutturato (architettura), realizzare effettivamente il software, convalidarlo verificando che funzioni e gestire l'intero progetto coordinando persone, tempi e attività.**
  Uno sviluppo software si considera in genere riuscito se (impossibile ottenerli tutti):
- i costi sono bassi,
- il tempo necessario al completamento è breve,
- la qualità del software è alta
- il software è grande e ha molte funzionalità.
#### **Durata, Funzionalità e Qualità**  
Nei progetti software la qualità spesso viene suddivisa in **Funzionalità(quante cose fa il programma) e Qualità(come le fa quindi se sono robuste, affidabili...), poi c'è la Durata(Tempo)**, mentre il Costo invece dipende proporzionalmente al Tempo, quindi **Tempo e Costi sono la stessa cosa.**

Non si può migliorare tutto contemporaneamente:  
Se voglio più qualità ho bisogno necessariamente di più tempo o più risorse, dunque più costi e più lavoro.  
Se voglio meno tempo dovrò rinunciare a qualche funzionalità o accettare una qualità più bassa.  
Allo stesso modo se voglio abbassare i costi devo diminuire il personale e quindi rallentare il o decidere di sacrificare la qualità.  
**Per migliorare uno devo sacrificare l'altro. Nessun progetto può massimizzare tutto contemporaneamente**
**Se il software è scadente fa danno a tutti**, il cliente perde soldi, l'utente smette di usarlo e il team perde motivazione.

**I due mondi**
- **Mondo dei problemi** --> prodotto, requisiti, progettazione e processo
- **Mondo delle soluzioni** --> tecniche di automazione, riuso e metodologiche dei requisiti, progettazione qualità e gestione

### Tacoma Narrows
Un caso molto importante analizzato è quello del **Tacoma Narrows**, un ponte sospeso che doveva coprire una distanza molto grande tra i due punti. L'ingegnere capo e l'esperto esterno di questo progetto avevano gestito già altri progetti molto importanti come il Golden Gate.
Nonostante i **parametri** di progettazione come i piloni, i cavi di sospensione, i materiali etc erano standard, nel progetto in questione **non si è tenuto bene conto delle eccezioni.**

I finanziatori volevano un ponte leggero, così Moisseiff progettò il ponte più lungo mai costruito all'epoca, era estremamente snello (molto stretto e basso). Gli ingegneri esterni criticarono il progetto perché consideravano il ponte troppo leggero e flessibile, ma Moisseiff tramite i suoi modelli matematici sostenne che la struttura da lui progettata avrebbe resistito a venti di oltre 140 Km/h. 
Già durante la costruzione oscillava molto e nel 1940 crollò, con un vento di appena 75 Km/h.

Il problema infatti non fu il vento in sé, ma le vibrazioni longitudinali che **non erano previste**, poiché visto che negli altri progetti i ponti erano molto più pesanti e rigidi questo fattore non previsto non creò problemi. La causa dunque fu **l'inesperienza in quel tipo di situazione.**
Si era spinti troppo oltre dall'esperienze precedenti. Questo tipo di procedura viene chiamata **Radical procedure**, ovvero quando non puoi basare il tuo progetto su esperienze precedenti ma **devi inventare qualcosa da zero.**
Nonostante allora si possa pensare che costruire da zero sia sempre la soluzione migliore, non è così, perché testando terreno nuovo si rischia di sprecare risorse ed inciampare in errori che magari precedentemente in progetti molto simili (requisiti simili...) erano stati intravisti.
[[Tecniche del riutilizzo]]
### eGK
La eGk è la tessera sanitaria elettronica. Si tratta di un sistema per gestire in modo digitale i dati sanitari dei pazienti ed è un ottimo esempio per comprendere i diversi errori che si possono affrontare in un progetto di ingegneria del software. 

Il progetto non riguarda solo la ricetta elettronica ma molte altre funzioni utili come lettere mediche, cartella clinica elettronica, dati di emergenza, tessera donatore organi...
Ci andiamo a concentrare però sulle **Prescrizioni** dove il medico può creare la ricetta, il farmacista l può riscattare e il paziente può cancellare o nascondere la ricetta.

Il sistema può sembrare semplice: leggere e scrivere una ricetta. Ma in realtà è molto più complessa perché bisogna tenere in considerazione ambienti già esistenti ovvero quello della sanità, le norme legali etc oltre che pensarla in modo tale da poterla aggiornare in continuazione e adattarla ad uno scenario internazionale.
Deve rispettare quindi gli standard medici di classificazione, terminologici, formato sicurezza... Non può essere arbitrario.Dunque **il software eGK non parte da zero, ma deve poter integrare tutti quegli standard già esistenti**. 

Si potrebbe infatti pensare di scrivere le prescrizioni :
class ePrescription {
  String medico;
  String paziente;
  String farmaco;
  int dose;
  String istruzioni;
} 

Ma dimentichiamo che 
- ogni oggetto (medico, paziente, farmaco...) ha **tantissimi attributi** (es. codice, certificazione, indirizzo, identificazione, lingua, permessi...)
- Le interazioni **non sono dirette** (es. serve autenticazione, sicurezza, firma digitale...)
- Ci sono **decine di classi** collegate fra loro
- Ci sono regole specifiche per ogni **soggetto, ruolo, situazione**

## Nozioni di base
I seguenti termini appartengono al vocabolario di base della programmazione (orientata agli oggetti) e dovrebbero esservi già noti. Verranno usati regolarmente quindi è importante che abbiate una comprensione chiara.

Una **classe** è un'entità generale astratta legata al problema da risolvere come Studente, Esame ecc. Definisce le caratteristiche comuni e i comportamenti di tutte le istanze di quella classe tramite **attributi**(i quali descrivono le caratteristiche dell'entità come nel caso di Studente possono essere nome, cognome, matricola etc.) e **metodi** (sono le azioni che l'entità può compiere, ad esempio uno studente sicuramente può prenotarsi alle lezioni quindi avrà un metodo come "prenotaLezione" etc.).

l'**istanza** o **oggetto** invece non è altro che un esemplare concreto di una classe. Una volta che una classe viene definita, si possono creare più istanze di quello stesso oggetto che avranno valori propri e specifici per ciascun attributo.
Ad esempio "Mario" può essere un'istanza della classe Studente e avrà come attributo nome=Mario, cognome=Rossi etc.

L'**ereditarietà** è un'altro concetto chiave che riguarda la programmazione ad oggetti basata sulla presenza di più classi. Avremo una classe "padre" e una sottoclasse "figlia" che eredita  i metodi e gli attributi (non private) della classe padre. Questi metodi possono essere anche riscritti tramite @override mantenendo la stessa firma, ovvero lo stesso nome e gli stessi parametri, oppure fare l'overload dove il nome resta invariato ma i parametri cambiano.

Per fortuna in ogni linguaggio esistono le **librerie** ovvero un insieme di classi, funzioni o metodi già pronti che possiamo utilizzare implementando semplicemente la libreria all'interno del nostro codice per non scriverlo completamente da zero. 

I metodi e le funzioni poi partono da una **specifica** ovvero l'obiettivo di quella funzione, lo scopo e successivamente vengono **implementate** (avviene la stesura del codice). Per **verificare** che queste funzioni e il resto del programma funzioni correttamente possiamo inserire all'intero del codice controlli vari, test etc.
