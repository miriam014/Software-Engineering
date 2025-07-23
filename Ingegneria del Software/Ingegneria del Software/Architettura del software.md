Progettare l'architettura significa decidere **come suddividere il sistema (in moduli) e come fare in modo che tutte le sue qualità desiderate emergano** dal suo funzionamento complessivo.
Architettura **significa capire cosa fa OGNI PARTE del sistema, come si collega alle altre e quali comportamenti ci aspettiamo.**
Serve a soddisfare i requisiti, soprattutto quelli non funzionali.

I principi per una buona progettazione sono una buona architettura, la modularizzazione e il riutilizzo insieme alla documentazione.

**Una volta ottenuti i requisiti**, sia funzionali (si sa cosa il sistema deve fare) che non funzionali (quali qualità), **è il momento di capire come costruirlo.** 
Decidere quindi:
1. Come suddividere il sistema in moduli;
2. Come soddisfare i requisiti non funzionali con una struttura complessiva adeguata.

Dobbiamo ricordarci che **le proprietà globali di un sistema derivano da come i moduli interagiscono** tra loro. Ad esempio, la robustezza o la sicurezza non sono funzioni di un singolo pezzo di codice, ma dell'intero insieme.
Per affrontare questo problema si fa riferimento spesso ad "architetture standard", ovvero soluzioni già collaudate in passato per problemi simili. 
Un esempio semplice di scelta architetturale è quello della costruzione di una casa. Se l'obiettivo è la mobilità, sceglieremo una roulotte; se è la difesa, un castello. Se vogliamo entrambe le cose, **serve un compromesso.**

## Stili architettonici
Affidarsi ad architetture standard riduce i rischi e migliora la qualità. Una buona architettura è il fondamento per costruire software robusto, scalabile e manutenibile.

- **Client/Server**: un **server centrale memorizza i dati, i client accedono alla rete per usare i servizi.** Adatto a sistemi distribuiti, con molti dati e alta interattività.
  È necessario che i clienti abbiano accesso alla rete e che le reti siano sufficientemente potenti e disponibili.
- **A 3 livelli/strati**: **presentazione (GUI)** incapsula le interazioni con gli utenti o sistemi, **logica (business logic)**, **dati (database)**. Ogni livello usa solo i livelli inferiori. Questo stile favorisce la modularità e l'organizzazione.
  Vantaggi: riduce gli accoppiamenti, struttura chiara, facile sostituire interi strati. 
  Svantaggi: può essere inefficiente, innaturale.
- **Event-based**: i moduli si registrano a un centro per ricevere notifiche di eventi.
  Svantaggi: il comportamento può essere difficile da vedere e cambiare.
  Usato in GUI, IoT, ecc.
- **Pipe-and-filter**: dati che passano attraverso una sequenza di trasformazioni (filtri). Semplice ma poco flessibile. Comune in bioinformatica, elaborazione segnali.
- **Architettura Web**: include sicurezza, internazionalizzazione, scalabilità, supporto a sviluppo distribuito. Spesso si usa una combinazione di architetture diverse.

Un altro aspetto importante è che **le immagini architetturali non sono l'architettura**, ma solo una rappresentazione parziale. Servono molte immagini (es. UML) e descrizioni testuali(OCL) per documentare bene un'architettura.
#### Architetture standard
In generale, si ci affida a un'architettura standard per una determinata area di applicazione.
Queste offrono principi, tecnologie e linee guida per costruire sistemi professionali.
- QUASAR
- Jakarta EE
- RM-ODP

## Modularizzazione
Una volta decisa l'architettura complessiva e compresi i requisiti funzionali e non funzionali, il passo successivo è decidere **come suddividere il sistema in moduli**, ossia in componenti indipendenti ma interconnessi. Questa suddivisione serve a **ridurre la complessità**, aumentare la **manutenibilità**, facilitare lo **sviluppo parallelo** e migliorare la **comprensibilità del sistema**.

Ogni modulo è una **parte del sistema** con una responsabilità chiara. Può contenere classi, funzioni, dati, algoritmi – ma l'importante è che abbia **confini ben definiti** rispetto agli altri moduli. 

Ogni modulo dovrebbe essere pensato con tre concetti fondamentali:
1. **Interfaccia**: ciò che il modulo offre agli altri, ovvero le funzioni, i metodi o i dati visibili all'esterno.
2. **Contratto**: le **regole e le condizioni** che chi usa il modulo deve rispettare e che il modulo garantisce in cambio.
3. **Segreto**: tutto ciò che avviene **all'interno del modulo** e che non deve interessare agli altri (implementazione, strutture dati interne, ecc.).
   Questo approccio è noto come **information hiding** (nascondere le informazioni): ogni modulo mostra solo ciò che è necessario e tiene nascosto il resto. 

Questo permette di **modificare un modulo** senza dover cambiare gli altri, purché l'interfaccia resti invariata.
### Criteri per una buona suddivisione in moduli
Il professore elenca **quattro criteri principali** per decidere come suddividere un sistema in moduli:
1. **Separazione delle preoccupazioni**: ogni modulo dovrebbe **occuparsi di un solo "concetto"** o responsabilità.
2. **Località**: se una modifica riguarda un certo comportamento, dovrebbe richiedere modifiche solo in un modulo.
3. **Isolamento dei cambiamenti**: se cambia qualcosa nel sistema (per es. un formato di dati), dovrebbe bastare cambiare un solo modulo.
4. **Comprensibilità**: i moduli devono avere nomi e compiti chiari, in modo che chi legge il codice capisca subito a cosa servono.

Un modulo è ben progettato quando:
- ha una responsabilità precisa e limitata;
- ha un'interfaccia semplice e ben documentata;
- è isolato da dipendenze inutili;
- può essere riutilizzato in altri contesti.
### Esempi pratici di buona modularizzazione
Un buon esempio è un modulo per la gestione degli utenti:
- Interfaccia: `creaUtente()`, `autentica()`, `modificaProfilo()`.
- Contratto: `creaUtente()` fallisce se l'email è già usata; `autentica()` restituisce un token solo se la password è corretta.
- Segreto: come vengono salvati i dati (file? database? hash delle password?) non interessa all'esterno.

Se domani decidiamo di cambiare da un database relazionale a uno NoSQL, il resto del sistema non deve essere modificato: basta aggiornare la parte segreta del modulo.
### Modularizzazione e sviluppo di gruppo
Una buona modularizzazione è cruciale anche per il lavoro di squadra. Se ogni gruppo lavora su un modulo indipendente, si evitano conflitti. È importante che le interfacce siano discusse e fissate all'inizio: **una volta deciso "cosa fa" ogni modulo, i gruppi possono lavorare in parallelo anche senza sapere "come" gli altri implementeranno il loro modulo.**

Infine, la modularizzazione non è un compito da fare una volta sola. Durante l'intero ciclo di vita del progetto, è necessario **rivalutare e migliorare** la suddivisione in moduli, adattandola ai cambiamenti nei requisiti o alla complessità emergente.