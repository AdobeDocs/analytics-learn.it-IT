---
title: Addio Excel, benvenute Metriche calcolate
description: Scopri i vantaggi dell’utilizzo delle metriche calcolate in Adobe Analytics e come possono fornirti una visualizzazione continua e dinamica dei tuoi dati, in questo articolo.
feature: Calculated Metrics
role: User
level: Experienced
doc-type: Article
last-substantial-update: 2023-05-02T00:00:00Z
jira: KT-13178
thumbnail: KT-13178.jpeg
exl-id: d4f69244-6614-41f3-ac48-70adabb8a8e7
source-git-commit: d95136a21c08312a81baba7673cb7135270af4bd
workflow-type: tm+mt
source-wordcount: '1286'
ht-degree: 2%

---

# Addio Excel, benvenute Metriche calcolate

Scopri i vantaggi dell’utilizzo delle metriche calcolate in Adobe Analytics e come possono fornirti una visualizzazione continua e dinamica dei tuoi dati, in questo articolo.

Ehi! Perché sei in Excel in questo momento? Cioè, so il perché. Devi segnalare per arrivare alle persone giuste. Si è impegnati a immettere dati da Adobe Analytics e a calcolare i tassi di conversione, a tracciarli e a prepararsi a inserirli tutti in un PowerPoint destinato ai responsabili decisionali. Spero davvero che tu stia almeno utilizzando Report Builder per farlo, ma so che alcuni di voi stanno copiando e incollando manualmente i dati da un Workspace a Excel.

Perché?

Perché seguire una procedura manuale ogni mese? Perché presentare una visualizzazione statica una volta al mese invece di una visualizzazione continua e dinamica? Perché copiarlo in PowerPoint? Perché non creare metriche calcolate direttamente in Adobe Analytics?

## Le metriche calcolate sono potenti

Le metriche calcolate sono potenti, ma anche le funzioni matematiche di base sono veramente utili e rappresentano un serio miglioramento rispetto alla matematica in Excel. Esaminiamo alcuni dei vantaggi e alcuni casi d’uso:

1. **Le metriche calcolate sono correnti e dinamiche**

   Quando si esportano numeri da Adobe Analytics, questi vengono bloccati in un determinato momento. Devi assolutamente sapere come sono andate le prestazioni del tuo sito o della tua app il mese prima, ma in che modo i decision maker tengono traccia di come stanno andando le cose a metà mese? Se il tasso di conversione precipita per un giorno e poi ritorna alla media entro la fine del mese, lo saprai? Questo tuffo potrebbe essere costituito da dati importanti che rivelano un importante problema di telemetria, o ancor più importante, un cambiamento nel comportamento dei visitatori. Con una metrica calcolata, puoi tracciarla e visualizzarla il giorno in cui si verifica, lasciandoti pronto a rispondere.

1. **Le Metriche Calcolate Ti Consentono Di Risparmiare Tempo**

   Io ci sono stato. Copiare/incollare. Immettere la formula o trascinare verso il basso la cella sopra di essa. Fai clic sul grafico e modifica l’intervallo in modo da disporre degli ultimi dodici o tredici mesi. Copiare il grafico. Ora fallo di nuovo. E ancora. E ancora. Invia PowerPoint. È noioso e richiede tempo e sembra che lo si debba fare ogni mese per sempre.

   Puoi invece creare un Workspace che utilizzi la metrica calcolata, che abbia Ultimi dodici o tredici mesi interi come intervallo di date e che faccia in modo che i dati e il grafico vengano aggiornati automaticamente alla mezzanotte del primo giorno di ogni mese. I destinatari possono avere accesso diretto a Workspace. Possono ricevere una copia PDF inviata loro automaticamente il primo giorno del mese o dopo aver utilizzato le Visualizzazioni di testo per aggiungere il commento ai dati (la parte divertente del reporting).

1. **Le metriche calcolate possono essere applicate a grandi insiemi di dati**

   Puoi esportare tutti i nomi dei prodotti in Excel e iniziare a calcolare i tassi di conversione e i ricavi per visitatore, ma questo diventa un problema se ne hai 100.000 o giù di lì. Nessun problema con le metriche calcolate. Rilascia la dimensione in una tabella come di consueto, quindi utilizza le metriche calcolate come metriche. Ora disponi di una tabella ordinabile dinamica che si aggiorna automaticamente man mano che i prodotti o qualsiasi dimensione che utilizzi vengono aggiunti al catalogo.

