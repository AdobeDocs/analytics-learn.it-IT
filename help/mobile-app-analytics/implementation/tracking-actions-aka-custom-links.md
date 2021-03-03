---
title: Tracciamento delle azioni (collegamenti personalizzati AKA) in un’app mobile con l’SDK di Experience Platform
description: 'Le azioni sono eventi che si verificano nell''app mobile. In questo video, scopri come utilizzare l’API trackAction per tracciare e misurare un’azione. '
feature: Mobile SDK
topics: null
activity: implement
doc-type: technical video
team: Technical Marketing
kt: 2563
topic: Mobile
role: '"Sviluppatore, data engineer"'
level: Esperienza
translation-type: tm+mt
source-git-commit: f3b3fa7d91b0cb21005b57768ca23ed6700fcc03
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 1%

---


# Tracciamento delle azioni (collegamenti personalizzati AKA) in un’app mobile con l’SDK di Experience Platform {#tracking-actions-aka-custom-links-in-a-mobile-app-with-the-experience-platform-sdk}

Le azioni sono eventi che si verificano nell&#39;app mobile. In questo video, scopri come utilizzare l’API trackAction per tracciare e misurare un’azione.

>[!VIDEO](https://video.tv.adobe.com/v/26268/?quality=12)

Questa è l’API da utilizzare per monitorare tutte le azioni non caricate sullo schermo sul sito. Se la schermata è in arrivo, utilizza trackState, che attiva un hit di visualizzazione della pagina. In caso contrario, utilizza trackAction per inviare le variabili associate all&#39;azione in corso.

Questi dati vengono inseriti come `contextData`, il che significa anche che dovrai utilizzare [!UICONTROL Processing Rules] per prendere i dati mobili da quelle variabili `contextData` e mapparli in [!DNL eVars], [!DNL Props], Eventi, ecc. in Adobe Analytics.

Per ulteriori informazioni su trackAction, consulta la [documentazione](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/configuration-reference/mobile-core-api-reference).
