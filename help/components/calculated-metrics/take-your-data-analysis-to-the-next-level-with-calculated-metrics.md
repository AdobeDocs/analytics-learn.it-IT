---
title: Effettua l’analisi dei dati a un livello successivo con Metriche calcolate
description: Scopri in che modo un esperto peer utilizza le metriche calcolate per creare nuove metriche senza modificarne l’implementazione e utilizzando i dati già raccolti per rispondere a domande aziendali complesse.
feature: Calculated Metrics
role: User
level: Beginner
doc-type: Article
last-substantial-update: 2023-05-16T00:00:00Z
jira: KT-13266
thumbnail: KT-13266.jpeg
source-git-commit: c64f2fde1b91edd9f3d6c0f87aa889ed2c613d9b
workflow-type: tm+mt
source-wordcount: '1566'
ht-degree: 1%

---


# Effettua l’analisi dei dati a un livello successivo con Metriche calcolate

La maggior parte dei nuovi utenti di Adobe Analytics conosce i segmenti come modo per suddividere i loro dati. Oggi, voglio presentarvi le metriche calcolate, il prossimo miglior strumento nella vostra casella degli strumenti di analisi.

In qualità di funzionalità avanzata di Adobe Analytics, le metriche calcolate ti consentono di creare nuove metriche senza modificare l’implementazione utilizzando i dati già raccolti. Il Generatore di metriche calcolate può utilizzare molte funzioni matematiche e statistiche diverse, per cui è possibile creare metriche che rispondano anche alle domande aziendali più complesse.

## Guida introduttiva alle metriche calcolate

Per iniziare a usare le metriche calcolate, vediamo un semplice esempio. Immagina di voler capire se gli utenti self-service online hanno un valore medio di ordine più alto (AOV) rispetto agli utenti assistiti da chiamate. Per creare una metrica calcolata per rispondere a questa domanda, procedi come segue:

Per aprire il Generatore di metriche calcolate, utilizza la navigazione superiore per fare clic su → **Componenti** → **Metriche calcolate** → **+ Aggiungi** Oppure, puoi fare clic sul pulsante **segno +** sopra **Metriche** nel pannello Componenti .


![Calc 01](assets/calc01.png) ![Calc 02](assets/calc03.png) ![Calc 03](assets/calc02.png)

![Calc 04](assets/calc04.png)

*Descrizioni di seguito per gli elementi dell&#39;interfaccia utente*

Una volta aperto il Generatore di metriche calcolate, aggiungi e/o esegui le seguenti operazioni:

**A.** Un nome per la metrica calcolata. Questo nome viene visualizzato nell’elenco dei componenti della metrica, quindi rendetelo chiaro a te stesso e agli altri, come *AOV del call center*.

**B.** Una descrizione della metrica calcolata. Questa descrizione viene visualizzata quando gli utenti fanno clic su &quot;**i**&quot; accanto alla metrica nell’elenco dei componenti, assicurati che sia informativa. Ad esempio, per AOV del call center, è possibile aggiungere *Calcola l&#39;AOV per gli ordini assistiti dal call center*.

**C.** Formato della metrica: Selezionare decimale, ora, percentuale o valuta e aggiungere posizioni decimali e polarità. Ecco, sceglieremo *Valuta per il formato, 0 per il numero di decimali e* ⬆ *Buono (verde) per polarità.*

**D**. Se utilizzi dei tag che ti consentono di applicare argomenti e individuare rapidamente le metriche calcolate, aggiungi i tag applicabili qui. Abbiamo aggiunto *AOV* e *Call center* tag.

**E.** Questa sezione è per la visualizzazione: quando si crea la metrica calcolata nella sezione F, la formula verrà visualizzata qui.

**F.** In questo caso, puoi trascinare dimensioni (H), metriche (I) o segmenti (J) per creare la metrica calcolata e gli operatori per la formula. Per ogni metrica, se fai clic sulla ruota dentata, puoi modificare il Tipo di metrica (Standard/Totale) e il Modello di attribuzione. *Trascineremo i Ricavi da call center, poi sotto,*÷ ￼*. Accetteremo il tipo di metrica e il modello di attribuzione predefiniti.*

**G**. Utilizza questo **+Aggiungi** opzione per aggiungere condizioni aggiuntive o numeri statici, che non sono necessari in questo caso.

