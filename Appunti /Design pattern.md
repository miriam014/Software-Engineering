Per **Pattern** si intente **schema ricorrente**, una struttura che aiuta la comprensione di qualcosa molto complesso e che riesce a raccogliere più concetti diversi sotto un'unica idea.
È utile, perché conoscendo il pattern, **l'idea si può riutilizzare anche se il codice cambia**, senza dover reinventare nuovi metodi ogni volta.

Un esempio è sicuramente il gioco Tic-Tac-Toe(Tris) e Get-15, nonostante sembrino due giochi completamente diversi alla fine tramite un'analisi approfondita capiamo che in entrambi i casi l'obiettivo è raggiungere prima il numero 15 (nel tris in ogni riga e ogni colonna la somma dei numeri è sempre 15). Quindi l'idea può essere riutilizzata anche per codici diversi. 

**I pattern non esistono isolati, ma lavorano in gruppo (Mustersprachen).** 
## Concetti
#### a) Per non confondersi

| Concetto                              | Cosa rappresenta                                                                                                                                            | Esempio              |
| ------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------- |
| **Componente**                        | Parte modulare e riusabile di un sistema, spesso con un’interfaccia ben definita<br><br>é un **elemento del sistema reale che può usare i pattern **        | `PaymentProcessor`   |
| **Design pattern**                    | Soluzione astratta a un problema ricorrente nel design software<br><br>é una **soluzione concettuale riusabile**                                            | `Singleton, Adapter` |
| **Architettura/stile architetturale** | Modello di organizzazione generale del sistema, orientato alla struttura globale<br><br>è una **visione macro** dell'intero sistema e delle sue connessioni | `MVC, Microservizi`  |

#### b) definizioni
- **Firma (signature)**: è la descrizione di un metodo che include il nome, i parametri e il tipo di ritorno.  Esempio: `int add(int x, int y)`
- **Interfaccia (interface)**: è un insieme di firme/metodi astratti (senza implementazione) che una classe può implementare. Definisce **cosa** una classe fa, **non** **come**.
- **Classe**: definisce struttura e comportamento di oggetti
- **Componente**: è un modulo software **indipendente e riusabile**, con un'interfaccia ben definita, spesso composto da più classi. È un'entità distribuita/riutilizzabile a livello architetturale. 
	Ad esempio 
	- Un componente `LoginService` serve solo per gestire login.
	- Un componente `DBConnection` serve per parlare col database.
 - **Modulo**: è un insieme di componenti che lavorano insieme per una funzione più grande.
	 Ad esempio il modulo "autenticazione" questo può contenere un componente per il login, ma anche uno per il logout e uno per il permessi ...
- **Coesione (Cohesion)**: misura quindi quanto bene le parti di un singolo componente lavorano tra loro per fare un sola cosa. Si punta ad una coesione alta quindi quando **un componente fa solo quello che deve e bene**, senza divagare e fare troppe cose diverse, in modo da avere un codice leggibile testabile e meno caotico
- **Accoppiamento (Coupling)**: misura la **dipendenza** tra moduli diversi, quanto uno dipenda dall'altro. Un buono obiettivo sarebbe creare un basso accoppiamento, ovvero far si che cambiando un modulo non siamo costretti a cambiare anche l'altro


## Tipi di Design Pattern - Famiglie

| Structural Patterns (Strutturali)                                                              | Creational Patterns (di creazione)                                                                                                                                 | Behavioral Patterns (comportamentali)                             |
| ---------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------- |
| Servono a **organizzare** oggetti e classi per costruire strutture flessibili e riutilizzabili | Servono a **creare**. oggetti in modo flessibile.<br>*Separano la creazione dell'oggetto dal suo utilizzo*                                                %%  . %% | Si concentrano su come gli oggetti si **comportano e comunicano** |
| -Adapter <br>-Bridge<br>-Facade<br>-Proxy<br>-Composite                                        | -Abstract Factory<br>-Builder<br>-Singleton                                                                                                                        | -Observer<br>-Command<br>-Strategy<br>-Iterator                   |

### Creational Patterns
#### Singleton. 
A volte in un'applicazione è necessario che **esista un solo oggetto** per gestire qualcosa di centrale, come un file di configurazione o un sistema di loggin. È qui che entra in gioco il Singleton.

Il **Singleton** è un modello di Creational Pattern che garantisce che una classe abbia **una sola istanza**(oggetto) **in tutto il sistema**, fornendo al contempo un **modo globale per accedervi** mantenendo un riferimento statico privato all'unica istanza.  *Evita la moltiplicazione di oggetti*

Niente, tranne la classe Singleton stessa, può sostituire l'istanza memorizzata nella cache. L'oggetto singleton viene inizializzato solo quando viene richiesto per la prima volta.
- quindi nascondo il costruttore rendendolo privato e faccio in modo che solo richiamando il mio metodo getIstance() per esempio posso andarlo a richiamare.

		 public class Logger {
		    private static Logger instance;
		    
		    private Logger() {} // costruttore privato
		
		    public static Logger getInstance() {
		        if (instance == null) {
		            instance = new Logger();
		        }
		        return instance;
		    }
		}

 Esempi
	1. **Logger globale**: ogni classe avrebbe un file di log diverso e non sarebbe possibile unire tutto in un unico log. invece con il Singleton tutte le classi di un’applicazione scrivono i log su un’unica istanza `Logger.getInstance().log(...)`.
	2. **Connessione a un database**: `DBConnection.getInstance()` assicura che ci sia un’unica connessione attiva, o una connessione condivisa thread-safe.

