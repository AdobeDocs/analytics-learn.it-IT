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
role: Developer
level: Experienced
exl-id: 541c51b8-638e-43b4-90ac-0ce94290a141
TQID: https://experienceleague.adobe.com/msvft7mQiNGjLqGEezPIbwruvSbsunPGUIFF1q7vlT0
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 677e5a22dab92be7ff021c8410525b9091975aef
workflow-type: tm+mt
source-wordcount: 182
ht-degree: 74%

---

# Azioni di tracciamento (o collegamenti personalizzati) in un’app mobile con l’SDK di Experience Platform {#tracking-actions-aka-custom-links-in-a-mobile-app-with-the-experience-platform-sdk}

Le azioni sono eventi che si verificano nell’app mobile. In questo video, scopri come utilizzare l’API trackAction per tracciare e misurare un’azione.

>[!VIDEO](https://video.tv.adobe.com/v/26268/?quality=12&learn=on)

Con questa API puoi monitorare tutte le azioni nel sito (eccetto quelle di caricamento di schermate). Se una schermata viene visualizzata, puoi usare trackState, che attiva un hit di visualizzazione della pagina. Altrimenti, utilizza trackAction per inviare le variabili associate all’azione in corso.

Questi dati vengono inseriti come `contextData`, il che significa anche che sarà necessario utilizzare [!UICONTROL Processing Rules] per acquisire i dati mobili da tali variabili `contextData` e mapparli in [!DNL eVars], [!DNL Props], Eventi, ecc. in Adobe Analytics.

Per ulteriori informazioni su trackAction, consulta la [documentazione](https://developer.adobe.com/client-sdks/documentation/getting-started/track-events/#track-user-actions-for-adobe-analytics).