1. **Le Metriche Calcolate Impediscono Gli Errori**

   Si verificano errori di Excel. Noi siamo stati tutti lì. Diavolo, l&#39;intera economia della Grecia e la reputazione di due stimati accademici sono stati rovinati a causa di un errore di formula Excel. Probabilmente non avete un&#39;economia europea che usa le vostre abilità Excel, ma sicuramente c&#39;è una qualche decisione sui budget che cambierà in base ai vostri numeri. L’utilizzo delle metriche calcolate consente di creare una metrica, sottoporla a QA’d e quindi non preoccuparsene di nuovo.

### Ora che abbiamo analizzato i vantaggi dell’utilizzo delle metriche calcolate, vediamo come metterle in pratica

**Caso d&#39;uso 1: tassi di conversione**

La maggior parte dei tassi di conversione sono solo semplici divisioni. Dividi il numero di conversioni per il numero di visitatori o visite. Dividi il numero di visualizzazioni di pagina per la pagina finale di un funnel per il numero di visualizzazioni di pagina per la prima pagina di un funnel. Dividi il numero di clickthrough di campagne interne per il numero di impression. Tutte queste operazioni possono essere eseguite facilmente come metriche calcolate e posizionate in un dashboard con latenza dei dati ridotta, visualizzazioni aggiornate e maggiore condibilità.

**Caso d&#39;uso 2: ricerca interna**

La ricerca interna è uno degli strumenti più importanti per comprendere il sito. I risultati della ricerca del sito indicano agli utenti cosa sono interessati e se possono trovarlo facilmente tramite la navigazione o meno. Devi essere in grado di capire se la ricerca del tuo sito funziona bene e utilizzando un po &#39;di aggiunta e divisione di base può darti quella risposta.

Cominciamo dai risultati della ricerca. Desideri sapere se un termine di ricerca ottiene risultati o non genera alcun risultato. Si tratta solitamente di eventi separati. Desideri superare il problema di ottenere un terzo evento per tutte le ricerche interne del sito aggiunte? Al contrario, dai ai tuoi sviluppatori un’interruzione e utilizza Metriche calcolate per aggiungere Ricerca interna: Risultati e Ricerca interna: Nessun risultato insieme per ottenere il totale delle ricerche interne.

Quale percentuale di ricerche non restituisce alcun risultato? Dividi ricerca interna: nessun risultato per la nuova metrica calcolata Ricerche interne totali. Ora sai se è urgente creare nuovi contenuti che corrispondano a questi termini di ricerca, o se forse il tuo team di contenuti può affrontare priorità più elevate.

Vogliamo sapere quante di queste ricerche con risultati ottengono clickthrough e in genere hanno una metrica separata per anche questo. Utilizza le metriche calcolate per dividere il numero di clickthrough per il numero di volte in cui il termine ha riportato i risultati della ricerca e visualizzarlo come percentuale. Ora disponi della percentuale di clickthrough per ogni termine di ricerca interno sul sito. È possibile isolare i termini di ricerca che generano risultati inutili. Ha a disposizione tutti i dati storici che vi permettono di creare un grafico, e man mano che apportate dei miglioramenti, potete facilmente vedere se funzionano guardando il tasso salire o scendere.

Dividi il numero di ricerche interne per il numero di visitatori che effettuano ricerche. Sono presenti ricerche per visitatore per ogni termine. Se quel numero è alto (più vicino è a 1,0, meglio è) hai uno dei due possibili problemi. I risultati su cui fai clic non sono validi e i visitatori eseguono più ricerche per trovare i risultati migliori, oppure non riescono a trovare le pagine che stanno cercando tramite navigazione.

Come puoi misurare se queste pagine chiave sono reperibili tramite il navigatore? Crea una metrica calcolata per le visualizzazioni di pagina che seguono la visualizzazione della pagina dei risultati di ricerca. Dividi questo dato per il totale delle visualizzazioni di pagina per quella pagina. Ora si conosce la percentuale di visualizzazioni di pagina derivante dai risultati di ricerca. Se la percentuale è alta, probabilmente c&#39;è del lavoro da fare nella navigazione.

### Le Metriche Calcolate Sono Potenti

Spero che questo vi abbia mostrato alcune delle possibilità di usare le funzioni matematiche di base in Metriche calcolate e che inizierete a costruirne qualcuna voi. Questo inizia solo a descrivere le possibilità della matematica che puoi fare nelle Metriche calcolate, anche con quattro semplici funzioni. Le metriche calcolate possono aiutarti a comprendere il comportamento dei visitatori a un livello completamente nuovo e, una volta che ne hai il controllo, hai aperto la porta per utilizzare funzioni più complesse disponibili anche per te.

## Autore

Questo documento è stato scritto da:

![Headshot Gittai](assets/gittai.png)

**Gitai Ben-Ammi**, Principal Consultant di Concentrix Catalyst

Adobe Analytics Champion
