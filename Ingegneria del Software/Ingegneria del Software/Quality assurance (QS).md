La **quality assurance** (QS) è l'insieme di tutte le attività per garantire che il software sia di alta qualità, il che non significa solo che "funzioni" ma che:
sia **affidabile, usabile, modificabile, robusto e sicuro**

##### Tipi di qualità
- quella **esterna** ovvero vista dall'utente che si basa sulla facilità d'uso, l'affidabilità, le prestazioni etc garantita dai test funzionali ed esperienza utente.
-  la qualità **interna** vista dallo sviluppatore che si basa invece sulla testabilità, manutenibilità, comprensibilità efficienza in velocità etc. garantita dai test statici e strutturali

##### Verifica e Validazione
Sono due attività chiave della **Quality Assurance**, aiutano a garantire che il software sia di alta qualità ma si concentrano su due aspetti differenti:
- **Verifica**: Stiamo costruendo il prodotto nel **modo giusto**?
	Questo viene fatto tramite casi di test come la **revisione** del codice (statici) e i **test dinamici** per controllare che il software funzioni come specificato stesso _in fase di sviluppo_. 
- **Validazione**: Stiamo costruendo il **prodotto giusto**?
	Questa verifica, _alla fine dello sviluppo_, se il software **soddisfa le esigenze e i requisiti del cliente finale o dell'ambiente reale** tramite un test da parte dell'utente finale **test dinamici** (come i test di accettazione).

##### Ma cos'è un caso di test?
Rappresenta una singola situazione che viene verificata per assicurarsi che il software funzioni come previsto. 
  Ogni caso di test è composto da:
	**Input**: dati inseriti per eseguire i test
	**Precondizioni**: condizioni che devono essere vere prima dell'esecuzione
	**Risultato/Comportamento atteso**: cosa si ci aspetta che il sistema faccia
	**Contesto di esecuzione**: l'ambiente o le condizioni in cui viene eseguito il test
	**Aspettative** rispetto al risultato
	
	Un caso di test è considerato "riuscito" se il comportamento effettivo del software coincide con quello previsto/atteso.

##### Approcci per garantire la qualità
-   Testare la **qualità costruttiva** si concentra sulla **prevenzione**, attraverso una buona documentazione, la formazione del team etc
-  **Qualità analitica**, la quale si concentra sul "controllo", puntando a trovare **errori che già esistono** tramite test, ispezioni e appunto analisi analitica.

# Qualità analitica
## Tipi di test per approccio analitico
La qualità analitica utilizza due tipi di test. 
### - Statici          il codice NON viene eseguito ma si legge
Si tratta di un controllo manuale tramite una revisione o un'ispezione, oppure con analisi statica automatica
Ha come obiettivo scovare errori nel codice sorgente.
A differenza dei test dinamici, questi **non dipendono dai dati di input** 

**Ispezione/revisione**: 
	*Si compila un report ci sono degli autori un moderatore, un lettore e dei revisore, l'autore presenta il codice, i colleghi fanno le domande, segnalano errori e si corregge.*

**Analisi statica**
	Insieme di strumenti software che analizzano il codice sorgente direttamente senza eseguirlo. Contrapposto all'ispezione che richiede l'intervento umano, questo è del tutto automatizzato tramite l'utilizzo di strumenti come FindBugs, Lint .. 
	Questi rilevano errori sintattici o catch vuoti, finally mancanti, errori con malloc/free...

### - Dinamici         il codice viene eseguito
Ha come obiettivo verificare che il software si comporti come atteso utilizzando i casi di test, applicabili a tutte le tipologie di test dinamici.
#### Black box testing -  test funzionale
Black-box testing è una tecnica dove **non si guarda il codice** ma ci basiamo solo su cosa dovrebbe fare la funzione, andando a **verificare se il sistema fa quello che dice la specifica.**
Ad esempio se abbiamo la funzione somma(2,3) sappiamo che questa deve restituire 5, quindi facciamo un test senza sapere come realmente la funzione funziona.
Andiamo a testare prendendo Casi di errore, i Casi limite e le Cos'è una classe di equivalenza

