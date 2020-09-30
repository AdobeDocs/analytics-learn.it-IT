---
title: Come identificare il server di tracciamento di Analytics e le suite di rapporti
description: Quando si configura  Adobe Analytics, o quando si fa riferimento ad esso in altre soluzioni  Experience Cloud, spesso è utile o addirittura necessario conoscere il "Server di tracciamento" di Analytics in uso, o anche la "Suite di rapporti" in cui si inviano i dati. In questo video viene illustrato come individuare entrambi i valori, indipendentemente dal fatto che abbiate già implementato  Adobe Analytics.
feature: implementation basics
topics: null
audience: implementer
activity: implement
doc-type: technical video
team: Technical Marketing
kt: 2358
translation-type: tm+mt
source-git-commit: 60f4ce4f563a990576b3331b01cd87c29d424f43
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Come identificare le analisi [!DNL Tracking Server] e [!UICONTROL Report Suites] {#how-to-identify-your-analytics-tracking-server-and-report-suites}

Quando si configura  Adobe Analytics, o quando si fa riferimento ad esso in altre soluzioni  Experience Cloud, spesso è utile o addirittura necessario conoscere [!DNL Analytics] &quot;[!DNL Tracking Server]&quot; in uso, o anche &quot;[!UICONTROL Report Suite]&quot; in cui si inviano i dati. In questo video viene illustrato come individuare entrambi i valori, indipendentemente dal fatto che abbiate già implementato  Adobe Analytics.

## Dopo l’implementazione {#after-implementation}

Dopo l&#39;implementazione [!DNL Analytics] su un sito, puoi trovare i dati [!DNL tracking server] e quelli [!DNL report suite ID] giusti nel beacon di tracciamento. Il nome host [!DNL tracking server] è quindi facile da trovare nel beacon. Gli [!UICONTROL report suite] ID sono un elenco separato da virgole subito dopo &quot;/b/ss/&quot; nel nome percorso del beacon.

Per visualizzare il beacon, così come tutte le altre informazioni che arrivano a [!DNL Analytics] e altre soluzioni di Experience Cloud , installare l&#39;estensione [Chrome](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj?hl=it)&quot;Experience Cloud Debugger&quot;.

## Prima dell&#39;implementazione {#before-implementation}

**[!DNL Tracking Server]** - Se non avete ancora iniziato con l&#39;implementazione di Adobe Analytics , sceglierete un sottodominio per &quot;.sc.omtrdc.net&quot; [!DNL tracking server]. Ad esempio, supponiamo che io abbia un negozio online chiamato &quot;Jim’s Brims&quot;. Posso semplicemente impostare il mio [!DNL tracking server] su:

&quot;jimsbrims.sc.omtrdc.net&quot;.

**[!UICONTROL Report Suite]** - Per trovare un elenco dei [!UICONTROL report suites] file creati, accedete [!DNL Analytics] a [!UICONTROL Admin] > [!UICONTROL Report Suites] nel menu principale per visualizzare un elenco di [!UICONTROL report suites], con i relativi ID e titoli.

Per ulteriori informazioni, consulta il video seguente.

>[!VIDEO](https://video.tv.adobe.com/v/26061/?quality=12)
