Se con i casi d'uso avevamo una visione esterna del sistema, **con la modellazione dinamica passiamo ad una visione interna, quindi non solo dal punto di vista dell'utente.** Ci aiutano a descrivere e specificare il comportamento atteso.
Non basta sapere cosa fa il sistema, ma dobbiamo sapere anche **quando lo fa, in che ordine.**

1. Si passa da capire qual'è il comportamento esterno (**casi d'uso**),
2. a capire qual'è la struttura del sistema tramite la **modellazione degli oggetti** con diagrammi di classe 
3. e infine capire il suo comportamento con la **modellazione dinamica** creando diagrammi di sequenza(già li conosciamo inutile andare a riprenderli) o di stato che identificano mittenti e destinatari e ci permettono di mostrare la sequenza di messaggi scambiati tra gli oggetti.

### Sequence diagram
Comunicazione tra oggetti. Mostra chi manda messaggi a chi e in quale ordine. **Viene applicato per descrivere un'interazione specifica tra oggetti in uno specifico caso d'uso.**
Lo conosciamo già quindi non andremo ad approfondirlo ulteriormente. C'è un'omino delle colonne verticali che rappresentano la durata dell'interazione e frecce che collegano avanti e dietro le varie classi.

## Altri tipi principali di diagrammi
Vengono usati tutti ma per scopi diversi.

**Approccio "state-based"** secondo cui:
Ogni entità (oggetto) può avere:
- **Stati interni** --> come "acceso", "spento", "attivo", "errore" 
  È una **condizione stabile**, in pausa fin quando non accade un **evento che la smuove**, come l'utente che preme qualcosa, o un timer che scade...
- **Transizioni** tra stati, causate da **eventi**
- **Azioni** sono attività eseguite **durante una transazione** o quando si entra/esce da uno stato.

Esempio lavatrice:
	**Stati**: spento, accensione, lavaggio, centrifuga, fine
	**Eventi**: tasto premuto, tempo scaduto, acqua raggiunta, sportello aperto
	**Transizioni**: collegano stati → "da A a B se succede X"
  
Questa logica viene modellata con i diagrammi degli stati UML.
### Diagramma si stato
**Deriva dallo "stato", dunque rappresenta il ciclo di vita di un oggetto.**  Ad esempio "In attesa di pagamento".
Mostra **come cambia nel tempo un singolo oggetto** (il suo ciclo di vita) basato su stati, eventi, transizioni e azioni.
Viene applicato per oggetti con ciclo di vita complesso (es. ordini, dispositivi, sessioni).

- Lo stato viene rappresentato con dei rettangoli con gli angoli arrotondati.
- Al suo interno ci sono scritte la varie azioni.
- Lo stato iniziale viene rappresentato da un pallino nero, mentre l'ultimo da un pallino nero con un contorno.
- Il rombo rappresenta una decisione o merge
- Le transizioni vengono rappresentate  da frecce con sopra un etichetta come:
evento [condizione] / azione
	Ad esempio: pagamento ricevuto [totale >= 0] / aggiorna stato → [Pagato]
	dove "pagamento ricevuto" è l'evento, il totale la condizione (facoltativa), e "aggiorna stato" è l'azione

##### Modellazione Interfacce Utente
I diagrammi di stato vengono riutilizzati per progettare interfacce utente, in particolare per **rappresentare il percorso di navigazione o il flusso delle schermate nel sistema.**

Ogni stato corrisponde ad una schermata e le transizioni rappresentano le azioni dell'utente come clic su un pulsante , la scelta da un menù o il movimento del cursore.
**Il nome dello stato rappresenta il nome della schermata e i punti elencati sotto lo stato sono le azioni disponibili.**

### Diagramma di attività
**Rappresenta una sequenza logica di azioni.**  Ad esempio "verifica disponibilità", "calcola prezzo"...
Usano lo stesso stile dei diagrammi di stato, ma invece di rappresentare gli stati interni di un oggetto, **mostrano la sequenza delle azioni/attività.**
Qui non è necessario esplicitare i simboli di join/split, perché sono impliciti nel flusso.

- Quando **due attività** partono da una **stessa freccia**, vuol dire che sono parallele (split)
- Quando **due frecce** si **uniscono in una**, vuol dire che devono **entrambe finire prima di proseguire** (join)

		Vedi pag 9 di latex per visionare esempio di diagramma di attività
