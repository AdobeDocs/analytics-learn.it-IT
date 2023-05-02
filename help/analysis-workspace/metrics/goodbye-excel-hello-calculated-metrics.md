---
title: Addio Excel, salve metriche calcolate
description: Scopri i vantaggi dell’utilizzo delle metriche calcolate in Adobe Analytics e come possono fornirti una visualizzazione continua e dinamica dei tuoi dati in questo articolo.
feature: Calculated Metrics
role: User
level: Experienced
doc-type: Article
last-substantial-update: 2023-05-02T00:00:00Z
jira: KT-13178
thumbnail: KT-13178.jpeg
source-git-commit: 28db96c38e5318942ddc9f39ec0a2d561e14200c
workflow-type: tm+mt
source-wordcount: '1282'
ht-degree: 0%

---


# Addio Excel, salve metriche calcolate

Scopri i vantaggi dell’utilizzo delle metriche calcolate in Adobe Analytics e come possono fornirti una visualizzazione continua e dinamica dei tuoi dati in questo articolo.

Ehi! Perché sei in Excel in questo momento? Voglio dire, so il perché. Devi fare dei rapporti per arrivare alle persone giuste. Sei occupato a inserire i dati da Adobe Analytics e a calcolare i tassi di conversione, a catalogarli e a prepararti per metterli tutti in un PowerPoint destinato ai decisori. Spero davvero che almeno tu stia usando il Report Builder per farlo, ma so che alcuni di voi stanno copiando e incollando manualmente i dati da un&#39;area di lavoro a Excel.

Perché?

Perché passare attraverso un processo manuale ogni mese? Perché presentare una visualizzazione statica una volta al mese invece di una visualizzazione continua e dinamica? Perché copiarlo in PowerPoint? Perché non creare direttamente metriche calcolate in Adobe Analytics?

## Le metriche calcolate sono potenti

Le metriche calcolate sono potenti, ma anche le funzioni matematiche di base sono molto utili e un miglioramento serio rispetto alla matematica in Excel. Diamo un’occhiata ad alcuni dei vantaggi e ad alcuni casi d’uso:

1. **Le metriche calcolate sono correnti e dinamiche**

   Quando si esportano numeri da Adobe Analytics, questi vengono bloccati in un momento. Devi assolutamente sapere come il tuo sito o app ha eseguito il mese prima, ma come i decisori tengono traccia di come vanno le cose a metà mese? Se il tasso di conversione scende per un giorno e poi torna alla media entro la fine del mese, lo sapete? Questo tuffo potrebbe essere dati preziosi che rivelano un importante problema di telemetria, o ancora più vitale, un cambiamento nel comportamento dei visitatori. Con una metrica calcolata, puoi creare un grafico e visualizzarla il giorno in cui si verifica, consentendoti di rispondere.

1. **Metriche calcolate Risparmia tempo**

   Ci sono stato. Copia/incolla. Inserire la formula o trascinare la cella sopra di essa verso il basso. Clicca sul grafico e cambia l&#39;intervallo in modo da avere gli ultimi dodici o tredici mesi. Ora copia il grafico. Ora lo rifaccia. E ancora. E ancora. Spegnere PowerPoint. È noioso e dispendioso in termini di tempo e sembra che lo si debba fare ogni mese per sempre.

   Puoi invece creare un’area di lavoro che utilizza la metrica calcolata, che includa nell’intervallo di date gli ultimi dodici o tredici mesi interi e che i dati e il grafico vengano aggiornati automaticamente alla mezzanotte del primo giorno di ogni mese. I destinatari possono avere accesso diretto all’area di lavoro. Possono ricevere automaticamente una copia di PDF tramite e-mail il primo giorno del mese o dopo aver utilizzato le visualizzazioni di testo per aggiungere commenti sui dati (sai, la parte divertente del reporting).

1. **Le metriche calcolate possono essere applicate a set di dati di grandi dimensioni**

   Puoi esportare tutti i nomi dei prodotti in Excel e iniziare a calcolare i tassi di conversione e i ricavi per visitatore, ma questo diventa un problema se disponi di circa 100.000 unità. Non è un problema con le metriche calcolate. Rilascia la dimensione in una tabella come di consueto, quindi utilizza le metriche calcolate come metriche. Ora disponi di una tabella ordinabile dinamica che si aggiorna automaticamente quando i prodotti o qualsiasi dimensione utilizzi vengono aggiunti al catalogo.

