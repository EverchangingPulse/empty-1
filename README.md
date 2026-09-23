# Raven Studio

**Raven Studio** è un'applicazione web standalone per esercizi di ragionamento astratto e visuospaziale basati su matrici logiche 3×3.

Genera dinamicamente problemi visivi nei quali bisogna individuare la figura mancante scegliendo fra otto possibili risposte. Include numerose famiglie di esercizi, livelli di difficoltà differenti, spiegazioni degli errori e una modalità di **test adattivo** che modifica progressivamente la complessità degli esercizi in funzione delle risposte date.

Raven Studio funziona interamente nel browser: dopo il download non richiede server, installazione, account o connessione Internet.

> **Importante:** Raven Studio è uno strumento sperimentale di esercitazione e valutazione relativa del ragionamento visivo. Non è un test di intelligenza standardizzato. I suoi punteggi non devono essere interpretati come IQ, diagnosi cliniche o valutazioni psicometriche certificate.

## Download diretto

**[Scarica Raven Studio come file HTML](https://github.com/EverchangingPulse/empty-1/raw/refs/heads/main/raven-studio.html)**

Dopo il download, apri `raven-studio.html` con un browser moderno. Il file è autonomo e può essere conservato, copiato o utilizzato offline.

Il repository contiene anche `index.html`, equivalente alla versione standalone corrente.

## A cosa serve

Raven Studio è progettato per esercitare e osservare diverse componenti del ragionamento astratto:

- identificazione di regole visive;
- ragionamento visuospaziale;
- rotazione mentale;
- trasformazioni geometriche;
- memoria di lavoro visiva;
- confronto simultaneo di più proprietà;
- composizione e decomposizione di figure;
- riconoscimento di sequenze;
- logica insiemistica e booleana;
- individuazione di relazioni fra righe e colonne;
- controllo di più regole indipendenti nello stesso problema.

Alcuni esercizi richiedono di seguire una sola trasformazione, mentre quelli più complessi combinano più proprietà contemporaneamente.

## Modalità di utilizzo

### Test adattivo

La modalità principale è il **Test adattivo**.

Il test parte con esercizi di calibrazione e successivamente sceglie esercizi vicini alla difficoltà stimata per la persona. Una risposta corretta tende a spostare la selezione verso esercizi più complessi, mentre una risposta errata tende a spostarla verso esercizi meno complessi.

Il sistema cerca inoltre di alternare famiglie di esercizi differenti per evitare che il risultato dipenda eccessivamente da un singolo tipo di matrice.

Per impostazione predefinita, i valori di difficoltà e punteggio sono nascosti durante il test, così l'interfaccia non suggerisce indirettamente se la risposta precedente fosse corretta. L'utente può scegliere di mostrarli tramite l'apposita opzione.

Il test può essere configurato con un limite temporale e un numero massimo di esercizi.

### Esercizio singolo

La modalità **Esercizio singolo** permette di scegliere direttamente:

- il tipo di esercizio;
- il livello di difficoltà;
- eventuali operazioni logiche;
- specifiche trasformazioni.

È utile per esercitarsi su una particolare categoria o per studiare nel dettaglio una regola.

## Tipi di esercizi

Il programma include numerose categorie generate proceduralmente, tra cui:

- Operazioni su Griglie;
- Logica con Copertura Mobile;
- Trasformazioni su Griglia;
- Operazioni sul Contorno;
- Progressioni di Figure;
- Cicli di Trasformazione;
- Spostamenti su Griglia;
- Disposizioni di Punti;
- Composizioni di Linee;
- Operazioni su Mini-Griglie;
- Blocchi e Rotazioni;
- Forme e Riempimenti;
- Riempimenti Diagonali;
- Ordine dei Simboli;
- Composizione di Figure;
- Raggi e Orientamenti;
- Sequenze e Quantità;
- Riempimenti su Mini-Griglia;
- Motivi Radiali;
- Bilanciamento di Blocchi;
- Bilanciamento di Punti;
- Sovrapposizione di Segmenti.

Gli esercizi possono combinare rotazione, traslazione, specchiatura, variazioni di scala, composizione, sovrapposizione, operazioni logiche e trasformazioni dei pattern.

## Logica booleana e inferibilità

Alcune matrici applicano una funzione tra due gruppi di elementi. Le operazioni possono includere:

- OR / unione;
- XOR / presenza in uno solo dei gruppi;
- AND / intersezione;
- sottrazione;
- somma con molteplicità.

Il generatore è progettato affinché i comportamenti necessari per risolvere l'ultima riga siano già inferibili dai gruppi completi precedenti.

La copertura mobile può nascondere una parte dell'informazione, ma non deve eliminare contemporaneamente causa ed effetto dello stesso caso discriminante. La trasformazione deve quindi rimanere deducibile da ciò che è visibile.

Ai livelli superiori aumenta il carico visuospaziale, ma la densità non viene spinta fino al riempimento quasi totale della mini-griglia: troppe celle piene permetterebbero di ragionare semplicemente sulle poche celle vuote.

## Operazioni sul contorno

Alcuni problemi distribuiscono simboli lungo il perimetro di una figura e possono combinare:

- rotazione;
- specchiatura;
- spostamento dei simboli lungo il contorno;
- scambio fra figura esterna e simbolo ripetuto;
- variazioni di riempimento;
- coperture mobili.

Le spiegazioni usano riferimenti visivi naturali come **alto**, **alto-destra**, **destra**, **basso-destra**, **basso**, **basso-sinistra**, **sinistra** e **alto-sinistra**, invece della nomenclatura interna del generatore.

## Risposte e distrattori

Ogni esercizio presenta otto possibili risposte.

Il generatore applica controlli automatici affinché:

- la risposta corretta sia presente;
- la risposta corretta compaia una sola volta;
- tutte le alternative siano visivamente distinguibili;
- proprietà completamente nascoste da una copertura non rendano artificialmente diverse due risposte che appaiono uguali;
- siano presenti distrattori vicini alla soluzione;
- la risposta corretta non sia riconoscibile per un giveaway visivo accidentale.

Diverse famiglie producono deliberatamente **near-miss**, cioè alternative quasi corrette che differiscono dalla soluzione per una sola proprietà significativa.

## Spiegazioni

Quando il feedback è abilitato, il programma può spiegare:

- quale regola era richiesta;
- quali proprietà della risposta scelta erano corrette;
- quali proprietà erano sbagliate;
- dove dovevano comparire punti, segmenti o simboli;
- quale rotazione, posizione, riempimento o trasformazione era necessaria;
- quali elementi mancavano;
- quali elementi erano presenti in più.

Le spiegazioni sono formulate in termini dell'aspetto effettivo della figura e non dei nomi dei campi interni usati dal codice.

## Difficoltà adattiva

Raven Studio usa una scala interna di difficoltà relativa per:

- confrontare gli esercizi;
- selezionare il successivo esercizio nel test adattivo;
- stimare la zona di difficoltà alla quale la persona riesce a lavorare.

La difficoltà può anche essere presentata con categorie qualitative come **Molto facile**, **Facile**, **Media**, **Difficile** e **Molto difficile**.

La scala numerica interna **non è un punteggio IQ** e non deve essere convertita direttamente in IQ o percentili senza una validazione psicometrica appropriata.

## Feedback e visibilità dei punteggi

Durante il test adattivo è possibile scegliere se mostrare i valori di difficoltà e la stima adattiva.

Con la visualizzazione disattivata, questi valori restano nascosti per evitare che un aumento o una diminuzione della difficoltà suggerisca indirettamente l'esito della risposta precedente.

Con la visualizzazione attivata, il programma può mostrare sia il valore numerico sia la relativa categoria qualitativa.

## Risposte troppo rapide

Il programma utilizza una soglia minima di latenza per evitare che click accidentali o risposte praticamente istantanee influenzino la stima adattiva.

Le risposte al di sotto della soglia possono essere conservate nei dati della sessione ma escluse dalla valutazione e dall'adattamento.

## Riproducibilità

Ogni matrice possiede un **seed**.

Usando lo stesso seed e le stesse impostazioni è possibile ricreare lo stesso esercizio. Questo è utile per debugging, analisi degli errori, confronto fra versioni e segnalazione di matrici problematiche.

## Utilizzo offline e privacy

Raven Studio è contenuto in un singolo file HTML e non richiede:

- backend;
- database;
- installazione;
- Node.js;
- Python;
- account utente;
- connessione a servizi esterni.

La logica del test viene eseguita localmente nel browser.

## Browser consigliati

È consigliata una versione recente di:

- Chrome / Chromium;
- Microsoft Edge;
- Firefox;
- Safari.

L'interfaccia è progettata anche per schermi mobili.

## Come iniziare

1. Scarica `raven-studio.html`.
2. Aprilo con il browser.
3. Seleziona **Test adattivo** oppure **Esercizio singolo**.
4. Nel test adattivo imposta durata e numero massimo di esercizi, se necessario.
5. Avvia la sessione.
6. Seleziona una delle otto risposte per ogni matrice.
7. Consulta il riepilogo al termine.

## Interpretazione dei risultati

Raven Studio non deve essere usato da solo per formulare conclusioni cliniche o psicologiche.

In particolare:

- non fornisce un IQ standardizzato;
- non sostituisce Raven's Progressive Matrices ufficiali;
- non sostituisce una valutazione neuropsicologica;
- non fornisce diagnosi;
- non dispone ancora di norme rappresentative della popolazione generale.

Il risultato adattivo va interpretato come una misura **interna e relativa alla banca di esercizi generata dal programma**.

## Qualità del generatore

Il progetto include controlli destinati a prevenire problemi tipici delle matrici generate proceduralmente:

- risposte duplicate;
- soluzione mancante;
- più soluzioni apparentemente corrette;
- stati interni differenti ma immagini finali identiche;
- indizi accidentali che rendono la soluzione troppo facile;
- casi logici presenti soltanto nella riga da completare;
- regole non inferibili dai gruppi di controllo;
- coperture che eliminano l'informazione necessaria;
- distrattori troppo lontani dalla soluzione.

Durante lo sviluppo il generatore è stato sottoposto a test automatici su grandi quantità di seed e, per le famiglie più delicate, anche a confronti del rendering visivo.

## Licenza

Il materiale originale di Raven Studio per il quale gli autori di questo repository possiedono i diritti è distribuito secondo la **Apache License 2.0**.

Consulta:

- [LICENSE](LICENSE)
- [NOTICE](NOTICE)
- [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md)

La licenza Apache-2.0 **non pretende di rilicenziare materiale di terzi** sul quale gli autori di questo repository non possiedono autorità.

## Attribuzioni e materiale precedente

Raven Studio deriva in parte da lavoro e idee presenti in:

**pyRavenMatrices — Can Mekik**  
https://github.com/cmekik/pyRavenMatrices

Una fase iniziale di Raven Studio ha analizzato e adattato alcune geometrie e strutture provenienti da quel progetto.

I diritti sul materiale originale rimangono dei rispettivi titolari. Al momento della preparazione di questo repository non è stata verificata nel repository upstream una licenza software esplicita che autorizzi a considerare quel materiale Apache-2.0.

Per questo motivo il presente repository conserva esplicitamente l'attribuzione e limita la propria dichiarazione di licenza al materiale per il quale i suoi autori hanno effettivamente autorità.

Per i dettagli consulta [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md).

## Segnalare problemi

Le segnalazioni più utili riguardano:

- matrici ambigue;
- soluzioni apparentemente duplicate;
- spiegazioni poco chiare;
- problemi di rendering;
- difficoltà incoerente;
- regole non inferibili;
- problemi su dispositivi mobili.

Quando possibile, includi:

- seed;
- tipo di esercizio;
- livello;
- screenshot;
- browser utilizzato.

Questo permette di riprodurre esattamente la matrice.

---

Raven Studio è un progetto sperimentale dedicato allo studio e all'esercizio del ragionamento visivo generato proceduralmente.
