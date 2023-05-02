---
title: Informazioni sul pannello di attribuzione e sulle finestre di lookback di Adobe Analytics
description: Scopri come utilizzare il pannello Attribuzione e l’intervallo di lookback per comprendere il comportamento dei clienti e personalizzare il modo in cui gli elementi dimensionali ricevono credito per gli eventi di successo.
feature: Attribution
role: User
level: Experienced
doc-type: Article
last-substantial-update: 2023-05-02T00:00:00Z
jira: KT-13181
thumbnail: KT-13181.jpeg
source-git-commit: d7b1fac5c98080f9ca786ea21a3700d2937c7ebc
workflow-type: tm+mt
source-wordcount: '1883'
ht-degree: 2%

---


# Informazioni sul pannello di attribuzione e sulle finestre di lookback di Adobe Analytics

Scopri come utilizzare il pannello Attribuzione e l’intervallo di lookback per comprendere il comportamento dei clienti e personalizzare il modo in cui gli elementi dimensionali ricevono credito per gli eventi di successo.

## Utilizzo del pannello Attribution 

![Delorea](assets/delorean.png)

&quot;Grande Scott!&quot;

Non appena ho pensato al [Pannello Attribution](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/attribution.html) e **Finestra di lookback** Mi è stato ricordato il brano &quot;Back in Time&quot; di Huey Lewis e il News; poi, ovviamente, mi è stato anche ricordato che la nostra tipica risposta a molti nuovi strumenti come questi è semplicemente di posticipare il tentativo di usarli, perché sembrano così complicati.

Voglio dire, guardate tutte quelle opzioni, interruttori, pannelli, letture e manopole.  E seriamente, parliamo di quel condensatore a flusso.  Aspetta, ho appena detto condensatore di flusso?

OK, ammetterò il **Pannello Attribution** è uno strumento piuttosto complesso; tuttavia, il nostro tipico lavoro come analisti, giorno dopo giorno, è quello di usare uno strumento molto complesso per guardare a quello che è successo in passato.  Questo strumento si chiama **Adobe Analytics**!

Perciò, perché dovremmo permettere a qualcosa come un po&#39; di paura di ostacolare uno strumento così forte e potente che ci permette di guardare letteralmente indietro nel tempo ogni giorno?

Siamo tutti di quella roba, giusto?  GIUSTO??! (Dai, sono abbastanza sicuro che vada bene e &quot;politicamente corretto&quot; chiamarci geeks?)

Ah, a chi importa?  Ingrandisci, Geeks, Nerds, Goobers, Dweebs, e Techies (sì anche i Trekies), posso sentire l&#39;auto stereo ora:

&quot;Allora portami via, non mi dispiace!  Ma è meglio che tu mi prometta... TORNERÒ IN TEMPO!&quot;

Ho la tua attenzione, ora, giusto?  Fantastico!


Distruggiamo un po&#39; le cose.  Ora che siamo tutti entusiasti **viaggio nel tempo** Facciamo un passo indietro e stabiliamo che cosa **Pannello Attribution** veramente è:

![Controllo del tempo](assets/time-control.gif)

No, no, no, no, no!  Non distraiamoci per ora.  Forse riproviamo:

![Finestra Attribution](assets/attribution-window.png)

In **Attribuzione**, considera semplicemente come eventi/azioni possano essere causati da un individuo, più individui, o uno o più elementi diversi nel tempo.

Secondo [Adobe](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/attribution.html), l’attribuzione consente agli analisti di personalizzare il modo in cui gli elementi dimensionali ottengono credito per gli eventi di successo.  Infatti, nessun dato percorso cliente è sempre realmente lineare ed è meno prevedibile.  Moreso, ogni cliente procederà secondo il proprio ritmo; spesso possono raddoppiare, arrestare, abbandonare o impegnarsi in altri comportamenti non lineari. Queste azioni organiche rendono difficile o praticamente impossibile conoscere l&#39;impatto delle attività di marketing in tutto il percorso di clienti. Inoltre, ostacola gli sforzi volti a collegare più canali di dati tra loro.

Qualcuno di questo vi suona familiare?  Pensateci nel contesto del percorso di Marty McFly:

![Torna al futuro 1](assets/back-to-the-future1.png)![Torna al futuro 2](assets/back-to-the-future2.png)

Dal momento in cui è fuggito dal parcheggio del centro commerciale Twin Pines a quando si è letteralmente buttato fuori dal DeLorean prima che fosse annientato da una locomotiva da 210 tonnellate sembra lontano dall&#39;essere lineare, e non è niente che nessuno avrebbe potuto prevedere.

Eppure, grazie al potere della magia cinematografica, possiamo seguire il percorso di Marty nel tempo e capire tutti i suoi punti di contatto, le sue bancarelle, i doppi schienali e gli abbandoni.

