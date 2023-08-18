---
title: Informazioni sul pannello di attribuzione e sugli intervalli di lookback di Adobe Analytics
description: Scopri come utilizzare il pannello Attribuzione e l’intervallo di lookback per comprendere il comportamento del cliente e personalizzare il modo in cui gli elementi dimensionali ricevono credito per gli eventi di successo.
feature: Attribution
role: User
level: Experienced
doc-type: Article
last-substantial-update: 2023-06-20T00:00:00Z
jira: KT-13181
thumbnail: KT-13181.jpeg
source-git-commit: f38a35067bf95fe02200d1409e3e70c1ef28abb3
workflow-type: tm+mt
source-wordcount: '1681'
ht-degree: 3%

---


# Informazioni sul pannello di attribuzione e sugli intervalli di lookback di Adobe Analytics

Quando ho pensato per la prima volta al [pannello attribuzione](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/attribution.html?lang=en) e **intervallo di lookback**, mi è stato subito ricordato il concetto di &#39;*viaggio nel tempo&quot;*; poi, ovviamente, mi è stato anche ricordato che la nostra risposta tipica a molti nuovi strumenti come questi è semplicemente di rimandare il tentativo di usarli, perché sembrano così complicati.

Voglio dire, onestamente, guardate tutte quelle opzioni, interruttori, pannelli, letture e manopole.  E seriamente, parliamo di quelle complicate luci lampeggianti, tubi, strumenti... ASPETTA!!  Non è il momento di distrarsi parlando di macchine del tempo, semplicemente non abbiamo il tempo... o no?

Ammetterò il **pannello attribuzione** è uno strumento abbastanza complesso; tuttavia, il nostro lavoro tipico come analisti, giorno dopo giorno, è quello di utilizzare un altro dei nostri strumenti preferiti e altamente complessi per dare un&#39;occhiata anche a ciò che è successo in passato. Tale strumento è denominato ***Adobe Analytics***!  Quindi sì, per rispondere alla nostra domanda molto rilevante, credo che queste due cose dicano che abbiamo molto tempo.

Quindi, perché dovremmo lasciare che qualcosa come un po&#39; di paura si frapponga alla strada di strumenti così incredibili, sofisticati e potenti come questi che ci permettono letteralmente di guardare *indietro* nel tempo, ogni singolo giorno?

Dopotutto - questo è TIME TRAVEL, gente!!  Ci occupiamo di questo genere di cose.  Giusto???!!

Quindi, cosa stiamo aspettando - un&#39;auto di metallo lucido, una cabina di polizia, o una cabina telefonica vintage utilizzando il cablaggio di un vecchio ombrello come antenna per apparire sulla nostra porta?

No!  Abbiamo qualcosa di ancora meglio, quindi entriamo e resistiamo!

Beh... hai capito l&#39;idea.


Ora che siamo tutti entusiasti dei viaggi nel tempo, facciamo un respiro profondo, facciamo un passo indietro un po&#39;, stabiliamo che cosa... **pannello attribuzione** *davvero* è, e scomporre un po&#39; le cose:

![Attribuzione](assets/attribution.png)

*Figura 1 - Numeri visualizzati in linea con il testo riportato di seguito*

In entrata **attribuzione**, è sufficiente considerare il modo in cui gli eventi/azioni possono essere causati da un individuo, da più individui o da uno qualsiasi dei diversi eventi nel tempo.

Secondo [Adobe](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/attribution/overview.html?lang=en), *attribuzione* consente agli analisti di personalizzare come *Dimension* gli oggetti ricevono credito per *eventi di successo*.


>[!WARNING]
>
>Solo una breve nota per richiamarlo **modelli di attribuzione** sono così frequentemente associati a **canali di marketing** che io intenzionalmente *barrato* ❷ CHANNEL nell’immagine qui sopra per illustrare come è possibile eseguire **attribuzione** analisi rispetto alla maggior parte degli altri ***dimensione***.


Di fatto, raramente un dato percorso di clienti è realmente lineare e anche meno spesso prevedibile.  Inoltre, ogni cliente procederà secondo il proprio ritmo; spesso, può tornare indietro, fermarsi, uscire o impegnarsi in altri comportamenti non lineari. Queste azioni organiche rendono difficile o praticamente impossibile conoscere l’impatto delle attività di marketing in tutto il percorso di clienti. Inoltre, ostacola gli sforzi volti a collegare più canali di dati tra loro.

