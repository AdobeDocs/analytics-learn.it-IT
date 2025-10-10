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
exl-id: 1da9334b-0edb-4237-b7ca-57640865208c
source-git-commit: f1bb981a83eb698f4185a22c367346a9ddd0c755
workflow-type: tm+mt
source-wordcount: '1659'
ht-degree: 1%

---

# Informazioni sul pannello di attribuzione e sugli intervalli di lookback di Adobe Analytics

Quando ho pensato per la prima volta al [pannello di attribuzione](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/attribution.html?lang=en) e all&#39;**intervallo di lookback**, mi è stato subito ricordato il concetto di &#39;*viaggio nel tempo&#39;*; poi, ovviamente, mi è stato anche ricordato che la nostra tipica risposta a molti nuovi strumenti come questi è semplicemente di rimandare il tentativo di utilizzarli, perché sembrano così complicati.

Voglio dire, onestamente, guardate tutte quelle opzioni, interruttori, pannelli, letture e manopole.  E seriamente, parliamo di quelle complicate luci lampeggianti, tubi, strumenti... ASPETTA!!  Non è il momento di distrarsi parlando di macchine del tempo, semplicemente non abbiamo il tempo... o no?

Ammetto che il **pannello di attribuzione** è uno strumento piuttosto complesso; tuttavia, il nostro lavoro tipico in qualità di analisti, giorno dopo giorno, è quello di utilizzare un altro dei nostri strumenti preferiti e altamente complessi per dare un&#39;occhiata anche a ciò che è successo in passato. Lo strumento è denominato ***Adobe Analytics***.  Quindi sì, per rispondere alla nostra domanda molto rilevante, credo che queste due cose dicano che abbiamo molto tempo.

Quindi, perché dovremmo permettere a qualcosa come un po&#39; di paura di ostacolare questi strumenti incredibili, sofisticati e potenti come questi che ci permettono letteralmente di guardare *indietro* nel tempo, ogni singolo giorno?

Dopotutto - questo è TIME TRAVEL, gente!!  Ci occupiamo di questo genere di cose.  Giusto???!!

Quindi, cosa stiamo aspettando - un&#39;auto di metallo lucido, una cabina di polizia, o una cabina telefonica vintage utilizzando il cablaggio di un vecchio ombrello come antenna per apparire sulla nostra porta?

No!  Abbiamo qualcosa di ancora meglio, quindi entriamo e resistiamo!

Beh... hai capito l&#39;idea.


Ora che siamo tutti entusiasti del viaggio nel tempo, facciamo un respiro profondo, facciamo un passo indietro un po&#39;, stabiliamo cos&#39;è il **pannello di attribuzione** *realmente* e analizziamo un po&#39; le cose:

![Attribuzione](assets/attribution.png)

*Figura 1 - I numeri visualizzati sono allineati con il testo più sotto*

In **attribuzione**, considera semplicemente il modo in cui gli eventi/azioni possono essere causati da un singolo, da più singoli utenti o da uno qualsiasi dei diversi eventi nel tempo.

In base a [Adobe](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/attribution/overview.html?lang=en), *attribution* consente agli analisti di personalizzare il modo in cui *Dimension* elementi ricevono credito per *eventi di successo*.


>[!WARNING]
>
>**I modelli di attribuzione** sono così frequentemente associati a **canali di marketing** che ho intenzionalmente *cancellato* ❷ CANALE nell&#39;immagine qui sopra per illustrare che è possibile eseguire l&#39;analisi di **attribuzione** rispetto alla maggior parte delle altre ***dimensioni***.


Di fatto, raramente un dato percorso di clienti è realmente lineare e anche meno spesso prevedibile.  Inoltre, ogni cliente procederà secondo il proprio ritmo; spesso, può tornare indietro, fermarsi, uscire o impegnarsi in altri comportamenti non lineari. Queste azioni organiche rendono difficile o praticamente impossibile conoscere l’impatto delle attività di marketing in tutto il percorso di clienti. Inoltre, ostacola gli sforzi volti a collegare più canali di dati tra loro.

Esatto.  Lasciate alle porte le vostre analogie &quot;domino&quot; e aprite le vostre menti a concetti più simili all&#39;effetto farfalla e alla teoria delle stringhe - ma come tutto il resto, dobbiamo iniziare con alcune delle basi.

## **Modelli di attribuzione**