## Modelli di attribuzione

Nella vita reale, usiamo il **Pannello Attribution** per vedere diverse cose diverse.  Ad esempio, il **Modelli di attribuzione** mostra come **conversioni** sono distribuiti tra **hit** in un determinato gruppo.

In poche parole, se 10 persone premono un pulsante per attraversare una porta, i nostri modelli di attribuzione ci diranno quale di quelle 10 persone vogliamo dare il merito di aver premuto quel pulsante.  Tenendo presente ciò, ecco alcuni esempi di come i modelli di attribuzione potrebbero influenzare queste 10 persone:
* **Primo contatto**: Questa è esattamente come sembra.  In questo caso, dà il 100% di credito alla prima persona che ha camminato attraverso la porta.  Per questo, è più probabile che gli esperti di marketing lo utilizzino per tattiche come Social o Display, ma spesso è una tattica eccellente per l&#39;efficacia dei consigli sui prodotti in loco.
* **Ultimo contatto**: Anche esattamente come suona.   Questo modello dà il 100% di credito all&#39;ultima persona che ha camminato nella porta.  Questo modello viene spesso utilizzato per analizzare elementi come campagne Search (Ricerca) e a breve termine del ciclo di marketing.
* **Lineare**: Questo dà pari merito a ogni singola persona che ha camminato attraverso la porta.  Esatto - Prendi un DeLorean, prendi un DeLorean, e prendi un DeLorean.  TUTTI SI DIVENTANO DELOREANI!!!
* **A forma di U**: Questo dà il 40% del credito al primo nella porta, distribuisce il 20% del credito a tutti nel mezzo e poi dà il 40% all&#39;ultimo attraverso.  Pensate a una situazione in cui volete riconoscere le conversioni a maggioranza sia sul fronte che sul retro, ma anche volete spruzzare una piccola quantità di credito in alcune delle interazioni che contribuiscono nel mezzo.
* **Decadimento nel tempo**: Mi mancherei se non avessi condiviso questo con te prima di inviarti alla documentazione ufficiale per rivedere i modelli rimanenti.  Come il plutonio di Doc Brown, questo modello ha letteralmente una mezza vita che è in declino esponenziale!  In questo caso, il parametro predefinito per la mezza durata del modello è 7 giorni.  Il modo in cui funziona consiste nell’applicare peso a ciascun canale di marketing, in base al tempo che trascorre dopo il punto di contatto iniziale e quando il cliente si converte.

Per ulteriori informazioni su questo e sugli altri **Modelli di attribuzione**, [fai clic qui](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html?lang=it).

Per rendere questo ancora più interessante, parliamo del **Windows di lookback**.

Già, eccoci qui - riportaci indietro nel tempo!!  Perché ecco dove inizia il divertimento!

Adobe definisce **Windows di lookback** come &quot;la quantità di tempo che una conversione deve recuperare per includere i punti di contatto. I modelli di attribuzione che attribuiscono maggiore credito alle prime interazioni visualizzano differenze più importanti quando si visualizzano diversi intervalli di lookback.&quot;

* **Intervallo di lookback su visita**: Considera fino all’inizio di una visita quando si è verificata una conversione
* **Intervallo di lookback su visitatore**: Esamina tutte le visite precedenti al 1° del mese dell’intervallo di date corrente.
* **Intervallo di lookback personalizzato**: Consente di espandere la finestra Attribuzione oltre l’intervallo di date del rapporto fino a un massimo di **90 giorni**.

Se avete visto TUTTI i film Back to the Future, sapete che Marty McFly è tornato indietro nel tempo più di una volta, e sapete anche che è tornato nel 1955 più di una volta.  Se ci affidiamo all&#39;acquisizione di &quot;Gray&#39;s Sports Almanac&quot; come nostro evento di conversione, allora considera quanto segue:

![Almanacco sportivo](assets/sports-almanac.png)

