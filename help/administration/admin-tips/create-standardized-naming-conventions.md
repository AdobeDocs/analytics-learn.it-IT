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
TQID: 'https://experienceleague.adobe.com/nnAluH2AvqNbWEPk3lbthk-xDl-tnqyW8uHg4Beurq0'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: c24fe15a-643a-47bd-8278-5e027df49785
    internal-label: Implementation basics
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 3e00cf9416ba2c6886e5a7efb952cac8ce370930
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 78%
---
# Standardizzare le convenzioni di denominazione

**COSA:** le convenzioni di denominazione standard interessano sia il nome della variabile quando questa è abilitata nell’interfaccia utente di Adobe Analytics (AA) per l’amministratore, sia i valori trasmessi nella dimensione. Ad esempio, i nomi di pagina saranno “page name (v1)” come nome di variabile, e i valori di nome della pagina trasmessi devono essere uniformi e seguire una struttura o gerarchia specifica (come “sitename|homepage” oppure “sitename|search|searchresults”).

**PERCHÉ:** le convenzioni di denominazione sono un ottimo modo per mantenere tutto uniforme e rendere l’interfaccia facile da capire per i tuoi utenti. Se crei questi elementi fin dall’inizio e li applichi nella piattaforma e nel codice, in futuro sarà più semplice estenderli.

**COME:** L&#39;interfaccia e il documento sui tag devono corrispondere per &#39;Nome&#39; e &#39;Descrizione&#39;. In questo modo gli utenti non dovranno usare un documento Excel e potranno comprendere i dati direttamente nell&#39;interfaccia. Si consiglia inoltre di usare sempre lettere minuscole, per coerenza.

È sempre meglio mantenere coerenza tra i nomi delle pagine (o tra i nomi delle schermate per le app) anche all’interno della piattaforma. È ad esempio possibile impostare `property:section:sub section:sub sub section:unique page name` in una variabile/dimensione. Se tutti questi sono campi separati nel livello dati, puoi anche creare il nome della pagina direttamente nel file JS o in Launch. Se tutti questi elementi sono impostati nelle proprie dimensioni, sarà più facile suddividere proprietà o aree specifiche del sito o dell’app e sarà possibile comprendere meglio il traffico e i flussi.

Qualsiasi cosa che consenta agli utenti di trovare e comprendere più facilmente i dati, compresi elementi semplici come le convenzioni di denominazione, aumenterà il tasso di utilizzo di Adobe Analytics e fornirà informazioni migliori per il business.

## Autori

Questo documento è stato scritto da:

![Christel Guidon](assets/Christel-Headshot-150.png)

Christel Guidon, Digital Analytics Platform Manager di NortonLifeLock
Adobe Analytics Champion

![Rachel Fenwick](assets/Rachel-Fenwick-150.png)

Rachel Fenwick, Senior Consultant presso Adobe