Esatto.  Lasciate alle porte le vostre analogie &quot;domino&quot; e aprite le vostre menti a concetti più simili all&#39;effetto farfalla e alla teoria delle stringhe - ma come tutto il resto, dobbiamo iniziare con alcune delle basi.

## **Modelli di attribuzione**

Quando si utilizza **pannello attribuzione**, possiamo iniziare a osservare diverse cose.  Ad esempio, **modelli di attribuzione** dimostraci in che modo *conversioni* (ad esempio, ❶ **metriche di successo**) può essere distribuito tra *hit* in un dato gruppo.

In breve, se **10 persone** premere a **PULSANTE ROSSO GRANDE** per varcare una porta, il nostro **modelli di attribuzione** ci dirà quali di queste **10 persone** vogliamo assegnare il &quot;credito&quot; - o meglio ancora, come *molto* &quot;merito&quot; che vogliamo assegnare loro - per aver premuto detto pulsante.

![Pulsante](assets/button.png)

Tenendo presente questo aspetto, ecco alcuni esempi di come la ❸ **modelli di attribuzione** potrebbero influire su **10 persone**:

- **Primo contatto**: questo modello funziona esattamente come se suonasse dando **100% di credito** al *primo* persona che ha varcato la porta.  È più probabile che gli addetti al marketing utilizzino questo approccio per tattiche come ***social media*** o ***visualizzare***; tuttavia, è anche un&#39;ottima tattica da utilizzare spesso per l&#39;efficacia delle raccomandazioni sui prodotti in loco.
- **Ultimo contatto**: questa tattica funziona esattamente come sembra, ma offre **100% di credito** all&#39;ULTIMA persona che ha varcato la porta.  Questo modello viene generalmente utilizzato per analizzare elementi come ***ricerca naturale (organica)*** e altro *a breve termine* campagne del ciclo di marketing.
- **Lineare**: questo modello distribuisce lo stesso credito a OGNI SINGOLA PERSONA che ha camminato attraverso la porta.

  >[!CAUTION]
  >
  >Tuttavia, si consiglia cautela in questo caso, perché è possibile diffondere i risultati molto rapidamente quando si applica questa tattica, considerando il tempo di esecuzione e l’ampiezza del pubblico che raggiunge.

- **A forma di U**: questo approccio assegna **40%** del credito al *prima persona* nella porta, si allarga **20%** del credito in *tutti nel mezzo*, e quindi dà **40%** al **ultimo/a** attraverso. Questo modello viene utilizzato il più delle volte in situazioni in cui **lungo ciclo di conversione/vendita** contenente *diversi punti di contatto* lungo la strada.  In questo caso, l’obiettivo è principalmente quello di evidenziare ***primo*** e ***ultimo*** tattiche di marketing che hanno contribuito alla conversione del cliente.
- **J**-**A forma di** e **J inversa**:
   - Pensa a **A forma di U**, ma questo modello assegna **60%** accreditare al *ultima persona* passeggiando attraverso la porta, **20%** al *primo*, e quindi *divisioni* il rimanente **20%** in orizzontale *tutti gli altri* al centro.  **J inversa** fa esattamente l&#39;opposto.

     L&#39;obiettivo è quello di mettere la maggior parte della vostra enfasi, o al *inizio* o *fine* della tua campagna; tuttavia, desideri comunque assegnare un certo importo di credito all’elemento contribuente all’estremità opposta, riconoscendo i &quot;ragazzi piccoli&quot; lungo il percorso.

- **Decadimento nel tempo**: Ora, sarei un rimprovero se non condividessi questo. Questo modello ha letteralmente un&#39;emivita che decade esponenzialmente - nel tempo!  In questo caso, il *predefinito* Il parametro per l&#39;emivita di questo modello è **7 giorni**.  Il modo in cui funziona è applicare *peso* a ciascuno **canale di marketing**, *in base al tempo* che passa dopo il *punto di contatto iniziale* e quando il cliente effettua la conversione.

  **Decadimento nel tempo** e **Modelli di attribuzione a U** vengono entrambi utilizzati in genere per misurare le campagne a più lungo termine, ma come puoi vedere, hanno obiettivi leggermente diversi, in base a come alla fine *pesare* il valore del risultato.

- **Personalizzato**: scegli chi avrà il merito.  È la tua campagna!

Per ulteriori informazioni su questi e altri modelli di attribuzione, [fai clic qui](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html?lang=it)