Quando si utilizza il **pannello di attribuzione**, è possibile osservare diverse cose.  Ad esempio, i **modelli di attribuzione** ci dimostrano come le nostre *conversioni* (ovvero ❶ **metriche di successo**) possono essere distribuite tra *hit* in qualsiasi gruppo.

In poche parole, se **10 persone** premete un **BIG RED BUTTON** per varcare una porta, i nostri **modelli di attribuzione** ci diranno a quali di queste **10 persone** vogliamo assegnare il &quot;credito&quot; - o meglio ancora, a quale *molto* &quot;credito&quot; vogliamo assegnare - per aver premuto detto pulsante.

![Button](assets/button.png)

Tenendo presente questo aspetto, ecco alcuni esempi di come i ❸ **modelli di attribuzione** potrebbero influire su queste **10 persone**:

- **Primo contatto**: questo modello funziona esattamente come sembra concedendo **100% di credito** alla *prima* persona che ha attraversato la porta.  È più probabile che gli addetti al marketing utilizzino questo approccio per tattiche come ***social media*** o ***display***; tuttavia, è anche un&#39;ottima tattica da utilizzare spesso per garantire l&#39;efficacia dei consigli sui prodotti nel sito.
- **Ultimo contatto**: questa tattica funziona esattamente come se suonasse, ma attribuisce invece **un credito del 100%** all&#39;ULTIMA persona che ha attraversato la porta.  Questo modello viene in genere utilizzato per analizzare elementi come ***ricerca naturale (organica)*** e altre *campagne a breve termine* del ciclo di marketing.
- **Lineare**: questo modello distribuisce lo stesso credito a OGNI SINGOLA PERSONA che ha camminato attraverso la porta.

  >[!CAUTION]
  >
  >Tuttavia, si consiglia cautela in questo caso, perché è possibile diffondere i risultati molto rapidamente quando si applica questa tattica, considerando il tempo di esecuzione e l’ampiezza del pubblico che raggiunge.

- **A forma di U**: questo approccio assegna il **40%** del credito alla *prima persona* sulla porta, distribuisce il **20%** del credito tra *tutti tra* e quindi assegna il **40%** al **ultimo** tramite. Questo modello verrà utilizzato il più delle volte in situazioni in cui si dispone di un **lungo ciclo di conversione/vendita** contenente *diversi punti di contatto* lungo il percorso.  In questo caso, l&#39;obiettivo è quello di evidenziare principalmente le tattiche di marketing ***first*** e ***last*** che hanno contribuito alla conversione del cliente.
- **J**-**A forma** e **J** inversa:
   - Pensa a **A forma di U**, ma questo modello assegna il credito **60%** alla *ultima persona* che cammina attraverso la porta, **20%** alla *prima*, quindi *divide* il resto **20%** in *tutti gli altri* al centro.  **J** inversa esegue l&#39;esatto contrario.

     L&#39;obiettivo è quello di mettere la maggior parte della tua enfasi, sia al *inizio* o al *fine* della tua campagna; tuttavia, desideri comunque assegnare un certo importo di credito all&#39;elemento che contribuisce sul lato opposto, riconoscendo i &quot;ragazzi piccoli&quot; lungo il percorso.

- **Decadimento nel tempo**: se non lo condividessi, verrei licenziato. Questo modello ha letteralmente un&#39;emivita che decade esponenzialmente - nel tempo!  In questo caso, il parametro *default* per l&#39;emivita di questo modello è **7 giorni**.  Funziona in modo da applicare *peso* a ciascun **canale di marketing**, *in base al tempo* trascorso dopo il *punto di contatto iniziale* e al momento della conversione del cliente.

  I modelli di attribuzione **Decadimento nel tempo** e **A forma di U** sono entrambi utilizzati in genere per misurare campagne a più lungo termine, ma come puoi vedere, hanno obiettivi leggermente diversi, in base a come alla fine *pesano* il valore del risultato.

- **Personalizzato**: scegli chi riceverà il credito.  È la tua campagna!

Per ulteriori informazioni su questi e altri modelli di attribuzione, [fai clic qui](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html?lang=en)

Per rendere questo ancora più interessante, parliamo di tornare indietro l&#39;orologio!

## **Intervalli di lookback**

Ora è il momento di iniziare a portare la tua mente al livello successivo.  In questo ambito aggiungiamo letteralmente l’elemento del viaggio nel tempo alla nostra analisi, e di nuovo iniziamo con le nozioni di base.

