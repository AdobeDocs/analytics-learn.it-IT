---
title: Creazione di segmenti di percorso di clienti - parte due
description: Nella parte due, scopri come creare segmenti di intento per visite di acquisto e fidelizzazione per comprendere il percorso di acquisto dei clienti e personalizzare i contenuti. Utilizzando segnali come i clic o gli accessi "Book Now", identifichiamo l’intento di acquisto e conservazione per un’analisi efficace e un marketing mirato.
feature: Segmentation
role: User
level: Experienced
last-substantial-update: 2023-07-21T00:00:00Z
jira: KT-13476
thumbnail: KT-13476.jpeg
exl-id: 2db73010-5cd0-4454-a4ba-fc1667a50cba
source-git-commit: d95136a21c08312a81baba7673cb7135270af4bd
workflow-type: tm+mt
source-wordcount: '1997'
ht-degree: 0%

---

# Creazione di segmenti di percorso di clienti - parte due

Nella parte due, scopri come creare segmenti di intento per visite di acquisto e fidelizzazione per comprendere il percorso di acquisto dei clienti e personalizzare i contenuti. Utilizzando segnali come i clic o gli accessi &quot;Book Now&quot;, identifichiamo l’intento di acquisto e conservazione per un’analisi efficace e un marketing mirato.

## Creazione di segmenti intento di visita acquisto e mantenimento

Nell’ultimo post, abbiamo descritto il processo di creazione dei segmenti di intento di visita e abbiamo creato il nostro primo segmento di intento di visita, One Hit Wonders. Oggi svilupperemo i nostri segmenti di acquisto e fidelizzazione. Abbiamo segmentato circa il 23% delle visite e costruito i segnaposto per i restanti segmenti Intento di visita.

![Immagine 1](assets/Image-1.png)

I segmenti di intento di visita che stiamo creando ora sono alla base della creazione di segmenti di percorso cliente basati sui visitatori. Creeremo questi segmenti di percorso basati su visitatori dopo aver creato i segmenti di intento della visita.

Ricorda che la creazione di segmenti di intento di visita è un processo di eliminazione. Quindi, non stiamo costruendo questi segmenti in ordine cronologico. Stiamo creando i segmenti di intento della visita in ordine dal più semplice da definire e definire con maggiore precisione:

1. Intento: 0 - One Hit Wonders
1. Intento: 3 - Acquisto
1. Intento: 4 - Mantenimento
1. Intento: 2 - Considerazione
1. Intento: 1 - Consapevolezza

Nel nostro ultimo post, ho chiamato il segmento &quot;Acquisto&quot; &quot;Prenotazione&quot; da quando sono nel business dei viaggi. Ma andando avanti lo chiameremo il segmento di acquisto per rendere più facile l&#39;applicazione a più settori.

Più è chiaro il segnale, più è facile creare il segmento. Nel nostro ultimo post, abbiamo creato il segmento One Hit Wonders, che era il più semplice da definire poiché si trattava solo di traffico non recapitato. Troverai che anche i segmenti di intento di acquisto e mantenimento sono molto facili da definire, in quanto si basano su segnali molto chiari.

## Il Percorso del cliente è diverso dalla propensione all&#39;acquisto

Nel valutare la creazione del segmento Intento di acquisto, è importante tenere presente che identificare la posizione di un cliente nel percorso è diverso dalla propensione. Potresti avere alcuni modelli di propensione all’acquisto che assegnano un punteggio ai visitatori web per prevedere la probabilità che effettuino un acquisto. Questi modelli sono super utili, ma sono diversi dal segmento Intento di acquisto che creeremo oggi.