Alcuni esperti non lo vedono nemmeno come un vero e proprio pattern ma più come una *tecnica* per l'imitare l'accesso alle risorse. Infatti va usato con molta attenzione e non abusarne poiché può portare a delle dipendenze nascoste e rende difficile fare test essendo globale.

#### Factory Method
Crea **un tipo di oggetto alla volta**
L'idea di base è quella di delegare la creazione di oggetti ad una sottoclasse invece di utilizzare direttamente new.
Ad esempio se voglio creare un documento ma non so se questo sarà Pdf o Word invece di scrivere *if (tipo.equals("pdf")) doc = new PDFDocumento();  else doc = new WordDocumento();*
e se voglio aggiungere un nuovo tipo come ad esempio html devo andare a modificare l'if, per questo utilizziamo Factory. 
**Quindi riduce la dipendenza tra lassi rendendo il codice più flessibile e testabile ma allo stesso tempo però  richiede più classi, una per ogni tipo.**

Faccio direttamente:

	abstract class Editor {
		public abstract Documento creaDocumento();
		
		public void apriDocumento() {
			Documento d = creaDocumento();
			d.visualizza();
		}
	}
		
	class PDFEditor extends Editor {
		public Documento creaDocumento() {
			return new PDFDocumento();
		}
	}
		
	class WordEditor extends Editor {
		public Documento creaDocumento() {
			return new WordDocumento();
		}
	}

#### Abstract Factory
Crea **un'intera famiglia di oggetti correlati**
L'idea chiava è quella di creare famiglie di oggetti correlati senza specificare classe concrete.

Ad esempio un problema potrebbe essere quello di creare un'interfaccia grafica per due sistemi operativi differenti come Windows e macOS. Se mischio le classi mi ritrovo con un codice del tipo if sistema== "win" allora bottone=new WindowsButton() etc 
Invece la mia idea è quella di **creare un'interfaccia GUIFactory con metodi per creare componenti**. Quindi ogni famiglia(Windows, macOS) alla fine ha una sua implementazione concreta dalla fabbrica.

Esempio:

	interface GUIFactory {
	    Button creaBottone();
	    Checkbox creaCheckbox();
	}
	
	class WinFactory implements GUIFactory {
	    public Button creaBottone() { return new WindowsButton(); }
	    public Checkbox creaCheckbox() { return new WindowsCheckbox(); }
	}
	
	class MacFactory implements GUIFactory {
	    public Button creaBottone() { return new MacButton(); }
	    public Checkbox creaCheckbox() { return new MacCheckbox(); }
	}

### Structural Patterns
#### Adapter 
Viene utilizzato quando si vuole **riutilizzare un componente esistente** adattandolo al nuovo sistema.
Ad esempio l'uso di una vecchia API in un nuovo programma:
	se ho una libreria che legge .xml, ma il mio software legge JSON allora Adapter traduce da xml a JSON dietro le quinte 

Rende compatibili due interfacce incompatibili
Può essere sviluppato tramite l'ereditarietà multipla di Java

#### Bridge 
Ha come scopo **separare l'astrazione dalla sua implementazione** 
Ad esempio in una GUI con supporto per più sistemi operativi otterrò una gerarchia complicata se uso l'ereditarietà diretta, poiché da un lato avrò le funzionalità: (Window, Dialog, IconWindow) e dall'altro le piattaforme (implementazioni, come vengono disegnate): (Window, Linux, Mac). Dovrei avere tante combinazioni quante le possibilità. 

Invece la nostra idea è quella di separare in due gerarchie in modo da **poterle combinare liberamente:**

		Abstraction: Window, Dialog etc
		Implementation: WindImpl, LinuxImpl etc

#### Facade 
Fornisce una **interfaccia semplificata** a un sottosistema complesso. 
Lo utilizziamo quando vogliamo **nascondere i dettagli interni** di un sistema per facilitarne l’uso. Ad esempio *dietro le quinte c'è il caos, ma io vedo solo il pulsante ON*

Quindi la mia classe Facade incapsula tutta la complessità e offre all'utente solo 1 o 2 metodi semplici.  Ad esempio in un sistema audio la classe Home gestisce DVD, proiettore, luci, schermo etc ma l'utente chiama solo startMovie("Matrix").

Ideale per costruire interfacce pubbliche

#### Proxy 
**Sostituire un oggetto reale con un altro oggetto che si comporta come lui**, ma aggiunge qualcosa.
È identico e lo utilizziamo quando vogliamo **controllare, proteggere o ritardare** l'accesso a un oggetto, nel caso in cui questo fosse troppo pesante da caricare, sensibile o lento(accesso da remoto) etc

