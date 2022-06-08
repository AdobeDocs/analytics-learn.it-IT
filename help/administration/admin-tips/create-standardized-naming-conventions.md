---
title: Creare convenzioni di denominazione standardizzate
description: Le convenzioni di denominazione standard si applicano sia al nome della variabile stesso quando è abilitato nell’interfaccia utente di amministrazione di AA che ai valori passati nella dimensione.
feature: Implementation Basics
topic: Administration
role: Admin
level: Beginner
doc-type: article
thumbnail: 10531.jpg
kt: 10531
source-git-commit: 160df6c23acb67f1b07f2fcd25f1eca96eb6dee7
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 0%

---


# Creare convenzioni di denominazione standardizzate

**COSA:** Le convenzioni di denominazione standardizzate si applicano sia al nome della variabile stesso quando è abilitato nell’interfaccia utente di amministrazione di Adobe Analytics (AA) sia ai valori passati nella dimensione. (ad esempio, i nomi di pagina saranno &quot;page name (v1)&quot; come nome di variabile e i valori del nome di pagina trasmessi devono essere uniformi e seguire una struttura/gerarchia specifica come &quot;sitename|homepage&quot; o &quot;sitename|search|searchresults&quot;).

**PERCHÉ:** Le convenzioni di denominazione sono un ottimo modo per mantenere tutto uniforme e mantenere l&#39;interfaccia facile da capire per i tuoi utenti. Se crei questi elementi fin dall’inizio e li applichi nella piattaforma e nel codice, sarà più semplice ridimensionarli.

**COME:** L’interfaccia e il documento di assegnazione tag devono corrispondere sia per &#39;Nome&#39; che per &#39;Descrizione&#39;, in modo da salvare i tuoi utenti dalla necessità di estrarre un documento Excel e consentire loro di comprendere i tuoi dati direttamente nell’interfaccia. Si consiglia inoltre di mantenere tutte le lettere minuscole per coerenza.

È sempre meglio mantenere coerenza tra i nomi delle pagine anche in tutta la piattaforma (o tra i nomi delle schermate per le app). Ad esempio, puoi impostare la proprietà:section:sottosezione:sottosezione:nome pagina univoco&quot; in una variabile/dimensione. Se tutti questi sono campi separati nel livello dati, puoi anche creare il nome della pagina direttamente nel file JS/Launch. Disporre di tutti questi elementi nelle proprie dimensioni può aiutarti a suddividere più facilmente proprietà o aree specifiche del sito/app e a comprendere meglio il traffico e i flussi.

Qualsiasi cosa che consenta agli utenti di trovare e comprendere più facilmente i dati, compresi elementi semplici come le convenzioni di denominazione, aumenterà l’utilizzo di Adobe Analytics e fornirà informazioni migliori per il business.

## Autori

Questo documento è stato scritto congiuntamente da:

![Christel Guidon](assets/Christel-Headshot-150.png)

Christel Guidon, Digital Analytics Platform Manager presso NortonLifeLock Adobe Analytics Champion

![Rachel Fenwick](assets/Rachel-Fenwick-150.png)

Rachel Fenwick, Consulente senior all&#39;Adobe
