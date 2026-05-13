---
title: Come identificare il server di tracciamento di Analytics e l’ID della suite di rapporti
description: Quando si configura Adobe Analytics, o quando vi si fa riferimento in altre soluzioni Experience Cloud, spesso è utile o addirittura necessario conoscere il “server di tracciamento” di Analytics in uso, o anche la “suite di rapporti” in cui si inviano i dati. Questo video illustra come individuare entrambi i valori, indipendentemente dal fatto che Adobe Analytics sia già stato implementato.
feature: Implementation Basics
topics: null
activity: implement
doc-type: technical video
team: Technical Marketing
kt: 2358
role: Developer
level: Beginner
exl-id: 3925026f-69f1-4425-b3a9-6fef26375fed
TQID: https://experienceleague.adobe.com/DRy-lxNuEQR9Tb-nIoev0Mu1OzSiCcLcqve1eDf7p6Q
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: 677e5a22dab92be7ff021c8410525b9091975aef
workflow-type: tm+mt
source-wordcount: 318
ht-degree: 100%

---

# Come identificare il [!DNL tracking server] e le [!UICONTROL report suite ID] di Analytics {#how-to-identify-your-analytics-tracking-server-and-report-suites}

Quando si configura Adobe Analytics, o quando vi si fa riferimento in altre soluzioni Experience Cloud, spesso è utile o addirittura necessario conoscere il “server di tracciamento” di Analytics in uso, o anche la “[!UICONTROL report suite]” in cui si inviano i dati. Questo video illustra come individuare entrambi i valori, indipendentemente dal fatto che Adobe Analytics sia già stato implementato.

>[!IMPORTANT]
>
>Questo articolo e questo video si applicano a un’implementazione “AppMeasurement” di Adobe Analytics e non a una che utilizza il Web SDK.

## Dopo l’implementazione {#after-implementation}

Dopo aver implementato Analytics su un sito, è possibile trovare il [!DNL tracking server] e la [!DNL report suite ID] direttamente nel beacon di tracciamento. Il [!DNL tracking server] corrisponde al nome host nel beacon ed è quindi facile da trovare. Gli ID [!UICONTROL report suite] sono un elenco separato da virgole subito dopo “/b/ss/” nel percorso del beacon.

Per visualizzare il beacon, così come tutte le altre informazioni che arrivano ad Analytics e altre soluzioni Experience Cloud, installa l’[estensione Chrome “Experience Cloud Debugger”](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj?hl=it).

## Prima dell’implementazione {#before-implementation}

**[!DNL Tracking server]**: se non hai ancora avviato l’implementazione di Adobe Analytics, scegli un sottodominio per “.sc.omtrdc.net” [!DNL tracking server]. Ad esempio, supponiamo che io abbia un negozio di cappelli online chiamato “Jim’s Brims”. Posso semplicemente impostare il mio [!DNL tracking server] su:

“jimsbrims.sc.omtrdc.net”.

**[!UICONTROL Report suite]**: per trovare un elenco delle [!UICONTROL report suites] create, accedi a [!DNL Analytics] e vai in [!UICONTROL Admin] > [!UICONTROL Report Suites] nel menu principale per visualizzare un elenco di [!UICONTROL report suites] con i relativi ID e titolo.

Per ulteriori informazioni, guarda il video seguente.

>[!VIDEO](https://video.tv.adobe.com/v/26061/?quality=12&learn=on)