Mentre un modello di propensione cerca di prevedere se un visitatore acquisterà, i nostri segmenti di Intento di Visita cercano di capire dove si trova una persona nel percorso di acquisto. L’utilizzo dei segmenti Intent per comprendere lo stato mentale di un cliente ci aiuta a personalizzare i contenuti e a personalizzare il marketing per indirizzare il traffico giusto per alimentare la nostra pipeline di vendita. Pertanto, il segmento Intento di acquisto cerca segnali comportamentali espliciti che indicano che un visitatore sta cercando di effettuare un acquisto.

## Creazione del segmento di intento della visita di acquisto

Il segmento Intento visita di acquisto è facile da definire. Nel mio caso, chiunque clicchi sul pulsante &quot;Prenota ora&quot; sta indicando una sorta di intenzione di prenotare una crociera. È simile a fare clic su &quot;Pagamento&quot; per un retailer online o su un collegamento &quot;Abbonati&quot; in un contesto multimediale.

Sarà necessario esercitare un certo giudizio quando si decide quale segnale utilizzare per dedurre l&#39;intento di acquisto. Vogliamo che il segmento Intento di acquisto contenga tutti gli acquisti, ma il tasso di conversione non deve essere del 100%. Pertanto, non è necessario utilizzare la pagina di conferma o ringraziamento dell’acquisto per questo segmento.

Allo stesso modo, la pagina Rivedi il tuo acquisto (o qualsiasi cosa si trovi immediatamente prima della conferma dell’acquisto) è probabilmente troppo in basso per funnel per essere utile per l’analisi e il targeting.

Andando oltre il funnel, può risultare meno chiaro se il segnale è utile o meno per indicare che un cliente intende effettuare un acquisto. Nel mio caso, &quot;Book Now&quot; è simile al collegamento &quot;Checkout&quot; di una vendita al dettaglio, e questo è il segnale che ho utilizzato. Ma in un contesto di vendita al dettaglio, Checkout potrebbe essere ancora troppo in basso nel funnel e Visualizza carrello o anche Aggiungi al carrello potrebbe essere meglio.

Possiamo immaginarlo come un negozio di alimentari. Se qualcuno ritira un prodotto dallo scaffale, non significa che abbia intenzione di comprarlo. Anche se lo mettono nel carrello, possono subito rimetterlo sullo scaffale. Ma se mettono il prodotto nel carrello e iniziano a camminare con esso, c&#39;è una buona probabilità che intendono comprarlo. E se entrano nella catena di pagamento con quel prodotto è una buona scommessa che compreranno.

Suggerisco di utilizzare le pagine visitate o altri segnali espliciti di intento di acquisto ed evitare altri segnali meno diretti per identificare l’intento di acquisto. Ad esempio, non utilizzerei il numero di sessioni o il numero di pagine in una sessione o simile. Questi segnali indiretti indicano Considerazione, non Intento di acquisto. Ricorda che lo scopo di questo segmento è di dedurre l’intento del visitatore per la visita, non la sua propensione.

### Utilizzo di Analytics Workspace per identificare i segnali di intento di acquisto

Il rapporto Fallout è molto utile per identificare un buon segnale che indica l’intento di acquisto. Cercate un luogo che indichi in modo logico l&#39;intento. Puoi confermare che il passaggio indica l’intento quando visualizzi un abbandono rilevante che avanza in quel passaggio, spesso seguito da un abbandono più piccolo per il passaggio immediatamente successivo.

![Immagine 2](assets/Image-2.png)

È utile anche esaminare i tassi di conversione associati alle varie pagine del sito. Questa funzione è particolarmente utile per identificare le pagine che indicano la finalità di acquisto, ma che potrebbero non essere necessarie per effettuare un acquisto (ad esempio pagine di finanziamento, pagine di configurazione dell’acquisto, ecc.).

![Immagine 3](assets/Image-3.png)

Infine, è importante includere nel segmento tutte le pagine comprese tra l’inizio dell’acquisto e la conferma dell’acquisto. I visitatori possono eseguire il bounce e rientrare nel flusso di acquisto in punti diversi.

### Esclusione di altri segmenti

