---
title: 'Azioni di tracciamento (collegamenti personalizzati AKA) in un’app mobile con l’SDK del Experience Platform '
description: 'Le azioni sono eventi che si verificano nell’app mobile. In questo video, scopri come utilizzare l’API trackAction per tracciare e misurare un’azione. '
feature: mobile sdk
topics: null
audience: implementer
activity: implement
doc-type: technical video
team: Technical Marketing
kt: 2563
translation-type: tm+mt
source-git-commit: a42658cfd4bae7b077ddd48b4cf5c7db54e35c98
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 0%

---


# Azioni di tracciamento (collegamenti personalizzati AKA) in un’app mobile con l’SDK del Experience Platform  {#tracking-actions-aka-custom-links-in-a-mobile-app-with-the-experience-platform-sdk}

Le azioni sono eventi che si verificano nell’app mobile. In questo video, scopri come utilizzare l’API trackAction per tracciare e misurare un’azione.

>[!VIDEO](https://video.tv.adobe.com/v/26268/?quality=12)

Questa è l&#39;API da utilizzare per monitorare tutte le azioni non caricate sullo schermo sul sito. Se la schermata viene visualizzata, usa trackState, che attiva un hit di visualizzazione della pagina. In caso contrario, utilizza trackAction per inviare le variabili associate all’azione in corso.

Questi dati entrano come `contextData`, il che significa anche che dovrete utilizzare [!UICONTROL Processing Rules] per prendere i dati mobili da quelle `contextData` variabili e mapparli in [!DNL eVars], [!DNL Props], Eventi, ecc. in  Adobe Analytics.

Per ulteriori informazioni su trackAction, consulta la [documentazione](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/configuration-reference/mobile-core-api-reference).
