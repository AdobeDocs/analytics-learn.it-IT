---
title: Azioni di tracciamento (o collegamenti personalizzati) in un’app mobile con l’SDK di Experience Platform
description: Le azioni sono eventi che si verificano nell’app mobile. In questo video, scopri come utilizzare l’API trackAction per tracciare e misurare un’azione.
feature: Mobile SDK
topics: null
activity: implement
doc-type: technical video
team: Technical Marketing
kt: 2563
topic: Mobile
role: Developer, Data Engineer
level: Experienced
exl-id: 541c51b8-638e-43b4-90ac-0ce94290a141
source-git-commit: 4d467928756950074620388645523021b21fb0d5
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 99%

---

# Azioni di tracciamento (o collegamenti personalizzati) in un’app mobile con l’SDK di Experience Platform {#tracking-actions-aka-custom-links-in-a-mobile-app-with-the-experience-platform-sdk}

Le azioni sono eventi che si verificano nell’app mobile. In questo video, scopri come utilizzare l’API trackAction per tracciare e misurare un’azione.

>[!VIDEO](https://video.tv.adobe.com/v/328305/?quality=12&learn=on&captions=ita)

Con questa API puoi monitorare tutte le azioni nel sito (eccetto quelle di caricamento di schermate). Se una schermata viene visualizzata, puoi usare trackState, che attiva un hit di visualizzazione della pagina. Altrimenti, utilizza trackAction per inviare le variabili associate all’azione in corso.

Questi dati vengono inseriti come `contextData`, quindi sarà anche necessario utilizzare [!UICONTROL Processing Rules] per acquisire i dati mobili da tali variabili `contextData` e mapparli in [!DNL eVars], [!DNL Props], Eventi, ecc. in Adobe Analytics.

Per ulteriori informazioni su trackAction, consulta la [documentazione](https://developer.adobe.com/client-sdks/documentation/getting-started/track-events/#track-user-actions-for-adobe-analytics).