Ricorda dal nostro primo post che i nostri segmenti di Intento di Visita devono essere reciprocamente esclusivi e completamente esaustivi. Questo è un ritornello che sentirete molto in questa serie.

Assicurati che il segmento Intento di acquisto escluda il segmento Uno e Fine. Dovresti escludere solo il segmento One (Uno) e Done (Fine), in quanto i segnali utilizzati per l’intento di acquisto sono molto specifici.

Tieni presente che l’esclusione del segmento One and Done potrebbe escludere gli utenti che accedono nuovamente al sito in una pagina di pagamento. Non si tratta di un errore. La definizione stessa di One and Done è una visualizzazione di pagina, il che significa che anche se un visitatore entra o si aggiorna in una pagina di pagamento, la sua visita non è andata avanti, quindi non c’è alcuna espressione di intento di acquisto.

### Segmento della finalità di acquisto nel Generatore di segmenti

La definizione del segmento per Intento di acquisto è molto semplice.

Utilizzando il contenitore Visita, includi le pagine o altre azioni che indicano esplicitamente l’intenzione di effettuare un acquisto. Se disponi di più condizioni di inclusione, assicurati di inserirle in un contenitore unito dalla condizione &quot;E&quot;.

Aggiungi un contenitore Escludi al segmento unito dalla condizione &quot;And&quot;. Aggiungi la definizione del segmento One Hit Wonders (Page Views = 1) al contenitore Exclude.

![Immagine 4](assets/Image-4.png)

Come best practice, accertati di etichettare i contenitori. Sarai lieto di averlo fatto, soprattutto quando le nostre definizioni dei segmenti diventano più complesse.

Ora che abbiamo creato il segmento Intento di acquisto, possiamo utilizzare il Workspace di qualità dei dati dell’intento di visita per vedere che il segmento Intento di acquisto si esclude a vicenda con il segmento Uno e Fine.

![Immagine 5](assets/Image-5.png)

## Creazione del segmento intento della visita di conservazione

Nel business delle crociere, molti ospiti arrivano sul nostro sito per gestire una prenotazione, ma non necessariamente per fare un acquisto. Possono venire sul sito per inserire informazioni di viaggio, rivedere il loro itinerario, fare prenotazioni di cena, o una serie di altre cose, senza fare acquisti per una crociera. I nostri ospiti possono anche acquistare escursioni a terra o altri miglioramenti alla loro esperienza. Consideriamo questi miglioramenti come parte della fidelizzazione, quindi li manteniamo separati dal nostro segmento Booking (che chiamiamo &quot;Purchase&quot; in questa serie di blog).

I clienti al dettaglio potrebbero essere in grado di fare ritorno o gestire il loro programma fedeltà. Gli abbonati ai contenuti multimediali o alla tecnologia potrebbero utilizzare il prodotto. Se il tuo ospite si trova sul tuo sito web per gestire il loro rapporto con te, si tratta di una visita di conservazione e dovremmo esaminare questi segnali. E se fornisci un prodotto online, come Media, Tech, Online Banking o altri, ci sono probabilmente molti altri tipi di segmenti di intento di visita che non discuteremo in questa serie.

Come per il segmento Intento di acquisto, stiamo cercando indicazioni di intento molto esplicite. Per me, abbiamo un&#39;intera sezione del sito dedicata alla gestione di una crociera in modo che sia facile identificare quelle pagine. Questo potrebbe essere più complesso per altre aziende. Cerca segnali come accessi, gestione account, visite alle pagine di supporto e simili.

Devo notare che &quot;Mantenimento&quot; è un po&#39; un nome imbarazzante per questa intenzione di visita, poiché il visitatore non è sul nostro sito, &quot;quindi posso essere mantenuto come cliente.&quot; Il mantenimento è la nostra intenzione per quella visita. Ricordati di essere empatico con i nostri clienti e di mantenere un focus sul cliente-primo!

