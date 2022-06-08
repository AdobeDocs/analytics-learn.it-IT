---
title: Utilizzare una suite di rapporti globale
description: Disporre di una singola suite di rapporti globale può essere utile in molti modi e semplificare davvero la tua implementazione.
feature: Implementation Basics
topic: Administration
role: Admin
level: Beginner
doc-type: article
thumbnail: 10536.jpg
kt: 10536
source-git-commit: 160df6c23acb67f1b07f2fcd25f1eca96eb6dee7
workflow-type: tm+mt
source-wordcount: '763'
ht-degree: 0%

---


# Utilizzare una suite di rapporti globale

**COSA:** È invitante creare suite di rapporti per ciascuno dei siti, ma questo può diventare rapidamente il tuo peggiore incubo, sia in termini di complicazione dei rapporti che di implementazione. Disporre di una singola suite di rapporti globale può essere utile in molti modi e semplificare davvero la tua implementazione.

**PERCHÉ:** La creazione di una suite di rapporti globale è l’unica opzione disponibile per una visualizzazione unificata delle proprietà digitali e dei percorsi degli utenti in ciascuna proprietà. Se disponi di un’app mobile e di un sito web, devi sempre combinare i dati dell’app e i dati web in un’unica suite di rapporti per sfruttare i percorsi dei diversi dispositivi e tenere traccia di quelli che visitano entrambe le proprietà come un singolo visitatore rispetto a suite di rapporti separate, dove avresti un set di dati slegati che mostra 2 visitatori - 1 per ogni proprietà - senza poter conoscere il crossover.

Di seguito sono riportati i vantaggi/gli svantaggi di avere una singola suite di rapporti per aiutarti a valutare le opzioni:

* PROS:
   * Essere in grado di capire facilmente il tuo panorama digitale. Se hai implementato la dimensione &quot;proprietà&quot; (eVar) a cui si fa riferimento in altri suggerimenti, sarai molto facilmente in grado di ottenere un&#39;unica visualizzazione di tutti i tuoi siti e app, traffico e conversioni. Questa visione d&#39;insieme è fondamentale per comprendere il tuo business in generale.
   * Allo stesso modo, ora puoi vedere come gli utenti scorrono tra tutte le tue proprietà e capire il loro percorso in tutto il tuo panorama digitale.
   * Facilità di amministrazione. Quando utilizzi più suite di rapporti, dovrai mantenere l’interfaccia in diverse posizioni, nonché diversi documenti di tagging (o più complessi). Mantenere tutto in un&#39;unica posizione significa che c&#39;è un solo posto in cui eseguire gli aggiornamenti. Inoltre, rende molto più semplice la concessione dell&#39;accesso.
   * Migliore usabilità nell&#39;interfaccia. Se gli utenti hanno una sola posizione in cui andare, non devono pensare a quale suite di rapporti selezionare. Tieni presente che non puoi utilizzare più suite di rapporti all’interno dello stesso pannello dell’area di lavoro e che averne diverse potrebbero confondere i tuoi utenti.
   * Meno chiamate server = meno costi. Se effettui chiamate a più suite di rapporti, aumenta i costi. Mantenere semplice l&#39;implementazione consente inoltre di ridurre i costi.
   * Puoi semplicemente sfruttare le suite di rapporti virtuali (VRS) per suddividere i dati specifici per il sito all’interno della suite di rapporti globale e limitare le autorizzazioni dell’utente in base a una VRS, se necessario. Una volta separati i dati in suite di rapporti individuali, non puoi eseguirne il rollup, ma se sono già uniti in un set di dati (RS globale), possono essere facilmente suddivisi.
* CONS:
   * Se disponi di proprietà molto separate in cui gli utenti non passano da una all’altra e non sono mai tenuti a farlo, puoi mantenere suite di rapporti separate.
   * Se le proprietà hanno esigenze di assegnazione tag e reporting molto diverse, può essere utile impostare suite di rapporti separate nell’interesse dell’efficienza variabile. Disporre di suite di rapporti separate offre maggiore flessibilità nell’utilizzo di variabili personalizzate (più eVar).
   * Superato gli Univoci: L’interfaccia di Adobe Analytics ti consente di visualizzare solo 500.000 valori univoci all’interno di una singola dimensione per un determinato periodo di tempo. Una volta superato questo limite, i valori verranno raggruppati come &quot;univoci superate&quot; o &quot;traffico ridotto&quot; nell’interfaccia. Questi valori rimangono disponibili sul backend (ad es. Data Warehouse, Feed dati), ma non possono essere visualizzati all’interno dell’interfaccia. Se disponi di dati molto granulari (come ID utente, PSN, ecc.), è facile raggiungere questo livello. Questo problema può essere utile se disponi di suite di rapporti separate.

**COME:** Iniziare con una nuova implementazione AA e utilizzare una suite di rapporti globale è semplice e semplice. È sufficiente creare la suite di rapporti globale (una per Dev e una per Prod) nell’interfaccia utente di amministrazione di AA e applicare gli stessi valori ID suite di rapporti (RSID) in tutte le proprietà.

La migrazione da una strategia a più tag con una suite di rapporti univoca per ogni proprietà richiede più strategia e pianificazione. Alcune delle considerazioni da tenere a mente:

* L’allineamento delle variabili (ad esempio, eVar1 sulla proprietà A deve acquisire lo stesso punto dati di eVar1 sulla proprietà B)
* Consolidamento di eventuali regole di elaborazione, regole del canale di marketing, classificazioni (SAINT e Generatore di regole)
* Migrazione di feed di dati e origini dati
* Scelta di una data di interruzione e comunicazione con tutti gli utenti aziendali

## Autori

Questo documento è stato scritto congiuntamente da:

![Christel Guidon](assets/Christel-Headshot-150.png)

Christel Guidon, Digital Analytics Platform Manager presso NortonLifeLock Adobe Analytics Champion

![Rachel Fenwick](assets/Rachel-Fenwick-150.png)

Rachel Fenwick, Consulente senior all&#39;Adobe
