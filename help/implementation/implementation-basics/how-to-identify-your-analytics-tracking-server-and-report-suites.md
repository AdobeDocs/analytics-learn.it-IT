---
title: Come identificare il server di tracciamento di Analytics e le suite di rapporti
description: Quando si configura Adobe Analytics, o quando vi si fa riferimento in altre soluzioni Experience Cloud, spesso è utile o addirittura necessario conoscere il “server di tracciamento” di Analytics in uso, o anche la “suite di rapporti” in cui si inviano i dati. Questo video illustra come individuare entrambi i valori, indipendentemente dal fatto che Adobe Analytics sia già stato implementato.
feature: Implementation Basics
topics: null
activity: implement
doc-type: technical video
team: Technical Marketing
kt: 2358
role: "Developer, Data Engineer"
level: Beginner
translation-type: ht
source-git-commit: f3b3fa7d91b0cb21005b57768ca23ed6700fcc03
workflow-type: ht
source-wordcount: '294'
ht-degree: 100%

---


# Come identificare il [!DNL Tracking Server] e le [!UICONTROL Report Suites] di Analytics {#how-to-identify-your-analytics-tracking-server-and-report-suites}

Quando si configura Adobe Analytics, o quando vi si fa riferimento in altre soluzioni Experience Cloud, spesso è utile o addirittura necessario conoscere il [!DNL Analytics] “[!DNL Tracking Server]” in uso, o anche la “[!UICONTROL Report Suite]” in cui si inviano i dati. Questo video illustra come individuare entrambi i valori, indipendentemente dal fatto che Adobe Analytics sia già stato implementato.

## Dopo l’implementazione {#after-implementation}

Dopo aver implementato [!DNL Analytics] su un sito, è possibile trovare il [!DNL tracking server] e la [!DNL report suite ID] direttamente nel beacon di tracciamento. Il [!DNL tracking server] corrisponde al nome host nel beacon ed è quindi facile da trovare. Gli ID [!UICONTROL report suite] sono un elenco separato da virgole subito dopo “/b/ss/” nel percorso del beacon.

Per visualizzare il beacon, così come tutte le altre informazioni che arrivano a [!DNL Analytics] e altre soluzioni Experience Cloud, installa l’[estensione Chrome “Experience Cloud Debugger”](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj?hl=it).

## Prima dell’implementazione {#before-implementation}

**[!DNL Tracking Server]**: se non hai ancora avviato l’implementazione di Adobe Analytics, scegli un sottodominio per “.sc.omtrdc.net” [!DNL tracking server]. Ad esempio, supponiamo che io abbia un negozio online chiamato “Jim’s Brims”. Posso semplicemente impostare il mio [!DNL tracking server] su:

“jimsbrims.sc.omtrdc.net”.

**[!UICONTROL Report Suite]**: per trovare un elenco delle [!UICONTROL report suites] create, accedi a [!DNL Analytics] e vai in [!UICONTROL Admin] > [!UICONTROL Report Suites] nel menu principale per visualizzare un elenco di [!UICONTROL report suites] con i relativi ID e titolo.

Per ulteriori informazioni, guarda il video seguente.

>[!VIDEO](https://video.tv.adobe.com/v/26061/?quality=12)
