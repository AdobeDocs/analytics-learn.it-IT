---
title: Utilizzare una suite di rapporti globale
description: L’utilizzo di una singola suite di rapporti globale può essere utile in molti modi e può semplificare notevolmente la tua implementazione.
feature: Implementation Basics
topic: Administration
role: Admin
level: Beginner
doc-type: article
thumbnail: 10536.jpg
kt: 10536
exl-id: 490addfd-b810-4f15-b065-e0e58048c882
source-git-commit: df00d4fb8cc5093903ed4628dfe12f152294123a
workflow-type: tm+mt
source-wordcount: '766'
ht-degree: 100%

---

# Utilizzare una suite di rapporti globale

**COSA:** benché si possa essere tentati di creare una suite di rapporti distinta per ciascun sitio, ben presto questo può rivelarsi molto problematico, complicando sia le attività di reporting sia l’implementazione. L’utilizzo di una singola suite di rapporti globale può essere utile in molti modi e può semplificare notevolmente la tua implementazione.

**PERCHÉ:** la creazione di una suite di rapporti globale è l’unica opzione disponibile per avere una visione unificata delle proprietà digitali e dei percorsi degli utenti nelle varie proprietà. Se hai un’app mobile e un sito web, è importante combinare i dati di entrambe queste proprietà in un’unica suite di rapporti: questo consente infatti sia di seguire i percorsi degli utenti che si avvalgono di diversi dispositivi, sia di tenere traccia di chi visita entrambe le proprietà come un singolo visitatore. Con suite di rapporti separate, invece, si ottengono set di dati distinti che presentatno la stessa persona come 2 visitatori diversi, uno per ogni proprietà, senza la possibilità di incrociarne le attività.

Per aiutarti nella tua scelta, di seguito sono riportati i pro e i contro di avere una singola suite di rapporti:

* PRO:
   * Essere in grado di capire facilmente il tuo intero panorama digitale. Se hai implementato la dimensione “proprietà” (eVar) a cui si fa riferimento in altri suggerimenti, potrai facilmente ottenere un’unica vista per tutti i tuoi siti e le tue app, con i relativi dati di traffico e conversioni. Questa visione d’insieme è fondamentale per comprendere il tuo business nel suo complesso.
   * Allo stesso modo, consente di vedere come gli utenti passano da una proprietà all’altra e capire il loro percorso in tutto il tuo panorama digitale.
   * Facilità di amministrazione. Quando utilizzi più suite di rapporti, devi mantenere l’interfaccia in aree diverse, nonché più documenti sui tag (o più complessi). Mantenendo tutto in un’unica posizione, sarà sufficiente eseguire gli aggiornamenti in un solo posto. Inoltre, è molto più semplice gestirne l’accesso.
   * Migliore usabilità nell’interfaccia. Gli utenti potranno trovare la suite di rapporti in un’unica posizione, e non dovranno preoccuparsi di selezionare quella giusta. Tieni presente che non puoi utilizzare più suite di rapporti all’interno dello stesso pannello dell’area di lavoro e che averne diverse potrebbe confondere i tuoi utenti.
   * Meno chiamate server = meno costi. Se effettui chiamate a più suite di rapporti, aumenti i costi. Mantenere semplice l’implementazione consente inoltre di ridurre i costi.
   * Puoi semplicemente sfruttare le suite di rapporti virtuali (VRS) per suddividere i dati di ogni sito all’interno della suite di rapporti globale e, se necessario, limitare le autorizzazioni utente in base a una VRS. Una volta separati i dati in suite di rapporti individuali, non puoi combinarli insieme; ma se sono già uniti in un singolo set di dati (suite di rapporti globale), possono essere facilmente suddivisi.
* CONTRO:
   * Se le tue proprietà sono molto diverse e gli utenti non possono passare dall’una all’altra, né è previsto che possano farlo, puoi essere preferibile mantenere suite di rapporti separate.
   * Se le varie proprietà hanno esigenze di tag e reporting molto diverse, può essere utile impostare suite di rapporti separate nell’interesse dell’efficienza delle variabili. Disporre di suite di rapporti separate offre maggiore flessibilità nell’utilizzo di variabili personalizzate (più eVar).
   * Valori univoci superati: l’interfaccia di Adobe Analytics consente di visualizzare solo 500.000 valori univoci all’interno di una singola dimensione per un determinato periodo di tempo. Una volta superato questo limite, i valori verranno raggruppati nell’interfaccia come “valori univoci superati” o “traffico ridotto”. Questi valori rimangono disponibili sul backend (ad es. Data Warehouse, Feed dati), ma non possono essere visualizzati nell’interfaccia. Se disponi di dati molto granulari (come ID utente, PSN, ecc.), è facile raggiungere questo limite. Questo problema può essere risolto utilizzando suite di rapporti separate.

**COME:** iniziare con una nuova implementazione di AA e utilizzare una suite di rapporti globale è semplice. È sufficiente creare la suite di rapporti globale (una per Dev e una per Prod) nell’interfaccia utente di amministrazione di AA e applicare gli stessi valori ID suite di rapporti (RSID) in tutte le proprietà.

La migrazione da una strategia a più tag con una suite di rapporti univoca per ogni proprietà richiede più pianificazione. Alcune considerazioni da tenere a mente:

* L’allineamento delle variabili (ad esempio, eVar1 nella proprietà A deve acquisire lo stesso punto dati di eVar1 nella proprietà B)
* Consolidamento di eventuali regole di elaborazione, regole del canale di marketing, classificazioni (SAINT e Rule Builder)
* Migrazione di feed di dati e origini dati
* Scelta di una data di interruzione e comunicazione a tutti gli utenti aziendali

## Autori

Questo documento è stato scritto da:

![Christel Guidon](assets/Christel-Headshot-150.png)

Christel Guidon, Digital Analytics Platform Manager presso NortonLifeLock 
Adobe Analytics Champion

![Rachel Fenwick](assets/Rachel-Fenwick-150.png)

Rachel Fenwick, Senior Consultant presso Adobe