***Adobe*** definisce ❹ **intervalli di lookback** come &quot;la quantità di tempo che una conversione deve recuperare per includere i punti di contatto. I modelli di attribuzione che attribuiscono maggiore credito alle prime interazioni visualizzano differenze più grandi quando si visualizzano diversi intervalli di lookback.&quot;


In altre parole, **intervalli di lookback** determinano il periodo di tempo durante il quale *vengono considerate le conversioni* e forniscono *contesto* all&#39;analisi dell&#39;attribuzione. ***Adobe Analytics*** offre tre tipi di **intervalli di lookback**:

- **Intervallo di lookback su visita:** considera l&#39;inizio di una ***visita*** in caso di conversione, fornendo informazioni sulle interazioni immediate che hanno portato alle conversioni.

  Ricorda che in genere si tratta dell&#39;**intervallo di lookback** più breve da utilizzare.
- **Intervallo di lookback su visitatore:** esamina tutte le ***visite*** fino al primo del mese all&#39;interno dell&#39;**intervallo di date** selezionato, offrendo una visualizzazione molto più ampia delle interazioni del cliente e aiutando a identificare i pattern nel tempo.
- **Intervallo di lookback personalizzato:** Consente di espandere la **finestra di attribuzione** oltre l&#39;**intervallo di date** di reporting fino a un *massimo* di **90 giorni**.  Offre *flessibilità* nell&#39;acquisizione dei punti di contatto che si sono verificati *al di fuori* dell&#39;**intervallo di date** selezionato, garantendo un&#39;analisi completa.

Regolando un determinato **intervallo di lookback**, gli analisti possono quindi esaminare l&#39;impatto di uno o più punti di contatto all&#39;interno di intervalli di tempo specifici e ottenere informazioni più approfondite su come le diverse durate influiscono sui risultati di attribuzione.

## **Raggruppamento di tutti i componenti**

Cosa significa tutto questo per noi analisti?

Il **pannello di attribuzione** e l&#39;**intervallo di lookback** ci offrono la possibilità di guardare oltre i dati mondani a livello di superficie e approfondire il percorso dei clienti. Capendo quali punti di contatto hanno avuto il maggiore impatto sulle *conversioni*, possiamo prendere decisioni informate sulle nostre strategie di marketing e allocare le risorse in modo più efficace.

Ricorda che dopo aver selezionato **modelli di attribuzione** e **intervalli di lookback**, puoi manipolare ulteriormente i dati filtrandoli con un ❺ **segmento,** o qualsiasi altro componente desiderato a questo punto.  Inoltre, una volta eseguito il rendering del pannello, avrai a disposizione tutte le funzionalità di un Workspace tradizionale.

## **Implementazione completata**

Ora che hai i concetti inattivi, immagina di eseguire una campagna di marketing e di provare a determinare quale canale è il *più efficace* per stimolare le conversioni. Con l&#39;aiuto del **pannello di attribuzione**, non solo puoi visualizzare l&#39;**ultimo contatto**, ma anche il **primo contatto**, **stesso contatto** e qualsiasi altro **modello** scelto per determinare quali **canali** sono i *più efficaci* per le *conversioni*. Queste informazioni possono quindi essere utilizzate per *ottimizzare* le campagne e migliorare le prestazioni complessive semplicemente ripristinando l&#39;orologio con l&#39;**intervallo di lookback** scelto.

Ora che hai visto cosa può fare, non farti ingannare o intimidire dalle caratteristiche apparentemente complesse del pannello attribuzione.  **Affrontalo**.  *Abbraccia*.  **Comprendi**.
MA SOPRATTUTTO - *Utilizzalo a tuo vantaggio.* Il **pannello di attribuzione** e l&#39;**intervallo di lookback** sono le chiavi per una comprensione più approfondita dei tuoi clienti e del loro percorso con il tuo marchio.

Ora possiamo viaggiare &quot;[indietro nel tempo](https://youtu.be/gVryJmZNFdU)&quot; con sicurezza e utilizzare la potenza della nostra affidabile macchina del tempo (alias ***Adobe Analytics***) per prendere decisioni basate sui dati.

## Autore

Questo documento è stato scritto da:

![Jeff Bloomer](assets/jeff-headshot.png)

**Jeff Bloomer**, Manager, Digital Analytics presso Kroger Personal Finance

Adobe Analytics Champion
