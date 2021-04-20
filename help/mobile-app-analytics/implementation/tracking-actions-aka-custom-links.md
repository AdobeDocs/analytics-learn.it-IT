---
title: Azioni di tracciamento (o collegamenti personalizzati) in un’app mobile con l’SDK di Experience Platform
description: 'Le azioni sono eventi che si verificano nell’app mobile. In questo video, scopri come utilizzare l’API trackAction per tracciare e misurare un’azione. '
feature: Mobile SDK
topics: null
activity: implement
doc-type: technical video
team: Technical Marketing
kt: 2563
topic: Mobile
role: "Developer, Data Engineer"
level: Experienced
translation-type: ht
source-git-commit: f3b3fa7d91b0cb21005b57768ca23ed6700fcc03
workflow-type: ht
source-wordcount: '179'
ht-degree: 100%

---


# Azioni di tracciamento (o collegamenti personalizzati) in un’app mobile con l’SDK di Experience Platform {#tracking-actions-aka-custom-links-in-a-mobile-app-with-the-experience-platform-sdk}

Le azioni sono eventi che si verificano nell’app mobile. In questo video, scopri come utilizzare l’API trackAction per tracciare e misurare un’azione.

>[!VIDEO](https://video.tv.adobe.com/v/26268/?quality=12)

Con questa API puoi monitorare tutte le azioni nel sito (eccetto quelle di caricamento di schermate). Se una schermata viene visualizzata, puoi usare trackState, che attiva un hit di visualizzazione della pagina. Altrimenti, utilizza trackAction per inviare le variabili associate all’azione in corso.

Questi dati vengono inseriti come `contextData`, quindi sarà anche necessario utilizzare [!UICONTROL Processing Rules] per acquisire i dati mobili da tali variabili `contextData` e mapparli in [!DNL eVars], [!DNL Props], Eventi, ecc. in Adobe Analytics.

Per ulteriori informazioni su trackAction, consulta la [documentazione](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/configuration-reference/mobile-core-api-reference).
