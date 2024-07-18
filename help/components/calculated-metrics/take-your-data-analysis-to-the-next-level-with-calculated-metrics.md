---
title: Porta l’analisi dei dati a un livello successivo con le Metriche calcolate
description: Scopri in che modo un esperto peer utilizza le metriche calcolate per creare nuove metriche senza modificarne l’implementazione e utilizzando i dati già raccolti per rispondere a domande di business complesse.
feature: Calculated Metrics
role: User
level: Beginner
doc-type: Article
last-substantial-update: 2023-05-16T00:00:00Z
jira: KT-13266
thumbnail: KT-13266.jpeg
exl-id: 74793149-9967-4765-832c-c65e578ee34b
source-git-commit: d95136a21c08312a81baba7673cb7135270af4bd
workflow-type: tm+mt
source-wordcount: '1583'
ht-degree: 2%

---

# Porta l’analisi dei dati a un livello successivo con le Metriche calcolate

La maggior parte dei nuovi utenti di Adobe Analytics ha familiarità con i segmenti per suddividere i dati. Oggi voglio presentarvi le metriche calcolate, il prossimo strumento migliore nella vostra casella degli strumenti di analisi.

Come funzione avanzata di Adobe Analytics, le metriche calcolate consentono di creare nuove metriche senza modificare l’implementazione utilizzando i dati già raccolti. Il Generatore di metriche calcolate può utilizzare molte funzioni matematiche e statistiche diverse, quindi puoi creare metriche che rispondono anche alle domande di business più complesse.

## Introduzione alle metriche calcolate

Per iniziare a usare le metriche calcolate, vediamo un semplice esempio. Immagina di voler capire se gli utenti self-service online hanno un valore medio di ordine (AOV) più alto rispetto agli utenti assistiti da chiamate. Per creare una metrica calcolata che risponda a questa domanda, effettua le seguenti operazioni:

Per aprire il Generatore di metriche calcolate, utilizzare la navigazione superiore per fare clic su → **Componenti** → **Metriche calcolate** → **+ Aggiungi.** Oppure puoi fare clic sul segno **+** sopra a **Metriche** nel pannello Componenti.


![Calcolo 01](assets/calc01.png) ![Calcolo 02](assets/calc03.png) ![Calcolo 03](assets/calc02.png)

![Calcolo 04](assets/calc04.png)

*Descrizioni seguenti per gli elementi dell&#39;interfaccia utente*

Una volta aperto il Generatore di metriche calcolate, aggiungi e/o fai quanto segue:

**A.** Nome per la metrica calcolata. Questo nome viene visualizzato nell&#39;elenco dei componenti delle metriche, quindi rendilo chiaro per te e per gli altri, ad esempio *Call Center AOV*.

**B.** Descrizione della metrica calcolata. Questa descrizione viene visualizzata quando gli utenti fanno clic su &#39;**i**&#39; accanto alla metrica nell&#39;elenco dei componenti, quindi assicurati che sia informativa. Ad esempio, per il call center AOV, è possibile aggiungere *Calcola AOV per gli ordini assistiti dal call center*.

**C.** Il formato della metrica: Scegli decimale, ora, percentuale o valuta e aggiungi cifre decimali e polarità. In questo caso, sceglieremo *Valuta per il formato, 0 per il numero di decimali e* ⬆ *Buona (verde) per la polarità.*

**D**. Se utilizzi i tag, che consentono di applicare argomenti e individuare rapidamente le metriche calcolate, aggiungi i tag applicabili qui. Sono stati aggiunti *AOV* e *Tag del call center*.

**E.** Questa sezione è riservata alla visualizzazione. La formula verrà visualizzata qui quando si crea la metrica calcolata nella sezione F.

**F.** In questo caso trascinerai dimensioni (H), metriche (I) o segmenti (J) per creare la metrica calcolata e gli operatori per la formula. Per ogni metrica, se fai clic sulla rotellina del baricentro, puoi modificare il tipo di metrica (Standard/Totale) e il modello di attribuzione. *Trascinerò i ricavi del call center, quindi, sotto,*÷￼*. Accetteremo il tipo di metrica e il modello di attribuzione predefiniti.*

**G**. Utilizza questa opzione **+Aggiungi** per aggiungere altre condizioni o numeri statici, che qui non sono necessari.

