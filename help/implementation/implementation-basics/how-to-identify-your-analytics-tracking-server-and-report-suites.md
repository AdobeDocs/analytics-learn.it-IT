---
title: Come identificare il server di tracciamento di Analytics e le suite di rapporti
description: Quando configuri Adobe Analytics o fai riferimento ad esso in altre soluzioni Experience Cloud, spesso è utile o anche necessario conoscere il "server di tracciamento" di Analytics in uso o anche la "Suite di rapporti" in cui stai inviando i dati. Questo video mostra come individuare entrambi i valori, siano essi già implementati o meno in Adobe Analytics.
feature: Nozioni di base sull’implementazione
topics: null
activity: implement
doc-type: technical video
team: Technical Marketing
kt: 2358
role: '"Sviluppatore, data engineer"'
level: Principiante
translation-type: tm+mt
source-git-commit: f3b3fa7d91b0cb21005b57768ca23ed6700fcc03
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 2%

---


# Come identificare i dati analitici [!DNL Tracking Server] e [!UICONTROL Report Suites] {#how-to-identify-your-analytics-tracking-server-and-report-suites}

Quando configuri Adobe Analytics o fai riferimento ad esso in altre soluzioni Experience Cloud, spesso è utile o anche necessario conoscere il [!DNL Analytics] &quot;[!DNL Tracking Server]&quot; in uso o anche il &quot;[!UICONTROL Report Suite]&quot; in cui stai inviando i dati. Questo video mostra come individuare entrambi i valori, siano essi già implementati o meno in Adobe Analytics.

## Dopo l&#39;implementazione {#after-implementation}

Dopo aver implementato [!DNL Analytics] su un sito, puoi trovare i [!DNL tracking server] e i [!DNL report suite ID] direttamente nel beacon di tracciamento. Il [!DNL tracking server] è il nome host nel beacon, in modo che sia facile da trovare. Gli [!UICONTROL report suite] ID sono un elenco separato da virgole subito dopo &quot;/b/ss/&quot; nel nome del percorso del beacon.

Per visualizzare il beacon e tutte le altre informazioni in arrivo su [!DNL Analytics] e altre soluzioni Experience Cloud, installa l’ [&quot;Experience Cloud Debugger&quot; estensione Chrome](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj?hl=it).

## Prima dell’implementazione {#before-implementation}

**[!DNL Tracking Server]** - Se non hai ancora iniziato con l’implementazione di Adobe Analytics, scegli un sottodominio per &quot;.sc.omtrdc.net&quot;  [!DNL tracking server]. Ad esempio, supponiamo che io abbia un negozio online di cappelli chiamato &quot;Jim&#39;s Brims&quot;. Posso semplicemente impostare il mio [!DNL tracking server] su:

&quot;jimsbrims.sc.omtrdc.net&quot;.

**[!UICONTROL Report Suite]** - Per trovare un elenco dei tuoi  [!UICONTROL report suites] che sono stati creati, accedi  [!DNL Analytics] e vai a  [!UICONTROL Admin] >  [!UICONTROL Report Suites] nel menu principale per visualizzare un elenco di  [!UICONTROL report suites], inclusi il loro ID e titolo.

Per ulteriori informazioni, guarda il video seguente.

>[!VIDEO](https://video.tv.adobe.com/v/26061/?quality=12)