Per rendere questo ancora più interessante, parliamo di tornare indietro l&#39;orologio!

## **Intervalli di lookback**

Ora è il momento di iniziare a portare la tua mente al livello successivo.  In questo ambito aggiungiamo letteralmente l’elemento del viaggio nel tempo alla nostra analisi, e di nuovo iniziamo con le nozioni di base.

***Adobe*** definisce ❹ **intervalli di lookback** come &quot;la quantità di tempo che una conversione deve recuperare per includere i punti di contatto. I modelli di attribuzione che attribuiscono maggiore credito alle prime interazioni visualizzano differenze più importanti quando si visualizzano diversi intervalli di lookback.&quot;


In altre parole, **intervalli di lookback** determinare il periodo di tempo durante il quale *conversioni* vengono considerati e forniscono *contesto* all’analisi di attribuzione. ***Adobe Analytics*** offre tre tipi di **intervalli di lookback**:

- **Intervallo di lookback su visita:** Torna all&#39;inizio di un ***visita*** quando si verifica una conversione, fornendo informazioni sulle interazioni immediate che portano alle conversioni.

  Tieni presente che in genere si tratta del più breve **intervallo di lookback** da utilizzare.
- **Intervallo di lookback su visitatore:** Guarda tutti ***visite*** esegui il backup fino al primo del mese entro il **intervallo date**, offrendo una visione molto più ampia delle interazioni del cliente e aiutando a identificare i modelli nel tempo.
- **Finestra di lookback personalizzata:** Consente di espandere **finestra di attribuzione** oltre il reporting **intervallo date** fino a un *massimo* di **90 giorni**.  Fornisce *flessibilità* acquisizione dei punti di contatto che si sono verificati *esterno* la selezione **intervallo date**, garantendo un&#39;analisi completa.

Regolando un dato **intervallo di lookback** Gli analisti possono quindi esaminare l’impatto di uno o più punti di contatto in intervalli di tempo specifici e ottenere informazioni più approfondite su come le diverse durate influiscono sui risultati di attribuzione.

## **Riunire tutto**

Cosa significa tutto questo per noi analisti?

Il **pannello attribuzione** e **intervallo di lookback** consentici di guardare oltre i dati mondani a livello di superficie e di approfondire il percorso dei clienti. Capendo quali punti di contatto hanno avuto il maggiore impatto su *conversioni* In questo modo possiamo prendere decisioni informate sulle nostre strategie di marketing e allocare le risorse in modo più efficace.

Ricorda, dopo aver ricevuto **modelli di attribuzione** e **intervalli di lookback** selezionato, puoi comunque manipolare ulteriormente i dati filtrandoli con un ❺ **segmento,** o qualsiasi altro componente desiderato a questo punto.  Inoltre, dopo il rendering del pannello, avrai a disposizione tutte le funzionalità di un’area di lavoro tradizionale.

## **Infine, la sua applicazione pratica**

Ora che hai i concetti, immagina di condurre una campagna di marketing e di cercare di determinare quale canale è il *più efficace* per favorire le conversioni. Con l&#39;aiuto del **pannello attribuzione**, non solo è possibile visualizzare **ultimo contatto**, ma anche **primo contatto**, **stesso contatto**, e qualsiasi altro **modello** scegliere quale **canali** sono *più efficace* nel guidare il *conversioni*. Quindi, queste informazioni possono essere utilizzate per *ottimizzare* campagne e migliorare le prestazioni complessive semplicemente tornando indietro nel tempo con **intervallo di lookback** a tua scelta!

Ora che hai visto cosa può fare, non farti ingannare o intimidire dalle caratteristiche apparentemente complesse del pannello attribuzione.  **Affrontalo**.  *Abbraccia* ...  **Comprendere** ...
MA SOPRATTUTTO - *Usatela a vostro vantaggio.* Il **pannello attribuzione** e **intervallo di lookback** sono le chiavi per comprendere meglio i tuoi clienti e il loro percorso con il tuo marchio.

Ora possiamo viaggiare &quot;.[indietro nel tempo](https://youtu.be/gVryJmZNFdU)&quot; con fiducia e utilizzare la potenza della nostra fidata macchina del tempo (alias ***Adobe Analytics***) per prendere decisioni basate sui dati.

## Autore

Questo documento è stato scritto da:

![Jeff Bloomer](assets/jeff-headshot.png)

**Jeff Bloomer**, Manager, Digital Analytics presso Kroger Personal Finance

Adobe Analytics Champion