**K.** E infine, costruendo i vostri calcoli, potete vedere in anteprima i dati degli ultimi 90 giorni qui.

Ora che abbiamo costruito l&#39;AOV del call center, abbiamo anche bisogno di una metrica calcolata per l&#39;AOV online. Lo faremo seguendo gli stessi passaggi sopra descritti.

Ora possiamo creare una terza metrica calcolata, utilizzando il Generatore di metriche calcolate o direttamente dalla tabella a forma libera, per confrontare il Call Center e il AOV online in modo da ottenere qualcosa di simile a questo:

![Calc 05](assets/calc05.png)

Nel nostro esempio, vediamo un incremento significativo quando gli acquirenti utilizzano il call center per aiutarli a fare un acquisto. Questi dati possono quindi informare le nostre decisioni su come aiutare i clienti ad ottenere assistenza sui loro acquisti, ad esempio tramite offerte a comparsa o altre esperienze guidate.

## Utilizzo dei segmenti nelle metriche calcolate

Ora, vediamo come possiamo utilizzare i segmenti nelle metriche calcolate per acquisire maggiori informazioni sul comportamento, le preferenze e le motivazioni del cliente. Con i segmenti e le metriche calcolate, possiamo imparare abbastanza sui clienti per migliorare la loro esperienza, aumentare i ricavi e migliorare la soddisfazione e la fedeltà dei clienti.

Sappiamo già dagli esempi AOV di cui sopra che gli acquisti assistiti dai call center hanno generalmente un AOV più alto. Tuttavia, altre metriche indicano che la maggior parte degli utenti non utilizza il call center per gli acquisti.

Quindi, quali categorie di vendita al dettaglio - e i percorsi degli utenti attraverso queste categorie - portano al più alto AOV?  Possiamo scoprirlo combinando segmenti con metriche calcolate.

Per farlo, dobbiamo prima creare a livello di visita *include* e *escludere* segmenti per ogni categoria di prodotto. L’opzione Includi o escludi è determinata facendo clic sul pulsante **Opzioni** nell’angolo a destra del contenitore. Il valore predefinito è Includi.

![Calc 06](assets/calc06.png) ![Calc 07](assets/calc07.png)

Una volta creati questi segmenti, possiamo creare una metrica calcolata per darvi la risposta alla vostra domanda. Aprite il Generatore di metriche calcolate ed effettuate le seguenti operazioni:

1. Cerca i segmenti appena creati e trascina e rilascia quelli che desideri utilizzare nell’area grigia nella parte superiore della **Definizione** scatola. Ad esempio, se desideri creare un AOV per gli utenti che hanno visitato le categorie Donne e Uomini, ma non quella dei Bambini, possiamo trascinare e rilasciare questi tre segmenti in tale area: *Include*, *Inclusi Uomini* e *Escludi*. Lo chiamiamo *impilare segmenti*.

   ![Calc 09](assets/calc09.png) ![Calc 08](assets/calc08.png)

1. Poi, trasciniamo e rilasciamo il **Ricavi online** nello stesso contenitore, quindi **Ordini online**. Poiché i contenitori funzionano come espressioni matematiche per determinare l’ordine delle operazioni, gli elementi nei contenitori vengono elaborati prima dei processi successivi, anche se in questo calcolo non sono presenti più contenitori o processi.
1. Cambiamo l’operatore tra le due metriche in divisione (÷).
1. Selezione **Valuta** come formato, **0** posizioni decimali e **SU** per polarità.
1. Denomina la metrica calcolata e fornisci una descrizione.
1. Salva.

Al termine, la metrica calcolata si presenta così:

![Calc 10](assets/calc10.png)

Dopo aver creato metriche calcolate utilizzando segmenti sovrapposti per ogni combinazione di percorso di categorie di visitatori e dato un&#39;occhiata ai dati, guarda cosa impariamo! Gli utenti che visitano sia le categorie Donne che Uomini durante la visita hanno il più alto AOV e, se confrontati con i visitatori di una singola categoria, l’incremento è significativo:

![Calc. 11](assets/calc11.png) ![Calc 12](assets/calc12.png)

A questo scopo, possiamo ottimizzare il layout di pagina, i posizionamenti dei prodotti e i messaggi promozionali per coinvolgere più persone in queste categorie prima di effettuare il check-out.