**Casi di equivalenza**
Le classi di equivalenza **hanno come obiettivo quello di ridurre il numero di test necessari creando insiemi** di input che rappresentano comportamenti simili del sistema, in modo tale da testare un solo valore del gruppo e non tutti.
Fa parte del black-box poiché testiamo alla "cieca"

Ad esempio se noi sappiamo che i valori da 1 a 19 sono considerati F, mi basterà testare solo uno di questi numeri presenti all'interno del range [1,19].

#### White box  testing -  test strutturale
White-box testing è l'opposto del black-box. Qui **guardiamo dentro il codice**, e dopo aver capito come questo funziona, andiamo a **testare tutte le decisioni logiche (if, else), verificando la loro correttezza**. Serve per scovare bug nascosti.

Utilizziamo diversi metodi quali:
**C0: statement coverage**
Il criterio di copertura più semplice.  Qui ogni istituzione deve essere eseguita almeno una volta da almeno un caso di test
**C1: condition or branch coverage**
Qui ogni if deve essere testato sia in quanto true che false 
**Data flow coverage** 
Controlla che ogni variabile usata sia stata inizializzata

#### Altri tipi di test dinamici:
- **Test di regressione** --> Questi test vengono eseguiti **dopo che il software è stato modificato**, per verificare che le modifiche non abbiano causato nuovi bug in parti già funzionanti del sistema.
- **Usability test** --> Si concentrano sull'**esperienza dell'utente finale**. Quanto è facile e piacevole usare il software?
- **Test di accettazione** --> Verifica se il programma se **soddisfa i bisogni** dell'utente. Viene testato solo alla fine di tutto.
- **Stress test** --> test stress spinge i programma _**oltre** le su possibili capacità_. 
- **Test di prestazioni e carico** --> Simula il programma in **uso intenso** come ad esempio molti utenti.
- **Test di performance** --> testano quanto è **veloce ed efficiente il sistema**
- **Test Top-Down e Test Bottom-Up** --> Top-Down si testano prima i moduli principali e poi quelli secondar mentre con Bottom-Up il contrario si parte da quelli base fino ad arrivare ai moduli più specifici

In ogni caso servono entrambi i tipi di test, dinamici e statici. Utilizzati insieme sicuramente sono migliori poiché il	test funzionale guarda solo cosa dovrebbe fare il programma **elencandoci i requisiti principali** da rispettare senza andare a vedere il codice, quindi ci dà maggiore chiarezza di quali potrebbero essere tutti i possibili casi da tenere in considerazione, mentre il secondo è strettamente **legato al codice** quindi possiamo più **facilmente trovare bug** logici ma utilizzato da solo senza precedenti test funzionali potrebbe perdere l'utilità perché concentrandoci sul funzionamento del codice potremmo perdere di vista quelli che sono i requisiti principali da rispettare che invece il test funzionale elenca. **Gli statici riescono a rilevale errori non rilevabili tramite esecuzione**. 

## Come si scrive un test dinamico
Prima di tutto bisogna sviluppare un buon **test plan**, ovvero un documento, uno schema o una checklist che descrive tutto ciò che riguarda i test. Quindi ci aiuta a ricordare cosa stiamo andando a testare(prestazioni, sicurezza etc), come(quale tipo di test), quali parti del sistema stiamo testando(tutto? solo alcune funzioni? classi?)  etc.

Successivamente andiamo ad applicare i seguenti strumenti e tecniche per poter scrivere test professionali, automatizzati , ordinati e completi. Non devono essere usati per forza in contemporanea ma sarebbe meglio.
#### Test modulari  e riutilizzabili
Un buon test non è un blocco lunghissimo di comandi, ma uno piccolo ben strutturato che può essere riutilizzabile, leggibile e facile da aggiornare.
**Evitiamo la dipendenza tra i vari test** in modo da non avere poi test che funzionano solo se eseguiti in un certo ordine (ogni test deve funzionare da solo).
**Organizziamo i test in classi o file per funzionalità**
#### Automazione dei test
Una volta sviluppato il mio piano di test, l'obiettivo è trovare un modo per eseguire i test in **automatico** in modo tale da non doverli scriverli da capo o lanciarli manualmente.
Questo non solo ci fa _**risparmiare tempo**_ poiché girano da soli, ma _**evita errori umani**_ (come dimenticare un test) e soprattutto se oggi modifico qualcosa, i test automatici _**riescono a dirmi subito se ho rotto qualcosa**_