Può essere utilizzato per rappresentare l'oggetto su un altro server, caricare un oggetto solo quando serve, limitare l'accesso in base ai permessi o memorizzare i dati per evitare ricalcoli. 

Caricamento lento di immagini su browser

#### Composite
Permette di **trattare in modo uniforme oggetti simili e gruppi di oggetti**. 
Viene utilizzato quando ho bisogno di rappresentare strutture gerarchiche (tipo alberi) dove ogni nodo può essere un oggetto semplice (foglia) o un contenitore di altri oggetti (nodo con figli).

Basta creare una superclasse comune Component e le sottoclassi saranno foglie e composite
Attenzione!! non è da confondere con l'ereditarietà perché non sto solo "specializzando" un comportamento, ma sto costruendo una **struttura ricorsiva**. 

Ad esempio se voglio fare la funzione Stampa, questa devo poterla utilizzare sia su un file singolo, che all'interno di una cartella che contiene poi tanti file. e devo poter chiamare Stampa allo stesso modo in entrambe le classi.

### Behavioral Patterns
I **pattern comportamentali** descrivono **come gli oggetti interagiscono** tra loro, **chi fa cosa**, **chi prende le decisioni**, e **come cambia il comportamento del sistema nel tempo**. 
Hanno come obiettivo principale quello di organizzare le responsabilità, per garantire un sistema flessibile ed estendibile.
#### Observer
L'Observer è perfetto quando vuoi **reazioni automatiche a cambiamenti di stato**, senza hardcodare le dipendenze. Viene utilizzato ovunque nell GUI(swing, JavaFX), Eventi(listener di mouse), moduli plugin...

 Solitamente si divide il sistema in due ruoli: il soggetto che contiene i dati e notifica i cambiamenti e poi l'observer che si iscrive al soggetto e riceve notifiche ogni volta che il soggetto cambia.
 E' difficile controllare l'ordine delle notifiche e c'è il rischio di ciclo di notifiche se gli observer cambiano il soggetto di nuovo. 

Un esempio è quello delle tabelle: al cambiamento dei dati vogliamo che la tabella si aggiorni insieme ai grafici, le altre celle e tutte le altre finestre della GUI collegate.
Infatti l'Observer ha un metodo update(), che viene chiamato quando il soggetto cambia. Su un singolo oggetto possiamo mettere più observer.

#### Command
Ha come scopo **incapsulare una richiesta come un oggetto**, in modo da poterla eseguire in un secondo momento, annullarla, salvarla, passarla ad altri oggetti, ritardare l'esecuzione etc

Immaginiamo di costruire una interfaccia con un menu (GUI): Ogni voce del menu dovrebbe eseguire un'azione (es. homepage, open, Report etc), ma vogliamo far si che la GUI sia riutilizzabile e riconfigurabile.

Quindi **l'dea più semplice sarebbe quella di chiamare il metodo homepage nel caso in cui l'utente clicchi il bottone homepage... ma in questo modo io non posso annullare l'azione, cambiando i comportamenti a runtime o salvarmi i movimenti dell'utente e ancor peggio il bottone è legato all'azione stessa tramite @FXML**
Questo metodo viene utilizzato per app piccole che hanno pochi bottoni, dove ogni bottone ha il suo proprio comportamento hardcoded: 

@FXML  
public void changeFamiglia(ActionEvent actionEvent) {  
    showDialog("/interfaccia/editFamiglia.fxml", changeFamily, "Modifica famiglia");  
    initialize();  
}  

Quindi la soluzione corretta sarebbe:
	Creare un'interfaccia Command e implementare le varie azioni all'interno di classi che la implementano. In questo modo ogni bottone contiene solo un oggetto comando e fa command.execute(). 

#### Strategy
Il Strategy Pattern ti permette di **cambiare dinamicamente il comportamento di un oggetto a runtime, senza if/else**  mantenendo il codice pulito, modulare e riutilizzabile, modificandolo e aggiornandolo non rompendo il codice esistente. 

Un esempio è l'utilizzo di Strategy all'interno di un'applicazione di una Database App dove si hanno **comportamenti che possono variare come la scelta del metodo di pagamento o il metodo di ordinamento ..**
 In un sistema di pagamento che supporta PayPal, carta di credito, bonifico.. ma l'interfaccia utente resta sempre la stessa.

In che modo? Si definisce una interfaccia comune (Pagamento) e si creano poi più classi concrete (PayPalPagamneto, CreditCardPagmento...) ognuna con la sua logica.
#### Iterator
Se ho una collezione di oggetti (List, Set, Tree, Array...) voglio poter accedere agli elementi uno alla volta senza esporre la struttura interna della collezione e possibilmente usare lo stesso tipo di ciclo per tutte le collezioni, utilizzo Iterator.

Il pattern Iterator introduce un oggetto separato chiamato Iterator, che ha un'interfaccia standard per scorrere gli elementi 
Ha come vantaggio quello di poter cambiare la struttura senza toccare il codice che la usa anche se è difficile da implementare se la struttura non è lineare (come i grafi complessi).