### Utilizzo di Analytics Workspace per identificare i segnali di intento di conservazione

Anche in questo caso, Analytics Workspace ci aiuta a identificare l’intento di conservazione. Puoi utilizzare le dimensioni pagine, sezione sito o segmento personalizzato per categorizzare le pagine. Cerca le pagine con tassi di conversione di acquisto bassi. Nel nostro caso, scopriamo che le pagine Check-in online e Shore Excursion (Shorex) hanno tassi di conversione relativamente più bassi rispetto ad altre pagine che sono più logicamente associate con lo shopping e l’acquisto.

![Immagine 6](assets/Image-6.png)

È inoltre consigliabile cercare in Workspace le pagine con traffico elevato. Analizza l’elenco delle pagine con traffico elevato e decide se indicano un intento di conservazione.

## Esclusione di altri segmenti

Anche in questo caso, i nostri segmenti Intento di visita devono escludersi a vicenda e risultare completamente esaustivi. Se non sei ancora stanco di leggere questo, lo sarai! Per il segmento Intento di mantenimento, è fondamentale escludere i comportamenti Intento di acquisto.

Per la maggior parte di noi, l’intento di acquisto e l’intento di mantenimento non si escludono a vicenda. Abbiamo ospiti che vengono sul sito per gestire la loro prossima crociera, ma anche per prenotare il loro prossimo viaggio (grazie!). Se sei un ristorante, un visitatore può controllare i suoi punti fedeltà e poi effettuare un ordine online.

Anche se il comportamento non si esclude a vicenda, i nostri segmenti devono essere per l’analisi del Percorso di clienti. Possiamo creare altri segmenti molto interessanti per analizzare la sovrapposizione tra i comportamenti di acquisto e fedeltà. Ma per i nostri scopi attuali, abbiamo bisogno che questi segmenti si escludano a vicenda.

Poiché la generazione della domanda è uno degli obiettivi principali del marketing, il nostro segmento dell’intento di mantenimento escluderà l’intento di acquisto. In altre parole, se qualcuno arriva sul nostro sito per gestire una crociera, ma indica anche l’intenzione di prenotare una nuova crociera, tale visita andrà al segmento Intento di acquisto.

### Segmento dell’intento di conservazione nel Generatore di segmenti

Le nostre definizioni dei segmenti stanno diventando un po&#39; più lente. Includi le visite nel segmento. Aggiungere i segnali degli intenti di conservazione. Per me, era semplice. Se il nome della pagina inizia con &quot;bge:&quot; (le pagine degli ospiti prenotate), sei nel segmento. Ho aggiunto che le visualizzazioni di pagina sono maggiori di una per misurazioni aggiuntive (ma escluderemo comunque una hit wonders di seguito).

Quindi aggiungi contenitori di esclusione per le tue Meraviglie di un hit e visite Intento di acquisto. Assicurati che i contenitori siano uniti con la condizione &quot;E&quot;.

![Immagine 7](assets/Image-7.png)

Ancora una volta, osserva il Workspace Visit Intent Data Quality per assicurarti che i segmenti si escludano a vicenda. I nostri segmenti di Intento di visita stanno prendendo forma correttamente!

![Immagine 8](assets/Image-8.png)

A questo punto, abbiamo configurato tre dei cinque segmenti Intento di visita. Vediamo che questi segmenti si escludono a vicenda. Nel prossimo post, creeremo i segmenti finali Intento di visita, Considerazione e consapevolezza, e i nostri segmenti saranno tutti completamente esaustivi. Una volta configurati i segmenti di Intento di visita, li riuniremo in segmenti basati su visitatori che troverai molto utili per l’analisi e la personalizzazione.

## Autore

Questo documento è stato scritto da:

![Fossum di Aaron](assets/aaron-headshot.png)

**Aaron Fossum**, Direttore, Digital Analytics

Adobe Analytics Champion