1. Un po&#39; prima **1:30** su **26 ottobre 1985**, Marty McFly torna indietro nel tempo a **5 novembre 1955**, dove prima corre sopra un pino in un DeLorean che viaggia nel tempo.  Nel corso della settimana successiva e mezzo, interagisce con più persone, inclusi i suoi genitori, influenzando in ultima analisi il futuro influenzando suo padre per opporsi ad un bullo di nome Biff, in modo che suo padre possa realizzare il suo potenziale per diventare un autore di fantascienza di successo.
1. Più tardi la stessa mattina **26 ottobre 1985** Il dottor Emmett Brown arriva sul vialetto di Marty McFly per informare lui e la sua ragazza che qualcosa è andato terribilmente storto con i loro figli e devono correre in futuro per risolvere i loro problemi.  Mentre partono, la loro partenza è testimoniata da Biff, che trova strano vedere un DeLorean volante.  Più tardi, in futuro, come Biff di nuovo testimoni un DeLorean volante e anche più tardi cattura la vista di &quot;due versioni&quot; di Marty, inizia a mettere insieme le cose.   Quando sente Doc Brown e Marty discutere come la &quot;macchina del tempo&quot; non dovrebbe mai essere utilizzata per un guadagno personale e solo per la ricerca (perché Marty aveva pensato di prendere un almanacco sportivo indietro al passato per fare alcune scommesse personali), Biff ruba la macchina del tempo mentre i due sono distratti a consegnare l&#39;almanacco sportivo al suo più giovane sé in passato.
1. Dopo il loro viaggio verso il futuro, Doc Brown e Marty ritornano a un **26 ottobre 1985** non riconoscono, e deducono che le linee temporali sono state alterate da un malvagio Biff.  Rendendosi conto che devono correggere quello che è successo, Doc e Marty decidono di tornare a **12 novembre 1955**, la notte fatale in cui tutto è stato cambiato da Marty quando ha visitato per la prima volta **1955**.  Doc e Marty in ultima analisi salvano la giornata rubando l&#39;almanacco sportivo che Old Biff dal futuro aveva consegnato a Young Biff in **1955** Ma non senza un altro colpo di scena è davvero necessario guardare la trilogia completa dei film per godere veramente e capire.

A seconda della nostra **Modello di attribuzione** e **Finestra di lookback**, possiamo concludere con alcuni scenari interessanti:

* Utilizzo **primo contatto** e **finestra di lookback su visita**, l&#39;attribuzione guarda alla visita di Marty dove si è verificata la più recente &quot;conversione&quot;, che è quando lui e Doc riescono a rubare l&#39;almanacco sportivo indietro da Young Biff e mantenere la sua avversione al letame.

![Biff 1](assets/biff1.png)![Biff 2](assets/biff2.png)

* Credeteci o no, utilizzando **primo contatto** e **intervallo di lookback su visitatore**, l’attribuzione favorirebbe la conversione in cui alla fine vince Biff.
* Applicazione di un **intervallo di lookback lineare** risulterebbe in un multiplo in cui esiste ogni timeline.  Spiacente, questo non lo è **Marvel** o **Star Trek**!

E a questo punto, spero che cominciate a farvi un&#39;idea.

Cosa significa tutto questo per noi analisti?

La **Pannello Attribution** e **Finestra di lookback** ci dà la possibilità di guardare oltre i semplici dati a livello di superficie e di immergerci nel percorso dei clienti. Capendo quali punti di contatto hanno avuto il maggiore impatto sulle conversioni, possiamo prendere decisioni informate sulle nostre strategie di marketing e allocare le risorse in modo più efficace.

Ricorda, dopo aver **Modelli di attribuzione** e **Windows di lookback** selezionata, puoi comunque manipolare ulteriormente i dati filtrandoli con un segmento o qualsiasi altro componente desiderato.  Inoltre, dopo il rendering del pannello, hai tutte le funzionalità di un **Area di lavoro**, che significa che il tuo permesso ufficiale di guidare 88 mph!

## Infine mettere in pratica

Ora che i concetti sono incompleti, immagina di lanciare una campagna di marketing e di cercare di determinare quale canale è più efficace per stimolare le conversioni. Con l&#39;aiuto del **Pannello Attribution**, non solo puoi vedere **Ultimo contatto**, ma anche **Primo contatto**, **Stesso contatto**, e qualsiasi altro modello scelto, per determinare quali canali sono più efficaci nel promuovere le conversioni. Quindi, queste informazioni possono essere utilizzate per ottimizzare le campagne e migliorare le prestazioni complessive.

Ora che avete visto cosa può fare, non lasciatevi intimidire dalle caratteristiche apparentemente complesse del **Pannello Attribution**.  **Faccia** .  **Abbracciare** .  **Comprendere** .  Soprattutto, usalo a tuo vantaggio. La **Pannello Attribution** e **Finestra di lookback** sono le chiavi per comprendere meglio i tuoi clienti e il loro percorso con il tuo marchio.

Ora, possiamo viaggiare &quot;indietro nel tempo&quot; con fiducia e usare la potenza della nostra fidata macchina del tempo (aka,  **Adobe Analytics**) prendere decisioni basate sui dati; e, cosa più importante, ricordate, &quot;Dove stiamo andando, non abbiamo bisogno di strade!&quot; (Solo un condensatore di flusso e un occhio attento per l&#39;attribuzione!).

![Ritorno al futuro](assets/back-to-the-future3.png)

## Autore

Questo documento è stato scritto da:

![Jeff Bloomer](assets/jeff-headshot.png)

**Jeff Bloomer**, Manager, Digital Analytics presso Kroger Personal Finance

Adobe Analytics Champion
