---
title: Standardizzare le convenzioni di denominazione
description: Le convenzioni di denominazione standard interessano sia il nome della variabile quando questa è abilitata nell’interfaccia utente di AA per l’amministratore, sia i valori trasmessi nella dimensione.
feature: Implementation Basics
topic: Administration
role: Admin
level: Beginner
doc-type: article
thumbnail: 10531.jpg
kt: 10531
exl-id: 0fe3b981-0d9b-4f12-a6ca-63a4140f4baf
source-git-commit: df00d4fb8cc5093903ed4628dfe12f152294123a
workflow-type: ht
source-wordcount: '339'
ht-degree: 100%

---

# Standardizzare le convenzioni di denominazione

**COSA:** le convenzioni di denominazione standard interessano sia il nome della variabile quando questa è abilitata nell’interfaccia utente di Adobe Analytics (AA) per l’amministratore, sia i valori trasmessi nella dimensione. Ad esempio, i nomi di pagina saranno “page name (v1)” come nome di variabile, e i valori di nome della pagina trasmessi devono essere uniformi e seguire una struttura o gerarchia specifica (come “sitename|homepage” oppure “sitename|search|searchresults”).

**PERCHÉ:** le convenzioni di denominazione sono un ottimo modo per mantenere tutto uniforme e rendere l’interfaccia facile da capire per i tuoi utenti. Se crei questi elementi fin dall’inizio e li applichi nella piattaforma e nel codice, in futuro sarà più semplice estenderli.

**COME:** l’interfaccia e il documento sui tag devono corrispondere per “Nome” e “Descrizione”; così gli utenti non dovranno usare un documento Excel e potranno comprendere i dati direttamente nell’interfaccia. Si consiglia inoltre di usare sempre lettere minuscole, per coerenza.

È sempre meglio mantenere coerenza tra i nomi delle pagine (o tra i nomi delle schermate per le app) anche in tutta la piattaforma. Ad esempio, puoi impostare “property:section:sub section:sub sub section:unique page name” in una variabile/dimensione. Se tutti questi sono campi separati nel livello dati, puoi anche creare il nome della pagina direttamente nel file JS o in Launch. Se tutti questi elementi sono impostati nelle proprie dimensioni, sarà più facile suddividere proprietà o aree specifiche del sito o dell’app e sarà possibile comprendere meglio il traffico e i flussi.

Qualsiasi cosa che consenta agli utenti di trovare e comprendere più facilmente i dati, compresi elementi semplici come le convenzioni di denominazione, aumenterà il tasso di utilizzo di Adobe Analytics e fornirà informazioni migliori per il business.

## Autori

Questo documento è stato scritto da:

![Christel Guidon](assets/Christel-Headshot-150.png)

Christel Guidon, Digital Analytics Platform Manager presso NortonLifeLock 
Adobe Analytics Champion

![Rachel Fenwick](assets/Rachel-Fenwick-150.png)

Rachel Fenwick, Senior Consultant presso Adobe