## Prezioso, ma non disponibile ovunque

**Le metriche calcolate, sia semplici che complesse, sono estremamente utili per gli analisti!**

Tuttavia, queste metriche non sono disponibili in tutte le aree di Adobe Analytics. Non è possibile utilizzare le metriche calcolate in:

- Abbandono in Analysis Workspace
- Analisi di coorte in Analysis Workspace
- Data Warehouse
- Rapporti in tempo reale
- Rapporti dati correnti
- Analytics for Target
- Report Builder

## Tecniche consigliate per le metriche calcolate

Ora che sai quanto possono essere preziose le metriche calcolate, diamo un’occhiata ad alcune best practice per crearle.

1. **Controlla la sintassi della formula.** Assicurati che la sintassi della formula sia corretta e segua la sintassi Adobe Analytics per assicurarti di ottenere informazioni significative.
1. **Verifica l’ordine delle operazioni.** Assicurati di utilizzare i contenitori con attenzione e mettere le cose in un corretto ordine matematico delle operazioni.
1. **Non contare due volte i dati**. Puoi evitare il doppio conteggio dei dati assicurando che la formula utilizzata nella metrica calcolata non conti più gli stessi dati. Spesso si ottiene combinando *Includi* e *Escludi* condizioni nella metrica calcolata o tramite l’uso di segmenti.
1. **Controlla la granularità del tempo.** Assicurati che la metrica calcolata abbia la stessa granularità temporale delle metriche di origine utilizzate nella formula.
1. **Utilizzare dati precisi:** Si otterrà risultati preziosi solo se si utilizzano dati accurati e affidabili nel calcolo.

## Tecniche consigliate per i segmenti personalizzati

Durante la creazione di segmenti in Adobe Analytics, tieni presente le seguenti best practice:

1. **La tenga semplice.** Evita di complicare eccessivamente il segmento. Mantenere il più semplice possibile e utilizzare solo le condizioni necessarie per garantire la precisione.
1. **Utilizza i tipi di contenitore corretti**. Assicurati di utilizzare il tipo di contenitore corretto (visitatore, visita o hit) nella definizione del segmento per evitare di ottenere risultati errati.
1. **Non contare due volte i dati**. Come per le metriche calcolate, assicurati che il segmento non conteggi più volte gli stessi dati. Possono essere utili i contenitori Includi ed Escludi .
   1. Quando si utilizza un contenitore di inclusione, questo *include* *tutti i contenuti della visita* se un hit corrisponde alla condizione all’interno della visita.
   1. Quando si utilizza un contenitore di esclusione, questo *esclude tutti i contenuti della visita* se un hit corrisponde alla condizione all’interno della visita.
1. **Nidificare correttamente i contenitori**. Determina i dati inclusi utilizzando il contenitore più esterno, quindi applica le regole nidificate ai dati rimanenti. Quando si applicano le regole nidificate, il flusso di segmenti agisce come funnel e le regole successive non si applicano agli hit esclusi dalla prima regola.
1. **Assicurati che i tuoi dati siano aggiornati.** Assicurati di utilizzare dati precisi e aggiornati nella definizione del segmento per ottenere risultati precisi.
1. **Verifica il segmento.** Esegui sempre il test del segmento per assicurarti che funzioni come previsto prima di rilasciarlo ad altri.
1. **Considera le prestazioni.** I segmenti possono rallentare l’elaborazione dei rapporti, pertanto considera tale impatto durante la loro creazione.

## Conclusioni principali

La combinazione di segmenti e metriche calcolate in Adobe Analytics può portare ad un’analisi dei dati più solida ed efficace. Affettare e suddividere i dati e generare calcoli per il confronto ti consente di ottenere informazioni più approfondite sul comportamento dei clienti da utilizzare per ottimizzare le campagne di marketing e creare dashboard e rapporti personalizzati. Tuttavia, ricorda che le metriche calcolate non sono disponibili in tutte le aree di Adobe Analytics e assicurati di seguire le best practice per assicurarti di ottenere dati accurati e utili.


## Autore

Questo documento è stato scritto da:

![Debbie Kern](assets/calc13.jpeg)

**Debbie Kern**, Senior Adobe Analytics Manager di Adswerve

![Adswerve](assets/calc14.png)