Ad esempio 
	public class CalcolatriceTest {
    
    @Test
    public void testSomma() {
        Calcolatrice c = new Calcolatrice();
        int risultato = c.somma(2, 3);
        assertEquals(5, risultato);
	    }
	}
È un test automatico poiché si può lanciare tutte le volte che si effettua una modifica e fallirà sempre se il risultato è diverso da 5. 
Ma attenzione! **automatico non significa migliore**. 
#### Framework 
Utilizzato spesso per l'automazione dei test.
È una **libreria di supporto** che ci aiuta a scrivere, eseguire organizzare etc. Come se fossero dei test già pronti per non doverli inventare ogni volta. Certo è che comunque non pensano al posto nostro e quindi vanno usati solo come strumento in aggiunta al nostro piano di test.

È composto da:
-  un **assertion** ovvero delle funzioni per dire "mi aspetto che x sia uguale a y",  `assertEquals(a, b)` controlla che `a == b`
- un **test runner** ovvero un sistema che lancia tutti i test insieme, 
- un'**organizzatore** per separare di test in base alle loro funzionalità, 
- un **report** che ci riassume quanti test sono passati, quanti sono falliti, dove e perché
- delle **annotazioni** come @test, @before @after per Java (JUnit) che semplificano la struttura
#### Registrazione e Riproduzione dei test
Serve per testare le **interfacce grafiche (GUI)** in modo automatico. 
È una tecnica in cui si **registra** quello che l'utente fa sull'interfaccia (clicca, digita...) e si **riproduce** quelle stesse azioni in automatico in futuro.

Gli strumenti più comuni sono 
- Selenium che simula browser e interazioni in maniera automatica, in modo tale da non doverci interagire noi stessi.
- TestComplete che registra le azioni e le riproduce sulla GUI
- Robot Framework che usa le parole chiave per testar descrittivi
  
Questa tecnica nonostante è molto comoda se si hanno tante funzionalità da testare, ha anche parecchi limiti e difficoltà:
**basta un cambio di nome di un bottone per rompere il test** oltre ad essere lenti ad eseguire.
Non possono sostituire in alcun modo gli altri test, ma li completano coprendo la parte visibile dell'app.

## Esercizio test analitici

#### Come sono collegati guasto, errore e difetto?
- **Difetto o bug** è un **errore nel codice** sorgente
- **Errore** è uno **stato errato del programma** che può derivare dal difetto
- **Failure** comportamento scorretto visibile del programma **ciò che si nota visibilmente**

	Difetto o bug nel codice -> causa uno stato errato -> che porta ad un comportamento sbagliato(guasto)

##### a) Specificare la precondizione dell'operazione 'classificaTriangolo' in OCL 

>**classificaTriangolo(int lato1, int lato2, int lato3)**
Questa funzione determina, a partire dalle lunghezze intere dei lati di un triangolo, se il triangolo è equilatero, rettangolo, isoscele o normale.  

Quali sono dunque le condizioni che devono essere vere prima di poter eseguire la nostra funzione?
Per funzionare correttamente bisogna inserire tre numeri interi positivi e la somma di qualsiasi due di loro deve essere maggiore di un solo.

context Math::classificaTriangolo(lato1: Integer, lato2: Integer, lato3: Integer)
pre: 
	lato1 > 0 and lato2 > 0 and lato3 > 0
     and lato1 + lato2 > lato3
     and lato2 + lato3 > lato1
     and lato1 + lato3 > lato2

##### b) Black-box testing:  Test funzionale
Crea **almeno 7 casi di test** basandoti **solo sulla descrizione dell’interfaccia** della funzione. Considera casi diversi in cui ti aspetti **comportamenti differenti del sistema**.    

	Black-box testing è una tecnica dove non si guarda il codice ma ci basiamo solo su cosa dovrebbe fare la funzione 