**K.** Infine, durante la generazione dei calcoli, è possibile visualizzare in anteprima i dati degli ultimi 90 giorni qui.

Ora che abbiamo costruito il Call Center AOV, abbiamo anche bisogno di una metrica calcolata per il Call Center AOV online. A tal fine, seguiremo gli stessi passaggi descritti sopra.

Ora possiamo costruire una terza metrica calcolata, usando il Generatore di metriche calcolate o al volo dall&#39;interno della tabella a forma libera, per confrontare il Call Center e l&#39;AOV online e così finiamo con qualcosa di simile a questo:

![Calcolo 05](assets/calc05.png)

Nel nostro esempio, notiamo un incremento significativo quando i clienti utilizzano il call center per effettuare un acquisto. Questi dati possono quindi orientare le nostre decisioni su come aiutare i clienti a ottenere assistenza per i loro acquisti, ad esempio tramite offerte pop-up o altre esperienze guidate.

## Utilizzo dei segmenti nelle metriche calcolate

Vediamo ora come utilizzare i segmenti nelle metriche calcolate per acquisire maggiori informazioni sul comportamento, le preferenze e le motivazioni del cliente. Con i segmenti e le metriche calcolate, possiamo imparare abbastanza sui clienti per migliorarne l’esperienza, aumentare i ricavi e migliorare la soddisfazione e la fedeltà dei clienti.

Sappiamo già dagli esempi di AOV di cui sopra che gli acquisti assistiti dal call center hanno in genere un AOV più alto. Tuttavia, altre metriche ci dicono che la maggior parte degli utenti non utilizza il call center per gli acquisti.

Quindi, quali categorie di vendita al dettaglio - e i percorsi degli utenti attraverso tali categorie - risultano nel punteggio AOV più alto?  Possiamo scoprirlo combinando segmenti con metriche calcolate.

Per farlo, devi innanzitutto creare segmenti a livello di visita *include* e *exclude* per ogni categoria di prodotto. Includi o escludi è determinato facendo clic sull&#39;ingranaggio **Opzioni** nell&#39;angolo destro del contenitore. Il valore predefinito è Includi.

![Calcolo 06](assets/calc06.png) ![Calcolo 07](assets/calc07.png)

Dopo aver creato questi segmenti, possiamo creare una metrica calcolata per rispondere alla tua domanda. Viene aperto il Generatore di metriche calcolate ed è possibile effettuare le seguenti operazioni:

1. Cerca i segmenti appena creati e trascina quelli che desideri utilizzare nell&#39;area grigia nella parte superiore della casella **Definizione**. Ad esempio, se si desidera creare un valore aggiunto per gli utenti che hanno visitato le categorie Donne e Uomini, ma non Bambini, è possibile trascinare e rilasciare i tre segmenti seguenti nell&#39;area: *Includi donne*, *Includi uomini* e *Escludi bambini*. Si chiama *stacking dei segmenti*.

   ![Calcolo 09](assets/calc09.png) ![Calcolo 08](assets/calc08.png)

1. Trasciniamo quindi la metrica **Ricavi online** nello stesso contenitore, quindi **Ordini online**. Poiché i contenitori funzionano come espressioni matematiche per determinare l’ordine delle operazioni, gli elementi nei contenitori vengono elaborati prima dei processi successivi, anche se non sono presenti più contenitori o processi in questo calcolo.
1. L’operatore viene modificato da metrica a divisione (÷).
1. Abbiamo selezionato **Valuta** come formato, **0** cifre decimali e **SU** per la polarità.
1. Denomina la metrica calcolata e fornisci una descrizione.
1. Salva.

Al termine, la metrica calcolata sarà simile alla seguente:

![Calcolo 10](assets/calc10.png)

Dopo aver creato le metriche calcolate utilizzando segmenti impilati per ogni combinazione del percorso di categorie del visitatore e aver dato un’occhiata ai dati, osserva cosa abbiamo imparato. Gli utenti che durante la visita visitano sia le categorie Donne che Uomini hanno il valore AOV più alto e, se confrontati con i visitatori di una singola categoria, l’incremento è significativo:

![Calcolo 11](assets/calc11.png) ![Calcolo 12](assets/calc12.png)

Sapendo questo, possiamo ottimizzare il layout di pagina, il posizionamento dei prodotti e i messaggi promozionali per inserire più persone in queste categorie prima del check-out.