1. **Le metriche calcolate impediscono gli errori**

   Errori di Excel. Ci siamo state tutte. Collo, l&#39;intera economia della Grecia e la reputazione di due stimati accademici sono stati rovinati a causa di un errore di formula Excel. Probabilmente non avete un&#39;economia europea che sfrutta le vostre competenze in Excel, ma c&#39;è sicuramente qualche decisione sui budget che cambierà in base ai vostri numeri. L’utilizzo di Metriche calcolate consente di creare una metrica, assegnarle un controllo qualità e quindi di non preoccuparti più di questa.

### Ora che abbiamo superato i vantaggi dell’utilizzo delle metriche calcolate, vediamo come metterle in pratica

**Caso d’uso 1 : Tassi di conversione**

La maggior parte dei tassi di conversione è solo una semplice divisione. Dividi il numero di conversioni in base al numero di visitatori o visite. Dividi il numero di visualizzazioni di pagina per la pagina finale di un funnel in base al numero di pagine visualizzate per la prima pagina di un funnel. Dividi il numero di click-through di campagne interne in base al numero di impression. Tutte queste operazioni possono essere facilmente eseguite come metriche calcolate e inserite in un dashboard con latenza di dati ridotta, aggiornamento delle visualizzazioni e maggiore condivisibilità.

**Caso d&#39;uso 2: Ricerca interna**

La ricerca interna è uno degli strumenti più importanti per comprendere il tuo sito. I risultati della ricerca sul sito ti dicono a cosa sono interessati i tuoi visitatori e se possono facilmente trovarli attraverso la navigazione o meno. Devi essere in grado di sapere se la ricerca del tuo sito funziona bene e utilizzando un po &#39;di aggiunta e divisione di base può darti la risposta.

Cominciamo con i risultati della ricerca. Vuoi sapere se un termine di ricerca ottiene risultati o non genera nulla. Questi sono solitamente eventi separati. Vuoi affrontare il problema di ottenere un terzo evento per tutte le ricerche interne del sito aggiunte? Al contrario, dai un’interruzione ai tuoi dispositivi e utilizza le metriche calcolate per aggiungere la ricerca interna: Risultati e ricerca interna: Nessun risultato per ottenere le ricerche interne totali.

Quale percentuale di ricerche non restituisce risultati? Dividi ricerca interna: Nessun risultato per la nuova metrica Totale ricerche interne calcolate. Ora sai se è urgente creare nuovi contenuti per far corrispondere tali termini di ricerca, o se il tuo team di contenuti può affrontare priorità più elevate.

Vogliamo sapere quante di queste ricerche con risultati ottengono click-through e di solito hanno una metrica separata anche per quello. Utilizza le metriche calcolate per dividere il numero di click-through per il numero di volte in cui il termine ha portato i risultati della ricerca e visualizzarli come percentuale. Ora hai il tasso di click-through per ogni termine di ricerca interno sul tuo sito. È possibile isolare i termini di ricerca che generano risultati non utili. Ha tutti i dati storici a vostra disposizione per poterli tracciare, e man mano che si apportano miglioramenti, potete facilmente vedere se funzionano guardando quel tasso aumentare o scendere.

Dividi il numero di ricerche interne in base al numero di visitatori che cercano. Hai ricerche per visitatore per ogni termine. Se quel numero è alto (più vicino è a 1,0 meglio è) si ha uno dei due possibili problemi. I risultati su cui si fa clic non sono corretti e i visitatori eseguono più ricerche per trovare i risultati migliori, oppure non possono trovare le pagine che stanno cercando tramite la navigazione.

Come puoi misurare se queste pagine chiave sono accessibili tramite la navigazione? Crea una metrica calcolata per le visualizzazioni di pagina che seguono la visualizzazione di una pagina dei risultati di ricerca. Dividetelo per visualizzazioni totali della pagina per quella pagina. Ora conosci la percentuale di visualizzazioni di pagina che proviene dai risultati della ricerca. Se hai una percentuale elevata, probabilmente hai del lavoro da fare sulla navigazione.

### Le Metriche Calcolate Sono Potenti

Spero che questo vi abbia mostrato alcune delle possibilità di usare le funzioni matematiche di base in Metriche calcolate e che inizierete a costruirne alcune voi stessi. Questo inizia solo a descrivere le possibilità di calcolo che è possibile fare in Metriche calcolate, anche con quattro semplici funzioni. Le metriche calcolate possono aiutarti a comprendere il comportamento dei visitatori su un livello completamente nuovo e una volta appeso, hai aperto la porta per utilizzare funzioni più complesse che sono anche disponibili per te.

## Autore

Questo documento è stato scritto da:

![Gittai](assets/gittai.png)

**Gitai Ben Ammi**, Consulente principale di Concentrix Catalyst

Adobe Analytics Champion