| Input `(l1, l2, l3)` | Tipo atteso | Motivo della scelta                                                           |
| -------------------- | ----------- | ----------------------------------------------------------------------------- |
| (3, 3, 3)            | Equilatero  | Tutti i lati uguali. Caso classico.                                           |
| (3, 4, 5)            | Rettangolo  | Triangolo rettangolo (3² + 4² = 5²).  Pitagora.                               |
| (5, 5, 3)            | Isoscele    | Due lati uguali. Caso base per isoscele.                                      |
| (4, 6, 5)            | Normale     | Nessun lato uguale.                                                           |
| (0, 5, 5)            | Errore      | Un lato è 0 → non può esistere. Test input non valido.                        |
| (-1, 4, 4)           | Errore      | Un lato negativo. Non ha senso fisicamente.                                   |
| (1, 2, 3)            | Errore      | Non rispetta la disuguaglianza triangolare (1+2=3 e non >). Test caso limite. |

##### c) White-box testing (Branch coverage C1): Test strutturale
Ora crea casi di test basandoti sulla **struttura del codice**, con l’obiettivo di ottenere la **copertura dei rami (branch coverage, C1)**, cioè ogni decisione condizionale del codice deve essere verificata sia nel caso **vero** che nel caso **falso**.

	White-box testing è l'opposto del black-box. Qui guardiamo dentro il codice e dopo aver capito cone questo funziona andiamo a testare tutte le decisioni logiche (if, else) sia in quanto vere che false.
	
class Math {
    enum TipoTriangolo { Rettangolo, Isoscele, Equilatero, Normale }
    
    public TipoTriangolo classificaTriangolo(int lato1, int lato2, int lato3) {
        if ((lato1 == lato2) || (lato2 == lato3) || (lato1 == lato3))
            return TipoTriangolo.Isoscele;

        if ((lato1 == lato2) && (lato2 == lato3))
            return TipoTriangolo.Equilatero;

        int q1 = lato1 * lato1;
        int q2 = lato2 * lato2;
        int q3 = lato3 * lato3;

        if ((q3 + q2 == q3) || (q1 + q3 == q2) || (q3 + q2 == q1))
            return TipoTriangolo.Rettangolo;

        return TipoTriangolo.Normale;
    }
}

Prima di tutto, **individua i punti del programma** in cui ci sono **ramificazioni** (condizioni `if`) e scrivile. 
	1) if ((l1 == l2) || (l2 == l3) || (l1 == l3))
	2) if ((l1 == l2) && (l2 == l3))
	3) if ((q3 + q2 == q3) || (q1 + q3 == q2) || (q3 + q2 == q1))

Poi, crea casi di test tali che **ogni ramo** del programma venga eseguito almeno una volta.
Presenta i casi in forma di tabella e spiega per ciascuno perché l’hai scelto.

| Input (l1, l2, l3) | Output atteso         | Spiegazione                                                                                                    |
| ------------------ | --------------------- | -------------------------------------------------------------------------------------------------------------- |
| (3, 3, 3)          | Isoscele + Equilatero | Tutti i `==` sono veri. 1) è **vero** 2) **vero** ma non ritorna equilatero perché c'è la return. **Problema** |
| (3, 3, 4)          | Isoscele              | Solo due lati uguali. 1 ) è **vero**. 2) **falso**                                                             |
| (3, 4, 5)          | Rettangolo            | 1)  è **falso**, 2) **falso**, 3) **vero**.  3² + 4² = 5².                                                     |
| (4, 5, 6)          | Normale               | 1) 2) 3) **falso** → ritorna triangolo normale.                                                                |

##### d) Combina tutti i casi test creati nei punti b) e c) in un unico insieme di test 