## Prezioso, ma non disponibile ovunque

**Quindi - le metriche calcolate, semplici e complesse, sono di grande valore per gli analisti!**

Tuttavia, queste metriche non sono disponibili in tutte le aree di Adobe Analytics. Non puoi utilizzare metriche calcolate in:

- Abbandono in Analysis Workspace
- Analisi di coorte in Analysis Workspace
- Data Warehouse
- Rapporti in tempo reale
- Rapporti sui dati correnti
- Analytics for Target
- Report Builder

## Best practice per le metriche calcolate

Ora che sai quanto possono essere preziose le metriche calcolate, vediamo alcune best practice per crearle.

1. **Verifica la sintassi della formula.** Assicurarsi che la sintassi della formula sia corretta e che segua la sintassi Adobe Analytics per ottenere informazioni significative.
1. **Verificare l&#39;ordine delle operazioni.** Assicurarsi di utilizzare i contenitori con attenzione e di disporre le operazioni nell&#39;ordine matematico corretto.
1. **Non conteggiare due volte i dati**. Puoi evitare il doppio conteggio dei dati assicurandoti che la formula utilizzata nella metrica calcolata non conti più volte gli stessi dati. Ciò si ottiene spesso combinando le condizioni *Includi* e *Escludi* nella metrica calcolata o tramite l&#39;utilizzo di segmenti.
1. **Verifica la granularità temporale.** Assicurarsi che la metrica calcolata abbia la stessa granularità temporale delle metriche di origine utilizzate nella formula.
1. **Utilizza dati accurati:** Otterrai risultati importanti solo se nel calcolo utilizzi dati accurati e affidabili.

## Best practice per i segmenti personalizzati

Quando crei segmenti in Adobe Analytics, tieni presenti le best practice seguenti:

1. **Semplifica.** Evita di complicare eccessivamente il segmento. Conservarla nel modo più semplice possibile e utilizzare solo le condizioni necessarie per garantire la precisione.
1. **Utilizzare i tipi di contenitore corretti**. Assicurati di utilizzare il tipo di contenitore corretto (visitatore, visita o hit) nella definizione del segmento per evitare di ottenere risultati errati.
1. **Non conteggiare due volte i dati**. Come per le metriche calcolate, assicurati che il segmento non conti più volte gli stessi dati. I contenitori Includi ed Escludi possono essere utili.
   1. Quando viene utilizzato un contenitore di inclusione, *include* *tutto il contenuto della visita* se un hit corrisponde alla condizione all&#39;interno della visita.
   1. Quando viene utilizzato un contenitore di esclusione, *esclude tutto il contenuto della visita* se un hit corrisponde alla condizione all&#39;interno della visita.
1. **Nidificare correttamente i contenitori**. Determina i dati inclusi utilizzando il contenitore più esterno, quindi applica le regole nidificate ai dati rimanenti. Quando vengono applicate le regole nidificate, il flusso di segmenti agisce come un funnel e le regole successive non si applicano agli hit esclusi dalla prima regola.
1. **Assicurarsi che i dati siano aggiornati.** Per ottenere risultati accurati, assicurati di utilizzare dati accurati e aggiornati nella definizione del segmento.
1. **Verifica il segmento.** Eseguire sempre il test del segmento per verificare che funzioni come previsto prima di rilasciarlo ad altri.
1. **Considerare le prestazioni.** I segmenti possono rallentare l&#39;elaborazione del rapporto, quindi considera tale impatto durante la creazione.

## Conclusioni principali

La combinazione di segmenti e metriche calcolate in Adobe Analytics può sicuramente portare ad un’analisi dei dati più solida ed efficace. Suddividendo in porzioni e indicando i dati e creando calcoli a scopo di confronto, puoi ottenere informazioni più approfondite sul comportamento dei clienti, utili per ottimizzare le campagne di marketing e creare dashboard e rapporti personalizzati. Tuttavia, ricorda che le metriche calcolate non sono disponibili in tutte le aree di Adobe Analytics e assicurati di seguire le best practice per ottenere dati accurati e utili.


## Autore

Questo documento è stato scritto da:

![Debbie Kern](assets/calc13.jpeg)

**Debbie Kern**, Senior Adobe Analytics Manager presso Adswerve

![Adswerve](assets/calc14.png)
