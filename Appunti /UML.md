# 6-1

| PomodoroSessione                                                           |
| -------------------------------------------------------------------------- |
| - durataStudio: float<br>- durataPausa: folat<br>- obiettivoDurata: string |
| - haRaggiuntoObiettivo: bool                                               |

Classe soluzione: TimerController
	Descrizione: Gestisce la logica per far partire un timer etc. con metodi tecnici come start, pause, reset ect. (parte software)
	Implementa un **comportamento**.

| TimerController                                               |
| ------------------------------------------------------------- |
| - tempoRimanente: float<br>- stato: string                    |
| + avvia()<br>+ iniziaPausa()<br>+ terminaPausa()<br>+ reset() |

_**c) Ricercare e descrivere le differenze tra i diagrammi delle classi usati nelle fasi di analisi, progettazione e implementazione.**_
Distinguere in base ai seguenti aspetti:
- Scopo d’uso, Terminologia utilizzata, Semantica delle classi modellate e delle loro proprietà, Semantica delle associazioni, Livello di dettaglio

| Aspetto                          | Analisi                                         | Progettazione                                   | Implementazione                                    |
| -------------------------------- | ----------------------------------------------- | ----------------------------------------------- | -------------------------------------------------- |
| **Scopo d’uso**                  | Comprendere e modellare il dominio del problema | Definire la struttura del sistema software      | Dettagliare la struttura per l'implementazione     |
| **Terminologia**                 | Termini del dominio (es. Studente, Corso)       | Termini tecnici (es. Controller, Servizio)      | Termini specifici del linguaggio di programmazione |
| **Semantica delle classi**       | Concetti reali del dominio                      | Componenti software astratti                    | Classi concrete con dettagli di implementazione    |
| **Semantica delle associazioni** | Relazioni logiche tra entità del dominio        | Relazioni tra componenti software               | Relazioni implementate tramite codice              |
| **Livello di dettaglio**         | Alto livello, senza dettagli tecnici            | Medio livello, con alcune decisioni progettuali | Basso livello, con tutti i dettagli necessari      |

# 6-2
_**Modellare il seguente caso d’uso come diagramma di activity UML:**_
- Usare **partizioni** per separare le attività in base agli attori che le eseguono (“activity partition”).
- Modellare sia il **flusso di controllo** sia i **flussi di dati**. Questi ultimi possono essere indicati come **“pins”** sui nodi delle attività o come **nodi oggetto** tra i nodi delle attività (“data flow”).

**Caso d'Uso:**
1. Il **docente** prende in carico un’unità di lezione non ancora preparata e la pianifica creando una serie di slide. Dopo di ciò, l’unità di lezione è considerata preparata.
2. Il docente utilizza le slide per tenere la lezione e le carica su un server web.
3. Un’unità di lezione preparata viene inviata al **tutor** degli esercizi, il quale pianifica un nuovo esercizio se è necessario un nuovo foglio di esercizi. (I fogli di esercizi escono settimanalmente, mentre normalmente ci sono due unità di lezione a settimana.)
4. Dalla pianificazione dell’esercizio derivano un nuovo foglio di esercizi e le relative soluzioni.
5. Gli **studenti** ricevono il foglio, lo svolgono e lo consegnano ai loro tutor.
6. I tutor valutano le consegne utilizzando le soluzioni e caricano le valutazioni nel sistema KVV.

**Spiegazioni sui concetti di dominio:**
- Ogni valutazione è riferita a uno studente specifico. Anche se lo studente non ha consegnato l’esercizio, deve comunque esserci una valutazione nel sistema.
- Le unità di lezione possono essere **non preparate** o **preparate**.

**Elementi UML utili:**
- **Nodi di Decisione**: per controllo e flussi di dati con “decisionInput” (nodo di decisione.  ROMBI sia all'inizio della condizione che alla fine
- **Nodi oggetto con Stato** degli oggetti: nodi per sapere lo stato delle cose come in questo caso della lezione se è in corso se è completata ecc (“object node”).  QUADRATI
- **Webserver e KVV** possono essere modellati come **datastore** (“data store node”).
- **Flussi oggetto multipli**: con “multicast” per distribuire a più destinatari e “multireceive” per raccogliere da più fonti.  RETTANGOLI colorati di nero per azioni che vengono svolte contemporaneamente 