Esegui mentalmente i test. Descrivi eventuali **difetti (bug)** che hai scoperto nel programma con questi test.
- Nei test del punto b) se non si impongono le precondizioni scritte nell'a), **(0, 5, 5), (-1, 4, 4), (1, 2, 3)** non ritornano errore ma dei tipi di triangoli.
- Nei test c) **(3, 3, 3)** ha un bug.  Quando si ha un triangolo che è sia Isoscele che Equilatero non ritorna come tipo Equilatero. Per definizione il triangolo Equilatero è una specializzazione dell'isoscele quindi per verificare se si ha a che fare con questo tipo di triangolo, bisogna impostare la 2) condizione logica if prima della 1)


#### Cos'è una classe di equivalenza. 
**Usiamo le classi di equivalenza in fase di test (black-box) quando non conosciamo il codice interno, ma solo il comportamento del sistema.**
Ad esempio se noi sappiamo che i valori da 1 a 19 sono considerati F, mi basterà testare solo uno di questi numeri presenti all'interno del range [1,19].

**Scenario:**  
Un corso universitario prevede due esami.
- Esame 1: massimo 40 punti
- Esame 2: massimo 60 punti
- Totale massimo: 100 punti

**Schema di valutazione:**
 >Se **uno dei due esami ha meno di 20 punti**, il risultato è "F" (insufficiente).
 >= **20%** → voto "D".
 >= **60%** → voto "C".
 >= **75%** → voto "B".
 >= **90%** → voto "A".
 Si assegnano **solo punti interi**.
 Tutti gli studenti **sostengono entrambi gli esami**.
 Il sistema riceve **due input interi** (punteggi) e restituisce **una lettera come voto**.

#### Per ciascuna classe di equivalenza, formulate un caso di test.

| Classe | Input (Esame1, Esame2) | Totale | Output Atteso | Spiegazione                 |
| ------ | ---------------------- | ------ | ------------- | --------------------------- |
| EQ1    | (15, 40)               | 55     | F             | Uno dei due < 20            |
| EQ2    | (25, 30)               | 55     | D             | Entrambi ≥ 20 ma somma < 60 |
| EQ3    | (30, 35)               | 65     | C             | Somma nella fascia 60–74    |
| EQ4    | (35, 40)               | 75     | B             | Somma nella fascia 75–89    |
| EQ5    | (40, 50)               | 90     | A             | Somma ≥ 90                  |

#### Esaminate i confini tra le vostre classi di equivalenza. Definite due casi di test per ogni confine: uno in ciascuna delle due classi. 

- **Transizione tra voto insufficiente (F) e sufficiente (D):**
    - Caso di test 1 (F): E1 = 19, E2 = 30 → Totale = 49, Voto = F
    - Caso di test 2 (D): E1 = 20, E2 = 30 → Totale = 50, Voto = D
    - Caso di test 3 (F): E1 = 30, E2 = 19 → Totale = 49, Voto = F
    - Caso di test 4 (D): E1 = 30, E2 = 20 → Totale = 50, Voto = D
        
- **Transizione tra voto D e voto C:**
    - Caso di test 5 (D): E1 = 29, E2 = 29 → Totale = 58, Voto = D
    - Caso di test 6 (C): E1 = 30, E2 = 30 → Totale = 60, Voto = C
        
- **Transizione tra voto F e voto C:**
    - Caso di test 7 (F): E1 = 19, E2 = 45 → Totale = 64, Voto = F
    - Caso di test 8 (C): E1 = 20, E2 = 45 → Totale = 65, Voto = C
        
- **Transizione tra voto C e voto B:**
    - Caso di test 9 (C): E1 = 29, E2 = 44 → Totale = 73, Voto = C
    - Caso di test 10 (B): E1 = 35, E2 = 40 → Totale = 75, Voto = B
        
- **Transizione tra voto F e voto B:**
    - Caso di test 11 (F): E1 = 19, E2 = 57 → Totale = 76, Voto = F
    - Caso di test 12 (B): E1 = 20, E2 = 57 → Totale = 77, Voto = B
        
- **Transizione tra voto B e voto A:**
    - Caso di test 13 (B): E1 = 34, E2 = 54 → Totale = 88, Voto = B
    - Caso di test 14 (A): E1 = 35, E2 = 55 → Totale = 90, Voto = A


